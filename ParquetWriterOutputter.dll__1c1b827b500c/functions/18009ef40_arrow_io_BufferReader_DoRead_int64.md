# arrow::io::BufferReader::DoRead(__int64)

- ea: `0x18009ef40`
- end: `0x18009f1a7`
- name: `?DoRead@BufferReader@io@arrow@@IEAA?AV?$Result@V?$shared_ptr@VBuffer@arrow@@@std@@@3@_J@Z`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18009fe00`

## callees

- `0x18001d5b0`
- `0x18001f8c0`
- `0x180059010`
- `0x180086ed0`
- `0x18009a010`
- `0x18009a530`
- `0x18009ef40`
- `0x18009f360`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x18009ef88`: `Operation forbidden on closed BufferReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall arrow::io::BufferReader::DoRead(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // r8
  __int64 v7; // rdx
  unsigned __int64 v8; // rdx
  _BYTE *v9; // rcx
  arrow::Status::State *v10; // rax
  arrow::Status::State *v11; // rcx
  const struct arrow::Status *v12; // rax
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  arrow::Status::State *v15; // rcx
  volatile signed __int32 *v16; // rbx
  volatile signed __int32 *v17; // rbx
  unsigned __int128 v18; // kr00_16
  __int64 v20; // [rsp+20h] [rbp-69h] BYREF
  arrow::Status::State *v21; // [rsp+28h] [rbp-61h]
  char v22[8]; // [rsp+30h] [rbp-59h] BYREF
  arrow::Status::State *v23; // [rsp+38h] [rbp-51h]
  char v24[8]; // [rsp+40h] [rbp-49h] BYREF
  arrow::Status::State *v25; // [rsp+48h] [rbp-41h]
  __int64 v26; // [rsp+50h] [rbp-39h]
  char v27[8]; // [rsp+58h] [rbp-31h] BYREF
  arrow::Status::State *v28; // [rsp+60h] [rbp-29h]
  unsigned __int128 v29; // [rsp+68h] [rbp-21h]
  __int64 v30; // [rsp+78h] [rbp-11h] BYREF
  arrow::Status::State *v31; // [rsp+80h] [rbp-9h]
  volatile signed __int32 *v32; // [rsp+90h] [rbp+7h]
  _BYTE *v33; // [rsp+98h] [rbp+Fh] BYREF
  unsigned __int64 v34; // [rsp+B0h] [rbp+27h]

  v26 = -2;
  v20 = a2;
  if ( *(_BYTE *)(a1 + 104) )
  {
    v10 = 0;
  }
  else
  {
    v6 = arrow::util::StringBuilder<char const (&)[13]>(&v33, "Operation forbidden on closed BufferReader");
    LOBYTE(v7) = 4;
    arrow::Status::Status(v22, v7, v6);
    if ( v34 >= 0x10 )
    {
      v8 = v34 + 1;
      v9 = v33;
      if ( v34 + 1 >= 0x1000 )
      {
        v8 = v34 + 40;
        v9 = (_BYTE *)*((_QWORD *)v33 - 1);
        if ( (unsigned __int64)(v33 - v9 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v9, v8);
    }
    v10 = v23;
  }
  v25 = v10;
  v23 = 0;
  if ( v10 )
  {
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v24);
    v11 = v25;
    goto LABEL_30;
  }
  v12 = (const struct arrow::Status *)arrow::io::BufferReader::DoReadAt(a1, &v30, *(_QWORD *)(a1 + 96), a3);
  v28 = 0;
  if ( *((_QWORD *)v12 + 1) )
  {
    arrow::Status::CopyFrom((arrow::Status *)v27, v12);
  }
  else
  {
    v28 = 0;
    *((_QWORD *)v12 + 1) = 0;
    v13 = *((_QWORD *)v12 + 2);
    v14 = *((_QWORD *)v12 + 3);
    *((_QWORD *)v12 + 2) = 0;
    *((_QWORD *)v12 + 3) = 0;
    v29 = __PAIR128__(v14, v13);
  }
  v15 = v31;
  if ( v31 )
    goto LABEL_19;
  v16 = v32;
  if ( v32 )
  {
    if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
    v15 = v31;
    if ( v31 )
    {
LABEL_19:
      arrow::Status::State::`scalar deleting destructor'(v15, 1u);
      v31 = 0;
    }
  }
  arrow::Status::Status((arrow::Status *)&v20, (const struct arrow::Status *)v27);
  if ( !v21 )
  {
    v18 = v29;
    v29 = 0;
    *(_QWORD *)(a1 + 96) += *(_QWORD *)(v18 + 32);
    *(_QWORD *)(a2 + 8) = 0;
    *(_OWORD *)(a2 + 16) = v18;
LABEL_29:
    v11 = v28;
LABEL_30:
    if ( v11 )
    {
LABEL_31:
      arrow::Status::State::`scalar deleting destructor'(v11, 1u);
      return a2;
    }
    return a2;
  }
  arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, &v20);
  if ( v21 )
  {
    arrow::Status::State::`scalar deleting destructor'(v21, 1u);
    v21 = 0;
  }
  v11 = v28;
  if ( v28 )
    goto LABEL_31;
  v17 = (volatile signed __int32 *)*((_QWORD *)&v29 + 1);
  if ( *((_QWORD *)&v29 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
    goto LABEL_29;
  }
  return a2;
}

```

## disassembly

```asm
0x18009ef40  push    rbp
0x18009ef42  push    rsi
0x18009ef43  push    rdi
0x18009ef44  push    r14
0x18009ef46  push    r15
0x18009ef48  lea     rbp, [rsp-37h]
0x18009ef4d  sub     rsp, 0C0h
0x18009ef54  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x18009ef5c  mov     [rsp+0E0h+arg_18], rbx
0x18009ef64  mov     rax, cs:__security_cookie
0x18009ef6b  xor     rax, rsp
0x18009ef6e  mov     [rbp+57h+var_28], rax
0x18009ef72  mov     rbx, r8
0x18009ef75  mov     rdi, rdx
0x18009ef78  mov     r14, rcx
0x18009ef7b  mov     [rbp+57h+var_C0], rdx
0x18009ef7f  xor     r15d, r15d
0x18009ef82  cmp     [rcx+68h], r15b
0x18009ef86  jnz     short loc_18009EFE9
0x18009ef88  lea     rdx, aOperationForbi; "Operation forbidden on closed BufferRea"...
0x18009ef8f  lea     rcx, [rbp+57h+var_48]
0x18009ef93  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x18009ef98  nop
0x18009ef99  mov     r8, rax
0x18009ef9c  mov     dl, 4
0x18009ef9e  lea     rcx, [rbp+57h+var_B0]
0x18009efa2  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x18009efa7  nop
0x18009efa8  mov     rdx, [rbp+57h+var_30]
0x18009efac  cmp     rdx, 10h
0x18009efb0  jb      short loc_18009EFE3
0x18009efb2  inc     rdx
0x18009efb5  mov     rcx, [rbp+57h+var_48]
0x18009efb9  mov     rax, rcx
0x18009efbc  cmp     rdx, 1000h
0x18009efc3  jb      short loc_18009EFDE
0x18009efc5  add     rdx, 27h ; '''; unsigned __int64
0x18009efc9  mov     rcx, [rcx-8]; void *
0x18009efcd  sub     rax, rcx
0x18009efd0  add     rax, 0FFFFFFFFFFFFFFF8h
0x18009efd4  cmp     rax, 1Fh
0x18009efd8  ja      loc_18009F1A1
0x18009efde  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009efe3  mov     rax, [rbp+57h+var_A8]
0x18009efe7  jmp     short loc_18009EFEC
0x18009efe9  mov     rax, r15
0x18009efec  mov     [rbp+57h+var_98], rax
0x18009eff0  mov     [rbp+57h+var_A8], r15
0x18009eff4  test    rax, rax
0x18009eff7  jz      short loc_18009F00F
0x18009eff9  lea     rdx, [rbp+57h+var_A0]
0x18009effd  mov     rcx, rdi
0x18009f000  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x18009f005  nop
0x18009f006  mov     rcx, [rbp+57h+var_98]
0x18009f00a  jmp     loc_18009F16C
0x18009f00f  mov     r9, rbx
0x18009f012  mov     r8, [r14+60h]
0x18009f016  lea     rdx, [rbp+57h+var_68]
0x18009f01a  mov     rcx, r14
0x18009f01d  call    ?DoReadAt@BufferReader@io@arrow@@IEAA?AV?$Result@V?$shared_ptr@VBuffer@arrow@@@std@@@3@_J0@Z; arrow::io::BufferReader::DoReadAt(__int64,__int64)
0x18009f022  nop
0x18009f023  mov     [rbp+57h+var_80], r15
0x18009f027  cmp     qword ptr [rax+8], 0
0x18009f02c  jnz     short loc_18009F050
0x18009f02e  mov     [rbp+57h+var_80], r15
0x18009f032  mov     [rax+8], r15
0x18009f036  mov     rdx, [rax+10h]
0x18009f03a  mov     rcx, [rax+18h]
0x18009f03e  mov     [rax+10h], r15
0x18009f042  mov     [rax+18h], r15
0x18009f046  mov     qword ptr [rbp+57h+var_78], rdx
0x18009f04a  mov     qword ptr [rbp+57h+var_78+8], rcx
0x18009f04e  jmp     short loc_18009F05D
0x18009f050  mov     rdx, rax; struct arrow::Status *
0x18009f053  lea     rcx, [rbp+57h+var_88]; this
0x18009f057  call    ?CopyFrom@Status@arrow@@AEAAXAEBV12@@Z; arrow::Status::CopyFrom(arrow::Status const &)
0x18009f05c  nop
0x18009f05d  mov     esi, 0FFFFFFFFh
0x18009f062  mov     rcx, [rbp+57h+var_60]
0x18009f066  test    rcx, rcx
0x18009f069  jnz     short loc_18009F0B4
0x18009f06b  mov     rbx, [rbp+57h+var_50]
0x18009f06f  test    rbx, rbx
0x18009f072  jz      short loc_18009F0C2
0x18009f074  mov     eax, esi
0x18009f076  lock xadd [rbx+8], eax
0x18009f07b  cmp     eax, 1
0x18009f07e  jnz     short loc_18009F0AB
0x18009f080  mov     rax, [rbx]
0x18009f083  mov     rcx, rbx
0x18009f086  mov     rax, [rax]
0x18009f089  call    cs:__guard_dispatch_icall_fptr
0x18009f08f  mov     eax, esi
0x18009f091  lock xadd [rbx+0Ch], eax
0x18009f096  cmp     eax, 1
0x18009f099  jnz     short loc_18009F0AB
0x18009f09b  mov     rax, [rbx]
0x18009f09e  mov     rcx, rbx
0x18009f0a1  mov     rax, [rax+8]
0x18009f0a5  call    cs:__guard_dispatch_icall_fptr
0x18009f0ab  mov     rcx, [rbp+57h+var_60]; this
0x18009f0af  test    rcx, rcx
0x18009f0b2  jz      short loc_18009F0C2
0x18009f0b4  mov     edx, 1; unsigned int
0x18009f0b9  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009f0be  mov     [rbp+57h+var_60], r15
0x18009f0c2  lea     rdx, [rbp+57h+var_88]; struct arrow::Status *
0x18009f0c6  lea     rcx, [rbp+57h+var_C0]; this
0x18009f0ca  call    ??0Status@arrow@@QEAA@AEBV01@@Z; arrow::Status::Status(arrow::Status const &)
0x18009f0cf  nop
0x18009f0d0  cmp     [rbp+57h+var_B8], 0
0x18009f0d5  jz      short loc_18009F144
0x18009f0d7  lea     rdx, [rbp+57h+var_C0]
0x18009f0db  mov     rcx, rdi
0x18009f0de  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x18009f0e3  nop
0x18009f0e4  mov     rcx, [rbp+57h+var_B8]; this
0x18009f0e8  test    rcx, rcx
0x18009f0eb  jz      short loc_18009F0FB
0x18009f0ed  mov     edx, 1; unsigned int
0x18009f0f2  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009f0f7  mov     [rbp+57h+var_B8], r15
0x18009f0fb  mov     rcx, [rbp+57h+var_80]
0x18009f0ff  test    rcx, rcx
0x18009f102  jnz     short loc_18009F171
0x18009f104  mov     rbx, qword ptr [rbp+57h+var_78+8]
0x18009f108  test    rbx, rbx
0x18009f10b  jz      short loc_18009F17B
0x18009f10d  mov     eax, esi
0x18009f10f  lock xadd [rbx+8], eax
0x18009f114  cmp     eax, 1
0x18009f117  jnz     short loc_18009F168
0x18009f119  mov     rax, [rbx]
0x18009f11c  mov     rcx, rbx
0x18009f11f  mov     rax, [rax]
0x18009f122  call    cs:__guard_dispatch_icall_fptr
0x18009f128  lock xadd [rbx+0Ch], esi
0x18009f12d  cmp     esi, 1
0x18009f130  jnz     short loc_18009F168
0x18009f132  mov     rax, [rbx]
0x18009f135  mov     rcx, rbx
0x18009f138  mov     rax, [rax+8]
0x18009f13c  call    cs:__guard_dispatch_icall_fptr
0x18009f142  jmp     short loc_18009F168
0x18009f144  mov     rcx, qword ptr [rbp+57h+var_78]
0x18009f148  mov     rdx, qword ptr [rbp+57h+var_78+8]
0x18009f14c  xorps   xmm0, xmm0
0x18009f14f  movdqu  [rbp+57h+var_78], xmm0
0x18009f154  mov     rax, [rcx+20h]
0x18009f158  add     [r14+60h], rax
0x18009f15c  mov     [rdi+8], r15
0x18009f160  mov     [rdi+10h], rcx
0x18009f164  mov     [rdi+18h], rdx
0x18009f168  mov     rcx, [rbp+57h+var_80]; this
0x18009f16c  test    rcx, rcx
0x18009f16f  jz      short loc_18009F17B
0x18009f171  mov     edx, 1; unsigned int
0x18009f176  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009f17b  mov     rax, rdi
0x18009f17e  mov     rcx, [rbp+57h+var_28]
0x18009f182  xor     rcx, rsp; StackCookie
0x18009f185  call    __security_check_cookie
0x18009f18a  mov     rbx, [rsp+0E0h+arg_18]
0x18009f192  add     rsp, 0C0h
0x18009f199  pop     r15
0x18009f19b  pop     r14
0x18009f19d  pop     rdi
0x18009f19e  pop     rsi
0x18009f19f  pop     rbp
0x18009f1a0  retn
0x18009f1a1  call    _invalid_parameter_noinfo_noreturn
```
