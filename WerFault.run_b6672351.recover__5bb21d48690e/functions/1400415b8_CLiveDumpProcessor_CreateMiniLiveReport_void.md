# CLiveDumpProcessor::CreateMiniLiveReport(void)

- ea: `0x1400415b8`
- end: `0x1400416ed`
- name: `?CreateMiniLiveReport@CLiveDumpProcessor@@AEAAJXZ`
- size: `309`
- prototype: `__int64 __fastcall(CLiveDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400416f4`

## callees

- `0x140002748`
- `0x1400054e4`
- `0x14000551c`
- `0x1400372dc`
- `0x1400415b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400416b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400416b7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140041661`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140041661`

## string_xrefs

- `0x140041609`: `Failed to sprintf registry key name`
- `0x14004169b`: `CLiveDumpProcessor::CreateLiveReportKey`
- `0x140041682`: `RegCreateKeyEx failed`

## pseudocode

```c
__int64 __fastcall CLiveDumpProcessor::CreateMiniLiveReport(CLiveDumpProcessor *this)
{
  __int64 v1; // r9
  signed int v2; // ebx
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  wil::details *dwOptions; // [rsp+20h] [rbp-50h]
  wil::details *dwOptionsa; // [rsp+20h] [rbp-50h]
  const char *lpSecurityAttributes; // [rsp+30h] [rbp-40h]
  const char *lpSecurityAttributesa; // [rsp+30h] [rbp-40h]
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-20h] BYREF
  _WORD v11[8]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+78h] [rbp+8h]
  HKEY hKey; // [rsp+80h] [rbp+10h] BYREF

  v1 = *((_QWORD *)this + 9);
  lpSubKey[0] = v11;
  lpSubKey[1] = v11;
  v11[0] = 0;
  hKey = 0;
  v2 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         lpSubKey,
         L"%s\\LiveKernelReports\\%s\\%s\\Busy",
         g_wszLiveKernelReportsQueueRoot,
         v1,
         *((_QWORD *)this + 13));
  if ( v2 < 0 )
  {
    LODWORD(dwOptions) = v2;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x20E,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
      "CLiveDumpProcessor::CreateLiveReportKey",
      dwOptions,
      (int)"Failed to sprintf registry key name",
      lpSecurityAttributes);
    goto LABEL_7;
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0, 0, 0x2001Du, 0, phkResult, 0);
  v2 = Key;
  if ( Key <= 0 )
  {
    if ( !Key )
      goto LABEL_7;
  }
  else
  {
    v2 = (unsigned __int16)Key | 0x80070000;
    Key = v2;
  }
  LODWORD(dwOptionsa) = Key;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0x220,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
    "CLiveDumpProcessor::CreateLiveReportKey",
    dwOptionsa,
    (int)"RegCreateKeyEx failed",
    lpSecurityAttributesa);
LABEL_7:
  if ( hKey )
    RegCloseKey(hKey);
  if ( lpSubKey[0] != v11 )
    operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400415b8  mov     [rsp-8+arg_8], rbx
0x1400415bd  push    rbp
0x1400415be  mov     rbp, rsp
0x1400415c1  sub     rsp, 70h
0x1400415c5  mov     r9, [rcx+48h]
0x1400415c9  lea     rax, [rbp+var_10]
0x1400415cd  mov     [rbp+lpSubKey], rax
0x1400415d1  lea     r8, ?g_wszLiveKernelReportsQueueRoot@@3PA_WA; "System\\CurrentControlSet\\Control\\Cra"...
0x1400415d8  lea     rax, [rbp+var_10]
0x1400415dc  mov     [rbp+var_18], rax
0x1400415e0  lea     rdx, aSLivekernelrep; "%s\\LiveKernelReports\\%s\\%s\\Busy"
0x1400415e7  xor     eax, eax
0x1400415e9  mov     [rbp+var_10], ax
0x1400415ed  mov     [rbp+hKey], rax
0x1400415f1  mov     rax, [rcx+68h]
0x1400415f5  lea     rcx, [rbp+lpSubKey]
0x1400415f9  mov     qword ptr [rsp+70h+dwOptions], rax
0x1400415fe  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140041603  mov     ebx, eax
0x140041605  test    eax, eax
0x140041607  jns     short loc_140041620
0x140041609  lea     rax, aFailedToSprint; "Failed to sprintf registry key name"
0x140041610  mov     edx, 20Eh
0x140041615  mov     qword ptr [rsp+70h+samDesired], rax
0x14004161a  mov     [rsp+70h+dwOptions], ebx
0x14004161e  jmp     short loc_140041697
0x140041620  lea     rcx, [rbp+hKey]
0x140041624  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140041629  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x14004162d  xor     r9d, r9d; lpClass
0x140041630  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x140041639  xor     r8d, r8d; Reserved
0x14004163c  mov     [rsp+70h+phkResult], rax; phkResult
0x140041641  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140041648  mov     [rsp+70h+lpSecurityAttributes], 0; char *
0x140041651  mov     [rsp+70h+samDesired], 2001Dh; samDesired
0x140041659  mov     [rsp+70h+dwOptions], 0; dwOptions
0x140041661  call    cs:__imp_RegCreateKeyExW
0x140041668  nop     dword ptr [rax+rax+00h]
0x14004166d  mov     ebx, eax
0x14004166f  test    eax, eax
0x140041671  jle     short loc_140041680
0x140041673  movzx   ebx, ax
0x140041676  or      ebx, 80070000h
0x14004167c  mov     eax, ebx
0x14004167e  jmp     short loc_140041682
0x140041680  jz      short loc_1400416AE
0x140041682  lea     rdx, aRegcreatekeyex; "RegCreateKeyEx failed"
0x140041689  mov     qword ptr [rsp+70h+samDesired], rdx; int
0x14004168e  mov     edx, 220h; void *
0x140041693  mov     [rsp+70h+dwOptions], eax; wil::details *
0x140041697  mov     rcx, [rbp+8]; this
0x14004169b  lea     r9, aClivedumpproce_5; "CLiveDumpProcessor::CreateLiveReportKey"
0x1400416a2  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x1400416a9  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400416ae  mov     rcx, [rbp+hKey]; hKey
0x1400416b2  test    rcx, rcx
0x1400416b5  jz      short loc_1400416C3
0x1400416b7  call    cs:__imp_RegCloseKey
0x1400416be  nop     dword ptr [rax+rax+00h]
0x1400416c3  mov     rcx, [rbp+lpSubKey]; void *
0x1400416c7  lea     rax, [rbp+var_10]
0x1400416cb  cmp     rcx, rax
0x1400416ce  jz      short loc_1400416DC
0x1400416d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400416d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400416dc  mov     eax, ebx
0x1400416de  mov     rbx, [rsp+70h+arg_8]
0x1400416e6  add     rsp, 70h
0x1400416ea  pop     rbp
0x1400416eb  retn
```
