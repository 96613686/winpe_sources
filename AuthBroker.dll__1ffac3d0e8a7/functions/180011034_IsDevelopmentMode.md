# _IsDevelopmentMode

- ea: `0x180011034`
- end: `0x180011207`
- name: `_IsDevelopmentMode`
- size: `467`
- prototype: `int __fastcall(void *clientTokenHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000ed84`

## callees

- `0x1800045c0`
- `0x180004940`
- `0x180004f00`
- `0x180006d0c`
- `0x18000737c`
- `0x180011034`
- `0x180011b30`
- `0x180011d74`
- `0x180011f00`

## import_xrefs

- `api-ms-win-appmodel-identity-l1-2-0!AppXGetDevelopmentMode` at `0x180011115`
- `api-ms-win-appmodel-identity-l1-2-0!AppXGetDevelopmentMode` at `0x180011115`

## pseudocode

```c
__int64 __fastcall IsDevelopmentMode(void *clientTokenHandle)
{
  signed int AuthBrokerClientAppContainerStringInfo; // eax
  int Logger; // eax
  const _GUID *v5; // r8
  WPP_PROJECT_CONTROL_BLOCK *v6; // rcx
  int isDevelopmentMode; // [rsp+40h] [rbp+10h] BYREF
  wchar_t *packageFullName; // [rsp+48h] [rbp+18h] BYREF

  packageFullName = 0;
  isDevelopmentMode = 0;
  if ( !clientTokenHandle )
    return 0;
  if ( !HasAppContainerCapability(clientTokenHandle, 3u) )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0xAu, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
    }
    goto $Exit_12;
  }
  AuthBrokerClientAppContainerStringInfo = GetAuthBrokerClientAppContainerStringInfo(
                                             2,
                                             clientTokenHandle,
                                             &packageFullName);
  if ( AuthBrokerClientAppContainerStringInfo < 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[1].Control.Logger,
        0xBu,
        WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
        AuthBrokerClientAppContainerStringInfo);
    }
    goto $Exit_12;
  }
  Logger = AppXGetDevelopmentMode(packageFullName, &isDevelopmentMode);
  if ( Logger < 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 3u )
    {
      WPP_SF_Sd(WPP_GLOBAL_Control[1].Control.Logger, 0xCu, v5, packageFullName, Logger);
    }
    isDevelopmentMode = 0;
    goto $Exit_12;
  }
  if ( !isDevelopmentMode || !(unsigned int)GetAuthHostRegDWORDValue(L"DisableDevelopmentMode") )
    goto LABEL_25;
  isDevelopmentMode = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0 || WPP_GLOBAL_Control[1].Control.Level < 3u )
    {
LABEL_26:
      if ( v6 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (v6[1].ReserveSpace[28] & 0x10) != 0
        && v6[1].Control.Level >= 5u )
      {
        WPP_SF_dS(
          v6[1].Control.Logger,
          0xEu,
          WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
          isDevelopmentMode,
          packageFullName);
      }
      goto $Exit_12;
    }
    WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0xDu, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
LABEL_25:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
$Exit_12:
  FreeAuthBrokerClientAppContainerString(ClientAppContainerPackageFullNameInfo, packageFullName);
  return (unsigned int)isDevelopmentMode;
}

```

## disassembly

