# arrow::io::BufferReader::DoTell(void)

- ea: `0x18009fa60`
- end: `0x18009fb66`
- name: `?DoTell@BufferReader@io@arrow@@IEBA?AV?$Result@_J@3@XZ`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800a0760`

## callees

- `0x18001f8c0`
- `0x180059010`
- `0x180086ed0`
- `0x18009a010`
- `0x18009fa60`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x18009fa97`: `Operation forbidden on closed BufferReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::io::BufferReader::DoTell(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  __int64 v5; // rdx
  unsigned __int64 v6; // rdx
  _BYTE *v7; // rcx
  arrow::Status::State *v8; // rax
  __int64 v10; // [rsp+20h] [rbp-58h] BYREF
  arrow::Status::State *v11; // [rsp+28h] [rbp-50h]
  char v12[8]; // [rsp+30h] [rbp-48h] BYREF
  arrow::Status::State *v13; // [rsp+38h] [rbp-40h]
  __int64 v14; // [rsp+40h] [rbp-38h]
  _BYTE *v15; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int64 v16; // [rsp+60h] [rbp-18h]

  v14 = -2;
  v10 = a2;
  if ( *(_BYTE *)(a1 + 104) )
  {
    v8 = 0;
  }
  else
  {
    v4 = arrow::util::StringBuilder<char const (&)[13]>(&v15, "Operation forbidden on closed BufferReader");
    LOBYTE(v5) = 4;
    arrow::Status::Status(&v10, v5, v4);
    if ( v16 >= 0x10 )
    {
      v6 = v16 + 1;
      v7 = v15;
      if ( v16 + 1 >= 0x1000 )
      {
        v6 = v16 + 40;
        v7 = (_BYTE *)*((_QWORD *)v15 - 1);
        if ( (unsigned __int64)(v15 - v7 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v7, v6);
    }
    v8 = v11;
  }
  v13 = v8;
  v11 = 0;
  if ( v8 )
  {
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v12);
    if ( v13 )
      arrow::Status::State::`scalar deleting destructor'(v13, 1u);
  }
  else
  {
    *(_QWORD *)(a2 + 8) = 0;
    *(_QWORD *)(a2 + 16) = *(_QWORD *)(a1 + 96);
  }
  return a2;
}

```

## disassembly

```asm
0x18009fa60  push    rdi
0x18009fa62  sub     rsp, 70h
0x18009fa66  mov     [rsp+78h+var_38], 0FFFFFFFFFFFFFFFEh
0x18009fa6f  mov     [rsp+78h+arg_0], rbx
0x18009fa77  mov     rax, cs:__security_cookie
0x18009fa7e  xor     rax, rsp
0x18009fa81  mov     [rsp+78h+var_10], rax
0x18009fa86  mov     rbx, rdx
0x18009fa89  mov     rdi, rcx
0x18009fa8c  mov     [rsp+78h+var_58], rdx
0x18009fa91  cmp     byte ptr [rcx+68h], 0
0x18009fa95  jnz     short loc_18009FAF9
0x18009fa97  lea     rdx, aOperationForbi; "Operation forbidden on closed BufferRea"...
0x18009fa9e  lea     rcx, [rsp+78h+var_30]
0x18009faa3  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x18009faa8  nop
0x18009faa9  mov     r8, rax
0x18009faac  mov     dl, 4
0x18009faae  lea     rcx, [rsp+78h+var_58]
0x18009fab3  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x18009fab8  nop
0x18009fab9  mov     rdx, [rsp+78h+var_18]
0x18009fabe  cmp     rdx, 10h
0x18009fac2  jb      short loc_18009FAF2
0x18009fac4  inc     rdx
0x18009fac7  mov     rcx, [rsp+78h+var_30]
0x18009facc  mov     rax, rcx
0x18009facf  cmp     rdx, 1000h
0x18009fad6  jb      short loc_18009FAED
0x18009fad8  add     rdx, 27h ; '''; unsigned __int64
0x18009fadc  mov     rcx, [rcx-8]; void *
0x18009fae0  sub     rax, rcx
0x18009fae3  add     rax, 0FFFFFFFFFFFFFFF8h
0x18009fae7  cmp     rax, 1Fh
0x18009faeb  ja      short loc_18009FB60
0x18009faed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009faf2  mov     rax, [rsp+78h+var_50]
0x18009faf7  jmp     short loc_18009FAFB
0x18009faf9  xor     eax, eax
0x18009fafb  mov     [rsp+78h+var_40], rax
0x18009fb00  mov     [rsp+78h+var_50], 0
0x18009fb09  test    rax, rax
0x18009fb0c  jz      short loc_18009FB32
0x18009fb0e  lea     rdx, [rsp+78h+var_48]
0x18009fb13  mov     rcx, rbx
0x18009fb16  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x18009fb1b  nop
0x18009fb1c  mov     rcx, [rsp+78h+var_40]; this
0x18009fb21  test    rcx, rcx
0x18009fb24  jz      short loc_18009FB42
0x18009fb26  mov     edx, 1; unsigned int
0x18009fb2b  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009fb30  jmp     short loc_18009FB42
0x18009fb32  mov     qword ptr [rbx+8], 0
0x18009fb3a  mov     rax, [rdi+60h]
0x18009fb3e  mov     [rbx+10h], rax
0x18009fb42  mov     rax, rbx
0x18009fb45  mov     rcx, [rsp+78h+var_10]
0x18009fb4a  xor     rcx, rsp; StackCookie
0x18009fb4d  call    __security_check_cookie
0x18009fb52  mov     rbx, [rsp+78h+arg_0]
0x18009fb5a  add     rsp, 70h
0x18009fb5e  pop     rdi
0x18009fb5f  retn
0x18009fb60  call    _invalid_parameter_noinfo_noreturn
```
