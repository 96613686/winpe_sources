# Comms::IsActiveDebugger(void)

- ea: `0x1800033f0`
- end: `0x180003419`
- name: `?IsActiveDebugger@Comms@@YAHXZ`
- size: `41`
- prototype: `_BOOL8 __fastcall(Comms *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800033f0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800033f4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800033f4`

## pseudocode

```c
_BOOL8 __fastcall Comms::IsActiveDebugger(Comms *this)
{
  return IsDebuggerPresent() || (MEMORY[0x7FFE02D4] & 3) == 3;
}

```

## disassembly

```asm
0x1800033f0  sub     rsp, 28h
0x1800033f4  call    cs:__imp_IsDebuggerPresent
0x1800033fa  test    eax, eax
0x1800033fc  jnz     short loc_18000340F
0x1800033fe  mov     al, ds:7FFE02D4h
0x180003405  and     al, 3
0x180003407  cmp     al, 3
0x180003409  jz      short loc_18000340F
0x18000340b  xor     eax, eax
0x18000340d  jmp     short loc_180003414
0x18000340f  mov     eax, 1
0x180003414  add     rsp, 28h
0x180003418  retn
```
