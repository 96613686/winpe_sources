# Windows::Graphics::Capture::Server::CaptureServerAccessStatics::RequestAccessAsync(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind,Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> * *)

- ea: `0x180019eb0`
- end: `0x180019f56`
- name: `?RequestAccessAsync@CaptureServerAccessStatics@Server@Capture@Graphics@Windows@@UEAAJW4CaptureServerAccessRequestKind@2345@PEAPEAU?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@5@@Z`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000907c`
- `0x180018ee4`
- `0x180018fbc`
- `0x180019eb0`
- `0x18001e964`

## string_xrefs

- `0x180019f28`: `Windows.Foundation.IAsyncOperation`1<Windows.Security.Authorization.AppCapabilityAccess.AppCapabilityAccessStatus>`
- `0x180019ede`: `onecoreuap\windows\dwm\capture\svc\dll\captureserveraccess.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureServerAccessStatics::RequestAccessAsync(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  unsigned int v4; // ecx
  int v5; // ebx
  __int64 v6; // rdx
  _QWORD *v8; // rax
  __int64 v9; // r9
  int v10; // [rsp+20h] [rbp-38h]
  int *v11; // [rsp+30h] [rbp-28h] BYREF
  __int64 v12; // [rsp+38h] [rbp-20h] BYREF
  int v13; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v15; // [rsp+78h] [rbp+20h] BYREF

  v4 = (unsigned int)a2;
  v15 = 3;
  LOBYTE(a2) = 1;
  v5 = Windows::Graphics::Capture::Server::CheckCAMCapability(v4, a2, &v15);
  if ( v5 < 0 )
  {
    v6 = 21;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\captureserveraccess.cpp",
      (const char *)(unsigned int)v5,
      v10);
    return (unsigned int)v5;
  }
  v11 = &v15;
  v12 = 4;
  v13 = 0;
  v8 = Windows::Internal::MakeOpLambda<0,Windows::Internal::CBasicResult<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,_lambda_8f1b120f2751ea3cce314e7831486f20_,>(&v11);
  v5 = Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::INilDelegate,Windows::Internal::CBasicResult<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
         a3,
         (__int64)&v12,
         (__int64)L"Windows.Foundation.IAsyncOperation`1<Windows.Security.Authorization.AppCapabilityAccess.AppCapabilityAccessStatus>",
         v9,
         (void (__fastcall ***)(_QWORD, __int64))v8);
  if ( v5 < 0 )
  {
    v6 = 28;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180019eb0  mov     [rsp+arg_0], rbx
0x180019eb5  push    rdi
0x180019eb6  sub     rsp, 50h
0x180019eba  mov     rdi, r8
0x180019ebd  mov     ecx, edx
0x180019ebf  mov     [rsp+58h+arg_18], 3
0x180019ec7  lea     r8, [rsp+58h+arg_18]
0x180019ecc  mov     dl, 1
0x180019ece  call    ?CheckCAMCapability@Server@Capture@Graphics@Windows@@YAJW4CaptureServerAccessRequestKind@1234@_NPEAW4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@4@@Z; Windows::Graphics::Capture::Server::CheckCAMCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind,bool,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus *)
0x180019ed3  mov     ebx, eax
0x180019ed5  test    eax, eax
0x180019ed7  jns     short loc_180019EF6
0x180019ed9  mov     edx, 15h; void *
0x180019ede  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180019ee5  mov     r9d, ebx; char *
0x180019ee8  mov     rcx, [rsp+58h]; this
0x180019eed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019ef2  mov     eax, ebx
0x180019ef4  jmp     short loc_180019F4B
0x180019ef6  mov     eax, [rsp+58h+arg_18]
0x180019efa  mov     [rsp+58h+arg_18], eax
0x180019efe  lea     rax, [rsp+58h+arg_18]
0x180019f03  mov     [rsp+58h+var_28], rax
0x180019f08  mov     [rsp+58h+var_20], 4
0x180019f11  mov     [rsp+58h+var_18], 0
0x180019f19  lea     rcx, [rsp+58h+var_28]
0x180019f1e  call    ??$MakeOpLambda@$0A@V?$CBasicResult@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@$02@Internal@Windows@@V_lambda_8f1b120f2751ea3cce314e7831486f20_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@V?$CBasicResult@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@$02@Internal@Windows@@@01@$$QEAV_lambda_8f1b120f2751ea3cce314e7831486f20_@@@Z; Windows::Internal::MakeOpLambda<0,Windows::Internal::CBasicResult<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,_lambda_8f1b120f2751ea3cce314e7831486f20_,>(_lambda_8f1b120f2751ea3cce314e7831486f20_ &&)
0x180019f23  mov     qword ptr [rsp+58h+var_38], rax
0x180019f28  lea     r8, aWindowsFoundat_0; "Windows.Foundation.IAsyncOperation`1<Wi"...
0x180019f2f  lea     rdx, [rsp+58h+var_20]
0x180019f34  mov     rcx, rdi
0x180019f37  call    ??$MakeAsyncHelper@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@23@UINilDelegate@Internal@3@V?$CBasicResult@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@$02@63@VComTaskPoolHandler@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@YAJPEAPEAU?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@1@$$QEAVComTaskPoolHandler@01@QEBGW4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CBasicResult@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@$02@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::INilDelegate,Windows::Internal::CBasicResult<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> * *,Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CBasicResult<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>> *)
0x180019f3c  mov     ebx, eax
0x180019f3e  test    eax, eax
0x180019f40  jns     short loc_180019F49
0x180019f42  mov     edx, 1Ch
0x180019f47  jmp     short loc_180019EDE
0x180019f49  xor     eax, eax
0x180019f4b  mov     rbx, [rsp+58h+arg_0]
0x180019f50  add     rsp, 50h
0x180019f54  pop     rdi
0x180019f55  retn
```
