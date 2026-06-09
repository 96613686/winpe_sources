# SetScenarioResultParameter

- ea: `0x180005b78`
- end: `0x180005bcd`
- name: `SetScenarioResultParameter`
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
- `0x180005b78`

## import_xrefs

- `wdi!WdiAddParameter` at `0x180005b9a`
- `wdi!WdiAddParameter` at `0x180005b9a`

## string_xrefs

- `0x180005bb9`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`

## pseudocode

```c
__int64 __fastcall SetScenarioResultParameter(__int64 a1, int a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+48h] [rbp+10h] BYREF

  v5 = a2;
  v2 = WdiAddParameter(a1, 0, L"ScenarioResult", 4, &v5);
  v3 = v2;
  if ( v2 < 0 )
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "SetScenarioResultParameter", 36, v2);
  return v3;
}

```

## disassembly

```asm
0x180005b78  mov     [rsp+arg_8], edx
0x180005b7c  push    rbx
0x180005b7d  sub     rsp, 30h
0x180005b81  lea     rax, [rsp+38h+arg_8]
0x180005b86  mov     r9d, 4
0x180005b8c  lea     r8, aScenarioresult; "ScenarioResult"
0x180005b93  mov     [rsp+38h+var_18], rax
0x180005b98  xor     edx, edx
0x180005b9a  call    cs:__imp_WdiAddParameter
0x180005ba0  mov     ebx, eax
0x180005ba2  test    eax, eax
0x180005ba4  jns     short loc_180005BC5
0x180005ba6  mov     r9d, 24h ; '$'
0x180005bac  mov     dword ptr [rsp+38h+var_18], eax
0x180005bb0  lea     r8, aSetscenariores; "SetScenarioResultParameter"
0x180005bb7  xor     ecx, ecx; Level
0x180005bb9  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x180005bc0  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180005bc5  mov     eax, ebx
0x180005bc7  add     rsp, 30h
0x180005bcb  pop     rbx
0x180005bcc  retn
```
