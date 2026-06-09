# winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<uint>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<uint>>::get_Completed(void * *)

- ea: `0x1800093a0`
- end: `0x18000941f`
- name: `?get_Completed@?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@I@Foundation@Windows@winrt@@PEAVCBSHelper@implementation@WaasMedicDocked@Internal@34@@experimental@std@@U?$IAsyncOperation@I@Foundation@Windows@winrt@@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002088`
- `0x180002094`
- `0x1800093a0`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<unsigned int>>::get_Completed(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rbx

  *a2 = 0;
  v4 = a1 + 56;
  if ( !a1 )
    v4 = 72;
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)v4);
  v5 = a1 + 64;
  if ( !a1 )
    v5 = 80;
  v6 = *(_QWORD *)v5;
  if ( *(_QWORD *)v5 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 8LL))(*(_QWORD *)v5);
  ReleaseSRWLockExclusive_0((PSRWLOCK)v4);
  *a2 = v6;
  return 0;
}

```

## disassembly

```asm
0x1800093a0  mov     [rsp+arg_8], rbx
0x1800093a5  mov     [rsp+arg_10], rsi
0x1800093aa  push    rdi
0x1800093ab  sub     rsp, 20h
0x1800093af  mov     rdi, rdx
0x1800093b2  mov     rbx, rcx
0x1800093b5  mov     qword ptr [rdx], 0
0x1800093bc  lea     rsi, [rcx+38h]
0x1800093c0  mov     eax, 48h ; 'H'
0x1800093c5  test    rcx, rcx
0x1800093c8  cmovz   rsi, rax
0x1800093cc  mov     rcx, rsi; SRWLock
0x1800093cf  call    WINRT_IMPL_AcquireSRWLockExclusive
0x1800093d4  lea     rax, [rbx+40h]
0x1800093d8  mov     ecx, 50h ; 'P'
0x1800093dd  test    rbx, rbx
0x1800093e0  cmovz   rax, rcx
0x1800093e4  mov     rbx, [rax]
0x1800093e7  test    rbx, rbx
0x1800093ea  jz      short loc_1800093FB
0x1800093ec  mov     rax, [rbx]
0x1800093ef  mov     rcx, rbx
0x1800093f2  mov     rax, [rax+8]
0x1800093f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093fb  mov     rcx, rsi; SRWLock
0x1800093fe  call    ReleaseSRWLockExclusive_0
0x180009403  mov     [rdi], rbx
0x180009406  xor     eax, eax
0x180009408  jmp     short loc_18000940E
0x18000940a  mov     eax, [rsp+28h+arg_0]
0x18000940e  mov     rbx, [rsp+28h+arg_8]
0x180009413  mov     rsi, [rsp+28h+arg_10]
0x180009418  add     rsp, 20h
0x18000941c  pop     rdi
0x18000941d  retn
```
