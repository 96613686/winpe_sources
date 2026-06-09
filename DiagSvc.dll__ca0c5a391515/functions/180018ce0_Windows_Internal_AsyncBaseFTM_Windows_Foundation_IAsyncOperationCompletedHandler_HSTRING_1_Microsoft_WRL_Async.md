# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *> *)

- ea: `0x180018ce0`
- end: `0x180018dfd`
- name: `?PutOnComplete@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAU?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@3@@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a5e0`

## callees

- `0x18000517c`
- `0x180015930`
- `0x180016aa0`
- `0x180018ce0`
- `0x180019af8`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180018d4b`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180018d4b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(
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

  AgileReference = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(a1);
  if ( AgileReference >= 0 )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 20)) != 1 )
      return (unsigned int)-2147483624;
    v10 = (__int64 *)(a1 + 120);
    v5 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v10);
    v6 = v5;
    if ( a2 )
    {
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(v5);
      AgileReference = RoGetAgileReference(0, &GUID_b79a741f_7fb5_50ae_9e99_911201ec3d41, a2, v6);
      if ( AgileReference < 0 )
        return (unsigned int)AgileReference;
    }
    else
    {
      v10 = (__int64 *)*v5;
      v11 = 0;
      *v5 = 0;
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease((__int64 *)&v10);
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v11);
      AgileReference = 0;
    }
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceDelegateAssigned(a1);
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
0x180018ce0  mov     [rsp+arg_0], rbx
0x180018ce5  mov     [rsp+arg_8], rsi
0x180018cea  push    rdi
0x180018ceb  sub     rsp, 20h
0x180018cef  mov     rsi, rdx
0x180018cf2  mov     rbx, rcx
0x180018cf5  call    ?CheckValidStateForDelegateCall@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(void)
0x180018cfa  mov     edi, eax
0x180018cfc  test    eax, eax
0x180018cfe  js      loc_180018DEB
0x180018d04  mov     eax, 1
0x180018d09  lock xadd [rbx+14h], eax
0x180018d0e  inc     eax
0x180018d10  cmp     eax, 1
0x180018d13  jnz     loc_180018DE6
0x180018d19  lea     rax, [rbx+78h]
0x180018d1d  lea     rcx, [rsp+28h+arg_10]
0x180018d22  mov     [rsp+28h+arg_10], rax
0x180018d27  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x180018d2c  mov     rdi, rax
0x180018d2f  test    rsi, rsi
0x180018d32  jz      short loc_180018D5D
0x180018d34  mov     rcx, rax
0x180018d37  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180018d3c  mov     r9, rdi
0x180018d3f  lea     rdx, _GUID_b79a741f_7fb5_50ae_9e99_911201ec3d41
0x180018d46  mov     r8, rsi
0x180018d49  xor     ecx, ecx
0x180018d4b  call    cs:__imp_RoGetAgileReference
0x180018d51  mov     edi, eax
0x180018d53  test    eax, eax
0x180018d55  js      loc_180018DEB
0x180018d5b  jmp     short loc_180018D8B
0x180018d5d  mov     rax, [rax]
0x180018d60  lea     rcx, [rsp+28h+arg_10]
0x180018d65  mov     [rsp+28h+arg_10], rax
0x180018d6a  mov     [rsp+28h+arg_18], 0
0x180018d73  mov     qword ptr [rdi], 0
0x180018d7a  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180018d7f  lea     rcx, [rsp+28h+arg_18]
0x180018d84  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180018d89  xor     edi, edi
0x180018d8b  mov     rcx, rbx
0x180018d8e  call    ?TraceDelegateAssigned@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceDelegateAssigned(void)
0x180018d93  test    rsi, rsi
0x180018d96  jz      short loc_180018DAD
0x180018d98  mov     rax, [rsi]
0x180018d9b  mov     rcx, [rax+18h]
0x180018d9f  mov     [rbx+80h], rcx
0x180018da6  lock inc dword ptr [rbx+88h]
0x180018dad  lock or [rsp+28h+var_28], 0
0x180018db2  mov     ecx, [rbx+38h]
0x180018db5  mov     dword ptr [rsp+28h+arg_10], 0FFFFFFFEh
0x180018dbd  mov     eax, dword ptr [rsp+28h+arg_10]
0x180018dc1  lock cmpxchg dword ptr [rsp+28h+arg_10], ecx
0x180018dc7  mov     ecx, dword ptr [rsp+28h+arg_10]
0x180018dcb  dec     ecx
0x180018dcd  cmp     ecx, 3
0x180018dd0  ja      short loc_180018DEB
0x180018dd2  mov     rax, [rbx]
0x180018dd5  mov     rcx, rbx
0x180018dd8  mov     rax, [rax+80h]
0x180018ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018de4  jmp     short loc_180018DEB
0x180018de6  mov     edi, 80000018h
0x180018deb  mov     rbx, [rsp+28h+arg_0]
0x180018df0  mov     eax, edi
0x180018df2  mov     rsi, [rsp+28h+arg_8]
0x180018df7  add     rsp, 20h
0x180018dfb  pop     rdi
0x180018dfc  retn
```
