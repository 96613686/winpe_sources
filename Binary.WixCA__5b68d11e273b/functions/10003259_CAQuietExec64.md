# CAQuietExec64

- ea: `0x10003259`
- end: `0x100032ac`
- name: `CAQuietExec64`
- size: `83`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x100030e4`
- `0x10003259`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`

## string_xrefs

- `0x1000328e`: `Failed in ExecCommon64 method`

## pseudocode

```c
int __stdcall CAQuietExec64(MSIHANDLE hInstall)
{
  int v1; // esi
  int v2; // eax
  const char *v3; // ecx

  v1 = 0;
  v2 = sub_1000D51F(hInstall, (int)"CAQuietExec64");
  if ( v2 < 0 )
  {
    v3 = "Failed to initialize";
LABEL_5:
    sub_1000DA66(v2, v3);
    v1 = 1603;
    return sub_1000D4AE(v1);
  }
  v2 = sub_100030E4(L"QtExec64CmdLine", L"QtExecCmdTimeout", 1, 1);
  if ( v2 < 0 )
  {
    v3 = "Failed in ExecCommon64 method";
    goto LABEL_5;
  }
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x10003259  push    ebp
0x1000325a  mov     ebp, esp
0x1000325c  push    esi
0x1000325d  push    offset aCaquietexec64_0; "CAQuietExec64"
0x10003262  push    [ebp+hInstall]; hInstall
0x10003265  xor     esi, esi
0x10003267  call    sub_1000D51F
0x1000326c  test    eax, eax
0x1000326e  jns     short loc_10003277
0x10003270  mov     ecx, offset aFailedToInitia_7; "Failed to initialize"
0x10003275  jmp     short loc_10003293
0x10003277  push    1; int
0x10003279  push    1; int
0x1000327b  push    offset aQtexeccmdtimeo; "QtExecCmdTimeout"
0x10003280  push    offset aQtexec64cmdlin; "QtExec64CmdLine"
0x10003285  call    sub_100030E4
0x1000328a  test    eax, eax
0x1000328c  jns     short loc_100032A1
0x1000328e  mov     ecx, offset aFailedInExecco; "Failed in ExecCommon64 method"
0x10003293  push    ecx
0x10003294  push    eax
0x10003295  call    sub_1000DA66
0x1000329a  pop     ecx
0x1000329b  pop     ecx
0x1000329c  mov     esi, 643h
0x100032a1  push    esi
0x100032a2  call    sub_1000D4AE
0x100032a7  pop     esi
0x100032a8  pop     ebp
0x100032a9  retn    4
```
