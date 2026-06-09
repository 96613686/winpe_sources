# _winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync_::_22_::_parameters_::__parameters_

- ea: `0x180006040`
- end: `0x1800060d4`
- name: `_winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync_::_22_::_parameters_::__parameters_`
- size: `148`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001c7a0`
- `0x18001dc8d`

## callees

- `0x180006040`
- `0x180016298`
- `0x18001629e`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800060cd`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800060cd`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync_::_22_::_parameters_::__parameters_(
        __int64 a1)
{
  volatile signed __int32 *v1; // rdi
  int v3; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v5; // rdi
  signed __int32 v6; // esi
  HANDLE v7; // rax

  v1 = *(volatile signed __int32 **)(a1 + 16);
  if ( v1 )
  {
    v3 = _InterlockedDecrement(v1 + 6);
    if ( v3 )
    {
      if ( v3 < 0 )
        goto LABEL_12;
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v1);
    }
    *(_QWORD *)(a1 + 16) = 0;
  }
  v5 = *(volatile signed __int32 **)(a1 + 8);
  if ( !v5 )
    return;
  v6 = _InterlockedExchangeAdd(v5 + 6, 0xFFFFFFFF);
  if ( v6 != 1 )
  {
    if ( v6 - 1 >= 0 )
      goto LABEL_9;
LABEL_12:
    abort();
  }
  v7 = WINRT_IMPL_GetProcessHeap();
  WINRT_IMPL_HeapFree(v7, 0, (LPVOID)v5);
LABEL_9:
  *(_QWORD *)(a1 + 8) = 0;
}

```

## disassembly

```asm
0x180006040  mov     [rsp+arg_8], rbx
0x180006045  mov     [rsp+arg_10], rsi
0x18000604a  push    rdi
0x18000604b  sub     rsp, 20h
0x18000604f  mov     rdi, [rcx+10h]
0x180006053  mov     rbx, rcx
0x180006056  mov     esi, 0FFFFFFFFh
0x18000605b  test    rdi, rdi
0x18000605e  jz      short loc_18000608C
0x180006060  mov     eax, esi
0x180006062  lock xadd [rdi+18h], eax
0x180006067  sub     eax, 1
0x18000606a  jnz     short loc_180006080
0x18000606c  call    WINRT_IMPL_GetProcessHeap
0x180006071  mov     rcx, rax; hHeap
0x180006074  mov     r8, rdi; lpMem
0x180006077  xor     edx, edx; dwFlags
0x180006079  call    WINRT_IMPL_HeapFree
0x18000607e  jmp     short loc_180006084
0x180006080  test    eax, eax
0x180006082  js      short loc_1800060CD
0x180006084  mov     qword ptr [rbx+10h], 0
0x18000608c  mov     rdi, [rbx+8]
0x180006090  test    rdi, rdi
0x180006093  jz      short loc_1800060BB
0x180006095  lock xadd [rdi+18h], esi
0x18000609a  lea     eax, [rsi-1]
0x18000609d  test    eax, eax
0x18000609f  jnz     short loc_1800060CB
0x1800060a1  call    WINRT_IMPL_GetProcessHeap
0x1800060a6  mov     rcx, rax; hHeap
0x1800060a9  mov     r8, rdi; lpMem
0x1800060ac  xor     edx, edx; dwFlags
0x1800060ae  call    WINRT_IMPL_HeapFree
0x1800060b3  mov     qword ptr [rbx+8], 0
0x1800060bb  mov     rbx, [rsp+28h+arg_8]
0x1800060c0  mov     rsi, [rsp+28h+arg_10]
0x1800060c5  add     rsp, 20h
0x1800060c9  pop     rdi
0x1800060ca  retn
0x1800060cb  jns     short loc_1800060B3
0x1800060cd  call    cs:__imp_abort
```
