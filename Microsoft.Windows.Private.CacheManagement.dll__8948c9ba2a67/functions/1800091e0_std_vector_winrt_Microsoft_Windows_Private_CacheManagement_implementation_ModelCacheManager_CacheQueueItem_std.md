# std::vector<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem,std::allocator<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem>>::~vector<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem,std::allocator<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem>>(void)

- ea: `0x1800091e0`
- end: `0x180009280`
- name: `??1?$vector@UCacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@V?$allocator@UCacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@std@@@std@@QEAA@XZ`
- size: `160`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800050f0`
- `0x18001d9ec`

## callees

- `0x1800059e0`
- `0x1800091e0`
- `0x180018238`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180009279`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180009279`

## pseudocode

```c
void __fastcall std::vector<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem>::~vector<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem>(
        __int64 a1)
{
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *v1; // rbx
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *i; // rdi
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *v4; // rcx
  unsigned __int64 v5; // rdx

  v1 = *(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem **)a1;
  if ( *(_QWORD *)a1 )
  {
    for ( i = *(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem **)(a1 + 8);
          v1 != i;
          v1 = (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)((char *)v1 + 32) )
    {
      winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem::~CacheQueueItem(v1);
    }
    v4 = *(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem **)a1;
    v5 = (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFE0uLL;
    if ( v5 >= 0x1000 )
    {
      _mm_lfence();
      v5 += 39LL;
      if ( (unsigned __int64)v4 - *((_QWORD *)v4 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v4 = (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)*((_QWORD *)v4 - 1);
    }
    operator delete(v4, v5);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x1800091e0  mov     [rsp+arg_10], rbx
0x1800091e5  push    rsi
0x1800091e6  sub     rsp, 30h
0x1800091ea  mov     rbx, [rcx]
0x1800091ed  mov     rsi, rcx
0x1800091f0  test    rbx, rbx
0x1800091f3  jz      short loc_18000925D
0x1800091f5  mov     [rsp+38h+arg_8], rdi
0x1800091fa  mov     rdi, [rcx+8]
0x1800091fe  cmp     rbx, rdi
0x180009201  jz      short loc_180009214
0x180009203  mov     rcx, rbx; this
0x180009206  call    ??1CacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem::~CacheQueueItem(void)
0x18000920b  add     rbx, 20h ; ' '
0x18000920f  cmp     rbx, rdi
0x180009212  jnz     short loc_180009203
0x180009214  mov     rcx, [rsi]
0x180009217  mov     rdx, [rsi+10h]
0x18000921b  mov     rdi, [rsp+38h+arg_8]
0x180009220  sub     rdx, rcx
0x180009223  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180009227  cmp     rdx, 1000h
0x18000922e  jb      short loc_18000924B
0x180009230  lfence
0x180009233  mov     rax, [rcx-8]
0x180009237  add     rdx, 27h ; '''; unsigned __int64
0x18000923b  sub     rcx, rax
0x18000923e  sub     rcx, 8
0x180009242  cmp     rcx, 1Fh
0x180009246  ja      short loc_180009268
0x180009248  mov     rcx, rax; void *
0x18000924b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009250  xor     eax, eax
0x180009252  mov     [rsi], rax
0x180009255  mov     [rsi+8], rax
0x180009259  mov     [rsi+10h], rax
0x18000925d  mov     rbx, [rsp+38h+arg_10]
0x180009262  add     rsp, 30h
0x180009266  pop     rsi
0x180009267  retn
0x180009268  xor     eax, eax
0x18000926a  xor     r9d, r9d; LineNo
0x18000926d  xor     r8d, r8d; FileName
0x180009270  mov     [rsp+38h+Reserved], rax; Reserved
0x180009275  xor     edx, edx; FunctionName
0x180009277  xor     ecx, ecx; Expression
0x180009279  call    cs:__imp__invoke_watson
```
