# Uev::Util::IsProcessTheShell(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,HKEY__ *)

- ea: `0x14001b48c`
- end: `0x14001b69f`
- name: `?IsProcessTheShell@Util@Uev@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHKEY__@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140014da0`

## callees

- `0x140003e50`
- `0x14000ac88`
- `0x14000ba60`
- `0x14000d5ac`
- `0x14000f01c`
- `0x1400191ec`
- `0x14001a310`
- `0x14001a7c4`
- `0x14001aae4`
- `0x14001b48c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001b60b`
- `ADVAPI32!RegOpenKeyExW` at `0x14001b60b`
- `KERNEL32!lstrcmpiW` at `0x14001b53f`
- `KERNEL32!lstrcmpiW` at `0x14001b53f`

## string_xrefs

- `0x14001b4c5`: `AgentService.Util::IsProcessTheShell: [%s]`
- `0x14001b55f`: `AgentService.Util::IsProcessTheShell: This process is recognized as the mock shell`
- `0x14001b58c`: `SOFTWARE\Microsoft\UEV\Agent\ShellProcesses\`
- `0x14001b61d`: `AgentService.Util::IsProcessTheShell: RegOpenKey passed`
- `0x14001b62d`: `AgentService.Util::IsProcessTheShell: RegOpenKey failed: [%ul]`
- `0x14001b66c`: `AgentService.Util::IsProcessTheShell: Exit [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall Uev::Util::IsProcessTheShell(const WCHAR *a1, __int64 a2)
{
  char v4; // di
  __int64 NameOfMockShellProgram; // rdx
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rax
  const WCHAR *v8; // rcx
  const WCHAR *v9; // rcx
  bool v10; // r14
  void *FileName; // rax
  __int64 v12; // rax
  const WCHAR *v13; // rdx
  char v15; // [rsp+30h] [rbp-78h]
  Uev::UevException *v16; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v17[32]; // [rsp+40h] [rbp-68h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-48h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+68h] [rbp-40h] BYREF
  __int128 v20; // [rsp+78h] [rbp-30h]

  DbgTraceFrmt<5,wchar_t const *>((wchar_t *)L"AgentService.Util::IsProcessTheShell: [%s]");
  try
  {
    v4 = 0;
    v15 = 0;
    NameOfMockShellProgram = Uev::Util::GetNameOfMockShellProgram(lpSubKey, a2);
    v6 = *((_QWORD *)a1 + 2);
    if ( v6
      && *(_QWORD *)(NameOfMockShellProgram + 16)
      && v6 >= *(_QWORD *)(NameOfMockShellProgram + 16)
      && ((v7 = v6 - *(_QWORD *)(NameOfMockShellProgram + 16)) == 0
       || (*((_QWORD *)a1 + 3) <= 7u ? (v8 = a1) : (v8 = *(const WCHAR **)a1), v8[v7 - 1] == 47 || v8[v7 - 1] == 92)) )
    {
      if ( *((_QWORD *)a1 + 3) <= 7u )
        v9 = a1;
      else
        v9 = *(const WCHAR **)a1;
      if ( *(_QWORD *)(NameOfMockShellProgram + 24) > 7u )
        NameOfMockShellProgram = *(_QWORD *)NameOfMockShellProgram;
      v10 = lstrcmpiW(&v9[v7], (LPCWSTR)NameOfMockShellProgram) == 0;
    }
    else
    {
      v10 = 0;
    }
    std::wstring::_Tidy_deallocate(lpSubKey);
    if ( v10 )
    {
      DbgTrace<5>(L"AgentService.Util::IsProcessTheShell: This process is recognized as the mock shell");
      v4 = 1;
      v15 = 1;
    }
    else
    {
      FileName = (void *)Uev::Util::ExtractFileName(v17, a1);
      v12 = std::wstring::_Insert<wchar_t>(FileName);
      *(_OWORD *)lpSubKey = 0;
      v20 = 0;
      *(_OWORD *)lpSubKey = *(_OWORD *)v12;
      v20 = *(_OWORD *)(v12 + 16);
      *(_QWORD *)(v12 + 16) = 0;
      *(_QWORD *)(v12 + 24) = 7;
      *(_WORD *)v12 = 0;
      std::wstring::_Tidy_deallocate(v17);
      phkResult = 0;
      v13 = (const WCHAR *)lpSubKey;
      if ( *((_QWORD *)&v20 + 1) > 7u )
        v13 = lpSubKey[0];
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v13, 0, 0x20019u, &phkResult) )
      {
        DbgTraceFrmt<5,long>((wchar_t *)L"AgentService.Util::IsProcessTheShell: RegOpenKey failed: [%ul]");
      }
      else
      {
        v4 = 1;
        v15 = 1;
        DbgTrace<5>(L"AgentService.Util::IsProcessTheShell: RegOpenKey passed");
      }
      Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&phkResult);
      std::wstring::_Tidy_deallocate(lpSubKey);
    }
  }
  catch ( Uev::UevException *v16 )
  {
    std::wstring::wstring((__int64)lpSubKey, (__int64)v16 + 24);
    DbgTraceFrmtErr<wchar_t const *>((wchar_t *)L"AgentService.Util::IsProcessTheShell: An error occurred while testing wh"
                                                 "ether the current process is the Shell: %s");
    std::wstring::_Tidy_deallocate(lpSubKey);
    v4 = v15;
  }
  DbgTraceFrmt<5,wchar_t const *>((wchar_t *)L"AgentService.Util::IsProcessTheShell: Exit [%s]");
  return v4;
}

