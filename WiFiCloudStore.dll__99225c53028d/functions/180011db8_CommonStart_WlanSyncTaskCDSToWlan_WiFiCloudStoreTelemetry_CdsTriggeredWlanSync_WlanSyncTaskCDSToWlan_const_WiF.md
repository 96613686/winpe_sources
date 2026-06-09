# CommonStart<WlanSyncTaskCDSToWlan *,WiFiCloudStoreTelemetry::CdsTriggeredWlanSync>(WlanSyncTaskCDSToWlan * const &,WiFiCloudStoreTelemetry::CdsTriggeredWlanSync &,IUnknown *)

- ea: `0x180011db8`
- end: `0x180011f84`
- name: `??$CommonStart@PEAVWlanSyncTaskCDSToWlan@@VCdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@@@YAJAEBQEAVWlanSyncTaskCDSToWlan@@AEAVCdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@PEAUIUnknown@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64 (__fastcall ***)(_QWORD, GUID *, int *))`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800121b0`

## callees

- `0x180006b88`
- `0x1800116e4`
- `0x18001171c`
- `0x180011d5c`
- `0x180011db8`
- `0x180012570`
- `0x180013bc0`
- `0x18001d7e0`
- `0x18002477c`
- `0x18002748c`
- `0x18002a030`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011ec1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011ec1`

## string_xrefs

