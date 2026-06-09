# CLiveDumpProcessor::CancelMiniLiveReport(void)

- ea: `0x140040c98`
- end: `0x140040e10`
- name: `?CancelMiniLiveReport@CLiveDumpProcessor@@AEAAJXZ`
- size: `376`
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
- `0x140040c98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140040dd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140040dd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140040d3b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140040d3b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140040d97`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140040d97`

## string_xrefs

- `0x140040cec`: `Failed to sprintf registry key name`
- `0x140040d66`: `Could not open key %ws`
- `0x140040dc2`: `Could not delete ReportId %ws tree`

## pseudocode

```c
__int64 __fastcall CLiveDumpProcessor::CancelMiniLiveReport(CLiveDumpProcessor *this)
{
  __int64 v1; // r9
  signed int v3; // ebx
  HKEY *v4; // rax
  LSTATUS v5; // eax
  __int64 v6; // rdx
  const char *v7; // rax
  LSTATUS v8; // eax
  wil::details *phkResult; // [rsp+20h] [rbp-40h]
  wil::details *phkResulta; // [rsp+20h] [rbp-40h]
  char *v12; // [rsp+30h] [rbp-30h]
  char *v13; // [rsp+30h] [rbp-30h]
  LPCWSTR lpSubKey[2]; // [rsp+40h] [rbp-20h] BYREF
  _WORD v15[8]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+68h] [rbp+8h]
  HKEY hKey; // [rsp+70h] [rbp+10h] BYREF

  v1 = *((_QWORD *)this + 9);
  lpSubKey[0] = v15;
  lpSubKey[1] = v15;
  v15[0] = 0;
  hKey = 0;
  v3 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         lpSubKey,
         L"%s\\LiveKernelReports\\%s",
         g_wszLiveKernelReportsQueueRoot,
         v1);
  if ( v3 < 0 )
  {
    LODWORD(phkResult) = v3;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
      "CLiveDumpProcessor::CancelMiniLiveReport",
      phkResult,
      (int)"Failed to sprintf registry key name",
      v12);
    goto LABEL_13;
  }
  v4 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x3001Bu, v4);
  v3 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    v6 = 77;
    v13 = (char *)lpSubKey[0];
    v7 = "Could not open key %ws";
LABEL_7:
    LODWORD(phkResulta) = v3;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
      "CLiveDumpProcessor::CancelMiniLiveReport",
      phkResulta,
      (int)v7,
      v13);
    goto LABEL_13;
  }
  v8 = RegDeleteTreeW(hKey, *((LPCWSTR *)this + 13));
  v3 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v3 = (unsigned __int16)v8 | 0x80070000;
    v6 = 85;
    v13 = (char *)*((_QWORD *)this + 13);
    v7 = "Could not delete ReportId %ws tree";
    goto LABEL_7;
  }
  v3 = 0;
LABEL_13:
  if ( hKey )
    RegCloseKey(hKey);
  if ( lpSubKey[0] != v15 )
    operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140040c98  mov     [rsp-8+arg_8], rbx
