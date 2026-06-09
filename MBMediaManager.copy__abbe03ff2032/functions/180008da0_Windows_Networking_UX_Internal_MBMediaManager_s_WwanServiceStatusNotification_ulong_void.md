# Windows::Networking::UX::Internal::MBMediaManager::s_WwanServiceStatusNotification(ulong,void *)

- ea: `0x180008da0`
- end: `0x180008eeb`
- name: `?s_WwanServiceStatusNotification@MBMediaManager@Internal@UX@Networking@Windows@@SAXKPEAX@Z`
- size: `331`
- prototype: `void __fastcall(unsigned int, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x180008da0`
- `0x18000ad20`
- `0x18000bde0`
- `0x18001a1ec`
- `0x18001addc`
- `0x18001bdb8`
- `0x180021310`
- `0x180022a1c`
- `0x180022d08`
- `0x180022e9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008dfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008dfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008e71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008e71`

## string_xrefs

- `0x180008de7`: `Windows::Networking::UX::Internal::MBMediaManager::_WwanServiceStatusNotification`
- `0x180008e7f`: `Windows::Networking::UX::Internal::MBMediaManager::_WwanServiceStatusNotification`
- `0x180008ddb`: `WwanSvc has started - start listening to wwanrpc and create categories. Service Notification=%d`
- `0x180008dbe`: `Windows::Networking::UX::Internal::MBMediaManager::s_WwanServiceStatusNotification`
- `0x180008e88`: `WwanSvc has been stopped - stop listening to wwanrpc and remove categories. Service Notification=%d`
- `0x180008ecf`: `WwanSvc is not startedService Notification=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Networking::UX::Internal::MBMediaManager::s_WwanServiceStatusNotification(int a1, char *a2)
{
  int started; // eax
  int Categories; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char *v7; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    if ( (a1 & 8) != 0 )
    {
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBMediaManager::_WwanServiceStatusNotification",
        645,
        "WwanSvc has started - start listening to wwanrpc and create categories. Service Notification=%d",
        a1);
      EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 104));
      v7 = a2 + 104;
      *((_DWORD *)a2 + 40) = 4;
      started = Windows::Networking::UX::Internal::MBMediaManager::_StartListeningToWwanRpc(a2);
      if ( started < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x289,
          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbmediamanager.cpp",
          (const char *)(unsigned int)started,
          v5);
      if ( !a2[20] )
      {
        Categories = Windows::Networking::UX::Internal::MBMediaManager::_EnumAndCreateCategories((Windows::Networking::UX::Internal::MediaManagerBase *)a2);
        if ( Categories >= 0 )
          a2[20] = 1;
        else
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x28E,
            (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbmediamanager.cpp",
            (const char *)(unsigned int)Categories,
            v5);
      }
      if ( a2 != (char *)-104LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 104));
    }
    else if ( (a1 & 0x101) != 0 )
    {
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBMediaManager::_WwanServiceStatusNotification",
        666,
        "WwanSvc has been stopped - stop listening to wwanrpc and remove categories. Service Notification=%d",
        a1);
      *((_DWORD *)a2 + 40) = 1;
      Windows::Networking::UX::Internal::MBMediaManager::_StopListeningToWwanRpc((Windows::Networking::UX::Internal::MBMediaManager *)a2);
      wil::EnterCriticalSection(&v7, a2 + 104);
      Windows::Networking::UX::Internal::MBMediaManager::_RemoveAllCategories(a2);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v7);
    }
    else
    {
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBMediaManager::_WwanServiceStatusNotification",
        679,
        "WwanSvc is not startedService Notification=%d",
        a1);
    }
  }
  else
  {
    MBSettingUXLogging::Warn(
      "Windows::Networking::UX::Internal::MBMediaManager::s_WwanServiceStatusNotification",
      623,
      "context contains nullptr. Ignore bad notifications");
  }
}

```

## disassembly

