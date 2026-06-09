# Windows::Internal::CapabilityAccess::Private::_dynamic_initializer_for__capabilityToSuspiciousToastResourcedIDsMap__

- ea: `0x180002a30`
- end: `0x180002b35`
- name: `Windows::Internal::CapabilityAccess::Private::_dynamic_initializer_for__capabilityToSuspiciousToastResourcedIDsMap__`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003c80`
- `0x180003cf4`
- `0x180004150`
- `0x180024bec`
- `0x1800251a0`

## string_xrefs

- `0x180002a8c`: `<toast launch="ms-settings:privacy-location" activationType="protocol" duration="long"> <visual>  <binding template="ToastGeneric">   <text id="2004">%s</text>   <text id="3004">%s</text>  </binding> </visual> <actions>   <action id="Expected" activationType="Background" content="%s"/>   <action id="Unexpected" activationType="Background" content="%s"/>   <action activationType="protocol" arguments="ms-settings:privacy-location-spotlightactivity" content="%s"/> </actions></toast>`
- `0x180002a5c`: `<toast launch="ms-settings:privacy-microphone" activationType="protocol" duration="long"> <visual>  <binding template="ToastGeneric">   <text id="2004">%s</text>   <text id="3004">%s</text>  </binding> </visual> <actions>   <action id="Expected" activationType="Background" content="%s"/>   <action id="Unexpected" activationType="Background" content="%s"/>   <action activationType="protocol" arguments="ms-settings:privacy-microphone-spotlightactivity" content="%s"/> </actions></toast>`
- `0x180002aba`: `<toast launch="ms-settings:privacy-webcam" activationType="protocol" duration="long"> <visual>  <binding template="ToastGeneric">   <text id="2004">%s</text>   <text id="3004">%s</text>  </binding> </visual> <actions>   <action id="Expected" activationType="Background" content="%s"/>   <action id="Unexpected" activationType="Background" content="%s"/>   <action activationType="protocol" arguments="ms-settings:privacy-webcam-spotlightactivity" content="%s"/> </actions></toast>`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int Windows::Internal::CapabilityAccess::Private::_dynamic_initializer_for__capabilityToSuspiciousToastResourcedIDsMap__()
{
  __int128 v1; // [rsp+20h] [rbp-89h] BYREF
  __int128 v2; // [rsp+30h] [rbp-79h] BYREF
  __int128 v3; // [rsp+40h] [rbp-69h] BYREF
  __int64 v4[2]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v5[48]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v6[48]; // [rsp+90h] [rbp-19h] BYREF
  _BYTE v7[48]; // [rsp+C0h] [rbp+17h] BYREF
  __int64 v8; // [rsp+F0h] [rbp+47h] BYREF

  *(_QWORD *)&v1 = 0xBBC000007D4LL;
  *((_QWORD *)&v1 + 1) = L"<toast launch=\"ms-settings:privacy-microphone\" activationType=\"protocol\" duration=\"long\">"
                          " <visual>  <binding template=\"ToastGeneric\">   <text id=\"2004\">%s</text>   <text id=\"3004"
                          "\">%s</text>  </binding> </visual> <actions>   <action id=\"Expected\" activationType=\"Backgr"
                          "ound\" content=\"%s\"/>   <action id=\"Unexpected\" activationType=\"Background\" content=\"%s"
                          "\"/>   <action activationType=\"protocol\" arguments=\"ms-settings:privacy-microphone-spotligh"
                          "tactivity\" content=\"%s\"/> </actions></toast>";
  std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>(
    (__int64)v5,
    &c_szCapabilityMicrophone,
    &v1);
  *(_QWORD *)&v2 = 0xBBC000007D4LL;
  *((_QWORD *)&v2 + 1) = L"<toast launch=\"ms-settings:privacy-location\" activationType=\"protocol\" duration=\"long\"> <"
                          "visual>  <binding template=\"ToastGeneric\">   <text id=\"2004\">%s</text>   <text id=\"3004\""
                          ">%s</text>  </binding> </visual> <actions>   <action id=\"Expected\" activationType=\"Backgrou"
                          "nd\" content=\"%s\"/>   <action id=\"Unexpected\" activationType=\"Background\" content=\"%s\""
                          "/>   <action activationType=\"protocol\" arguments=\"ms-settings:privacy-location-spotlightact"
                          "ivity\" content=\"%s\"/> </actions></toast>";
  std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>(
    (__int64)v6,
    &c_szCapabilityLocation,
    &v2);
  *(_QWORD *)&v3 = 0xBBC000007D4LL;
  *((_QWORD *)&v3 + 1) = L"<toast launch=\"ms-settings:privacy-webcam\" activationType=\"protocol\" duration=\"long\"> <vi"
                          "sual>  <binding template=\"ToastGeneric\">   <text id=\"2004\">%s</text>   <text id=\"3004\">%"
                          "s</text>  </binding> </visual> <actions>   <action id=\"Expected\" activationType=\"Background"
                          "\" content=\"%s\"/>   <action id=\"Unexpected\" activationType=\"Background\" content=\"%s\"/>"
                          "   <action activationType=\"protocol\" arguments=\"ms-settings:privacy-webcam-spotlightactivit"
                          "y\" content=\"%s\"/> </actions></toast>";
  std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>(
    (__int64)v7,
    &c_szCapabilityWebcam,
    &v3);
  v4[0] = (__int64)v5;
  v4[1] = (__int64)&v8;
  std::map<std::wstring,Windows::Internal::CapabilityAccess::Private::ToastConfig>::map<std::wstring,Windows::Internal::CapabilityAccess::Private::ToastConfig>(
    qword_180062260,
    v4);
  `eh vector destructor iterator'(
    v5,
    0x30u,
    3u,
    (void (*)(void *))std::pair<std::wstring const,unsigned int>::~pair<std::wstring const,unsigned int>);
  return atexit(Windows::Internal::CapabilityAccess::Private::_dynamic_atexit_destructor_for__capabilityToSuspiciousToastResourcedIDsMap__);
}

