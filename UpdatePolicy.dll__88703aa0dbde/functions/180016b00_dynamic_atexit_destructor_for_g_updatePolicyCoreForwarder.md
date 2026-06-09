# _dynamic_atexit_destructor_for__g_updatePolicyCoreForwarder__

- ea: `0x180016b00`
- end: `0x180016b4f`
- name: `_dynamic_atexit_destructor_for__g_updatePolicyCoreForwarder__`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180015430`
- `0x180016b00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016b10`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016b10`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016b1d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016b1d`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_updatePolicyCoreForwarder__()
{
  void (__fastcall ***v0)(_QWORD, __int64); // rcx

  if ( hLibModule )
    FreeLibrary(hLibModule);
  DeleteCriticalSection(&CriticalSection);
  v0 = (void (__fastcall ***)(_QWORD, __int64))qword_180020490;
  qword_180020490 = 0;
  if ( v0 )
    (**v0)(v0, 1);
}

```

## disassembly

```asm
0x180016b00  sub     rsp, 28h
0x180016b04  mov     rcx, cs:hLibModule; hLibModule
0x180016b0b  test    rcx, rcx
0x180016b0e  jz      short loc_180016B16
0x180016b10  call    cs:__imp_FreeLibrary
0x180016b16  lea     rcx, CriticalSection; lpCriticalSection
0x180016b1d  call    cs:__imp_DeleteCriticalSection
0x180016b23  mov     rcx, cs:qword_180020490
0x180016b2a  mov     cs:qword_180020490, 0
0x180016b35  test    rcx, rcx
0x180016b38  jz      short loc_180016B4A
0x180016b3a  mov     rax, [rcx]
0x180016b3d  mov     edx, 1
0x180016b42  mov     rax, [rax]
0x180016b45  call    _guard_dispatch_icall
0x180016b4a  add     rsp, 28h
0x180016b4e  retn
```
