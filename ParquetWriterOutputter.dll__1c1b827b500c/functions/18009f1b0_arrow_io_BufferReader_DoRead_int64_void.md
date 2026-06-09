# arrow::io::BufferReader::DoRead(__int64,void *)

- ea: `0x18009f1b0`
- end: `0x18009f358`
- name: `?DoRead@BufferReader@io@arrow@@IEAA?AV?$Result@_J@3@_JPEAX@Z`
- size: `424`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18009ff30`

## callees

- `0x18001d5b0`
- `0x18001f8c0`
- `0x180059010`
- `0x180086ed0`
- `0x18009a010`
- `0x18009a530`
- `0x18009f1b0`
- `0x18009f7a0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x18009f1f4`: `Operation forbidden on closed BufferReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall arrow::io::BufferReader::DoRead(__int64 a1, __int64 a2, __int64 a3, void *a4)
{
  __int64 v8; // r8
  __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  _BYTE *v11; // rcx
  arrow::Status::State *v12; // rax
  arrow::Status::State *v13; // rcx
  const struct arrow::Status *v14; // rax
  __int64 v15; // rax
  __int64 v17; // [rsp+30h] [rbp-49h] BYREF
  arrow::Status::State *v18; // [rsp+38h] [rbp-41h]
  __int64 v19; // [rsp+40h] [rbp-39h]
  char v20[8]; // [rsp+48h] [rbp-31h] BYREF
  arrow::Status::State *v21; // [rsp+50h] [rbp-29h]
  __int64 v22; // [rsp+58h] [rbp-21h]
  int v23; // [rsp+60h] [rbp-19h] BYREF
  arrow::Status::State *v24; // [rsp+68h] [rbp-11h]
  _BYTE *v25; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int64 v26; // [rsp+90h] [rbp+17h]

  v19 = -2;
  v17 = a2;
  if ( *(_BYTE *)(a1 + 104) )
  {
    v12 = 0;
  }
  else
  {
    v8 = arrow::util::StringBuilder<char const (&)[13]>(&v25, "Operation forbidden on closed BufferReader");
    LOBYTE(v9) = 4;
    arrow::Status::Status(&v17, v9, v8);
    if ( v26 >= 0x10 )
    {
      v10 = v26 + 1;
      v11 = v25;
      if ( v26 + 1 >= 0x1000 )
      {
        v10 = v26 + 40;
        v11 = (_BYTE *)*((_QWORD *)v25 - 1);
        if ( (unsigned __int64)(v25 - v11 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v11, v10);
    }
    v12 = v18;
  }
  v24 = v12;
  v18 = 0;
  if ( v12 )
  {
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, &v23);
    v13 = v24;
  }
  else
  {
    v14 = (const struct arrow::Status *)arrow::io::BufferReader::DoReadAt(
                                          a1,
                                          (__int64)&v23,
                                          *(_QWORD *)(a1 + 96),
                                          a3,
                                          a4);
    v21 = 0;
    if ( *((_QWORD *)v14 + 1) )
    {
      arrow::Status::CopyFrom((arrow::Status *)v20, v14);
    }
    else
    {
      v21 = 0;
      *((_QWORD *)v14 + 1) = 0;
      v22 = *((_QWORD *)v14 + 2);
    }
    if ( v24 )
    {
      arrow::Status::State::`scalar deleting destructor'(v24, 1u);
      v24 = 0;
    }
    arrow::Status::Status((arrow::Status *)&v17, (const struct arrow::Status *)v20);
    if ( v18 )
    {
      arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, &v17);
      if ( v18 )
      {
        arrow::Status::State::`scalar deleting destructor'(v18, 1u);
        v18 = 0;
      }
    }
    else
    {
      v15 = v22;
      *(_QWORD *)(a1 + 96) += v22;
      *(_QWORD *)(a2 + 8) = 0;
      *(_QWORD *)(a2 + 16) = v15;
    }
    v13 = v21;
  }
  if ( v13 )
    arrow::Status::State::`scalar deleting destructor'(v13, 1u);
  return a2;
}

```

## disassembly

```asm
0x18009f1b0  push    rbp
0x18009f1b2  push    rbx
0x18009f1b3  push    rsi
0x18009f1b4  push    rdi
0x18009f1b5  push    r14
0x18009f1b7  push    r15
0x18009f1b9  lea     rbp, [rsp-2Fh]
0x18009f1be  sub     rsp, 0A8h
0x18009f1c5  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x18009f1cd  mov     rax, cs:__security_cookie
0x18009f1d4  xor     rax, rsp
0x18009f1d7  mov     [rbp+57h+var_38], rax
0x18009f1db  mov     r14, r9
0x18009f1de  mov     rsi, r8
0x18009f1e1  mov     rbx, rdx
0x18009f1e4  mov     rdi, rcx
0x18009f1e7  mov     [rbp+57h+var_A0], rdx
0x18009f1eb  xor     r15d, r15d
0x18009f1ee  cmp     [rcx+68h], r15b
0x18009f1f2  jnz     short loc_18009F255
0x18009f1f4  lea     rdx, aOperationForbi; "Operation forbidden on closed BufferRea"...
0x18009f1fb  lea     rcx, [rbp+57h+var_58]
0x18009f1ff  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x18009f204  nop
0x18009f205  mov     r8, rax
0x18009f208  mov     dl, 4
0x18009f20a  lea     rcx, [rbp+57h+var_A0]
0x18009f20e  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x18009f213  nop
0x18009f214  mov     rdx, [rbp+57h+var_40]
0x18009f218  cmp     rdx, 10h
0x18009f21c  jb      short loc_18009F24F
0x18009f21e  inc     rdx
0x18009f221  mov     rcx, [rbp+57h+var_58]
0x18009f225  mov     rax, rcx
0x18009f228  cmp     rdx, 1000h
0x18009f22f  jb      short loc_18009F24A
0x18009f231  add     rdx, 27h ; '''; unsigned __int64
0x18009f235  mov     rcx, [rcx-8]; void *
0x18009f239  sub     rax, rcx
0x18009f23c  add     rax, 0FFFFFFFFFFFFFFF8h
0x18009f240  cmp     rax, 1Fh
0x18009f244  ja      loc_18009F352
0x18009f24a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009f24f  mov     rax, [rbp+57h+var_98]
0x18009f253  jmp     short loc_18009F258
0x18009f255  mov     rax, r15
0x18009f258  mov     [rbp+57h+var_68], rax
0x18009f25c  mov     [rbp+57h+var_98], r15
0x18009f260  test    rax, rax
0x18009f263  jz      short loc_18009F27B
0x18009f265  lea     rdx, [rbp+57h+var_70]
0x18009f269  mov     rcx, rbx
0x18009f26c  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x18009f271  nop
0x18009f272  mov     rcx, [rbp+57h+var_68]
0x18009f276  jmp     loc_18009F324
0x18009f27b  mov     [rsp+0D0h+var_B0], r14; void *
0x18009f280  mov     r9, rsi; int
0x18009f283  mov     r8, [rdi+60h]; int
0x18009f287  lea     rdx, [rbp+57h+var_70]; int
0x18009f28b  mov     rcx, rdi; int
0x18009f28e  call    ?DoReadAt@BufferReader@io@arrow@@IEAA?AV?$Result@_J@3@_J0PEAX@Z; arrow::io::BufferReader::DoReadAt(__int64,__int64,void *)
0x18009f293  nop
0x18009f294  mov     [rbp+57h+var_80], r15
0x18009f298  cmp     qword ptr [rax+8], 0
0x18009f29d  jnz     short loc_18009F2B1
0x18009f29f  mov     [rbp+57h+var_80], r15
0x18009f2a3  mov     [rax+8], r15
0x18009f2a7  mov     rax, [rax+10h]
0x18009f2ab  mov     [rbp+57h+var_78], rax
0x18009f2af  jmp     short loc_18009F2BE
0x18009f2b1  mov     rdx, rax; struct arrow::Status *
0x18009f2b4  lea     rcx, [rbp+57h+var_88]; this
0x18009f2b8  call    ?CopyFrom@Status@arrow@@AEAAXAEBV12@@Z; arrow::Status::CopyFrom(arrow::Status const &)
0x18009f2bd  nop
0x18009f2be  mov     rcx, [rbp+57h+var_68]; this
0x18009f2c2  test    rcx, rcx
0x18009f2c5  jz      short loc_18009F2D5
0x18009f2c7  mov     edx, 1; unsigned int
0x18009f2cc  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009f2d1  mov     [rbp+57h+var_68], r15
0x18009f2d5  lea     rdx, [rbp+57h+var_88]; struct arrow::Status *
0x18009f2d9  lea     rcx, [rbp+57h+var_A0]; this
0x18009f2dd  call    ??0Status@arrow@@QEAA@AEBV01@@Z; arrow::Status::Status(arrow::Status const &)
0x18009f2e2  nop
0x18009f2e3  cmp     [rbp+57h+var_98], 0
0x18009f2e8  jz      short loc_18009F310
0x18009f2ea  lea     rdx, [rbp+57h+var_A0]
0x18009f2ee  mov     rcx, rbx
0x18009f2f1  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x18009f2f6  nop
0x18009f2f7  mov     rcx, [rbp+57h+var_98]; this
0x18009f2fb  test    rcx, rcx
0x18009f2fe  jz      short loc_18009F320
0x18009f300  mov     edx, 1; unsigned int
0x18009f305  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009f30a  mov     [rbp+57h+var_98], r15
0x18009f30e  jmp     short loc_18009F320
0x18009f310  mov     rax, [rbp+57h+var_78]
0x18009f314  add     [rdi+60h], rax
0x18009f318  mov     [rbx+8], r15
0x18009f31c  mov     [rbx+10h], rax
0x18009f320  mov     rcx, [rbp+57h+var_80]; this
0x18009f324  test    rcx, rcx
0x18009f327  jz      short loc_18009F333
0x18009f329  mov     edx, 1; unsigned int
0x18009f32e  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009f333  mov     rax, rbx
0x18009f336  mov     rcx, [rbp+57h+var_38]
0x18009f33a  xor     rcx, rsp; StackCookie
0x18009f33d  call    __security_check_cookie
0x18009f342  add     rsp, 0A8h
0x18009f349  pop     r15
0x18009f34b  pop     r14
0x18009f34d  pop     rdi
0x18009f34e  pop     rsi
0x18009f34f  pop     rbx
0x18009f350  pop     rbp
0x18009f351  retn
0x18009f352  call    _invalid_parameter_noinfo_noreturn
```
