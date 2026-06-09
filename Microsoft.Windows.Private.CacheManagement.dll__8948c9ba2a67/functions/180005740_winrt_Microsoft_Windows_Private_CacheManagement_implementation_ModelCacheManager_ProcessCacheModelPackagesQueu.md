# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::ProcessCacheModelPackagesQueue(void)

- ea: `0x180005740`
- end: `0x18000597b`
- name: `?ProcessCacheModelPackagesQueue@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAAXXZ`
- size: `571`
- prototype: `void __fastcall(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180005740`
- `0x1800059e0`
- `0x180005a80`
- `0x180007ed0`
- `0x180016298`
- `0x18001629e`
- `0x1800165b8`
- `0x1800165c0`
- `0x18001700c`
- `0x180017320`
- `0x1800181b0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005954`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005954`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::ProcessCacheModelPackagesQueue(
        winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *this)
{
  struct _Mtx_internal_imp_t *v2; // rsi
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *v3; // rcx
  void *v4; // rdi
  int v5; // eax
  HANDLE ProcessHeap; // rax
  void *v7; // rdi
  int v8; // eax
  HANDLE v9; // rax
  void *v10; // rdi
  int v11; // eax
  HANDLE v12; // rax
  void *v13; // rdi
  signed __int32 v14; // r14d
  HANDLE v15; // rax
  LPVOID v16; // [rsp+30h] [rbp-48h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-40h]
  char v18; // [rsp+40h] [rbp-38h]
  char v19; // [rsp+48h] [rbp-30h]

  if ( !*((_BYTE *)this + 232) )
  {
    v2 = (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *)((char *)this + 80);
    while ( 1 )
    {
      v16 = 0;
      v18 = 0;
      v19 = 0;
      if ( Mtx_lock(v2) )
        std::_Throw_Cpp_error(5);
      if ( *((_DWORD *)this + 39) == 0x7FFFFFFF )
      {
        *((_DWORD *)this + 39) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      while ( *((_QWORD *)this + 5) == *((_QWORD *)this + 6) && !*((_BYTE *)this + 232) )
        Cnd_wait(
          (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *)((char *)this + 160),
          v2);
      if ( *((_BYTE *)this + 232) )
        break;
      winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem::operator=(
        &v16,
        *((_QWORD *)this + 6) - 32LL);
      winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem::~CacheQueueItem((winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)(*((_QWORD *)this + 6) - 32LL));
      *((_QWORD *)this + 6) -= 32LL;
      Mtx_unlock(v2);
      winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::StartWorkloadSessionAndCacheModels_NoThrow(
        v3,
        (const struct winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)&v16);
      if ( v18 )
      {
        v4 = lpMem;
        if ( lpMem )
        {
          v5 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
          if ( v5 )
          {
            if ( v5 < 0 )
              goto LABEL_31;
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, v4);
          }
          lpMem = 0;
        }
      }
      v7 = v16;
      if ( v16 )
      {
        v8 = _InterlockedDecrement((volatile signed __int32 *)v16 + 6);
        if ( v8 )
        {
          if ( v8 < 0 )
            goto LABEL_31;
        }
        else
        {
          v9 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v9, 0, v7);
        }
      }
      if ( *((_BYTE *)this + 232) )
        goto LABEL_20;
    }
    Mtx_unlock(v2);
    if ( v18 )
    {
      v10 = lpMem;
      if ( lpMem )
      {
        v11 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
        if ( v11 )
        {
          if ( v11 < 0 )
            goto LABEL_31;
        }
        else
        {
          v12 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v12, 0, v10);
        }
        lpMem = 0;
      }
    }
    v13 = v16;
    if ( v16 )
    {
      v14 = _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 6, 0xFFFFFFFF);
      if ( v14 == 1 )
      {
        v15 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v15, 0, v13);
        goto LABEL_20;
      }
      if ( v14 - 1 >= 0 )
        goto LABEL_20;
LABEL_31:
      abort();
    }
  }
LABEL_20:
  *((_BYTE *)this + 233) = 0;
}

```

## disassembly

