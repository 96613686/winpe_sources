# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(void)

- ea: `0x180019580`
- end: `0x1800195fe`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `126`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180019400`
- `0x180019610`
- `0x180019620`
- `0x180019640`
- `0x180019660`
- `0x180019680`
- `0x1800196a0`
- `0x1800196c0`

## callees

- `0x180010bc4`
- `0x180019580`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(
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
0x180019580  push    rbx
0x180019582  sub     rsp, 20h
0x180019586  mov     rax, [rcx+0E0h]
0x18001958d  mov     r10, rcx
0x180019590  test    rax, rax
0x180019593  js      short loc_1800195B4
0x180019595  cmp     eax, 7FFFFFFFh
0x18001959a  jz      short loc_1800195AD
0x18001959c  lea     rbx, [rax-1]
0x1800195a0  lock cmpxchg [rcx+0E0h], rbx
0x1800195a9  jnz     short loc_180019590
0x1800195ab  jmp     short loc_1800195C3
0x1800195ad  mov     ebx, 7FFFFFFEh
0x1800195b2  jmp     short loc_1800195F6
0x1800195b4  lea     rcx, ds:10h[rax*2]; this
0x1800195bc  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x1800195c1  mov     ebx, eax
0x1800195c3  test    ebx, ebx
0x1800195c5  jnz     short loc_1800195F6
0x1800195c7  test    r10, r10
0x1800195ca  jz      short loc_1800195DE
0x1800195cc  mov     rcx, [r10]
0x1800195cf  lea     edx, [rbx+1]
0x1800195d2  mov     rax, [rcx+58h]
0x1800195d6  mov     rcx, r10
0x1800195d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195de  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800195e5  test    rcx, rcx
0x1800195e8  jz      short loc_1800195F6
0x1800195ea  mov     rax, [rcx]
0x1800195ed  mov     rax, [rax+10h]
0x1800195f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195f6  mov     eax, ebx
0x1800195f8  add     rsp, 20h
0x1800195fc  pop     rbx
0x1800195fd  retn
```
