# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem::operator=(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem const &)

- ea: `0x180005a80`
- end: `0x180005b98`
- name: `??4CacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAAAEAU01234567@AEBU01234567@@Z`
- size: `280`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005740`

## callees

- `0x180005a80`
- `0x1800127e0`
- `0x180016298`
- `0x18001629e`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005b91`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005b91`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem::operator=(
        __int64 a1,
        __int64 a2)
{
  struct winrt::impl::hstring_header *v4; // rax
  struct winrt::impl::hstring_header *v5; // rdx
  volatile signed __int32 *v6; // rsi
  struct winrt::impl::hstring_header *v7; // rbp
  int v8; // eax
  HANDLE ProcessHeap; // rax
  char v10; // al
  winrt::impl *v11; // rcx
  struct winrt::impl::hstring_header *v12; // rax
  volatile signed __int32 *v13; // rsi
  struct winrt::impl::hstring_header *v14; // rbp
  int v15; // edi
  HANDLE v16; // rax
  volatile signed __int32 *v17; // rsi
  int v18; // edi
  HANDLE v19; // rax
  __int64 result; // rax

  v4 = winrt::impl::duplicate_hstring(*(winrt::impl **)a2, (struct winrt::impl::hstring_header *)a2);
  v6 = *(volatile signed __int32 **)a1;
  v7 = v4;
  if ( *(_QWORD *)a1 )
  {
    v8 = _InterlockedDecrement(v6 + 6);
    if ( v8 )
    {
      if ( v8 < 0 )
        goto LABEL_21;
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v6);
    }
  }
  *(_QWORD *)a1 = v7;
  v10 = *(_BYTE *)(a1 + 16);
  if ( !*(_BYTE *)(a2 + 16) )
  {
    if ( !v10 )
      goto LABEL_19;
    v17 = *(volatile signed __int32 **)(a1 + 8);
    if ( v17 )
    {
      v18 = _InterlockedDecrement(v17 + 6);
      if ( v18 )
      {
        if ( v18 < 0 )
          goto LABEL_21;
      }
      else
      {
        v19 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v19, 0, (LPVOID)v17);
      }
      *(_QWORD *)(a1 + 8) = 0;
    }
    *(_BYTE *)(a1 + 16) = 0;
    goto LABEL_19;
  }
  v11 = *(winrt::impl **)(a2 + 8);
  if ( !v10 )
  {
    *(_QWORD *)(a1 + 8) = winrt::impl::duplicate_hstring(v11, v5);
    *(_BYTE *)(a1 + 16) = 1;
    goto LABEL_19;
  }
  v12 = winrt::impl::duplicate_hstring(v11, v5);
  v13 = *(volatile signed __int32 **)(a1 + 8);
  v14 = v12;
  if ( !v13 )
    goto LABEL_11;
  v15 = _InterlockedDecrement(v13 + 6);
  if ( v15 )
  {
    if ( v15 >= 0 )
    {
LABEL_11:
      *(_QWORD *)(a1 + 8) = v12;
      goto LABEL_19;
    }
LABEL_21:
    abort();
  }
  v16 = WINRT_IMPL_GetProcessHeap();
  WINRT_IMPL_HeapFree(v16, 0, (LPVOID)v13);
  *(_QWORD *)(a1 + 8) = v14;
LABEL_19:
  result = a1;
  *(_BYTE *)(a1 + 24) = *(_BYTE *)(a2 + 24);
  return result;
}

```

## disassembly

