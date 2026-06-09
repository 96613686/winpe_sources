# ICloseGroupProc

- ea: `0x180058b10`
- end: `0x180058b52`
- name: `ICloseGroupProc`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180058b10`
- `0x18005bbf8`
- `0x18005c404`

## string_xrefs

- `0x180058b19`: `InstallableOptions`

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
0x180058b10  push    rbx
0x180058b12  sub     rsp, 20h
0x180058b16  mov     rbx, rcx
0x180058b19  lea     rdx, aInstallableopt; "InstallableOptions"
0x180058b20  mov     rcx, [rcx+3F8h]; Str1
0x180058b27  call    strcmp_0
0x180058b2c  test    eax, eax
0x180058b2e  jnz     short loc_180058B4A
0x180058b30  cmp     [rbx+3Ch], eax
0x180058b33  jnz     short loc_180058B43
0x180058b35  mov     rcx, [rbx+10h]
0x180058b39  add     rsp, 20h
0x180058b3d  pop     rbx
0x180058b3e  jmp     ISyntaxErrorMessage
0x180058b43  mov     dword ptr [rbx+3Ch], 0
0x180058b4a  xor     eax, eax
0x180058b4c  add     rsp, 20h
0x180058b50  pop     rbx
0x180058b51  retn
```
