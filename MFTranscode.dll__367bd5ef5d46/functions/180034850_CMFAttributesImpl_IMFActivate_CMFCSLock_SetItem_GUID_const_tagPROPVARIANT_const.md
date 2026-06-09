# CMFAttributesImpl<IMFActivate,CMFCSLock>::SetItem(_GUID const &,tagPROPVARIANT const &)

- ea: `0x180034850`
- end: `0x1800348ec`
- name: `?SetItem@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@UEAAJAEBU_GUID@@AEBUtagPROPVARIANT@@@Z`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180031f1c`
- `0x180034850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800348db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800348db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034866`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034866`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800348c8`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800348c8`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFActivate,CMFCSLock>::SetItem(__int64 a1, __int64 a2, const PROPVARIANT *a3)
{
  PROPVARIANT *Item; // rax
  unsigned int v7; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = (PROPVARIANT *)CMFAttributesImpl<IMFActivate,CMFCSLock>::CreateItem(a1, a2);
  if ( a3->vt == 5
    || a3->vt == 13
    || a3->vt == 19
    || a3->vt == 21
    || a3->vt == 31
    || a3->vt == 72
    || a3->vt == 4113
    || a3->vt == 4127 )
  {
    if ( Item )
    {
      v7 = PropVariantCopy(Item, a3);
      *(_DWORD *)(a1 + 64) = 1;
    }
    else
    {
      v7 = -2147024882;
    }
  }
  else
  {
    v7 = -1072875843;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v7;
}

```

## disassembly

```asm
0x180034850  push    rbx
0x180034852  push    rbp
0x180034853  push    rsi
0x180034854  push    rdi
0x180034855  sub     rsp, 28h
0x180034859  mov     rdi, rcx
0x18003485c  mov     rbp, r8
0x18003485f  add     rcx, 8; lpCriticalSection
0x180034863  mov     rbx, rdx
0x180034866  call    cs:__imp_EnterCriticalSection
0x18003486c  mov     rdx, rbx
0x18003486f  mov     rcx, rdi
0x180034872  call    ?CreateItem@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFActivate,CMFCSLock>::CreateItem(_GUID const &)
0x180034877  movzx   r9d, word ptr [rbp+0]
0x18003487c  sub     r9d, 5
0x180034880  jz      short loc_1800348B6
0x180034882  sub     r9d, 8
0x180034886  jz      short loc_1800348B6
0x180034888  sub     r9d, 6
0x18003488c  jz      short loc_1800348B6
0x18003488e  sub     r9d, 2
0x180034892  jz      short loc_1800348B6
0x180034894  sub     r9d, 0Ah
0x180034898  jz      short loc_1800348B6
0x18003489a  sub     r9d, 29h ; ')'
0x18003489e  jz      short loc_1800348B6
0x1800348a0  sub     r9d, 0FC9h
0x1800348a7  jz      short loc_1800348B6
0x1800348a9  cmp     r9d, 0Eh
0x1800348ad  jz      short loc_1800348B6
0x1800348af  mov     ebx, 0C00D36BDh
0x1800348b4  jmp     short loc_1800348D7
0x1800348b6  test    rax, rax
0x1800348b9  jnz     short loc_1800348C2
0x1800348bb  mov     ebx, 8007000Eh
0x1800348c0  jmp     short loc_1800348D7
0x1800348c2  mov     rdx, rbp; pvarSrc
0x1800348c5  mov     rcx, rax; pvarDest
0x1800348c8  call    cs:__imp_PropVariantCopy
0x1800348ce  mov     ebx, eax
0x1800348d0  mov     dword ptr [rdi+40h], 1
0x1800348d7  lea     rcx, [rdi+8]; lpCriticalSection
0x1800348db  call    cs:__imp_LeaveCriticalSection
0x1800348e1  mov     eax, ebx
0x1800348e3  add     rsp, 28h
0x1800348e7  pop     rdi
0x1800348e8  pop     rsi
0x1800348e9  pop     rbp
0x1800348ea  pop     rbx
0x1800348eb  retn
```
