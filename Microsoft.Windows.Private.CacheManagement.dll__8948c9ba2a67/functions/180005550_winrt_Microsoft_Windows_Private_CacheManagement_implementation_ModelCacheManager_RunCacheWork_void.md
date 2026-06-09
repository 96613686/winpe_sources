# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::RunCacheWork(void)

- ea: `0x180005550`
- end: `0x180005734`
- name: `?RunCacheWork@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAAXXZ`
- size: `484`
- prototype: `void __fastcall(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001cca0`

## callees

- `0x180005550`
- `0x1800083b0`
- `0x18000ab70`
- `0x1800165b8`
- `0x1800165c0`
- `0x18001700c`
- `0x180017f20`
- `0x1800181fc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800055c0`
- `KERNEL32!GetLastError` at `0x1800055ec`
- `KERNEL32!GetLastError` at `0x1800055c0`
- `KERNEL32!GetLastError` at `0x1800055ec`
- `KERNEL32!SetLastError` at `0x1800055d3`
- `KERNEL32!SetLastError` at `0x1800055ff`
- `KERNEL32!SetLastError` at `0x1800055d3`
- `KERNEL32!SetLastError` at `0x1800055ff`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!UnsubscribeActivityCoordinatorPolicy` at `0x1800055f7`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!UnsubscribeActivityCoordinatorPolicy` at `0x1800055f7`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!DestroyActivityCoordinatorPolicy` at `0x1800055cb`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!DestroyActivityCoordinatorPolicy` at `0x1800055cb`
- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x1800056bd`
- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x1800056bd`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x1800056a7`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x1800056a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::RunCacheWork(
        winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *this)
{
  __int64 v2; // rbp
  DWORD LastError; // edi
  __int64 v4; // rbp
  DWORD v5; // edi
  char *v6; // rax
  _Thrd_t v7; // xmm1
  _Thrd_t ThrdAddr; // [rsp+30h] [rbp-38h] BYREF
  __int128 v9; // [rsp+40h] [rbp-28h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55709058>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55709058>::GetImpl'::`2'::impl) )
  {
    if ( Mtx_lock((winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *)((char *)this + 80)) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)this + 39) == 0x7FFFFFFF )
    {
      *((_DWORD *)this + 39) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    if ( *((_QWORD *)this + 5) == *((_QWORD *)this + 6) )
    {
      winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CancelPolicyUpdateTimer(this);
      *((_DWORD *)this + 8) = 0;
      v2 = *((_QWORD *)this + 30);
      if ( v2 )
      {
        LastError = GetLastError();
        DestroyActivityCoordinatorPolicy(v2);
        SetLastError(LastError);
      }
      *((_QWORD *)this + 30) = 0;
      v4 = *((_QWORD *)this + 31);
      if ( v4 )
      {
        v5 = GetLastError();
        UnsubscribeActivityCoordinatorPolicy(v4);
        SetLastError(v5);
      }
      *((_QWORD *)this + 31) = 0;
      goto LABEL_11;
    }
    if ( *((_BYTE *)this + 280) )
    {
LABEL_11:
      Mtx_unlock((winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *)((char *)this + 80));
      return;
    }
    Mtx_unlock((winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *)((char *)this + 80));
  }
  if ( !*((_BYTE *)this + 233) )
  {
    *((_BYTE *)this + 232) = 0;
    *((_BYTE *)this + 233) = 1;
    *(_QWORD *)&v9 = winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::ProcessCacheModelPackagesQueue;
    DWORD2(v9) = 0;
    v6 = (char *)operator new(0x18u);
    *(_QWORD *)v6 = this;
    *(_OWORD *)(v6 + 8) = v9;
    *(_QWORD *)&v9 = v6;
    ThrdAddr._Hnd = (void *)_beginthreadex(
                              0,
                              0,
                              (_beginthreadex_proc_type)std::thread::_Invoke<std::tuple<void (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::*)(void),winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *>,0,1>,
                              v6,
                              0,
                              &ThrdAddr._Id);
    if ( !ThrdAddr._Hnd )
    {
      ThrdAddr._Id = 0;
      std::_Throw_Cpp_error(6);
    }
    if ( *((_DWORD *)this + 18) )
      terminate();
    v7 = ThrdAddr;
    ThrdAddr = 0;
    *((_Thrd_t *)this + 4) = v7;
    if ( !*((_DWORD *)this + 18) || (ThrdAddr = v7, Thrd_detach(&ThrdAddr)) )
      std::_Throw_Cpp_error(1);
    *((_OWORD *)this + 4) = 0;
  }
}

