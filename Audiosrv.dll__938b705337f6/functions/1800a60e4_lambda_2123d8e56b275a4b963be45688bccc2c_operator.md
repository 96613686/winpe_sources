# _lambda_2123d8e56b275a4b963be45688bccc2c_::operator()

- ea: `0x1800a60e4`
- end: `0x1800a63b6`
- name: `_lambda_2123d8e56b275a4b963be45688bccc2c_::operator()`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ffa90`

## callees

- `0x18000accc`
- `0x1800126bc`
- `0x1800a60e4`
- `0x1800a63bc`
- `0x1800a6514`
- `0x1800a6700`
- `0x1800a67d0`
- `0x1800cdfbc`
- `0x1800cf8c0`
- `0x1800d0740`
- `0x1800ff150`
- `0x1800ff770`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a61c7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a629f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a62c4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a637f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a61c7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a629f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a62c4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a637f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800a6264`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800a6264`

## string_xrefs

- `0x1800a6149`: `avcore\audiocore\server\audiosrv\dll\btbroadcastprovider.cpp`
- `0x1800a6201`: `avcore\audiocore\server\audiosrv\dll\btbroadcastprovider.cpp`
- `0x1800a62ae`: `avcore\audiocore\server\audiosrv\dll\btbroadcastprovider.cpp`
- `0x1800a62ed`: `avcore\audiocore\server\audiosrv\dll\btbroadcastprovider.cpp`
- `0x1800a6341`: `avcore\audiocore\server\audiosrv\dll\btbroadcastprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall lambda_2123d8e56b275a4b963be45688bccc2c_::operator()(__int64 a1)
{
  const unsigned __int16 *v2; // rdx
  int EndpointProperties; // eax
  unsigned int v4; // ebx
  struct IPropertyStore *v6; // r8
  BluetoothBroadcastProvider *v7; // rcx
  const unsigned __int16 *v8; // rdx
  int v9; // eax
  char v10; // r15
  __int64 i; // r14
  HRESULT v12; // eax
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  int v15; // eax
  int v16; // [rsp+20h] [rbp-60h] BYREF
  struct IPropertyStore *v17; // [rsp+28h] [rbp-58h] BYREF
  __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 v18; // [rsp+30h] [rbp-50h] BYREF
  PROPVARIANT pvar[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v20; // [rsp+48h] [rbp-38h]
  __int128 Buf2; // [rsp+50h] [rbp-30h] BYREF
  GUID pclsid; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  LOBYTE(v16) = 0;
  v18 = eRender;
  v17 = 0;
  v2 = *(const unsigned __int16 **)(a1 + 8);
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(const unsigned __int16 **)v2;
  EndpointProperties = BluetoothBroadcastProvider::GetEndpointProperties(
                         (BluetoothBroadcastProvider *)a1,
                         v2,
                         &v17,
                         &v18);
  v4 = EndpointProperties;
  if ( EndpointProperties < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x110,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btbroadcastprovider.cpp",
      (const char *)(unsigned int)EndpointProperties,
      v16);
    if ( v17 )
      ((void (__fastcall *)(struct IPropertyStore *))v17->lpVtbl->Release)(v17);
    return v4;
  }
  if ( v18 )
  {
    v4 = 0;
LABEL_39:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v17);
    return v4;
  }
  *(_OWORD *)pvar = 0;
  v20 = 0;
  ((void (__fastcall *)(struct IPropertyStore *, void *, PROPVARIANT *))v17->lpVtbl->GetValue)(
    v17,
    &PKEY_Endpoint_IsBluetooth,
    pvar);
  if ( LOWORD(pvar[0]) == 11 && LOWORD(pvar[1]) == 0xFFFF )
  {
    PropVariantClear(pvar);
    v7 = *(BluetoothBroadcastProvider **)(a1 + 32);
    v8 = *(const unsigned __int16 **)(a1 + 8);
    if ( *(_BYTE *)(a1 + 24) )
    {
      if ( *((_QWORD *)v8 + 3) > 7u )
        v8 = *(const unsigned __int16 **)v8;
      v9 = BluetoothBroadcastProvider::OnBluetoothRenderEndpointActivation(v7, v8, v17, (bool *)&v16);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x110,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btbroadcastprovider.cpp",
          (const char *)(unsigned int)v9,
          v16);
      v10 = 0;
      *(_OWORD *)pvar = 0;
      v20 = 0;
      ((void (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, PROPVARIANT *))v17->lpVtbl->GetValue)(
        v17,
        &PKEY_Multicast_CompatibleProviders,
        pvar);
      if ( LOWORD(pvar[0]) == 4127 )
      {
        for ( i = 0; (unsigned int)i < LODWORD(pvar[1]); i = (unsigned int)(i + 1) )
        {
          pclsid = 0;
          v12 = CLSIDFromString(*(LPCOLESTR *)(v20 + 8 * i), &pclsid);
          v4 = v12;
          if ( v12 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x110,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btbroadcastprovider.cpp",
              (const char *)(unsigned int)v12,
              v16);
            PropVariantClear(pvar);
            goto LABEL_39;
          }
          Buf2 = BLUETOOTH_AUDIO_BROADCAST_PROVIDER;
          if ( !memcmp_0(&pclsid, &Buf2, 0x10u) )
          {
            v10 = 1;
            break;
          }
        }
      }
      PropVariantClear(pvar);
    }
    else
    {
      if ( *((_QWORD *)v8 + 3) > 7u )
        v8 = *(const unsigned __int16 **)v8;
      v13 = BluetoothBroadcastProvider::OnBluetoothRenderEndpointInactivation(v7, v8, v6, (bool *)&v16);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x110,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btbroadcastprovider.cpp",
          (const char *)(unsigned int)v13,
          v16);
      v10 = 0;
    }
    v14 = *(const unsigned __int16 **)(a1 + 8);
    if ( v10 )
    {
      if ( *((_QWORD *)v14 + 3) > 7u )
        v14 = *(const unsigned __int16 **)v14;
      v15 = BluetoothBroadcastProvider::AddEndpointToCompatibleList(
              *(BluetoothBroadcastProvider **)a1,
              v14,
              (bool *)&v16);
    }
    else
    {
      if ( *((_QWORD *)v14 + 3) > 7u )
        v14 = *(const unsigned __int16 **)v14;
      v15 = BluetoothBroadcastProvider::RemoveEndpointFromCompatibleList(
              *(BluetoothBroadcastProvider **)a1,
              v14,
              (bool *)&v16);
    }
    v4 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x110,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\btbroadcastprovider.cpp",
        (const char *)(unsigned int)v15,
        v16);
      goto LABEL_39;
    }
    if ( (_BYTE)v16 && *(_BYTE *)(*(_QWORD *)a1 + 16LL) )
      BluetoothBroadcastProvider::NotifyMulticastManager(*(BluetoothBroadcastProvider **)a1);
  }
  else
  {
    PropVariantClear(pvar);
  }
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v17);
  return 0;
}

