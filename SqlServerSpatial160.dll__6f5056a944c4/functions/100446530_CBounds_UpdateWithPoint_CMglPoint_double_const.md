# CBounds::UpdateWithPoint(CMglPoint<double> const &)

- ea: `0x100446530`
- end: `0x1004465c2`
- name: `?UpdateWithPoint@CBounds@@QEAAXAEBV?$CMglPoint@N@@@Z`
- size: `146`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x100435b40`
- `0x1004465d0`
- `0x10044cf80`

## callees

- `0x100446530`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100446595`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x1004465a5`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100446595`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x1004465a5`

## pseudocode

```c
void __fastcall CBounds::UpdateWithPoint(__int64 a1, double *a2)
{
  double v2; // xmm1_8
  double v4; // xmm1_8
  double X[3]; // [rsp+20h] [rbp-18h]

  v2 = *a2;
  if ( *(double *)a1 > *a2 )
  {
    *(double *)a1 = v2;
    v2 = *a2;
  }
  if ( v2 > *(double *)(a1 + 8) )
    *(double *)(a1 + 8) = v2;
  v4 = a2[1];
  if ( *(double *)(a1 + 16) > v4 )
  {
    *(double *)(a1 + 16) = v4;
    v4 = a2[1];
  }
  if ( v4 > *(double *)(a1 + 24) )
    *(double *)(a1 + 24) = v4;
  *(_OWORD *)X = *(_OWORD *)a2;
  *(_BYTE *)(a1 + 32) = *(_BYTE *)(a1 + 32) || _isnan(X[0]) || _isnan(X[1]);
}

```

## disassembly

```asm
0x100446530  push    rbx
0x100446532  sub     rsp, 30h
0x100446536  movsd   xmm1, qword ptr [rdx]
0x10044653a  mov     rbx, rcx
0x10044653d  movsd   xmm0, qword ptr [rcx]
0x100446541  comisd  xmm0, xmm1
0x100446545  jbe     short loc_10044654F
0x100446547  movsd   qword ptr [rcx], xmm1
0x10044654b  movsd   xmm1, qword ptr [rdx]
0x10044654f  comisd  xmm1, qword ptr [rcx+8]
0x100446554  jbe     short loc_10044655B
0x100446556  movsd   qword ptr [rcx+8], xmm1
0x10044655b  movsd   xmm1, qword ptr [rdx+8]
0x100446560  movsd   xmm0, qword ptr [rcx+10h]
0x100446565  comisd  xmm0, xmm1
0x100446569  jbe     short loc_100446575
0x10044656b  movsd   qword ptr [rcx+10h], xmm1
0x100446570  movsd   xmm1, qword ptr [rdx+8]
0x100446575  comisd  xmm1, qword ptr [rcx+18h]
0x10044657a  jbe     short loc_100446581
0x10044657c  movsd   qword ptr [rcx+18h], xmm1
0x100446581  cmp     byte ptr [rcx+20h], 0
0x100446585  movups  xmm0, xmmword ptr [rdx]
0x100446588  movaps  xmmword ptr [rsp+38h+X], xmm0
0x10044658d  jnz     short loc_1004465B8
0x10044658f  movsd   xmm0, [rsp+38h+X]; X
0x100446595  call    cs:__imp__isnan
0x10044659b  test    eax, eax
0x10044659d  jnz     short loc_1004465B8
0x10044659f  movsd   xmm0, [rsp+38h+X+8]; X
0x1004465a5  call    cs:__imp__isnan
0x1004465ab  test    eax, eax
0x1004465ad  jnz     short loc_1004465B8
0x1004465af  mov     [rbx+20h], al
0x1004465b2  add     rsp, 30h
0x1004465b6  pop     rbx
0x1004465b7  retn
0x1004465b8  mov     byte ptr [rbx+20h], 1
0x1004465bc  add     rsp, 30h
0x1004465c0  pop     rbx
0x1004465c1  retn
```
