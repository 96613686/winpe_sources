# winrt::Microsoft::Windows::Workloads::Internal::implementation::CacheManagerInternal::EnsureModelIsCachedAsync(winrt::Microsoft::Windows::Workloads::Internal::ModelKind)

- ea: `0x18002c290`
- end: `0x18002c3d0`
- name: `?EnsureModelIsCachedAsync@CacheManagerInternal@implementation@Internal@Workloads@Windows@Microsoft@winrt@@SA?AUIAsyncAction@Foundation@57@W4ModelKind@34567@@Z`
- size: `320`
- prototype: `char **__fastcall(char **, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002c890`

## callees

- `0x18002c290`
- `0x18003422c`
- `0x180034ef0`
- `0x180035060`
- `0x18003b980`
- `0x18003bed0`

## pseudocode

```c
char **__fastcall winrt::Microsoft::Windows::Workloads::Internal::implementation::CacheManagerInternal::EnsureModelIsCachedAsync(
        char **a1,
        int a2)
{
  _DWORD *v4; // rax
  char *v5; // rbx
  char *v6; // rsi

  v4 = operator new(0x150u);
  v5 = (char *)(v4 + 28);
  v4[81] = a2;
  *((_QWORD *)v4 + 14) = winrt::Microsoft::Windows::Workloads::Internal::implementation::CacheManagerInternal::EnsureModelIsCachedAsync__ResumeCoro_1;
  v4[30] = 65538;
  *(_OWORD *)v4 = 0;
  *((_OWORD *)v4 + 1) = 0;
  *((_OWORD *)v4 + 2) = 0;
  *((_OWORD *)v4 + 3) = 0;
  *((_OWORD *)v4 + 4) = 0;
  *((_OWORD *)v4 + 5) = 0;
  *((_QWORD *)v4 + 12) = 0;
  v6 = (char *)(v4 + 4);
  *((_QWORD *)v4 + 2) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable';
  *((_QWORD *)v4 + 3) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)v4 + 1) = 1;
  *((_QWORD *)v4 + 4) = 0;
  *((_QWORD *)v4 + 5) = 0;
  *((_BYTE *)v4 + 48) = 0;
  *(_QWORD *)v4 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind>::promise_type::`vftable';
  *((_QWORD *)v4 + 7) = 0;
  *((_QWORD *)v4 + 8) = 0;
  __ExceptionPtrCreate((_QWORD *)v4 + 7);
  *((_QWORD *)v5 - 5) = 0;
  *((_QWORD *)v5 - 4) = 0;
  *((_QWORD *)v5 - 3) = 0;
  *((_DWORD *)v5 - 4) = 0;
  *(v5 - 12) = 0;
  *((_QWORD *)v5 - 14) = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind>::promise_type::`vftable';
  *a1 = v6;
  if ( v6 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
  v5[208] = 0;
  winrt::Microsoft::Windows::Workloads::Internal::implementation::CacheManagerInternal::EnsureModelIsCachedAsync__ResumeCoro_1(v5);
  return a1;
}

```

## disassembly

