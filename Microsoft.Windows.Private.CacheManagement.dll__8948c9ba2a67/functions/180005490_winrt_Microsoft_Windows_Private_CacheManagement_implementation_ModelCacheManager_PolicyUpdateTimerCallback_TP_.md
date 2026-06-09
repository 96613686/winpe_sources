# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::PolicyUpdateTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180005490`
- end: `0x1800054d2`
- name: `?PolicyUpdateTimerCallback@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `66`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180005490`
- `0x180007ef0`
- `0x180012a40`

## string_xrefs

- `0x1800054bc`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.Private.CacheManagement\ModelCacheManager.cpp`
- `0x1800054aa`: `PolicyUpdateTimerCallback context is null.`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::PolicyUpdateTimerCallback(
        PTP_CALLBACK_INSTANCE Instance,
        winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *Context,
        PTP_TIMER Timer)
{
  const char *v3; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( Context )
    winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::UpdateActivityCoordinatorPolicy(Context);
  else
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x79,
      (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Private.CacheManagement\\ModelCacheManager.cpp",
      (const char *)0x8000FFFFLL,
      (int)"PolicyUpdateTimerCallback context is null.",
      v3);
}

```

## disassembly

```asm
0x180005490  sub     rsp, 38h
0x180005494  test    rdx, rdx
0x180005497  jz      short loc_1800054A5
0x180005499  mov     rcx, rdx; this
0x18000549c  add     rsp, 38h
0x1800054a0  jmp     ?UpdateActivityCoordinatorPolicy@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAAXXZ; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::UpdateActivityCoordinatorPolicy(void)
0x1800054a5  mov     rcx, [rsp+38h]; this
0x1800054aa  lea     rax, aPolicyupdateti; "PolicyUpdateTimerCallback context is nu"...
0x1800054b1  mov     r9d, 8000FFFFh; char *
0x1800054b7  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800054bc  lea     r8, aCW1SProductApi; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800054c3  mov     edx, 79h ; 'y'; void *
0x1800054c8  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800054cd  add     rsp, 38h
0x1800054d1  retn
```
