# WixQuietExec64

- ea: `0x100032ff`
- end: `0x10003352`
- name: `WixQuietExec64`
- size: `83`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x100030e4`
- `0x100032ff`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`

## string_xrefs

- `0x10003334`: `Failed in ExecCommon method`

## pseudocode

```c
int __stdcall WixQuietExec64(MSIHANDLE hInstall)
{
  int v1; // esi
  int v2; // eax
  const char *v3; // ecx

  v1 = 0;
  v2 = sub_1000D51F(hInstall, (int)"WixQuietExec64");
  if ( v2 < 0 )
  {
    v3 = "Failed to initialize";
LABEL_5:
    sub_1000DA66(v2, v3);
    v1 = 1603;
    return sub_1000D4AE(v1);
  }
  v2 = sub_100030E4(L"WixQuietExec64CmdLine", L"WixQuietExec64CmdTimeout", 1, 1);
  if ( v2 < 0 )
  {
    v3 = "Failed in ExecCommon method";
    goto LABEL_5;
  }
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x100032ff  push    ebp
0x10003300  mov     ebp, esp
0x10003302  push    esi
0x10003303  push    offset aWixquietexec64_0; "WixQuietExec64"
0x10003308  push    [ebp+hInstall]; hInstall
0x1000330b  xor     esi, esi
0x1000330d  call    sub_1000D51F
0x10003312  test    eax, eax
0x10003314  jns     short loc_1000331D
0x10003316  mov     ecx, offset aFailedToInitia_7; "Failed to initialize"
0x1000331b  jmp     short loc_10003339
0x1000331d  push    1; int
0x1000331f  push    1; int
0x10003321  push    offset aWixquietexec64_1; "WixQuietExec64CmdTimeout"
0x10003326  push    offset aWixquietexec64_2; "WixQuietExec64CmdLine"
0x1000332b  call    sub_100030E4
0x10003330  test    eax, eax
0x10003332  jns     short loc_10003347
0x10003334  mov     ecx, offset aFailedInExecco_0; "Failed in ExecCommon method"
0x10003339  push    ecx
0x1000333a  push    eax
0x1000333b  call    sub_1000DA66
0x10003340  pop     ecx
0x10003341  pop     ecx
0x10003342  mov     esi, 643h
0x10003347  push    esi
0x10003348  call    sub_1000D4AE
0x1000334d  pop     esi
0x1000334e  pop     ebp
0x1000334f  retn    4
```
