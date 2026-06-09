# WixCheckRebootRequired

- ea: `0x100011ab`
- end: `0x10001228`
- name: `WixCheckRebootRequired`
- size: `125`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x100011ab`
- `0x10009956`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e058`

## pseudocode

```c
int __stdcall WixCheckRebootRequired(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // esi
  signed int v3; // eax

  v1 = 0;
  v2 = sub_1000D51F(hInstall, (int)"WixCheckRebootRequired");
  if ( v2 < 0 )
  {
    sub_1000DA66(v2, "failed to initialize");
    goto LABEL_9;
  }
  if ( !sub_1000E058() )
  {
LABEL_9:
    if ( v2 < 0 )
      v1 = 1603;
    return sub_1000D4AE(v1);
  }
  sub_1000D9AB(2, "Reboot required by deferred CustomAction.");
  v3 = MsiSetMode(hInstall, MSIRUNMODE_REBOOTATEND, 1);
  v1 = v3;
  if ( v3 > 0 )
    v2 = (unsigned __int16)v3 | 0x80070000;
  else
    v2 = v3;
  if ( v2 < 0 )
  {
    sub_1000DA66(v2, "Failed to schedule reboot.");
    goto LABEL_9;
  }
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x100011ab  push    ebp
0x100011ac  mov     ebp, esp
0x100011ae  push    esi
0x100011af  push    edi
0x100011b0  push    offset aWixcheckreboot_0; "WixCheckRebootRequired"
0x100011b5  push    [ebp+hInstall]; hInstall
0x100011b8  xor     edi, edi
0x100011ba  call    sub_1000D51F
0x100011bf  mov     esi, eax
0x100011c1  test    esi, esi
0x100011c3  jns     short loc_100011CC
0x100011c5  push    offset aFailedToInitia_2; "failed to initialize"
0x100011ca  jmp     short loc_1000120B
0x100011cc  call    sub_1000E058
0x100011d1  test    eax, eax
0x100011d3  jz      short loc_10001213
0x100011d5  push    offset aRebootRequired; "Reboot required by deferred CustomActio"...
0x100011da  push    2
0x100011dc  call    sub_1000D9AB
0x100011e1  pop     ecx
0x100011e2  pop     ecx
0x100011e3  push    1; fState
0x100011e5  push    6; eRunMode
0x100011e7  push    [ebp+hInstall]; hInstall
0x100011ea  call    MsiSetMode
0x100011ef  mov     edi, eax
0x100011f1  test    edi, edi
0x100011f3  jg      short loc_100011F9
0x100011f5  mov     esi, edi
0x100011f7  jmp     short loc_10001202
0x100011f9  movzx   esi, di
0x100011fc  or      esi, 80070000h
0x10001202  test    esi, esi
0x10001204  jns     short loc_1000121C
0x10001206  push    offset aFailedToSchedu; "Failed to schedule reboot."
0x1000120b  push    esi
0x1000120c  call    sub_1000DA66
0x10001211  pop     ecx
0x10001212  pop     ecx
0x10001213  test    esi, esi
0x10001215  jns     short loc_1000121C
0x10001217  mov     edi, 643h
0x1000121c  push    edi
0x1000121d  call    sub_1000D4AE
0x10001222  pop     edi
0x10001223  pop     esi
0x10001224  pop     ebp
0x10001225  retn    4
```
