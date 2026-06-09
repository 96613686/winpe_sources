# ICloseGroupProc

- ea: `0x18005a730`
- end: `0x18005a773`
- name: `ICloseGroupProc`
- size: `67`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18005a730`
- `0x18005d864`
- `0x18005e094`

## string_xrefs

- `0x18005a739`: `InstallableOptions`

## pseudocode

```c
__int64 __fastcall ICloseGroupProc(__int64 a1)
{
  if ( !strcmp_0(*(const char **)(a1 + 1016), "InstallableOptions") )
  {
    if ( !*(_DWORD *)(a1 + 60) )
      return ISyntaxErrorMessage(*(_QWORD *)(a1 + 16));
    *(_DWORD *)(a1 + 60) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18005a730  push    rbx
0x18005a732  sub     rsp, 20h
0x18005a736  mov     rbx, rcx
0x18005a739  lea     rdx, aInstallableopt; "InstallableOptions"
0x18005a740  mov     rcx, [rcx+3F8h]; Str1
0x18005a747  call    strcmp_0
0x18005a74c  test    eax, eax
0x18005a74e  jnz     short loc_18005A76A
0x18005a750  cmp     [rbx+3Ch], eax
0x18005a753  jnz     short loc_18005A763
0x18005a755  mov     rcx, [rbx+10h]
0x18005a759  add     rsp, 20h
0x18005a75d  pop     rbx
0x18005a75e  jmp     ISyntaxErrorMessage
0x18005a763  mov     dword ptr [rbx+3Ch], 0
0x18005a76a  xor     eax, eax
0x18005a76c  add     rsp, 20h
0x18005a770  pop     rbx
0x18005a771  retn
```