```

## disassembly

```asm
0x180002a30  push    rbp
0x180002a32  lea     rbp, [rsp-57h]
0x180002a37  sub     rsp, 100h
0x180002a3e  mov     rax, cs:__security_cookie
0x180002a45  xor     rax, rsp
0x180002a48  mov     [rbp+57h+var_10], rax
0x180002a4c  mov     [rsp+100h+var_E0], 7D4h
0x180002a54  mov     [rsp+100h+var_DC], 0BBCh
0x180002a5c  lea     rax, aToastLaunchMsS_1; "<toast launch=\"ms-settings:privacy-mic"...
0x180002a63  mov     [rsp+100h+var_D8], rax
0x180002a68  lea     r8, [rsp+100h+var_E0]
0x180002a6d  lea     rdx, ?c_szCapabilityMicrophone@@3QEBGEB; ushort const * const c_szCapabilityMicrophone
0x180002a74  lea     rcx, [rbp+57h+var_A0]
0x180002a78  call    ??$?0AEBQEBGUToastConfig@Private@CapabilityAccess@Internal@Windows@@$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UToastConfig@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBQEBG$$QEAUToastConfig@Private@CapabilityAccess@Internal@Windows@@@Z; std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>(ushort const * const &,Windows::Internal::CapabilityAccess::Private::ToastConfig &&)
0x180002a7d  nop
0x180002a7e  mov     [rbp+57h+var_D0], 7D4h
0x180002a85  mov     [rbp+57h+var_CC], 0BBCh
0x180002a8c  lea     rax, aToastLaunchMsS_0; "<toast launch=\"ms-settings:privacy-loc"...
0x180002a93  mov     [rbp+57h+var_C8], rax
0x180002a97  lea     r8, [rbp+57h+var_D0]
0x180002a9b  lea     rdx, ?c_szCapabilityLocation@@3QEBGEB; ushort const * const c_szCapabilityLocation
0x180002aa2  lea     rcx, [rbp+57h+var_70]
0x180002aa6  call    ??$?0AEBQEBGUToastConfig@Private@CapabilityAccess@Internal@Windows@@$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UToastConfig@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBQEBG$$QEAUToastConfig@Private@CapabilityAccess@Internal@Windows@@@Z; std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>(ushort const * const &,Windows::Internal::CapabilityAccess::Private::ToastConfig &&)
0x180002aab  nop
0x180002aac  mov     [rbp+57h+var_C0], 7D4h
0x180002ab3  mov     [rbp+57h+var_BC], 0BBCh
0x180002aba  lea     rax, aToastLaunchMsS_2; "<toast launch=\"ms-settings:privacy-web"...
0x180002ac1  mov     [rbp+57h+var_B8], rax
0x180002ac5  lea     r8, [rbp+57h+var_C0]
0x180002ac9  lea     rdx, ?c_szCapabilityWebcam@@3QEBGEB; ushort const * const c_szCapabilityWebcam
0x180002ad0  lea     rcx, [rbp+57h+var_40]
0x180002ad4  call    ??$?0AEBQEBGUToastConfig@Private@CapabilityAccess@Internal@Windows@@$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UToastConfig@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBQEBG$$QEAUToastConfig@Private@CapabilityAccess@Internal@Windows@@@Z; std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>(ushort const * const &,Windows::Internal::CapabilityAccess::Private::ToastConfig &&)
0x180002ad9  nop
0x180002ada  lea     rax, [rbp+57h+var_A0]
0x180002ade  mov     [rbp+57h+var_B0], rax
0x180002ae2  lea     rax, [rbp+57h+var_10]
0x180002ae6  mov     [rbp+57h+var_A8], rax
0x180002aea  lea     rdx, [rbp+57h+var_B0]
0x180002aee  lea     rcx, qword_180062260
0x180002af5  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UToastConfig@Private@CapabilityAccess@Internal@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UToastConfig@Private@CapabilityAccess@Internal@Windows@@@std@@@2@@std@@QEAA@V?$initializer_list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UToastConfig@Private@CapabilityAccess@Internal@Windows@@@std@@@1@@Z; std::map<std::wstring,Windows::Internal::CapabilityAccess::Private::ToastConfig>::map<std::wstring,Windows::Internal::CapabilityAccess::Private::ToastConfig>(std::initializer_list<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>>)
0x180002afa  nop
0x180002afb  lea     r9, ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@std@@QEAA@XZ; void (*)(void *)
0x180002b02  mov     edx, 30h ; '0'; unsigned __int64
0x180002b07  lea     r8d, [rdx-2Dh]; unsigned __int64
0x180002b0b  lea     rcx, [rbp+57h+var_A0]; void *
0x180002b0f  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180002b14  lea     rcx, Windows__Internal__CapabilityAccess__Private___dynamic_atexit_destructor_for__capabilityToSuspiciousToastResourcedIDsMap__; void (__cdecl *)()
0x180002b1b  call    atexit
0x180002b20  mov     rcx, [rbp+57h+var_10]
0x180002b24  xor     rcx, rsp; StackCookie
0x180002b27  call    __security_check_cookie
0x180002b2c  add     rsp, 100h
0x180002b33  pop     rbp
0x180002b34  retn
```
