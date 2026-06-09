# WxDevice::CreateWfdDevice(void)

- ea: `0x1400cbbdc`
- end: `0x1400cbf04`
- name: `?CreateWfdDevice@WxDevice@@QEAAJXZ`
- size: `808`
- prototype: `__int64 __fastcall(WxDevice *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x1400695e0`

## callees

- `0x14000c778`
- `0x140054ed8`
- `0x140061338`
- `0x14006ab94`
- `0x14008c238`
- `0x1400cac7c`
- `0x1400cb630`
- `0x1400cbbdc`
- `0x1400ceac8`
- `0x1400dfd40`

## string_xrefs

- `0x1400cbcfd`: `adapterExtensionInit`

## pseudocode

```c
__int64 __fastcall WxDevice::CreateWfdDevice(WxDevice *this)
{
  __int64 v2; // rax
  CAdapter *v3; // r12
  int v4; // edx
  __int64 v6; // rax
  int v7; // edx
  int v8; // r8d
  __int64 v9; // rbx
  int v10; // r9d
  const char *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rdi
  int v14; // esi
  __int64 v15; // rax
  int v16; // edx
  WxDevice *v17; // rcx
  struct NETADAPTER__ *v18; // rbx
  int started; // eax
  int v20; // r9d
  __int64 v21; // r14
  struct CPort *v22; // r14
  int v23; // r12d
  __int64 v24; // [rsp+28h] [rbp-40h]
  __int64 v25; // [rsp+70h] [rbp+8h] BYREF
  __int64 v26; // [rsp+78h] [rbp+10h] BYREF

  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01031 + 1616))(
         WdfDriverGlobals,
         *((_QWORD *)this + 1),
         off_14010E308);
  LOWORD(v25) = 0;
  v3 = (CAdapter *)(v2 + 56);
  if ( (unsigned int)CAdapter::GetPortIdForPortType(v2 + 56, 4, &v25) || !(_WORD)v25 )
  {
    v6 = ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, _QWORD))NetFunctions)(NetDriverGlobals, *((_QWORD *)this + 1));
    v26 = v6;
    v9 = v6;
    if ( !v6 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v10 = 33;
        v11 = "adapterInit.get()";
LABEL_12:
        WPP_RECORDER_SF_qs(
          WPP_GLOBAL_Control->DeviceExtension,
          v7,
          v8,
          v10,
          (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
          *((_QWORD *)this + 1),
          (__int64)v11);
        goto LABEL_13;
      }
      goto LABEL_13;
    }
    v12 = ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, __int64))qword_140110C98)(NetDriverGlobals, v6);
    v13 = v12;
    if ( !v12 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v10 = 34;
        v11 = "adapterExtensionInit";
        goto LABEL_12;
      }
LABEL_13:
      v14 = -1073741670;
LABEL_35:
      wil::details::unique_storage<wil::details::resource_policy<_NETADAPTER_INIT *,void (*)(_NETADAPTER_INIT *),&void NetAdapterInitFree(_NETADAPTER_INIT *),wistd::integral_constant<unsigned __int64,0>,_NETADAPTER_INIT *,_NETADAPTER_INIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_NETADAPTER_INIT *,void (*)(_NETADAPTER_INIT *),&void NetAdapterInitFree(_NETADAPTER_INIT *),wistd::integral_constant<unsigned __int64,0>,_NETADAPTER_INIT *,_NETADAPTER_INIT *,0,std::nullptr_t>>(&v26);
      return (unsigned int)v14;
    }
    ((void (__fastcall *)(PNET_DRIVER_GLOBALS, __int64, void *))qword_140110CA0)(
      NetDriverGlobals,
      v12,
      &EvtWfdDevicePreProcessOidRequest);
    ((void (__fastcall *)(PNET_DRIVER_GLOBALS, __int64, void *))qword_140110E50)(
      NetDriverGlobals,
      v13,
      &EvtWfdDevicePreProcessDirectOidRequest);
    v14 = (*((__int64 (__fastcall **)(_QWORD, __int64))this + 6))(*((_QWORD *)this + 1), v9);
    v15 = ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, __int64))qword_140110C90)(NetDriverGlobals, v9);
    v25 = v15;
    v18 = (struct NETADAPTER__ *)v15;
    if ( v14 )
    {
      if ( v15 )
      {
        v21 = *(_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                           WdfDriverGlobals,
                           v15,
                           off_14010EC10);
        if ( v21 )
        {
          v22 = (struct CPort *)(v21 + 32);
          if ( v22 )
          {
            if ( *((_DWORD *)v22 + 38) )
            {
              v23 = CAdapter::RemovePort(v3, v22);
              CPort::Uninitialize(v22);
              if ( v23 != -1073676261 && v23 )
                __int2c();
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v16) = 2;
                WPP_RECORDER_SF_d(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v16,
                  1,
                  35,
                  (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
                  *((_DWORD *)v22 + 38));
              }
            }
          }
        }
      }
      if ( v14 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_33:
          wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(&v25);
          goto LABEL_35;
        }
        v20 = 36;
        LODWORD(v24) = v14;
LABEL_32:
        LOBYTE(v16) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v16,
          1,
          v20,
          (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
          v24);
        goto LABEL_33;
      }
    }
    else if ( !v15 )
    {
      __int2c();
    }
    started = WxDevice::StartWfdDeviceInnerNetAdapter(v17, v18);
    v14 = started;
    if ( started >= 0 )
    {
      v25 = 0;
      wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(&v25);
      v14 = 0;
      goto LABEL_35;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_33;
    v20 = 37;
    LODWORD(v24) = started;
    goto LABEL_32;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      1,
      32,
      (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
      (unsigned __int16)v25);
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x1400cbbdc  mov     [rsp+arg_10], rbx
0x1400cbbe1  mov     [rsp+arg_18], rbp
0x1400cbbe6  push    rsi
0x1400cbbe7  push    rdi
0x1400cbbe8  push    r12
0x1400cbbea  push    r13
0x1400cbbec  push    r14
0x1400cbbee  sub     rsp, 40h
0x1400cbbf2  mov     rax, cs:WdfFunctions_01031
0x1400cbbf9  mov     rsi, rcx
0x1400cbbfc  mov     rdx, [rcx+8]
0x1400cbc00  mov     r8, cs:off_14010E308
0x1400cbc07  mov     rcx, cs:WdfDriverGlobals
0x1400cbc0e  mov     rax, [rax+650h]
0x1400cbc15  call    _guard_dispatch_icall
0x1400cbc1a  xor     r13d, r13d
0x1400cbc1d  lea     r8, [rsp+68h+arg_0]
0x1400cbc22  mov     word ptr [rsp+68h+arg_0], r13w
0x1400cbc28  lea     r12, [rax+38h]
0x1400cbc2c  mov     rcx, r12
0x1400cbc2f  lea     edx, [r13+4]
0x1400cbc33  call    ?GetPortIdForPortType@CAdapter@@QEAAHW4_WFC_PORT_TYPE@@PEAG@Z; CAdapter::GetPortIdForPortType(_WFC_PORT_TYPE,ushort *)
0x1400cbc38  test    eax, eax
0x1400cbc3a  jnz     short loc_1400CBC8A
0x1400cbc3c  movzx   eax, word ptr [rsp+68h+arg_0]
0x1400cbc41  test    ax, ax
0x1400cbc44  jz      short loc_1400CBC8A
0x1400cbc46  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400cbc4d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400cbc54  jz      short loc_1400CBC80
0x1400cbc56  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbc5d  lea     rbp, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cbc64  mov     dword ptr [rsp+68h+var_40], eax
0x1400cbc68  lea     r9d, [r13+20h]
0x1400cbc6c  lea     r8d, [r13+1]
0x1400cbc70  mov     [rsp+68h+var_48], rbp
0x1400cbc75  mov     dl, 2
0x1400cbc77  mov     rcx, [rcx+40h]
0x1400cbc7b  call    WPP_RECORDER_SF_d
0x1400cbc80  mov     eax, 0C0000001h
0x1400cbc85  jmp     loc_1400CBEEA
0x1400cbc8a  mov     rax, cs:NetFunctions
0x1400cbc91  mov     rdx, [rsi+8]
0x1400cbc95  mov     rcx, cs:NetDriverGlobals
0x1400cbc9c  call    _guard_dispatch_icall
0x1400cbca1  mov     [rsp+68h+arg_8], rax
0x1400cbca6  mov     rbx, rax
0x1400cbca9  test    rax, rax
0x1400cbcac  jnz     short loc_1400CBCCB
0x1400cbcae  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400cbcb5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400cbcbc  jz      short loc_1400CBD2E
0x1400cbcbe  lea     r9d, [rax+21h]
0x1400cbcc2  lea     rax, aAdapterinitGet; "adapterInit.get()"
0x1400cbcc9  jmp     short loc_1400CBD04
0x1400cbccb  mov     rax, cs:qword_140110C98
0x1400cbcd2  mov     rdx, rbx
0x1400cbcd5  mov     rcx, cs:NetDriverGlobals
0x1400cbcdc  call    _guard_dispatch_icall
0x1400cbce1  mov     rdi, rax
0x1400cbce4  test    rax, rax
0x1400cbce7  jnz     short loc_1400CBD38
0x1400cbce9  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400cbcf0  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400cbcf7  jz      short loc_1400CBD2E
0x1400cbcf9  lea     r9d, [rax+22h]
0x1400cbcfd  lea     rax, aAdapterextensi; "adapterExtensionInit"
0x1400cbd04  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbd0b  lea     rbp, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cbd12  mov     [rsp+68h+var_38], rax
0x1400cbd17  mov     rax, [rsi+8]
0x1400cbd1b  mov     [rsp+68h+var_40], rax
0x1400cbd20  mov     rcx, [rcx+40h]
0x1400cbd24  mov     [rsp+68h+var_48], rbp
0x1400cbd29  call    WPP_RECORDER_SF_qs
0x1400cbd2e  mov     esi, 0C000009Ah
0x1400cbd33  jmp     loc_1400CBEDE
0x1400cbd38  mov     rax, cs:qword_140110CA0
0x1400cbd3f  lea     r8, EvtWfdDevicePreProcessOidRequest
0x1400cbd46  mov     rcx, cs:NetDriverGlobals
0x1400cbd4d  mov     rdx, rdi
0x1400cbd50  call    _guard_dispatch_icall
0x1400cbd55  mov     rax, cs:qword_140110E50
0x1400cbd5c  lea     r8, EvtWfdDevicePreProcessDirectOidRequest
0x1400cbd63  mov     rcx, cs:NetDriverGlobals
0x1400cbd6a  mov     rdx, rdi
0x1400cbd6d  call    _guard_dispatch_icall
0x1400cbd72  mov     rax, [rsi+30h]
0x1400cbd76  mov     rdx, rbx
0x1400cbd79  mov     rcx, [rsi+8]
0x1400cbd7d  call    _guard_dispatch_icall
0x1400cbd82  mov     rcx, cs:NetDriverGlobals
0x1400cbd89  mov     esi, eax
0x1400cbd8b  mov     rax, cs:qword_140110C90
0x1400cbd92  mov     rdx, rbx
0x1400cbd95  call    _guard_dispatch_icall
0x1400cbd9a  mov     [rsp+68h+arg_0], rax
0x1400cbd9f  mov     rbx, rax
0x1400cbda2  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400cbda9  lea     rbp, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cbdb0  test    esi, esi
0x1400cbdb2  jnz     short loc_1400CBDE9
0x1400cbdb4  test    rax, rax
0x1400cbdb7  jnz     short loc_1400CBDBB
0x1400cbdb9  int     2Ch; Windows NT - assertion failure
0x1400cbdbb  mov     rdx, rbx; struct NETADAPTER__ *
0x1400cbdbe  call    ?StartWfdDeviceInnerNetAdapter@WxDevice@@QEAAJPEAUNETADAPTER__@@@Z; WxDevice::StartWfdDeviceInnerNetAdapter(NETADAPTER__ *)
0x1400cbdc3  mov     esi, eax
0x1400cbdc5  test    eax, eax
0x1400cbdc7  jns     loc_1400CBECC
0x1400cbdcd  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400cbdd4  jz      loc_1400CBEC0
0x1400cbdda  mov     r9d, 25h ; '%'
0x1400cbde0  mov     dword ptr [rsp+68h+var_40], eax
0x1400cbde4  jmp     loc_1400CBEA3
0x1400cbde9  test    rbx, rbx
0x1400cbdec  jz      loc_1400CBE88
0x1400cbdf2  mov     rax, cs:WdfFunctions_01031
0x1400cbdf9  mov     rdx, rbx
0x1400cbdfc  mov     r8, cs:off_14010EC10
0x1400cbe03  mov     rcx, cs:WdfDriverGlobals
0x1400cbe0a  mov     rax, [rax+650h]
0x1400cbe11  call    _guard_dispatch_icall
0x1400cbe16  mov     r14, [rax]
0x1400cbe19  test    r14, r14
0x1400cbe1c  jz      short loc_1400CBE88
0x1400cbe1e  add     r14, 20h ; ' '
0x1400cbe22  jz      short loc_1400CBE88
0x1400cbe24  cmp     [r14+98h], r13d
0x1400cbe2b  jz      short loc_1400CBE88
0x1400cbe2d  mov     rdx, r14; struct CPort *
0x1400cbe30  mov     rcx, r12; this
0x1400cbe33  call    ?RemovePort@CAdapter@@QEAAHPEAVCPort@@@Z; CAdapter::RemovePort(CPort *)
0x1400cbe38  mov     rcx, r14; this
0x1400cbe3b  mov     r12d, eax
0x1400cbe3e  call    ?Uninitialize@CPort@@QEAAXXZ; CPort::Uninitialize(void)
0x1400cbe43  cmp     r12d, 0C001001Bh
0x1400cbe4a  jz      short loc_1400CBE53
0x1400cbe4c  test    r12d, r12d
0x1400cbe4f  jz      short loc_1400CBE53
0x1400cbe51  int     2Ch; Windows NT - assertion failure
0x1400cbe53  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400cbe5a  jz      short loc_1400CBE88
0x1400cbe5c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbe63  mov     r9d, 23h ; '#'
0x1400cbe69  mov     eax, [r14+98h]
0x1400cbe70  mov     dl, 2
0x1400cbe72  mov     dword ptr [rsp+68h+var_40], eax
0x1400cbe76  mov     [rsp+68h+var_48], rbp
0x1400cbe7b  mov     rcx, [rcx+40h]
0x1400cbe7f  lea     r8d, [r9-22h]
0x1400cbe83  call    WPP_RECORDER_SF_d
0x1400cbe88  test    esi, esi
0x1400cbe8a  jns     loc_1400CBDBB
0x1400cbe90  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400cbe97  jz      short loc_1400CBEC0
0x1400cbe99  mov     r9d, 24h ; '$'
0x1400cbe9f  mov     dword ptr [rsp+68h+var_40], esi
0x1400cbea3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbeaa  mov     r8d, 1
0x1400cbeb0  mov     dl, 2
0x1400cbeb2  mov     [rsp+68h+var_48], rbp
0x1400cbeb7  mov     rcx, [rcx+40h]
0x1400cbebb  call    WPP_RECORDER_SF_d
0x1400cbec0  lea     rcx, [rsp+68h+arg_0]
0x1400cbec5  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x1400cbeca  jmp     short loc_1400CBEDE
0x1400cbecc  lea     rcx, [rsp+68h+arg_0]
0x1400cbed1  mov     [rsp+68h+arg_0], r13
0x1400cbed6  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x1400cbedb  mov     esi, r13d
0x1400cbede  lea     rcx, [rsp+68h+arg_8]
0x1400cbee3  call    ??1?$unique_storage@U?$resource_policy@PEAU_NETADAPTER_INIT@@P6AXPEAU1@@Z$1?NetAdapterInitFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_NETADAPTER_INIT *,void (*)(_NETADAPTER_INIT *),&NetAdapterInitFree(_NETADAPTER_INIT *),wistd::integral_constant<unsigned __int64,0>,_NETADAPTER_INIT *,_NETADAPTER_INIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_NETADAPTER_INIT *,void (*)(_NETADAPTER_INIT *),&NetAdapterInitFree(_NETADAPTER_INIT *),wistd::integral_constant<unsigned __int64,0>,_NETADAPTER_INIT *,_NETADAPTER_INIT *,0,std::nullptr_t>>(void)
0x1400cbee8  mov     eax, esi
0x1400cbeea  lea     r11, [rsp+68h+var_28]
0x1400cbeef  mov     rbx, [r11+40h]
0x1400cbef3  mov     rbp, [r11+48h]
0x1400cbef7  mov     rsp, r11
0x1400cbefa  pop     r14
0x1400cbefc  pop     r13
0x1400cbefe  pop     r12
0x1400cbf00  pop     rdi
0x1400cbf01  pop     rsi
0x1400cbf02  retn
```
