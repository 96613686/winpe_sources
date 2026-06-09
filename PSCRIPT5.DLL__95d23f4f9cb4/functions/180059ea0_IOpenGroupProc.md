# IOpenGroupProc

- ea: `0x180059ea0`
- end: `0x180059ee3`
- name: `IOpenGroupProc`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180059ea0`
- `0x18005bbf8`
- `0x18005c404`

## string_xrefs

- `0x180059ea9`: `InstallableOptions`

## pseudocode

```c
__int64 __fastcall IOpenGroupProc(__int64 a1)
{
  if ( !strcmp_0(*(const char **)(a1 + 1016), "InstallableOptions") )
  {
    if ( *(_DWORD *)(a1 + 60) == 1 )
      return ISyntaxErrorMessage(*(_QWORD *)(a1 + 16));
    *(_DWORD *)(a1 + 60) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180059ea0  push    rbx
0x180059ea2  sub     rsp, 20h
0x180059ea6  mov     rbx, rcx
0x180059ea9  lea     rdx, aInstallableopt; "InstallableOptions"
0x180059eb0  mov     rcx, [rcx+3F8h]; Str1
0x180059eb7  call    strcmp_0
0x180059ebc  test    eax, eax
0x180059ebe  jnz     short loc_180059EDB
0x180059ec0  cmp     dword ptr [rbx+3Ch], 1
0x180059ec4  jnz     short loc_180059ED4
0x180059ec6  mov     rcx, [rbx+10h]
0x180059eca  add     rsp, 20h
0x180059ece  pop     rbx
0x180059ecf  jmp     ISyntaxErrorMessage
0x180059ed4  mov     dword ptr [rbx+3Ch], 1
0x180059edb  xor     eax, eax
0x180059edd  add     rsp, 20h
0x180059ee1  pop     rbx
0x180059ee2  retn
```
