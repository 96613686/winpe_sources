# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::FaceAnalysis::FaceTracker *>,Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *>>(Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::FaceAnalysis::FaceTracker *>,Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *>>(Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::FaceAnalysis::FaceTracker *>,Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *>>(Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18000cc84`
- end: `0x18000cdbc`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d0ac`

## callees

- `0x18000290c`
- `0x180005660`
- `0x180008318`
- `0x1800085ac`
- `0x18000cc84`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000cd4d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000cd4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd5c`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVFaceTracker_FaceAnalysis_Media_Windows___Foundation_Windows__U__IAsyncOperation_PEAVFaceTracker_FaceAnalysis_Media_Windows___23___YAJPEAU__IAsyncOperation_PEAVFaceTracker_FaceAnalysis_Media_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVFaceTracker_FaceAnalysis_Media_Windows___Foundation_Windows__U__IAsyncOperation_PEAVFaceTracker_FaceAnalysis_Media_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVFaceTracker_FaceAnalysis_Media_Windows___Foundation_Windows__U__IAsyncOperation_PEAVFaceTracker_FaceAnalysis_Media_Windows___23___YAJPEAU__IAsyncOperation_PEAVFaceTracker_FaceAnalysis_Media_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::FaceAnalysis::FaceTracker *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::FaceAnalysis::FaceTracker *>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::FaceAnalysis::FaceTracker *>,Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::FaceAnalysis::FaceTracker *>,Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::FaceAnalysis::FaceTracker *>,Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *>>'::`2'::FTMEventDelegate::`vftable';
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
0x18000cc84  mov     [rsp+arg_10], rbx
0x18000cc89  mov     [rsp+arg_18], rsi
0x18000cc8e  push    rdi
0x18000cc8f  sub     rsp, 20h
0x18000cc93  mov     rsi, rcx
0x18000cc96  mov     qword ptr [rcx], 0
0x18000cc9d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cca4  mov     ecx, 40h ; '@'; unsigned __int64
0x18000cca9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ccae  mov     rbx, rax
0x18000ccb1  mov     [rsp+28h+arg_8], rax
0x18000ccb6  test    rax, rax
0x18000ccb9  jnz     short loc_18000CCC5
0x18000ccbb  mov     edi, 8007000Eh
0x18000ccc0  jmp     loc_18000CDA0
0x18000ccc5  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>::`vftable'
0x18000cccc  mov     [rbx], rax
0x18000cccf  lea     rdi, [rbx+8]
0x18000ccd3  mov     rcx, rdi; this
0x18000ccd6  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000ccdb  mov     dword ptr [rbx+2Ch], 1
0x18000cce2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::FaceAnalysis::FaceTracker *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::FaceAnalysis::FaceTracker *>'}
0x18000cce9  mov     [rbx], rax
0x18000ccec  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::FaceAnalysis::FaceTracker *>,Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *>>(Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000ccf3  mov     [rdi], rax
0x18000ccf6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000ccfd  test    rcx, rcx
0x18000cd00  jz      short loc_18000CD0F
0x18000cd02  mov     rax, [rcx]
0x18000cd05  mov     rax, [rax+8]
0x18000cd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd0e  nop
0x18000cd0f  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::FaceAnalysis::FaceTracker *>,Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *>>(Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::FaceAnalysis::FaceTracker *>'}
0x18000cd16  mov     [rbx], rax
0x18000cd19  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::FaceAnalysis::FaceTracker *>,Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *>>(Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000cd20  mov     [rdi], rax
0x18000cd23  mov     dword ptr [rbx+30h], 0
0x18000cd2a  mov     qword ptr [rbx+38h], 0
0x18000cd32  mov     [rsp+28h+arg_0], rbx
0x18000cd37  mov     [rsp+28h+arg_8], 0
0x18000cd40  mov     r9d, 1F0003h; dwDesiredAccess
0x18000cd46  xor     r8d, r8d; dwFlags
0x18000cd49  xor     edx, edx; lpName
0x18000cd4b  xor     ecx, ecx; lpEventAttributes
0x18000cd4d  call    cs:__imp_CreateEventExW
0x18000cd53  mov     [rbx+38h], rax
0x18000cd57  test    rax, rax
0x18000cd5a  jnz     short loc_18000CD81
0x18000cd5c  call    cs:__imp_GetLastError
0x18000cd62  mov     edi, eax
0x18000cd64  test    eax, eax
0x18000cd66  jle     short loc_18000CD71
0x18000cd68  movzx   edi, ax
0x18000cd6b  or      edi, 80070000h
0x18000cd71  test    edi, edi
0x18000cd73  jns     short loc_18000CD81
0x18000cd75  lea     rcx, [rsp+28h+arg_0]
0x18000cd7a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cd7f  jmp     short loc_18000CDA0
0x18000cd81  mov     rax, [rbx]
0x18000cd84  mov     rcx, rbx
0x18000cd87  mov     rax, [rax+8]
0x18000cd8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd90  nop
0x18000cd91  mov     [rsi], rbx
0x18000cd94  lea     rcx, [rsp+28h+arg_0]
0x18000cd99  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cd9e  xor     edi, edi
0x18000cda0  lea     rcx, [rsp+28h+arg_8]
0x18000cda5  call    ??1?$MakeAllocator@VHighDynamicRangeControlImpl@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<HighDynamicRangeControlImpl>::~MakeAllocator<HighDynamicRangeControlImpl>(void)
0x18000cdaa  mov     eax, edi
0x18000cdac  mov     rbx, [rsp+28h+arg_10]
0x18000cdb1  mov     rsi, [rsp+28h+arg_18]
0x18000cdb6  add     rsp, 20h
0x18000cdba  pop     rdi
0x18000cdbb  retn
```
