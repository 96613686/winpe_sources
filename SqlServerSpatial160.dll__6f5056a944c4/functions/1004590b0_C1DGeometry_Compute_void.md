# C1DGeometry::Compute(void)

- ea: `0x1004590b0`
- end: `0x10045918b`
- name: `?Compute@C1DGeometry@@UEAAXXZ`
- size: `219`
- prototype: `void __fastcall(C1DGeometry *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100417030`
- `0x1004190d0`
- `0x10041aca0`
- `0x10041bd30`

## callees

- `0x1004590b0`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x1004590d8`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x1004590d8`

## pseudocode

```c
void __fastcall C1DGeometry::Compute(void **this)
{
  int v2; // esi
  __int64 v3; // rdi
  __int64 v4; // rcx
  unsigned int v5; // edx
  double i; // xmm2_8
  double *v7; // r8
  int v8; // r9d
  int v9; // r9d
  _QWORD *v10; // r8
  double v11; // xmm1_8
  double v12; // xmm0_8

  v2 = 0;
  v3 = 0;
  qsort(this[3], *((unsigned int *)this + 5), 8u, CompareT<C1DGeometry::CIntervalBound>);
  v4 = 0;
  v5 = 1;
  for ( i = 0.0; (unsigned int)v4 < *((_DWORD *)this + 5); v2 = v9 )
  {
    v7 = (double *)this[3];
    v8 = -1;
    if ( v7[v4] > 0.0 )
      v8 = 1;
    v9 = v2 + v8;
    if ( !(v2 * v9) )
    {
      v7[v3] = v7[v4];
      v3 = (unsigned int)(v3 + 1);
    }
    v4 = (unsigned int)(v4 + 1);
  }
  *((_DWORD *)this + 5) = v3;
  this[1] = 0;
  if ( (unsigned int)v3 > 1 )
  {
    v10 = this[3];
    do
    {
      *(_QWORD *)&v11 = v10[v5] & _xmm;
      *(_QWORD *)&v12 = v10[v5 - 1] & _xmm;
      v5 += 2;
      i = i + v11 - v12;
      *((double *)this + 1) = i;
    }
    while ( v5 < (unsigned int)v3 );
  }
}

```

## disassembly

```asm
0x1004590b0  mov     [rsp+arg_0], rbx
0x1004590b5  mov     [rsp+arg_8], rsi
0x1004590ba  push    rdi
0x1004590bb  sub     rsp, 20h
0x1004590bf  mov     edx, [rcx+14h]; NumOfElements
0x1004590c2  lea     r9, ??$CompareT@VCIntervalBound@C1DGeometry@@@@YAHPEBX0@Z; CompareFunction
0x1004590c9  mov     rbx, rcx
0x1004590cc  xor     esi, esi
0x1004590ce  mov     rcx, [rcx+18h]; Base
0x1004590d2  xor     edi, edi
0x1004590d4  lea     r8d, [rsi+8]; SizeOfElements
0x1004590d8  call    cs:__imp_qsort
0x1004590de  xor     ecx, ecx
0x1004590e0  lea     edx, [rsi+1]
0x1004590e3  xorps   xmm2, xmm2
0x1004590e6  cmp     [rbx+14h], ecx
0x1004590e9  jbe     short loc_10045912D
0x1004590eb  nop     dword ptr [rax+rax+00h]
0x1004590f0  mov     r8, [rbx+18h]
0x1004590f4  mov     r9d, 0FFFFFFFFh
0x1004590fa  movsd   xmm0, qword ptr [r8+rcx*8]
0x100459100  comisd  xmm0, xmm2
0x100459104  cmova   r9d, edx
0x100459108  add     r9d, esi
0x10045910b  mov     eax, r9d
0x10045910e  imul    eax, esi
0x100459111  test    eax, eax
0x100459113  jnz     short loc_100459123
0x100459115  movsd   xmm0, qword ptr [r8+rcx*8]
0x10045911b  movsd   qword ptr [r8+rdi*8], xmm0
0x100459121  inc     edi
0x100459123  inc     ecx
0x100459125  mov     esi, r9d
0x100459128  cmp     ecx, [rbx+14h]
0x10045912b  jb      short loc_1004590F0
0x10045912d  mov     [rbx+14h], edi
0x100459130  mov     qword ptr [rbx+8], 0
0x100459138  cmp     edi, edx
0x10045913a  jbe     short loc_10045917B
0x10045913c  mov     r8, [rbx+18h]
0x100459140  movsd   xmm3, qword ptr cs:__xmm@7fffffffffffffff7fffffffffffffff
0x100459148  nop     dword ptr [rax+rax+00000000h]
0x100459150  mov     eax, edx
0x100459152  movsd   xmm1, qword ptr [r8+rax*8]
0x100459158  lea     eax, [rdx-1]
0x10045915b  movsd   xmm0, qword ptr [r8+rax*8]
0x100459161  andps   xmm1, xmm3
0x100459164  andps   xmm0, xmm3
0x100459167  add     edx, 2
0x10045916a  subsd   xmm1, xmm0
0x10045916e  addsd   xmm2, xmm1
0x100459172  movsd   qword ptr [rbx+8], xmm2
0x100459177  cmp     edx, edi
0x100459179  jb      short loc_100459150
0x10045917b  mov     rbx, [rsp+28h+arg_0]
0x100459180  mov     rsi, [rsp+28h+arg_8]
0x100459185  add     rsp, 20h
0x100459189  pop     rdi
0x10045918a  retn
```
