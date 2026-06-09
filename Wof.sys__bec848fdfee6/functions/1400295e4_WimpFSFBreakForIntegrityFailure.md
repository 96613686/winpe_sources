# WimpFSFBreakForIntegrityFailure

- ea: `0x1400295e4`
- end: `0x140029624`
- name: `WimpFSFBreakForIntegrityFailure`
- size: `64`
- prototype: `void()`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140029ca0`
- `0x140029f78`
- `0x14002ac38`

## callees

- `0x1400295e4`

## import_xrefs

- `ntoskrnl!RtlCheckRegistryKey` at `0x14002960d`
- `ntoskrnl!RtlCheckRegistryKey` at `0x14002960d`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400295f1`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400295f1`

## pseudocode

```c
void WimpFSFBreakForIntegrityFailure()
{
  if ( !g_WimIntegrityDoNotBreakIntoKd
    && !KdRefreshDebuggerNotPresent()
    && RtlCheckRegistryKey(2u, (PWSTR)L"CI\\WIMIntegrity\\DisableKdBreak") < 0 )
  {
    __debugbreak();
  }
}

```

## disassembly

```asm
0x1400295e4  sub     rsp, 28h
0x1400295e8  cmp     cs:g_WimIntegrityDoNotBreakIntoKd, 0
0x1400295ef  jnz     short loc_14002961E
0x1400295f1  call    cs:__imp_KdRefreshDebuggerNotPresent
0x1400295f8  nop     dword ptr [rax+rax+00h]
0x1400295fd  test    al, al
0x1400295ff  jnz     short loc_14002961E
0x140029601  lea     rdx, Path; "CI\\WIMIntegrity\\DisableKdBreak"
0x140029608  mov     ecx, 2; RelativeTo
0x14002960d  call    cs:__imp_RtlCheckRegistryKey
0x140029614  nop     dword ptr [rax+rax+00h]
0x140029619  test    eax, eax
0x14002961b  jns     short loc_14002961E
0x14002961d  int     3; Trap to Debugger
0x14002961e  add     rsp, 28h
0x140029622  retn
```