- `0x180011e2f`: `onecoreuap\net\wlan\cloudstore\provider\lib\SyncTaskCommon.h`
- `0x180011f02`: `onecoreuap\net\wlan\cloudstore\provider\lib\SyncTaskCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CommonStart<WlanSyncTaskCDSToWlan *,WiFiCloudStoreTelemetry::CdsTriggeredWlanSync>(
        __int64 *a1,
        __int64 a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, int *))
{
  __int64 (__fastcall *v6)(_QWORD, GUID *, int *); // rbx
  int v7; // eax
  volatile int *v8; // rdx
  unsigned int v9; // ebx
  __int64 v10; // rbx
  signed __int64 v11; // rax
  signed __int64 v12; // rtt
  DWORD CurrentThreadId; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // edi
  __int64 v18; // rcx
  int v19[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  *(_QWORD *)v19 = 0;
  v6 = **a3;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v19);
  v7 = v6(a3, &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a, v19);
  v9 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\SyncTaskCommon.h",
      (const char *)(unsigned int)v7,
      v19[0]);
LABEL_14:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v19);
    return v9;
  }
  v10 = *a1;
  v20 = v10;
  if ( v10 )
  {
    v11 = *(_QWORD *)(v10 + 56);
    while ( v11 >= 0 )
    {
      if ( (_DWORD)v11 != 0x7FFFFFFF )
      {
        v12 = v11;
        v11 = _InterlockedCompareExchange64((volatile signed __int64 *)(v10 + 56), v11 + 1, v11);
        if ( v12 != v11 )
          continue;
      }
      goto LABEL_10;
    }
    Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(2 * v11 + 16), v8);
  }
LABEL_10:
  v21 = v10;
  Microsoft::WRL::ComPtr<WlanSyncTaskCDSToWlan>::InternalAddRef(&v21);
  v22 = *(_QWORD *)v19;
  if ( *(_QWORD *)v19 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v19 + 8LL))(*(_QWORD *)v19);
  wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v23,
    a2);
  v23[0] = &WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::`vftable';
  CurrentThreadId = GetCurrentThreadId();
  v16 = Windows::Internal::ComTaskPool::QueueTask<_lambda_5907047c5d0b0999ef7eaffd146f2f9d_>(
          v15,
          v14,
          CurrentThreadId,
          &v21);
  WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::~CdsTriggeredWlanSync((WiFiCloudStoreTelemetry::CdsTriggeredWlanSync *)v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(&v21);
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\SyncTaskCommon.h",
      (const char *)(unsigned int)v16,
      v19[0]);
    Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(&v20);
    v9 = v16;
    goto LABEL_14;
  }
  if ( v10 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::Release(v10);
  v18 = *(_QWORD *)v19;
  if ( *(_QWORD *)v19 )
  {
    *(_QWORD *)v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x180011db8  mov     [rsp-8+arg_0], rbx
0x180011dbd  mov     [rsp-8+arg_18], rsi
0x180011dc2  push    rbp
0x180011dc3  push    rdi
0x180011dc4  push    r14
0x180011dc6  lea     rbp, [rsp-0A0h]
0x180011dce  sub     rsp, 1A0h
0x180011dd5  mov     rax, cs:__security_cookie
0x180011ddc  xor     rax, rsp
0x180011ddf  mov     [rbp+0B0h+var_20], rax
0x180011de6  mov     rdi, r8
0x180011de9  mov     r14, rdx
0x180011dec  mov     rsi, rcx
0x180011def  mov     qword ptr [rsp+1B0h+var_190], 0; int
0x180011df8  mov     rax, [r8]
0x180011dfb  mov     rbx, [rax]
0x180011dfe  lea     rcx, [rsp+1B0h+var_190]
0x180011e03  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011e08  lea     r8, [rsp+1B0h+var_190]
0x180011e0d  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180011e14  mov     rcx, rdi
0x180011e17  mov     rax, rbx
0x180011e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e1f  mov     ebx, eax
0x180011e21  test    eax, eax
0x180011e23  jns     short loc_180011E45
0x180011e25  mov     rcx, [rbp+0B8h]; this
0x180011e2c  mov     r9d, eax; char *
0x180011e2f  lea     r8, aOnecoreuapNetW_4; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180011e36  mov     edx, 13h; void *
0x180011e3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011e40  jmp     loc_180011F1F
0x180011e45  mov     rbx, [rsi]
0x180011e48  mov     [rsp+1B0h+var_188], rbx
0x180011e4d  test    rbx, rbx
0x180011e50  jz      short loc_180011E7D
0x180011e52  mov     rax, [rbx+38h]
0x180011e56  test    rax, rax
0x180011e59  js      short loc_180011E70
0x180011e5b  cmp     eax, 7FFFFFFFh
0x180011e60  jz      short loc_180011E7D
0x180011e62  lea     rcx, [rax+1]
0x180011e66  lock cmpxchg [rbx+38h], rcx
0x180011e6c  jnz     short loc_180011E56
0x180011e6e  jmp     short loc_180011E7D
0x180011e70  lea     rcx, ds:10h[rax*2]; this
0x180011e78  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180011e7d  mov     [rsp+1B0h+var_180], rbx
0x180011e82  lea     rcx, [rsp+1B0h+var_180]
0x180011e87  call    ?InternalAddRef@?$ComPtr@VWlanSyncTaskCDSToWlan@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<WlanSyncTaskCDSToWlan>::InternalAddRef(void)
0x180011e8c  mov     rcx, qword ptr [rsp+1B0h+var_190]
0x180011e91  mov     [rsp+1B0h+var_178], rcx
0x180011e96  test    rcx, rcx
0x180011e99  jz      short loc_180011EA8
0x180011e9b  mov     rax, [rcx]
0x180011e9e  mov     rax, [rax+8]
0x180011ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ea7  nop
0x180011ea8  mov     rdx, r14
0x180011eab  lea     rcx, [rsp+1B0h+var_170]
0x180011eb0  call    ??0?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x180011eb5  lea     rax, ??_7CdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@6B@; const WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::`vftable'
0x180011ebc  mov     [rsp+1B0h+var_170], rax
0x180011ec1  call    cs:__imp_GetCurrentThreadId
0x180011ec7  lea     r9, [rsp+1B0h+var_180]
0x180011ecc  mov     r8d, eax
0x180011ecf  call    ??$QueueTask@V_lambda_5907047c5d0b0999ef7eaffd146f2f9d_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@W4TaskOptions@12@K$$QEAV_lambda_5907047c5d0b0999ef7eaffd146f2f9d_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_5907047c5d0b0999ef7eaffd146f2f9d_>(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,_lambda_5907047c5d0b0999ef7eaffd146f2f9d_ &&)
0x180011ed4  mov     edi, eax
0x180011ed6  lea     rcx, [rsp+1B0h+var_170]; this
0x180011edb  call    ??1CdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@QEAA@XZ; WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::~CdsTriggeredWlanSync(void)
0x180011ee0  lea     rcx, [rsp+1B0h+var_178]
0x180011ee5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011eea  lea     rcx, [rsp+1B0h+var_180]
0x180011eef  call    ?InternalRelease@?$ComPtr@VWlanSyncTaskWlanToCDS@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(void)
0x180011ef4  test    edi, edi
0x180011ef6  jns     short loc_180011F2D
0x180011ef8  mov     rcx, [rbp+0B8h]; this
0x180011eff  mov     r9d, edi; char *
0x180011f02  lea     r8, aOnecoreuapNetW_4; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180011f09  mov     edx, 36h ; '6'; void *
0x180011f0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011f13  lea     rcx, [rsp+1B0h+var_188]
0x180011f18  call    ?InternalRelease@?$ComPtr@VWlanSyncTaskWlanToCDS@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(void)
0x180011f1d  mov     ebx, edi
0x180011f1f  lea     rcx, [rsp+1B0h+var_190]
0x180011f24  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011f29  mov     eax, ebx
0x180011f2b  jmp     short loc_180011F5D
0x180011f2d  test    rbx, rbx
0x180011f30  jz      short loc_180011F3B
0x180011f32  mov     rcx, rbx
0x180011f35  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::Release(void)
0x180011f3a  nop
0x180011f3b  mov     rcx, qword ptr [rsp+1B0h+var_190]
0x180011f40  test    rcx, rcx
0x180011f43  jz      short loc_180011F5B
0x180011f45  mov     qword ptr [rsp+1B0h+var_190], 0
0x180011f4e  mov     rax, [rcx]
0x180011f51  mov     rax, [rax+10h]
0x180011f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f5a  nop
0x180011f5b  xor     eax, eax
0x180011f5d  mov     rcx, [rbp+0B0h+var_20]
0x180011f64  xor     rcx, rsp; StackCookie
0x180011f67  call    __security_check_cookie
0x180011f6c  lea     r11, [rsp+1B0h+var_10]
0x180011f74  mov     rbx, [r11+20h]
0x180011f78  mov     rsi, [r11+38h]
0x180011f7c  mov     rsp, r11
0x180011f7f  pop     r14
0x180011f81  pop     rdi
0x180011f82  pop     rbp
0x180011f83  retn
```
