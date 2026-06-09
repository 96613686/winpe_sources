# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(void)

- ea: `0x180016a10`
- end: `0x180016a8e`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `126`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180016930`
- `0x180016aa0`
- `0x180016ab0`
- `0x180016ad0`
- `0x180016af0`
- `0x180016b10`
- `0x180016b30`
- `0x180016b50`

## callees

- `0x18000ce30`
- `0x180016a10`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(
        __int64 a1,
        volatile int *a2)
{
  signed __int64 v2; // rax
  __int64 v3; // r10
  unsigned int v4; // ebx
  signed __int64 v5; // rtt

  v2 = *(_QWORD *)(a1 + 224);
  v3 = a1;
  while ( v2 >= 0 )
  {
    if ( (_DWORD)v2 == 0x7FFFFFFF )
      return 2147483646;
    v4 = v2 - 1;
    v5 = v2;
    v2 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 224), v2 - 1, v2);
    if ( v5 == v2 )
      goto LABEL_8;
  }
  v4 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(2 * v2 + 16), a2);
LABEL_8:
  if ( !v4 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 88LL))(v3, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v4;
}

```

## disassembly

```asm
0x180016a10  push    rbx
0x180016a12  sub     rsp, 20h
0x180016a16  mov     rax, [rcx+0E0h]
0x180016a1d  mov     r10, rcx
0x180016a20  test    rax, rax
0x180016a23  js      short loc_180016A44
0x180016a25  cmp     eax, 7FFFFFFFh
0x180016a2a  jz      short loc_180016A3D
0x180016a2c  lea     rbx, [rax-1]
0x180016a30  lock cmpxchg [rcx+0E0h], rbx
0x180016a39  jnz     short loc_180016A20
0x180016a3b  jmp     short loc_180016A53
0x180016a3d  mov     ebx, 7FFFFFFEh
0x180016a42  jmp     short loc_180016A86
0x180016a44  lea     rcx, ds:10h[rax*2]; this
0x180016a4c  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x180016a51  mov     ebx, eax
0x180016a53  test    ebx, ebx
0x180016a55  jnz     short loc_180016A86
0x180016a57  test    r10, r10
0x180016a5a  jz      short loc_180016A6E
0x180016a5c  mov     rcx, [r10]
0x180016a5f  lea     edx, [rbx+1]
0x180016a62  mov     rax, [rcx+58h]
0x180016a66  mov     rcx, r10
0x180016a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a6e  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180016a75  test    rcx, rcx
0x180016a78  jz      short loc_180016A86
0x180016a7a  mov     rax, [rcx]
0x180016a7d  mov     rax, [rax+10h]
0x180016a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a86  mov     eax, ebx
0x180016a88  add     rsp, 20h
0x180016a8c  pop     rbx
0x180016a8d  retn
```
