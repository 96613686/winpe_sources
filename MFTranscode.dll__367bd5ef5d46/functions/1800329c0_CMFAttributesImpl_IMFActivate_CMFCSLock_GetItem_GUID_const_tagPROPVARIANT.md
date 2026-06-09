# CMFAttributesImpl<IMFActivate,CMFCSLock>::GetItem(_GUID const &,tagPROPVARIANT *)

- ea: `0x1800329c0`
- end: `0x180032a1d`
- name: `?GetItem@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800088d0`
- `0x1800329c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032a0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032a0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800329d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800329d6`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800329f9`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800329f9`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFActivate,CMFCSLock>::GetItem(__int64 a1, __int64 a2, PROPVARIANT *a3)
{
  const PROPVARIANT *Item; // rax
  unsigned int v7; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = (const PROPVARIANT *)CMFAttributesImpl<IMFActivate,CMFCSLock>::_FindItem(a1, a2);
  if ( Item )
  {
    v7 = 0;
    if ( a3 )
      v7 = PropVariantCopy(a3, Item);
  }
  else
  {
    v7 = -1072875802;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v7;
}

```

## disassembly

```asm
0x1800329c0  push    rbx
0x1800329c2  push    rbp
0x1800329c3  push    rsi
0x1800329c4  push    rdi
0x1800329c5  sub     rsp, 28h
0x1800329c9  mov     rdi, rcx
0x1800329cc  mov     rsi, r8
0x1800329cf  add     rcx, 8; lpCriticalSection
0x1800329d3  mov     rbx, rdx
0x1800329d6  call    cs:__imp_EnterCriticalSection
0x1800329dc  mov     rdx, rbx
0x1800329df  mov     rcx, rdi
0x1800329e2  call    ?_FindItem@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFActivate,CMFCSLock>::_FindItem(_GUID const &)
0x1800329e7  test    rax, rax
0x1800329ea  jz      short loc_180032A03
0x1800329ec  xor     ebx, ebx
0x1800329ee  test    rsi, rsi
0x1800329f1  jz      short loc_180032A08
0x1800329f3  mov     rdx, rax; pvarSrc
0x1800329f6  mov     rcx, rsi; pvarDest
0x1800329f9  call    cs:__imp_PropVariantCopy
0x1800329ff  mov     ebx, eax
0x180032a01  jmp     short loc_180032A08
0x180032a03  mov     ebx, 0C00D36E6h
0x180032a08  lea     rcx, [rdi+8]; lpCriticalSection
0x180032a0c  call    cs:__imp_LeaveCriticalSection
0x180032a12  mov     eax, ebx
0x180032a14  add     rsp, 28h
0x180032a18  pop     rdi
0x180032a19  pop     rsi
0x180032a1a  pop     rbp
0x180032a1b  pop     rbx
0x180032a1c  retn
```
