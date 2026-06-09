# arrow::io::BufferReader::DoGetSize(void)

- ea: `0x18009ecf0`
- end: `0x18009edf6`
- name: `?DoGetSize@BufferReader@io@arrow@@IEAA?AV?$Result@_J@3@XZ`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18009fc70`

## callees

- `0x18001f8c0`
- `0x180059010`
- `0x180086ed0`
- `0x18009a010`
- `0x18009ecf0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x18009ed27`: `Operation forbidden on closed BufferReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::io::BufferReader::DoGetSize(__int64 a1, __int64 a2)
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
    *(_QWORD *)(a2 + 16) = *(_QWORD *)(a1 + 88);
  }
  return a2;
}

```

## disassembly

```asm
0x18009ecf0  push    rdi
0x18009ecf2  sub     rsp, 70h
0x18009ecf6  mov     [rsp+78h+var_38], 0FFFFFFFFFFFFFFFEh
0x18009ecff  mov     [rsp+78h+arg_0], rbx
0x18009ed07  mov     rax, cs:__security_cookie
0x18009ed0e  xor     rax, rsp
0x18009ed11  mov     [rsp+78h+var_10], rax
0x18009ed16  mov     rbx, rdx
0x18009ed19  mov     rdi, rcx
0x18009ed1c  mov     [rsp+78h+var_58], rdx
0x18009ed21  cmp     byte ptr [rcx+68h], 0
0x18009ed25  jnz     short loc_18009ED89
0x18009ed27  lea     rdx, aOperationForbi; "Operation forbidden on closed BufferRea"...
0x18009ed2e  lea     rcx, [rsp+78h+var_30]
0x18009ed33  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x18009ed38  nop
0x18009ed39  mov     r8, rax
0x18009ed3c  mov     dl, 4
0x18009ed3e  lea     rcx, [rsp+78h+var_58]
0x18009ed43  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x18009ed48  nop
0x18009ed49  mov     rdx, [rsp+78h+var_18]
0x18009ed4e  cmp     rdx, 10h
0x18009ed52  jb      short loc_18009ED82
0x18009ed54  inc     rdx
0x18009ed57  mov     rcx, [rsp+78h+var_30]
0x18009ed5c  mov     rax, rcx
0x18009ed5f  cmp     rdx, 1000h
0x18009ed66  jb      short loc_18009ED7D
0x18009ed68  add     rdx, 27h ; '''; unsigned __int64
0x18009ed6c  mov     rcx, [rcx-8]; void *
0x18009ed70  sub     rax, rcx
0x18009ed73  add     rax, 0FFFFFFFFFFFFFFF8h
0x18009ed77  cmp     rax, 1Fh
0x18009ed7b  ja      short loc_18009EDF0
0x18009ed7d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009ed82  mov     rax, [rsp+78h+var_50]
0x18009ed87  jmp     short loc_18009ED8B
0x18009ed89  xor     eax, eax
0x18009ed8b  mov     [rsp+78h+var_40], rax
0x18009ed90  mov     [rsp+78h+var_50], 0
0x18009ed99  test    rax, rax
0x18009ed9c  jz      short loc_18009EDC2
0x18009ed9e  lea     rdx, [rsp+78h+var_48]
0x18009eda3  mov     rcx, rbx
0x18009eda6  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x18009edab  nop
0x18009edac  mov     rcx, [rsp+78h+var_40]; this
0x18009edb1  test    rcx, rcx
0x18009edb4  jz      short loc_18009EDD2
0x18009edb6  mov     edx, 1; unsigned int
0x18009edbb  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009edc0  jmp     short loc_18009EDD2
0x18009edc2  mov     qword ptr [rbx+8], 0
0x18009edca  mov     rax, [rdi+58h]
0x18009edce  mov     [rbx+10h], rax
0x18009edd2  mov     rax, rbx
0x18009edd5  mov     rcx, [rsp+78h+var_10]
0x18009edda  xor     rcx, rsp; StackCookie
0x18009eddd  call    __security_check_cookie
0x18009ede2  mov     rbx, [rsp+78h+arg_0]
0x18009edea  add     rsp, 70h
0x18009edee  pop     rdi
0x18009edef  retn
0x18009edf0  call    _invalid_parameter_noinfo_noreturn
```
