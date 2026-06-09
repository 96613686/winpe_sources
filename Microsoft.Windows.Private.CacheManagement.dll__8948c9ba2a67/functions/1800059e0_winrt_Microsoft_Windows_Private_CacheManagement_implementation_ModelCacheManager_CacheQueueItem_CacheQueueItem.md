# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem::~CacheQueueItem(void)

- ea: `0x1800059e0`
- end: `0x180005a78`
- name: `??1CacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAA@XZ`
- size: `152`
- prototype: `void __fastcall(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *__hidden this)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005740`
- `0x1800091e0`
- `0x180009f70`
- `0x18000b700`
- `0x18001db20`
- `0x18001dda0`
- `0x18001f86b`
- `0x18001faf0`

## callees

- `0x1800059e0`
- `0x180016298`
- `0x18001629e`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005a71`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005a71`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem::~CacheQueueItem(
        winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *this)
{
  volatile signed __int32 *v2; // rdi
  int v3; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v5; // rdi
  int v6; // esi
  HANDLE v7; // rax

  if ( *((_BYTE *)this + 16) )
  {
    v2 = (volatile signed __int32 *)*((_QWORD *)this + 1);
    if ( v2 )
    {
      v3 = _InterlockedDecrement(v2 + 6);
      if ( v3 )
      {
        if ( v3 < 0 )
          goto LABEL_13;
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v2);
      }
      *((_QWORD *)this + 1) = 0;
    }
  }
  v5 = *(volatile signed __int32 **)this;
  if ( !*(_QWORD *)this )
    return;
  v6 = _InterlockedDecrement(v5 + 6);
  if ( v6 )
  {
    if ( v6 >= 0 )
      goto LABEL_10;
LABEL_13:
    abort();
  }
  v7 = WINRT_IMPL_GetProcessHeap();
  WINRT_IMPL_HeapFree(v7, 0, (LPVOID)v5);
LABEL_10:
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x1800059e0  mov     [rsp+arg_8], rbx
0x1800059e5  mov     [rsp+arg_10], rsi
0x1800059ea  push    rdi
0x1800059eb  sub     rsp, 20h
0x1800059ef  cmp     byte ptr [rcx+10h], 0
0x1800059f3  mov     rbx, rcx
0x1800059f6  mov     esi, 0FFFFFFFFh
0x1800059fb  jz      short loc_180005A32
0x1800059fd  mov     rdi, [rcx+8]
0x180005a01  test    rdi, rdi
0x180005a04  jz      short loc_180005A32
0x180005a06  mov     eax, esi
0x180005a08  lock xadd [rdi+18h], eax
0x180005a0d  sub     eax, 1
0x180005a10  jnz     short loc_180005A26
0x180005a12  call    WINRT_IMPL_GetProcessHeap
0x180005a17  mov     rcx, rax; hHeap
0x180005a1a  mov     r8, rdi; lpMem
0x180005a1d  xor     edx, edx; dwFlags
0x180005a1f  call    WINRT_IMPL_HeapFree
0x180005a24  jmp     short loc_180005A2A
0x180005a26  test    eax, eax
0x180005a28  js      short loc_180005A71
0x180005a2a  mov     qword ptr [rbx+8], 0
0x180005a32  mov     rdi, [rbx]
0x180005a35  test    rdi, rdi
0x180005a38  jz      short loc_180005A5D
0x180005a3a  lock xadd [rdi+18h], esi
0x180005a3f  sub     esi, 1
0x180005a42  jnz     short loc_180005A6D
0x180005a44  call    WINRT_IMPL_GetProcessHeap
0x180005a49  mov     rcx, rax; hHeap
0x180005a4c  mov     r8, rdi; lpMem
0x180005a4f  xor     edx, edx; dwFlags
0x180005a51  call    WINRT_IMPL_HeapFree
0x180005a56  mov     qword ptr [rbx], 0
0x180005a5d  mov     rbx, [rsp+28h+arg_8]
0x180005a62  mov     rsi, [rsp+28h+arg_10]
0x180005a67  add     rsp, 20h
0x180005a6b  pop     rdi
0x180005a6c  retn
0x180005a6d  test    esi, esi
0x180005a6f  jns     short loc_180005A56
0x180005a71  call    cs:__imp_abort
```
