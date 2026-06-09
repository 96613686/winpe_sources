# _wctomb_internal

- ea: `0x180057e0c`
- end: `0x180057fbc`
- name: `_wctomb_internal`
- size: `432`
- prototype: ``
- caller_count: `23`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180049434`
- `0x18004996c`
- `0x180049ebc`
- `0x18004a3f4`
- `0x18004a864`
- `0x18004ad14`
- `0x18004fc80`
- `0x18004fd54`
- `0x18004fe70`
- `0x18004ff44`
- `0x180050018`
- `0x180050134`
- `0x180053f2c`
- `0x180054118`
- `0x180054304`
- `0x1800544f0`
- `0x180054690`
- `0x180054830`
- `0x180057fbc`
- `0x1800580a8`
- `0x180058158`
- `0x180058220`
- `0x1800585c8`

## callees

- `0x1800073e8`
- `0x18000b034`
- `0x1800149cc`
- `0x180057e0c`
- `0x18005c4b4`
- `0x180060270`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180057f6a`
- `KERNEL32!GetLastError` at `0x180057f6a`

## pseudocode

```c
__int64 __fastcall wctomb_internal(int *a1, _BYTE *a2, size_t a3, unsigned __int16 a4, struct _Mbstatet *a5)
{
  unsigned int v5; // ebx
  struct _Mbstatet *v9; // rdi
  unsigned int v10; // esi
  struct _Mbstatet v11; // rax
  int v12; // ecx
  int v13; // eax
  __int64 result; // rax
  int v15; // eax
  __int64 v16; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int16 v17; // [rsp+78h] [rbp+20h] BYREF

  v17 = a4;
  v5 = 0;
  if ( !a2 && a3 )
  {
    if ( a1 )
      *a1 = 0;
    return 0;
  }
  if ( a1 )
    *a1 = -1;
  v9 = a5;
  if ( a3 > 0x7FFFFFFF )
  {
    v10 = 22;
LABEL_39:
    *(_DWORD *)&v9[5]._Byte = v10;
    LOBYTE(v9[6]._Wchar) = 1;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)v9);
    return v10;
  }
  if ( !LOBYTE(a5[5]._Wchar) )
  {
    __crt_cached_ptd_host::update_locale_slow((__crt_cached_ptd_host *)a5);
    a4 = v17;
  }
  v11 = v9[3];
  v12 = *(_DWORD *)(*(_QWORD *)&v11 + 12LL);
  if ( v12 != 65001 )
  {
    if ( !*(_QWORD *)(*(_QWORD *)&v11 + 312LL) )
    {
      if ( a4 > 0xFFu )
      {
        if ( a2 && a3 )
          memset(a2, 0, a3);
        goto LABEL_23;
      }
      if ( !a2 )
      {
LABEL_27:
        if ( a1 )
          *a1 = 1;
        return 0;
      }
      if ( a3 )
      {
        *a2 = a4;
        goto LABEL_27;
      }
LABEL_38:
      v10 = 34;
      goto LABEL_39;
    }
    LODWORD(v16) = 0;
    v15 = _acrt_WideCharToMultiByte(v12, 0, (unsigned int)&v17, 1, (_DWORD)a2, a3, 0, (__int64)&v16);
    if ( v15 )
    {
      if ( !(_DWORD)v16 )
      {
        if ( a1 )
          *a1 = v15;
        return 0;
      }
    }
    else if ( GetLastError() == 122 )
    {
      if ( a2 && a3 )
        memset(a2, 0, a3);
      goto LABEL_38;
    }
LABEL_23:
    result = 42;
    *(_DWORD *)&v9[5]._Byte = 42;
    LOBYTE(v9[6]._Wchar) = 1;
    return result;
  }
  v16 = 0;
  v13 = __crt_mbstring::__c32rtomb_utf8((__crt_mbstring *)a2, (char *)a4, (__crt_mbstring *)&v16, v9);
  if ( a1 )
    *a1 = v13;
  if ( v13 <= 4 )
    return 0;
  if ( LOBYTE(v9[6]._Wchar) )
    return *(unsigned int *)&v9[5]._Byte;
  return v5;
}

```

## disassembly