```asm
0x180005740  mov     [rsp+arg_8], rbx
0x180005745  mov     [rsp+arg_10], rbp
0x18000574a  push    rsi
0x18000574b  push    rdi
0x18000574c  push    r14
0x18000574e  sub     rsp, 60h
0x180005752  mov     rax, cs:__security_cookie
0x180005759  xor     rax, rsp
0x18000575c  mov     [rsp+78h+var_28], rax
0x180005761  mov     rbx, rcx
0x180005764  movzx   eax, byte ptr [rcx+0E8h]
0x18000576b  xor     ebp, ebp
0x18000576d  test    al, al
0x18000576f  jnz     loc_1800058B2
0x180005775  lea     rsi, [rcx+50h]
0x180005779  mov     r14d, 0FFFFFFFFh
0x18000577f  nop
0x180005780  xor     eax, eax
0x180005782  mov     [rsp+78h+var_48], rbp
0x180005787  mov     [rsp+78h+var_38], al
0x18000578b  mov     [rsp+78h+var_30], al
0x18000578f  xorps   xmm0, xmm0
0x180005792  movups  [rsp+78h+var_58], xmm0
0x180005797  mov     qword ptr [rsp+78h+var_58], rsi
0x18000579c  mov     byte ptr [rsp+78h+var_58+8], al
0x1800057a0  mov     rcx, rsi; _Mtx_t
0x1800057a3  call    _Mtx_lock
0x1800057a8  test    eax, eax
0x1800057aa  jnz     loc_180005970
0x1800057b0  cmp     dword ptr [rbx+9Ch], 7FFFFFFFh
0x1800057ba  jz      loc_18000595B
0x1800057c0  mov     byte ptr [rsp+78h+var_58+8], 1
0x1800057c5  mov     rax, [rbx+30h]
0x1800057c9  cmp     [rbx+28h], rax
0x1800057cd  jnz     short loc_1800057EB
0x1800057cf  movzx   eax, byte ptr [rbx+0E8h]
0x1800057d6  test    al, al
0x1800057d8  jnz     short loc_1800057EB
0x1800057da  mov     rdx, rsi; _Mtx_t
0x1800057dd  lea     rcx, [rbx+0A0h]; _Cnd_t
0x1800057e4  call    _Cnd_wait
0x1800057e9  jmp     short loc_1800057C5
0x1800057eb  movzx   eax, byte ptr [rbx+0E8h]
0x1800057f2  test    al, al
0x1800057f4  jnz     loc_1800058DB
0x1800057fa  mov     rdx, [rbx+30h]
0x1800057fe  sub     rdx, 20h ; ' '
0x180005802  lea     rcx, [rsp+78h+var_48]
0x180005807  call    ??4CacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAAAEAU01234567@AEBU01234567@@Z; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem::operator=(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem const &)
0x18000580c  mov     rcx, [rbx+30h]
0x180005810  sub     rcx, 20h ; ' '; this
0x180005814  call    ??1CacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem::~CacheQueueItem(void)
0x180005819  add     qword ptr [rbx+30h], 0FFFFFFFFFFFFFFE0h
0x18000581e  mov     rcx, rsi; _Mtx_t
0x180005821  call    _Mtx_unlock
0x180005826  lea     rdx, [rsp+78h+var_48]; struct winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *
0x18000582b  call    ?StartWorkloadSessionAndCacheModels_NoThrow@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAAXAEBUCacheQueueItem@1234567@@Z; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::StartWorkloadSessionAndCacheModels_NoThrow(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem const &)
0x180005830  nop
0x180005831  cmp     [rsp+78h+var_38], 0
0x180005836  jz      short loc_180005870
0x180005838  mov     rdi, [rsp+78h+lpMem]
0x18000583d  test    rdi, rdi
0x180005840  jz      short loc_180005870
0x180005842  mov     eax, r14d
0x180005845  lock xadd [rdi+18h], eax
0x18000584a  sub     eax, 1
0x18000584d  jnz     short loc_180005863
0x18000584f  call    WINRT_IMPL_GetProcessHeap
0x180005854  mov     rcx, rax; hHeap
0x180005857  mov     r8, rdi; lpMem
0x18000585a  xor     edx, edx; dwFlags
0x18000585c  call    WINRT_IMPL_HeapFree
0x180005861  jmp     short loc_18000586B
0x180005863  test    eax, eax
0x180005865  js      loc_180005954
0x18000586b  mov     [rsp+78h+lpMem], rbp
0x180005870  mov     rdi, [rsp+78h+var_48]
0x180005875  test    rdi, rdi
0x180005878  jz      short loc_1800058A3
0x18000587a  mov     eax, r14d
0x18000587d  lock xadd [rdi+18h], eax
0x180005882  sub     eax, 1
0x180005885  jnz     short loc_18000589B
0x180005887  call    WINRT_IMPL_GetProcessHeap
0x18000588c  mov     rcx, rax; hHeap
0x18000588f  mov     r8, rdi; lpMem
0x180005892  xor     edx, edx; dwFlags
0x180005894  call    WINRT_IMPL_HeapFree
0x180005899  jmp     short loc_1800058A3
0x18000589b  test    eax, eax
0x18000589d  js      loc_180005954
0x1800058a3  movzx   eax, byte ptr [rbx+0E8h]
0x1800058aa  test    al, al
0x1800058ac  jz      loc_180005780
0x1800058b2  xchg    bpl, [rbx+0E9h]
0x1800058b9  mov     rcx, [rsp+78h+var_28]
0x1800058be  xor     rcx, rsp; StackCookie
0x1800058c1  call    __security_check_cookie
0x1800058c6  lea     r11, [rsp+78h+var_18]
0x1800058cb  mov     rbx, [r11+28h]
0x1800058cf  mov     rbp, [r11+30h]
0x1800058d3  mov     rsp, r11
0x1800058d6  pop     r14
0x1800058d8  pop     rdi
0x1800058d9  pop     rsi
0x1800058da  retn
0x1800058db  mov     rcx, rsi; _Mtx_t
0x1800058de  call    _Mtx_unlock
0x1800058e3  nop
0x1800058e4  cmp     [rsp+78h+var_38], 0
0x1800058e9  jz      short loc_18000591F
0x1800058eb  mov     rdi, [rsp+78h+lpMem]
0x1800058f0  test    rdi, rdi
0x1800058f3  jz      short loc_18000591F
0x1800058f5  mov     eax, r14d
0x1800058f8  lock xadd [rdi+18h], eax
0x1800058fd  sub     eax, 1
0x180005900  jnz     short loc_180005916
0x180005902  call    WINRT_IMPL_GetProcessHeap
0x180005907  mov     rcx, rax; hHeap
0x18000590a  mov     r8, rdi; lpMem
0x18000590d  xor     edx, edx; dwFlags
0x18000590f  call    WINRT_IMPL_HeapFree
0x180005914  jmp     short loc_18000591A
0x180005916  test    eax, eax
0x180005918  js      short loc_180005954
0x18000591a  mov     [rsp+78h+lpMem], rbp
0x18000591f  mov     rdi, [rsp+78h+var_48]
0x180005924  test    rdi, rdi
0x180005927  jz      short loc_1800058B2
0x180005929  lock xadd [rdi+18h], r14d
0x18000592f  lea     eax, [r14-1]
0x180005933  test    eax, eax
0x180005935  jnz     short loc_18000594E
0x180005937  call    WINRT_IMPL_GetProcessHeap
0x18000593c  mov     rcx, rax; hHeap
0x18000593f  mov     r8, rdi; lpMem
0x180005942  xor     edx, edx; dwFlags
0x180005944  call    WINRT_IMPL_HeapFree
0x180005949  jmp     loc_1800058B2
0x18000594e  jns     loc_1800058B2
0x180005954  call    cs:__imp_abort
0x18000595b  mov     dword ptr [rbx+9Ch], 7FFFFFFEh
0x180005965  mov     ecx, 6; int
0x18000596a  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180005970  mov     ecx, 5; int
0x180005975  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
