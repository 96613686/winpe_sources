# SceneAnalysisEffectDefnImpl::~SceneAnalysisEffectDefnImpl(void)

- ea: `0x1800ac644`
- end: `0x1800ac6d8`
- name: `??1SceneAnalysisEffectDefnImpl@@EEAA@XZ`
- size: `148`
- prototype: `void __fastcall(SceneAnalysisEffectDefnImpl *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800ac720`

## callees

- `0x18000b480`
- `0x18000c0b8`
- `0x18002ae0c`
- `0x18002afd0`
- `0x180030060`
- `0x1800ac644`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac6bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac6bd`

## pseudocode

```c
void __fastcall SceneAnalysisEffectDefnImpl::~SceneAnalysisEffectDefnImpl(SceneAnalysisEffectDefnImpl *this)
{
  char v2; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &SceneAnalysisEffectDefnImpl::`vftable';
  *((_QWORD *)this + 1) = &SceneAnalysisEffectDefnImpl::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &SceneAnalysisEffectDefnImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v2,
    "SceneAnalysisEffectDefnImpl::~SceneAnalysisEffectDefnImpl",
    28);
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 11, WPP_45341311ee633afec8922ce86d82bcb5_Traceguids, this);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v2);
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::IReference<float>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::IReference<float>,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1800ac644  push    rbx
0x1800ac646  sub     rsp, 20h
0x1800ac64a  lea     rax, ??_7SceneAnalysisEffectDefnImpl@@6B@; const SceneAnalysisEffectDefnImpl::`vftable'
0x1800ac651  mov     rbx, rcx
0x1800ac654  mov     [rcx], rax
0x1800ac657  lea     rdx, aSceneanalysise; "SceneAnalysisEffectDefnImpl::~SceneAnal"...
0x1800ac65e  lea     rax, ??_7SceneAnalysisEffectDefnImpl@@6BIWeakReferenceSource@@@; const SceneAnalysisEffectDefnImpl::`vftable'{for `IWeakReferenceSource'}
0x1800ac665  mov     r8d, 1Ch; int
0x1800ac66b  mov     [rcx+8], rax
0x1800ac66f  lea     rax, ??_7SceneAnalysisEffectDefnImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const SceneAnalysisEffectDefnImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800ac676  mov     [rcx+10h], rax
0x1800ac67a  lea     rcx, [rsp+28h+arg_0]; this
0x1800ac67f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ac684  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800ac689  cmp     al, 20h ; ' '
0x1800ac68b  jb      short loc_1800AC6AF
0x1800ac68d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac694  lea     r8, WPP_45341311ee633afec8922ce86d82bcb5_Traceguids
0x1800ac69b  mov     edx, 0Bh
0x1800ac6a0  mov     r9, rbx
0x1800ac6a3  mov     rcx, [rcx+0D8h]
0x1800ac6aa  call    WPP_SF_q
0x1800ac6af  lea     rcx, [rsp+28h+arg_0]; this
0x1800ac6b4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ac6b9  mov     rcx, [rbx+40h]; string
0x1800ac6bd  call    cs:__imp_WindowsDeleteString
0x1800ac6c3  mov     rcx, rbx
0x1800ac6c6  mov     qword ptr [rbx+40h], 0
0x1800ac6ce  add     rsp, 20h
0x1800ac6d2  pop     rbx
0x1800ac6d3  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IReference@M@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::IReference<float>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::IReference<float>,Microsoft::WRL::FtmBase>(void)
```
