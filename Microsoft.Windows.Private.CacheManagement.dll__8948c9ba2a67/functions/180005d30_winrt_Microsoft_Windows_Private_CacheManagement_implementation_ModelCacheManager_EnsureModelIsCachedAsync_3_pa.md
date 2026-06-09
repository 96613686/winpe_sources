# _winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnsureModelIsCachedAsync_::_3_::_parameters_::__parameters_

- ea: `0x180005d30`
- end: `0x180005d85`
- name: `_winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnsureModelIsCachedAsync_::_3_::_parameters_::__parameters_`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001dbc1`

## callees

- `0x180005d30`
- `0x180016298`
- `0x18001629e`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005d7e`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005d7e`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnsureModelIsCachedAsync_::_3_::_parameters_::__parameters_(
        __int64 a1)
{
  volatile signed __int32 *v1; // rbx
  int v3; // eax
  HANDLE ProcessHeap; // rax

  v1 = *(volatile signed __int32 **)(a1 + 8);
  if ( v1 )
  {
    v3 = _InterlockedDecrement(v1 + 6);
    if ( v3 )
    {
      if ( v3 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v1);
    }
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180005d30  mov     [rsp+arg_8], rbx
0x180005d35  push    rdi
0x180005d36  sub     rsp, 20h
0x180005d3a  mov     rbx, [rcx+8]
0x180005d3e  mov     rdi, rcx
0x180005d41  test    rbx, rbx
0x180005d44  jz      short loc_180005D6F
0x180005d46  mov     eax, 0FFFFFFFFh
0x180005d4b  lock xadd [rbx+18h], eax
0x180005d50  sub     eax, 1
0x180005d53  jnz     short loc_180005D7A
0x180005d55  call    WINRT_IMPL_GetProcessHeap
0x180005d5a  mov     rcx, rax; hHeap
0x180005d5d  mov     r8, rbx; lpMem
0x180005d60  xor     edx, edx; dwFlags
0x180005d62  call    WINRT_IMPL_HeapFree
0x180005d67  mov     qword ptr [rdi+8], 0
0x180005d6f  mov     rbx, [rsp+28h+arg_8]
0x180005d74  add     rsp, 20h
0x180005d78  pop     rdi
0x180005d79  retn
0x180005d7a  test    eax, eax
0x180005d7c  jns     short loc_180005D67
0x180005d7e  call    cs:__imp_abort
```
