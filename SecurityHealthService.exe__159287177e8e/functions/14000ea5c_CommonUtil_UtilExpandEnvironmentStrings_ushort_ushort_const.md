# CommonUtil::UtilExpandEnvironmentStrings(ushort * *,ushort const *)

- ea: `0x14000ea5c`
- end: `0x14000eb74`
- name: `?UtilExpandEnvironmentStrings@CommonUtil@@YAJPEAPEAGPEBG@Z`
- size: `280`
- prototype: `int __fastcall(CommonUtil *this, unsigned __int16 **, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140003a94`
- `0x140006008`

## callees

- `0x1400015d0`
- `0x1400015f4`
- `0x140005578`
- `0x14000e6e4`
- `0x14000ea5c`
- `0x1400100bc`

## pseudocode

```c
int __fastcall CommonUtil::UtilExpandEnvironmentStrings(
        CommonUtil *this,
        unsigned __int16 **a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int result; // eax
  const unsigned __int16 *v7; // r8
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rdx
  int v10; // ebx
  unsigned __int16 *v11; // r9
  void *v12; // rbx
  unsigned __int64 v13; // rdx
  int v14; // esi
  unsigned __int16 v15[4]; // [rsp+20h] [rbp-E0h] BYREF
  void *v16; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v17[66]; // [rsp+30h] [rbp-D0h] BYREF

  *(_QWORD *)v15 = 260;
  result = CommonUtil::HrExpandEnvironmentStrings((CommonUtil *)a2, v15, (unsigned __int64 *)v17, a4);
  if ( result >= 0 )
  {
    v8 = *(_QWORD *)v15;
    if ( *(_QWORD *)v15 > 0x104u )
    {
      while ( 1 )
      {
        v16 = 0;
        v10 = CommonUtil::MpNewBuffer<unsigned short>(&v16, v8, v7);
        if ( v10 < 0 )
          break;
        v12 = v16;
        *(_QWORD *)v15 = v8;
        v14 = CommonUtil::HrExpandEnvironmentStrings((CommonUtil *)a2, v15, (unsigned __int64 *)v16, v11);
        if ( v14 < 0 )
        {
          if ( v12 )
            operator delete(v12, v13);
          return v14;
        }
        if ( *(_QWORD *)v15 <= v8 )
        {
          *(_QWORD *)this = v12;
          return 0;
        }
        v8 = *(_QWORD *)v15;
        if ( v12 )
          operator delete(v12, v13);
      }
      if ( v16 )
        operator delete(v16, v9);
      return v10;
    }
    else
    {
      return CommonUtil::HrDuplicateStringW(this, v17, v7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000ea5c  mov     [rsp-8+arg_10], rbx
0x14000ea61  push    rbp
0x14000ea62  push    rsi
0x14000ea63  push    rdi
0x14000ea64  push    r14
0x14000ea66  push    r15
0x14000ea68  lea     rbp, [rsp-150h]
0x14000ea70  sub     rsp, 250h
0x14000ea77  mov     rax, cs:__security_cookie
0x14000ea7e  xor     rax, rsp
0x14000ea81  mov     [rbp+170h+var_30], rax
0x14000ea88  mov     r15, rdx
0x14000ea8b  lea     r8, [rsp+270h+var_240]; unsigned __int64 *
0x14000ea90  mov     r14, rcx
0x14000ea93  lea     rdx, [rsp+270h+var_250]; unsigned __int16 *
0x14000ea98  mov     ebx, 104h
0x14000ea9d  mov     rcx, r15; this
0x14000eaa0  mov     qword ptr [rsp+270h+var_250], rbx
0x14000eaa5  call    ?HrExpandEnvironmentStrings@CommonUtil@@YAJPEBGPEA_KPEAG@Z; CommonUtil::HrExpandEnvironmentStrings(ushort const *,unsigned __int64 *,ushort *)
0x14000eaaa  test    eax, eax
0x14000eaac  js      loc_14000EB4E
0x14000eab2  mov     rdi, qword ptr [rsp+270h+var_250]
0x14000eab7  cmp     rdi, rbx
0x14000eaba  ja      short loc_14000EACE
0x14000eabc  lea     rdx, [rsp+270h+var_240]; unsigned __int16 **
0x14000eac1  mov     rcx, r14; this
0x14000eac4  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x14000eac9  jmp     loc_14000EB4E
0x14000eace  mov     rdx, rdi
0x14000ead1  mov     [rsp+270h+var_248], 0
0x14000eada  lea     rcx, [rsp+270h+var_248]
0x14000eadf  call    ??$MpNewBuffer@G@CommonUtil@@YAJPEAPEAG_K@Z; CommonUtil::MpNewBuffer<ushort>(ushort * *,unsigned __int64)
0x14000eae4  mov     ebx, eax
0x14000eae6  test    eax, eax
0x14000eae8  js      short loc_14000EB3D
0x14000eaea  mov     rbx, [rsp+270h+var_248]
0x14000eaef  lea     rdx, [rsp+270h+var_250]; unsigned __int16 *
0x14000eaf4  mov     r8, rbx; unsigned __int64 *
0x14000eaf7  mov     qword ptr [rsp+270h+var_250], rdi
0x14000eafc  mov     rcx, r15; this
0x14000eaff  call    ?HrExpandEnvironmentStrings@CommonUtil@@YAJPEBGPEA_KPEAG@Z; CommonUtil::HrExpandEnvironmentStrings(ushort const *,unsigned __int64 *,ushort *)
0x14000eb04  mov     esi, eax
0x14000eb06  test    eax, eax
0x14000eb08  js      short loc_14000EB2C
0x14000eb0a  cmp     qword ptr [rsp+270h+var_250], rdi
0x14000eb0f  jbe     short loc_14000EB25
0x14000eb11  mov     rdi, qword ptr [rsp+270h+var_250]
0x14000eb16  test    rbx, rbx
0x14000eb19  jz      short loc_14000EACE
0x14000eb1b  mov     rcx, rbx; void *
0x14000eb1e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000eb23  jmp     short loc_14000EACE
0x14000eb25  mov     [r14], rbx
0x14000eb28  xor     eax, eax
0x14000eb2a  jmp     short loc_14000EB4E
0x14000eb2c  test    rbx, rbx
0x14000eb2f  jz      short loc_14000EB39
0x14000eb31  mov     rcx, rbx; void *
0x14000eb34  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000eb39  mov     eax, esi
0x14000eb3b  jmp     short loc_14000EB4E
0x14000eb3d  mov     rcx, [rsp+270h+var_248]; void *
0x14000eb42  test    rcx, rcx
0x14000eb45  jz      short loc_14000EB4C
0x14000eb47  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000eb4c  mov     eax, ebx
0x14000eb4e  mov     rcx, [rbp+170h+var_30]
0x14000eb55  xor     rcx, rsp; StackCookie
0x14000eb58  call    __security_check_cookie
0x14000eb5d  mov     rbx, [rsp+270h+arg_10]
0x14000eb65  add     rsp, 250h
0x14000eb6c  pop     r15
0x14000eb6e  pop     r14
0x14000eb70  pop     rdi
0x14000eb71  pop     rsi
0x14000eb72  pop     rbp
0x14000eb73  retn
```
