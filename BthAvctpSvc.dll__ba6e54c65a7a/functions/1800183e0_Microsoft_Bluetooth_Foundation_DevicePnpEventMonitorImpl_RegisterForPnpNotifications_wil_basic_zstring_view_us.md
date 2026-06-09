# Microsoft::Bluetooth::Foundation::DevicePnpEventMonitorImpl::RegisterForPnpNotifications(wil::basic_zstring_view<ushort>,Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::MonitorInterfaceRemovals)

- ea: `0x1800183e0`
- end: `0x180018492`
- name: `?RegisterForPnpNotifications@DevicePnpEventMonitorImpl@Foundation@Bluetooth@Microsoft@@EEAAXV?$basic_zstring_view@G@wil@@W4MonitorInterfaceRemovals@DevicePnpEventMonitor@234@@Z`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000dca8`
- `0x18000fa08`
- `0x1800183e0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001841d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001841d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Bluetooth::Foundation::DevicePnpEventMonitorImpl::RegisterForPnpNotifications(
        __int64 a1,
        LPCWSTR *a2,
        unsigned int a3)
{
  HANDLE FileW; // rax
  const char *v7; // r9
  __int128 v9; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HANDLE v11; // [rsp+68h] [rbp+10h] BYREF

  FileW = CreateFileW(*a2, 0x80000000, 3u, 0, 3u, 0x40000080u, 0);
  v11 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x960,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\DeviceIoTarget.h",
      v7);
  v9 = *(_OWORD *)a2;
  (*(void (__fastcall **)(__int64, __int128 *, HANDLE, _QWORD))(*(_QWORD *)a1 + 16LL))(a1, &v9, FileW, a3);
  return wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
}

```

## disassembly

```asm
0x1800183e0  mov     rax, rsp
0x1800183e3  mov     [rax+8], rbx
0x1800183e7  mov     [rax+18h], rsi
0x1800183eb  push    rdi
0x1800183ec  sub     rsp, 50h
0x1800183f0  mov     esi, r8d
0x1800183f3  mov     rdi, rdx
0x1800183f6  mov     rbx, rcx
0x1800183f9  mov     qword ptr [rax-28h], 0
0x180018401  mov     dword ptr [rax-30h], 40000080h
0x180018408  mov     r8d, 3; dwShareMode
0x18001840e  mov     [rax-38h], r8d
0x180018412  xor     r9d, r9d; lpSecurityAttributes
0x180018415  mov     edx, 80000000h; dwDesiredAccess
0x18001841a  mov     rcx, [rdi]; lpFileName
0x18001841d  call    cs:__imp_CreateFileW
0x180018423  mov     [rsp+58h+arg_8], rax
0x180018428  lea     rcx, [rax+1]
0x18001842c  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180018433  setz    dl
0x180018436  mov     rcx, [rsp+58h]; this
0x18001843b  test    dl, dl
0x18001843d  jnz     short loc_180018480
0x18001843f  movups  xmm0, xmmword ptr [rdi]
0x180018442  movdqu  [rsp+58h+var_18], xmm0
0x180018448  mov     rcx, [rbx]
0x18001844b  mov     r10, [rcx+10h]
0x18001844f  mov     r9d, esi
0x180018452  mov     r8, rax
0x180018455  lea     rdx, [rsp+58h+var_18]
0x18001845a  mov     rcx, rbx
0x18001845d  mov     rax, r10
0x180018460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018465  nop
0x180018466  lea     rcx, [rsp+58h+arg_8]
0x18001846b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180018470  mov     rbx, [rsp+58h+arg_0]
0x180018475  mov     rsi, [rsp+58h+arg_10]
0x18001847a  add     rsp, 50h
0x18001847e  pop     rdi
0x18001847f  retn
0x180018480  lea     r8, aOnecoreDrivers_19; "onecore\\drivers\\bluetooth\\foundation"...
0x180018487  mov     edx, 960h; void *
0x18001848c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
