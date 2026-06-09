# WixCloseApplicationsDeferred

- ea: `0x1000196c`
- end: `0x10001b52`
- name: `WixCloseApplicationsDeferred`
- size: `486`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update`

## callees

- `0x10001416`
- `0x10001583`
- `0x1000196c`
- `0x1000a952`
- `0x1000aeff`
- `0x1000b2d8`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e004`
- `0x1000e662`
- `0x1000ee5c`
- `0x1000ef44`
- `0x1000efcc`

## pseudocode

```c
int __stdcall WixCloseApplicationsDeferred(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // esi
  _WORD *v3; // eax
  char v4; // al
  UINT uExitCode; // [esp+8h] [ebp-20h] BYREF
  int v7; // [esp+Ch] [ebp-1Ch] BYREF
  DWORD dwMilliseconds; // [esp+10h] [ebp-18h] BYREF
  DWORD pcchValueBuf; // [esp+14h] [ebp-14h] BYREF
  LPVOID lpMem; // [esp+18h] [ebp-10h] BYREF
  wchar_t SubStr[2]; // [esp+1Ch] [ebp-Ch] BYREF
  int v12; // [esp+20h] [ebp-8h] BYREF
  int v13; // [esp+24h] [ebp-4h] BYREF

  v1 = 0;
  *(_DWORD *)SubStr = 0;
  pcchValueBuf = 0;
  v13 = 0;
  v12 = 0;
  dwMilliseconds = 0;
  uExitCode = 0;
  lpMem = 0;
  v7 = 0;
  v2 = sub_1000D51F(hInstall, (int)"WixCloseApplicationsDeferred");
  if ( v2 >= 0 )
  {
    v2 = sub_1000E662(L"CustomActionData", (DWORD)&pcchValueBuf);
    if ( v2 >= 0 )
    {
      sub_1000D9AB(0, "CustomActionData: %ls");
      v3 = (_WORD *)pcchValueBuf;
      *(_DWORD *)SubStr = pcchValueBuf;
      while ( v3 && *v3 )
      {
        v2 = sub_1000EFCC((wchar_t)SubStr, (int)&v13);
        if ( v2 < 0 )
        {
          sub_1000DA66(v2, "failed to process target from CustomActionData");
          break;
        }
        v2 = sub_1000EF44((wchar_t)SubStr, (int)&v12);
        if ( v2 < 0 )
        {
          sub_1000DA66(v2, "failed to process attributes from CustomActionData");
          break;
        }
        v2 = sub_1000EF44((wchar_t)SubStr, (int)&dwMilliseconds);
        if ( v2 < 0 )
        {
          sub_1000DA66(v2, "failed to process timeout from CustomActionData");
          break;
        }
        v2 = sub_1000EF44((wchar_t)SubStr, (int)&uExitCode);
        if ( v2 < 0 )
        {
          sub_1000DA66(v2, "failed to process terminate exit code from CustomActionData");
          break;
        }
        sub_1000D9AB(1, "Checking for App: %ls Attributes: %d");
        v4 = v12;
        if ( (v12 & 4) != 0 )
        {
          sub_10001416(v13, 16, dwMilliseconds);
          v4 = v12;
        }
        if ( (v4 & 0x10) != 0 )
          sub_10001416(v13, 17, dwMilliseconds);
        sub_1000B2D8(v13, &lpMem, &v7);
        if ( v7 )
        {
          if ( (v12 & 2) != 0 )
          {
            sub_1000D9AB(1, "App: %ls found running, requiring a reboot.");
            sub_1000E004();
          }
          else if ( (v12 & 0x20) != 0 )
          {
            sub_10001583((int)lpMem, v7, uExitCode);
          }
        }
        v2 = sub_1000EE5C(500, 0);
        if ( v2 < 0 )
        {
          sub_1000DA66(v2, "failed to send progress message");
          break;
        }
        v3 = *(_WORD **)SubStr;
      }
    }
    else
    {
      sub_1000DA66(v2, "failed to get CustomActionData");
    }
  }
  else
  {
    sub_1000DA66(v2, "failed to initialize");
  }
  if ( lpMem )
    sub_1000AEFF(lpMem);
  if ( v13 )
    sub_1000A952(v13);
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
  if ( v2 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x1000196c  push    ebp
0x1000196d  mov     ebp, esp
0x1000196f  sub     esp, 20h
0x10001972  push    esi
0x10001973  push    edi
0x10001974  xor     edi, edi
0x10001976  push    offset aWixcloseapplic_3; "WixCloseApplicationsDeferred"
0x1000197b  push    [ebp+hInstall]; hInstall
0x1000197e  mov     dword ptr [ebp+SubStr], edi
0x10001981  mov     [ebp+pcchValueBuf], edi
0x10001984  mov     [ebp+var_4], edi
0x10001987  mov     [ebp+var_8], edi
0x1000198a  mov     [ebp+dwMilliseconds], edi
0x1000198d  mov     [ebp+uExitCode], edi
0x10001990  mov     [ebp+lpMem], edi
0x10001993  mov     [ebp+var_1C], edi
0x10001996  call    sub_1000D51F
0x1000199b  mov     esi, eax
0x1000199d  test    esi, esi
0x1000199f  jns     short loc_100019AB
0x100019a1  push    offset aFailedToInitia_2; "failed to initialize"
0x100019a6  jmp     loc_10001B0E
0x100019ab  lea     eax, [ebp+pcchValueBuf]
0x100019ae  push    eax; pcchValueBuf
0x100019af  push    offset aCustomactionda; "CustomActionData"
0x100019b4  call    sub_1000E662
0x100019b9  mov     esi, eax
0x100019bb  test    esi, esi
0x100019bd  jns     short loc_100019C9
0x100019bf  push    offset aFailedToGetCus; "failed to get CustomActionData"
0x100019c4  jmp     loc_10001B0E
0x100019c9  push    [ebp+pcchValueBuf]
0x100019cc  push    offset aCustomactionda_0; "CustomActionData: %ls"
0x100019d1  push    edi
0x100019d2  call    sub_1000D9AB
0x100019d7  mov     eax, [ebp+pcchValueBuf]
0x100019da  add     esp, 0Ch
0x100019dd  mov     dword ptr [ebp+SubStr], eax
0x100019e0  jmp     loc_10001AE3
0x100019e5  cmp     [eax], di
0x100019e8  jz      loc_10001B16
0x100019ee  lea     eax, [ebp+var_4]
0x100019f1  push    eax; int
0x100019f2  lea     eax, [ebp+SubStr]
0x100019f5  push    eax; SubStr
0x100019f6  call    sub_1000EFCC
0x100019fb  mov     esi, eax
0x100019fd  test    esi, esi
0x100019ff  js      loc_10001B09
0x10001a05  lea     eax, [ebp+var_8]
0x10001a08  push    eax; int
0x10001a09  lea     eax, [ebp+SubStr]
0x10001a0c  push    eax; SubStr
0x10001a0d  call    sub_1000EF44
0x10001a12  mov     esi, eax
0x10001a14  test    esi, esi
0x10001a16  js      loc_10001B02
0x10001a1c  lea     eax, [ebp+dwMilliseconds]
0x10001a1f  push    eax; int
0x10001a20  lea     eax, [ebp+SubStr]
0x10001a23  push    eax; SubStr
0x10001a24  call    sub_1000EF44
0x10001a29  mov     esi, eax
0x10001a2b  test    esi, esi
0x10001a2d  js      loc_10001AFB
0x10001a33  lea     eax, [ebp+uExitCode]
0x10001a36  push    eax; int
0x10001a37  lea     eax, [ebp+SubStr]
0x10001a3a  push    eax; SubStr
0x10001a3b  call    sub_1000EF44
0x10001a40  mov     esi, eax
0x10001a42  test    esi, esi
0x10001a44  js      loc_10001AF4
0x10001a4a  push    [ebp+var_8]
0x10001a4d  push    [ebp+var_4]
0x10001a50  push    offset aCheckingForApp; "Checking for App: %ls Attributes: %d"
0x10001a55  push    1
0x10001a57  call    sub_1000D9AB
0x10001a5c  mov     eax, [ebp+var_8]
0x10001a5f  add     esp, 10h
0x10001a62  test    al, 4
0x10001a64  jz      short loc_10001A76
0x10001a66  push    [ebp+dwMilliseconds]; dwMilliseconds
0x10001a69  push    10h; int
0x10001a6b  push    [ebp+var_4]; int
0x10001a6e  call    sub_10001416
0x10001a73  mov     eax, [ebp+var_8]
0x10001a76  test    al, 10h
0x10001a78  jz      short loc_10001A87
0x10001a7a  push    [ebp+dwMilliseconds]; dwMilliseconds
0x10001a7d  push    11h; int
0x10001a7f  push    [ebp+var_4]; int
0x10001a82  call    sub_10001416
0x10001a87  lea     eax, [ebp+var_1C]
0x10001a8a  push    eax
0x10001a8b  lea     eax, [ebp+lpMem]
0x10001a8e  push    eax
0x10001a8f  push    [ebp+var_4]
0x10001a92  call    sub_1000B2D8
0x10001a97  cmp     [ebp+var_1C], edi
0x10001a9a  jbe     short loc_10001ACF
0x10001a9c  test    byte ptr [ebp+var_8], 2
0x10001aa0  jz      short loc_10001ABB
0x10001aa2  push    [ebp+var_4]
0x10001aa5  push    offset aAppLsFoundRunn_1; "App: %ls found running, requiring a reb"...
0x10001aaa  push    1
0x10001aac  call    sub_1000D9AB
0x10001ab1  add     esp, 0Ch
0x10001ab4  call    sub_1000E004
0x10001ab9  jmp     short loc_10001ACF
0x10001abb  test    byte ptr [ebp+var_8], 20h
0x10001abf  jz      short loc_10001ACF
0x10001ac1  push    [ebp+uExitCode]; uExitCode
0x10001ac4  push    [ebp+var_1C]; int
0x10001ac7  push    [ebp+lpMem]; int
0x10001aca  call    sub_10001583
0x10001acf  push    edi; int
0x10001ad0  push    1F4h; iValue
0x10001ad5  call    sub_1000EE5C
0x10001ada  mov     esi, eax
0x10001adc  test    esi, esi
0x10001ade  js      short loc_10001AED
0x10001ae0  mov     eax, dword ptr [ebp+SubStr]
0x10001ae3  test    eax, eax
0x10001ae5  jnz     loc_100019E5
0x10001aeb  jmp     short loc_10001B16
0x10001aed  push    offset aFailedToSendPr; "failed to send progress message"
0x10001af2  jmp     short loc_10001B0E
0x10001af4  push    offset aFailedToProces_1; "failed to process terminate exit code f"...
0x10001af9  jmp     short loc_10001B0E
0x10001afb  push    offset aFailedToProces_2; "failed to process timeout from CustomAc"...
0x10001b00  jmp     short loc_10001B0E
0x10001b02  push    offset aFailedToProces_3; "failed to process attributes from Custo"...
0x10001b07  jmp     short loc_10001B0E
0x10001b09  push    offset aFailedToProces_4; "failed to process target from CustomAct"...
0x10001b0e  push    esi
0x10001b0f  call    sub_1000DA66
0x10001b14  pop     ecx
0x10001b15  pop     ecx
0x10001b16  cmp     [ebp+lpMem], edi
0x10001b19  jz      short loc_10001B23
0x10001b1b  push    [ebp+lpMem]; lpMem
0x10001b1e  call    sub_1000AEFF
0x10001b23  cmp     [ebp+var_4], edi
0x10001b26  jz      short loc_10001B30
0x10001b28  push    [ebp+var_4]
0x10001b2b  call    sub_1000A952
0x10001b30  mov     eax, [ebp+pcchValueBuf]
0x10001b33  test    eax, eax
0x10001b35  jz      short loc_10001B3D
0x10001b37  push    eax
0x10001b38  call    sub_1000A952
0x10001b3d  test    esi, esi
0x10001b3f  jns     short loc_10001B46
0x10001b41  mov     edi, 643h
0x10001b46  push    edi
0x10001b47  call    sub_1000D4AE
0x10001b4c  pop     edi
0x10001b4d  pop     esi
0x10001b4e  leave
0x10001b4f  retn    4
```
