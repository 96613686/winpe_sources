# StripGPSCoordinateReferenceDataFromGPSCoordVector(tagPROPVARIANT *)

- ea: `0x180009020`
- end: `0x18000912b`
- name: `?StripGPSCoordinateReferenceDataFromGPSCoordVector@@YAJPEAUtagPROPVARIANT@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarDest)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003900`
- `0x180012d00`

## callees

- `0x180009020`
- `0x1800096a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800090d5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800090d5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009072`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800090bc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009072`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800090bc`

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
0x180009020  push    rbp
0x180009022  push    rbx
0x180009023  push    rsi
0x180009024  push    rdi
0x180009025  mov     rbp, rsp
0x180009028  sub     rsp, 48h
0x18000902c  mov     rdi, rcx
0x18000902f  xor     eax, eax
0x180009031  movzx   ecx, word ptr [rcx]
0x180009034  mov     esi, 1014h
0x180009039  mov     qword ptr [rbp+pvar+10h], rax
0x18000903d  xorps   xmm0, xmm0
0x180009040  mov     ebx, 80070057h
0x180009045  movups  xmmword ptr [rbp+pvar], xmm0
0x180009049  sub     ecx, esi
0x18000904b  jz      loc_1800090E5
0x180009051  cmp     ecx, 1
0x180009054  jnz     short loc_18000906E
0x180009056  cmp     dword ptr [rdi+8], 3
0x18000905a  jbe     short loc_18000908A
0x18000905c  lea     rdx, [rbp+pvar+10h]; void **
0x180009060  lea     ecx, [rax+18h]; Size
0x180009063  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180009068  mov     ebx, eax
0x18000906a  test    eax, eax
0x18000906c  jns     short loc_18000908E
0x18000906e  lea     rcx, [rbp+pvar]; pvar
0x180009072  call    cs:__imp_PropVariantClear
0x180009079  nop     dword ptr [rax+rax+00h]
0x18000907e  mov     eax, ebx
0x180009080  add     rsp, 48h
0x180009084  pop     rdi
0x180009085  pop     rsi
0x180009086  pop     rbx
0x180009087  pop     rbp
0x180009088  retn
0x18000908a  xor     ebx, ebx
0x18000908c  jmp     short loc_18000906E
0x18000908e  mov     eax, 1015h
0x180009093  mov     dword ptr [rbp+pvar+8], 3
0x18000909a  mov     word ptr [rbp+pvar], ax
0x18000909e  xor     edx, edx
0x1800090a0  mov     rax, [rdi+10h]
0x1800090a4  mov     rcx, [rax+rdx*8]
0x1800090a8  mov     rax, qword ptr [rbp+pvar+10h]
0x1800090ac  mov     [rax+rdx*8], rcx
0x1800090b0  inc     rdx
0x1800090b3  cmp     rdx, 3
0x1800090b7  jnz     short loc_1800090A0
0x1800090b9  mov     rcx, rdi; pvar
0x1800090bc  call    cs:__imp_PropVariantClear
0x1800090c3  nop     dword ptr [rax+rax+00h]
0x1800090c8  mov     ebx, eax
0x1800090ca  test    eax, eax
0x1800090cc  js      short loc_18000906E
0x1800090ce  lea     rdx, [rbp+pvar]; pvarSrc
0x1800090d2  mov     rcx, rdi; pvarDest
0x1800090d5  call    cs:__imp_PropVariantCopy
0x1800090dc  nop     dword ptr [rax+rax+00h]
0x1800090e1  mov     ebx, eax
0x1800090e3  jmp     short loc_18000906E
0x1800090e5  cmp     dword ptr [rdi+8], 3
0x1800090e9  jbe     short loc_18000908A
0x1800090eb  lea     rdx, [rbp+pvar+10h]; void **
0x1800090ef  mov     ecx, 18h; Size
0x1800090f4  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x1800090f9  mov     ebx, eax
0x1800090fb  test    eax, eax
0x1800090fd  js      loc_18000906E
0x180009103  mov     word ptr [rbp+pvar], si
0x180009107  xor     edx, edx
0x180009109  mov     dword ptr [rbp+pvar+8], 3
0x180009110  mov     rax, [rdi+10h]
0x180009114  mov     rcx, [rax+rdx*8]
0x180009118  mov     rax, qword ptr [rbp+pvar+10h]
0x18000911c  mov     [rax+rdx*8], rcx
0x180009120  inc     rdx
0x180009123  cmp     rdx, 3
0x180009127  jnz     short loc_180009110
0x180009129  jmp     short loc_1800090B9
```
