# AIXPolicyHelper::InstallAttempts::SaveAttemptsToRegistry(AIXPolicyHelper::InstallAttempts const &,HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001e2dc`
- end: `0x18001e448`
- name: `?SaveAttemptsToRegistry@InstallAttempts@AIXPolicyHelper@@SAXAEBU12@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b7fc`
- `0x18002d050`

## callees

- `0x18001e2dc`
- `0x18002062c`
- `0x1800233ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e432`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e432`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e35a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e3aa`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e3fb`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e35a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e3aa`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e3fb`

## string_xrefs

- `0x18001e335`: `AttemptedInstallCount`
- `0x18001e3db`: `MaxInstallAttemptsAllowed`
- `0x18001e374`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`
- `0x18001e3c4`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`
- `0x18001e41a`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`

## pseudocode

```c
void __fastcall AIXPolicyHelper::InstallAttempts::SaveAttemptsToRegistry(_DWORD *a1, __int64 a2, __int64 a3)
{
  bool v3; // cc
  const WCHAR *v4; // rax
  int v6; // eax
  __int64 v7; // rdx
  int v8; // eax
  bool v9; // sf
  int v10; // eax
  bool v11; // sf
  bool v12; // sf
  int lpData; // [rsp+20h] [rbp-10h]
  int lpDataa; // [rsp+20h] [rbp-10h]
  int lpDatab; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  __int64 Data; // [rsp+48h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF

  Data = a2;
  v3 = *(_QWORD *)(a3 + 24) <= 7u;
  v4 = (const WCHAR *)a3;
  hKey = 0;
  if ( !v3 )
    v4 = *(const WCHAR **)a3;
  v6 = wil::reg::open_unique_key_nothrow(HKEY_LOCAL_MACHINE, v4, &hKey);
  if ( v6 < 0 )
  {
    v7 = 779;
LABEL_17:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
      (const char *)(unsigned int)v6,
      lpData);
    goto LABEL_18;
  }
  LODWORD(Data) = a1[1];
  v8 = RegSetKeyValueW(hKey, 0, L"AttemptedInstallCount", 4u, &Data, 4u);
  v9 = v8 < 0;
  if ( v8 > 0 )
  {
    v8 = (unsigned __int16)v8 | 0x80070000;
    v9 = v8 < 0;
  }
  if ( v9 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x30D,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
      (const char *)(unsigned int)v8,
      lpDataa);
  LODWORD(Data) = *a1;
  v10 = RegSetKeyValueW(hKey, 0, L"LastBuild", 4u, &Data, 4u);
  v11 = v10 < 0;
  if ( v10 > 0 )
  {
    v10 = (unsigned __int16)v10 | 0x80070000;
    v11 = v10 < 0;
  }
  if ( v11 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x30E,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
      (const char *)(unsigned int)v10,
      lpDatab);
  LODWORD(Data) = a1[2];
  v6 = RegSetKeyValueW(hKey, 0, L"MaxInstallAttemptsAllowed", 4u, &Data, 4u);
  v12 = v6 < 0;
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
    v12 = v6 < 0;
  }
  if ( v12 )
  {
    v7 = 783;
    goto LABEL_17;
  }
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18001e2dc  mov     [rsp-8+arg_0], rbx
0x18001e2e1  mov     [rsp-8+arg_18], rsi
0x18001e2e6  mov     [rsp-8+Data], rdx
0x18001e2eb  push    rbp
0x18001e2ec  mov     rbp, rsp
0x18001e2ef  sub     rsp, 30h
0x18001e2f3  cmp     qword ptr [r8+18h], 7
0x18001e2f8  mov     rax, r8
0x18001e2fb  mov     rbx, rcx
0x18001e2fe  mov     [rbp+hKey], 0
0x18001e306  jbe     short loc_18001E30B
0x18001e308  mov     rax, [r8]
0x18001e30b  mov     r9d, 1
0x18001e311  lea     r8, [rbp+hKey]; phkResult
0x18001e315  mov     rdx, rax; lpSubKey
0x18001e318  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e31f  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18001e324  test    eax, eax
0x18001e326  jns     short loc_18001E332
0x18001e328  mov     edx, 30Bh
0x18001e32d  jmp     loc_18001E416
0x18001e332  mov     eax, [rbx+4]
0x18001e335  lea     r8, aAttemptedinsta; "AttemptedInstallCount"
0x18001e33c  mov     rcx, [rbp+hKey]; hKey
0x18001e340  mov     esi, 4
0x18001e345  mov     dword ptr [rbp+Data], eax
0x18001e348  mov     r9d, esi; dwType
0x18001e34b  lea     rax, [rbp+Data]
0x18001e34f  mov     [rsp+30h+cbData], esi; cbData
0x18001e353  xor     edx, edx; lpSubKey
0x18001e355  mov     [rsp+30h+lpData], rax; int
0x18001e35a  call    cs:__imp_RegSetKeyValueW
0x18001e360  test    eax, eax
0x18001e362  jle     short loc_18001E36E
0x18001e364  movzx   eax, ax
0x18001e367  or      eax, 80070000h
0x18001e36c  test    eax, eax
0x18001e36e  jns     short loc_18001E388
0x18001e370  mov     rcx, [rbp+8]; this
0x18001e374  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x18001e37b  mov     r9d, eax; char *
0x18001e37e  mov     edx, 30Dh; void *
0x18001e383  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e388  mov     eax, [rbx]
0x18001e38a  lea     r8, aLastbuild; "LastBuild"
0x18001e391  mov     rcx, [rbp+hKey]; hKey
0x18001e395  mov     r9d, esi; dwType
0x18001e398  mov     dword ptr [rbp+Data], eax
0x18001e39b  xor     edx, edx; lpSubKey
0x18001e39d  lea     rax, [rbp+Data]
0x18001e3a1  mov     [rsp+30h+cbData], esi; cbData
0x18001e3a5  mov     [rsp+30h+lpData], rax; int
0x18001e3aa  call    cs:__imp_RegSetKeyValueW
0x18001e3b0  test    eax, eax
0x18001e3b2  jle     short loc_18001E3BE
0x18001e3b4  movzx   eax, ax
0x18001e3b7  or      eax, 80070000h
0x18001e3bc  test    eax, eax
0x18001e3be  jns     short loc_18001E3D8
0x18001e3c0  mov     rcx, [rbp+8]; this
0x18001e3c4  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x18001e3cb  mov     r9d, eax; char *
0x18001e3ce  mov     edx, 30Eh; void *
0x18001e3d3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e3d8  mov     eax, [rbx+8]
0x18001e3db  lea     r8, aMaxinstallatte; "MaxInstallAttemptsAllowed"
0x18001e3e2  mov     rcx, [rbp+hKey]; hKey
0x18001e3e6  mov     r9d, esi; dwType
0x18001e3e9  mov     dword ptr [rbp+Data], eax
0x18001e3ec  xor     edx, edx; lpSubKey
0x18001e3ee  lea     rax, [rbp+Data]
0x18001e3f2  mov     [rsp+30h+cbData], esi; cbData
0x18001e3f6  mov     [rsp+30h+lpData], rax; int
0x18001e3fb  call    cs:__imp_RegSetKeyValueW
0x18001e401  test    eax, eax
0x18001e403  jle     short loc_18001E40F
0x18001e405  movzx   eax, ax
0x18001e408  or      eax, 80070000h
0x18001e40d  test    eax, eax
0x18001e40f  jns     short loc_18001E429
0x18001e411  mov     edx, 30Fh; void *
0x18001e416  mov     rcx, [rbp+8]; this
0x18001e41a  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x18001e421  mov     r9d, eax; char *
0x18001e424  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e429  mov     rcx, [rbp+hKey]; hKey
0x18001e42d  test    rcx, rcx
0x18001e430  jz      short loc_18001E438
0x18001e432  call    cs:__imp_RegCloseKey
0x18001e438  mov     rbx, [rsp+30h+arg_0]
0x18001e43d  mov     rsi, [rsp+30h+arg_18]
0x18001e442  add     rsp, 30h
0x18001e446  pop     rbp
0x18001e447  retn
```
