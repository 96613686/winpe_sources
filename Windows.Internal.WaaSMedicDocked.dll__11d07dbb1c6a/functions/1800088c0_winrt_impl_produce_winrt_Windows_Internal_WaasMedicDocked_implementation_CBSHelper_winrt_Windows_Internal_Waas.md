# winrt::impl::produce<winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper,winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::PerformCorruptionRepair(void * *)

- ea: `0x1800088c0`
- end: `0x1800089fa`
- name: `?PerformCorruptionRepair@?$produce@VCBSHelper@implementation@WaasMedicDocked@Internal@Windows@winrt@@UICBSHelper@3456@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x18000197c`
- `0x180001fde`
- `0x180008230`
- `0x1800088c0`
- `0x18000d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000897e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000897e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper,winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::PerformCorruptionRepair(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rdi
  _QWORD *v4; // rbx
  _QWORD *v5; // rdi
  __int64 result; // rax
  _QWORD *v7; // [rsp+50h] [rbp+8h] BYREF
  _QWORD *v8; // [rsp+58h] [rbp+10h]

  *a2 = 0;
  v3 = (a1 - 16) & -(__int64)(a1 != 0);
  try
  {
    v4 = operator new(0x110u);
    v7 = v4 + 14;
    v4[33] = v3;
    v4[14] = winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair__ResumeCoro_1;
    *((_DWORD *)v4 + 30) = 65538;
    memset_0(v4, 0, 0x70u);
    v5 = v4 + 2;
    v4[2] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<unsigned int>>::`vftable';
    v4[3] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v4[1] = 1;
    v4[4] = 0;
    v4[5] = 0;
    *((_BYTE *)v4 + 48) = 0;
    *v4 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<unsigned int>,void>::`vftable';
    v4[7] = 0;
    v4[8] = 0;
    __ExceptionPtrCreate(v4 + 7);
    v4[9] = 0;
    v4[10] = 0;
    v4[11] = 0;
    *((_DWORD *)v4 + 24) = 0;
    *((_BYTE *)v4 + 100) = 0;
    *v4 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type::`vftable';
    *((_DWORD *)v4 + 26) = 0;
    v8 = v4 + 2;
    if ( v4 != (_QWORD *)-16LL )
      (*(void (__fastcall **)(_QWORD *))(*v5 + 8LL))(v4 + 2);
    *((_BYTE *)v4 + 256) = 0;
    winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair__ResumeCoro_1(v4 + 14);
    *a2 = v5;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800088c0  mov     [rsp+arg_10], rbx
0x1800088c5  push    rsi
0x1800088c6  push    rdi
0x1800088c7  push    r14
0x1800088c9  sub     rsp, 30h
0x1800088cd  mov     r14, rdx
0x1800088d0  mov     qword ptr [rdx], 0
0x1800088d7  lea     rax, [rcx-10h]
0x1800088db  neg     rcx
0x1800088de  sbb     rdi, rdi
0x1800088e1  and     rdi, rax
0x1800088e4  mov     ecx, 110h; Size
0x1800088e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800088ee  mov     rbx, rax
0x1800088f1  mov     [rsp+48h+arg_0], rax
0x1800088f6  lea     rsi, [rax+70h]
0x1800088fa  mov     [rsp+48h+arg_0], rsi
0x1800088ff  mov     [rsi+98h], rdi
0x180008906  lea     rax, winrt__Windows__Internal__WaasMedicDocked__implementation__CBSHelper__PerformCorruptionRepair$_ResumeCoro$1
0x18000890d  mov     [rsi], rax
0x180008910  mov     dword ptr [rsi+8], 10002h
0x180008917  xor     edx, edx; Val
0x180008919  lea     r8d, [rdx+70h]; Size
0x18000891d  mov     rcx, rbx; void *
0x180008920  call    memset_0
0x180008925  lea     rdi, [rbx+10h]
0x180008929  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@I@Foundation@Windows@winrt@@PEAVCBSHelper@implementation@WaasMedicDocked@Internal@34@@experimental@std@@U?$IAsyncOperation@I@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<uint>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<uint>>::`vftable'
0x180008930  mov     [rdi], rax
0x180008933  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@I@Foundation@Windows@winrt@@PEAVCBSHelper@implementation@WaasMedicDocked@Internal@34@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<uint>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18000893a  mov     [rdi+8], rax
0x18000893e  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180008945  mov     qword ptr [rbx+8], 1
0x18000894d  mov     qword ptr [rbx+20h], 0
0x180008955  mov     qword ptr [rbx+28h], 0
0x18000895d  mov     byte ptr [rbx+30h], 0
0x180008961  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@I@Foundation@Windows@winrt@@PEAVCBSHelper@implementation@WaasMedicDocked@Internal@34@@experimental@std@@U?$IAsyncOperation@I@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<uint>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<uint>,void>::`vftable'
0x180008968  mov     [rbx], rax
0x18000896b  lea     rcx, [rbx+38h]
0x18000896f  mov     qword ptr [rcx], 0
0x180008976  mov     qword ptr [rcx+8], 0
0x18000897e  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180008984  mov     qword ptr [rbx+48h], 0
0x18000898c  mov     qword ptr [rbx+50h], 0
0x180008994  mov     qword ptr [rbx+58h], 0
0x18000899c  xor     eax, eax
0x18000899e  mov     [rbx+60h], eax
0x1800089a1  mov     [rbx+64h], al
0x1800089a4  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@I@Foundation@Windows@winrt@@PEAVCBSHelper@implementation@WaasMedicDocked@Internal@34@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<uint>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type::`vftable'
0x1800089ab  mov     [rbx], rax
0x1800089ae  mov     dword ptr [rbx+68h], 0
0x1800089b5  mov     [rsp+48h+arg_8], rdi
0x1800089ba  test    rdi, rdi
0x1800089bd  jz      short loc_1800089CF
0x1800089bf  mov     rax, [rdi]
0x1800089c2  mov     rcx, rdi
0x1800089c5  mov     rax, [rax+8]
0x1800089c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089ce  nop
0x1800089cf  xor     eax, eax
0x1800089d1  mov     [rsi+90h], al
0x1800089d7  mov     rcx, rsi
0x1800089da  call    winrt__Windows__Internal__WaasMedicDocked__implementation__CBSHelper__PerformCorruptionRepair$_ResumeCoro$1
0x1800089df  nop
0x1800089e0  mov     [r14], rdi
0x1800089e3  xor     eax, eax
0x1800089e5  jmp     short loc_1800089EB
0x1800089e7  mov     eax, dword ptr [rsp+48h+arg_0]
0x1800089eb  mov     rbx, [rsp+48h+arg_10]
0x1800089f0  add     rsp, 30h
0x1800089f4  pop     r14
0x1800089f6  pop     rdi
0x1800089f7  pop     rsi
0x1800089f8  retn
```
