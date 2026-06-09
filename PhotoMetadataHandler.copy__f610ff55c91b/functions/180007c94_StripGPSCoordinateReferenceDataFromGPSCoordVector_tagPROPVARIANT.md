# StripGPSCoordinateReferenceDataFromGPSCoordVector(tagPROPVARIANT *)

- ea: `0x180007c94`
- end: `0x180007d88`
- name: `?StripGPSCoordinateReferenceDataFromGPSCoordVector@@YAJPEAUtagPROPVARIANT@@@Z`
- size: `244`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarDest)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003970`
- `0x180012440`

## callees

- `0x180007c94`
- `0x180007d90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007d3c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007d3c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007ce6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007d29`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007ce6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007d29`

## pseudocode

```c
__int64 __fastcall StripGPSCoordinateReferenceDataFromGPSCoordVector(PROPVARIANT *pvarDest)
{
  int vt; // ecx
  HRESULT v3; // ebx
  int v4; // ecx
  __int64 i; // rdx
  __int64 v7; // rdx
  PROPVARIANT pvar; // [rsp+20h] [rbp-28h] BYREF

  vt = pvarDest->vt;
  v3 = -2147024809;
  memset(&pvar, 0, sizeof(pvar));
  v4 = vt - 4116;
  if ( v4 )
  {
    if ( v4 != 1 )
      goto LABEL_5;
    if ( pvarDest->lVal > 3u )
    {
      v3 = CoTaskMemAllocWithInit(0x18u, (void **)&pvar.bstrblobVal.pData);
      if ( v3 < 0 )
        goto LABEL_5;
      pvar.lVal = 3;
      pvar.vt = 4117;
      for ( i = 0; i != 3; ++i )
        *(_QWORD *)&pvar.bstrblobVal.pData[8 * i] = *(_QWORD *)&pvarDest->bstrblobVal.pData[8 * i];
      goto LABEL_9;
    }
LABEL_6:
    v3 = 0;
    goto LABEL_5;
  }
  if ( pvarDest->lVal <= 3u )
    goto LABEL_6;
  v3 = CoTaskMemAllocWithInit(0x18u, (void **)&pvar.bstrblobVal.pData);
  if ( v3 < 0 )
    goto LABEL_5;
  pvar.vt = 4116;
  v7 = 0;
  pvar.lVal = 3;
  do
  {
    *(_QWORD *)&pvar.bstrblobVal.pData[8 * v7] = *(_QWORD *)&pvarDest->bstrblobVal.pData[8 * v7];
    ++v7;
  }
  while ( v7 != 3 );
LABEL_9:
  v3 = PropVariantClear(pvarDest);
  if ( v3 >= 0 )
    v3 = PropVariantCopy(pvarDest, &pvar);
LABEL_5:
  PropVariantClear(&pvar);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180007c94  push    rbp
0x180007c96  push    rbx
0x180007c97  push    rsi
0x180007c98  push    rdi
0x180007c99  mov     rbp, rsp
0x180007c9c  sub     rsp, 48h
0x180007ca0  mov     rdi, rcx
0x180007ca3  xor     eax, eax
0x180007ca5  movzx   ecx, word ptr [rcx]
0x180007ca8  mov     esi, 1014h
0x180007cad  mov     qword ptr [rbp+pvar+10h], rax
0x180007cb1  xorps   xmm0, xmm0
0x180007cb4  mov     ebx, 80070057h
0x180007cb9  movups  xmmword ptr [rbp+pvar], xmm0
0x180007cbd  sub     ecx, esi
0x180007cbf  jz      loc_180007D46
0x180007cc5  cmp     ecx, 1
0x180007cc8  jnz     short loc_180007CE2
0x180007cca  cmp     dword ptr [rdi+8], 3
0x180007cce  jbe     short loc_180007CF7
0x180007cd0  lea     rdx, [rbp+pvar+10h]; void **
0x180007cd4  lea     ecx, [rax+18h]; Size
0x180007cd7  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180007cdc  mov     ebx, eax
0x180007cde  test    eax, eax
0x180007ce0  jns     short loc_180007CFB
0x180007ce2  lea     rcx, [rbp+pvar]; pvar
0x180007ce6  call    cs:__imp_PropVariantClear
0x180007cec  mov     eax, ebx
0x180007cee  add     rsp, 48h
0x180007cf2  pop     rdi
0x180007cf3  pop     rsi
0x180007cf4  pop     rbx
0x180007cf5  pop     rbp
0x180007cf6  retn
0x180007cf7  xor     ebx, ebx
0x180007cf9  jmp     short loc_180007CE2
0x180007cfb  mov     eax, 1015h
0x180007d00  mov     dword ptr [rbp+pvar+8], 3
0x180007d07  mov     word ptr [rbp+pvar], ax
0x180007d0b  xor     edx, edx
0x180007d0d  mov     rax, [rdi+10h]
0x180007d11  mov     rcx, [rax+rdx*8]
0x180007d15  mov     rax, qword ptr [rbp+pvar+10h]
0x180007d19  mov     [rax+rdx*8], rcx
0x180007d1d  inc     rdx
0x180007d20  cmp     rdx, 3
0x180007d24  jnz     short loc_180007D0D
0x180007d26  mov     rcx, rdi; pvar
0x180007d29  call    cs:__imp_PropVariantClear
0x180007d2f  mov     ebx, eax
0x180007d31  test    eax, eax
0x180007d33  js      short loc_180007CE2
0x180007d35  lea     rdx, [rbp+pvar]; pvarSrc
0x180007d39  mov     rcx, rdi; pvarDest
0x180007d3c  call    cs:__imp_PropVariantCopy
0x180007d42  mov     ebx, eax
0x180007d44  jmp     short loc_180007CE2
0x180007d46  cmp     dword ptr [rdi+8], 3
0x180007d4a  jbe     short loc_180007CF7
0x180007d4c  lea     rdx, [rbp+pvar+10h]; void **
0x180007d50  mov     ecx, 18h; Size
0x180007d55  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180007d5a  mov     ebx, eax
0x180007d5c  test    eax, eax
0x180007d5e  js      short loc_180007CE2
0x180007d60  mov     word ptr [rbp+pvar], si
0x180007d64  xor     edx, edx
0x180007d66  mov     dword ptr [rbp+pvar+8], 3
0x180007d6d  mov     rax, [rdi+10h]
0x180007d71  mov     rcx, [rax+rdx*8]
0x180007d75  mov     rax, qword ptr [rbp+pvar+10h]
0x180007d79  mov     [rax+rdx*8], rcx
0x180007d7d  inc     rdx
0x180007d80  cmp     rdx, 3
0x180007d84  jnz     short loc_180007D6D
0x180007d86  jmp     short loc_180007D26
```