```asm
0x180011034  mov     [rsp-8+arg_10], rbx
0x180011039  push    rbp
0x18001103a  mov     rbp, rsp
0x18001103d  sub     rsp, 30h
0x180011041  mov     [rbp+packageFullName], 0
0x180011049  mov     rbx, clientTokenHandle
0x18001104c  mov     [rbp+isDevelopmentMode], 0
0x180011053  test    clientTokenHandle, clientTokenHandle
0x180011056  jnz     short loc_18001105F
0x180011058  xor     eax, eax
0x18001105a  jmp     loc_1800111FC
0x18001105f  mov     edx, 3; capabilityToCheck
0x180011064  call    _HasAppContainerCapability
0x180011069  test    eax, eax
0x18001106b  jnz     short loc_1800110B0
0x18001106d  mov     clientTokenHandle, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180011074  lea     rbx, WPP_GLOBAL_Control
0x18001107b  cmp     clientTokenHandle, rbx
0x18001107e  jz      $Exit_12
0x180011084  test    byte ptr [clientTokenHandle+44h], 10h
0x180011088  jz      $Exit_12
0x18001108e  cmp     byte ptr [clientTokenHandle+41h], 5
0x180011092  jb      $Exit_12
0x180011098  mov     clientTokenHandle, [clientTokenHandle+38h]; Logger
0x18001109c  lea     edx, [rax+0Ah]; id
0x18001109f  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x1800110a6  call    WPP_SF_
0x1800110ab  jmp     $Exit_12
0x1800110b0  lea     r8, [rbp+packageFullName]; string
0x1800110b4  mov     rdx, rbx; clientTokenHandle
0x1800110b7  mov     ecx, 2; infoType
0x1800110bc  call    ?GetAuthBrokerClientAppContainerStringInfo@@YAJW4ClientAppContainerStringInfoType@@PEAXPEAPEAG@Z; GetAuthBrokerClientAppContainerStringInfo(ClientAppContainerStringInfoType,void *,ushort * *)
0x1800110c1  test    eax, eax
0x1800110c3  jns     short loc_18001110D
0x1800110c5  mov     clientTokenHandle, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800110cc  lea     rbx, WPP_GLOBAL_Control
0x1800110d3  cmp     clientTokenHandle, rbx
0x1800110d6  jz      $Exit_12
0x1800110dc  test    byte ptr [clientTokenHandle+44h], 10h
0x1800110e0  jz      $Exit_12
0x1800110e6  cmp     byte ptr [clientTokenHandle+41h], 2
0x1800110ea  jb      $Exit_12
0x1800110f0  mov     clientTokenHandle, [clientTokenHandle+38h]; Logger
0x1800110f4  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x1800110fb  mov     edx, 0Bh; id
0x180011100  mov     r9d, eax; _a1
0x180011103  call    WPP_SF_d
0x180011108  jmp     $Exit_12
0x18001110d  mov     clientTokenHandle, [rbp+packageFullName]
0x180011111  lea     rdx, [rbp+isDevelopmentMode]
0x180011115  call    cs:__imp_AppXGetDevelopmentMode
0x18001111b  test    eax, eax
0x18001111d  jns     short loc_180011160
0x18001111f  mov     clientTokenHandle, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180011126  lea     rbx, WPP_GLOBAL_Control
0x18001112d  cmp     clientTokenHandle, rbx
0x180011130  jz      short loc_180011154
0x180011132  test    byte ptr [clientTokenHandle+44h], 10h
0x180011136  jz      short loc_180011154
0x180011138  cmp     byte ptr [clientTokenHandle+41h], 3
0x18001113c  jb      short loc_180011154
0x18001113e  mov     r9, [rbp+packageFullName]; _a2
0x180011142  mov     edx, 0Ch; id
0x180011147  mov     clientTokenHandle, [clientTokenHandle+38h]; Logger
0x18001114b  mov     [rsp+30h+Logger], eax; Logger
0x18001114f  call    WPP_SF_Sd
0x180011154  mov     [rbp+isDevelopmentMode], 0
0x18001115b  jmp     $Exit_12
0x180011160  cmp     [rbp+isDevelopmentMode], 0
0x180011164  lea     rbx, WPP_GLOBAL_Control
0x18001116b  jz      short loc_1800111B1
0x18001116d  lea     clientTokenHandle, aDisabledevelop; "DisableDevelopmentMode"
0x180011174  call    ?GetAuthHostRegDWORDValue@@YAKPEBG@Z; GetAuthHostRegDWORDValue(ushort const *)
0x180011179  test    eax, eax
0x18001117b  jz      short loc_1800111B1
0x18001117d  mov     [rbp+isDevelopmentMode], 0
0x180011184  mov     clientTokenHandle, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001118b  cmp     clientTokenHandle, rbx
0x18001118e  jz      short $Exit_12
0x180011190  test    byte ptr [clientTokenHandle+44h], 10h
0x180011194  jz      short loc_1800111B8
0x180011196  cmp     byte ptr [clientTokenHandle+41h], 3
0x18001119a  jb      short loc_1800111B8
0x18001119c  mov     clientTokenHandle, [clientTokenHandle+38h]; Logger
0x1800111a0  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x1800111a7  mov     edx, 0Dh; id
0x1800111ac  call    WPP_SF_
0x1800111b1  mov     clientTokenHandle, cs:WPP_GLOBAL_Control
0x1800111b8  cmp     clientTokenHandle, rbx; __annotation("TMF:",
0x1800111bb  jz      short $Exit_12
0x1800111bd  test    byte ptr [clientTokenHandle+44h], 10h
0x1800111c1  jz      short $Exit_12
0x1800111c3  cmp     byte ptr [clientTokenHandle+41h], 5
0x1800111c7  jb      short $Exit_12
0x1800111c9  mov     rax, [rbp+packageFullName]
0x1800111cd  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x1800111d4  mov     r9d, [rbp+isDevelopmentMode]; _a1
0x1800111d8  mov     edx, 0Eh; id
0x1800111dd  mov     clientTokenHandle, [clientTokenHandle+38h]; Logger
0x1800111e1  mov     qword ptr [rsp+30h+Logger], rax; _a2
0x1800111e6  call    WPP_SF_dS
0x1800111eb  mov     rdx, [rbp+packageFullName]; string
0x1800111ef  mov     ecx, 2; infoType
0x1800111f4  call    ?FreeAuthBrokerClientAppContainerString@@YAXW4ClientAppContainerStringInfoType@@PEAG@Z; FreeAuthBrokerClientAppContainerString(ClientAppContainerStringInfoType,ushort *)
0x1800111f9  mov     eax, [rbp+isDevelopmentMode]
0x1800111fc  mov     rbx, [rsp+30h+arg_10]
0x180011201  add     rsp, 30h
0x180011205  pop     rbp
0x180011206  retn
```
