# WixCreateInternetShortcuts

- ea: `0x10001e21`
- end: `0x10001fe6`
- name: `WixCreateInternetShortcuts`
- size: `453`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10001b5a`
- `0x10001c59`
- `0x10001e21`
- `0x1000a952`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`
- `0x1000e662`
- `0x1000ee5c`
- `0x1000ef44`
- `0x1000efcc`

## import_xrefs

- `ole32!CoInitialize` at `0x10001e61`
- `ole32!CoInitialize` at `0x10001e61`
- `ole32!CoUninitialize` at `0x10001fca`
- `ole32!CoUninitialize` at `0x10001fca`

## string_xrefs

- `0x10001e6d`: `failed to initialize COM`
- `0x10001e2c`: `WixCreateInternetShortcuts`
- `0x10001e56`: `failed to initialize WixCreateInternetShortcuts`
- `0x10001f92`: `failed to read shortcut path from custom action data`
- `0x10001f8b`: `failed to read shortcut target from custom action data`
- `0x10001f84`: `failed to read shortcut attributes from custom action data`
- `0x10001f7d`: `failed to read shortcut icon path from custom action data`
- `0x10001f76`: `failed to read shortcut icon index from custom action data`
- `0x10001f6f`: `failed to create Internet shortcut`

## pseudocode

