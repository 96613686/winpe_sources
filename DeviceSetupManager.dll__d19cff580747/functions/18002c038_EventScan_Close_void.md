# EventScan::Close(void)

- ea: `0x18002c038`
- end: `0x18002c11d`
- name: `?Close@EventScan@@QEAAJXZ`
- size: `229`
- prototype: `__int64 __fastcall(EventScan *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800240dc`

## callees

- `0x180021790`
- `0x18002c038`
- `0x18002d010`
- `0x18002d064`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002c087`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002c087`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c0de`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c0de`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18002c0f1`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18002c0f1`

## pseudocode

```c
__int64 __fastcall EventScan::Close(EventScan *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_5f220cccee2e33150182d68011e709f6_Traceguids);
  if ( *((_BYTE *)this + 16) )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v2,
        v3,
        SystemTimeAsFileTime.dwHighDateTime,
        SystemTimeAsFileTime.dwLowDateTime);
    RegSetValueExW(g_hPersistentStateKey, L"LastActiveTime", 0, 3u, (const BYTE *)&SystemTimeAsFileTime, 8u);
    *((_BYTE *)this + 16) = 0;
  }
  if ( *((_QWORD *)this + 1) )
  {
    DevCloseObjectQuery();
    *((_QWORD *)this + 1) = 0;
  }
  if ( *((_QWORD *)this + 7) )
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset((char *)this + 56);
  return 0;
}

```

## disassembly

```asm
0x18002c038  mov     [rsp+arg_8], rbx
0x18002c03d  push    rsi
0x18002c03e  sub     rsp, 30h
0x18002c042  mov     rbx, rcx
0x18002c045  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c04c  lea     rsi, WPP_GLOBAL_Control
0x18002c053  cmp     rcx, rsi
0x18002c056  jz      short loc_18002C073
0x18002c058  test    byte ptr [rcx+1Ch], 1
0x18002c05c  jz      short loc_18002C073
0x18002c05e  mov     rcx, [rcx+10h]
0x18002c062  lea     r8, WPP_5f220cccee2e33150182d68011e709f6_Traceguids
0x18002c069  mov     edx, 10h
0x18002c06e  call    WPP_SF_
0x18002c073  cmp     byte ptr [rbx+10h], 0
0x18002c077  jz      short loc_18002C0E8
0x18002c079  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002c07e  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002c087  call    cs:__imp_GetSystemTimeAsFileTime
0x18002c08d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c094  cmp     rcx, rsi
0x18002c097  jz      short loc_18002C0B5
0x18002c099  test    byte ptr [rcx+1Ch], 1
0x18002c09d  jz      short loc_18002C0B5
0x18002c09f  mov     eax, [rsp+38h+SystemTimeAsFileTime.dwLowDateTime]
0x18002c0a3  mov     r9d, [rsp+38h+SystemTimeAsFileTime.dwHighDateTime]
0x18002c0a8  mov     rcx, [rcx+10h]
0x18002c0ac  mov     dword ptr [rsp+38h+lpData], eax
0x18002c0b0  call    WPP_SF_DD
0x18002c0b5  mov     rcx, cs:?g_hPersistentStateKey@@3PEAUHKEY__@@EA; hKey
0x18002c0bc  lea     rax, [rsp+38h+SystemTimeAsFileTime]
0x18002c0c1  mov     [rsp+38h+cbData], 8; cbData
0x18002c0c9  lea     rdx, aLastactivetime; "LastActiveTime"
0x18002c0d0  mov     r9d, 3; dwType
0x18002c0d6  mov     [rsp+38h+lpData], rax; lpData
0x18002c0db  xor     r8d, r8d; Reserved
0x18002c0de  call    cs:__imp_RegSetValueExW
0x18002c0e4  mov     byte ptr [rbx+10h], 0
0x18002c0e8  mov     rcx, [rbx+8]
0x18002c0ec  test    rcx, rcx
0x18002c0ef  jz      short loc_18002C0FF
0x18002c0f1  call    cs:__imp_DevCloseObjectQuery
0x18002c0f7  mov     qword ptr [rbx+8], 0
0x18002c0ff  lea     rcx, [rbx+38h]
0x18002c103  cmp     qword ptr [rcx], 0
0x18002c107  jz      short loc_18002C110
0x18002c109  xor     edx, edx
0x18002c10b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)
0x18002c110  mov     rbx, [rsp+38h+arg_8]
0x18002c115  xor     eax, eax
0x18002c117  add     rsp, 30h
0x18002c11b  pop     rsi
0x18002c11c  retn
```
