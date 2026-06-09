# DeinitializeHostRouteInfo

- ea: `0x180008594`
- end: `0x1800085f6`
- name: `DeinitializeHostRouteInfo`
- size: `98`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005560`

## callees

- `0x180008594`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800085c5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800085c5`

## pseudocode

```c
void DeinitializeHostRouteInfo()
{
  if ( *((_QWORD *)&xmmword_18002DBA0 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gHostRoutTemplateFunc)(
      gHostRoutEtwContext,
      *((_QWORD *)&xmmword_18002DBA0 + 1),
      L"Entering DeinitializeHostRouteInfo");
  DeleteCriticalSection(&RouteEntryCs);
  if ( *((_QWORD *)&xmmword_18002DBA0 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gHostRoutTemplateFunc)(
      gHostRoutEtwContext,
      *((_QWORD *)&xmmword_18002DBA0 + 1),
      L"Leaving DeinitializeHostRouteInfo");
}

```

## disassembly

```asm
0x180008594  sub     rsp, 28h
0x180008598  mov     rdx, qword ptr cs:xmmword_18002DBA0+8
0x18000859f  test    rdx, rdx
0x1800085a2  jz      short loc_1800085BE
0x1800085a4  mov     rcx, cs:gHostRoutEtwContext
0x1800085ab  lea     r8, aEnteringDeinit; "Entering DeinitializeHostRouteInfo"
0x1800085b2  mov     rax, cs:gHostRoutTemplateFunc
0x1800085b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085be  lea     rcx, RouteEntryCs; lpCriticalSection
0x1800085c5  call    cs:__imp_DeleteCriticalSection
0x1800085cb  mov     rdx, qword ptr cs:xmmword_18002DBA0+8
0x1800085d2  test    rdx, rdx
0x1800085d5  jz      short loc_1800085F1
0x1800085d7  mov     rcx, cs:gHostRoutEtwContext
0x1800085de  lea     r8, aLeavingDeiniti; "Leaving DeinitializeHostRouteInfo"
0x1800085e5  mov     rax, cs:gHostRoutTemplateFunc
0x1800085ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085f1  add     rsp, 28h
0x1800085f5  retn
```
