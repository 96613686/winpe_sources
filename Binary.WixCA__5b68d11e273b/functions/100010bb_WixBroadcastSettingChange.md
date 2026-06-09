# WixBroadcastSettingChange

- ea: `0x100010bb`
- end: `0x10001103`
- name: `WixBroadcastSettingChange`
- size: `72`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x100010bb`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`

## import_xrefs

- `USER32!SendMessageTimeoutW` at `0x100010f2`
- `USER32!SendMessageTimeoutW` at `0x100010f2`

## pseudocode

```c
int __stdcall WixBroadcastSettingChange(MSIHANDLE hInstall)
{
  int v1; // eax

  v1 = sub_1000D51F(hInstall, (int)"WixBroadcastSettingChange");
  if ( v1 >= 0 )
    SendMessageTimeoutW(HWND_BROADCAST, 0x1Au, 0, 0, 2u, 0x3E8u, 0);
  else
    sub_1000DA66(v1, (int)"failed to initialize WixBroadcastSettingChange");
  return sub_1000D4AE(0);
}

```

## disassembly

```asm
0x100010bb  push    ebp
0x100010bc  mov     ebp, esp
0x100010be  push    esi
0x100010bf  push    offset aWixbroadcastse_0; "WixBroadcastSettingChange"
0x100010c4  push    [ebp+hInstall]; hInstall
0x100010c7  call    sub_1000D51F
0x100010cc  xor     esi, esi
0x100010ce  test    eax, eax
0x100010d0  jns     short loc_100010E1
0x100010d2  push    offset aFailedToInitia_0; "failed to initialize WixBroadcastSettin"...
0x100010d7  push    eax
0x100010d8  call    sub_1000DA66
0x100010dd  pop     ecx
0x100010de  pop     ecx
0x100010df  jmp     short loc_100010F8
0x100010e1  push    esi; lpdwResult
0x100010e2  push    3E8h; uTimeout
0x100010e7  push    2; fuFlags
0x100010e9  push    esi; lParam
0x100010ea  push    esi; wParam
0x100010eb  push    1Ah; Msg
0x100010ed  push    0FFFFh; hWnd
0x100010f2  call    ds:SendMessageTimeoutW
0x100010f8  push    esi
0x100010f9  call    sub_1000D4AE
0x100010fe  pop     esi
0x100010ff  pop     ebp
0x10001100  retn    4
```