```asm
0x180008da0  mov     [rsp+arg_0], rbx
0x180008da5  push    rdi; int
0x180008da6  sub     rsp, 20h
0x180008daa  mov     rbx, rdx
0x180008dad  test    rdx, rdx
0x180008db0  jnz     short loc_180008DCF
0x180008db2  lea     r8, aContextContain; "context contains nullptr. Ignore bad no"...
0x180008db9  mov     edx, 26Fh; unsigned int
0x180008dbe  lea     rcx, aWindowsNetwork_63; "Windows::Networking::UX::Internal::MBMe"...
0x180008dc5  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x180008dca  jmp     loc_180008EE0
0x180008dcf  mov     r9d, ecx
0x180008dd2  test    cl, 8
0x180008dd5  jz      loc_180008E79
0x180008ddb  lea     r8, aWwansvcHasStar; "WwanSvc has started - start listening t"...
0x180008de2  mov     edx, 285h; unsigned int
0x180008de7  lea     rcx, aWindowsNetwork_276; "Windows::Networking::UX::Internal::MBMe"...
0x180008dee  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180008df3  lea     rdi, [rbx+68h]
0x180008df7  mov     rcx, rdi; lpCriticalSection
0x180008dfa  call    cs:__imp_EnterCriticalSection
0x180008e00  mov     [rsp+28h+arg_8], rdi
0x180008e05  mov     dword ptr [rbx+0A0h], 4
0x180008e0f  mov     rcx, rbx
0x180008e12  call    ?_StartListeningToWwanRpc@MBMediaManager@Internal@UX@Networking@Windows@@AEAAJUwrite_lock_required@wil@@@Z; Windows::Networking::UX::Internal::MBMediaManager::_StartListeningToWwanRpc(wil::write_lock_required)
0x180008e17  mov     rcx, [rsp+28h]; this
0x180008e1c  test    eax, eax
0x180008e1e  jns     short loc_180008E34
0x180008e20  mov     r9d, eax; char *
0x180008e23  lea     r8, aOnecoreuapNetU_15; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180008e2a  mov     edx, 289h; void *
0x180008e2f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008e34  cmp     byte ptr [rbx+14h], 0
0x180008e38  jnz     short loc_180008E69
0x180008e3a  mov     dl, byte ptr [rsp+28h+arg_8]
0x180008e3e  mov     rcx, rbx
0x180008e41  call    ?_EnumAndCreateCategories@MBMediaManager@Internal@UX@Networking@Windows@@AEAAJUwrite_lock_required@wil@@@Z; Windows::Networking::UX::Internal::MBMediaManager::_EnumAndCreateCategories(wil::write_lock_required)
0x180008e46  mov     rcx, [rsp+28h]; this
0x180008e4b  test    eax, eax
0x180008e4d  jns     short loc_180008E65
0x180008e4f  mov     r9d, eax; char *
0x180008e52  lea     r8, aOnecoreuapNetU_15; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180008e59  mov     edx, 28Eh; void *
0x180008e5e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008e63  jmp     short loc_180008E69
0x180008e65  mov     byte ptr [rbx+14h], 1
0x180008e69  test    rdi, rdi
0x180008e6c  jz      short loc_180008EE0
0x180008e6e  mov     rcx, rdi; lpCriticalSection
0x180008e71  call    cs:__imp_LeaveCriticalSection
0x180008e77  jmp     short loc_180008EE0
0x180008e79  test    ecx, 101h
0x180008e7f  lea     rcx, aWindowsNetwork_276; "Windows::Networking::UX::Internal::MBMe"...
0x180008e86  jz      short loc_180008ECF
0x180008e88  lea     r8, aWwansvcHasBeen; "WwanSvc has been stopped - stop listeni"...
0x180008e8f  mov     edx, 29Ah; unsigned int
0x180008e94  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180008e99  mov     dword ptr [rbx+0A0h], 1
0x180008ea3  mov     rcx, rbx; this
0x180008ea6  call    ?_StopListeningToWwanRpc@MBMediaManager@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBMediaManager::_StopListeningToWwanRpc(void)
0x180008eab  lea     rdx, [rbx+68h]
0x180008eaf  lea     rcx, [rsp+28h+arg_8]
0x180008eb4  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180008eb9  nop
0x180008eba  mov     rcx, rbx
0x180008ebd  call    ?_RemoveAllCategories@MBMediaManager@Internal@UX@Networking@Windows@@AEAAXUwrite_lock_required@wil@@@Z; Windows::Networking::UX::Internal::MBMediaManager::_RemoveAllCategories(wil::write_lock_required)
0x180008ec2  nop
0x180008ec3  lea     rcx, [rsp+28h+arg_8]
0x180008ec8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180008ecd  jmp     short loc_180008EE0
0x180008ecf  lea     r8, aWwansvcIsNotSt; "WwanSvc is not startedService Notificat"...
0x180008ed6  mov     edx, 2A7h; unsigned int
0x180008edb  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180008ee0  mov     rbx, [rsp+28h+arg_0]
0x180008ee5  add     rsp, 20h
0x180008ee9  pop     rdi
0x180008eea  retn
```
