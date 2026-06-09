# Windows::Networking::UX::Internal::MBMediaManager::_StartListeningToWwanRpc(wil::write_lock_required)

- ea: `0x18001addc`
- end: `0x18001aee5`
- name: `?_StartListeningToWwanRpc@MBMediaManager@Internal@UX@Networking@Windows@@AEAAJUwrite_lock_required@wil@@@Z`
- size: `265`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180008da0`
- `0x18001c0cc`

## callees

- `0x18000ad20`
- `0x18000bde0`
- `0x180017ac4`
- `0x18001addc`
- `0x18001b1d4`
- `0x18003265c`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanRegisterNotification` at `0x18001ae9c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanRegisterNotification` at `0x18001ae9c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18001ae4a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18001ae4a`

## string_xrefs

- `0x18001aec0`: `Already registered for WwanRpc`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::MBMediaManager::_StartListeningToWwanRpc(__int64 a1, char a2)
{
  _QWORD *v4; // rbx
  unsigned int v5; // eax
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  unsigned int v8; // edi
  unsigned int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v11; // [rsp+48h] [rbp+10h] BYREF

  LOBYTE(v11) = a2;
  if ( *(_DWORD *)(a1 + 160) != 4 )
  {
    MBSettingUXLogging::Warn(
      "Windows::Networking::UX::Internal::MBMediaManager::_StartListeningToWwanRpc",
      291,
      "WwanSvc is not running.");
    return 2147942421LL;
  }
  v4 = (_QWORD *)(a1 + 152);
  if ( *(_QWORD *)(a1 + 152) == -1 )
  {
    v11 = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset(a1 + 152);
    v5 = WwanOpenHandle(1, 0, &v11, v4);
    if ( v5 )
    {
      v6 = v5;
      v7 = 298;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v7,
               (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbmediamanager.cpp",
               (const char *)v6,
               v9);
    }
    v9 = 0;
    v8 = WwanRegisterNotification(
           *v4,
           6,
           Windows::Networking::UX::Internal::MBMediaManager::s_ProcessWwanNotification,
           a1);
    if ( v8 )
    {
      if ( *v4 != -1 )
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>>::operator=(v4);
      v6 = v8;
      v7 = 321;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v7,
               (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbmediamanager.cpp",
               (const char *)v6,
               v9);
    }
  }
  else
  {
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBMediaManager::_StartListeningToWwanRpc",
      303,
      "Already registered for WwanRpc");
  }
  return 0;
}

```

## disassembly

```asm
0x18001addc  mov     [rsp+arg_10], rbx
0x18001ade1  mov     byte ptr [rsp+arg_8], dl
0x18001ade5  push    rdi
0x18001ade6  sub     rsp, 30h
0x18001adea  cmp     dword ptr [rcx+0A0h], 4
0x18001adf1  mov     rdi, rcx
0x18001adf4  jz      short loc_18001AE18
0x18001adf6  lea     r8, aWwansvcIsNotRu; "WwanSvc is not running."
0x18001adfd  mov     edx, 123h; unsigned int
0x18001ae02  lea     rcx, aWindowsNetwork_167; "Windows::Networking::UX::Internal::MBMe"...
0x18001ae09  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x18001ae0e  mov     eax, 80070015h
0x18001ae13  jmp     loc_18001AEDA
0x18001ae18  lea     rbx, [rcx+98h]
0x18001ae1f  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18001ae23  jnz     loc_18001AEC0
0x18001ae29  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001ae2d  mov     [rsp+38h+arg_8], 0
0x18001ae35  mov     rcx, rbx
0x18001ae38  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset(void *)
0x18001ae3d  xor     edx, edx
0x18001ae3f  lea     r8, [rsp+38h+arg_8]
0x18001ae44  mov     r9, rbx
0x18001ae47  lea     ecx, [rdx+1]
0x18001ae4a  call    cs:__imp_WwanOpenHandle
0x18001ae50  test    eax, eax
0x18001ae52  jz      short loc_18001AE6F
0x18001ae54  mov     r9d, eax; char *
0x18001ae57  mov     edx, 12Ah; void *
0x18001ae5c  mov     rcx, [rsp+38h]; this
0x18001ae61  lea     r8, aOnecoreuapNetU_15; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001ae68  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001ae6d  jmp     short loc_18001AEDA
0x18001ae6f  mov     rcx, [rbx]
0x18001ae72  lea     rax, [rsp+38h+arg_0]
0x18001ae77  mov     [rsp+38h+var_10], rax
0x18001ae7c  lea     r8, ?s_ProcessWwanNotification@MBMediaManager@Internal@UX@Networking@Windows@@SAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; Windows::Networking::UX::Internal::MBMediaManager::s_ProcessWwanNotification(_L2_NOTIFICATION_DATA *,void *)
0x18001ae83  mov     r9, rdi
0x18001ae86  mov     [rsp+38h+var_18], 0
0x18001ae8f  mov     edx, 6
0x18001ae94  mov     [rsp+38h+arg_0], 0
0x18001ae9c  call    cs:__imp_WwanRegisterNotification
0x18001aea2  mov     edi, eax
0x18001aea4  test    eax, eax
0x18001aea6  jz      short loc_18001AED8
0x18001aea8  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18001aeac  jz      short loc_18001AEB6
0x18001aeae  mov     rcx, rbx
0x18001aeb1  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>>::operator=(std::nullptr_t)
0x18001aeb6  mov     r9d, edi
0x18001aeb9  mov     edx, 141h
0x18001aebe  jmp     short loc_18001AE5C
0x18001aec0  lea     r8, aAlreadyRegiste; "Already registered for WwanRpc"
0x18001aec7  mov     edx, 12Fh; unsigned int
0x18001aecc  lea     rcx, aWindowsNetwork_167; "Windows::Networking::UX::Internal::MBMe"...
0x18001aed3  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001aed8  xor     eax, eax
0x18001aeda  mov     rbx, [rsp+38h+arg_10]
0x18001aedf  add     rsp, 30h
0x18001aee3  pop     rdi
0x18001aee4  retn
```
