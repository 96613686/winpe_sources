# CLiveDumpProcessor::CancelMiniLiveReport(void)

- ea: `0x14003e244`
- end: `0x14003e3a9`
- name: `?CancelMiniLiveReport@CLiveDumpProcessor@@AEAAJXZ`
- size: `357`
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
- `0x14003e244`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003e376`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003e376`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003e2e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003e2e7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14003e33d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14003e33d`

## string_xrefs

- `0x14003e298`: `Failed to sprintf registry key name`
- `0x14003e30c`: `Could not open key %ws`
- `0x14003e362`: `Could not delete ReportId %ws tree`

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
0x14003e244  mov     [rsp-8+arg_8], rbx
0x14003e249  mov     [rsp-8+arg_10], rdi
0x14003e24e  push    rbp
0x14003e24f  mov     rbp, rsp
0x14003e252  sub     rsp, 60h
0x14003e256  mov     r9, [rcx+48h]
0x14003e25a  lea     rax, [rbp+var_10]
0x14003e25e  mov     [rbp+lpSubKey], rax
0x14003e262  lea     r8, ?g_wszLiveKernelReportsQueueRoot@@3PA_WA; "System\\CurrentControlSet\\Control\\Cra"...
0x14003e269  lea     rax, [rbp+var_10]
0x14003e26d  mov     rdi, rcx
0x14003e270  mov     [rbp+var_18], rax
0x14003e274  lea     rdx, aSLivekernelrep_0; "%s\\LiveKernelReports\\%s"
0x14003e27b  xor     eax, eax
0x14003e27d  lea     rcx, [rbp+lpSubKey]
0x14003e281  mov     [rbp+var_10], ax
0x14003e285  mov     [rbp+hKey], rax
0x14003e289  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14003e28e  mov     ebx, eax
0x14003e290  test    eax, eax
0x14003e292  jns     short loc_14003E2C5
0x14003e294  mov     rcx, [rbp+8]; this
0x14003e298  lea     rax, aFailedToSprint; "Failed to sprintf registry key name"
0x14003e29f  mov     qword ptr [rsp+60h+var_38], rax; int
0x14003e2a4  lea     r9, aClivedumpproce_1; "CLiveDumpProcessor::CancelMiniLiveRepor"...
0x14003e2ab  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14003e2b2  mov     dword ptr [rsp+60h+phkResult], ebx; wil::details *
0x14003e2b6  mov     edx, 40h ; '@'; void *
0x14003e2bb  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003e2c0  jmp     loc_14003E36D
0x14003e2c5  lea     rcx, [rbp+hKey]
0x14003e2c9  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003e2ce  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x14003e2d2  mov     r9d, 3001Bh; samDesired
0x14003e2d8  xor     r8d, r8d; ulOptions
0x14003e2db  mov     [rsp+60h+phkResult], rax; phkResult
0x14003e2e0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003e2e7  call    cs:__imp_RegOpenKeyExW
0x14003e2ed  mov     ebx, eax
0x14003e2ef  test    eax, eax
0x14003e2f1  jz      short loc_14003E335
0x14003e2f3  jle     short loc_14003E2FE
0x14003e2f5  movzx   ebx, ax
0x14003e2f8  or      ebx, 80070000h
0x14003e2fe  mov     rax, [rbp+lpSubKey]
0x14003e302  mov     edx, 4Dh ; 'M'; void *
0x14003e307  mov     [rsp+60h+var_30], rax; char *
0x14003e30c  lea     rax, aCouldNotOpenKe; "Could not open key %ws"
0x14003e313  mov     rcx, [rbp+8]; this
0x14003e317  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14003e31e  mov     qword ptr [rsp+60h+var_38], rax; int
0x14003e323  lea     r9, aClivedumpproce_1; "CLiveDumpProcessor::CancelMiniLiveRepor"...
0x14003e32a  mov     dword ptr [rsp+60h+phkResult], ebx; wil::details *
0x14003e32e  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003e333  jmp     short loc_14003E36D
0x14003e335  mov     rdx, [rdi+68h]; lpSubKey
0x14003e339  mov     rcx, [rbp+hKey]; hKey
0x14003e33d  call    cs:__imp_RegDeleteTreeW
0x14003e343  mov     ebx, eax
0x14003e345  test    eax, eax
0x14003e347  jz      short loc_14003E36B
0x14003e349  jle     short loc_14003E354
0x14003e34b  movzx   ebx, ax
0x14003e34e  or      ebx, 80070000h
0x14003e354  mov     rax, [rdi+68h]
0x14003e358  mov     edx, 55h ; 'U'
0x14003e35d  mov     [rsp+60h+var_30], rax
0x14003e362  lea     rax, aCouldNotDelete_0; "Could not delete ReportId %ws tree"
0x14003e369  jmp     short loc_14003E313
0x14003e36b  xor     ebx, ebx
0x14003e36d  mov     rcx, [rbp+hKey]; hKey
0x14003e371  test    rcx, rcx
0x14003e374  jz      short loc_14003E37C
0x14003e376  call    cs:__imp_RegCloseKey
0x14003e37c  mov     rcx, [rbp+lpSubKey]; void *
0x14003e380  lea     rax, [rbp+var_10]
0x14003e384  cmp     rcx, rax
0x14003e387  jz      short loc_14003E395
0x14003e389  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003e390  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003e395  lea     r11, [rsp+60h+var_s0]
0x14003e39a  mov     eax, ebx
0x14003e39c  mov     rbx, [r11+18h]
0x14003e3a0  mov     rdi, [r11+20h]
0x14003e3a4  mov     rsp, r11
0x14003e3a7  pop     rbp
0x14003e3a8  retn
```
