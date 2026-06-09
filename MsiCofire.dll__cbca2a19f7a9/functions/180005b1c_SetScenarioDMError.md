# SetScenarioDMError

- ea: `0x180005b1c`
- end: `0x180005b71`
- name: `SetScenarioDMError`
- size: `85`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180002770`
- `0x1800038cc`
- `0x180003ac8`

## callees

- `0x180002590`
- `0x180005b1c`

## import_xrefs

- `wdi!WdiAddParameter` at `0x180005b3e`
- `wdi!WdiAddParameter` at `0x180005b3e`

## string_xrefs

- `0x180005b5d`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`

## pseudocode

```c
__int64 __fastcall SetScenarioDMError(__int64 a1, int a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+48h] [rbp+10h] BYREF

  v5 = a2;
  v2 = WdiAddParameter(a1, 0, L"DMError", 4, &v5);
  v3 = v2;
  if ( v2 < 0 )
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "SetScenarioDMError", 82, v2);
  return v3;
}

```

## disassembly

```asm
0x180005b1c  mov     [rsp+arg_8], edx
0x180005b20  push    rbx
0x180005b21  sub     rsp, 30h
0x180005b25  lea     rax, [rsp+38h+arg_8]
0x180005b2a  mov     r9d, 4
0x180005b30  lea     r8, aDmerror; "DMError"
0x180005b37  mov     [rsp+38h+var_18], rax
0x180005b3c  xor     edx, edx
0x180005b3e  call    cs:__imp_WdiAddParameter
0x180005b44  mov     ebx, eax
0x180005b46  test    eax, eax
0x180005b48  jns     short loc_180005B69
0x180005b4a  mov     r9d, 52h ; 'R'
0x180005b50  mov     dword ptr [rsp+38h+var_18], eax
0x180005b54  lea     r8, aSetscenariodme; "SetScenarioDMError"
0x180005b5b  xor     ecx, ecx; Level
0x180005b5d  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x180005b64  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180005b69  mov     eax, ebx
0x180005b6b  add     rsp, 30h
0x180005b6f  pop     rbx
0x180005b70  retn
```
