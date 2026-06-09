# WixBroadcastEnvironmentChange

- ea: `0x10001070`
- end: `0x100010bb`
- name: `WixBroadcastEnvironmentChange`
- size: `75`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x10001070`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`

## import_xrefs

- `USER32!SendMessageTimeoutW` at `0x100010aa`
- `USER32!SendMessageTimeoutW` at `0x100010aa`

## pseudocode

```c
int __stdcall WixBroadcastEnvironmentChange(MSIHANDLE hInstall)
{
  int v1; // eax

  v1 = sub_1000D51F(hInstall, (int)"WixBroadcastEnvironmentChange");
  if ( v1 >= 0 )
    SendMessageTimeoutW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"Environment", 2u, 0x3E8u, 0);
  else
    sub_1000DA66(v1, (int)"failed to initialize WixBroadcastEnvironmentChange");
  return sub_1000D4AE(0);
}

```

## disassembly

```asm
0x10001070  push    ebp
0x10001071  mov     ebp, esp
0x10001073  push    offset aWixbroadcasten_0; "WixBroadcastEnvironmentChange"
0x10001078  push    [ebp+hInstall]; hInstall
0x1000107b  call    sub_1000D51F
0x10001080  test    eax, eax
0x10001082  jns     short loc_10001093
0x10001084  push    offset aFailedToInitia; "failed to initialize WixBroadcastEnviro"...
0x10001089  push    eax
0x1000108a  call    sub_1000DA66
0x1000108f  pop     ecx
0x10001090  pop     ecx
0x10001091  jmp     short loc_100010B0
0x10001093  push    0; lpdwResult
0x10001095  push    3E8h; uTimeout
0x1000109a  push    2; fuFlags
0x1000109c  push    offset aEnvironment; "Environment"
0x100010a1  push    0; wParam
0x100010a3  push    1Ah; Msg
0x100010a5  push    0FFFFh; hWnd
0x100010aa  call    ds:SendMessageTimeoutW
0x100010b0  push    0
0x100010b2  call    sub_1000D4AE
0x100010b7  pop     ebp
0x100010b8  retn    4
```