```c
int __stdcall WixCreateInternetShortcuts(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // ebx
  HRESULT v3; // esi
  _WORD *v4; // eax
  int v5; // eax
  int v6; // eax
  int v8; // [esp+Ch] [ebp-1Ch] BYREF
  int v9; // [esp+10h] [ebp-18h] BYREF
  int v10; // [esp+14h] [ebp-14h] BYREF
  DWORD pcchValueBuf; // [esp+18h] [ebp-10h] BYREF
  int v12; // [esp+1Ch] [ebp-Ch] BYREF
  int v13; // [esp+20h] [ebp-8h] BYREF
  wchar_t SubStr[2]; // [esp+24h] [ebp-4h] BYREF

  v1 = 0;
  *(_DWORD *)SubStr = 0;
  v2 = 0;
  pcchValueBuf = 0;
  v12 = 0;
  v13 = 0;
  v9 = 0;
  v8 = 0;
  v10 = 0;
  v3 = sub_1000D51F(hInstall, (int)"WixCreateInternetShortcuts");
  if ( v3 >= 0 )
  {
    v3 = CoInitialize(0);
    if ( v3 >= 0 )
    {
      v2 = 1;
      v3 = sub_1000E662(L"CustomActionData", (DWORD)&pcchValueBuf);
      if ( v3 >= 0 )
      {
        v4 = (_WORD *)pcchValueBuf;
        *(_DWORD *)SubStr = pcchValueBuf;
        if ( !pcchValueBuf )
          goto LABEL_30;
        while ( *v4 )
        {
          v3 = sub_1000EFCC((wchar_t)SubStr, (int)&v13);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to read shortcut path from custom action data");
            break;
          }
          v3 = sub_1000EFCC((wchar_t)SubStr, (int)&v12);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to read shortcut target from custom action data");
            break;
          }
          v3 = sub_1000EF44((wchar_t)SubStr, (int)&v8);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to read shortcut attributes from custom action data");
            break;
          }
          v3 = sub_1000EFCC((wchar_t)SubStr, (int)&v9);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to read shortcut icon path from custom action data");
            break;
          }
          v3 = sub_1000EF44((wchar_t)SubStr, (int)&v10);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to read shortcut icon index from custom action data");
            break;
          }
          if ( (v8 & 1) != 0 )
            v5 = sub_10001C59(v12, v13, v9, v10);
          else
            v5 = sub_10001B5A(v12, v13, v9, v10);
          v3 = v5;
          if ( v5 < 0 )
          {
            sub_1000DA66(v5, "failed to create Internet shortcut");
            break;
          }
          v6 = sub_1000EE5C(2000, 0);
          v3 = v6;
          if ( v6 < 0 )
          {
            sub_1000DA66(v6, "failed to tick progress bar for shortcut: %ls");
            break;
          }
          v4 = *(_WORD **)SubStr;
          if ( !*(_DWORD *)SubStr )
            break;
        }
      }
      else
      {
        sub_1000DA66(v3, "failed to get CustomActionData");
      }
    }
    else
    {
      sub_1000DA66(v3, "failed to initialize COM");
    }
  }
  else
  {
    sub_1000DA66(v3, "failed to initialize WixCreateInternetShortcuts");
  }
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
LABEL_30:
  if ( v12 )
    sub_1000A952(v12);
  if ( v13 )
    sub_1000A952(v13);
  if ( v2 )
    CoUninitialize();
  if ( v3 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x10001e21  push    ebp
0x10001e22  mov     ebp, esp
0x10001e24  sub     esp, 1Ch
0x10001e27  push    ebx
0x10001e28  push    esi
0x10001e29  push    edi
0x10001e2a  xor     edi, edi
0x10001e2c  push    offset aWixcreateinter_0; "WixCreateInternetShortcuts"
0x10001e31  push    [ebp+hInstall]; hInstall
0x10001e34  mov     dword ptr [ebp+SubStr], edi
0x10001e37  mov     ebx, edi
0x10001e39  mov     [ebp+pcchValueBuf], edi
0x10001e3c  mov     [ebp+var_C], edi
0x10001e3f  mov     [ebp+var_8], edi
0x10001e42  mov     [ebp+var_18], edi
0x10001e45  mov     [ebp+var_1C], edi
0x10001e48  mov     [ebp+var_14], edi
0x10001e4b  call    sub_1000D51F
0x10001e50  mov     esi, eax
0x10001e52  test    esi, esi
0x10001e54  jns     short loc_10001E60
0x10001e56  push    offset aFailedToInitia_3; "failed to initialize WixCreateInternetS"...
0x10001e5b  jmp     loc_10001F97
0x10001e60  push    edi; pvReserved
0x10001e61  call    ds:CoInitialize
0x10001e67  mov     esi, eax
0x10001e69  test    esi, esi
0x10001e6b  jns     short loc_10001E77
0x10001e6d  push    offset aFailedToInitia_4; "failed to initialize COM"
0x10001e72  jmp     loc_10001F97
0x10001e77  lea     eax, [ebp+pcchValueBuf]
0x10001e7a  xor     ebx, ebx
0x10001e7c  push    eax; pcchValueBuf
0x10001e7d  push    offset aCustomactionda; "CustomActionData"
0x10001e82  inc     ebx
0x10001e83  call    sub_1000E662
0x10001e88  mov     esi, eax
0x10001e8a  test    esi, esi
0x10001e8c  jns     short loc_10001E98
0x10001e8e  push    offset aFailedToGetCus; "failed to get CustomActionData"
0x10001e93  jmp     loc_10001F97
0x10001e98  mov     eax, [ebp+pcchValueBuf]
0x10001e9b  mov     dword ptr [ebp+SubStr], eax
0x10001e9e  test    eax, eax
0x10001ea0  jz      loc_10001FAC
0x10001ea6  cmp     [eax], di
0x10001ea9  jz      loc_10001F9F
0x10001eaf  lea     eax, [ebp+var_8]
0x10001eb2  push    eax; int
0x10001eb3  lea     eax, [ebp+SubStr]
0x10001eb6  push    eax; SubStr
0x10001eb7  call    sub_1000EFCC
0x10001ebc  mov     esi, eax
0x10001ebe  test    esi, esi
0x10001ec0  js      loc_10001F92
0x10001ec6  lea     eax, [ebp+var_C]
0x10001ec9  push    eax; int
0x10001eca  lea     eax, [ebp+SubStr]
0x10001ecd  push    eax; SubStr
0x10001ece  call    sub_1000EFCC
0x10001ed3  mov     esi, eax
0x10001ed5  test    esi, esi
0x10001ed7  js      loc_10001F8B
0x10001edd  lea     eax, [ebp+var_1C]
0x10001ee0  push    eax; int
0x10001ee1  lea     eax, [ebp+SubStr]
0x10001ee4  push    eax; SubStr
0x10001ee5  call    sub_1000EF44
0x10001eea  mov     esi, eax
0x10001eec  test    esi, esi
0x10001eee  js      loc_10001F84
0x10001ef4  lea     eax, [ebp+var_18]
0x10001ef7  push    eax; int
0x10001ef8  lea     eax, [ebp+SubStr]
0x10001efb  push    eax; SubStr
0x10001efc  call    sub_1000EFCC
0x10001f01  mov     esi, eax
0x10001f03  test    esi, esi
0x10001f05  js      short loc_10001F7D
0x10001f07  lea     eax, [ebp+var_14]
0x10001f0a  push    eax; int
0x10001f0b  lea     eax, [ebp+SubStr]
0x10001f0e  push    eax; SubStr
0x10001f0f  call    sub_1000EF44
0x10001f14  mov     esi, eax
0x10001f16  test    esi, esi
0x10001f18  js      short loc_10001F76
0x10001f1a  test    byte ptr [ebp+var_1C], 1
0x10001f1e  push    [ebp+var_14]
0x10001f21  push    [ebp+var_18]
0x10001f24  push    [ebp+var_8]
0x10001f27  push    [ebp+var_C]
0x10001f2a  jz      short loc_10001F33
0x10001f2c  call    sub_10001C59
0x10001f31  jmp     short loc_10001F38
0x10001f33  call    sub_10001B5A
0x10001f38  mov     esi, eax
0x10001f3a  test    esi, esi
0x10001f3c  js      short loc_10001F6F
0x10001f3e  push    edi; int
0x10001f3f  push    7D0h; iValue
0x10001f44  call    sub_1000EE5C
0x10001f49  mov     esi, eax
0x10001f4b  test    esi, esi
0x10001f4d  js      short loc_10001F5C
0x10001f4f  mov     eax, dword ptr [ebp+SubStr]
0x10001f52  test    eax, eax
0x10001f54  jnz     loc_10001EA6
0x10001f5a  jmp     short loc_10001F9F
0x10001f5c  push    [ebp+var_8]
0x10001f5f  push    offset aFailedToTickPr; "failed to tick progress bar for shortcu"...
0x10001f64  push    esi
0x10001f65  call    sub_1000DA66
0x10001f6a  add     esp, 0Ch
0x10001f6d  jmp     short loc_10001F9F
0x10001f6f  push    offset aFailedToCreate_2; "failed to create Internet shortcut"
0x10001f74  jmp     short loc_10001F97
0x10001f76  push    offset aFailedToReadSh; "failed to read shortcut icon index from"...
0x10001f7b  jmp     short loc_10001F97
0x10001f7d  push    offset aFailedToReadSh_0; "failed to read shortcut icon path from "...
0x10001f82  jmp     short loc_10001F97
0x10001f84  push    offset aFailedToReadSh_1; "failed to read shortcut attributes from"...
0x10001f89  jmp     short loc_10001F97
0x10001f8b  push    offset aFailedToReadSh_2; "failed to read shortcut target from cus"...
0x10001f90  jmp     short loc_10001F97
0x10001f92  push    offset aFailedToReadSh_3; "failed to read shortcut path from custo"...
0x10001f97  push    esi
0x10001f98  call    sub_1000DA66
0x10001f9d  pop     ecx
0x10001f9e  pop     ecx
0x10001f9f  cmp     [ebp+pcchValueBuf], edi
0x10001fa2  jz      short loc_10001FAC
0x10001fa4  push    [ebp+pcchValueBuf]
0x10001fa7  call    sub_1000A952
0x10001fac  cmp     [ebp+var_C], edi
0x10001faf  jz      short loc_10001FB9
0x10001fb1  push    [ebp+var_C]
0x10001fb4  call    sub_1000A952
0x10001fb9  cmp     [ebp+var_8], edi
0x10001fbc  jz      short loc_10001FC6
0x10001fbe  push    [ebp+var_8]
0x10001fc1  call    sub_1000A952
0x10001fc6  test    ebx, ebx
0x10001fc8  jz      short loc_10001FD0
0x10001fca  call    ds:CoUninitialize
0x10001fd0  test    esi, esi
0x10001fd2  jns     short loc_10001FD9
0x10001fd4  mov     edi, 643h
0x10001fd9  push    edi
0x10001fda  call    sub_1000D4AE
0x10001fdf  pop     edi
0x10001fe0  pop     esi
0x10001fe1  pop     ebx
0x10001fe2  leave
0x10001fe3  retn    4
```
