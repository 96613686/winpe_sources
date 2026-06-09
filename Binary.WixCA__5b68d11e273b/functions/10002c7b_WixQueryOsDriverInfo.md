# WixQueryOsDriverInfo

- ea: `0x10002c7b`
- end: `0x10002cd0`
- name: `WixQueryOsDriverInfo`
- size: `85`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x100025ae`
- `0x1000265c`
- `0x10002c7b`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`

## string_xrefs

- `0x10002cb2`: `Failed to detect WIX_DWM_COMPOSITION_ENABLED`

## pseudocode

```c
int __stdcall WixQueryOsDriverInfo(MSIHANDLE hInstall)
{
  int v1; // esi
  int v2; // eax
  const char *v3; // ecx

  v1 = 0;
  v2 = sub_1000D51F(hInstall, (int)"WixQueryOsDriverInfo");
  if ( v2 < 0 )
  {
    v3 = "WixQueryOsDriverInfo failed to initialize";
LABEL_7:
    sub_1000DA66(v2, v3);
    v1 = 1603;
    return sub_1000D4AE(v1);
  }
  v2 = sub_1000265C();
  if ( v2 < 0 )
  {
    v3 = "Failed to detect WIX_WDDM_DRIVER_PRESENT";
    goto LABEL_7;
  }
  v2 = sub_100025AE();
  if ( v2 < 0 )
  {
    v3 = "Failed to detect WIX_DWM_COMPOSITION_ENABLED";
    goto LABEL_7;
  }
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x10002c7b  push    ebp
0x10002c7c  mov     ebp, esp
0x10002c7e  push    esi
0x10002c7f  push    offset aWixqueryosdriv_0; "WixQueryOsDriverInfo"
0x10002c84  push    [ebp+hInstall]; hInstall
0x10002c87  xor     esi, esi
0x10002c89  call    sub_1000D51F
0x10002c8e  test    eax, eax
0x10002c90  jns     short loc_10002C99
0x10002c92  mov     ecx, offset aWixqueryosdriv_1; "WixQueryOsDriverInfo failed to initiali"...
0x10002c97  jmp     short loc_10002CB7
0x10002c99  call    sub_1000265C
0x10002c9e  test    eax, eax
0x10002ca0  jns     short loc_10002CA9
0x10002ca2  mov     ecx, offset aFailedToDetect; "Failed to detect WIX_WDDM_DRIVER_PRESEN"...
0x10002ca7  jmp     short loc_10002CB7
0x10002ca9  call    sub_100025AE
0x10002cae  test    eax, eax
0x10002cb0  jns     short loc_10002CC5
0x10002cb2  mov     ecx, offset aFailedToDetect_0; "Failed to detect WIX_DWM_COMPOSITION_EN"...
0x10002cb7  push    ecx
0x10002cb8  push    eax
0x10002cb9  call    sub_1000DA66
0x10002cbe  pop     ecx
0x10002cbf  pop     ecx
0x10002cc0  mov     esi, 643h
0x10002cc5  push    esi
0x10002cc6  call    sub_1000D4AE
0x10002ccb  pop     esi
0x10002ccc  pop     ebp
0x10002ccd  retn    4
```
