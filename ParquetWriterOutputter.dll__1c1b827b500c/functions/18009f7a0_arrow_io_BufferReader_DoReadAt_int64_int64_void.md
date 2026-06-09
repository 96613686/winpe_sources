# arrow::io::BufferReader::DoReadAt(__int64,__int64,void *)

- ea: `0x18009f7a0`
- end: `0x18009f95e`
- name: `?DoReadAt@BufferReader@io@arrow@@IEAA?AV?$Result@_J@3@_J0PEAX@Z`
- size: `446`
- prototype: `__int64 __fastcall(int, int, int, int, void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18009f1b0`
- `0x1800a02b0`

## callees

- `0x18001d5b0`
- `0x18001f8c0`
- `0x180059010`
- `0x180086ed0`
- `0x1800973c0`
- `0x18009a010`
- `0x18009a530`
- `0x18009f7a0`
- `0x18030c180`
- `0x18030c3f0`
- `0x18032ab90`
- `0x180334640`

## string_xrefs

- `0x18009f7ea`: `Operation forbidden on closed BufferReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall arrow::io::BufferReader::DoReadAt(__int64 a1, __int64 a2, __int64 a3, __int64 a4, void *a5)
{
  __int64 v9; // r8
  __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  _BYTE *v12; // rcx
  arrow::Status::State *v13; // rax
  arrow::Status::State *v14; // rcx
  const struct arrow::Status *Range; // rax
  size_t v16; // rdi
  __int64 v18; // [rsp+20h] [rbp-51h] BYREF
  arrow::Status::State *v19; // [rsp+28h] [rbp-49h]
  __int64 v20; // [rsp+30h] [rbp-41h]
  char v21[8]; // [rsp+38h] [rbp-39h] BYREF
  arrow::Status::State *v22; // [rsp+40h] [rbp-31h]
  size_t Size; // [rsp+48h] [rbp-29h]
  char v24[8]; // [rsp+50h] [rbp-21h] BYREF
  arrow::Status::State *v25; // [rsp+58h] [rbp-19h]
  _BYTE *v26; // [rsp+68h] [rbp-9h] BYREF
  unsigned __int64 v27; // [rsp+80h] [rbp+Fh]

  v20 = -2;
  v18 = a2;
  if ( *(_BYTE *)(a1 + 104) )
  {
    v13 = 0;
  }
  else
  {
    v9 = arrow::util::StringBuilder<char const (&)[13]>(&v26, "Operation forbidden on closed BufferReader");
    LOBYTE(v10) = 4;
    arrow::Status::Status(&v18, v10, v9);
    if ( v27 >= 0x10 )
    {
      v11 = v27 + 1;
      v12 = v26;
      if ( v27 + 1 >= 0x1000 )
      {
        v11 = v27 + 40;
        v12 = (_BYTE *)*((_QWORD *)v26 - 1);
        if ( (unsigned __int64)(v26 - v12 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v12, v11);
    }
    v13 = v19;
  }
  v25 = v13;
  v19 = 0;
  if ( v13 )
  {
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v24);
    v14 = v25;
  }
  else
  {
    Range = (const struct arrow::Status *)arrow::io::internal::ValidateReadRange(
                                            (__int64)v24,
                                            a3,
                                            a4,
                                            *(_QWORD *)(a1 + 88));
    v22 = 0;
    if ( *((_QWORD *)Range + 1) )
    {
      arrow::Status::CopyFrom((arrow::Status *)v21, Range);
    }
    else
    {
      v22 = 0;
      *((_QWORD *)Range + 1) = 0;
      Size = *((_QWORD *)Range + 2);
    }
    if ( v25 )
    {
      arrow::Status::State::`scalar deleting destructor'(v25, 1u);
      v25 = 0;
    }
    arrow::Status::Status((arrow::Status *)&v18, (const struct arrow::Status *)v21);
    if ( v19 )
    {
      arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, &v18);
      if ( v19 )
      {
        arrow::Status::State::`scalar deleting destructor'(v19, 1u);
        v19 = 0;
      }
    }
    else
    {
      v16 = Size;
      if ( Size )
        memmove(a5, (const void *)(a3 + *(_QWORD *)(a1 + 80)), Size);
      *(_QWORD *)(a2 + 8) = 0;
      *(_QWORD *)(a2 + 16) = v16;
    }
    v14 = v22;
  }
  if ( v14 )
    arrow::Status::State::`scalar deleting destructor'(v14, 1u);
  return a2;
}

