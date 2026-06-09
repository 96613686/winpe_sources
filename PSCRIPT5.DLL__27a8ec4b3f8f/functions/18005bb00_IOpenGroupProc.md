# IOpenGroupProc

- ea: `0x18005bb00`
- end: `0x18005bb44`
- name: `IOpenGroupProc`
- size: `68`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18005bb00`
- `0x18005d864`
- `0x18005e094`

## string_xrefs

- `0x18005bb09`: `InstallableOptions`

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
0x18005bb00  push    rbx
0x18005bb02  sub     rsp, 20h
0x18005bb06  mov     rbx, rcx
0x18005bb09  lea     rdx, aInstallableopt; "InstallableOptions"
0x18005bb10  mov     rcx, [rcx+3F8h]; Str1
0x18005bb17  call    strcmp_0
0x18005bb1c  test    eax, eax
0x18005bb1e  jnz     short loc_18005BB3B
0x18005bb20  cmp     dword ptr [rbx+3Ch], 1
0x18005bb24  jnz     short loc_18005BB34
0x18005bb26  mov     rcx, [rbx+10h]
0x18005bb2a  add     rsp, 20h
0x18005bb2e  pop     rbx
0x18005bb2f  jmp     ISyntaxErrorMessage
0x18005bb34  mov     dword ptr [rbx+3Ch], 1
0x18005bb3b  xor     eax, eax
0x18005bb3d  add     rsp, 20h
0x18005bb41  pop     rbx
0x18005bb42  retn
```
