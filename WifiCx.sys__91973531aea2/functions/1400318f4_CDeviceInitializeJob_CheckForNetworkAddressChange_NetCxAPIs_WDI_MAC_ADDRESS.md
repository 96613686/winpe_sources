# CDeviceInitializeJob::CheckForNetworkAddressChange_NetCxAPIs(_WDI_MAC_ADDRESS *)

- ea: `0x1400318f4`
- end: `0x140031b6c`
- name: `?CheckForNetworkAddressChange_NetCxAPIs@CDeviceInitializeJob@@AEAAHPEAU_WDI_MAC_ADDRESS@@@Z`
- size: `632`
- prototype: `__int64 __fastcall(CDeviceInitializeJob *__hidden this, struct _WDI_MAC_ADDRESS *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400317ac`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x14001eed0`
- `0x14001f8e4`
- `0x1400318f4`
- `0x1400687a4`
- `0x14006b8ac`
- `0x1400dfd00`
- `0x1400dfd40`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140031ab1`
- `ntoskrnl!RtlCompareMemory` at `0x140031ab1`

## pseudocode

```c
__int64 __fastcall CDeviceInitializeJob::CheckForNetworkAddressChange_NetCxAPIs(
        CAdapter **this,
        struct _WDI_MAC_ADDRESS *a2)
{
  struct _WDI_MAC_ADDRESS *v2; // rsi
  __int64 v4; // rdx
  struct CPort *PortFromNdisPortNumber; // rdi
  int v6; // r9d
  int v7; // r8d
  int v9; // eax
  int v10; // edx
  int v11; // r8d
  unsigned int v12; // ebx
  int v13; // r9d
  __int64 v14; // [rsp+40h] [rbp-40h] BYREF
  _OWORD Source2[2]; // [rsp+48h] [rbp-38h] BYREF
  __int16 v16; // [rsp+68h] [rbp-18h]
  int Source1; // [rsp+70h] [rbp-10h] BYREF
  __int16 v18; // [rsp+74h] [rbp-Ch]

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      21,
      (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids);
  }
  PortFromNdisPortNumber = CAdapter::GetPortFromNdisPortNumber(this[68], 0);
  if ( !PortFromNdisPortNumber )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = v4 + 22;
      v7 = v4 + 1;
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        v7,
        v6,
        (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids);
    }
    return 3221291014LL;
  }
  v14 = v4;
  v9 = ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, _QWORD, _QWORD, __int64 *))qword_140110C48)(
         NetDriverGlobals,
         *((_QWORD *)PortFromNdisPortNumber + 11),
         0,
         &v14);
  v12 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = 23;
LABEL_13:
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        v13,
        (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
        *((_QWORD *)PortFromNdisPortNumber + 11),
        v9);
      goto LABEL_14;
    }
    goto LABEL_14;
  }
  v16 = 0;
  memset(Source2, 0, sizeof(Source2));
  v9 = ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, __int64, _OWORD *))qword_140110D08)(NetDriverGlobals, v14, Source2);
  v12 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = 24;
      goto LABEL_13;
    }
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<NETCONFIGURATION__ *,void (*)(NETCONFIGURATION__ *),&void NetConfigurationClose(NETCONFIGURATION__ *),wistd::integral_constant<unsigned __int64,0>,NETCONFIGURATION__ *,NETCONFIGURATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<NETCONFIGURATION__ *,void (*)(NETCONFIGURATION__ *),&void NetConfigurationClose(NETCONFIGURATION__ *),wistd::integral_constant<unsigned __int64,0>,NETCONFIGURATION__ *,NETCONFIGURATION__ *,0,std::nullptr_t>>(&v14);
    return v12;
  }
  if ( LOWORD(Source2[0]) != 6 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        1,
        25,
        (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
        Source2[0]);
    }
LABEL_25:
    wil::details::unique_storage<wil::details::resource_policy<NETCONFIGURATION__ *,void (*)(NETCONFIGURATION__ *),&void NetConfigurationClose(NETCONFIGURATION__ *),wistd::integral_constant<unsigned __int64,0>,NETCONFIGURATION__ *,NETCONFIGURATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<NETCONFIGURATION__ *,void (*)(NETCONFIGURATION__ *),&void NetConfigurationClose(NETCONFIGURATION__ *),wistd::integral_constant<unsigned __int64,0>,NETCONFIGURATION__ *,NETCONFIGURATION__ *,0,std::nullptr_t>>(&v14);
    return 3221225485LL;
  }
  Source1 = 0;
  v18 = 0;
  if ( (BYTE2(Source2[0]) & 3) != 2 || RtlCompareMemory(&Source1, (char *)Source2 + 2, 6u) == 6 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF__MAC_(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        26,
        (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
        (__int64)Source2 + 2);
    }
    goto LABEL_25;
  }
  *(_DWORD *)v2->Address = *(_DWORD *)((char *)Source2 + 2);
  *(_WORD *)&v2->Address[4] = WORD3(Source2[0]);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 4;
    WPP_RECORDER_SF__MAC_(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      v11,
      27,
      (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
      (__int64)Source2 + 2);
  }
  wil::details::unique_storage<wil::details::resource_policy<NETCONFIGURATION__ *,void (*)(NETCONFIGURATION__ *),&void NetConfigurationClose(NETCONFIGURATION__ *),wistd::integral_constant<unsigned __int64,0>,NETCONFIGURATION__ *,NETCONFIGURATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<NETCONFIGURATION__ *,void (*)(NETCONFIGURATION__ *),&void NetConfigurationClose(NETCONFIGURATION__ *),wistd::integral_constant<unsigned __int64,0>,NETCONFIGURATION__ *,NETCONFIGURATION__ *,0,std::nullptr_t>>(&v14);
  return 0;
}

```

