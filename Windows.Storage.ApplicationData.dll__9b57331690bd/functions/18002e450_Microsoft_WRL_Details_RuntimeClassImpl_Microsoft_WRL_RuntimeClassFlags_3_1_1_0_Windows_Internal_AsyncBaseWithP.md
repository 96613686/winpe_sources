# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetIids(ulong *,_GUID * *)

- ea: `0x18002e450`
- end: `0x18002e4d5`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@PEAVApplicationData@Storage@Windows@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `133`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> >,Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion> > *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e4e0`

## callees

- `0x18002df8c`
- `0x18002dfdc`
- `0x18002e450`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e472`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e472`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetIids(
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> >,Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion> > *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> >,Microsoft::WRL::FtmBase> *v5; // rcx
  _GUID *v6; // r8
  __int64 result; // rax
  __int64 v8; // rax
  _GUID *v9; // r8
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion> > *v10; // rcx
  _GUID *v11; // r8
  unsigned int index; // [rsp+38h] [rbp+10h] BYREF

  *iids = 0;
  *iidCount = 0;
  v6 = (_GUID *)CoTaskMemAlloc(0x40u);
  if ( !v6 )
    return 2147942414LL;
  index = 0;
  Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &index,
    v6);
  v8 = index++;
  v9[v8] = GUID_00000038_0000_0000_c000_000000000046;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::FillArrayWithIid(
    v10,
    &index,
    v9);
  *iidCount = 4;
  result = 0;
  *iids = v11;
  return result;
}

```

## disassembly

```asm
0x18002e450  mov     [rsp+arg_0], rbx
0x18002e455  push    rdi
0x18002e456  sub     rsp, 20h
0x18002e45a  mov     qword ptr [iids], 0
0x18002e461  mov     ecx, 40h ; '@'; cb
0x18002e466  mov     dword ptr [iidCount], 0
0x18002e46c  mov     rbx, iids
0x18002e46f  mov     rdi, iidCount
0x18002e472  call    cs:__imp_CoTaskMemAlloc
0x18002e478  mov     iids, rax; iids
0x18002e47b  test    rax, rax
0x18002e47e  jnz     short loc_18002E487
0x18002e480  mov     eax, 8007000Eh
0x18002e485  jmp     short loc_18002E4CA
0x18002e487  lea     iidCount, [rsp+28h+index]; index
0x18002e48c  mov     [rsp+28h+index], 0
0x18002e494  call    ?FillArrayWithIid@?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@23@VFtmBase@23@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18002e499  mov     edx, [rsp+28h+index]
0x18002e49d  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18002e4a4  mov     eax, edx
0x18002e4a6  inc     edx
0x18002e4a8  add     rax, rax
0x18002e4ab  mov     [rsp+28h+index], edx
0x18002e4af  lea     iidCount, [rsp+28h+index]; index
0x18002e4b4  movdqu  xmmword ptr [iids+rax*8], xmm0
0x18002e4ba  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$IAsyncOperation@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@UIAsyncOperationLocal@Internal@6@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::FillArrayWithIid(ulong *,_GUID *)
0x18002e4bf  mov     dword ptr [rdi], 4
0x18002e4c5  xor     eax, eax
0x18002e4c7  mov     [rbx], iids
0x18002e4ca  mov     rbx, [rsp+28h+arg_0]
0x18002e4cf  add     rsp, 20h
0x18002e4d3  pop     rdi
0x18002e4d4  retn
```