```asm
0x180005a80  mov     [rsp+arg_10], rbx
0x180005a85  mov     [rsp+arg_18], rbp
0x180005a8a  push    rsi
0x180005a8b  push    rdi
0x180005a8c  push    r14
0x180005a8e  sub     rsp, 20h
0x180005a92  mov     rbx, rcx
0x180005a95  mov     r14, rdx
0x180005a98  mov     rcx, [rdx]; this
0x180005a9b  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180005aa0  mov     rsi, [rbx]
0x180005aa3  mov     rbp, rax
0x180005aa6  mov     edi, 0FFFFFFFFh
0x180005aab  test    rsi, rsi
0x180005aae  jz      short loc_180005AD8
0x180005ab0  mov     eax, edi
0x180005ab2  lock xadd [rsi+18h], eax
0x180005ab7  sub     eax, 1
0x180005aba  jnz     short loc_180005AD0
0x180005abc  call    WINRT_IMPL_GetProcessHeap
0x180005ac1  mov     rcx, rax; hHeap
0x180005ac4  mov     r8, rsi; lpMem
0x180005ac7  xor     edx, edx; dwFlags
0x180005ac9  call    WINRT_IMPL_HeapFree
0x180005ace  jmp     short loc_180005AD8
0x180005ad0  test    eax, eax
0x180005ad2  js      loc_180005B91
0x180005ad8  mov     [rbx], rbp
0x180005adb  cmp     byte ptr [r14+10h], 0
0x180005ae0  movzx   eax, byte ptr [rbx+10h]
0x180005ae4  jz      short loc_180005B3A
0x180005ae6  mov     rcx, [r14+8]; this
0x180005aea  test    al, al
0x180005aec  jz      short loc_180005B2B
0x180005aee  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180005af3  mov     rsi, [rbx+8]
0x180005af7  mov     rbp, rax
0x180005afa  test    rsi, rsi
0x180005afd  jz      short loc_180005B25
0x180005aff  lock xadd [rsi+18h], edi
0x180005b04  sub     edi, 1
0x180005b07  jnz     short loc_180005B21
0x180005b09  call    WINRT_IMPL_GetProcessHeap
0x180005b0e  mov     rcx, rax; hHeap
0x180005b11  mov     r8, rsi; lpMem
0x180005b14  xor     edx, edx; dwFlags
0x180005b16  call    WINRT_IMPL_HeapFree
0x180005b1b  mov     [rbx+8], rbp
0x180005b1f  jmp     short loc_180005B6F
0x180005b21  test    edi, edi
0x180005b23  js      short loc_180005B91
0x180005b25  mov     [rbx+8], rbp
0x180005b29  jmp     short loc_180005B6F
0x180005b2b  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180005b30  mov     [rbx+8], rax
0x180005b34  mov     byte ptr [rbx+10h], 1
0x180005b38  jmp     short loc_180005B6F
0x180005b3a  test    al, al
0x180005b3c  jz      short loc_180005B6F
0x180005b3e  mov     rsi, [rbx+8]
0x180005b42  test    rsi, rsi
0x180005b45  jz      short loc_180005B6B
0x180005b47  lock xadd [rsi+18h], edi
0x180005b4c  sub     edi, 1
0x180005b4f  jnz     short loc_180005B8D
0x180005b51  call    WINRT_IMPL_GetProcessHeap
0x180005b56  mov     rcx, rax; hHeap
0x180005b59  mov     r8, rsi; lpMem
0x180005b5c  xor     edx, edx; dwFlags
0x180005b5e  call    WINRT_IMPL_HeapFree
0x180005b63  mov     qword ptr [rbx+8], 0
0x180005b6b  mov     byte ptr [rbx+10h], 0
0x180005b6f  movzx   ecx, byte ptr [r14+18h]
0x180005b74  mov     rax, rbx
0x180005b77  mov     rbp, [rsp+38h+arg_18]
0x180005b7c  mov     [rbx+18h], cl
0x180005b7f  mov     rbx, [rsp+38h+arg_10]
0x180005b84  add     rsp, 20h
0x180005b88  pop     r14
0x180005b8a  pop     rdi
0x180005b8b  pop     rsi
0x180005b8c  retn
0x180005b8d  test    edi, edi
0x180005b8f  jns     short loc_180005B63
0x180005b91  call    cs:__imp_abort
```
