# _dynamic_initializer_for__g_writeDumpEventSem__

- ea: `0x180001040`
- end: `0x180001082`
- name: `_dynamic_initializer_for__g_writeDumpEventSem__`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001040`
- `0x180001fe0`
- `0x18000e6fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180001050`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180001050`

## string_xrefs

- `0x180001066`: `CreateEvent returned a NULL handle.`

## pseudocode

```c
int dynamic_initializer_for__g_writeDumpEventSem__()
{
  unsigned __int16 *v0; // rdx

  g_writeDumpEventSem = CreateEventA(0, 1, 0, 0);
  if ( !g_writeDumpEventSem )
    UtsemWin32Error(L"CreateEvent returned a NULL handle.", v0, 0x64u);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_writeDumpEventSem__);
}

```

## disassembly

```asm
0x180001040  sub     rsp, 28h
0x180001044  xor     r9d, r9d; lpName
0x180001047  xor     r8d, r8d; bInitialState
0x18000104a  xor     ecx, ecx; lpEventAttributes
0x18000104c  lea     edx, [r9+1]; bManualReset
0x180001050  call    cs:__imp_CreateEventA
0x180001056  mov     cs:?g_writeDumpEventSem@@3VCEventSem@@A, rax; CEventSem g_writeDumpEventSem
0x18000105d  test    rax, rax
0x180001060  jnz     short loc_180001072
0x180001062  lea     r8d, [rax+64h]; unsigned int
0x180001066  lea     rcx, aCreateeventRet; "CreateEvent returned a NULL handle."
0x18000106d  call    ?UtsemWin32Error@@YAXPEAG0K@Z; UtsemWin32Error(ushort *,ushort *,ulong)
0x180001072  lea     rcx, _dynamic_atexit_destructor_for__g_writeDumpEventSem__
0x180001079  add     rsp, 28h
0x18000107d  jmp     atexit
```
