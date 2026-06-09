# CGeodeticScannerConstruction::CMerger::CreatePointFigures(void)

- ea: `0x1004631e0`
- end: `0x100463369`
- name: `?CreatePointFigures@CMerger@CGeodeticScannerConstruction@@AEAAJXZ`
- size: `393`
- prototype: `__int64 __fastcall(CGeodeticScannerConstruction::CMerger *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100463370`

## callees

- `0x1004631e0`
- `0x1004656a0`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x1004631ff`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x100463217`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x1004631ff`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x100463217`

## pseudocode

```c
__int64 __fastcall CGeodeticScannerConstruction::CMerger::CreatePointFigures(void **this)
{
  unsigned int v2; // ebx
  unsigned int v3; // eax
  unsigned int v4; // edx
  unsigned int v5; // r8d
  double *v6; // r10
  double v7; // xmm0_8
  double v8; // xmm1_8
  unsigned int i; // edx
  _QWORD *v10; // r8
  unsigned int v11; // esi
  _QWORD *v12; // rax
  char *v13; // rbp
  void *v14; // rbx
  __int64 result; // rax
  char v16[40]; // [rsp+20h] [rbp-28h] BYREF

  v2 = 0;
  qsort(this[13], *((unsigned int *)this + 25), 0x18u, CompareT<CGeodeticScannerConstruction::CPointFigure>);
  qsort(this[11], *((unsigned int *)this + 21), 8u, CompareT<double>);
  v3 = *((_DWORD *)this + 25);
  v4 = 0;
  v5 = 0;
  if ( v3 )
  {
    while ( 1 )
    {
      if ( v5 >= *((_DWORD *)this + 21) )
        goto LABEL_8;
      v6 = (double *)this[13];
      v7 = v6[3 * v4 + 1];
      v8 = *((double *)this[11] + v5);
      if ( v8 > v7 )
        goto LABEL_6;
      ++v5;
      if ( v7 <= v8 )
        break;
LABEL_7:
      v3 = *((_DWORD *)this + 25);
      if ( v4 >= v3 )
        goto LABEL_8;
    }
    *(_QWORD *)&v6[3 * v4 + 2] = 0x500000000LL;
LABEL_6:
    ++v4;
    goto LABEL_7;
  }
LABEL_8:
  for ( i = 1; i < v3; ++i )
  {
    v10 = this[13];
    if ( *(double *)&v10[3 * i + 1] == *(double *)&v10[3 * i - 2] )
      v10[3 * i + 2] = 0x500000000LL;
    v3 = *((_DWORD *)this + 25);
  }
  v11 = 0;
  if ( !v3 )
    return v2;
  while ( 1 )
  {
    v12 = this[13];
    v13 = (char *)&v12[3 * v11];
    if ( (unsigned __int8)BYTE4(*((_QWORD *)v13 + 2)) != 5 )
    {
      v14 = this[14];
      *(_OWORD *)v13 = *(_OWORD *)CGeodeticScannerConstruction::RetrieveOriginalPoint(
                                    v16,
                                    this[32],
                                    v12[3 * v11 + 2],
                                    v13);
      result = (*(__int64 (__fastcall **)(void *, char *, __int64, char *))(*(_QWORD *)v14 + 64LL))(
                 v14,
                 v13,
                 1,
                 v13 + 16);
      v2 = result;
      if ( (int)result < 0 )
        break;
    }
    if ( ++v11 >= *((_DWORD *)this + 25) )
      return v2;
  }
  _mm_lfence();
  return result;
}

```

## disassembly

