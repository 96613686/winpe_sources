# Windows::Internal::CapabilityAccess::Private::_dynamic_initializer_for__capabilityToToastResourceIDsMap___0

- ea: `0x180002b40`
- end: `0x180002c7e`
- name: `Windows::Internal::CapabilityAccess::Private::_dynamic_initializer_for__capabilityToToastResourceIDsMap___0`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003c80`
- `0x180003cf4`
- `0x180004150`
- `0x180024bb4`
- `0x180024bec`
- `0x1800251a0`

## string_xrefs

- `0x180002b6c`: `<toast launch="ms-settings:privacy" activationType="protocol"> <visual>  <binding template="ToastGeneric">   <text id="2000"></text>   <text id="3000"></text>  </binding> </visual></toast>`
- `0x180002bca`: `<toast launch="ms-settings:privacy-location" activationType="protocol"> <visual>  <binding template="ToastGeneric">   <text id="2002"></text>   <text id="3002"></text>  </binding> </visual></toast>`
- `0x180002b98`: `<toast launch="ms-settings:privacy-microphone" activationType="protocol"> <visual>  <binding template="ToastGeneric">   <text id="2001"></text>   <text id="3001"></text>  </binding> </visual></toast>`
- `0x180002bfc`: `<toast launch="ms-settings:privacy-webcam" activationType="protocol"> <visual>  <binding template="ToastGeneric">   <text id="2003"></text>   <text id="3003"></text>  </binding> </visual></toast>`

## pseudocode

```c
int __fastcall Windows::Internal::CapabilityAccess::Private::_dynamic_initializer_for__capabilityToToastResourceIDsMap___0(
        __int64 a1,
        __int64 a2)
{
  __int128 v3; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v4; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v5; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v6; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v7[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v8[48]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v9[48]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v10[48]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v11[48]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v12; // [rsp+130h] [rbp+30h] BYREF

  *(_QWORD *)&v3 = 12884901890000LL;
  *((_QWORD *)&v3 + 1) = L"<toast launch=\"ms-settings:privacy\" activationType=\"protocol\"> <visual>  <binding template="
                          "\"ToastGeneric\">   <text id=\"2000\"></text>   <text id=\"3000\"></text>  </binding> </visual></toast>";
  std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>(
    (__int64)v8,
    a2,
    &v3);
  *(_QWORD *)&v4 = 0xBB9000007D1LL;
  *((_QWORD *)&v4 + 1) = L"<toast launch=\"ms-settings:privacy-microphone\" activationType=\"protocol\"> <visual>  <bindin"
                          "g template=\"ToastGeneric\">   <text id=\"2001\"></text>   <text id=\"3001\"></text>  </bindin"
                          "g> </visual></toast>";
  std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>(
    (__int64)v9,
    &c_szCapabilityMicrophone,
    &v4);
  *(_QWORD *)&v5 = 0xBBA000007D2LL;
  *((_QWORD *)&v5 + 1) = L"<toast launch=\"ms-settings:privacy-location\" activationType=\"protocol\"> <visual>  <binding "
                          "template=\"ToastGeneric\">   <text id=\"2002\"></text>   <text id=\"3002\"></text>  </binding>"
                          " </visual></toast>";
  std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>(
    (__int64)v10,
    &c_szCapabilityLocation,
    &v5);
  *(_QWORD *)&v6 = 0xBBB000007D3LL;
  *((_QWORD *)&v6 + 1) = L"<toast launch=\"ms-settings:privacy-webcam\" activationType=\"protocol\"> <visual>  <binding te"
                          "mplate=\"ToastGeneric\">   <text id=\"2003\"></text>   <text id=\"3003\"></text>  </binding> <"
                          "/visual></toast>";
  std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>(
    (__int64)v11,
    &c_szCapabilityWebcam,
    &v6);
  v7[0] = (__int64)v8;
  v7[1] = (__int64)&v12;
  std::map<std::wstring,Windows::Internal::CapabilityAccess::Private::ToastConfig>::map<std::wstring,Windows::Internal::CapabilityAccess::Private::ToastConfig>(
    qword_180062270,
    v7);
  `eh vector destructor iterator'(
    v8,
    0x30u,
    4u,
    (void (*)(void *))std::pair<std::wstring const,unsigned int>::~pair<std::wstring const,unsigned int>);
  return atexit(Windows::Internal::CapabilityAccess::Private::_dynamic_atexit_destructor_for__capabilityToToastResourceIDsMap___0);
}

```

## disassembly

```asm
0x180002b40  push    rbp
0x180002b42  lea     rbp, [rsp-40h]
0x180002b47  sub     rsp, 140h
0x180002b4e  mov     rax, cs:__security_cookie
0x180002b55  xor     rax, rsp
0x180002b58  mov     [rbp+40h+var_10], rax
0x180002b5c  mov     [rsp+140h+var_120], 7D0h
0x180002b64  mov     [rsp+140h+var_11C], 0BB8h
0x180002b6c  lea     rax, aToastLaunchMsS_4; "<toast launch=\"ms-settings:privacy\" a"...
0x180002b73  mov     [rsp+140h+var_118], rax
0x180002b78  lea     r8, [rsp+140h+var_120]
0x180002b7d  lea     rcx, [rsp+140h+var_D0]
0x180002b82  call    ??$?0AEAY0CM@$$CBGUToastConfig@Private@CapabilityAccess@Internal@Windows@@$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UToastConfig@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEAY0CM@$$CBG$$QEAUToastConfig@Private@CapabilityAccess@Internal@Windows@@@Z; std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>(ushort const (&)[44],Windows::Internal::CapabilityAccess::Private::ToastConfig &&)
0x180002b87  nop
0x180002b88  mov     [rsp+140h+var_110], 7D1h
0x180002b90  mov     [rsp+140h+var_10C], 0BB9h
0x180002b98  lea     rax, aToastLaunchMsS_3; "<toast launch=\"ms-settings:privacy-mic"...
0x180002b9f  mov     [rsp+140h+var_108], rax
0x180002ba4  lea     r8, [rsp+140h+var_110]
0x180002ba9  lea     rdx, ?c_szCapabilityMicrophone@@3QEBGEB; ushort const * const c_szCapabilityMicrophone
0x180002bb0  lea     rcx, [rbp+40h+var_A0]
0x180002bb4  call    ??$?0AEBQEBGUToastConfig@Private@CapabilityAccess@Internal@Windows@@$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UToastConfig@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBQEBG$$QEAUToastConfig@Private@CapabilityAccess@Internal@Windows@@@Z; std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>(ushort const * const &,Windows::Internal::CapabilityAccess::Private::ToastConfig &&)
0x180002bb9  nop
0x180002bba  mov     [rsp+140h+var_100], 7D2h
0x180002bc2  mov     [rsp+140h+var_FC], 0BBAh
0x180002bca  lea     rax, aToastLaunchMsS; "<toast launch=\"ms-settings:privacy-loc"...
0x180002bd1  mov     [rsp+140h+var_F8], rax
0x180002bd6  lea     r8, [rsp+140h+var_100]
0x180002bdb  lea     rdx, ?c_szCapabilityLocation@@3QEBGEB; ushort const * const c_szCapabilityLocation
0x180002be2  lea     rcx, [rbp+40h+var_70]
0x180002be6  call    ??$?0AEBQEBGUToastConfig@Private@CapabilityAccess@Internal@Windows@@$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UToastConfig@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBQEBG$$QEAUToastConfig@Private@CapabilityAccess@Internal@Windows@@@Z; std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>(ushort const * const &,Windows::Internal::CapabilityAccess::Private::ToastConfig &&)
0x180002beb  nop
0x180002bec  mov     [rsp+140h+var_F0], 7D3h
0x180002bf4  mov     [rsp+140h+var_EC], 0BBBh
0x180002bfc  lea     rax, aToastLaunchMsS_5; "<toast launch=\"ms-settings:privacy-web"...
0x180002c03  mov     [rsp+140h+var_E8], rax
0x180002c08  lea     r8, [rsp+140h+var_F0]
0x180002c0d  lea     rdx, ?c_szCapabilityWebcam@@3QEBGEB; ushort const * const c_szCapabilityWebcam
0x180002c14  lea     rcx, [rbp+40h+var_40]
0x180002c18  call    ??$?0AEBQEBGUToastConfig@Private@CapabilityAccess@Internal@Windows@@$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UToastConfig@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBQEBG$$QEAUToastConfig@Private@CapabilityAccess@Internal@Windows@@@Z; std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>(ushort const * const &,Windows::Internal::CapabilityAccess::Private::ToastConfig &&)
0x180002c1d  nop
0x180002c1e  lea     rax, [rsp+140h+var_D0]
0x180002c23  mov     [rsp+140h+var_E0], rax
0x180002c28  lea     rax, [rbp+40h+var_10]
0x180002c2c  mov     [rsp+140h+var_D8], rax
0x180002c31  lea     rdx, [rsp+140h+var_E0]
0x180002c36  lea     rcx, qword_180062270
0x180002c3d  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UToastConfig@Private@CapabilityAccess@Internal@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UToastConfig@Private@CapabilityAccess@Internal@Windows@@@std@@@2@@std@@QEAA@V?$initializer_list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UToastConfig@Private@CapabilityAccess@Internal@Windows@@@std@@@1@@Z; std::map<std::wstring,Windows::Internal::CapabilityAccess::Private::ToastConfig>::map<std::wstring,Windows::Internal::CapabilityAccess::Private::ToastConfig>(std::initializer_list<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ToastConfig>>)
0x180002c42  nop
0x180002c43  lea     r9, ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@std@@QEAA@XZ; void (*)(void *)
0x180002c4a  mov     edx, 30h ; '0'; unsigned __int64
0x180002c4f  lea     r8d, [rdx-2Ch]; unsigned __int64
0x180002c53  lea     rcx, [rsp+140h+var_D0]; void *
0x180002c58  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180002c5d  lea     rcx, Windows__Internal__CapabilityAccess__Private___dynamic_atexit_destructor_for__capabilityToToastResourceIDsMap___0; void (__cdecl *)()
0x180002c64  call    atexit
0x180002c69  mov     rcx, [rbp+40h+var_10]
0x180002c6d  xor     rcx, rsp; StackCookie
0x180002c70  call    __security_check_cookie
0x180002c75  add     rsp, 140h
0x180002c7c  pop     rbp
0x180002c7d  retn
```