```asm
0x18002c290  mov     [rsp+arg_8], rbx
0x18002c295  mov     [rsp+arg_10], rbp
0x18002c29a  push    rsi
0x18002c29b  push    rdi
0x18002c29c  push    r14
0x18002c29e  sub     rsp, 50h
0x18002c2a2  mov     rax, cs:__security_cookie
0x18002c2a9  xor     rax, rsp
0x18002c2ac  mov     [rsp+68h+var_28], rax
0x18002c2b1  mov     esi, edx
0x18002c2b3  mov     rdi, rcx
0x18002c2b6  mov     [rsp+68h+var_40], rcx
0x18002c2bb  mov     r14d, 0D0h
0x18002c2c1  lea     rcx, [r14+80h]; Size
0x18002c2c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c2cd  mov     [rsp+68h+var_48], rax
0x18002c2d2  lea     rbx, [rax+70h]
0x18002c2d6  mov     [rsp+68h+var_48], rbx
0x18002c2db  mov     [rbx+r14+4], esi
0x18002c2e0  lea     rax, winrt__Microsoft__Windows__Workloads__Internal__implementation__CacheManagerInternal__EnsureModelIsCachedAsync$_ResumeCoro$1
0x18002c2e7  mov     [rbx], rax
0x18002c2ea  mov     dword ptr [rbx+8], 10002h
0x18002c2f1  xorps   xmm0, xmm0
0x18002c2f4  xor     eax, eax
0x18002c2f6  movups  xmmword ptr [rbx-70h], xmm0
0x18002c2fa  movups  xmmword ptr [rbx-60h], xmm0
0x18002c2fe  movups  xmmword ptr [rbx-50h], xmm0
0x18002c302  movups  xmmword ptr [rbx-40h], xmm0
0x18002c306  movups  xmmword ptr [rbx-30h], xmm0
0x18002c30a  movups  xmmword ptr [rbx-20h], xmm0
0x18002c30e  mov     [rbx-10h], rax
0x18002c312  lea     rsi, [rbx-60h]
0x18002c316  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@W4ModelKind@Internal@Workloads@3Microsoft@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Workloads::Internal::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable'
0x18002c31d  mov     [rsi], rax
0x18002c320  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@W4ModelKind@Internal@Workloads@3Microsoft@4@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Workloads::Internal::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18002c327  mov     [rsi+8], rax
0x18002c32b  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18002c332  mov     qword ptr [rbx-68h], 1
0x18002c33a  xor     ebp, ebp
0x18002c33c  mov     [rbx-50h], rbp
0x18002c340  mov     [rbx-48h], rbp
0x18002c344  mov     [rbx-40h], bpl
0x18002c348  lea     rax, ??_7promise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@W4ModelKind@Internal@Workloads@3Microsoft@4@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Workloads::Internal::ModelKind>::promise_type::`vftable'
0x18002c34f  mov     [rbx-70h], rax
0x18002c353  lea     rcx, [rbx-38h]; void *
0x18002c357  mov     [rcx], rbp
0x18002c35a  mov     [rcx+8], rbp
0x18002c35e  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002c363  mov     [rbx-28h], rbp
0x18002c367  mov     [rbx-20h], rbp
0x18002c36b  mov     [rbx-18h], rbp
0x18002c36f  xor     eax, eax
0x18002c371  mov     [rbx-10h], eax
0x18002c374  mov     [rbx-0Ch], al
0x18002c377  lea     rax, ??_7promise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@W4ModelKind@Internal@Workloads@3Microsoft@4@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Workloads::Internal::ModelKind>::promise_type::`vftable'
0x18002c37e  mov     [rbx-70h], rax
0x18002c382  mov     [rdi], rsi
0x18002c385  test    rsi, rsi
0x18002c388  jz      short loc_18002C39B
0x18002c38a  mov     rax, [rsi]
0x18002c38d  mov     rcx, rsi
0x18002c390  mov     rax, [rax+8]
0x18002c394  call    cs:__guard_dispatch_icall_fptr
0x18002c39a  nop
0x18002c39b  xor     eax, eax
0x18002c39d  mov     [rbx+r14], al
0x18002c3a1  mov     rcx, rbx
0x18002c3a4  call    winrt__Microsoft__Windows__Workloads__Internal__implementation__CacheManagerInternal__EnsureModelIsCachedAsync$_ResumeCoro$1
0x18002c3a9  nop
0x18002c3aa  mov     rax, rdi
0x18002c3ad  mov     rcx, [rsp+68h+var_28]
0x18002c3b2  xor     rcx, rsp; StackCookie
0x18002c3b5  call    __security_check_cookie
0x18002c3ba  mov     rbx, [rsp+68h+arg_8]
0x18002c3bf  mov     rbp, [rsp+68h+arg_10]
0x18002c3c7  add     rsp, 50h
0x18002c3cb  pop     r14
0x18002c3cd  pop     rdi
0x18002c3ce  pop     rsi
0x18002c3cf  retn
```
