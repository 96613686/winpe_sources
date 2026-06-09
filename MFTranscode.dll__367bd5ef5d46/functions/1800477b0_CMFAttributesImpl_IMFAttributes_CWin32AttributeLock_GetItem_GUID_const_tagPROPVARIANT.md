# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetItem(_GUID const &,tagPROPVARIANT *)

- ea: `0x1800477b0`
- end: `0x18004780d`
- name: `?GetItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800076c0`
- `0x1800477b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800477fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800477fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800477c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800477c6`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800477e9`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800477e9`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetItem(
        __int64 a1,
        __int64 a2,
        PROPVARIANT *a3)
{
  const PROPVARIANT *Item; // rax
  unsigned int v7; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = (const PROPVARIANT *)CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(a1, a2);
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
0x1800477b0  push    rbx
0x1800477b2  push    rbp
0x1800477b3  push    rsi
0x1800477b4  push    rdi
0x1800477b5  sub     rsp, 28h
0x1800477b9  mov     rdi, rcx
0x1800477bc  mov     rsi, r8
0x1800477bf  add     rcx, 8; lpCriticalSection
0x1800477c3  mov     rbx, rdx
0x1800477c6  call    cs:__imp_EnterCriticalSection
0x1800477cc  mov     rdx, rbx
0x1800477cf  mov     rcx, rdi
0x1800477d2  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x1800477d7  test    rax, rax
0x1800477da  jz      short loc_1800477F3
0x1800477dc  xor     ebx, ebx
0x1800477de  test    rsi, rsi
0x1800477e1  jz      short loc_1800477F8
0x1800477e3  mov     rdx, rax; pvarSrc
0x1800477e6  mov     rcx, rsi; pvarDest
0x1800477e9  call    cs:__imp_PropVariantCopy
0x1800477ef  mov     ebx, eax
0x1800477f1  jmp     short loc_1800477F8
0x1800477f3  mov     ebx, 0C00D36E6h
0x1800477f8  lea     rcx, [rdi+8]; lpCriticalSection
0x1800477fc  call    cs:__imp_LeaveCriticalSection
0x180047802  mov     eax, ebx
0x180047804  add     rsp, 28h
0x180047808  pop     rdi
0x180047809  pop     rsi
0x18004780a  pop     rbp
0x18004780b  pop     rbx
0x18004780c  retn
```