```asm
0x180057e0c  mov     [rsp+arg_0], rbx
0x180057e11  mov     [rsp+arg_10], rbp
0x180057e16  mov     [rsp+arg_18], r9w
0x180057e1c  push    rsi
0x180057e1d  push    rdi
0x180057e1e  push    r14
0x180057e20  sub     rsp, 40h
0x180057e24  xor     ebx, ebx
0x180057e26  mov     rbp, r8
0x180057e29  mov     r14, rdx
0x180057e2c  mov     rsi, rcx
0x180057e2f  test    rdx, rdx
0x180057e32  jnz     short loc_180057E49
0x180057e34  test    r8, r8
0x180057e37  jz      short loc_180057E49
0x180057e39  test    rcx, rcx
0x180057e3c  jz      loc_180057F66
0x180057e42  mov     [rcx], ebx
0x180057e44  jmp     loc_180057F66
0x180057e49  test    rsi, rsi
0x180057e4c  jz      short loc_180057E51
0x180057e4e  or      dword ptr [rcx], 0FFFFFFFFh
0x180057e51  mov     rdi, [rsp+58h+arg_20]
0x180057e59  cmp     rbp, 7FFFFFFFh
0x180057e60  jbe     short loc_180057E6C
0x180057e62  mov     esi, 16h
0x180057e67  jmp     loc_180057F95
0x180057e6c  cmp     [rdi+28h], bl
0x180057e6f  jnz     short loc_180057E7F
0x180057e71  mov     rcx, rdi; this
0x180057e74  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180057e79  movzx   r9d, [rsp+58h+arg_18]
0x180057e7f  mov     rax, [rdi+18h]
0x180057e83  mov     ecx, [rax+0Ch]
0x180057e86  cmp     ecx, 0FDE9h
0x180057e8c  jnz     short loc_180057EC3
0x180057e8e  movzx   edx, r9w; char *
0x180057e92  lea     r8, [rsp+58h+arg_8]; char32_t
0x180057e97  mov     r9, rdi; struct _Mbstatet *
0x180057e9a  mov     [rsp+58h+arg_8], rbx
0x180057e9f  mov     rcx, r14; this
0x180057ea2  call    ?__c32rtomb_utf8@__crt_mbstring@@YA_KPEAD_UPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c32rtomb_utf8(char *,char32_t,_Mbstatet *,__crt_cached_ptd_host &)
0x180057ea7  test    rsi, rsi
0x180057eaa  jz      short loc_180057EAE
0x180057eac  mov     [rsi], eax
0x180057eae  cmp     eax, 4
0x180057eb1  jle     loc_180057F66
0x180057eb7  cmp     [rdi+30h], bl
0x180057eba  jz      short loc_180057EBF
0x180057ebc  mov     ebx, [rdi+2Ch]
0x180057ebf  mov     eax, ebx
0x180057ec1  jmp     short loc_180057EFA
0x180057ec3  cmp     [rax+138h], rbx
0x180057eca  jnz     short loc_180057F27
0x180057ecc  mov     eax, 0FFh
0x180057ed1  cmp     r9w, ax
0x180057ed5  jbe     short loc_180057F0D
0x180057ed7  test    r14, r14
0x180057eda  jz      short loc_180057EEE
0x180057edc  test    rbp, rbp
0x180057edf  jz      short loc_180057EEE
0x180057ee1  mov     r8, rbp; Size
0x180057ee4  xor     edx, edx; Val
0x180057ee6  mov     rcx, r14; void *
0x180057ee9  call    memset
0x180057eee  mov     eax, 2Ah ; '*'
0x180057ef3  mov     [rdi+2Ch], eax
0x180057ef6  mov     byte ptr [rdi+30h], 1
0x180057efa  mov     rbx, [rsp+58h+arg_0]
0x180057eff  mov     rbp, [rsp+58h+arg_10]
0x180057f04  add     rsp, 40h
0x180057f08  pop     r14
0x180057f0a  pop     rdi
0x180057f0b  pop     rsi
0x180057f0c  retn
0x180057f0d  test    r14, r14
0x180057f10  jz      short loc_180057F1A
0x180057f12  test    rbp, rbp
0x180057f15  jz      short loc_180057F90
0x180057f17  mov     [r14], r9b
0x180057f1a  test    rsi, rsi
0x180057f1d  jz      short loc_180057F66
0x180057f1f  mov     dword ptr [rsi], 1
0x180057f25  jmp     short loc_180057F66
0x180057f27  lea     rax, [rsp+58h+arg_8]
0x180057f2c  mov     dword ptr [rsp+58h+arg_8], ebx
0x180057f30  mov     [rsp+58h+var_20], rax
0x180057f35  lea     r8, [rsp+58h+arg_18]
0x180057f3a  mov     [rsp+58h+var_28], rbx
0x180057f3f  mov     r9d, 1
0x180057f45  mov     dword ptr [rsp+58h+var_30], ebp
0x180057f49  xor     edx, edx
0x180057f4b  mov     [rsp+58h+var_38], r14
0x180057f50  call    __acrt_WideCharToMultiByte
0x180057f55  test    eax, eax
0x180057f57  jz      short loc_180057F6A
0x180057f59  cmp     dword ptr [rsp+58h+arg_8], ebx
0x180057f5d  jnz     short loc_180057EEE
0x180057f5f  test    rsi, rsi
0x180057f62  jz      short loc_180057F66
0x180057f64  mov     [rsi], eax
0x180057f66  xor     eax, eax
0x180057f68  jmp     short loc_180057EFA
0x180057f6a  call    cs:__imp_GetLastError
0x180057f70  cmp     eax, 7Ah ; 'z'
0x180057f73  jnz     loc_180057EEE
0x180057f79  test    r14, r14
0x180057f7c  jz      short loc_180057F90
0x180057f7e  test    rbp, rbp
0x180057f81  jz      short loc_180057F90
0x180057f83  mov     r8, rbp; Size
0x180057f86  xor     edx, edx; Val
0x180057f88  mov     rcx, r14; void *
0x180057f8b  call    memset
0x180057f90  mov     esi, 22h ; '"'
0x180057f95  mov     [rdi+2Ch], esi
0x180057f98  xor     r9d, r9d; LineNo
0x180057f9b  mov     [rsp+58h+var_30], rdi; __crt_cached_ptd_host *
0x180057fa0  xor     r8d, r8d; FileName
0x180057fa3  xor     edx, edx; FunctionName
0x180057fa5  mov     byte ptr [rdi+30h], 1
0x180057fa9  xor     ecx, ecx; Expression
0x180057fab  mov     [rsp+58h+var_38], rbx; uintptr_t
0x180057fb0  call    _invalid_parameter_internal
0x180057fb5  mov     eax, esi
0x180057fb7  jmp     loc_180057EFA
```