```

## disassembly

```asm
0x18009f7a0  push    rbp
0x18009f7a2  push    rbx
0x18009f7a3  push    rsi
0x18009f7a4  push    rdi
0x18009f7a5  push    r12
0x18009f7a7  push    r14
0x18009f7a9  push    r15
0x18009f7ab  lea     rbp, [rsp-1Fh]
0x18009f7b0  sub     rsp, 90h
0x18009f7b7  mov     [rbp+4Fh+var_90], 0FFFFFFFFFFFFFFFEh
0x18009f7bf  mov     rax, cs:__security_cookie
0x18009f7c6  xor     rax, rsp
0x18009f7c9  mov     [rbp+4Fh+var_38], rax
0x18009f7cd  mov     rdi, r9
0x18009f7d0  mov     r14, r8
0x18009f7d3  mov     rbx, rdx
0x18009f7d6  mov     rsi, rcx
0x18009f7d9  mov     [rbp+4Fh+var_A0], rdx
0x18009f7dd  mov     r15, [rbp+4Fh+arg_20]
0x18009f7e1  xor     r12d, r12d
0x18009f7e4  cmp     [rcx+68h], r12b
0x18009f7e8  jnz     short loc_18009F84B
0x18009f7ea  lea     rdx, aOperationForbi; "Operation forbidden on closed BufferRea"...
0x18009f7f1  lea     rcx, [rbp+4Fh+var_58]
0x18009f7f5  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x18009f7fa  nop
0x18009f7fb  mov     r8, rax
0x18009f7fe  mov     dl, 4
0x18009f800  lea     rcx, [rbp+4Fh+var_A0]
0x18009f804  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x18009f809  nop
0x18009f80a  mov     rdx, [rbp+4Fh+var_40]
0x18009f80e  cmp     rdx, 10h
0x18009f812  jb      short loc_18009F845
0x18009f814  inc     rdx
0x18009f817  mov     rcx, [rbp+4Fh+var_58]
0x18009f81b  mov     rax, rcx
0x18009f81e  cmp     rdx, 1000h
0x18009f825  jb      short loc_18009F840
0x18009f827  add     rdx, 27h ; '''; unsigned __int64
0x18009f82b  mov     rcx, [rcx-8]; void *
0x18009f82f  sub     rax, rcx
0x18009f832  add     rax, 0FFFFFFFFFFFFFFF8h
0x18009f836  cmp     rax, 1Fh
0x18009f83a  ja      loc_18009F958
0x18009f840  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009f845  mov     rax, [rbp+4Fh+var_98]
0x18009f849  jmp     short loc_18009F84E
0x18009f84b  mov     rax, r12
0x18009f84e  mov     [rbp+4Fh+var_68], rax
0x18009f852  mov     [rbp+4Fh+var_98], r12
0x18009f856  test    rax, rax
0x18009f859  jz      short loc_18009F871
0x18009f85b  lea     rdx, [rbp+4Fh+var_70]
0x18009f85f  mov     rcx, rbx
0x18009f862  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x18009f867  nop
0x18009f868  mov     rcx, [rbp+4Fh+var_68]
0x18009f86c  jmp     loc_18009F928
0x18009f871  mov     r9, [rsi+58h]
0x18009f875  mov     r8, rdi
0x18009f878  mov     rdx, r14
0x18009f87b  lea     rcx, [rbp+4Fh+var_70]
0x18009f87f  call    ?ValidateReadRange@internal@io@arrow@@YA?AV?$Result@_J@3@_J00@Z; arrow::io::internal::ValidateReadRange(__int64,__int64,__int64)
0x18009f884  nop
0x18009f885  mov     [rbp+4Fh+var_80], r12
0x18009f889  cmp     qword ptr [rax+8], 0
0x18009f88e  jnz     short loc_18009F8A2
0x18009f890  mov     [rbp+4Fh+var_80], r12
0x18009f894  mov     [rax+8], r12
0x18009f898  mov     rax, [rax+10h]
0x18009f89c  mov     [rbp+4Fh+Size], rax
0x18009f8a0  jmp     short loc_18009F8AF
0x18009f8a2  mov     rdx, rax; struct arrow::Status *
0x18009f8a5  lea     rcx, [rbp+4Fh+var_88]; this
0x18009f8a9  call    ?CopyFrom@Status@arrow@@AEAAXAEBV12@@Z; arrow::Status::CopyFrom(arrow::Status const &)
0x18009f8ae  nop
0x18009f8af  mov     rcx, [rbp+4Fh+var_68]; this
0x18009f8b3  test    rcx, rcx
0x18009f8b6  jz      short loc_18009F8C6
0x18009f8b8  mov     edx, 1; unsigned int
0x18009f8bd  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009f8c2  mov     [rbp+4Fh+var_68], r12
0x18009f8c6  lea     rdx, [rbp+4Fh+var_88]; struct arrow::Status *
0x18009f8ca  lea     rcx, [rbp+4Fh+var_A0]; this
0x18009f8ce  call    ??0Status@arrow@@QEAA@AEBV01@@Z; arrow::Status::Status(arrow::Status const &)
0x18009f8d3  nop
0x18009f8d4  cmp     [rbp+4Fh+var_98], 0
0x18009f8d9  jz      short loc_18009F901
0x18009f8db  lea     rdx, [rbp+4Fh+var_A0]
0x18009f8df  mov     rcx, rbx
0x18009f8e2  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x18009f8e7  nop
0x18009f8e8  mov     rcx, [rbp+4Fh+var_98]; this
0x18009f8ec  test    rcx, rcx
0x18009f8ef  jz      short loc_18009F924
0x18009f8f1  mov     edx, 1; unsigned int
0x18009f8f6  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009f8fb  mov     [rbp+4Fh+var_98], r12
0x18009f8ff  jmp     short loc_18009F924
0x18009f901  mov     rdi, [rbp+4Fh+Size]
0x18009f905  test    rdi, rdi
0x18009f908  jz      short loc_18009F91C
0x18009f90a  mov     rdx, [rsi+50h]
0x18009f90e  add     rdx, r14; Src
0x18009f911  mov     r8, rdi; Size
0x18009f914  mov     rcx, r15; void *
0x18009f917  call    memmove
0x18009f91c  mov     [rbx+8], r12
0x18009f920  mov     [rbx+10h], rdi
0x18009f924  mov     rcx, [rbp+4Fh+var_80]; this
0x18009f928  test    rcx, rcx
0x18009f92b  jz      short loc_18009F937
0x18009f92d  mov     edx, 1; unsigned int
0x18009f932  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009f937  mov     rax, rbx
0x18009f93a  mov     rcx, [rbp+4Fh+var_38]
0x18009f93e  xor     rcx, rsp; StackCookie
0x18009f941  call    __security_check_cookie
0x18009f946  add     rsp, 90h
0x18009f94d  pop     r15
0x18009f94f  pop     r14
0x18009f951  pop     r12
0x18009f953  pop     rdi
0x18009f954  pop     rsi
0x18009f955  pop     rbx
0x18009f956  pop     rbp
0x18009f957  retn
0x18009f958  call    _invalid_parameter_noinfo_noreturn
```
