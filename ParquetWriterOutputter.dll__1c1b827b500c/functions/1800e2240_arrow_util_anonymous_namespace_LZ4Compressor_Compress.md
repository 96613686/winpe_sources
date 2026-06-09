# arrow::util::_anonymous_namespace_::LZ4Compressor::Compress

- ea: `0x1800e2240`
- end: `0x1800e23c1`
- name: `arrow::util::_anonymous_namespace_::LZ4Compressor::Compress`
- size: `385`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007eb0`
- `0x180008760`
- `0x180008780`
- `0x180008ba0`
- `0x18001f8c0`
- `0x180059010`
- `0x1800e2240`
- `0x1800e30d0`

## string_xrefs

- `0x1800e22c7`: `LZ4 compress begin failed: `
- `0x1800e235f`: `LZ4 compress update failed: `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::util::_anonymous_namespace_::LZ4Compressor::Compress(
        __int64 a1,
        __int64 a2,
        arrow::Status::State *a3,
        int a4,
        unsigned __int64 a5,
        __int64 a6)
{
  int v10; // r15d
  unsigned __int64 v11; // rdi
  arrow::Status::State *v12; // rsi
  __int64 v13; // r12
  __int64 v14; // rdx
  __int64 v15; // rdi
  __int64 v16; // rdx
  arrow::Status::State *v18[2]; // [rsp+38h] [rbp-40h] BYREF

  v10 = a6;
  v11 = a5;
  v12 = 0;
  if ( *(_BYTE *)(a1 + 72) )
  {
    if ( a5 < 0x13 )
    {
      *(_QWORD *)(a2 + 8) = 0;
      *(_OWORD *)(a2 + 16) = 0;
      return a2;
    }
    v13 = a1 + 16;
    v12 = (arrow::Status::State *)LZ4F_compressBegin(*(_QWORD *)(a1 + 8), a6, a5, a1 + 16);
    if ( (unsigned int)LZ4F_isError(v12) )
    {
      v14 = arrow::util::_anonymous_namespace_::LZ4Error(v18, v12, "LZ4 compress begin failed: ");
      arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v14);
      goto LABEL_6;
    }
    *(_BYTE *)(a1 + 72) = 0;
    v10 = (_DWORD)v12 + a6;
    v11 = a5 - (_QWORD)v12;
  }
  else
  {
    v13 = a1 + 16;
  }
  if ( v11 < LZ4F_compressBound(a3, v13) )
  {
    v18[0] = 0;
    v18[1] = v12;
LABEL_15:
    *(_QWORD *)(a2 + 8) = 0;
    *(_OWORD *)(a2 + 16) = *(_OWORD *)v18;
    return a2;
  }
  v15 = LZ4F_compressUpdate(*(_QWORD *)(a1 + 8), v10, v11, a4, (size_t)a3, 0);
  if ( !(unsigned int)LZ4F_isError(v15) )
  {
    v18[0] = a3;
    v18[1] = (arrow::Status::State *)((char *)v12 + v15);
    goto LABEL_15;
  }
  v16 = arrow::util::_anonymous_namespace_::LZ4Error(v18, v15, "LZ4 compress update failed: ");
  arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v16);
LABEL_6:
  if ( v18[1] )
    arrow::Status::State::`scalar deleting destructor'(v18[1], 1u);
  return a2;
}

