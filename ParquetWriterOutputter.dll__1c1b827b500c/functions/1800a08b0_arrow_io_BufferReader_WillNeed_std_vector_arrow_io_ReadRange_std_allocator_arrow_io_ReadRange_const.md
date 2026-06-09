# arrow::io::BufferReader::WillNeed(std::vector<arrow::io::ReadRange,std::allocator<arrow::io::ReadRange>> const &)

- ea: `0x1800a08b0`
- end: `0x1800a0bea`
- name: `?WillNeed@BufferReader@io@arrow@@UEAA?AVStatus@3@AEBV?$vector@UReadRange@io@arrow@@V?$allocator@UReadRange@io@arrow@@@std@@@std@@@Z`
- size: `826`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x18001d5b0`
- `0x18001f8c0`
- `0x180086ed0`
- `0x1800973c0`
- `0x18009a010`
- `0x18009a530`
- `0x18009e050`
- `0x1800a08b0`
- `0x1800e4bb0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x1800a08fc`: `Operation forbidden on closed BufferReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
arrow::Status *__fastcall arrow::io::BufferReader::WillNeed(__int64 a1, arrow::Status *a2, __int64 *a3)
{
  __int64 v6; // r8
  __int64 v7; // rdx
  unsigned __int64 v8; // rdx
  _BYTE *v9; // rcx
  __int64 v10; // rax
  unsigned __int64 v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // rdi
  _QWORD *v14; // r14
  const struct arrow::Status *Range; // rax
  arrow::Status::State *v16; // rcx
  void *v17; // rcx
  unsigned __int64 v18; // rdx
  char v20[8]; // [rsp+20h] [rbp-79h] BYREF
  arrow::Status *v21; // [rsp+28h] [rbp-71h] BYREF
  arrow::Status::State *v22; // [rsp+30h] [rbp-69h]
  __int128 v23; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v24[2]; // [rsp+48h] [rbp-51h] BYREF
  __int64 v25; // [rsp+58h] [rbp-41h]
  __int64 v26; // [rsp+60h] [rbp-39h]
  char v27[8]; // [rsp+68h] [rbp-31h] BYREF
  __int64 v28; // [rsp+70h] [rbp-29h]
  char v29[8]; // [rsp+78h] [rbp-21h] BYREF
  arrow::Status::State *v30; // [rsp+80h] [rbp-19h]
  __int64 v31; // [rsp+88h] [rbp-11h]
  _BYTE *v32; // [rsp+90h] [rbp-9h] BYREF
  arrow::Status::State *v33; // [rsp+98h] [rbp-1h]
  unsigned __int64 v34; // [rsp+A8h] [rbp+Fh]

  v26 = -2;
  v21 = a2;
  if ( *(_BYTE *)(a1 + 104) )
  {
    v10 = 0;
  }
  else
  {
    v6 = arrow::util::StringBuilder<char const (&)[13]>(&v32, "Operation forbidden on closed BufferReader");
    LOBYTE(v7) = 4;
    arrow::Status::Status(&v23, v7, v6);
    if ( v34 >= 0x10 )
    {
      v8 = v34 + 1;
      v9 = v32;
      if ( v34 + 1 >= 0x1000 )
      {
        v8 = v34 + 40;
        v9 = (_BYTE *)*((_QWORD *)v32 - 1);
        if ( (unsigned __int64)(v32 - v9 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v9, v8);
    }
    v10 = *((_QWORD *)&v23 + 1);
  }
  if ( v10 )
  {
    *((_QWORD *)a2 + 1) = v10;
    return a2;
  }
  std::vector<arrow::internal::MemoryRegion>::vector<arrow::internal::MemoryRegion>(v24, (a3[1] - *a3) >> 4, v20);
  v11 = 0;
  v12 = *a3;
  if ( !((a3[1] - *a3) >> 4) )
  {
LABEL_21:
    arrow::internal::MemoryAdviseWillNeed(&v21, v24);
    v16 = v22;
    if ( v22 && *(_BYTE *)v22 == 5 )
    {
      *((_QWORD *)a2 + 1) = 0;
      arrow::Status::State::`scalar deleting destructor'(v16, 1u);
      v22 = 0;
      v17 = (void *)v24[0];
      if ( !v24[0] )
        return a2;
      v18 = (v25 - v24[0]) & 0xFFFFFFFFFFFFFFF0uLL;
      if ( v18 >= 0x1000 )
      {
        v18 += 39LL;
        v17 = *(void **)(v24[0] - 8LL);
        if ( (unsigned __int64)(v24[0] - (_QWORD)v17 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
    }
    else
    {
      arrow::Status::Status(a2, (const struct arrow::Status *)&v21);
      if ( v22 )
      {
        arrow::Status::State::`scalar deleting destructor'(v22, 1u);
        v22 = 0;
      }
      v17 = (void *)v24[0];
      if ( !v24[0] )
        return a2;
      v18 = (v25 - v24[0]) & 0xFFFFFFFFFFFFFFF0uLL;
      if ( v18 >= 0x1000 )
      {
        v18 += 39LL;
        v17 = *(void **)(v24[0] - 8LL);
        if ( (unsigned __int64)(v24[0] - (_QWORD)v17 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
    }
LABEL_38:
    operator delete(v17, v18);
    return a2;
  }
  v13 = 0;
  while ( 1 )
  {
    v14 = (_QWORD *)(v13 + v12);
    Range = (const struct arrow::Status *)arrow::io::internal::ValidateReadRange(
                                            (__int64)&v32,
                                            *(_QWORD *)(v13 + v12),
                                            *(_QWORD *)(v13 + v12 + 8),
                                            *(_QWORD *)(a1 + 88));
    v30 = 0;
    if ( *((_QWORD *)Range + 1) )
    {
      arrow::Status::CopyFrom((arrow::Status *)v29, Range);
    }
    else
    {
      v30 = 0;
      *((_QWORD *)Range + 1) = 0;
      v31 = *((_QWORD *)Range + 2);
    }
    if ( v33 )
    {
      arrow::Status::State::`scalar deleting destructor'(v33, 1u);
      v33 = 0;
    }
    arrow::Status::Status((arrow::Status *)v27, (const struct arrow::Status *)v29);
    if ( v28 )
      break;
    *(_QWORD *)&v23 = *v14 + *(_QWORD *)(a1 + 80);
    *((_QWORD *)&v23 + 1) = v31;
    *(_OWORD *)(v13 + v24[0]) = v23;
    if ( v30 )
      arrow::Status::State::`scalar deleting destructor'(v30, 1u);
    ++v11;
    v13 += 16;
    v12 = *a3;
    if ( v11 >= (a3[1] - *a3) >> 4 )
      goto LABEL_21;
  }
  *((_QWORD *)a2 + 1) = v28;
  if ( v30 )
  {
    arrow::Status::State::`scalar deleting destructor'(v30, 1u);
    v30 = 0;
  }
  v17 = (void *)v24[0];
  if ( v24[0] )
  {
    v18 = (v25 - v24[0]) & 0xFFFFFFFFFFFFFFF0uLL;
    if ( v18 >= 0x1000 )
    {
      v18 += 39LL;
      v17 = *(void **)(v24[0] - 8LL);
      if ( (unsigned __int64)(v24[0] - (_QWORD)v17 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    goto LABEL_38;
  }
  return a2;
}

```

## disassembly

```asm
0x1800a08b0  push    rbp
0x1800a08b2  push    rsi
0x1800a08b3  push    rdi
0x1800a08b4  push    r12
0x1800a08b6  push    r13
0x1800a08b8  push    r14
0x1800a08ba  push    r15
0x1800a08bc  lea     rbp, [rsp-27h]
0x1800a08c1  sub     rsp, 0C0h
0x1800a08c8  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x1800a08d0  mov     [rsp+0F0h+arg_18], rbx
0x1800a08d8  mov     rax, cs:__security_cookie
0x1800a08df  xor     rax, rsp
0x1800a08e2  mov     [rbp+57h+var_40], rax
0x1800a08e6  mov     r15, r8
0x1800a08e9  mov     rbx, rdx
0x1800a08ec  mov     r13, rcx
0x1800a08ef  mov     [rbp+57h+var_C8], rdx
0x1800a08f3  xor     r12d, r12d
0x1800a08f6  cmp     [rcx+68h], r12b
0x1800a08fa  jnz     short loc_1800A095D
0x1800a08fc  lea     rdx, aOperationForbi; "Operation forbidden on closed BufferRea"...
0x1800a0903  lea     rcx, [rbp+57h+var_60]
0x1800a0907  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1800a090c  nop
0x1800a090d  mov     r8, rax
0x1800a0910  mov     dl, 4
0x1800a0912  lea     rcx, [rbp+57h+var_B8]
0x1800a0916  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800a091b  nop
0x1800a091c  mov     rdx, [rbp+57h+var_48]
0x1800a0920  cmp     rdx, 10h
0x1800a0924  jb      short loc_1800A0957
0x1800a0926  inc     rdx
0x1800a0929  mov     rcx, [rbp+57h+var_60]
0x1800a092d  mov     rax, rcx
0x1800a0930  cmp     rdx, 1000h
0x1800a0937  jb      short loc_1800A0952
0x1800a0939  add     rdx, 27h ; '''; unsigned __int64
0x1800a093d  mov     rcx, [rcx-8]; void *
0x1800a0941  sub     rax, rcx
0x1800a0944  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800a0948  cmp     rax, 1Fh
0x1800a094c  ja      loc_1800A0BE4
0x1800a0952  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a0957  mov     rax, qword ptr [rbp+57h+var_B8+8]
0x1800a095b  jmp     short loc_1800A0960
0x1800a095d  mov     rax, r12
0x1800a0960  test    rax, rax
0x1800a0963  jz      short loc_1800A096E
0x1800a0965  mov     [rbx+8], rax
0x1800a0969  jmp     loc_1800A0BA8
0x1800a096e  mov     rdx, [r15+8]
0x1800a0972  sub     rdx, [r15]
0x1800a0975  sar     rdx, 4
0x1800a0979  lea     r8, [rbp+57h+var_D0]
0x1800a097d  lea     rcx, [rbp+57h+var_A8]
0x1800a0981  call    ??0?$vector@UMemoryRegion@internal@arrow@@V?$allocator@UMemoryRegion@internal@arrow@@@std@@@std@@QEAA@_KAEBV?$allocator@UMemoryRegion@internal@arrow@@@1@@Z; std::vector<arrow::internal::MemoryRegion>::vector<arrow::internal::MemoryRegion>(unsigned __int64,std::allocator<arrow::internal::MemoryRegion> const &)
0x1800a0986  nop
0x1800a0987  mov     rsi, r12
0x1800a098a  mov     rcx, [r15]
0x1800a098d  mov     rax, [r15+8]
0x1800a0991  sub     rax, rcx
0x1800a0994  sar     rax, 4
0x1800a0998  test    rax, rax
0x1800a099b  jz      loc_1800A0A74
0x1800a09a1  mov     rdi, r12
0x1800a09a4  nop     dword ptr [rax+00h]
0x1800a09a8  nop     dword ptr [rax+rax+00000000h]
0x1800a09b0  lea     r14, [rdi+rcx]
0x1800a09b4  mov     r9, [r13+58h]
0x1800a09b8  mov     r8, [r14+8]
0x1800a09bc  mov     rdx, [r14]
0x1800a09bf  lea     rcx, [rbp+57h+var_60]
0x1800a09c3  call    ?ValidateReadRange@internal@io@arrow@@YA?AV?$Result@_J@3@_J00@Z; arrow::io::internal::ValidateReadRange(__int64,__int64,__int64)
0x1800a09c8  nop
0x1800a09c9  mov     [rbp+57h+var_70], r12
0x1800a09cd  cmp     qword ptr [rax+8], 0
0x1800a09d2  jnz     short loc_1800A09E6
0x1800a09d4  mov     [rbp+57h+var_70], r12
0x1800a09d8  mov     [rax+8], r12
0x1800a09dc  mov     rax, [rax+10h]
0x1800a09e0  mov     [rbp+57h+var_68], rax
0x1800a09e4  jmp     short loc_1800A09F3
0x1800a09e6  mov     rdx, rax; struct arrow::Status *
0x1800a09e9  lea     rcx, [rbp+57h+var_78]; this
0x1800a09ed  call    ?CopyFrom@Status@arrow@@AEAAXAEBV12@@Z; arrow::Status::CopyFrom(arrow::Status const &)
0x1800a09f2  nop
0x1800a09f3  mov     rcx, [rbp+57h+var_58]; this
0x1800a09f7  test    rcx, rcx
0x1800a09fa  jz      short loc_1800A0A0A
0x1800a09fc  mov     edx, 1; unsigned int
0x1800a0a01  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800a0a06  mov     [rbp+57h+var_58], r12
0x1800a0a0a  lea     rdx, [rbp+57h+var_78]; struct arrow::Status *
0x1800a0a0e  lea     rcx, [rbp+57h+var_88]; this
0x1800a0a12  call    ??0Status@arrow@@QEAA@AEBV01@@Z; arrow::Status::Status(arrow::Status const &)
0x1800a0a17  mov     rax, [rbp+57h+var_80]
0x1800a0a1b  test    rax, rax
0x1800a0a1e  jnz     loc_1800A0AF0
0x1800a0a24  mov     rax, [r13+50h]
0x1800a0a28  add     rax, [r14]
0x1800a0a2b  mov     qword ptr [rbp+57h+var_B8], rax
0x1800a0a2f  mov     rax, [rbp+57h+var_68]
0x1800a0a33  mov     qword ptr [rbp+57h+var_B8+8], rax
0x1800a0a37  mov     rax, [rbp+57h+var_A8]
0x1800a0a3b  movups  xmm0, [rbp+57h+var_B8]
0x1800a0a3f  movups  xmmword ptr [rdi+rax], xmm0
0x1800a0a43  mov     rcx, [rbp+57h+var_70]; this
0x1800a0a47  test    rcx, rcx
0x1800a0a4a  jz      short loc_1800A0A56
0x1800a0a4c  mov     edx, 1; unsigned int
0x1800a0a51  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800a0a56  inc     rsi
0x1800a0a59  add     rdi, 10h
0x1800a0a5d  mov     rcx, [r15]
0x1800a0a60  mov     rax, [r15+8]
0x1800a0a64  sub     rax, rcx
0x1800a0a67  sar     rax, 4
0x1800a0a6b  cmp     rsi, rax
0x1800a0a6e  jb      loc_1800A09B0
0x1800a0a74  lea     rdx, [rbp+57h+var_A8]
0x1800a0a78  lea     rcx, [rbp+57h+var_C8]
0x1800a0a7c  call    ?MemoryAdviseWillNeed@internal@arrow@@YA?AVStatus@2@AEBV?$vector@UMemoryRegion@internal@arrow@@V?$allocator@UMemoryRegion@internal@arrow@@@std@@@std@@@Z; arrow::internal::MemoryAdviseWillNeed(std::vector<arrow::internal::MemoryRegion> const &)
0x1800a0a81  nop
0x1800a0a82  mov     rcx, [rbp+57h+var_C0]; this
0x1800a0a86  test    rcx, rcx
0x1800a0a89  jz      loc_1800A0B4A
0x1800a0a8f  cmp     byte ptr [rcx], 5
0x1800a0a92  jnz     loc_1800A0B4A
0x1800a0a98  mov     [rbx+8], r12
0x1800a0a9c  mov     edx, 1; unsigned int
0x1800a0aa1  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800a0aa6  mov     [rbp+57h+var_C0], r12
0x1800a0aaa  mov     rcx, [rbp+57h+var_A8]
0x1800a0aae  test    rcx, rcx
0x1800a0ab1  jz      loc_1800A0BA8
0x1800a0ab7  mov     rdx, [rbp+57h+var_98]
0x1800a0abb  sub     rdx, rcx
0x1800a0abe  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800a0ac2  mov     rax, rcx
0x1800a0ac5  cmp     rdx, 1000h
0x1800a0acc  jb      loc_1800A0BA3
0x1800a0ad2  add     rdx, 27h ; '''
0x1800a0ad6  mov     rcx, [rcx-8]
0x1800a0ada  sub     rax, rcx
0x1800a0add  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800a0ae1  cmp     rax, 1Fh
0x1800a0ae5  ja      loc_1800A0BD8
0x1800a0aeb  jmp     loc_1800A0BA3
0x1800a0af0  mov     [rbx+8], rax
0x1800a0af4  mov     rcx, [rbp+57h+var_70]; this
0x1800a0af8  test    rcx, rcx
0x1800a0afb  jz      short loc_1800A0B0B
0x1800a0afd  mov     edx, 1; unsigned int
0x1800a0b02  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800a0b07  mov     [rbp+57h+var_70], r12
0x1800a0b0b  mov     rcx, [rbp+57h+var_A8]
0x1800a0b0f  test    rcx, rcx
0x1800a0b12  jz      loc_1800A0BA8
0x1800a0b18  mov     rdx, [rbp+57h+var_98]
0x1800a0b1c  sub     rdx, rcx
0x1800a0b1f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800a0b23  mov     rax, rcx
0x1800a0b26  cmp     rdx, 1000h
0x1800a0b2d  jb      short loc_1800A0BA3
0x1800a0b2f  add     rdx, 27h ; '''
0x1800a0b33  mov     rcx, [rcx-8]
0x1800a0b37  sub     rax, rcx
0x1800a0b3a  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800a0b3e  cmp     rax, 1Fh
0x1800a0b42  ja      loc_1800A0BDE
0x1800a0b48  jmp     short loc_1800A0BA3
0x1800a0b4a  lea     rdx, [rbp+57h+var_C8]; struct arrow::Status *
0x1800a0b4e  mov     rcx, rbx; this
0x1800a0b51  call    ??0Status@arrow@@QEAA@AEBV01@@Z; arrow::Status::Status(arrow::Status const &)
0x1800a0b56  nop
0x1800a0b57  mov     rcx, [rbp+57h+var_C0]; this
0x1800a0b5b  test    rcx, rcx
0x1800a0b5e  jz      short loc_1800A0B6E
0x1800a0b60  mov     edx, 1; unsigned int
0x1800a0b65  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800a0b6a  mov     [rbp+57h+var_C0], r12
0x1800a0b6e  mov     rcx, [rbp+57h+var_A8]
0x1800a0b72  test    rcx, rcx
0x1800a0b75  jz      short loc_1800A0BA8
0x1800a0b77  mov     rdx, [rbp+57h+var_98]
0x1800a0b7b  sub     rdx, rcx
0x1800a0b7e  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800a0b82  mov     rax, rcx
0x1800a0b85  cmp     rdx, 1000h
0x1800a0b8c  jb      short loc_1800A0BA3
0x1800a0b8e  add     rdx, 27h ; '''; unsigned __int64
0x1800a0b92  mov     rcx, [rcx-8]; void *
0x1800a0b96  sub     rax, rcx
0x1800a0b99  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800a0b9d  cmp     rax, 1Fh
0x1800a0ba1  ja      short loc_1800A0BD2
0x1800a0ba3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a0ba8  mov     rax, rbx
0x1800a0bab  mov     rcx, [rbp+57h+var_40]
0x1800a0baf  xor     rcx, rsp; StackCookie
0x1800a0bb2  call    __security_check_cookie
0x1800a0bb7  mov     rbx, [rsp+0F0h+arg_18]
0x1800a0bbf  add     rsp, 0C0h
0x1800a0bc6  pop     r15
0x1800a0bc8  pop     r14
0x1800a0bca  pop     r13
0x1800a0bcc  pop     r12
0x1800a0bce  pop     rdi
0x1800a0bcf  pop     rsi
0x1800a0bd0  pop     rbp
0x1800a0bd1  retn
0x1800a0bd2  call    _invalid_parameter_noinfo_noreturn
0x1800a0bd8  call    _invalid_parameter_noinfo_noreturn
0x1800a0bde  call    _invalid_parameter_noinfo_noreturn
0x1800a0be4  call    _invalid_parameter_noinfo_noreturn
```
