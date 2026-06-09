# winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::get_Completed(void * *)

- ea: `0x180008bf0`
- end: `0x180008c69`
- name: `?get_Completed@?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `121`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180008bf0`
- `0x1800162aa`
- `0x1800162b0`
- `0x18001cdf0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::get_Completed(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v2; // rdi
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 result; // rax

  *a2 = 0;
  v2 = a1 + 56;
  if ( !a1 )
    v2 = 72;
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)v2);
  v5 = a1 + 64;
  if ( !a1 )
    v5 = 80;
  v6 = *(_QWORD *)v5;
  if ( *(_QWORD *)v5 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 8LL))(*(_QWORD *)v5);
  ReleaseSRWLockExclusive_0((PSRWLOCK)v2);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180008bf0  mov     [rsp+arg_0], rbx
0x180008bf5  mov     [rsp+arg_8], rsi
0x180008bfa  push    rdi
0x180008bfb  sub     rsp, 20h
0x180008bff  test    rcx, rcx
0x180008c02  mov     qword ptr [rdx], 0
0x180008c09  lea     rdi, [rcx+38h]
0x180008c0d  mov     eax, 48h ; 'H'
0x180008c12  cmovz   rdi, rax
0x180008c16  mov     rbx, rcx
0x180008c19  mov     rcx, rdi; SRWLock
0x180008c1c  mov     rsi, rdx
0x180008c1f  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180008c24  test    rbx, rbx
0x180008c27  lea     rax, [rbx+40h]
0x180008c2b  mov     ecx, 50h ; 'P'
0x180008c30  cmovz   rax, rcx
0x180008c34  mov     rbx, [rax]
0x180008c37  test    rbx, rbx
0x180008c3a  jz      short loc_180008C4C
0x180008c3c  mov     rax, [rbx]
0x180008c3f  mov     rcx, rbx
0x180008c42  mov     rax, [rax+8]
0x180008c46  call    cs:__guard_dispatch_icall_fptr
0x180008c4c  mov     rcx, rdi; SRWLock
0x180008c4f  call    ReleaseSRWLockExclusive_0
0x180008c54  xor     eax, eax
0x180008c56  mov     [rsi], rbx
0x180008c59  mov     rbx, [rsp+28h+arg_0]
0x180008c5e  mov     rsi, [rsp+28h+arg_8]
0x180008c63  add     rsp, 20h
0x180008c67  pop     rdi
0x180008c68  retn
```
