# WixQuietExec

- ea: `0x10003352`
- end: `0x100033a5`
- name: `WixQuietExec`
- size: `83`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10003192`
- `0x10003352`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`

## string_xrefs

- `0x10003387`: `Failed in ExecCommon method`

## pseudocode

```c
int __stdcall WixQuietExec(MSIHANDLE hInstall)
{
  int v1; // esi
  int v2; // eax
  const char *v3; // ecx

  v1 = 0;
  v2 = sub_1000D51F(hInstall, (int)"WixQuietExec");
  if ( v2 < 0 )
  {
    v3 = "Failed to initialize";
LABEL_5:
    sub_1000DA66(v2, v3);
    v1 = 1603;
    return sub_1000D4AE(v1);
  }
  v2 = sub_10003192(L"WixQuietExecCmdLine", L"WixQuietExecCmdTimeout", 1, 1);
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
0x10003352  push    ebp
0x10003353  mov     ebp, esp
0x10003355  push    esi
0x10003356  push    offset aWixquietexec_0; "WixQuietExec"
0x1000335b  push    [ebp+hInstall]; hInstall
0x1000335e  xor     esi, esi
0x10003360  call    sub_1000D51F
0x10003365  test    eax, eax
0x10003367  jns     short loc_10003370
0x10003369  mov     ecx, offset aFailedToInitia_7; "Failed to initialize"
0x1000336e  jmp     short loc_1000338C
0x10003370  push    1; int
0x10003372  push    1; int
0x10003374  push    offset aWixquietexeccm; "WixQuietExecCmdTimeout"
0x10003379  push    offset aWixquietexeccm_0; "WixQuietExecCmdLine"
0x1000337e  call    sub_10003192
0x10003383  test    eax, eax
0x10003385  jns     short loc_1000339A
0x10003387  mov     ecx, offset aFailedInExecco_0; "Failed in ExecCommon method"
0x1000338c  push    ecx
0x1000338d  push    eax
0x1000338e  call    sub_1000DA66
0x10003393  pop     ecx
0x10003394  pop     ecx
0x10003395  mov     esi, 643h
0x1000339a  push    esi
0x1000339b  call    sub_1000D4AE
0x100033a0  pop     esi
0x100033a1  pop     ebp
0x100033a2  retn    4
```