```

## disassembly

```asm
0x1800a60e4  mov     [rsp-18h+arg_8], rbx
0x1800a60e9  mov     [rsp-18h+arg_10], rsi
0x1800a60ee  push    rbp
0x1800a60ef  push    r14
0x1800a60f1  push    r15
0x1800a60f3  mov     rbp, rsp
0x1800a60f6  sub     rsp, 80h
0x1800a60fd  mov     rax, cs:__security_cookie
0x1800a6104  xor     rax, rsp
0x1800a6107  mov     [rbp+var_10], rax
0x1800a610b  mov     rsi, rcx
0x1800a610e  mov     byte ptr [rbp+var_60], 0
0x1800a6112  mov     [rbp+var_50], 0
0x1800a6119  mov     [rbp+var_58], 0
0x1800a6121  mov     rdx, [rcx+8]
0x1800a6125  cmp     qword ptr [rdx+18h], 7
0x1800a612a  jbe     short loc_1800A612F
0x1800a612c  mov     rdx, [rdx]; unsigned __int16 *
0x1800a612f  lea     r9, [rbp+var_50]; enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 *
0x1800a6133  lea     r8, [rbp+var_58]; struct IPropertyStore **
0x1800a6137  call    ?GetEndpointProperties@BluetoothBroadcastProvider@@AEAAJPEBGPEAPEAUIPropertyStore@@PEAW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@@Z; BluetoothBroadcastProvider::GetEndpointProperties(ushort const *,IPropertyStore * *,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 *)
0x1800a613c  mov     ebx, eax
0x1800a613e  test    eax, eax
0x1800a6140  jns     short loc_1800A6178
0x1800a6142  mov     rcx, [rbp+18h]; this
0x1800a6146  mov     r9d, eax; char *
0x1800a6149  lea     r8, aAvcoreAudiocor_29; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800a6150  mov     edx, 110h; void *
0x1800a6155  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a615a  nop
0x1800a615b  mov     rcx, [rbp+var_58]
0x1800a615f  test    rcx, rcx
0x1800a6162  jz      short loc_1800A6171
0x1800a6164  mov     rax, [rcx]
0x1800a6167  mov     rax, [rax+10h]
0x1800a616b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6170  nop
0x1800a6171  mov     eax, ebx
0x1800a6173  jmp     loc_1800A6391
0x1800a6178  cmp     [rbp+var_50], 0
0x1800a617c  jz      short loc_1800A6185
0x1800a617e  xor     ebx, ebx
0x1800a6180  jmp     loc_1800A6357
0x1800a6185  xorps   xmm0, xmm0
0x1800a6188  xor     eax, eax
0x1800a618a  movups  xmmword ptr [rbp+pvar], xmm0
0x1800a618e  mov     [rbp+var_38], rax
0x1800a6192  mov     rcx, [rbp+var_58]
0x1800a6196  mov     rax, [rcx]
0x1800a6199  lea     r8, [rbp+pvar]
0x1800a619d  lea     rdx, PKEY_Endpoint_IsBluetooth
0x1800a61a4  mov     rax, [rax+28h]
0x1800a61a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a61ad  cmp     word ptr [rbp+pvar], 0Bh
0x1800a61b2  jnz     loc_1800A637B
0x1800a61b8  cmp     word ptr [rbp+pvar+8], 0FFFFh
0x1800a61bd  jnz     loc_1800A637B
0x1800a61c3  lea     rcx, [rbp+pvar]; pvar
0x1800a61c7  call    cs:__imp_PropVariantClear
0x1800a61cd  mov     rcx, [rsi+20h]; this
0x1800a61d1  mov     rdx, [rsi+8]
0x1800a61d5  cmp     byte ptr [rsi+18h], 0
0x1800a61d9  jz      loc_1800A62CF
0x1800a61df  cmp     qword ptr [rdx+18h], 7
0x1800a61e4  jbe     short loc_1800A61E9
0x1800a61e6  mov     rdx, [rdx]; unsigned __int16 *
0x1800a61e9  lea     r9, [rbp+var_60]; bool *
0x1800a61ed  mov     r8, [rbp+var_58]; struct IPropertyStore *
0x1800a61f1  call    ?OnBluetoothRenderEndpointActivation@BluetoothBroadcastProvider@@AEAAJPEBGPEAUIPropertyStore@@PEA_N@Z; BluetoothBroadcastProvider::OnBluetoothRenderEndpointActivation(ushort const *,IPropertyStore *,bool *)
0x1800a61f6  mov     rcx, [rbp+18h]; this
0x1800a61fa  test    eax, eax
0x1800a61fc  jns     short loc_1800A6212
0x1800a61fe  mov     r9d, eax; char *
0x1800a6201  lea     r8, aAvcoreAudiocor_29; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800a6208  mov     edx, 110h; void *
0x1800a620d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a6212  xor     r15b, r15b
0x1800a6215  xorps   xmm0, xmm0
0x1800a6218  xor     eax, eax
0x1800a621a  movups  xmmword ptr [rbp+pvar], xmm0
0x1800a621e  mov     [rbp+var_38], rax
0x1800a6222  mov     rcx, [rbp+var_58]
0x1800a6226  mov     rax, [rcx]
0x1800a6229  lea     r8, [rbp+pvar]
0x1800a622d  lea     rdx, PKEY_Multicast_CompatibleProviders
0x1800a6234  mov     rax, [rax+28h]
0x1800a6238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a623d  mov     eax, 101Fh
0x1800a6242  cmp     word ptr [rbp+pvar], ax
0x1800a6246  jnz     short loc_1800A629B
0x1800a6248  xor     r14d, r14d
0x1800a624b  cmp     r14d, dword ptr [rbp+pvar+8]
0x1800a624f  jnb     short loc_1800A629B
0x1800a6251  xorps   xmm0, xmm0
0x1800a6254  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x1800a6258  lea     rdx, [rbp+pclsid]; pclsid
0x1800a625c  mov     rcx, [rbp+var_38]
0x1800a6260  mov     rcx, [rcx+r14*8]; lpsz
0x1800a6264  call    cs:__imp_CLSIDFromString
0x1800a626a  mov     ebx, eax
0x1800a626c  test    eax, eax
0x1800a626e  js      short loc_1800A62A7
0x1800a6270  movups  xmm0, cs:BLUETOOTH_AUDIO_BROADCAST_PROVIDER
0x1800a6277  movdqu  [rbp+Buf2], xmm0
0x1800a627c  mov     r8d, 10h; Size
0x1800a6282  lea     rdx, [rbp+Buf2]; Buf2
0x1800a6286  lea     rcx, [rbp+pclsid]; Buf1
0x1800a628a  call    memcmp_0
0x1800a628f  test    eax, eax
0x1800a6291  jz      short loc_1800A6298
0x1800a6293  inc     r14d
0x1800a6296  jmp     short loc_1800A624B
0x1800a6298  mov     r15b, 1
0x1800a629b  lea     rcx, [rbp+pvar]; pvar
0x1800a629f  call    cs:__imp_PropVariantClear
0x1800a62a5  jmp     short loc_1800A6301
0x1800a62a7  mov     rcx, [rbp+18h]; this
0x1800a62ab  mov     r9d, eax; char *
0x1800a62ae  lea     r8, aAvcoreAudiocor_29; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800a62b5  mov     edx, 110h; void *
0x1800a62ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a62bf  nop
0x1800a62c0  lea     rcx, [rbp+pvar]; pvar
0x1800a62c4  call    cs:__imp_PropVariantClear
0x1800a62ca  jmp     loc_1800A6357
0x1800a62cf  cmp     qword ptr [rdx+18h], 7
0x1800a62d4  jbe     short loc_1800A62D9
0x1800a62d6  mov     rdx, [rdx]; unsigned __int16 *
0x1800a62d9  lea     r9, [rbp+var_60]; bool *
0x1800a62dd  call    ?OnBluetoothRenderEndpointInactivation@BluetoothBroadcastProvider@@AEAAJPEBGPEAUIPropertyStore@@PEA_N@Z; BluetoothBroadcastProvider::OnBluetoothRenderEndpointInactivation(ushort const *,IPropertyStore *,bool *)
0x1800a62e2  mov     rcx, [rbp+18h]; this
0x1800a62e6  test    eax, eax
0x1800a62e8  jns     short loc_1800A62FE
0x1800a62ea  mov     r9d, eax; char *
0x1800a62ed  lea     r8, aAvcoreAudiocor_29; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800a62f4  mov     edx, 110h; void *
0x1800a62f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a62fe  xor     r15b, r15b
0x1800a6301  mov     rdx, [rsi+8]
0x1800a6305  test    r15b, r15b
0x1800a6308  jz      short loc_1800A6322
0x1800a630a  cmp     qword ptr [rdx+18h], 7
0x1800a630f  jbe     short loc_1800A6314
0x1800a6311  mov     rdx, [rdx]; unsigned __int16 *
0x1800a6314  lea     r8, [rbp+var_60]; bool *
0x1800a6318  mov     rcx, [rsi]; this
0x1800a631b  call    ?AddEndpointToCompatibleList@BluetoothBroadcastProvider@@AEAAJPEBGPEA_N@Z; BluetoothBroadcastProvider::AddEndpointToCompatibleList(ushort const *,bool *)
0x1800a6320  jmp     short loc_1800A6338
0x1800a6322  cmp     qword ptr [rdx+18h], 7
0x1800a6327  jbe     short loc_1800A632C
0x1800a6329  mov     rdx, [rdx]; unsigned __int16 *
0x1800a632c  lea     r8, [rbp+var_60]; bool *
0x1800a6330  mov     rcx, [rsi]; this
0x1800a6333  call    ?RemoveEndpointFromCompatibleList@BluetoothBroadcastProvider@@AEAAJPEBGPEA_N@Z; BluetoothBroadcastProvider::RemoveEndpointFromCompatibleList(ushort const *,bool *)
0x1800a6338  test    eax, eax
0x1800a633a  mov     ebx, eax
0x1800a633c  jns     short loc_1800A6365
0x1800a633e  mov     r9d, eax; char *
0x1800a6341  lea     r8, aAvcoreAudiocor_29; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800a6348  mov     edx, 110h; void *
0x1800a634d  mov     rcx, [rbp+18h]; this
0x1800a6351  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6356  nop
0x1800a6357  lea     rcx, [rbp+var_58]
0x1800a635b  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800a6360  jmp     loc_1800A6171
0x1800a6365  cmp     byte ptr [rbp+var_60], 0
0x1800a6369  jz      short loc_1800A6386
0x1800a636b  mov     rcx, [rsi]; this
0x1800a636e  cmp     byte ptr [rcx+10h], 0
0x1800a6372  jz      short loc_1800A6386
0x1800a6374  call    ?NotifyMulticastManager@BluetoothBroadcastProvider@@AEAAXXZ; BluetoothBroadcastProvider::NotifyMulticastManager(void)
0x1800a6379  jmp     short loc_1800A6386
0x1800a637b  lea     rcx, [rbp+pvar]; pvar
0x1800a637f  call    cs:__imp_PropVariantClear
0x1800a6385  nop
0x1800a6386  lea     rcx, [rbp+var_58]
0x1800a638a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800a638f  xor     eax, eax
0x1800a6391  mov     rcx, [rbp+var_10]
0x1800a6395  xor     rcx, rsp; StackCookie
0x1800a6398  call    __security_check_cookie
0x1800a639d  lea     r11, [rsp+80h+var_s0]
0x1800a63a5  mov     rbx, [r11+28h]
0x1800a63a9  mov     rsi, [r11+30h]
0x1800a63ad  mov     rsp, r11
0x1800a63b0  pop     r15
0x1800a63b2  pop     r14
0x1800a63b4  pop     rbp
0x1800a63b5  retn
```
