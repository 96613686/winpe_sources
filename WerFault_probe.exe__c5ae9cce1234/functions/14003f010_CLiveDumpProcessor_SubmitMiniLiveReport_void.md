# CLiveDumpProcessor::SubmitMiniLiveReport(void)

- ea: `0x14003f010`
- end: `0x14003f16c`
- name: `?SubmitMiniLiveReport@CLiveDumpProcessor@@AEAAJXZ`
- size: `348`
- prototype: `__int64 __fastcall(CLiveDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x14003ebec`

## callees

- `0x140002728`
- `0x140005430`
- `0x140005468`
- `0x140034d9c`
- `0x14003f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f140`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f140`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003f0b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003f0b4`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14003f10d`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14003f10d`

## string_xrefs

- `0x14003f061`: `Failed to sprintf registry key name`
- `0x14003f0eb`: `Could not open key %ws`
- `0x14003f124`: `Could not delete busy key`

## pseudocode

```c
__int64 __fastcall CLiveDumpProcessor::SubmitMiniLiveReport(CLiveDumpProcessor *this)
{
  __int64 v1; // r9
  signed int v2; // ebx
  const char *v3; // rax
  __int64 v4; // rdx
  HKEY *v5; // rax
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  wil::details *phkResult; // [rsp+20h] [rbp-40h]
  char *v10; // [rsp+30h] [rbp-30h]
  LPCWSTR lpSubKey[2]; // [rsp+40h] [rbp-20h] BYREF
  _WORD v12[8]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+68h] [rbp+8h]
  HKEY hKey; // [rsp+70h] [rbp+10h] BYREF

  v1 = *((_QWORD *)this + 9);
  lpSubKey[0] = v12;
  lpSubKey[1] = v12;
  v12[0] = 0;
  hKey = 0;
  v2 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         lpSubKey,
         L"%s\\LiveKernelReports\\%s\\%s",
         g_wszLiveKernelReportsQueueRoot,
         v1,
         *((_QWORD *)this + 13));
  if ( v2 < 0 )
  {
    v3 = "Failed to sprintf registry key name";
    v4 = 817;
LABEL_3:
    LODWORD(phkResult) = v2;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
      "CLiveDumpProcessor::SubmitMiniLiveReport",
      phkResult,
      (int)v3,
      v10);
    goto LABEL_13;
  }
  v5 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x10000u, v5);
  v2 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    LODWORD(phkResult) = v2;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x33E,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
      "CLiveDumpProcessor::SubmitMiniLiveReport",
      phkResult,
      (int)"Could not open key %ws",
      (const char *)lpSubKey[0]);
  }
  else
  {
    v7 = RegDeleteKeyW(hKey, L"Busy");
    v2 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v2 = (unsigned __int16)v7 | 0x80070000;
      v3 = "Could not delete busy key";
      v4 = 841;
      goto LABEL_3;
    }
    v2 = 0;
  }
LABEL_13:
  if ( hKey )
    RegCloseKey(hKey);
  if ( lpSubKey[0] != v12 )
    operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14003f010  mov     [rsp-8+arg_8], rbx
0x14003f015  push    rbp
0x14003f016  mov     rbp, rsp
0x14003f019  sub     rsp, 60h
0x14003f01d  mov     r9, [rcx+48h]
0x14003f021  lea     rax, [rbp+var_10]
0x14003f025  mov     [rbp+lpSubKey], rax
0x14003f029  lea     r8, ?g_wszLiveKernelReportsQueueRoot@@3PA_WA; "System\\CurrentControlSet\\Control\\Cra"...
0x14003f030  lea     rax, [rbp+var_10]
0x14003f034  mov     [rbp+var_18], rax
0x14003f038  lea     rdx, aSLivekernelrep_1; "%s\\LiveKernelReports\\%s\\%s"
0x14003f03f  xor     eax, eax
0x14003f041  mov     [rbp+var_10], ax
0x14003f045  mov     [rbp+hKey], rax
0x14003f049  mov     rax, [rcx+68h]
0x14003f04d  lea     rcx, [rbp+lpSubKey]
0x14003f051  mov     [rsp+60h+phkResult], rax
0x14003f056  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14003f05b  mov     ebx, eax
0x14003f05d  test    eax, eax
0x14003f05f  jns     short loc_14003F092
0x14003f061  lea     rax, aFailedToSprint; "Failed to sprintf registry key name"
0x14003f068  mov     edx, 331h; void *
0x14003f06d  mov     rcx, [rbp+8]; this
0x14003f071  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14003f078  mov     qword ptr [rsp+60h+var_38], rax; int
0x14003f07d  lea     r9, aClivedumpproce_0; "CLiveDumpProcessor::SubmitMiniLiveRepor"...
0x14003f084  mov     dword ptr [rsp+60h+phkResult], ebx; wil::details *
0x14003f088  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003f08d  jmp     loc_14003F137
0x14003f092  lea     rcx, [rbp+hKey]
0x14003f096  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003f09b  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x14003f09f  mov     r9d, 10000h; samDesired
0x14003f0a5  xor     r8d, r8d; ulOptions
0x14003f0a8  mov     [rsp+60h+phkResult], rax; phkResult
0x14003f0ad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003f0b4  call    cs:__imp_RegOpenKeyExW
0x14003f0ba  mov     ebx, eax
0x14003f0bc  test    eax, eax
0x14003f0be  jz      short loc_14003F102
0x14003f0c0  jle     short loc_14003F0CB
0x14003f0c2  movzx   ebx, ax
0x14003f0c5  or      ebx, 80070000h
0x14003f0cb  mov     rax, [rbp+lpSubKey]
0x14003f0cf  lea     r9, aClivedumpproce_0; "CLiveDumpProcessor::SubmitMiniLiveRepor"...
0x14003f0d6  mov     rcx, [rbp+8]; this
0x14003f0da  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14003f0e1  mov     [rsp+60h+var_30], rax; char *
0x14003f0e6  mov     edx, 33Eh; void *
0x14003f0eb  lea     rax, aCouldNotOpenKe; "Could not open key %ws"
0x14003f0f2  mov     qword ptr [rsp+60h+var_38], rax; int
0x14003f0f7  mov     dword ptr [rsp+60h+phkResult], ebx; wil::details *
0x14003f0fb  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003f100  jmp     short loc_14003F137
0x14003f102  mov     rcx, [rbp+hKey]; hKey
0x14003f106  lea     rdx, aBusy; "Busy"
0x14003f10d  call    cs:__imp_RegDeleteKeyW
0x14003f113  mov     ebx, eax
0x14003f115  test    eax, eax
0x14003f117  jz      short loc_14003F135
0x14003f119  jle     short loc_14003F124
0x14003f11b  movzx   ebx, ax
0x14003f11e  or      ebx, 80070000h
0x14003f124  lea     rax, aCouldNotDelete; "Could not delete busy key"
0x14003f12b  mov     edx, 349h
0x14003f130  jmp     loc_14003F06D
0x14003f135  xor     ebx, ebx
0x14003f137  mov     rcx, [rbp+hKey]; hKey
0x14003f13b  test    rcx, rcx
0x14003f13e  jz      short loc_14003F146
0x14003f140  call    cs:__imp_RegCloseKey
0x14003f146  mov     rcx, [rbp+lpSubKey]; void *
0x14003f14a  lea     rax, [rbp+var_10]
0x14003f14e  cmp     rcx, rax
0x14003f151  jz      short loc_14003F15F
0x14003f153  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003f15a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003f15f  mov     eax, ebx
0x14003f161  mov     rbx, [rsp+60h+arg_8]
0x14003f166  add     rsp, 60h
0x14003f16a  pop     rbp
0x14003f16b  retn
```