0x140040c9d  mov     [rsp-8+arg_10], rdi
0x140040ca2  push    rbp
0x140040ca3  mov     rbp, rsp
0x140040ca6  sub     rsp, 60h
0x140040caa  mov     r9, [rcx+48h]
0x140040cae  lea     rax, [rbp+var_10]
0x140040cb2  mov     [rbp+lpSubKey], rax
0x140040cb6  lea     r8, ?g_wszLiveKernelReportsQueueRoot@@3PA_WA; "System\\CurrentControlSet\\Control\\Cra"...
0x140040cbd  lea     rax, [rbp+var_10]
0x140040cc1  mov     rdi, rcx
0x140040cc4  mov     [rbp+var_18], rax
0x140040cc8  lea     rdx, aSLivekernelrep_0; "%s\\LiveKernelReports\\%s"
0x140040ccf  xor     eax, eax
0x140040cd1  lea     rcx, [rbp+lpSubKey]
0x140040cd5  mov     [rbp+var_10], ax
0x140040cd9  mov     [rbp+hKey], rax
0x140040cdd  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140040ce2  mov     ebx, eax
0x140040ce4  test    eax, eax
0x140040ce6  jns     short loc_140040D19
0x140040ce8  mov     rcx, [rbp+8]; this
0x140040cec  lea     rax, aFailedToSprint; "Failed to sprintf registry key name"
0x140040cf3  mov     qword ptr [rsp+60h+var_38], rax; int
0x140040cf8  lea     r9, aClivedumpproce_1; "CLiveDumpProcessor::CancelMiniLiveRepor"...
0x140040cff  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x140040d06  mov     dword ptr [rsp+60h+phkResult], ebx; wil::details *
0x140040d0a  mov     edx, 40h ; '@'; void *
0x140040d0f  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140040d14  jmp     loc_140040DCD
0x140040d19  lea     rcx, [rbp+hKey]
0x140040d1d  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140040d22  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x140040d26  mov     r9d, 3001Bh; samDesired
0x140040d2c  xor     r8d, r8d; ulOptions
0x140040d2f  mov     [rsp+60h+phkResult], rax; phkResult
0x140040d34  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140040d3b  call    cs:__imp_RegOpenKeyExW
0x140040d42  nop     dword ptr [rax+rax+00h]
0x140040d47  mov     ebx, eax
0x140040d49  test    eax, eax
0x140040d4b  jz      short loc_140040D8F
0x140040d4d  jle     short loc_140040D58
0x140040d4f  movzx   ebx, ax
0x140040d52  or      ebx, 80070000h
0x140040d58  mov     rax, [rbp+lpSubKey]
0x140040d5c  mov     edx, 4Dh ; 'M'; void *
0x140040d61  mov     [rsp+60h+var_30], rax; char *
0x140040d66  lea     rax, aCouldNotOpenKe; "Could not open key %ws"
0x140040d6d  mov     rcx, [rbp+8]; this
0x140040d71  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x140040d78  mov     qword ptr [rsp+60h+var_38], rax; int
0x140040d7d  lea     r9, aClivedumpproce_1; "CLiveDumpProcessor::CancelMiniLiveRepor"...
0x140040d84  mov     dword ptr [rsp+60h+phkResult], ebx; wil::details *
0x140040d88  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140040d8d  jmp     short loc_140040DCD
0x140040d8f  mov     rdx, [rdi+68h]; lpSubKey
0x140040d93  mov     rcx, [rbp+hKey]; hKey
0x140040d97  call    cs:__imp_RegDeleteTreeW
0x140040d9e  nop     dword ptr [rax+rax+00h]
0x140040da3  mov     ebx, eax
0x140040da5  test    eax, eax
0x140040da7  jz      short loc_140040DCB
0x140040da9  jle     short loc_140040DB4
0x140040dab  movzx   ebx, ax
0x140040dae  or      ebx, 80070000h
0x140040db4  mov     rax, [rdi+68h]
0x140040db8  mov     edx, 55h ; 'U'
0x140040dbd  mov     [rsp+60h+var_30], rax
0x140040dc2  lea     rax, aCouldNotDelete_0; "Could not delete ReportId %ws tree"
0x140040dc9  jmp     short loc_140040D6D
0x140040dcb  xor     ebx, ebx
0x140040dcd  mov     rcx, [rbp+hKey]; hKey
0x140040dd1  test    rcx, rcx
0x140040dd4  jz      short loc_140040DE2
0x140040dd6  call    cs:__imp_RegCloseKey
0x140040ddd  nop     dword ptr [rax+rax+00h]
0x140040de2  mov     rcx, [rbp+lpSubKey]; void *
0x140040de6  lea     rax, [rbp+var_10]
0x140040dea  cmp     rcx, rax
0x140040ded  jz      short loc_140040DFB
0x140040def  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140040df6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140040dfb  lea     r11, [rsp+60h+var_s0]
0x140040e00  mov     eax, ebx
0x140040e02  mov     rbx, [r11+18h]
0x140040e06  mov     rdi, [r11+20h]
0x140040e0a  mov     rsp, r11
0x140040e0d  pop     rbp
0x140040e0e  retn
```
