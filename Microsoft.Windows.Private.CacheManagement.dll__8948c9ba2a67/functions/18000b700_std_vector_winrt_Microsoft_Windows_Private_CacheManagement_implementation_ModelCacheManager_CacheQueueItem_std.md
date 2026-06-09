# std::vector<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem,std::allocator<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x18000b700`
- end: `0x18000b799`
- name: `??1_Reallocation_guard@?$vector@UCacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@V?$allocator@UCacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@std@@@std@@QEAA@XZ`
- size: `153`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001e390`

## callees

- `0x1800059e0`
- `0x18000b700`
- `0x180018238`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000b792`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000b792`

## pseudocode

```c
void __fastcall std::vector<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *v2; // rbx
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *i; // rdi
  _QWORD *v4; // rcx
  unsigned __int64 v5; // rdx

  if ( a1[1] )
  {
    v2 = (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)a1[3];
    for ( i = (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)a1[4];
          v2 != i;
          v2 = (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)((char *)v2 + 32) )
    {
      winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem::~CacheQueueItem(v2);
    }
    v4 = (_QWORD *)a1[1];
    v5 = 32LL * a1[2];
    if ( v5 >= 0x1000 )
    {
      v5 += 39LL;
      if ( (unsigned __int64)v4 - *(v4 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v4 = (_QWORD *)*(v4 - 1);
    }
    operator delete(v4, v5);
  }
}

```

## disassembly

```asm
0x18000b700  push    rsi
0x18000b702  sub     rsp, 30h
0x18000b706  cmp     qword ptr [rcx+8], 0
0x18000b70b  mov     rsi, rcx
0x18000b70e  jz      short loc_18000B779
0x18000b710  mov     [rsp+38h+arg_8], rbx
0x18000b715  mov     rbx, [rcx+18h]
0x18000b719  mov     [rsp+38h+arg_10], rdi
0x18000b71e  mov     rdi, [rcx+20h]
0x18000b722  cmp     rbx, rdi
0x18000b725  jz      short loc_18000B738
0x18000b727  mov     rcx, rbx; this
0x18000b72a  call    ??1CacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem::~CacheQueueItem(void)
0x18000b72f  add     rbx, 20h ; ' '
0x18000b733  cmp     rbx, rdi
0x18000b736  jnz     short loc_18000B727
0x18000b738  mov     rdx, [rsi+10h]
0x18000b73c  mov     rcx, [rsi+8]
0x18000b740  mov     rdi, [rsp+38h+arg_10]
0x18000b745  mov     rbx, [rsp+38h+arg_8]
0x18000b74a  shl     rdx, 5
0x18000b74e  cmp     rdx, 1000h
0x18000b755  jb      short loc_18000B76F
0x18000b757  mov     rax, [rcx-8]
0x18000b75b  add     rdx, 27h ; '''; unsigned __int64
0x18000b75f  sub     rcx, rax
0x18000b762  sub     rcx, 8
0x18000b766  cmp     rcx, 1Fh
0x18000b76a  ja      short loc_18000B77F
0x18000b76c  mov     rcx, rax; void *
0x18000b76f  add     rsp, 30h
0x18000b773  pop     rsi
0x18000b774  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b779  add     rsp, 30h
0x18000b77d  pop     rsi
0x18000b77e  retn
0x18000b77f  xor     r9d, r9d; LineNo
0x18000b782  mov     [rsp+38h+Reserved], 0; Reserved
0x18000b78b  xor     r8d, r8d; FileName
0x18000b78e  xor     edx, edx; FunctionName
0x18000b790  xor     ecx, ecx; Expression
0x18000b792  call    cs:__imp__invoke_watson
```
