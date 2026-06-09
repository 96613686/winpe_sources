# GetAppControlSettingAsInt(void)

- ea: `0x18002e6ac`
- end: `0x18002e919`
- name: `?GetAppControlSettingAsInt@@YAHXZ`
- size: `621`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180030f28`

## callees

- `0x1800026b0`
- `0x18002c4b8`
- `0x18002e6ac`
- `0x18002fbb4`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e6ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e6ff`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002e741`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002e741`

## string_xrefs

- `0x18002e7a7`: `Smart Install App Control setting retrieved: %d`
- `0x18002e794`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x18002e864`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x18002e8bd`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x18002e89c`: `Failed AppReputationService activation, returning failure value 99.`
- `0x18002e6f8`: `Windows.Internal.Security.SmartScreen.AppReputationService`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 GetAppControlSettingAsInt(void)
{
  HRESULT v0; // eax
  int v1; // edx
  unsigned int v2; // r8d
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // [rsp+30h] [rbp-58h]
  _BYTE v10[8]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v11; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v12; // [rsp+50h] [rbp-38h] BYREF
  int v13; // [rsp+54h] [rbp-34h] BYREF
  HSTRING_HEADER v14; // [rsp+58h] [rbp-30h] BYREF
  HSTRING v15; // [rsp+70h] [rbp-18h] BYREF

  v11 = 0;
  v12 = 0;
  v13 = 0;
  v10[0] = 0;
  v15 = 0;
  v0 = WindowsCreateStringReference(L"Windows.Internal.Security.SmartScreen.AppReputationService", 0x3Au, &v14, &v15);
  if ( v0 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v0, v1, v2);
    JUMPOUT(0x18002E917LL);
  }
  if ( (int)RoGetActivationFactory(v15, &GUID_343baa78_e34f_466c_9ffa_81af5ce4cd34, &v11) < 0 )
  {
    LogMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
      0x72u,
      "GetAppControlSettingAsInt",
      -1,
      L"Failed AppReputationService activation, returning failure value 99.");
    v8 = v11;
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return 99;
  }
  else if ( (*(int (__fastcall **)(__int64, int *, _BYTE *))(*(_QWORD *)v11 + 48LL))(v11, &v13, v10) < 0 )
  {
    LogMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
      0x6Cu,
      "GetAppControlSettingAsInt",
      -1,
      L"Failed GetAppReputationEnforcementLevel, returning failure value 99.");
    v7 = v11;
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return 99;
  }
  else if ( (*(int (__fastcall **)(__int64, unsigned int *, _BYTE *))(*(_QWORD *)v11 + 64LL))(v11, &v12, v10) < 0 )
  {
    LogMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
      0x66u,
      "GetAppControlSettingAsInt",
      -1,
      L"Failed GetAppControlEnforcementLevel, returning failure value 99.");
    v6 = v11;
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return 99;
  }
  else
  {
    v9 = v12;
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
      0x61u,
      "GetAppControlSettingAsInt",
      -1,
      L"Smart Install App Control setting retrieved: %d",
      v9);
    v3 = v12;
    v4 = v11;
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return v3;
  }
}

```

## disassembly

