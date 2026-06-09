# CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::GetItem(_GUID const &,tagPROPVARIANT *)

- ea: `0x18009ae50`
- end: `0x18009aee2`
- name: `?GetItem@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18009ae50`
- `0x18009e6d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18009ae9f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18009ae9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009aeb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009aeb8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ae78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ae78`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::GetItem(
        __int64 a1,
        __int64 a2,
        PROPVARIANT *a3)
{
  unsigned int v6; // esi
  const PROPVARIANT *Item; // rax

  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = (const PROPVARIANT *)CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_FindItem(a1, a2);
  if ( Item )
  {
    if ( a3 )
      v6 = PropVariantCopy(a3, Item);
  }
  else
  {
    v6 = -1072875802;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v6;
}

```

## disassembly

```asm
0x18009ae50  mov     rax, rsp
0x18009ae53  mov     [rax+8], rbx
0x18009ae57  mov     [rax+10h], rbp
0x18009ae5b  mov     [rax+18h], rsi
0x18009ae5f  mov     [rax+20h], rdi
0x18009ae63  push    r14
0x18009ae65  sub     rsp, 20h
0x18009ae69  mov     rdi, rcx
0x18009ae6c  mov     rbp, r8
0x18009ae6f  add     rcx, 8; lpCriticalSection
0x18009ae73  mov     rbx, rdx
0x18009ae76  xor     esi, esi
0x18009ae78  call    cs:__imp_EnterCriticalSection
0x18009ae7f  nop     dword ptr [rax+rax+00h]
0x18009ae84  mov     rdx, rbx
0x18009ae87  mov     rcx, rdi
0x18009ae8a  call    ?_FindItem@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_FindItem(_GUID const &)
0x18009ae8f  test    rax, rax
0x18009ae92  jz      short loc_18009AEAF
0x18009ae94  test    rbp, rbp
0x18009ae97  jz      short loc_18009AEB4
0x18009ae99  mov     rdx, rax; pvarSrc
0x18009ae9c  mov     rcx, rbp; pvarDest
0x18009ae9f  call    cs:__imp_PropVariantCopy
0x18009aea6  nop     dword ptr [rax+rax+00h]
0x18009aeab  mov     esi, eax
0x18009aead  jmp     short loc_18009AEB4
0x18009aeaf  mov     esi, 0C00D36E6h
0x18009aeb4  lea     rcx, [rdi+8]; lpCriticalSection
0x18009aeb8  call    cs:__imp_LeaveCriticalSection
0x18009aebf  nop     dword ptr [rax+rax+00h]
0x18009aec4  mov     rbx, [rsp+28h+arg_0]
0x18009aec9  mov     eax, esi
0x18009aecb  mov     rsi, [rsp+28h+arg_10]
0x18009aed0  mov     rbp, [rsp+28h+arg_8]
0x18009aed5  mov     rdi, [rsp+28h+arg_18]
0x18009aeda  add     rsp, 20h
0x18009aede  pop     r14
0x18009aee0  retn
```
