# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetIids(ulong *,_GUID * *)

- ea: `0x180046ff0`
- end: `0x180047075`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180047080`

## callees

- `0x180032f08`
- `0x1800458e4`
- `0x180046ff0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047012`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047012`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // r8
  unsigned int v12; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x40u);
  if ( !v6 )
    return 2147942414LL;
  v12 = 0;
  Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::DisableCausality>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v12,
    v6);
  v8 = 2LL * v12++;
  *(GUID *)(v9 + 8 * v8) = GUID_00000038_0000_0000_c000_000000000046;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::FillArrayWithIid(
    v10,
    &v12);
  *a2 = 4;
  result = 0;
  *a3 = v11;
  return result;
}

```

## disassembly

```asm
0x180046ff0  mov     [rsp+arg_0], rbx
0x180046ff5  push    rdi
0x180046ff6  sub     rsp, 20h
0x180046ffa  mov     qword ptr [r8], 0
0x180047001  mov     ecx, 40h ; '@'; cb
0x180047006  mov     dword ptr [rdx], 0
0x18004700c  mov     rbx, r8
0x18004700f  mov     rdi, rdx
0x180047012  call    cs:__imp_CoTaskMemAlloc
0x180047018  mov     r8, rax
0x18004701b  test    rax, rax
0x18004701e  jnz     short loc_180047027
0x180047020  mov     eax, 8007000Eh
0x180047025  jmp     short loc_18004706A
0x180047027  lea     rdx, [rsp+28h+arg_8]
0x18004702c  mov     [rsp+28h+arg_8], 0
0x180047034  call    ?FillArrayWithIid@?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@V?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00UDisableCausality@67@@23@VFtmBase@23@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::DisableCausality>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180047039  mov     edx, [rsp+28h+arg_8]
0x18004703d  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180047044  mov     eax, edx
0x180047046  inc     edx
0x180047048  add     rax, rax
0x18004704b  mov     [rsp+28h+arg_8], edx
0x18004704f  lea     rdx, [rsp+28h+arg_8]
0x180047054  movdqu  xmmword ptr [r8+rax*8], xmm0
0x18004705a  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$IAsyncOperation@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@UIAsyncOperationLocal@Internal@6@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::FillArrayWithIid(ulong *,_GUID *)
0x18004705f  mov     dword ptr [rdi], 4
0x180047065  xor     eax, eax
0x180047067  mov     [rbx], r8
0x18004706a  mov     rbx, [rsp+28h+arg_0]
0x18004706f  add     rsp, 20h
0x180047073  pop     rdi
0x180047074  retn
```