```asm
0x18002e6ac  mov     r11, rsp
0x18002e6af  push    rbx
0x18002e6b0  sub     rsp, 80h
0x18002e6b7  mov     rax, cs:__security_cookie
0x18002e6be  xor     rax, rsp
0x18002e6c1  mov     [rsp+88h+var_10], rax
0x18002e6c6  mov     qword ptr [r11-40h], 0
0x18002e6ce  mov     [rsp+88h+var_38], 0
0x18002e6d6  mov     [rsp+88h+var_34], 0
0x18002e6de  mov     [rsp+88h+var_48], 0
0x18002e6e3  mov     qword ptr [r11-18h], 0
0x18002e6eb  lea     r9, [r11-18h]; string
0x18002e6ef  lea     r8, [r11-30h]; hstringHeader
0x18002e6f3  mov     edx, 3Ah ; ':'; length
0x18002e6f8  lea     rcx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_AppReputationService@@3QBGB; "Windows.Internal.Security.SmartScreen.A"...
0x18002e6ff  call    cs:__imp_WindowsCreateStringReference
0x18002e705  test    eax, eax
0x18002e707  js      loc_18002E910
0x18002e70d  mov     rbx, [rsp+88h+var_18]
0x18002e712  mov     rcx, [rsp+88h+var_40]
0x18002e717  test    rcx, rcx
0x18002e71a  jz      short loc_18002E732
0x18002e71c  mov     [rsp+88h+var_40], 0
0x18002e725  mov     rax, [rcx]
0x18002e728  mov     rax, [rax+10h]
0x18002e72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e731  nop
0x18002e732  lea     r8, [rsp+88h+var_40]
0x18002e737  lea     rdx, _GUID_343baa78_e34f_466c_9ffa_81af5ce4cd34
0x18002e73e  mov     rcx, rbx
0x18002e741  call    cs:__imp_RoGetActivationFactory
0x18002e747  test    eax, eax
0x18002e749  js      loc_18002E89C
0x18002e74f  mov     rcx, [rsp+88h+var_40]
0x18002e754  mov     rax, [rcx]
0x18002e757  lea     r8, [rsp+88h+var_48]
0x18002e75c  lea     rdx, [rsp+88h+var_34]
0x18002e761  mov     rax, [rax+30h]
0x18002e765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e76a  test    eax, eax
0x18002e76c  js      loc_18002E843
0x18002e772  mov     rcx, [rsp+88h+var_40]
0x18002e777  mov     rax, [rcx]
0x18002e77a  lea     r8, [rsp+88h+var_48]
0x18002e77f  lea     rdx, [rsp+88h+var_38]
0x18002e784  mov     rax, [rax+40h]
0x18002e788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e78d  lea     r9, aGetappcontrols; "GetAppControlSettingAsInt"
0x18002e794  lea     rdx, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002e79b  test    eax, eax
0x18002e79d  js      short loc_18002E7F5
0x18002e79f  mov     eax, [rsp+88h+var_38]
0x18002e7a3  mov     [rsp+88h+var_58], eax
0x18002e7a7  lea     rax, aSmartInstallAp; "Smart Install App Control setting retri"...
0x18002e7ae  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x18002e7b3  mov     [rsp+88h+var_68], 0FFFFFFFFh; int
0x18002e7bb  mov     r8d, 61h ; 'a'; unsigned int
0x18002e7c1  lea     ecx, [r8-5Eh]; unsigned int
0x18002e7c5  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x18002e7ca  mov     ebx, [rsp+88h+var_38]
0x18002e7ce  mov     rcx, [rsp+88h+var_40]
0x18002e7d3  test    rcx, rcx
0x18002e7d6  jz      short loc_18002E7EE
0x18002e7d8  mov     [rsp+88h+var_40], 0
0x18002e7e1  mov     rdx, [rcx]
0x18002e7e4  mov     rax, [rdx+10h]
0x18002e7e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7ed  nop
0x18002e7ee  mov     eax, ebx
0x18002e7f0  jmp     loc_18002E8FA
0x18002e7f5  lea     rax, aFailedGetappco; "Failed GetAppControlEnforcementLevel, r"...
0x18002e7fc  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x18002e801  mov     [rsp+88h+var_68], 0FFFFFFFFh; int
0x18002e809  mov     r8d, 66h ; 'f'; unsigned int
0x18002e80f  lea     ecx, [r8-64h]; unsigned int
0x18002e813  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x18002e818  nop
0x18002e819  mov     rcx, [rsp+88h+var_40]
0x18002e81e  test    rcx, rcx
0x18002e821  jz      short loc_18002E839
0x18002e823  mov     [rsp+88h+var_40], 0
0x18002e82c  mov     rax, [rcx]
0x18002e82f  mov     rax, [rax+10h]
0x18002e833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e838  nop
0x18002e839  mov     eax, 63h ; 'c'
0x18002e83e  jmp     loc_18002E8FA
0x18002e843  lea     rax, aFailedGetappre; "Failed GetAppReputationEnforcementLevel"...
0x18002e84a  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x18002e84f  mov     [rsp+88h+var_68], 0FFFFFFFFh; int
0x18002e857  lea     r9, aGetappcontrols; "GetAppControlSettingAsInt"
0x18002e85e  mov     r8d, 6Ch ; 'l'; unsigned int
0x18002e864  lea     rdx, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002e86b  lea     ecx, [r8-6Ah]; unsigned int
0x18002e86f  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x18002e874  nop
0x18002e875  mov     rcx, [rsp+88h+var_40]
0x18002e87a  test    rcx, rcx
0x18002e87d  jz      short loc_18002E895
0x18002e87f  mov     [rsp+88h+var_40], 0
0x18002e888  mov     rax, [rcx]
0x18002e88b  mov     rax, [rax+10h]
0x18002e88f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e894  nop
0x18002e895  mov     eax, 63h ; 'c'
0x18002e89a  jmp     short loc_18002E8FA
0x18002e89c  lea     rax, aFailedAppreput; "Failed AppReputationService activation,"...
0x18002e8a3  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x18002e8a8  mov     [rsp+88h+var_68], 0FFFFFFFFh; int
0x18002e8b0  lea     r9, aGetappcontrols; "GetAppControlSettingAsInt"
0x18002e8b7  mov     r8d, 72h ; 'r'; unsigned int
0x18002e8bd  lea     rdx, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002e8c4  lea     ecx, [r8-70h]; unsigned int
0x18002e8c8  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x18002e8cd  nop
0x18002e8ce  mov     rcx, [rsp+88h+var_40]
0x18002e8d3  test    rcx, rcx
0x18002e8d6  jz      short loc_18002E8EE
0x18002e8d8  mov     [rsp+88h+var_40], 0
0x18002e8e1  mov     rax, [rcx]
0x18002e8e4  mov     rax, [rax+10h]
0x18002e8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8ed  nop
0x18002e8ee  mov     eax, 63h ; 'c'
0x18002e8f3  jmp     short loc_18002E8FA
0x18002e8f5  mov     eax, 63h ; 'c'
0x18002e8fa  mov     rcx, [rsp+88h+var_10]
0x18002e8ff  xor     rcx, rsp; StackCookie
0x18002e902  call    __security_check_cookie
0x18002e907  add     rsp, 80h
0x18002e90e  pop     rbx
0x18002e90f  retn
0x18002e910  mov     ecx, eax; this
0x18002e912  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
