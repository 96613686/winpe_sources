# CLiveDumpProcessor::SubmitMiniLiveReport(void)

- ea: `0x140041b40`
- end: `0x140041caf`
- name: `?SubmitMiniLiveReport@CLiveDumpProcessor@@AEAAJXZ`
- size: `367`
- prototype: `__int64 __fastcall(CLiveDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1400416f4`

## callees

- `0x140002748`
- `0x1400054e4`
- `0x14000551c`
- `0x1400372dc`
- `0x140041b40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041c7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041c7c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140041be4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140041be4`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x140041c43`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x140041c43`

## string_xrefs

- `0x140041b91`: `Failed to sprintf registry key name`
- `0x140041c21`: `Could not open key %ws`
- `0x140041c60`: `Could not delete busy key`

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
0x140041b40  mov     [rsp-8+arg_8], rbx
0x140041b45  push    rbp
0x140041b46  mov     rbp, rsp
0x140041b49  sub     rsp, 60h
0x140041b4d  mov     r9, [rcx+48h]
0x140041b51  lea     rax, [rbp+var_10]
0x140041b55  mov     [rbp+lpSubKey], rax
0x140041b59  lea     r8, ?g_wszLiveKernelReportsQueueRoot@@3PA_WA; "System\\CurrentControlSet\\Control\\Cra"...
0x140041b60  lea     rax, [rbp+var_10]
0x140041b64  mov     [rbp+var_18], rax
0x140041b68  lea     rdx, aSLivekernelrep_1; "%s\\LiveKernelReports\\%s\\%s"
0x140041b6f  xor     eax, eax
0x140041b71  mov     [rbp+var_10], ax
0x140041b75  mov     [rbp+hKey], rax
0x140041b79  mov     rax, [rcx+68h]
0x140041b7d  lea     rcx, [rbp+lpSubKey]
0x140041b81  mov     [rsp+60h+phkResult], rax
0x140041b86  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140041b8b  mov     ebx, eax
0x140041b8d  test    eax, eax
0x140041b8f  jns     short loc_140041BC2
0x140041b91  lea     rax, aFailedToSprint; "Failed to sprintf registry key name"
0x140041b98  mov     edx, 331h; void *
0x140041b9d  mov     rcx, [rbp+8]; this
0x140041ba1  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x140041ba8  mov     qword ptr [rsp+60h+var_38], rax; int
0x140041bad  lea     r9, aClivedumpproce_0; "CLiveDumpProcessor::SubmitMiniLiveRepor"...
0x140041bb4  mov     dword ptr [rsp+60h+phkResult], ebx; wil::details *
0x140041bb8  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140041bbd  jmp     loc_140041C73
0x140041bc2  lea     rcx, [rbp+hKey]
0x140041bc6  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140041bcb  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x140041bcf  mov     r9d, 10000h; samDesired
0x140041bd5  xor     r8d, r8d; ulOptions
0x140041bd8  mov     [rsp+60h+phkResult], rax; phkResult
0x140041bdd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140041be4  call    cs:__imp_RegOpenKeyExW
0x140041beb  nop     dword ptr [rax+rax+00h]
0x140041bf0  mov     ebx, eax
0x140041bf2  test    eax, eax
0x140041bf4  jz      short loc_140041C38
0x140041bf6  jle     short loc_140041C01
0x140041bf8  movzx   ebx, ax
0x140041bfb  or      ebx, 80070000h
0x140041c01  mov     rax, [rbp+lpSubKey]
0x140041c05  lea     r9, aClivedumpproce_0; "CLiveDumpProcessor::SubmitMiniLiveRepor"...
0x140041c0c  mov     rcx, [rbp+8]; this
0x140041c10  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x140041c17  mov     [rsp+60h+var_30], rax; char *
0x140041c1c  mov     edx, 33Eh; void *
0x140041c21  lea     rax, aCouldNotOpenKe; "Could not open key %ws"
0x140041c28  mov     qword ptr [rsp+60h+var_38], rax; int
0x140041c2d  mov     dword ptr [rsp+60h+phkResult], ebx; wil::details *
0x140041c31  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140041c36  jmp     short loc_140041C73
0x140041c38  mov     rcx, [rbp+hKey]; hKey
0x140041c3c  lea     rdx, aBusy; "Busy"
0x140041c43  call    cs:__imp_RegDeleteKeyW
0x140041c4a  nop     dword ptr [rax+rax+00h]
0x140041c4f  mov     ebx, eax
0x140041c51  test    eax, eax
0x140041c53  jz      short loc_140041C71
0x140041c55  jle     short loc_140041C60
0x140041c57  movzx   ebx, ax
0x140041c5a  or      ebx, 80070000h
0x140041c60  lea     rax, aCouldNotDelete; "Could not delete busy key"
0x140041c67  mov     edx, 349h
0x140041c6c  jmp     loc_140041B9D
0x140041c71  xor     ebx, ebx
0x140041c73  mov     rcx, [rbp+hKey]; hKey
0x140041c77  test    rcx, rcx
0x140041c7a  jz      short loc_140041C88
0x140041c7c  call    cs:__imp_RegCloseKey
0x140041c83  nop     dword ptr [rax+rax+00h]
0x140041c88  mov     rcx, [rbp+lpSubKey]; void *
0x140041c8c  lea     rax, [rbp+var_10]
0x140041c90  cmp     rcx, rax
0x140041c93  jz      short loc_140041CA1
0x140041c95  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140041c9c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140041ca1  mov     eax, ebx
0x140041ca3  mov     rbx, [rsp+60h+arg_8]
0x140041ca8  add     rsp, 60h
0x140041cac  pop     rbp
0x140041cad  retn
```
