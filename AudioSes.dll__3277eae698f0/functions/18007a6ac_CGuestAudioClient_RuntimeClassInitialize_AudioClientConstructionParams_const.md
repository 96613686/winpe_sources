# CGuestAudioClient::RuntimeClassInitialize(AudioClientConstructionParams const *)

- ea: `0x18007a6ac`
- end: `0x18007aabc`
- name: `?RuntimeClassInitialize@CGuestAudioClient@@QEAAJPEBUAudioClientConstructionParams@@@Z`
- size: `1040`
- prototype: `__int64 __fastcall(CGuestAudioClient *__hidden this, const struct AudioClientConstructionParams *)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180099174`

## callees

- `0x180007f00`
- `0x18000cae4`
- `0x18000cd10`
- `0x18000d11c`
- `0x18000f72c`
- `0x180010a90`
- `0x18001550c`
- `0x180025a04`
- `0x180025a3c`
- `0x18003346c`
- `0x18004d8a8`
- `0x18007a6ac`
- `0x18008323c`
- `0x180087e80`
- `0x180088ce8`
- `0x18008ac99`
- `0x1800929a0`
- `0x180095fb8`
- `0x180096764`
- `0x1800994e8`
- `0x1800aa59c`
- `0x1800aa5c4`
- `0x1800aaa14`
- `0x1800af1c8`
- `0x1800b0470`
- `0x1800b17f0`
- `0x1800b183c`
- `0x18011ddd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a89e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a975`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aa81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a89e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a975`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aa81`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CGuestAudioClient::RuntimeClassInitialize(CAudioClient **this, const unsigned __int16 **a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  struct XvmEndpointId *v6; // rdi
  int v7; // eax
  __int64 v8; // r9
  __int64 v9; // rdx
  struct XvmEndpointId *v10; // rbx
  struct CGuestXvmAudioObject *RootProxyAudioObjectActivator; // rdi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // edi
  void *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  int MediaNotificationCallback; // eax
  __int64 v17; // rdx
  unsigned __int64 v18; // r9
  void *v19; // rcx
  CAudioClient *v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rax
  void *v23; // rcx
  int v25; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  struct XvmEndpointId *v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v29; // [rsp+48h] [rbp-B8h] BYREF
  int v30[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID *p_pv; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  char v33; // [rsp+68h] [rbp-98h]
  _BYTE v34[1568]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v35[1568]; // [rsp+690h] [rbp+590h] BYREF
  _BYTE v36[64]; // [rsp+CB0h] [rbp+BB0h] BYREF
  int Src; // [rsp+CF0h] [rbp+BF0h] BYREF
  __int64 v38; // [rsp+CF4h] [rbp+BF4h]
  int v39; // [rsp+CFCh] [rbp+BFCh]
  int v40; // [rsp+D00h] [rbp+C00h]
  _BYTE v41[1548]; // [rsp+D04h] [rbp+C04h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1348h] [rbp+1248h]

  Src = 2;
  v38 = 1;
  v39 = 0;
  v40 = 135;
  memset_0(v41, 0, 0x600u);
  v28 = 0;
  v4 = XvmActivateProxyAudioObject::CastTo<XvmActivateClient2>(&Src, &v28);
  if ( v4 >= 0 )
  {
    v6 = v28;
    v4 = CopyToXvmEndpointId(a2[3], v28);
    if ( v4 < 0 )
    {
      v5 = 92;
      goto LABEL_3;
    }
    *((GUID *)v6 + 7) = GUID_00000000_0000_0000_0000_000000000000;
    v28 = 0;
    v7 = Microsoft::WRL::Details::MakeAndInitialize<CAudioClient,CAudioClient,>(&v28);
    v4 = v7;
    if ( v7 < 0 )
    {
      v8 = (unsigned int)v7;
      v9 = 97;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientcore.cpp",
        (const char *)v8,
        v25);
LABEL_37:
      wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v28);
      return (unsigned int)v4;
    }
    v10 = v28;
    *((_OWORD *)v6 + 8) = *((_OWORD *)v28 + 33);
    *((_DWORD *)v6 + 36) = *((_DWORD *)v10 + 104);
    RootProxyAudioObjectActivator = GetRootProxyAudioObjectActivator();
    if ( !RootProxyAudioObjectActivator )
    {
      v4 = -2147418113;
      v8 = 2147549183LL;
      v9 = 105;
      goto LABEL_10;
    }
    pv = 0;
    *(_QWORD *)v30 = 0;
    p_pv = &pv;
    v32 = 0;
    v33 = 1;
    memcpy_0(v34, &Src, 0x614u);
    memcpy_0(v35, v34, 0x614u);
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(RootProxyAudioObjectActivator, *((unsigned int *)RootProxyAudioObjectActivator + 12), v35, &v32);
    wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientcore.cpp",
        (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
        (int)v30);
LABEL_13:
      v13 = pv;
      pv = 0;
      if ( v13 )
        CoTaskMemFree(v13);
      v4 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
      goto LABEL_37;
    }
    v27 = 0;
    v29 = &v27;
    v14 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v29);
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = Microsoft::WRL::AsWeak<CGuestAudioClient>(this, v14);
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      v15 = 112;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientcore.cpp",
        (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
        (int)v30);
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v27);
      goto LABEL_13;
    }
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this + 182, 0);
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      v15 = 114;
      goto LABEL_18;
    }
    wil::com_ptr_t<CAudioClient,wil::err_returncode_policy>::operator=(this + 19, v10);
    MediaNotificationCallback = CAudioClient::FinishConstruction(
                                  this[19],
                                  (const struct AudioClientConstructionParams *)a2);
    v4 = MediaNotificationCallback;
    if ( MediaNotificationCallback >= 0 )
    {
      v20 = this[19];
      wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset(this + 7);
      MediaNotificationCallback = CAudioClient::GetMediaNotificationCallback(v20, this + 7);
      v4 = MediaNotificationCallback;
      if ( MediaNotificationCallback >= 0 )
      {
        MediaNotificationCallback = CGuestXvmAudioObject::Initialize(
                                      (CGuestXvmAudioObject *)(this + 3),
                                      *(_DWORD *)(*(_QWORD *)v30 + 12LL),
                                      (struct Microsoft::WRL::WeakRef *)&v27,
                                      0);
        v4 = MediaNotificationCallback;
        if ( MediaNotificationCallback >= 0 )
        {
          v21 = lambda_3db8bcd5c969fae5248b7dc465e144ed_::_lambda_3db8bcd5c969fae5248b7dc465e144ed_(&v29, this);
          std::function_void___cdecl_void__::function_void___cdecl_void____lambda_129c027699bfc4538fa71b6704031c9e__0_(
            v36,
            v21);
          v4 = CGuestXvmAudioObject::TryRegisterAppSuspensionHandler(this + 3, v36);
          std::_Func_class<void,>::_Tidy(v36);
          if ( v4 >= 0 )
          {
            v22 = lambda_3db8bcd5c969fae5248b7dc465e144ed_::_lambda_3db8bcd5c969fae5248b7dc465e144ed_(&v29, this);
            std::function_void___cdecl_void__::function_void___cdecl_void____lambda_a2cbb55ad9eed09ebede9af5196b3771__0_(
              v36,
              v22);
            v4 = CGuestXvmAudioObject::TryRegisterAppResumptionHandler(this + 3, v36);
            std::_Func_class<void,>::_Tidy(v36);
            if ( v4 >= 0 )
            {
              Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v27);
              v23 = pv;
              pv = 0;
              if ( v23 )
                CoTaskMemFree(v23);
              v4 = 0;
              goto LABEL_37;
            }
            v18 = (unsigned int)v4;
            v17 = 150;
          }
          else
          {
            v18 = (unsigned int)v4;
            v17 = 130;
          }
          goto LABEL_24;
        }
        v17 = 122;
      }
      else
      {
        v17 = 120;
      }
    }
    else
    {
      v17 = 118;
    }
    v18 = (unsigned int)MediaNotificationCallback;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientcore.cpp",
      (const char *)v18,
      (int)v30);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v27);
    v19 = pv;
    pv = 0;
    if ( v19 )
      CoTaskMemFree(v19);
    goto LABEL_37;
  }
  v5 = 90;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientcore.cpp",
    (const char *)(unsigned int)v4,
    v25);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007a6ac  mov     [rsp-8+arg_10], rbx