## disassembly

```asm
0x1400318f4  mov     [rsp-28h+arg_10], rbx
0x1400318f9  push    rbp
0x1400318fa  push    rsi
0x1400318fb  push    rdi
0x1400318fc  push    r12
0x1400318fe  push    r15
0x140031900  mov     rbp, rsp
0x140031903  sub     rsp, 80h
0x14003190a  mov     rax, cs:__security_cookie
0x140031911  xor     rax, rsp
0x140031914  mov     [rbp+var_8], rax
0x140031918  mov     rsi, rdx
0x14003191b  mov     rbx, rcx
0x14003191e  lea     r15, WPP_RECORDER_INITIALIZED
0x140031925  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14003192c  lea     r12, WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids
0x140031933  jz      short loc_140031956
0x140031935  mov     rcx, cs:WPP_GLOBAL_Control
0x14003193c  mov     r9d, 15h
0x140031942  mov     dl, 4
0x140031944  mov     [rsp+80h+var_60], r12
0x140031949  mov     rcx, [rcx+40h]
0x14003194d  lea     r8d, [r9-14h]
0x140031951  call    WPP_RECORDER_SF_
0x140031956  mov     rcx, [rbx+220h]; this
0x14003195d  xor     edx, edx; unsigned int
0x14003195f  call    ?GetPortFromNdisPortNumber@CAdapter@@QEBAPEAVCPort@@K@Z; CAdapter::GetPortFromNdisPortNumber(ulong)
0x140031964  mov     rdi, rax
0x140031967  test    rax, rax
0x14003196a  jnz     short loc_14003199E
0x14003196c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140031973  jz      short loc_140031994
0x140031975  mov     rcx, cs:WPP_GLOBAL_Control
0x14003197c  lea     r9d, [rdx+16h]
0x140031980  lea     r8d, [rdx+1]
0x140031984  mov     [rsp+80h+var_60], r12
0x140031989  mov     dl, 2
0x14003198b  mov     rcx, [rcx+40h]
0x14003198f  call    WPP_RECORDER_SF_
0x140031994  mov     eax, 0C0010006h
0x140031999  jmp     loc_140031B48
0x14003199e  mov     rax, cs:qword_140110C48
0x1400319a5  lea     r9, [rbp+var_40]
0x1400319a9  mov     rcx, cs:NetDriverGlobals
0x1400319b0  xor     r8d, r8d
0x1400319b3  mov     [rbp+var_40], rdx
0x1400319b7  mov     rdx, [rdi+58h]
0x1400319bb  call    _guard_dispatch_icall
0x1400319c0  mov     ebx, eax
0x1400319c2  test    eax, eax
0x1400319c4  jns     short loc_1400319D7
0x1400319c6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400319cd  jz      short loc_140031A3C
0x1400319cf  mov     r9d, 17h
0x1400319d5  jmp     short loc_140031A18
0x1400319d7  mov     rdx, [rbp+var_40]
0x1400319db  lea     r8, [rbp+Source2]
0x1400319df  mov     rcx, cs:NetDriverGlobals
0x1400319e6  xor     eax, eax
0x1400319e8  xorps   xmm0, xmm0
0x1400319eb  mov     [rbp+var_18], ax
0x1400319ef  mov     rax, cs:qword_140110D08
0x1400319f6  movups  [rbp+Source2], xmm0
0x1400319fa  movups  [rbp+var_28], xmm0
0x1400319fe  call    _guard_dispatch_icall
0x140031a03  mov     ebx, eax
0x140031a05  test    eax, eax
0x140031a07  jns     short loc_140031A4C
0x140031a09  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140031a10  jz      short loc_140031A3C
0x140031a12  mov     r9d, 18h
0x140031a18  mov     rcx, [rdi+58h]
0x140031a1c  mov     dl, 2
0x140031a1e  mov     [rsp+80h+var_50], eax
0x140031a22  mov     [rsp+80h+var_58], rcx
0x140031a27  mov     rcx, cs:WPP_GLOBAL_Control
0x140031a2e  mov     [rsp+80h+var_60], r12
0x140031a33  mov     rcx, [rcx+40h]
0x140031a37  call    WPP_RECORDER_SF_qD
0x140031a3c  lea     rcx, [rbp+var_40]
0x140031a40  call    ??1?$unique_storage@U?$resource_policy@PEAUNETCONFIGURATION__@@P6AXPEAU1@@Z$1?NetConfigurationClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<NETCONFIGURATION__ *,void (*)(NETCONFIGURATION__ *),&NetConfigurationClose(NETCONFIGURATION__ *),wistd::integral_constant<unsigned __int64,0>,NETCONFIGURATION__ *,NETCONFIGURATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<NETCONFIGURATION__ *,void (*)(NETCONFIGURATION__ *),&NetConfigurationClose(NETCONFIGURATION__ *),wistd::integral_constant<unsigned __int64,0>,NETCONFIGURATION__ *,NETCONFIGURATION__ *,0,std::nullptr_t>>(void)
0x140031a45  mov     eax, ebx
0x140031a47  jmp     loc_140031B48
0x140031a4c  mov     ebx, 6
0x140031a51  cmp     word ptr [rbp+Source2], bx
0x140031a55  jz      short loc_140031A90
0x140031a57  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140031a5e  jz      loc_140031B3A
0x140031a64  mov     rcx, cs:WPP_GLOBAL_Control
0x140031a6b  lea     r9d, [rbx+13h]
0x140031a6f  movzx   eax, word ptr [rbp+Source2]
0x140031a73  lea     r8d, [rbx-5]
0x140031a77  mov     dword ptr [rsp+80h+var_58], eax
0x140031a7b  mov     dl, 2
0x140031a7d  mov     [rsp+80h+var_60], r12
0x140031a82  mov     rcx, [rcx+40h]
0x140031a86  call    WPP_RECORDER_SF_d
0x140031a8b  jmp     loc_140031B3A
0x140031a90  mov     al, byte ptr [rbp+Source2+2]
0x140031a93  and     al, 3
0x140031a95  mov     [rbp+Source1], 0
0x140031a9c  mov     [rbp+var_C], 0
0x140031aa2  cmp     al, 2
0x140031aa4  jnz     short loc_140031B0B
0x140031aa6  mov     r8, rbx; Length
0x140031aa9  lea     rdx, [rbp+Source2+2]; Source2
0x140031aad  lea     rcx, [rbp+Source1]; Source1
0x140031ab1  call    cs:__imp_RtlCompareMemory
0x140031ab8  nop     dword ptr [rax+rax+00h]
0x140031abd  cmp     rax, rbx
0x140031ac0  jz      short loc_140031B0B
0x140031ac2  mov     eax, dword ptr [rbp+Source2+2]
0x140031ac5  mov     [rsi], eax
0x140031ac7  movzx   eax, word ptr [rbp+Source2+6]
0x140031acb  mov     [rsi+4], ax
0x140031acf  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140031ad6  jz      short loc_140031AFE
0x140031ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x140031adf  lea     rax, [rbp+Source2+2]
0x140031ae3  mov     [rsp+80h+var_58], rax
0x140031ae8  mov     r9d, 1Bh
0x140031aee  mov     dl, 4
0x140031af0  mov     [rsp+80h+var_60], r12
0x140031af5  mov     rcx, [rcx+40h]
0x140031af9  call    WPP_RECORDER_SF__MAC_
0x140031afe  lea     rcx, [rbp+var_40]
0x140031b02  call    ??1?$unique_storage@U?$resource_policy@PEAUNETCONFIGURATION__@@P6AXPEAU1@@Z$1?NetConfigurationClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<NETCONFIGURATION__ *,void (*)(NETCONFIGURATION__ *),&NetConfigurationClose(NETCONFIGURATION__ *),wistd::integral_constant<unsigned __int64,0>,NETCONFIGURATION__ *,NETCONFIGURATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<NETCONFIGURATION__ *,void (*)(NETCONFIGURATION__ *),&NetConfigurationClose(NETCONFIGURATION__ *),wistd::integral_constant<unsigned __int64,0>,NETCONFIGURATION__ *,NETCONFIGURATION__ *,0,std::nullptr_t>>(void)
0x140031b07  xor     eax, eax
0x140031b09  jmp     short loc_140031B48
0x140031b0b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140031b12  jz      short loc_140031B3A
0x140031b14  mov     rcx, cs:WPP_GLOBAL_Control
0x140031b1b  lea     rax, [rbp+Source2+2]
0x140031b1f  mov     [rsp+80h+var_58], rax
0x140031b24  mov     r9d, 1Ah
0x140031b2a  mov     dl, 2
0x140031b2c  mov     [rsp+80h+var_60], r12
0x140031b31  mov     rcx, [rcx+40h]
0x140031b35  call    WPP_RECORDER_SF__MAC_
0x140031b3a  lea     rcx, [rbp+var_40]
0x140031b3e  call    ??1?$unique_storage@U?$resource_policy@PEAUNETCONFIGURATION__@@P6AXPEAU1@@Z$1?NetConfigurationClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<NETCONFIGURATION__ *,void (*)(NETCONFIGURATION__ *),&NetConfigurationClose(NETCONFIGURATION__ *),wistd::integral_constant<unsigned __int64,0>,NETCONFIGURATION__ *,NETCONFIGURATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<NETCONFIGURATION__ *,void (*)(NETCONFIGURATION__ *),&NetConfigurationClose(NETCONFIGURATION__ *),wistd::integral_constant<unsigned __int64,0>,NETCONFIGURATION__ *,NETCONFIGURATION__ *,0,std::nullptr_t>>(void)
0x140031b43  mov     eax, 0C000000Dh
0x140031b48  mov     rcx, [rbp+var_8]
0x140031b4c  xor     rcx, rsp; StackCookie
0x140031b4f  call    __security_check_cookie
0x140031b54  mov     rbx, [rsp+80h+arg_10]
0x140031b5c  add     rsp, 80h
0x140031b63  pop     r15
0x140031b65  pop     r12
0x140031b67  pop     rdi
0x140031b68  pop     rsi
0x140031b69  pop     rbp
0x140031b6a  retn
```
