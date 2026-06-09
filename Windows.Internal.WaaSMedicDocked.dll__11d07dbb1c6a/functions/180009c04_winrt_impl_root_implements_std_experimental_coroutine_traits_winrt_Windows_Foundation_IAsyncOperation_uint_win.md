# winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<uint>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<uint>,winrt::Windows::Foundation::IAsyncInfo>::subtract_reference(void)

- ea: `0x180009c04`
- end: `0x180009c89`
- name: `?subtract_reference@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@I@Foundation@Windows@winrt@@PEAVCBSHelper@implementation@WaasMedicDocked@Internal@34@@experimental@std@@U?$IAsyncOperation@I@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@IEAAIXZ`
- size: `133`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180008e60`
- `0x180008eb0`
- `0x18000917c`

## callees

- `0x180001940`
- `0x180009c04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180009c82`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180009c82`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<unsigned int>,winrt::Windows::Foundation::IAsyncInfo>::subtract_reference(
        __int64 a1)
{
  signed __int64 v1; // rax
  unsigned __int32 v3; // edx
  signed __int64 v4; // rtt
  volatile signed __int32 *v5; // rcx
  signed __int32 v6; // edi

  v1 = *(_QWORD *)(a1 + 8);
  while ( v1 >= 0 )
  {
    v3 = v1 - 1;
    v4 = v1;
    v1 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8), v1 - 1, v1);
    if ( v4 == v1 )
      goto LABEL_11;
  }
  v5 = (volatile signed __int32 *)(2 * v1);
  v6 = _InterlockedDecrement((volatile signed __int32 *)(2 * v1 + 24));
  if ( !v6 && _InterlockedExchangeAdd(v5 + 7, 0xFFFFFFFF) == 1 && v5 )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      abort();
    operator delete((void *)v5);
  }
  v3 = v6;
LABEL_11:
  if ( !v3 )
    *(_QWORD *)(a1 + 8) = 1;
  return v3;
}

```

## disassembly

```asm
0x180009c04  mov     [rsp+arg_0], rbx
0x180009c09  push    rdi
0x180009c0a  sub     rsp, 20h
0x180009c0e  mov     rax, [rcx+8]
0x180009c12  mov     rbx, rcx
0x180009c15  test    rax, rax
0x180009c18  js      short loc_180009C28
0x180009c1a  lea     rdx, [rax-1]
0x180009c1e  lock cmpxchg [rcx+8], rdx
0x180009c24  jnz     short loc_180009C15
0x180009c26  jmp     short loc_180009C65
0x180009c28  or      edx, 0FFFFFFFFh
0x180009c2b  lea     rcx, [rax+rax]; void *
0x180009c2f  mov     edi, edx
0x180009c31  lock xadd [rcx+18h], edi
0x180009c36  sub     edi, 1
0x180009c39  jnz     short loc_180009C63
0x180009c3b  mov     eax, edx
0x180009c3d  lock xadd [rcx+1Ch], eax
0x180009c42  cmp     eax, 1
0x180009c45  jnz     short loc_180009C63
0x180009c47  test    rcx, rcx
0x180009c4a  jz      short loc_180009C63
0x180009c4c  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, edx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180009c54  sub     edx, eax
0x180009c56  jnz     short loc_180009C7E
0x180009c58  nop
0x180009c59  mov     edx, 20h ; ' '; unsigned __int64
0x180009c5e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009c63  mov     edx, edi
0x180009c65  test    edx, edx
0x180009c67  jnz     short loc_180009C71
0x180009c69  mov     qword ptr [rbx+8], 1
0x180009c71  mov     rbx, [rsp+28h+arg_0]
0x180009c76  mov     eax, edx
0x180009c78  add     rsp, 20h
0x180009c7c  pop     rdi
0x180009c7d  retn
0x180009c7e  test    edx, edx
0x180009c80  jns     short loc_180009C59
0x180009c82  call    cs:__imp_abort
```
