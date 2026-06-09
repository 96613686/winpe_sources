# CoerceStringVectors(tagPROPVARIANT const &,tagPROPVARIANT *)

- ea: `0x1800c597c`
- end: `0x1800c5a14`
- name: `?CoerceStringVectors@@YAJAEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `152`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180048d3c`

## callees

- `0x1800c597c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800c59e5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800c59e5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c59fa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c59fa`

## pseudocode

```c
__int64 __fastcall CoerceStringVectors(const PROPVARIANT *a1, PROPVARIANT *a2)
{
  VARTYPE v3; // dx
  const PROPVARIANT *v4; // rdx
  BYTE *v5; // rax
  HRESULT v6; // ebx
  _BYTE pvarSrc[20]; // [rsp+20h] [rbp-28h] BYREF
  int v9; // [rsp+34h] [rbp-14h]

  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  v3 = *(_WORD *)a1;
  if ( (unsigned __int16)(*(_WORD *)a1 - 4126) <= 1u )
  {
    memset(pvarSrc, 0, sizeof(pvarSrc));
    v9 = 0;
    if ( *((_DWORD *)a1 + 2) )
    {
      v5 = (BYTE *)*((_QWORD *)a1 + 2);
      *(_WORD *)pvarSrc = v3 & 0xFFF;
      *(_QWORD *)&pvarSrc[8] = *(_QWORD *)v5;
    }
    v4 = (const PROPVARIANT *)pvarSrc;
  }
  else
  {
    v4 = a1;
  }
  v6 = PropVariantCopy(a2, v4);
  if ( v6 < 0 )
    PropVariantClear(a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800c597c  mov     [rsp+arg_0], rbx
0x1800c5981  push    rdi
0x1800c5982  sub     rsp, 40h
0x1800c5986  xor     eax, eax
0x1800c5988  xorps   xmm0, xmm0
0x1800c598b  movups  xmmword ptr [rdx], xmm0
0x1800c598e  mov     [rdx+10h], rax
0x1800c5992  mov     rdi, rdx
0x1800c5995  movzx   edx, word ptr [rcx]
0x1800c5998  mov     r8d, 101Eh
0x1800c599e  movzx   eax, dx
0x1800c59a1  sub     ax, r8w
0x1800c59a5  cmp     ax, 1
0x1800c59a9  jbe     short loc_1800C59B0
0x1800c59ab  mov     rdx, rcx
0x1800c59ae  jmp     short loc_1800C59E2
0x1800c59b0  xor     eax, eax
0x1800c59b2  mov     dword ptr [rsp+48h+pvarSrc], eax
0x1800c59b6  movups  xmmword ptr [rsp+48h+pvarSrc+4], xmm0
0x1800c59bb  mov     [rsp+48h+var_14], eax
0x1800c59bf  cmp     [rcx+8], eax
0x1800c59c2  jz      short loc_1800C59DD
0x1800c59c4  mov     eax, 0FFFh
0x1800c59c9  and     dx, ax
0x1800c59cc  mov     rax, [rcx+10h]
0x1800c59d0  mov     word ptr [rsp+48h+pvarSrc], dx
0x1800c59d5  mov     rcx, [rax]
0x1800c59d8  mov     qword ptr [rsp+48h+pvarSrc+8], rcx
0x1800c59dd  lea     rdx, [rsp+48h+pvarSrc]; pvarSrc
0x1800c59e2  mov     rcx, rdi; pvarDest
0x1800c59e5  call    cs:__imp_PropVariantCopy
0x1800c59ec  nop     dword ptr [rax+rax+00h]
0x1800c59f1  mov     ebx, eax
0x1800c59f3  test    eax, eax
0x1800c59f5  jns     short loc_1800C5A06
0x1800c59f7  mov     rcx, rdi; pvar
0x1800c59fa  call    cs:__imp_PropVariantClear
0x1800c5a01  nop     dword ptr [rax+rax+00h]
0x1800c5a06  mov     eax, ebx
0x1800c5a08  mov     rbx, [rsp+48h+arg_0]
0x1800c5a0d  add     rsp, 40h
0x1800c5a11  pop     rdi
0x1800c5a12  retn
```