```asm
0x1004631e0  push    rbx
0x1004631e2  push    rsi
0x1004631e3  push    rdi
0x1004631e4  sub     rsp, 30h
0x1004631e8  mov     edx, [rcx+64h]; NumOfElements
0x1004631eb  lea     r9, ??$CompareT@VCPointFigure@CGeodeticScannerConstruction@@@@YAHPEBX0@Z; CompareFunction
0x1004631f2  mov     rdi, rcx
0x1004631f5  xor     ebx, ebx
0x1004631f7  mov     rcx, [rcx+68h]; Base
0x1004631fb  lea     r8d, [rbx+18h]; SizeOfElements
0x1004631ff  call    cs:__imp_qsort
0x100463205  mov     edx, [rdi+54h]; NumOfElements
0x100463208  lea     r9, ??$CompareT@N@@YAHPEBX0@Z; CompareFunction
0x10046320f  mov     rcx, [rdi+58h]; Base
0x100463213  lea     r8d, [rbx+8]; SizeOfElements
0x100463217  call    cs:__imp_qsort
0x10046321d  mov     eax, [rdi+64h]
0x100463220  mov     edx, ebx
0x100463222  mov     r8d, ebx
0x100463225  test    eax, eax
0x100463227  jz      short loc_100463289
0x100463229  nop     dword ptr [rax+00000000h]
0x100463230  cmp     r8d, [rdi+54h]
0x100463234  jnb     short loc_100463289
0x100463236  mov     r10, [rdi+68h]
0x10046323a  mov     eax, edx
0x10046323c  mov     ecx, r8d
0x10046323f  lea     r9, [rax+rax*2]
0x100463243  mov     rax, [rdi+58h]
0x100463247  movsd   xmm0, qword ptr [r10+r9*8+8]
0x10046324e  movsd   xmm1, qword ptr [rax+rcx*8]
0x100463253  comisd  xmm1, xmm0
0x100463257  ja      short loc_100463280
0x100463259  inc     r8d
0x10046325c  comisd  xmm0, xmm1
0x100463260  ja      short loc_100463282
0x100463262  mov     [rsp+48h+arg_0], rbx
0x100463267  mov     word ptr [rsp+48h+arg_0+4], 5
0x10046326e  mov     dword ptr [rsp+48h+arg_0], ebx
0x100463272  mov     byte ptr [rsp+48h+arg_0+6], bl
0x100463276  mov     rax, [rsp+48h+arg_0]
0x10046327b  mov     [r10+r9*8+10h], rax
0x100463280  inc     edx
0x100463282  mov     eax, [rdi+64h]
0x100463285  cmp     edx, eax
0x100463287  jb      short loc_100463230
0x100463289  mov     edx, 1
0x10046328e  cmp     eax, edx
0x100463290  jbe     short loc_1004632DC
0x100463292  mov     r8, [rdi+68h]
0x100463296  mov     eax, edx
0x100463298  lea     r9, [rax+rax*2]
0x10046329c  movsd   xmm0, qword ptr [r8+r9*8+8]
0x1004632a3  lea     eax, [rdx-1]
0x1004632a6  lea     rax, [rax+rax*2]
0x1004632aa  ucomisd xmm0, qword ptr [r8+rax*8+8]
0x1004632b1  jp      short loc_1004632D3
0x1004632b3  jnz     short loc_1004632D3
0x1004632b5  mov     [rsp+48h+arg_8], rbx
0x1004632ba  mov     word ptr [rsp+48h+arg_8+4], 5
0x1004632c1  mov     dword ptr [rsp+48h+arg_8], ebx
0x1004632c5  mov     byte ptr [rsp+48h+arg_8+6], bl
0x1004632c9  mov     rax, [rsp+48h+arg_8]
0x1004632ce  mov     [r8+r9*8+10h], rax
0x1004632d3  mov     eax, [rdi+64h]
0x1004632d6  inc     edx
0x1004632d8  cmp     edx, eax
0x1004632da  jb      short loc_100463292
0x1004632dc  mov     [rsp+48h+arg_10], rbp
0x1004632e1  mov     esi, ebx
0x1004632e3  mov     [rsp+48h+arg_18], r14
0x1004632e8  test    eax, eax
0x1004632ea  jz      short loc_100463350
0x1004632ec  nop     dword ptr [rax+00h]
0x1004632f0  mov     eax, esi
0x1004632f2  lea     rcx, [rax+rax*2]
0x1004632f6  mov     rax, [rdi+68h]
0x1004632fa  mov     r8, [rax+rcx*8+10h]
0x1004632ff  lea     rbp, [rax+rcx*8]
0x100463303  mov     rax, r8
0x100463306  shr     rax, 20h
0x10046330a  cmp     al, 5
0x10046330c  jz      short loc_100463349
0x10046330e  mov     rdx, [rdi+100h]
0x100463315  lea     rcx, [rsp+48h+var_28]
0x10046331a  mov     rbx, [rdi+70h]
0x10046331e  mov     r9, rbp
0x100463321  call    ?RetrieveOriginalPoint@CGeodeticScannerConstruction@@KA?AV?$CMglPoint@N@@PEBVCOriginalPoints@@_KAEBU?$MglPoint@N@@@Z; CGeodeticScannerConstruction::RetrieveOriginalPoint(COriginalPoints const *,unsigned __int64,MglPoint<double> const &)
0x100463326  lea     r9, [rbp+10h]
0x10046332a  mov     r8d, 1
0x100463330  mov     rdx, rbp
0x100463333  mov     rcx, rbx
0x100463336  movups  xmm0, xmmword ptr [rax]
0x100463339  movups  xmmword ptr [rbp+0], xmm0
0x10046333d  mov     rax, [rbx]
0x100463340  call    qword ptr [rax+40h]
0x100463343  mov     ebx, eax
0x100463345  test    eax, eax
0x100463347  js      short loc_100463364
0x100463349  inc     esi
0x10046334b  cmp     esi, [rdi+64h]
0x10046334e  jb      short loc_1004632F0
0x100463350  mov     eax, ebx
0x100463352  mov     r14, [rsp+48h+arg_18]
0x100463357  mov     rbp, [rsp+48h+arg_10]
0x10046335c  add     rsp, 30h
0x100463360  pop     rdi
0x100463361  pop     rsi
0x100463362  pop     rbx
0x100463363  retn
0x100463364  lfence
0x100463367  jmp     short loc_100463352
```
