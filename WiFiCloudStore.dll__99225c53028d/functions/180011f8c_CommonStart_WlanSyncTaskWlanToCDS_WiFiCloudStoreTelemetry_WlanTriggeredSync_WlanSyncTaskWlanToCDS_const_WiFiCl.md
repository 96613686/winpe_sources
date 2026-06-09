# CommonStart<WlanSyncTaskWlanToCDS *,WiFiCloudStoreTelemetry::WlanTriggeredSync>(WlanSyncTaskWlanToCDS * const &,WiFiCloudStoreTelemetry::WlanTriggeredSync &,IUnknown *)

- ea: `0x180011f8c`
- end: `0x180012179`
- name: `??$CommonStart@PEAVWlanSyncTaskWlanToCDS@@VWlanTriggeredSync@WiFiCloudStoreTelemetry@@@@YAJAEBQEAVWlanSyncTaskWlanToCDS@@AEAVWlanTriggeredSync@WiFiCloudStoreTelemetry@@PEAUIUnknown@@@Z`
- size: `493`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64 (__fastcall ***)(_QWORD, GUID *, int *))`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800121b0`

## callees

- `0x180006b88`
- `0x18001171c`
- `0x180011f8c`
- `0x180012180`
- `0x180012570`
- `0x180013bc0`
- `0x18001d7e0`
- `0x18002477c`
- `0x180026a50`
- `0x1800276f4`
- `0x18002a030`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800120b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800120b8`

## string_xrefs

- `0x180012003`: `onecoreuap\net\wlan\cloudstore\provider\lib\SyncTaskCommon.h`
- `0x1800120f9`: `onecoreuap\net\wlan\cloudstore\provider\lib\SyncTaskCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CommonStart<WlanSyncTaskWlanToCDS *,WiFiCloudStoreTelemetry::WlanTriggeredSync>(
        __int64 *a1,
        __int64 a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, int *))
{
  __int64 (__fastcall *v6)(_QWORD, GUID *, int *); // rbx
  int v7; // eax
  volatile int *v8; // rdx
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v12; // rbx
  signed __int64 v13; // rax
  signed __int64 v14; // rtt
  DWORD CurrentThreadId; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // edi
  __int64 v19; // rcx
  int v20[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v24[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  *(_QWORD *)v20 = 0;
  v6 = **a3;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v20);
  v7 = v6(a3, &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a, v20);
  v9 = v7;
  if ( v7 >= 0 )
  {
    v12 = *a1;
    v21 = v12;
    if ( v12 )
    {
      v13 = *(_QWORD *)(v12 + 56);
      while ( v13 >= 0 )
      {
        if ( (_DWORD)v13 != 0x7FFFFFFF )
        {
          v14 = v13;
          v13 = _InterlockedCompareExchange64((volatile signed __int64 *)(v12 + 56), v13 + 1, v13);
          if ( v14 != v13 )
            continue;
        }
        goto LABEL_12;
      }
      Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(2 * v13 + 16), v8);
    }
LABEL_12:
    v22 = v12;
    Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalAddRef(&v22);
    v23 = *(_QWORD *)v20;
    if ( *(_QWORD *)v20 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v20 + 8LL))(*(_QWORD *)v20);
    wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v24,
      a2);
    v24[0] = &WiFiCloudStoreTelemetry::WlanTriggeredSync::`vftable';
    CurrentThreadId = GetCurrentThreadId();
    v18 = Windows::Internal::ComTaskPool::QueueTask<_lambda_5b71e87bbd38edd0b6bc262bc572dce1_>(
            v17,
            v16,
            CurrentThreadId,
            &v22);
    WiFiCloudStoreTelemetry::WlanTriggeredSync::~WlanTriggeredSync((WiFiCloudStoreTelemetry::WlanTriggeredSync *)v24);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(&v22);
    if ( v18 >= 0 )
    {
      if ( v12 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::Release(v12);
      v19 = *(_QWORD *)v20;
      if ( *(_QWORD *)v20 )
      {
        *(_QWORD *)v20 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\SyncTaskCommon.h",
        (const char *)(unsigned int)v18,
        v20[0]);
      Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(&v21);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v20);
      return (unsigned int)v18;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\SyncTaskCommon.h",
      (const char *)(unsigned int)v7,
      v20[0]);
    v10 = *(_QWORD *)v20;
    if ( *(_QWORD *)v20 )
    {
      *(_QWORD *)v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return v9;
  }
}

```

## disassembly

