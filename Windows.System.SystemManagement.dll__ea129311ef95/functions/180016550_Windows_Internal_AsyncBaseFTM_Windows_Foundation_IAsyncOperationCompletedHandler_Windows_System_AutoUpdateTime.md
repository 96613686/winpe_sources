# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus> *)

- ea: `0x180016550`
- end: `0x18001666d`
- name: `?PutOnComplete@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAU?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@3@@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017a70`

## callees

- `0x180007248`
- `0x180014708`
- `0x180014ff0`
- `0x180016550`
- `0x1800170ac`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800165bb`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800165bb`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(
        __int64 a1,
        __int64 a2)
{
  int AgileReference; // edi
  __int64 *v5; // rax
  __int64 *v6; // rdi
  signed __int32 v7; // ecx
  signed __int32 v9[10]; // [rsp+0h] [rbp-28h] BYREF
  __int64 v10; // [rsp+40h] [rbp+18h] BYREF
  __int64 v11; // [rsp+48h] [rbp+20h] BYREF

  AgileReference = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(a1);
  if ( AgileReference >= 0 )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 20)) != 1 )
      return (unsigned int)-2147483624;
    v10 = a1 + 120;
    v5 = (__int64 *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v10);
    v6 = v5;
    if ( a2 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v5);
      AgileReference = RoGetAgileReference(0, &GUID_c2b7624c_9f35_5074_8021_0633184899a7, a2, v6);
      if ( AgileReference < 0 )
        return (unsigned int)AgileReference;
    }
    else
    {
      v10 = *v5;
      v11 = 0;
      *v5 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
      AgileReference = 0;
    }
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceDelegateAssigned(a1);
    if ( a2 )
    {
      *(_QWORD *)(a1 + 128) = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 136));
    }
    _InterlockedOr(v9, 0);
    v7 = *(_DWORD *)(a1 + 56);
    LODWORD(v10) = -2;
    _InterlockedCompareExchange((volatile signed __int32 *)&v10, v7, -2);
    if ( (unsigned int)(v10 - 1) <= 3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
  }
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x180016550  mov     [rsp+arg_0], rbx
0x180016555  mov     [rsp+arg_8], rsi
0x18001655a  push    rdi
0x18001655b  sub     rsp, 20h
0x18001655f  mov     rsi, rdx
0x180016562  mov     rbx, rcx
0x180016565  call    ?CheckValidStateForDelegateCall@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(void)
0x18001656a  mov     edi, eax
0x18001656c  test    eax, eax
0x18001656e  js      loc_18001665B
0x180016574  mov     eax, 1
0x180016579  lock xadd [rbx+14h], eax
0x18001657e  inc     eax
0x180016580  cmp     eax, 1
0x180016583  jnz     loc_180016656
0x180016589  lea     rax, [rbx+78h]
0x18001658d  lea     rcx, [rsp+28h+arg_10]
0x180016592  mov     [rsp+28h+arg_10], rax
0x180016597  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x18001659c  mov     rdi, rax
0x18001659f  test    rsi, rsi
0x1800165a2  jz      short loc_1800165CD
0x1800165a4  mov     rcx, rax
0x1800165a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800165ac  mov     r9, rdi
0x1800165af  lea     rdx, _GUID_c2b7624c_9f35_5074_8021_0633184899a7
0x1800165b6  mov     r8, rsi
0x1800165b9  xor     ecx, ecx
0x1800165bb  call    cs:__imp_RoGetAgileReference
0x1800165c1  mov     edi, eax
0x1800165c3  test    eax, eax
0x1800165c5  js      loc_18001665B
0x1800165cb  jmp     short loc_1800165FB
0x1800165cd  mov     rax, [rax]
0x1800165d0  lea     rcx, [rsp+28h+arg_10]
0x1800165d5  mov     [rsp+28h+arg_10], rax
0x1800165da  mov     [rsp+28h+arg_18], 0
0x1800165e3  mov     qword ptr [rdi], 0
0x1800165ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800165ef  lea     rcx, [rsp+28h+arg_18]
0x1800165f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800165f9  xor     edi, edi
0x1800165fb  mov     rcx, rbx
0x1800165fe  call    ?TraceDelegateAssigned@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVProcessLauncherResult@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceDelegateAssigned(void)
0x180016603  test    rsi, rsi
0x180016606  jz      short loc_18001661D
0x180016608  mov     rax, [rsi]
0x18001660b  mov     rcx, [rax+18h]
0x18001660f  mov     [rbx+80h], rcx
0x180016616  lock inc dword ptr [rbx+88h]
0x18001661d  lock or [rsp+28h+var_28], 0
0x180016622  mov     ecx, [rbx+38h]
0x180016625  mov     dword ptr [rsp+28h+arg_10], 0FFFFFFFEh
0x18001662d  mov     eax, dword ptr [rsp+28h+arg_10]
0x180016631  lock cmpxchg dword ptr [rsp+28h+arg_10], ecx
0x180016637  mov     ecx, dword ptr [rsp+28h+arg_10]
0x18001663b  dec     ecx
0x18001663d  cmp     ecx, 3
0x180016640  ja      short loc_18001665B
0x180016642  mov     rax, [rbx]
0x180016645  mov     rcx, rbx
0x180016648  mov     rax, [rax+80h]
0x18001664f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016654  jmp     short loc_18001665B
0x180016656  mov     edi, 80000018h
0x18001665b  mov     rbx, [rsp+28h+arg_0]
0x180016660  mov     eax, edi
0x180016662  mov     rsi, [rsp+28h+arg_8]
0x180016667  add     rsp, 20h
0x18001666b  pop     rdi
0x18001666c  retn
```
