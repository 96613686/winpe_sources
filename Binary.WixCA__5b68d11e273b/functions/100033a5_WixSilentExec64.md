# WixSilentExec64

- ea: `0x100033a5`
- end: `0x100033f6`
- name: `WixSilentExec64`
- size: `81`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x100030e4`
- `0x100033a5`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`

## string_xrefs

- `0x100033d8`: `Failed in ExecCommon method`

## pseudocode

```c
int __stdcall WixSilentExec64(MSIHANDLE hInstall)
{
  int v1; // esi
  int v2; // eax
  const char *v3; // ecx

  v1 = 0;
  v2 = sub_1000D51F(hInstall, (int)"WixSilentExec64");
  if ( v2 < 0 )
  {
    v3 = "Failed to initialize";
LABEL_5:
    sub_1000DA66(v2, v3);
    v1 = 1603;
    return sub_1000D4AE(v1);
  }
  v2 = sub_100030E4(L"WixSilentExec64CmdLine", L"WixSilentExec64CmdTimeout", 0, 0);
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
0x100033a5  push    ebp
0x100033a6  mov     ebp, esp
0x100033a8  push    esi
0x100033a9  push    offset aWixsilentexec6_0; "WixSilentExec64"
0x100033ae  push    [ebp+hInstall]; hInstall
0x100033b1  xor     esi, esi
0x100033b3  call    sub_1000D51F
0x100033b8  test    eax, eax
0x100033ba  jns     short loc_100033C3
0x100033bc  mov     ecx, offset aFailedToInitia_7; "Failed to initialize"
0x100033c1  jmp     short loc_100033DD
0x100033c3  push    esi; int
0x100033c4  push    esi; int
0x100033c5  push    offset aWixsilentexec6_1; "WixSilentExec64CmdTimeout"
0x100033ca  push    offset aWixsilentexec6_2; "WixSilentExec64CmdLine"
0x100033cf  call    sub_100030E4
0x100033d4  test    eax, eax
0x100033d6  jns     short loc_100033EB
0x100033d8  mov     ecx, offset aFailedInExecco_0; "Failed in ExecCommon method"
0x100033dd  push    ecx
0x100033de  push    eax
0x100033df  call    sub_1000DA66
0x100033e4  pop     ecx
0x100033e5  pop     ecx
0x100033e6  mov     esi, 643h
0x100033eb  push    esi
0x100033ec  call    sub_1000D4AE
0x100033f1  pop     esi
0x100033f2  pop     ebp
0x100033f3  retn    4
```