```asm
0x180011f8c  mov     [rsp-8+arg_0], rbx
0x180011f91  mov     [rsp-8+arg_18], rsi
0x180011f96  push    rbp
0x180011f97  push    rdi
0x180011f98  push    r14
0x180011f9a  lea     rbp, [rsp-0A0h]
0x180011fa2  sub     rsp, 1A0h
0x180011fa9  mov     rax, cs:__security_cookie
0x180011fb0  xor     rax, rsp
0x180011fb3  mov     [rbp+0B0h+var_20], rax
0x180011fba  mov     rdi, r8
0x180011fbd  mov     r14, rdx
0x180011fc0  mov     rsi, rcx
0x180011fc3  mov     qword ptr [rsp+1B0h+var_190], 0; int
0x180011fcc  mov     rax, [r8]
0x180011fcf  mov     rbx, [rax]
0x180011fd2  lea     rcx, [rsp+1B0h+var_190]
0x180011fd7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011fdc  lea     r8, [rsp+1B0h+var_190]
0x180011fe1  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180011fe8  mov     rcx, rdi
0x180011feb  mov     rax, rbx
0x180011fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ff3  mov     ebx, eax
0x180011ff5  test    eax, eax
0x180011ff7  jns     short loc_18001203C
0x180011ff9  mov     rcx, [rbp+0B8h]; this
0x180012000  mov     r9d, eax; char *
0x180012003  lea     r8, aOnecoreuapNetW_4; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18001200a  mov     edx, 13h; void *
0x18001200f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012014  nop
0x180012015  mov     rcx, qword ptr [rsp+1B0h+var_190]
0x18001201a  test    rcx, rcx
0x18001201d  jz      short loc_180012035
0x18001201f  mov     qword ptr [rsp+1B0h+var_190], 0
0x180012028  mov     rax, [rcx]
0x18001202b  mov     rax, [rax+10h]
0x18001202f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012034  nop
0x180012035  mov     eax, ebx
0x180012037  jmp     loc_180012152
0x18001203c  mov     rbx, [rsi]
0x18001203f  mov     [rsp+1B0h+var_188], rbx
0x180012044  test    rbx, rbx
0x180012047  jz      short loc_180012074
0x180012049  mov     rax, [rbx+38h]
0x18001204d  test    rax, rax
0x180012050  js      short loc_180012067
0x180012052  cmp     eax, 7FFFFFFFh
0x180012057  jz      short loc_180012074
0x180012059  lea     rcx, [rax+1]
0x18001205d  lock cmpxchg [rbx+38h], rcx
0x180012063  jnz     short loc_18001204D
0x180012065  jmp     short loc_180012074
0x180012067  lea     rcx, ds:10h[rax*2]; this
0x18001206f  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180012074  mov     [rsp+1B0h+var_180], rbx
0x180012079  lea     rcx, [rsp+1B0h+var_180]
0x18001207e  call    ?InternalAddRef@?$ComPtr@VWlanSyncTaskWlanToCDS@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalAddRef(void)
0x180012083  mov     rcx, qword ptr [rsp+1B0h+var_190]
0x180012088  mov     [rsp+1B0h+var_178], rcx
0x18001208d  test    rcx, rcx
0x180012090  jz      short loc_18001209F
0x180012092  mov     rax, [rcx]
0x180012095  mov     rax, [rax+8]
0x180012099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001209e  nop
0x18001209f  mov     rdx, r14
0x1800120a2  lea     rcx, [rsp+1B0h+var_170]
0x1800120a7  call    ??0?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x1800120ac  lea     rax, ??_7WlanTriggeredSync@WiFiCloudStoreTelemetry@@6B@; const WiFiCloudStoreTelemetry::WlanTriggeredSync::`vftable'
0x1800120b3  mov     [rsp+1B0h+var_170], rax
0x1800120b8  call    cs:__imp_GetCurrentThreadId
0x1800120be  lea     r9, [rsp+1B0h+var_180]
0x1800120c3  mov     r8d, eax
0x1800120c6  call    ??$QueueTask@V_lambda_5b71e87bbd38edd0b6bc262bc572dce1_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@W4TaskOptions@12@K$$QEAV_lambda_5b71e87bbd38edd0b6bc262bc572dce1_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_5b71e87bbd38edd0b6bc262bc572dce1_>(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,_lambda_5b71e87bbd38edd0b6bc262bc572dce1_ &&)
0x1800120cb  mov     edi, eax
0x1800120cd  lea     rcx, [rsp+1B0h+var_170]; this
0x1800120d2  call    ??1WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAA@XZ; WiFiCloudStoreTelemetry::WlanTriggeredSync::~WlanTriggeredSync(void)
0x1800120d7  lea     rcx, [rsp+1B0h+var_178]
0x1800120dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800120e1  lea     rcx, [rsp+1B0h+var_180]
0x1800120e6  call    ?InternalRelease@?$ComPtr@VWlanSyncTaskWlanToCDS@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(void)
0x1800120eb  test    edi, edi
0x1800120ed  jns     short loc_180012122
0x1800120ef  mov     rcx, [rbp+0B8h]; this
0x1800120f6  mov     r9d, edi; char *
0x1800120f9  lea     r8, aOnecoreuapNetW_4; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180012100  mov     edx, 36h ; '6'; void *
0x180012105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001210a  lea     rcx, [rsp+1B0h+var_188]
0x18001210f  call    ?InternalRelease@?$ComPtr@VWlanSyncTaskWlanToCDS@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(void)
0x180012114  lea     rcx, [rsp+1B0h+var_190]
0x180012119  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001211e  mov     eax, edi
0x180012120  jmp     short loc_180012152
0x180012122  test    rbx, rbx
0x180012125  jz      short loc_180012130
0x180012127  mov     rcx, rbx
0x18001212a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::Release(void)
0x18001212f  nop
0x180012130  mov     rcx, qword ptr [rsp+1B0h+var_190]
0x180012135  test    rcx, rcx
0x180012138  jz      short loc_180012150
0x18001213a  mov     qword ptr [rsp+1B0h+var_190], 0
0x180012143  mov     rax, [rcx]
0x180012146  mov     rax, [rax+10h]
0x18001214a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001214f  nop
0x180012150  xor     eax, eax
0x180012152  mov     rcx, [rbp+0B0h+var_20]
0x180012159  xor     rcx, rsp; StackCookie
0x18001215c  call    __security_check_cookie
0x180012161  lea     r11, [rsp+1B0h+var_10]
0x180012169  mov     rbx, [r11+20h]
0x18001216d  mov     rsi, [r11+38h]
0x180012171  mov     rsp, r11
0x180012174  pop     r14
0x180012176  pop     rdi
0x180012177  pop     rbp
0x180012178  retn
```
