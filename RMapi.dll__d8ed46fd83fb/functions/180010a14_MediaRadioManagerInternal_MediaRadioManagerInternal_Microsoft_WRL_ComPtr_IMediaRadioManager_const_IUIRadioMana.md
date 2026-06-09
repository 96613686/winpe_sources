# MediaRadioManagerInternal::MediaRadioManagerInternal(Microsoft::WRL::ComPtr<IMediaRadioManager> const &,IUIRadioManagerInternal *)

- ea: `0x180010a14`
- end: `0x180010b10`
- name: `??0MediaRadioManagerInternal@@QEAA@AEBV?$ComPtr@UIMediaRadioManager@@@WRL@Microsoft@@PEAUIUIRadioManagerInternal@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800199f8`

## callees

- `0x180006650`
- `0x180007658`
- `0x1800086d0`
- `0x180010a14`
- `0x180010f80`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180010aa2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180010aa2`

## string_xrefs

- `0x180010afe`: `onecoreuap\net\mobility\radiomanagement\dll\mediaradiomanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct IUnknown *__fastcall MediaRadioManagerInternal::MediaRadioManagerInternal(
        struct IUnknown *a1,
        struct IUnknownVtbl **a2,
        struct IUnknownVtbl *a3)
{
  struct IUnknown *v6; // r8
  int v7; // eax
  unsigned int *v9; // [rsp+20h] [rbp-28h]
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  a1[1].lpVtbl = (struct IUnknownVtbl *)&IMediaRadioManagerInternal::`vftable';
  HIDWORD(a1[2].lpVtbl) = 1;
  a1->lpVtbl = (struct IUnknownVtbl *)&Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMediaRadioManagerNotifySink,IMediaRadioManagerInternal>::`vftable'{for `IMediaRadioManagerNotifySink'};
  a1[1].lpVtbl = (struct IUnknownVtbl *)&Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMediaRadioManagerNotifySink,IMediaRadioManagerInternal>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMediaRadioManagerInternal>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  a1->lpVtbl = (struct IUnknownVtbl *)&MediaRadioManagerInternal::`vftable'{for `IMediaRadioManagerNotifySink'};
  a1[1].lpVtbl = (struct IUnknownVtbl *)&MediaRadioManagerInternal::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMediaRadioManagerInternal>'};
  a1[3].lpVtbl = *a2;
  Microsoft::WRL::ComPtr<IMediaRadioManager>::InternalAddRef(&a1[3]);
  LODWORD(a1[4].lpVtbl) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)&a1[5], 0, 0);
  a1[10].lpVtbl = a3;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_q(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, v6, a1);
  v7 = RMAPI::Advise((RMAPI *)a1[3].lpVtbl, a1, v6, (const struct _GUID *)&a1[4], v9);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x12,
      (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\mediaradiomanager.cpp",
      (const char *)(unsigned int)v7,
      v10);
  return a1;
}

```

## disassembly

```asm
0x180010a14  mov     [rsp+arg_0], rcx
0x180010a19  push    rbx
0x180010a1a  push    rbp
0x180010a1b  push    rsi
0x180010a1c  push    rdi
0x180010a1d  sub     rsp, 28h
0x180010a21  mov     rbp, r8
0x180010a24  mov     rsi, rdx
0x180010a27  mov     rbx, rcx
0x180010a2a  lea     rax, ??_7IMediaRadioManagerInternal@@6B@; const IMediaRadioManagerInternal::`vftable'
0x180010a31  mov     [rcx+8], rax
0x180010a35  mov     dword ptr [rcx+14h], 1
0x180010a3c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMediaRadioManagerNotifySink@@UIMediaRadioManagerInternal@@@WRL@Microsoft@@6BIMediaRadioManagerNotifySink@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMediaRadioManagerNotifySink,IMediaRadioManagerInternal>::`vftable'{for `IMediaRadioManagerNotifySink'}
0x180010a43  mov     [rcx], rax
0x180010a46  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMediaRadioManagerNotifySink@@UIMediaRadioManagerInternal@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMediaRadioManagerInternal@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMediaRadioManagerNotifySink,IMediaRadioManagerInternal>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMediaRadioManagerInternal>'}
0x180010a4d  mov     [rcx+8], rax
0x180010a51  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180010a58  test    rcx, rcx
0x180010a5b  jz      short loc_180010A6A
0x180010a5d  mov     rax, [rcx]
0x180010a60  mov     rax, [rax+8]
0x180010a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a69  nop
0x180010a6a  lea     rax, ??_7MediaRadioManagerInternal@@6BIMediaRadioManagerNotifySink@@@; const MediaRadioManagerInternal::`vftable'{for `IMediaRadioManagerNotifySink'}
0x180010a71  mov     [rbx], rax
0x180010a74  lea     rax, ??_7MediaRadioManagerInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMediaRadioManagerInternal@@@Details@WRL@Microsoft@@@; const MediaRadioManagerInternal::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMediaRadioManagerInternal>'}
0x180010a7b  mov     [rbx+8], rax
0x180010a7f  lea     rdi, [rbx+18h]
0x180010a83  mov     rax, [rsi]
0x180010a86  mov     [rdi], rax
0x180010a89  mov     rcx, rdi
0x180010a8c  call    ?InternalAddRef@?$ComPtr@UIMediaRadioManager@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMediaRadioManager>::InternalAddRef(void)
0x180010a91  nop
0x180010a92  mov     dword ptr [rbx+20h], 0
0x180010a99  lea     rcx, [rbx+28h]; lpCriticalSection
0x180010a9d  xor     r8d, r8d; Flags
0x180010aa0  xor     edx, edx; dwSpinCount
0x180010aa2  call    cs:__imp_InitializeCriticalSectionEx
0x180010aa8  nop
0x180010aa9  mov     [rbx+50h], rbp
0x180010aad  lea     rax, WPP_GLOBAL_Control
0x180010ab4  mov     rcx, cs:WPP_GLOBAL_Control
0x180010abb  cmp     rcx, rax
0x180010abe  jz      short loc_180010AD7
0x180010ac0  test    byte ptr [rcx+1Ch], 4
0x180010ac4  jz      short loc_180010AD7
0x180010ac6  mov     edx, 0Ah
0x180010acb  mov     r9, rbx
0x180010ace  mov     rcx, [rcx+10h]
0x180010ad2  call    WPP_SF_q
0x180010ad7  lea     r9, [rbx+20h]; struct _GUID *
0x180010adb  mov     rdx, rbx; struct IUnknown *
0x180010ade  mov     rcx, [rdi]; this
0x180010ae1  call    ?Advise@RMAPI@@YAJPEAUIUnknown@@0AEBU_GUID@@PEAK@Z; RMAPI::Advise(IUnknown *,IUnknown *,_GUID const &,ulong *)
0x180010ae6  mov     rcx, [rsp+48h]; this
0x180010aeb  test    eax, eax
0x180010aed  js      short loc_180010AFB
0x180010aef  mov     rax, rbx
0x180010af2  add     rsp, 28h
0x180010af6  pop     rdi
0x180010af7  pop     rsi
0x180010af8  pop     rbp
0x180010af9  pop     rbx
0x180010afa  retn
0x180010afb  mov     r9d, eax; char *
0x180010afe  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobility\\radiomanagem"...
0x180010b05  mov     edx, 12h; void *
0x180010b0a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
