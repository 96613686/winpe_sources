# CoerceStringVectors(tagPROPVARIANT const &,tagPROPVARIANT *)

- ea: `0x1800c35d0`
- end: `0x1800c365b`
- name: `?CoerceStringVectors@@YAJAEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `139`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180055aa4`

## callees

- `0x1800c35d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800c3639`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800c3639`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c3648`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c3648`

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
0x1800c35d0  mov     [rsp+arg_0], rbx
0x1800c35d5  push    rdi
0x1800c35d6  sub     rsp, 40h
0x1800c35da  xor     eax, eax
0x1800c35dc  xorps   xmm0, xmm0
0x1800c35df  movups  xmmword ptr [rdx], xmm0
0x1800c35e2  mov     [rdx+10h], rax
0x1800c35e6  mov     rdi, rdx
0x1800c35e9  movzx   edx, word ptr [rcx]
0x1800c35ec  mov     r8d, 101Eh
0x1800c35f2  movzx   eax, dx
0x1800c35f5  sub     ax, r8w
0x1800c35f9  cmp     ax, 1
0x1800c35fd  jbe     short loc_1800C3604
0x1800c35ff  mov     rdx, rcx
0x1800c3602  jmp     short loc_1800C3636
0x1800c3604  xor     eax, eax
0x1800c3606  mov     dword ptr [rsp+48h+pvarSrc], eax
0x1800c360a  movups  xmmword ptr [rsp+48h+pvarSrc+4], xmm0
0x1800c360f  mov     [rsp+48h+var_14], eax
0x1800c3613  cmp     [rcx+8], eax
0x1800c3616  jz      short loc_1800C3631
0x1800c3618  mov     eax, 0FFFh
0x1800c361d  and     dx, ax
0x1800c3620  mov     rax, [rcx+10h]
0x1800c3624  mov     word ptr [rsp+48h+pvarSrc], dx
0x1800c3629  mov     rcx, [rax]
0x1800c362c  mov     qword ptr [rsp+48h+pvarSrc+8], rcx
0x1800c3631  lea     rdx, [rsp+48h+pvarSrc]; pvarSrc
0x1800c3636  mov     rcx, rdi; pvarDest
0x1800c3639  call    cs:__imp_PropVariantCopy
0x1800c363f  mov     ebx, eax
0x1800c3641  test    eax, eax
0x1800c3643  jns     short loc_1800C364E
0x1800c3645  mov     rcx, rdi; pvar
0x1800c3648  call    cs:__imp_PropVariantClear
0x1800c364e  mov     eax, ebx
0x1800c3650  mov     rbx, [rsp+48h+arg_0]
0x1800c3655  add     rsp, 40h
0x1800c3659  pop     rdi
0x1800c365a  retn
```
