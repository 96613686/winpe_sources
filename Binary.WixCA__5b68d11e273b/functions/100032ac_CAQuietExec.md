# CAQuietExec

- ea: `0x100032ac`
- end: `0x100032ff`
- name: `CAQuietExec`
- size: `83`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10003192`
- `0x100032ac`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`

## string_xrefs

- `0x100032e1`: `Failed in ExecCommon method`

## pseudocode

```c
int __stdcall CAQuietExec(MSIHANDLE hInstall)
{
  int v1; // esi
  int v2; // eax
  const char *v3; // ecx

  v1 = 0;
  v2 = sub_1000D51F(hInstall, (int)"CAQuietExec");
  if ( v2 < 0 )
  {
    v3 = "Failed to initialize";
LABEL_5:
    sub_1000DA66(v2, v3);
    v1 = 1603;
    return sub_1000D4AE(v1);
  }
  v2 = sub_10003192(L"QtExecCmdLine", L"QtExecCmdTimeout", 1, 1);
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
0x100032ac  push    ebp
0x100032ad  mov     ebp, esp
0x100032af  push    esi
0x100032b0  push    offset aCaquietexec_0; "CAQuietExec"
0x100032b5  push    [ebp+hInstall]; hInstall
0x100032b8  xor     esi, esi
0x100032ba  call    sub_1000D51F
0x100032bf  test    eax, eax
0x100032c1  jns     short loc_100032CA
0x100032c3  mov     ecx, offset aFailedToInitia_7; "Failed to initialize"
0x100032c8  jmp     short loc_100032E6
0x100032ca  push    1; int
0x100032cc  push    1; int
0x100032ce  push    offset aQtexeccmdtimeo; "QtExecCmdTimeout"
0x100032d3  push    offset aQtexeccmdline; "QtExecCmdLine"
0x100032d8  call    sub_10003192
0x100032dd  test    eax, eax
0x100032df  jns     short loc_100032F4
0x100032e1  mov     ecx, offset aFailedInExecco_0; "Failed in ExecCommon method"
0x100032e6  push    ecx
0x100032e7  push    eax
0x100032e8  call    sub_1000DA66
0x100032ed  pop     ecx
0x100032ee  pop     ecx
0x100032ef  mov     esi, 643h
0x100032f4  push    esi
0x100032f5  call    sub_1000D4AE
0x100032fa  pop     esi
0x100032fb  pop     ebp
0x100032fc  retn    4
```
