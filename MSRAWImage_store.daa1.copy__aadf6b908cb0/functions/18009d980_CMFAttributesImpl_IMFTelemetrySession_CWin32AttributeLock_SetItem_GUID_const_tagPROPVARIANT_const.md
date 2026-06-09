# CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::SetItem(_GUID const &,tagPROPVARIANT const &)

- ea: `0x18009d980`
- end: `0x18009da46`
- name: `?SetItem@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@AEBUtagPROPVARIANT@@@Z`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180098fe4`
- `0x18009d980`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18009da09`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18009da09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009da22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009da22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009d9a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009d9a1`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::SetItem(
        __int64 a1,
        __int64 a2,
        const PROPVARIANT *a3)
{
  PROPVARIANT *Item; // rax
  unsigned int v7; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = (PROPVARIANT *)CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::CreateItem(a1, a2);
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
0x18009d980  mov     [rsp+arg_0], rbx
0x18009d985  mov     [rsp+arg_8], rbp
0x18009d98a  mov     [rsp+arg_10], rsi
0x18009d98f  push    rdi
0x18009d990  sub     rsp, 20h
0x18009d994  mov     rdi, rcx
0x18009d997  mov     rbp, r8
0x18009d99a  add     rcx, 8; lpCriticalSection
0x18009d99e  mov     rbx, rdx
0x18009d9a1  call    cs:__imp_EnterCriticalSection
0x18009d9a8  nop     dword ptr [rax+rax+00h]
0x18009d9ad  mov     rdx, rbx
0x18009d9b0  mov     rcx, rdi
0x18009d9b3  call    ?CreateItem@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::CreateItem(_GUID const &)
0x18009d9b8  movzx   r9d, word ptr [rbp+0]
0x18009d9bd  sub     r9d, 5
0x18009d9c1  jz      short loc_18009D9F7
0x18009d9c3  sub     r9d, 8
0x18009d9c7  jz      short loc_18009D9F7
0x18009d9c9  sub     r9d, 6
0x18009d9cd  jz      short loc_18009D9F7
0x18009d9cf  sub     r9d, 2
0x18009d9d3  jz      short loc_18009D9F7
0x18009d9d5  sub     r9d, 0Ah
0x18009d9d9  jz      short loc_18009D9F7
0x18009d9db  sub     r9d, 29h ; ')'
0x18009d9df  jz      short loc_18009D9F7
0x18009d9e1  sub     r9d, 0FC9h
0x18009d9e8  jz      short loc_18009D9F7
0x18009d9ea  cmp     r9d, 0Eh
0x18009d9ee  jz      short loc_18009D9F7
0x18009d9f0  mov     ebx, 0C00D36BDh
0x18009d9f5  jmp     short loc_18009DA1E
0x18009d9f7  test    rax, rax
0x18009d9fa  jnz     short loc_18009DA03
0x18009d9fc  mov     ebx, 8007000Eh
0x18009da01  jmp     short loc_18009DA1E
0x18009da03  mov     rdx, rbp; pvarSrc
0x18009da06  mov     rcx, rax; pvarDest
0x18009da09  call    cs:__imp_PropVariantCopy
0x18009da10  nop     dword ptr [rax+rax+00h]
0x18009da15  mov     ebx, eax
0x18009da17  mov     dword ptr [rdi+40h], 1
0x18009da1e  lea     rcx, [rdi+8]; lpCriticalSection
0x18009da22  call    cs:__imp_LeaveCriticalSection
0x18009da29  nop     dword ptr [rax+rax+00h]
0x18009da2e  mov     rbp, [rsp+28h+arg_8]
0x18009da33  mov     eax, ebx
0x18009da35  mov     rbx, [rsp+28h+arg_0]
0x18009da3a  mov     rsi, [rsp+28h+arg_10]
0x18009da3f  add     rsp, 20h
0x18009da43  pop     rdi
0x18009da44  retn
```
