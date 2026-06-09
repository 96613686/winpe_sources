# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> *)

- ea: `0x180019ca0`
- end: `0x180019dbd`
- name: `?PutOnComplete@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAU?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@3@@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a380`

## callees

- `0x180007630`
- `0x18000e264`
- `0x18000f48c`
- `0x180015b2c`
- `0x180019ca0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180019d0b`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180019d0b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(
        __int64 a1,
        __int64 a2)
{
  int AgileReference; // edi
  __int64 *v5; // rax
  __int64 *v6; // rdi
  signed __int32 v7; // ecx
  signed __int32 v9[10]; // [rsp+0h] [rbp-28h] BYREF
  __int64 *v10; // [rsp+40h] [rbp+18h] BYREF
  __int64 v11; // [rsp+48h] [rbp+20h] BYREF

  AgileReference = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(a1);
  if ( AgileReference >= 0 )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 20)) != 1 )
      return (unsigned int)-2147483624;
    v10 = (__int64 *)(a1 + 120);
    v5 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v10);
    v6 = v5;
    if ( a2 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v5);
      AgileReference = RoGetAgileReference(0, &GUID_6ea0f2e9_bc97_58e8_a3a6_c829b9e5f2aa, a2, v6);
      if ( AgileReference < 0 )
        return (unsigned int)AgileReference;
    }
    else
    {
      v10 = (__int64 *)*v5;
      v11 = 0;
      *v5 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v10);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
      AgileReference = 0;
    }
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceDelegateAssigned(a1);
    if ( a2 )
    {
      *(_QWORD *)(a1 + 128) = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 136));
    }
    _InterlockedOr(v9, 0);
    v7 = *(_DWORD *)(a1 + 56);
    LODWORD(v10) = -2;
    _InterlockedCompareExchange((volatile signed __int32 *)&v10, v7, -2);
    if ( (unsigned int)((_DWORD)v10 - 1) <= 3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
  }
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x180019ca0  mov     [rsp+arg_0], rbx
0x180019ca5  mov     [rsp+arg_8], rsi
0x180019caa  push    rdi
0x180019cab  sub     rsp, 20h
0x180019caf  mov     rsi, rdx
0x180019cb2  mov     rbx, rcx
0x180019cb5  call    ?CheckValidStateForDelegateCall@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(void)
0x180019cba  mov     edi, eax
0x180019cbc  test    eax, eax
0x180019cbe  js      loc_180019DAB
0x180019cc4  mov     eax, 1
0x180019cc9  lock xadd [rbx+14h], eax
0x180019cce  inc     eax
0x180019cd0  cmp     eax, 1
0x180019cd3  jnz     loc_180019DA6
0x180019cd9  lea     rax, [rbx+78h]
0x180019cdd  lea     rcx, [rsp+28h+arg_10]
0x180019ce2  mov     [rsp+28h+arg_10], rax
0x180019ce7  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x180019cec  mov     rdi, rax
0x180019cef  test    rsi, rsi
0x180019cf2  jz      short loc_180019D1D
0x180019cf4  mov     rcx, rax
0x180019cf7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019cfc  mov     r9, rdi
0x180019cff  lea     rdx, _GUID_6ea0f2e9_bc97_58e8_a3a6_c829b9e5f2aa
0x180019d06  mov     r8, rsi
0x180019d09  xor     ecx, ecx
0x180019d0b  call    cs:__imp_RoGetAgileReference
0x180019d11  mov     edi, eax
0x180019d13  test    eax, eax
0x180019d15  js      loc_180019DAB
0x180019d1b  jmp     short loc_180019D4B
0x180019d1d  mov     rax, [rax]
0x180019d20  lea     rcx, [rsp+28h+arg_10]
0x180019d25  mov     [rsp+28h+arg_10], rax
0x180019d2a  mov     [rsp+28h+arg_18], 0
0x180019d33  mov     qword ptr [rdi], 0
0x180019d3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019d3f  lea     rcx, [rsp+28h+arg_18]
0x180019d44  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019d49  xor     edi, edi
0x180019d4b  mov     rcx, rbx
0x180019d4e  call    ?TraceDelegateAssigned@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceDelegateAssigned(void)
0x180019d53  test    rsi, rsi
0x180019d56  jz      short loc_180019D6D
0x180019d58  mov     rax, [rsi]
0x180019d5b  mov     rcx, [rax+18h]
0x180019d5f  mov     [rbx+80h], rcx
0x180019d66  lock inc dword ptr [rbx+88h]
0x180019d6d  lock or [rsp+28h+var_28], 0
0x180019d72  mov     ecx, [rbx+38h]
0x180019d75  mov     dword ptr [rsp+28h+arg_10], 0FFFFFFFEh
0x180019d7d  mov     eax, dword ptr [rsp+28h+arg_10]
0x180019d81  lock cmpxchg dword ptr [rsp+28h+arg_10], ecx
0x180019d87  mov     ecx, dword ptr [rsp+28h+arg_10]
0x180019d8b  dec     ecx
0x180019d8d  cmp     ecx, 3
0x180019d90  ja      short loc_180019DAB
0x180019d92  mov     rax, [rbx]
0x180019d95  mov     rcx, rbx
0x180019d98  mov     rax, [rax+80h]
0x180019d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019da4  jmp     short loc_180019DAB
0x180019da6  mov     edi, 80000018h
0x180019dab  mov     rbx, [rsp+28h+arg_0]
0x180019db0  mov     eax, edi
0x180019db2  mov     rsi, [rsp+28h+arg_8]
0x180019db7  add     rsp, 20h
0x180019dbb  pop     rdi
0x180019dbc  retn
```
