# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18000cb44`
- end: `0x18000cc7c`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cf1c`

## callees

- `0x18000290c`
- `0x180005660`
- `0x180008318`
- `0x1800085ac`
- `0x18000cb44`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000cc0d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000cc0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVector_PEAVDetectedFace_FaceAnalysis_Media_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVector_PEAVDetectedFace_FaceAnalysis_Media_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVector_PEAVDetectedFace_FaceAnalysis_Media_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVector_PEAVDetectedFace_FaceAnalysis_Media_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVector_PEAVDetectedFace_FaceAnalysis_Media_Windows___Collections_Foundation_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVector_PEAVDetectedFace_FaceAnalysis_Media_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVector_PEAVDetectedFace_FaceAnalysis_Media_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVector_PEAVDetectedFace_FaceAnalysis_Media_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  signed int v3; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  _DWORD *v7; // [rsp+30h] [rbp+8h] BYREF
  _DWORD *v8; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>>'::`2'::FTMEventDelegate::`vftable';
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v7 = v2;
    v8 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    *((_QWORD *)v2 + 7) = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_10:
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
      *a1 = v2;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<HighDynamicRangeControlImpl>::~MakeAllocator<HighDynamicRangeControlImpl>(&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000cb44  mov     [rsp+arg_10], rbx
0x18000cb49  mov     [rsp+arg_18], rsi
0x18000cb4e  push    rdi
0x18000cb4f  sub     rsp, 20h
0x18000cb53  mov     rsi, rcx
0x18000cb56  mov     qword ptr [rcx], 0
0x18000cb5d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cb64  mov     ecx, 40h ; '@'; unsigned __int64
0x18000cb69  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000cb6e  mov     rbx, rax
0x18000cb71  mov     [rsp+28h+arg_8], rax
0x18000cb76  test    rax, rax
0x18000cb79  jnz     short loc_18000CB85
0x18000cb7b  mov     edi, 8007000Eh
0x18000cb80  jmp     loc_18000CC60
0x18000cb85  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>::`vftable'
0x18000cb8c  mov     [rbx], rax
0x18000cb8f  lea     rdi, [rbx+8]
0x18000cb93  mov     rcx, rdi; this
0x18000cb96  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000cb9b  mov     dword ptr [rbx+2Ch], 1
0x18000cba2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>'}
0x18000cba9  mov     [rbx], rax
0x18000cbac  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000cbb3  mov     [rdi], rax
0x18000cbb6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000cbbd  test    rcx, rcx
0x18000cbc0  jz      short loc_18000CBCF
0x18000cbc2  mov     rax, [rcx]
0x18000cbc5  mov     rax, [rax+8]
0x18000cbc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbce  nop
0x18000cbcf  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>'}
0x18000cbd6  mov     [rbx], rax
0x18000cbd9  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000cbe0  mov     [rdi], rax
0x18000cbe3  mov     dword ptr [rbx+30h], 0
0x18000cbea  mov     qword ptr [rbx+38h], 0
0x18000cbf2  mov     [rsp+28h+arg_0], rbx
0x18000cbf7  mov     [rsp+28h+arg_8], 0
0x18000cc00  mov     r9d, 1F0003h; dwDesiredAccess
0x18000cc06  xor     r8d, r8d; dwFlags
0x18000cc09  xor     edx, edx; lpName
0x18000cc0b  xor     ecx, ecx; lpEventAttributes
0x18000cc0d  call    cs:__imp_CreateEventExW
0x18000cc13  mov     [rbx+38h], rax
0x18000cc17  test    rax, rax
0x18000cc1a  jnz     short loc_18000CC41
0x18000cc1c  call    cs:__imp_GetLastError
0x18000cc22  mov     edi, eax
0x18000cc24  test    eax, eax
0x18000cc26  jle     short loc_18000CC31
0x18000cc28  movzx   edi, ax
0x18000cc2b  or      edi, 80070000h
0x18000cc31  test    edi, edi
0x18000cc33  jns     short loc_18000CC41
0x18000cc35  lea     rcx, [rsp+28h+arg_0]
0x18000cc3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cc3f  jmp     short loc_18000CC60
0x18000cc41  mov     rax, [rbx]
0x18000cc44  mov     rcx, rbx
0x18000cc47  mov     rax, [rax+8]
0x18000cc4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc50  nop
0x18000cc51  mov     [rsi], rbx
0x18000cc54  lea     rcx, [rsp+28h+arg_0]
0x18000cc59  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cc5e  xor     edi, edi
0x18000cc60  lea     rcx, [rsp+28h+arg_8]
0x18000cc65  call    ??1?$MakeAllocator@VHighDynamicRangeControlImpl@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<HighDynamicRangeControlImpl>::~MakeAllocator<HighDynamicRangeControlImpl>(void)
0x18000cc6a  mov     eax, edi
0x18000cc6c  mov     rbx, [rsp+28h+arg_10]
0x18000cc71  mov     rsi, [rsp+28h+arg_18]
0x18000cc76  add     rsp, 20h
0x18000cc7a  pop     rdi
0x18000cc7b  retn
```
