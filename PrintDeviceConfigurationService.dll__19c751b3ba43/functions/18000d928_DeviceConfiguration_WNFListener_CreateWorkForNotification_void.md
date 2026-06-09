# DeviceConfiguration::WNFListener::_CreateWorkForNotification(void *)

- ea: `0x18000d928`
- end: `0x18000d9bf`
- name: `?_CreateWorkForNotification@WNFListener@DeviceConfiguration@@AEAAJPEAX@Z`
- size: `151`
- prototype: `__int64 __fastcall(DeviceConfiguration::WNFListener *this, void *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000da84`
- `0x18000db34`
- `0x18000dbe4`

## callees

- `0x180004e44`
- `0x18000d868`
- `0x18000d928`
- `0x18000dcfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d944`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d944`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000d977`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000d977`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000d969`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000d969`

## string_xrefs

- `0x18000d9ac`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\wnflistener.cpp`
- `0x18000d9a5`: `CreateThreadpoolWork failed!`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::WNFListener::_CreateWorkForNotification(
        DeviceConfiguration::WNFListener *this,
        void *a2)
{
  char *v4; // rbx
  struct _TP_WORK *ThreadpoolWork; // rax
  const char *v7; // r9
  const char **v8; // rdx
  const char *v9[5]; // [rsp+0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char *v11; // [rsp+30h] [rbp+8h] BYREF

  v4 = (char *)this + 48;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v11 = v4;
  if ( !(unsigned __int8)std::_Atomic_storage<bool,1>::load((char *)this + 88) )
  {
    ThreadpoolWork = CreateThreadpoolWork(DeviceConfiguration::WNFListener::s_WorkCallback, a2, 0);
    if ( !ThreadpoolWork )
    {
      try
      {
        wil::details::in1diag3::Throw_GetLastErrorMsg(
          retaddr,
          (void *)0xD4,
          (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
          "CreateThreadpoolWork failed!",
          v9[4]);
      }
      catch ( ... )
      {
        v8 = v9;
        *((_DWORD *)v8 + 12) = wil::details::in1diag3::Return_CaughtException(
                                 (wil::details::in1diag3 *)v8[5],
                                 (void *)0xDA,
                                 (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib"
                                               "\\wnflistener.cpp",
                                 v7);
        return (unsigned int)v11;
      }
    }
    SubmitThreadpoolWork(ThreadpoolWork);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v11);
  return 0;
}

```

## disassembly

```asm
0x18000d928  mov     [rsp+arg_8], rbx
0x18000d92d  mov     [rsp+arg_10], rsi
0x18000d932  push    rdi; char *
0x18000d933  sub     rsp, 20h
0x18000d937  mov     rsi, rdx
0x18000d93a  mov     rdi, rcx
0x18000d93d  lea     rbx, [rcx+30h]
0x18000d941  mov     rcx, rbx; lpCriticalSection
0x18000d944  call    cs:__imp_EnterCriticalSection
0x18000d94a  mov     [rsp+28h+arg_0], rbx
0x18000d94f  lea     rcx, [rdi+58h]
0x18000d953  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x18000d958  test    al, al
0x18000d95a  jnz     short loc_18000D97E
0x18000d95c  xor     r8d, r8d; pcbe
0x18000d95f  mov     rdx, rsi; pv
0x18000d962  lea     rcx, ?s_WorkCallback@WNFListener@DeviceConfiguration@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000d969  call    cs:__imp_CreateThreadpoolWork
0x18000d96f  test    rax, rax
0x18000d972  jz      short loc_18000D9A0
0x18000d974  mov     rcx, rax; pwk
0x18000d977  call    cs:__imp_SubmitThreadpoolWork
0x18000d97d  nop
0x18000d97e  lea     rcx, [rsp+28h+arg_0]
0x18000d983  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000d988  xor     eax, eax
0x18000d98a  jmp     short loc_18000D990
0x18000d98c  mov     eax, dword ptr [rsp+28h+arg_0]
0x18000d990  mov     rbx, [rsp+28h+arg_8]
0x18000d995  mov     rsi, [rsp+28h+arg_10]
0x18000d99a  add     rsp, 20h
0x18000d99e  pop     rdi
0x18000d99f  retn
0x18000d9a0  mov     rcx, [rsp+28h]; this
0x18000d9a5  lea     r9, aCreatethreadpo; "CreateThreadpoolWork failed!"
0x18000d9ac  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\configuratio"...
0x18000d9b3  mov     edx, 0D4h; void *
0x18000d9b8  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
