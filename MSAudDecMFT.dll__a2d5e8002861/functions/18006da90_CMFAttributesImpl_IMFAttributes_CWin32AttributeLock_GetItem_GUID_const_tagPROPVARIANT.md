# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetItem(_GUID const &,tagPROPVARIANT *)

- ea: `0x18006da90`
- end: `0x18006db00`
- name: `?GetItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800445e4`
- `0x18006da90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dae8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dae8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006daa6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006daa6`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006dacf`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006dacf`

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
0x18006da90  push    rbx
0x18006da92  push    rbp
0x18006da93  push    rsi
0x18006da94  push    rdi
0x18006da95  sub     rsp, 28h
0x18006da99  mov     rdi, rcx
0x18006da9c  mov     rsi, r8
0x18006da9f  add     rcx, 8; lpCriticalSection
0x18006daa3  mov     rbx, rdx
0x18006daa6  call    cs:__imp_EnterCriticalSection
0x18006daad  nop     dword ptr [rax+rax+00h]
0x18006dab2  mov     rdx, rbx
0x18006dab5  mov     rcx, rdi
0x18006dab8  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x18006dabd  test    rax, rax
0x18006dac0  jz      short loc_18006DADF
0x18006dac2  xor     ebx, ebx
0x18006dac4  test    rsi, rsi
0x18006dac7  jz      short loc_18006DAE4
0x18006dac9  mov     rdx, rax; pvarSrc
0x18006dacc  mov     rcx, rsi; pvarDest
0x18006dacf  call    cs:__imp_PropVariantCopy
0x18006dad6  nop     dword ptr [rax+rax+00h]
0x18006dadb  mov     ebx, eax
0x18006dadd  jmp     short loc_18006DAE4
0x18006dadf  mov     ebx, 0C00D36E6h
0x18006dae4  lea     rcx, [rdi+8]; lpCriticalSection
0x18006dae8  call    cs:__imp_LeaveCriticalSection
0x18006daef  nop     dword ptr [rax+rax+00h]
0x18006daf4  mov     eax, ebx
0x18006daf6  add     rsp, 28h
0x18006dafa  pop     rdi
0x18006dafb  pop     rsi
0x18006dafc  pop     rbp
0x18006dafd  pop     rbx
0x18006dafe  retn
```