0x18007a6b1  push    rbp
0x18007a6b2  push    rsi
0x18007a6b3  push    rdi
0x18007a6b4  push    r12
0x18007a6b6  push    r14
0x18007a6b8  lea     rbp, [rsp-1220h]
0x18007a6c0  mov     eax, 1320h
0x18007a6c5  call    _alloca_probe
0x18007a6ca  sub     rsp, rax
0x18007a6cd  mov     rax, cs:__security_cookie
0x18007a6d4  xor     rax, rsp
0x18007a6d7  mov     [rbp+1240h+var_30], rax
0x18007a6de  mov     r14, rdx
0x18007a6e1  mov     rsi, rcx
0x18007a6e4  mov     [rbp+1240h+Src], 2
0x18007a6ee  mov     [rbp+1240h+var_64C], 1
0x18007a6f9  xor     r12d, r12d
0x18007a6fc  mov     [rbp+1240h+var_644], r12d
0x18007a703  mov     [rbp+1240h+var_640], 87h
0x18007a70d  xor     edx, edx; Val
0x18007a70f  mov     r8d, 600h; Size
0x18007a715  lea     rcx, [rbp+1240h+var_63C]; void *
0x18007a71c  call    memset_0
0x18007a721  mov     [rsp+1340h+var_1300], r12
0x18007a726  lea     rdx, [rsp+1340h+var_1300]
0x18007a72b  lea     rcx, [rbp+1240h+Src]
0x18007a732  call    ??$CastTo@UXvmActivateClient2@@@XvmActivateProxyAudioObject@@QEAAJPEAPEAUXvmActivateClient2@@@Z; XvmActivateProxyAudioObject::CastTo<XvmActivateClient2>(XvmActivateClient2 * *)
0x18007a737  mov     ebx, eax
0x18007a739  test    eax, eax
0x18007a73b  jns     short loc_18007A75D
0x18007a73d  lea     edx, [r12+5Ah]; void *
0x18007a742  lea     r8, aAvcoreAudiocor_66; "avcore\\audiocore\\client\\audioclient"...
0x18007a749  mov     r9d, ebx; char *
0x18007a74c  mov     rcx, [rbp+1248h]; this
0x18007a753  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a758  jmp     loc_18007AA94
0x18007a75d  mov     rdi, [rsp+1340h+var_1300]
0x18007a762  mov     rdx, rdi; struct XvmEndpointId *
0x18007a765  mov     rcx, [r14+18h]; unsigned __int16 *
0x18007a769  call    ?CopyToXvmEndpointId@@YAJPEBGPEAUXvmEndpointId@@@Z; CopyToXvmEndpointId(ushort const *,XvmEndpointId *)
0x18007a76e  mov     ebx, eax
0x18007a770  test    eax, eax
0x18007a772  jns     short loc_18007A77B
0x18007a774  mov     edx, 5Ch ; '\'
0x18007a779  jmp     short loc_18007A742
0x18007a77b  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18007a782  movdqu  xmmword ptr [rdi+70h], xmm0
0x18007a787  mov     [rsp+1340h+var_1300], r12
0x18007a78c  lea     rcx, [rsp+1340h+var_1300]
0x18007a791  call    ??$MakeAndInitialize@VCAudioClient@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCAudioClient@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CAudioClient,CAudioClient,>(CAudioClient * *)
0x18007a796  mov     ebx, eax
0x18007a798  test    eax, eax
0x18007a79a  jns     short loc_18007A7A6
0x18007a79c  mov     r9d, eax
0x18007a79f  mov     edx, 61h ; 'a'
0x18007a7a4  jmp     short loc_18007A7DE
0x18007a7a6  mov     rbx, [rsp+1340h+var_1300]
0x18007a7ab  movups  xmm0, xmmword ptr [rbx+210h]
0x18007a7b2  movdqu  xmmword ptr [rdi+80h], xmm0
0x18007a7ba  mov     eax, [rbx+1A0h]
0x18007a7c0  mov     [rdi+90h], eax
0x18007a7c6  call    ?GetRootProxyAudioObjectActivator@@YAPEAVCGuestXvmAudioObject@@XZ; GetRootProxyAudioObjectActivator(void)
0x18007a7cb  mov     rdi, rax
0x18007a7ce  test    rax, rax
0x18007a7d1  jnz     short loc_18007A7F6
0x18007a7d3  mov     ebx, 8000FFFFh
0x18007a7d8  mov     r9d, ebx; char *
0x18007a7db  lea     edx, [rax+69h]; void *
0x18007a7de  lea     r8, aAvcoreAudiocor_66; "avcore\\audiocore\\client\\audioclient"...
0x18007a7e5  mov     rcx, [rbp+1248h]; this
0x18007a7ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a7f1  jmp     loc_18007AA8A
0x18007a7f6  mov     [rsp+1340h+pv], r12
0x18007a7fb  mov     qword ptr [rsp+1340h+var_12F0], r12
0x18007a800  lea     rax, [rsp+1340h+pv]
0x18007a805  mov     [rsp+1340h+var_12E8], rax
0x18007a80a  mov     [rsp+1340h+var_12E0], r12
0x18007a80f  mov     [rsp+1340h+var_12D8], 1
0x18007a814  lea     rcx, [rsp+1340h+var_12D0]; void *
0x18007a819  lea     rdx, [rbp+1240h+Src]; Src
0x18007a820  mov     r8d, 614h; Size
0x18007a826  call    memcpy_0
0x18007a82b  lea     rcx, [rbp+1240h+var_CB0]; void *
0x18007a832  lea     rdx, [rsp+1340h+var_12D0]; Src
0x18007a837  mov     r8d, 614h; Size
0x18007a83d  call    memcpy_0
0x18007a842  lea     rax, [rsp+1340h+var_12F0]
0x18007a847  mov     qword ptr [rsp+1340h+var_1320], rax; int
0x18007a84c  lea     r9, [rsp+1340h+var_12E0]
0x18007a851  lea     r8, [rbp+1240h+var_CB0]
0x18007a858  mov     edx, [rdi+30h]
0x18007a85b  mov     rcx, rdi
0x18007a85e  call    ??$SendAndValidateResponse@UXvmActivateProxyAudioObject@@@CGuestXvmAudioObject@@QEAAJIUXvmActivateProxyAudioObject@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(uint,XvmActivateProxyAudioObject,XvmMessage * *,XvmActivateProxyAudioObject * *)
0x18007a863  mov     edi, eax
0x18007a865  lea     rcx, [rsp+1340h+var_12E8]
0x18007a86a  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18007a86f  test    edi, edi
0x18007a871  jns     short loc_18007A8AB
0x18007a873  mov     rcx, [rbp+1248h]; this
0x18007a87a  mov     r9d, edi; char *
0x18007a87d  lea     r8, aAvcoreAudiocor_66; "avcore\\audiocore\\client\\audioclient"...
0x18007a884  mov     edx, 6Dh ; 'm'; void *
0x18007a889  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a88e  nop
0x18007a88f  mov     rcx, [rsp+1340h+pv]; pv
0x18007a894  mov     [rsp+1340h+pv], r12
0x18007a899  test    rcx, rcx
0x18007a89c  jz      short loc_18007A8A4
0x18007a89e  call    cs:__imp_CoTaskMemFree
0x18007a8a4  mov     ebx, edi
0x18007a8a6  jmp     loc_18007AA8A
0x18007a8ab  mov     [rsp+1340h+var_1308], r12
0x18007a8b0  lea     rax, [rsp+1340h+var_1308]
0x18007a8b5  mov     [rsp+1340h+var_12F8], rax
0x18007a8ba  lea     rcx, [rsp+1340h+var_12F8]
0x18007a8bf  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18007a8c4  mov     rdx, rax
0x18007a8c7  mov     rcx, rsi
0x18007a8ca  call    ??$AsWeak@VCGuestAudioClient@@@WRL@Microsoft@@YAJPEAVCGuestAudioClient@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<CGuestAudioClient>(CGuestAudioClient *,Microsoft::WRL::WeakRef *)
0x18007a8cf  mov     edi, eax
0x18007a8d1  test    eax, eax
0x18007a8d3  jns     short loc_18007A8FD
0x18007a8d5  mov     edx, 70h ; 'p'; void *
0x18007a8da  lea     r8, aAvcoreAudiocor_66; "avcore\\audiocore\\client\\audioclient"...
0x18007a8e1  mov     r9d, edi; char *
0x18007a8e4  mov     rcx, [rbp+1248h]; this
0x18007a8eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a8f0  nop
0x18007a8f1  lea     rcx, [rsp+1340h+var_1308]
0x18007a8f6  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18007a8fb  jmp     short loc_18007A88F
0x18007a8fd  lea     rcx, [rsi+5B0h]
0x18007a904  xor     edx, edx
0x18007a906  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18007a90b  mov     edi, eax
0x18007a90d  test    eax, eax
0x18007a90f  jns     short loc_18007A918
0x18007a911  mov     edx, 72h ; 'r'
0x18007a916  jmp     short loc_18007A8DA
0x18007a918  lea     rdi, [rsi+98h]
0x18007a91f  mov     rdx, rbx
0x18007a922  mov     rcx, rdi
0x18007a925  call    ??4?$com_ptr_t@VCAudioClient@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAVCAudioClient@@@Z; wil::com_ptr_t<CAudioClient,wil::err_returncode_policy>::operator=(CAudioClient *)
0x18007a92a  mov     rdx, r14; struct AudioClientConstructionParams *
0x18007a92d  mov     rcx, [rdi]; this
0x18007a930  call    ?FinishConstruction@CAudioClient@@QEAAJPEBUAudioClientConstructionParams@@@Z; CAudioClient::FinishConstruction(AudioClientConstructionParams const *)
0x18007a935  mov     ebx, eax
0x18007a937  test    eax, eax
0x18007a939  jns     short loc_18007A980
0x18007a93b  mov     edx, 76h ; 'v'; void *
0x18007a940  mov     r9d, eax; char *
0x18007a943  mov     rcx, [rbp+1248h]; this
0x18007a94a  lea     r8, aAvcoreAudiocor_66; "avcore\\audiocore\\client\\audioclient"...
0x18007a951  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a956  nop
0x18007a957  lea     rcx, [rsp+1340h+var_1308]
0x18007a95c  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18007a961  nop
0x18007a962  mov     rcx, [rsp+1340h+pv]; pv
0x18007a967  mov     [rsp+1340h+pv], r12
0x18007a96c  test    rcx, rcx
0x18007a96f  jz      loc_18007AA8A
0x18007a975  call    cs:__imp_CoTaskMemFree
0x18007a97b  jmp     loc_18007AA8A
0x18007a980  mov     rdi, [rdi]
0x18007a983  lea     rcx, [rsi+38h]
0x18007a987  call    ?reset@?$com_ptr_t@UIMediaNotificationCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset(void)
0x18007a98c  lea     rdx, [rsi+38h]; struct IMediaNotificationCallback **
0x18007a990  mov     rcx, rdi; this
0x18007a993  call    ?GetMediaNotificationCallback@CAudioClient@@QEAAJPEAPEAUIMediaNotificationCallback@@@Z; CAudioClient::GetMediaNotificationCallback(IMediaNotificationCallback * *)
0x18007a998  mov     ebx, eax
0x18007a99a  test    eax, eax
0x18007a99c  jns     short loc_18007A9A5
0x18007a99e  mov     edx, 78h ; 'x'
0x18007a9a3  jmp     short loc_18007A940
0x18007a9a5  lea     rdi, [rsi+18h]
0x18007a9a9  xor     r9d, r9d; struct XvmActivateProxyAudioObject *
0x18007a9ac  lea     r8, [rsp+1340h+var_1308]; struct Microsoft::WRL::WeakRef *
0x18007a9b1  mov     rdx, qword ptr [rsp+1340h+var_12F0]
0x18007a9b6  mov     edx, [rdx+0Ch]; unsigned int
0x18007a9b9  mov     rcx, rdi; this
0x18007a9bc  call    ?Initialize@CGuestXvmAudioObject@@IEAAJIAEAVWeakRef@WRL@Microsoft@@PEAUXvmActivateProxyAudioObject@@@Z; CGuestXvmAudioObject::Initialize(uint,Microsoft::WRL::WeakRef &,XvmActivateProxyAudioObject *)
0x18007a9c1  mov     ebx, eax
0x18007a9c3  test    eax, eax
0x18007a9c5  jns     short loc_18007A9D1
0x18007a9c7  mov     edx, 7Ah ; 'z'
0x18007a9cc  jmp     loc_18007A940
0x18007a9d1  mov     rdx, rsi
0x18007a9d4  lea     rcx, [rsp+1340h+var_12F8]
0x18007a9d9  call    _lambda_3db8bcd5c969fae5248b7dc465e144ed____lambda_3db8bcd5c969fae5248b7dc465e144ed_
0x18007a9de  mov     rdx, rax
0x18007a9e1  lea     rcx, [rbp+1240h+var_690]
0x18007a9e8  call    std__function_void___cdecl_void____function_void___cdecl_void____lambda_129c027699bfc4538fa71b6704031c9e__0_
0x18007a9ed  nop
0x18007a9ee  lea     rdx, [rbp+1240h+var_690]
0x18007a9f5  mov     rcx, rdi
0x18007a9f8  call    ?TryRegisterAppSuspensionHandler@CGuestXvmAudioObject@@IEAAJAEBV?$function@$$A6AXXZ@std@@@Z; CGuestXvmAudioObject::TryRegisterAppSuspensionHandler(std::function<void (void)> const &)
0x18007a9fd  mov     ebx, eax
0x18007a9ff  lea     rcx, [rbp+1240h+var_690]
0x18007aa06  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18007aa0b  test    ebx, ebx
0x18007aa0d  jns     short loc_18007AA1C
0x18007aa0f  mov     r9d, ebx
0x18007aa12  mov     edx, 82h
0x18007aa17  jmp     loc_18007A943
0x18007aa1c  mov     rdx, rsi
0x18007aa1f  lea     rcx, [rsp+1340h+var_12F8]
0x18007aa24  call    _lambda_3db8bcd5c969fae5248b7dc465e144ed____lambda_3db8bcd5c969fae5248b7dc465e144ed_
0x18007aa29  mov     rdx, rax
0x18007aa2c  lea     rcx, [rbp+1240h+var_690]
0x18007aa33  call    std__function_void___cdecl_void____function_void___cdecl_void____lambda_a2cbb55ad9eed09ebede9af5196b3771__0_
0x18007aa38  nop
0x18007aa39  lea     rdx, [rbp+1240h+var_690]
0x18007aa40  mov     rcx, rdi
0x18007aa43  call    ?TryRegisterAppResumptionHandler@CGuestXvmAudioObject@@IEAAJAEBV?$function@$$A6AXXZ@std@@@Z; CGuestXvmAudioObject::TryRegisterAppResumptionHandler(std::function<void (void)> const &)
0x18007aa48  mov     ebx, eax
0x18007aa4a  lea     rcx, [rbp+1240h+var_690]
0x18007aa51  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18007aa56  test    ebx, ebx
0x18007aa58  jns     short loc_18007AA67
0x18007aa5a  mov     r9d, ebx
0x18007aa5d  mov     edx, 96h
0x18007aa62  jmp     loc_18007A943
0x18007aa67  lea     rcx, [rsp+1340h+var_1308]
0x18007aa6c  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18007aa71  nop
0x18007aa72  mov     rcx, [rsp+1340h+pv]; pv
0x18007aa77  mov     [rsp+1340h+pv], r12
0x18007aa7c  test    rcx, rcx
0x18007aa7f  jz      short loc_18007AA87
0x18007aa81  call    cs:__imp_CoTaskMemFree
0x18007aa87  mov     ebx, r12d
0x18007aa8a  lea     rcx, [rsp+1340h+var_1300]; void *
0x18007aa8f  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18007aa94  mov     eax, ebx
0x18007aa96  mov     rcx, [rbp+1240h+var_30]
0x18007aa9d  xor     rcx, rsp; StackCookie
0x18007aaa0  call    __security_check_cookie
0x18007aaa5  mov     rbx, [rsp+1340h+arg_10]
0x18007aaad  add     rsp, 1320h
0x18007aab4  pop     r14
0x18007aab6  pop     r12
0x18007aab8  pop     rdi
0x18007aab9  pop     rsi
0x18007aaba  pop     rbp
0x18007aabb  retn
```