```

## disassembly

```asm
0x14001b48c  mov     [rsp+arg_10], rbx
0x14001b491  push    rsi
0x14001b492  push    rdi
0x14001b493  push    r14
0x14001b495  sub     rsp, 90h
0x14001b49c  mov     rax, cs:__security_cookie
0x14001b4a3  xor     rax, rsp
0x14001b4a6  mov     [rsp+0A8h+var_20], rax
0x14001b4ae  mov     r14, rdx
0x14001b4b1  mov     rsi, rcx
0x14001b4b4  xor     ebx, ebx
0x14001b4b6  cmp     qword ptr [rcx+18h], 7
0x14001b4bb  jbe     short loc_14001B4C2
0x14001b4bd  mov     rdx, [rcx]
0x14001b4c0  jmp     short loc_14001B4C5
0x14001b4c2  mov     rdx, rsi
0x14001b4c5  lea     rcx, aAgentserviceUt_34; "AgentService.Util::IsProcessTheShell: ["...
0x14001b4cc  call    ??$DbgTraceFrmt@$04PEB_W@@YAXPEB_W0@Z; DbgTraceFrmt<5,wchar_t const *>(wchar_t const *,wchar_t const *)
0x14001b4d1  mov     dil, bl
0x14001b4d4  mov     [rsp+0A8h+var_78], bl
0x14001b4d8  mov     rdx, r14
0x14001b4db  lea     rcx, [rsp+0A8h+lpSubKey]
0x14001b4e0  call    ?GetNameOfMockShellProgram@Util@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHKEY__@@@Z; Uev::Util::GetNameOfMockShellProgram(HKEY__ *)
0x14001b4e5  mov     rdx, rax
0x14001b4e8  mov     rax, [rsi+10h]
0x14001b4ec  test    rax, rax
0x14001b4ef  jz      short loc_14001B54D
0x14001b4f1  cmp     [rdx+10h], rbx
0x14001b4f5  jz      short loc_14001B54D
0x14001b4f7  cmp     rax, [rdx+10h]
0x14001b4fb  jb      short loc_14001B54D
0x14001b4fd  sub     rax, [rdx+10h]
0x14001b501  jz      short loc_14001B522
0x14001b503  cmp     qword ptr [rsi+18h], 7
0x14001b508  jbe     short loc_14001B50F
0x14001b50a  mov     rcx, [rsi]
0x14001b50d  jmp     short loc_14001B512
0x14001b50f  mov     rcx, rsi
0x14001b512  cmp     word ptr [rcx+rax*2-2], 2Fh ; '/'
0x14001b518  jz      short loc_14001B522
0x14001b51a  cmp     word ptr [rcx+rax*2-2], 5Ch ; '\'
0x14001b520  jnz     short loc_14001B54D
0x14001b522  cmp     qword ptr [rsi+18h], 7
0x14001b527  jbe     short loc_14001B52E
0x14001b529  mov     rcx, [rsi]
0x14001b52c  jmp     short loc_14001B531
0x14001b52e  mov     rcx, rsi
0x14001b531  cmp     qword ptr [rdx+18h], 7
0x14001b536  jbe     short loc_14001B53B
0x14001b538  mov     rdx, [rdx]; lpString2
0x14001b53b  lea     rcx, [rcx+rax*2]; lpString1
0x14001b53f  call    cs:__imp_lstrcmpiW
0x14001b545  test    eax, eax
0x14001b547  setz    r14b
0x14001b54b  jmp     short loc_14001B550
0x14001b54d  mov     r14b, bl
0x14001b550  lea     rcx, [rsp+0A8h+lpSubKey]
0x14001b555  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001b55a  test    r14b, r14b
0x14001b55d  jz      short loc_14001B578
0x14001b55f  lea     rcx, aAgentserviceUt_31; "AgentService.Util::IsProcessTheShell: T"...
0x14001b566  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14001b56b  mov     dil, 1
0x14001b56e  mov     [rsp+0A8h+var_78], dil
0x14001b573  jmp     loc_14001B650
0x14001b578  mov     rdx, rsi
0x14001b57b  lea     rcx, [rsp+0A8h+var_68]
0x14001b580  call    ?ExtractFileName@Util@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@@Z; Uev::Util::ExtractFileName(std::wstring const &)
0x14001b585  nop
0x14001b586  mov     r9d, 2Ch ; ','
0x14001b58c  lea     r8, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\UEV\\Agent\\ShellP"...
0x14001b593  xor     edx, edx
0x14001b595  mov     rcx, rax; Src
0x14001b598  call    ??$_Insert@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KQEB_W0@Z; std::wstring::_Insert<wchar_t>(unsigned __int64,wchar_t const * const,unsigned __int64)
0x14001b59d  xorps   xmm0, xmm0
0x14001b5a0  movups  xmmword ptr [rsp+0A8h+lpSubKey], xmm0
0x14001b5a5  xorps   xmm1, xmm1
0x14001b5a8  movdqu  [rsp+0A8h+var_30], xmm1
0x14001b5ae  movups  xmm0, xmmword ptr [rax]
0x14001b5b1  movups  xmmword ptr [rsp+0A8h+lpSubKey], xmm0
0x14001b5b6  movups  xmm1, xmmword ptr [rax+10h]
0x14001b5ba  movups  [rsp+0A8h+var_30], xmm1
0x14001b5bf  mov     [rax+10h], rbx
0x14001b5c3  mov     qword ptr [rax+18h], 7
0x14001b5cb  mov     [rax], bx
0x14001b5ce  lea     rcx, [rsp+0A8h+var_68]
0x14001b5d3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001b5d8  mov     [rsp+0A8h+var_48], rbx
0x14001b5dd  lea     rdx, [rsp+0A8h+lpSubKey]
0x14001b5e2  cmp     qword ptr [rsp+0A8h+var_30+8], 7
0x14001b5eb  cmova   rdx, [rsp+0A8h+lpSubKey]; lpSubKey
0x14001b5f1  lea     rax, [rsp+0A8h+var_48]
0x14001b5f6  mov     [rsp+0A8h+phkResult], rax; phkResult
0x14001b5fb  mov     r9d, 20019h; samDesired
0x14001b601  xor     r8d, r8d; ulOptions
0x14001b604  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001b60b  call    cs:__imp_RegOpenKeyExW
0x14001b611  test    eax, eax
0x14001b613  jnz     short loc_14001B62B
0x14001b615  mov     dil, 1
0x14001b618  mov     [rsp+0A8h+var_78], dil
0x14001b61d  lea     rcx, aAgentserviceUt_36; "AgentService.Util::IsProcessTheShell: R"...
0x14001b624  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14001b629  jmp     short loc_14001B63A
0x14001b62b  mov     edx, eax
0x14001b62d  lea     rcx, aAgentserviceUt_8; "AgentService.Util::IsProcessTheShell: R"...
0x14001b634  call    ??$DbgTraceFrmt@$04J@@YAXPEB_WJ@Z; DbgTraceFrmt<5,long>(wchar_t const *,long)
0x14001b639  nop
0x14001b63a  lea     rcx, [rsp+0A8h+var_48]
0x14001b63f  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x14001b644  nop
0x14001b645  lea     rcx, [rsp+0A8h+lpSubKey]
0x14001b64a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001b64f  nop
0x14001b650  jmp     short loc_14001B657
0x14001b652  mov     dil, [rsp+0A8h+var_78]
0x14001b657  lea     rdx, aTrue; "true"
0x14001b65e  lea     rax, aFalse; "false"
0x14001b665  test    dil, dil
0x14001b668  cmovz   rdx, rax
0x14001b66c  lea     rcx, aAgentserviceUt_11; "AgentService.Util::IsProcessTheShell: E"...
0x14001b673  call    ??$DbgTraceFrmt@$04PEB_W@@YAXPEB_W0@Z; DbgTraceFrmt<5,wchar_t const *>(wchar_t const *,wchar_t const *)
0x14001b678  mov     al, dil
0x14001b67b  mov     rcx, [rsp+0A8h+var_20]
0x14001b683  xor     rcx, rsp; StackCookie
0x14001b686  call    __security_check_cookie
0x14001b68b  mov     rbx, [rsp+0A8h+arg_10]
0x14001b693  add     rsp, 90h
0x14001b69a  pop     r14
0x14001b69c  pop     rdi
0x14001b69d  pop     rsi
0x14001b69e  retn
```
