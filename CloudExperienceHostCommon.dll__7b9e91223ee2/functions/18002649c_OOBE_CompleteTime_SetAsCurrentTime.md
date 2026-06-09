# OOBE::CompleteTime::SetAsCurrentTime

- ea: `0x18002649c`
- end: `0x180026568`
- name: `OOBE::CompleteTime::SetAsCurrentTime`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026848`

## callees

- `0x18001475c`
- `0x1800153f8`
- `0x18001a540`
- `0x180024cbc`
- `0x180026478`
- `0x18002649c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800264be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800264be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026520`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026520`

## string_xrefs

- `0x180026514`: `OOBECompleteTimestamp`
- `0x1800264e6`: `onecoreuap\internal\shell\inc\OOBECompleteTime.h`
- `0x180026532`: `onecoreuap\internal\shell\inc\OOBECompleteTime.h`

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
  _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  SystemTime = 0;
  GetSystemTime(&SystemTime);
  hKey = 0;
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
0x18002649c  push    rbx
0x18002649e  sub     rsp, 50h
0x1800264a2  mov     rax, cs:__security_cookie
0x1800264a9  xor     rax, rsp
0x1800264ac  mov     [rsp+58h+var_10], rax
0x1800264b1  xorps   xmm0, xmm0
0x1800264b4  movups  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x1800264b9  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x1800264be  call    cs:__imp_GetSystemTime
0x1800264c4  nop
0x1800264c5  mov     [rsp+58h+hKey], 0
0x1800264ce  lea     rcx, [rsp+58h+hKey]; phkResult
0x1800264d3  call    OOBE__CompleteTime__details__GetOOBECompleteKey
0x1800264d8  mov     ebx, eax
0x1800264da  test    eax, eax
0x1800264dc  jns     short loc_1800264F9
0x1800264de  mov     rcx, [rsp+58h]; this
0x1800264e3  mov     r9d, eax; char *
0x1800264e6  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\OOBEC"...
0x1800264ed  mov     edx, 23h ; '#'; void *
0x1800264f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800264f7  jmp     short loc_180026549
0x1800264f9  mov     [rsp+58h+cbData], 10h; cbData
0x180026501  lea     rax, [rsp+58h+SystemTime]
0x180026506  mov     [rsp+58h+lpData], rax; unsigned int
0x18002650b  mov     r9d, 3; dwType
0x180026511  xor     r8d, r8d; Reserved
0x180026514  lea     rdx, aOobecompleteti; "OOBECompleteTimestamp"
0x18002651b  mov     rcx, [rsp+58h+hKey]; hKey
0x180026520  call    cs:__imp_RegSetValueExW
0x180026526  test    eax, eax
0x180026528  jz      short loc_180026547
0x18002652a  mov     rcx, [rsp+58h]; this
0x18002652f  mov     r9d, eax; char *
0x180026532  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\OOBEC"...
0x180026539  mov     edx, 24h ; '$'; void *
0x18002653e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180026543  mov     ebx, eax
0x180026545  jmp     short loc_180026549
0x180026547  xor     ebx, ebx
0x180026549  lea     rcx, [rsp+58h+hKey]
0x18002654e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026553  mov     eax, ebx
0x180026555  mov     rcx, [rsp+58h+var_10]
0x18002655a  xor     rcx, rsp; StackCookie
0x18002655d  call    __security_check_cookie
0x180026562  add     rsp, 50h
0x180026566  pop     rbx
0x180026567  retn
```