```

## disassembly

```asm
0x1800e2240  mov     rax, rsp
0x1800e2243  push    rdi
0x1800e2244  push    r12
0x1800e2246  push    r13
0x1800e2248  push    r14
0x1800e224a  push    r15
0x1800e224c  sub     rsp, 50h
0x1800e2250  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800e2258  mov     [rax+8], rbx
0x1800e225c  mov     [rax+10h], rbp
0x1800e2260  mov     [rax+18h], rsi
0x1800e2264  mov     r13, r9
0x1800e2267  mov     r14, r8
0x1800e226a  mov     rbx, rdx
0x1800e226d  mov     rbp, rcx
0x1800e2270  mov     r15, [rsp+78h+arg_28]
0x1800e2278  mov     rdi, [rsp+78h+arg_20]
0x1800e2280  xor     esi, esi
0x1800e2282  cmp     [rcx+48h], sil
0x1800e2286  jz      loc_1800E2311
0x1800e228c  cmp     rdi, 13h
0x1800e2290  jnb     short loc_1800E22A2
0x1800e2292  xorps   xmm0, xmm0
0x1800e2295  mov     [rdx+8], rsi
0x1800e2299  movups  xmmword ptr [rdx+10h], xmm0
0x1800e229d  jmp     loc_1800E23A0
0x1800e22a2  lea     r12, [rcx+10h]
0x1800e22a6  mov     r9, r12
0x1800e22a9  mov     r8, rdi
0x1800e22ac  mov     rdx, r15
0x1800e22af  mov     rcx, [rcx+8]
0x1800e22b3  call    LZ4F_compressBegin
0x1800e22b8  mov     rsi, rax
0x1800e22bb  mov     rcx, rax
0x1800e22be  call    LZ4F_isError
0x1800e22c3  test    eax, eax
0x1800e22c5  jz      short loc_1800E2305
0x1800e22c7  lea     r8, aLz4CompressBeg; "LZ4 compress begin failed: "
0x1800e22ce  mov     rdx, rsi
0x1800e22d1  lea     rcx, [rsp+78h+var_40]
0x1800e22d6  call    arrow__util___anonymous_namespace___LZ4Error
0x1800e22db  nop
0x1800e22dc  mov     rdx, rax
0x1800e22df  mov     rcx, rbx
0x1800e22e2  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e22e7  nop
0x1800e22e8  mov     rcx, [rsp+78h+var_40+8]; this
0x1800e22ed  test    rcx, rcx
0x1800e22f0  jz      loc_1800E23A0
0x1800e22f6  mov     edx, 1; unsigned int
0x1800e22fb  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e2300  jmp     loc_1800E23A0
0x1800e2305  mov     byte ptr [rbp+48h], 0
0x1800e2309  add     r15, rsi
0x1800e230c  sub     rdi, rsi
0x1800e230f  jmp     short loc_1800E2315
0x1800e2311  lea     r12, [rcx+10h]
0x1800e2315  mov     rdx, r12
0x1800e2318  mov     rcx, r14
0x1800e231b  call    LZ4F_compressBound
0x1800e2320  xor     r12d, r12d
0x1800e2323  cmp     rdi, rax
0x1800e2326  jnb     short loc_1800E2334
0x1800e2328  mov     [rsp+78h+var_40], r12
0x1800e232d  mov     [rsp+78h+var_40+8], rsi
0x1800e2332  jmp     short loc_1800E2393
0x1800e2334  mov     [rsp+78h+var_50], r12; __int64
0x1800e2339  mov     [rsp+78h+Size], r14; Size
0x1800e233e  mov     r9, r13; int
0x1800e2341  mov     r8, rdi; int
0x1800e2344  mov     rdx, r15; int
0x1800e2347  mov     rcx, [rbp+8]; int
0x1800e234b  call    LZ4F_compressUpdate
0x1800e2350  mov     rdi, rax
0x1800e2353  mov     rcx, rax
0x1800e2356  call    LZ4F_isError
0x1800e235b  test    eax, eax
0x1800e235d  jz      short loc_1800E2385
0x1800e235f  lea     r8, aLz4CompressUpd; "LZ4 compress update failed: "
0x1800e2366  mov     rdx, rdi
0x1800e2369  lea     rcx, [rsp+78h+var_40]
0x1800e236e  call    arrow__util___anonymous_namespace___LZ4Error
0x1800e2373  nop
0x1800e2374  mov     rdx, rax
0x1800e2377  mov     rcx, rbx
0x1800e237a  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e237f  nop
0x1800e2380  jmp     loc_1800E22E8
0x1800e2385  mov     [rsp+78h+var_40], r14
0x1800e238a  lea     rax, [rdi+rsi]
0x1800e238e  mov     [rsp+78h+var_40+8], rax
0x1800e2393  mov     [rbx+8], r12
0x1800e2397  movups  xmm0, xmmword ptr [rsp+78h+var_40]
0x1800e239c  movups  xmmword ptr [rbx+10h], xmm0
0x1800e23a0  mov     rax, rbx
0x1800e23a3  lea     r11, [rsp+78h+var_28]
0x1800e23a8  mov     rbx, [r11+30h]
0x1800e23ac  mov     rbp, [r11+38h]
0x1800e23b0  mov     rsi, [r11+40h]
0x1800e23b4  mov     rsp, r11
0x1800e23b7  pop     r15
0x1800e23b9  pop     r14
0x1800e23bb  pop     r13
0x1800e23bd  pop     r12
0x1800e23bf  pop     rdi
0x1800e23c0  retn
```
