# WixSilentExec

- ea: `0x100033f6`
- end: `0x10003447`
- name: `WixSilentExec`
- size: `81`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10003192`
- `0x100033f6`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`

## string_xrefs

- `0x10003429`: `Failed in ExecCommon method`

## pseudocode

```c
int __stdcall WixSilentExec(MSIHANDLE hInstall)
{
  int v1; // esi
  int v2; // eax
  const char *v3; // ecx

  v1 = 0;
  v2 = sub_1000D51F(hInstall, (int)"WixSilentExec");
  if ( v2 < 0 )
  {
    v3 = "Failed to initialize";
LABEL_5:
    sub_1000DA66(v2, v3);
    v1 = 1603;
    return sub_1000D4AE(v1);
  }
  v2 = sub_10003192(L"WixSilentExecCmdLine", L"WixSilentExecCmdTimeout", 0, 0);
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
0x100033f6  push    ebp
0x100033f7  mov     ebp, esp
0x100033f9  push    esi
0x100033fa  push    offset aWixsilentexec_0; "WixSilentExec"
0x100033ff  push    [ebp+hInstall]; hInstall
0x10003402  xor     esi, esi
0x10003404  call    sub_1000D51F
0x10003409  test    eax, eax
0x1000340b  jns     short loc_10003414
0x1000340d  mov     ecx, offset aFailedToInitia_7; "Failed to initialize"
0x10003412  jmp     short loc_1000342E
0x10003414  push    esi; int
0x10003415  push    esi; int
0x10003416  push    offset aWixsilentexecc; "WixSilentExecCmdTimeout"
0x1000341b  push    offset aWixsilentexecc_0; "WixSilentExecCmdLine"
0x10003420  call    sub_10003192
0x10003425  test    eax, eax
0x10003427  jns     short loc_1000343C
0x10003429  mov     ecx, offset aFailedInExecco_0; "Failed in ExecCommon method"
0x1000342e  push    ecx
0x1000342f  push    eax
0x10003430  call    sub_1000DA66
0x10003435  pop     ecx
0x10003436  pop     ecx
0x10003437  mov     esi, 643h
0x1000343c  push    esi
0x1000343d  call    sub_1000D4AE
0x10003442  pop     esi
0x10003443  pop     ebp
0x10003444  retn    4
```
