# OOBE::CompleteTime::SetAsCurrentTime

- ea: `0x1800269d0`
- end: `0x180026aa7`
- name: `OOBE::CompleteTime::SetAsCurrentTime`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026c00`

## callees

- `0x1800032b0`
- `0x180007134`
- `0x180018c98`
- `0x18001f168`
- `0x18001f6c4`
- `0x18002586c`
- `0x1800269d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026a5f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026a5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800269f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800269f2`

## string_xrefs

- `0x180026a53`: `OOBECompleteTimestamp`
- `0x180026a25`: `onecoreuap\internal\shell\inc\OOBECompleteTime.h`
- `0x180026a71`: `onecoreuap\internal\shell\inc\OOBECompleteTime.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 OOBE::CompleteTime::SetAsCurrentTime()
{
  int OOBECompleteKey; // eax
  unsigned int v1; // ebx
  unsigned int v2; // eax
  int lpData; // [rsp+20h] [rbp-38h]
  unsigned int lpDataa; // [rsp+20h] [rbp-38h]
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  SystemTime = 0;
  GetSystemTime(&SystemTime);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  OOBECompleteKey = OOBE::CompleteTime::details::GetOOBECompleteKey(&hKey);
  v1 = OOBECompleteKey;
  if ( OOBECompleteKey >= 0 )
  {
    v2 = RegSetValueExW(hKey, L"OOBECompleteTimestamp", 0, 3u, (const BYTE *)&SystemTime, 0x10u);
    if ( v2 )
      v1 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x24,
             (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBECompleteTime.h",
             (const char *)v2,
             lpDataa);
    else
      v1 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBECompleteTime.h",
      (const char *)(unsigned int)OOBECompleteKey,
      lpData);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v1;
}

```

## disassembly

```asm
0x1800269d0  push    rbx
0x1800269d2  sub     rsp, 50h
0x1800269d6  mov     rax, cs:__security_cookie
0x1800269dd  xor     rax, rsp
0x1800269e0  mov     [rsp+58h+var_10], rax
0x1800269e5  xorps   xmm0, xmm0
0x1800269e8  movups  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x1800269ed  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x1800269f2  call    cs:__imp_GetSystemTime
0x1800269f8  mov     [rsp+58h+hKey], 0
0x180026a01  xor     edx, edx
0x180026a03  lea     rcx, [rsp+58h+hKey]
0x180026a08  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180026a0d  lea     rcx, [rsp+58h+hKey]; phkResult
0x180026a12  call    OOBE__CompleteTime__details__GetOOBECompleteKey
0x180026a17  mov     ebx, eax
0x180026a19  test    eax, eax
0x180026a1b  jns     short loc_180026A38
0x180026a1d  mov     rcx, [rsp+58h]; this
0x180026a22  mov     r9d, eax; char *
0x180026a25  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\shell\\inc\\OOBEC"...
0x180026a2c  mov     edx, 23h ; '#'; void *
0x180026a31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026a36  jmp     short loc_180026A88
0x180026a38  mov     [rsp+58h+cbData], 10h; cbData
0x180026a40  lea     rax, [rsp+58h+SystemTime]
0x180026a45  mov     [rsp+58h+lpData], rax; unsigned int
0x180026a4a  mov     r9d, 3; dwType
0x180026a50  xor     r8d, r8d; Reserved
0x180026a53  lea     rdx, aOobecompleteti; "OOBECompleteTimestamp"
0x180026a5a  mov     rcx, [rsp+58h+hKey]; hKey
0x180026a5f  call    cs:__imp_RegSetValueExW
0x180026a65  test    eax, eax
0x180026a67  jz      short loc_180026A86
0x180026a69  mov     rcx, [rsp+58h]; this
0x180026a6e  mov     r9d, eax; char *
0x180026a71  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\shell\\inc\\OOBEC"...
0x180026a78  mov     edx, 24h ; '$'; void *
0x180026a7d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180026a82  mov     ebx, eax
0x180026a84  jmp     short loc_180026A88
0x180026a86  xor     ebx, ebx
0x180026a88  lea     rcx, [rsp+58h+hKey]
0x180026a8d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026a92  mov     eax, ebx
0x180026a94  mov     rcx, [rsp+58h+var_10]
0x180026a99  xor     rcx, rsp; StackCookie
0x180026a9c  call    __security_check_cookie
0x180026aa1  add     rsp, 50h
0x180026aa5  pop     rbx
0x180026aa6  retn
```