```

## disassembly

```asm
0x180005550  mov     [rsp+arg_8], rbx
0x180005555  mov     [rsp+arg_10], rbp
0x18000555a  push    rsi
0x18000555b  push    rdi
0x18000555c  push    r14
0x18000555e  sub     rsp, 50h
0x180005562  mov     rsi, rcx
0x180005565  xor     r14d, r14d
0x180005568  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55709058@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55709058@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55709058> `wil::Feature<__WilFeatureTraits_Feature_55709058>::GetImpl(void)'::`2'::impl
0x18000556f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55709058@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55709058>::__private_IsEnabled(void)
0x180005574  test    al, al
0x180005576  jz      loc_18000563F
0x18000557c  lea     rcx, [rsi+50h]; _Mtx_t
0x180005580  call    _Mtx_lock
0x180005585  test    eax, eax
0x180005587  jnz     loc_180005716
0x18000558d  mov     eax, [rsi+9Ch]
0x180005593  cmp     eax, 7FFFFFFFh
0x180005598  jz      loc_180005721
0x18000559e  mov     rax, [rsi+30h]
0x1800055a2  cmp     [rsi+28h], rax
0x1800055a6  jnz     short loc_18000560E
0x1800055a8  mov     rcx, rsi; this
0x1800055ab  call    ?CancelPolicyUpdateTimer@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAAXXZ; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CancelPolicyUpdateTimer(void)
0x1800055b0  mov     [rsi+20h], r14d
0x1800055b4  mov     rbp, [rsi+0F0h]
0x1800055bb  test    rbp, rbp
0x1800055be  jz      short loc_1800055D9
0x1800055c0  call    cs:__imp_GetLastError
0x1800055c6  mov     edi, eax
0x1800055c8  mov     rcx, rbp
0x1800055cb  call    cs:__imp_DestroyActivityCoordinatorPolicy
0x1800055d1  mov     ecx, edi; dwErrCode
0x1800055d3  call    cs:__imp_SetLastError
0x1800055d9  mov     [rsi+0F0h], r14
0x1800055e0  mov     rbp, [rsi+0F8h]
0x1800055e7  test    rbp, rbp
0x1800055ea  jz      short loc_180005605
0x1800055ec  call    cs:__imp_GetLastError
0x1800055f2  mov     edi, eax
0x1800055f4  mov     rcx, rbp
0x1800055f7  call    cs:__imp_UnsubscribeActivityCoordinatorPolicy
0x1800055fd  mov     ecx, edi; dwErrCode
0x1800055ff  call    cs:__imp_SetLastError
0x180005605  mov     [rsi+0F8h], r14
0x18000560c  jmp     short loc_180005617
0x18000560e  cmp     [rsi+118h], r14b
0x180005615  jz      short loc_180005636
0x180005617  lea     rcx, [rsi+50h]; _Mtx_t
0x18000561b  call    _Mtx_unlock
0x180005620  mov     rbx, [rsp+68h+arg_8]
0x180005625  mov     rbp, [rsp+68h+arg_10]
0x18000562d  add     rsp, 50h
0x180005631  pop     r14
0x180005633  pop     rdi
0x180005634  pop     rsi
0x180005635  retn
0x180005636  lea     rcx, [rsi+50h]; _Mtx_t
0x18000563a  call    _Mtx_unlock
0x18000563f  movzx   eax, byte ptr [rsi+0E9h]
0x180005646  test    al, al
0x180005648  jnz     short loc_180005620
0x18000564a  mov     eax, r14d
0x18000564d  xchg    al, [rsi+0E8h]
0x180005653  mov     eax, 1
0x180005658  xchg    al, [rsi+0E9h]
0x18000565e  lea     rcx, ?ProcessCacheModelPackagesQueue@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAAXXZ; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::ProcessCacheModelPackagesQueue(void)
0x180005665  mov     qword ptr [rsp+68h+var_28], rcx
0x18000566a  mov     dword ptr [rsp+68h+var_28+8], r14d
0x18000566f  mov     ecx, 18h; Size
0x180005674  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005679  mov     [rax], rsi
0x18000567c  movups  xmm0, [rsp+68h+var_28]
0x180005681  movups  xmmword ptr [rax+8], xmm0
0x180005685  mov     qword ptr [rsp+68h+var_28], rax
0x18000568a  lea     rcx, [rsp+68h+var_38._Id]
0x18000568f  mov     [rsp+68h+ThrdAddr], rcx; ThrdAddr
0x180005694  mov     [rsp+68h+InitFlag], r14d; InitFlag
0x180005699  mov     r9, rax; ArgList
0x18000569c  lea     r8, ??$_Invoke@V?$tuple@P8ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@EAAXXZPEAU1234567@@std@@$0A@$00@thread@std@@CAIPEAX@Z; StartAddress
0x1800056a3  xor     edx, edx; StackSize
0x1800056a5  xor     ecx, ecx; Security
0x1800056a7  call    cs:__imp__beginthreadex
0x1800056ad  mov     [rsp+68h+var_38._Hnd], rax
0x1800056b2  test    rax, rax
0x1800056b5  jz      short loc_180005706
0x1800056b7  cmp     dword ptr [rsi+48h], 0
0x1800056bb  jz      short loc_1800056C4
0x1800056bd  call    cs:__imp_terminate
0x1800056c4  xorps   xmm0, xmm0
0x1800056c7  movaps  xmm1, xmmword ptr [rsp+68h+var_38._Hnd]
0x1800056cc  movdqa  xmmword ptr [rsp+68h+var_38._Hnd], xmm0
0x1800056d2  movups  xmmword ptr [rsi+40h], xmm1
0x1800056d6  cmp     dword ptr [rsi+48h], 0
0x1800056da  jz      short loc_1800056FB
0x1800056dc  movaps  xmmword ptr [rsp+68h+var_38._Hnd], xmm1
0x1800056e1  lea     rcx, [rsp+68h+var_38]; _Thrd_t
0x1800056e6  call    _Thrd_detach
0x1800056eb  test    eax, eax
0x1800056ed  jnz     short loc_1800056FB
0x1800056ef  xorps   xmm0, xmm0
0x1800056f2  movups  xmmword ptr [rsi+40h], xmm0
0x1800056f6  jmp     loc_180005620
0x1800056fb  mov     ecx, 1; int
0x180005700  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180005706  mov     [rsp+68h+var_38._Id], r14d
0x18000570b  mov     ecx, 6; int
0x180005710  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180005716  mov     ecx, 5; int
0x18000571b  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180005721  dec     eax
0x180005723  mov     [rsi+9Ch], eax
0x180005729  mov     ecx, 6; int
0x18000572e  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
