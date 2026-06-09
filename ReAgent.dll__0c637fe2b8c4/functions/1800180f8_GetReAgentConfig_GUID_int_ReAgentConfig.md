# GetReAgentConfig(_GUID *,int,ReAgentConfig * *)

- ea: `0x1800180f8`
- end: `0x180018356`
- name: `?GetReAgentConfig@@YAKPEAU_GUID@@HPEAPEAVReAgentConfig@@@Z`
- size: `606`
- prototype: `__int64 __fastcall(struct _GUID *, int, struct ReAgentConfig **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800193e8`

## callees

- `0x180001f54`
- `0x1800059fc`
- `0x1800109d0`
- `0x1800180f8`
- `0x180030b98`
- `0x180031a00`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180018309`
- `ole32!CoTaskMemFree` at `0x180018309`

## string_xrefs

- `0x18001827a`: `DisableUpdateEnhancedConfigInfo`
- `0x18001813c`: `Get ReAgent config`
- `0x18001816a`: `base\diagnosis\srt\reagent2\reagent\installex.cpp`
- `0x1800182e1`: `base\diagnosis\srt\reagent2\reagent\installex.cpp`
- `0x180018179`: `Failed to get config path`
- `0x180018180`: `GetReAgentConfig %s (0x%x) in file %S line %d`
- `0x1800182f0`: `GetReAgentConfig %s (0x%x) in file %S line %d`
- `0x1800181c1`: `GetReAgentConfig Config file path: %s`
- `0x180018259`: `GetReAgentConfig System setup is in progress.`
- `0x18001826c`: `GetReAgentConfig Disabling update enhanced config info for legacy setup.`
- `0x1800182b5`: `Failed to initialize config file`

## pseudocode

```c
__int64 __fastcall GetReAgentConfig(struct _GUID *a1, int a2, struct ReAgentConfig **a3)
{
  struct ReAgentConfig **v3; // r15
  struct ReAgentConfig *v6; // rbx
  __int64 v7; // r8
  unsigned int ConfigFilePathFromOsGuid; // esi
  void *v9; // r14
  struct ReAgentConfig *v10; // rax
  int v12; // [rsp+28h] [rbp-50h]
  LPVOID pv; // [rsp+48h] [rbp-30h] BYREF

  v3 = a3;
  pv = 0;
  v6 = 0;
  UnattendLogW(0, L"Get ReAgent config");
  if ( a1 )
  {
    ConfigFilePathFromOsGuid = winreGetConfigFilePathFromOsGuid(a1);
    if ( ConfigFilePathFromOsGuid )
    {
      v12 = 63;
LABEL_4:
      UnattendLogW(
        2,
        L"GetReAgentConfig %s (0x%x) in file %S line %d",
        L"Failed to get config path",
        ConfigFilePathFromOsGuid,
        "base\\diagnosis\\srt\\reagent2\\reagent\\installex.cpp",
        v12);
      v9 = pv;
      goto LABEL_18;
    }
  }
  else
  {
    ConfigFilePathFromOsGuid = winreGetConfigFilePathFromWinDir(0, 0, v7, &pv);
    if ( ConfigFilePathFromOsGuid )
    {
      v12 = 72;
      goto LABEL_4;
    }
  }
  v9 = pv;
  UnattendLogW(0, L"GetReAgentConfig Config file path: %s", pv);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v10 = (struct ReAgentConfig *)operator new(0x50u);
    v6 = v10;
    if ( v10 )
    {
      *((_QWORD *)v10 + 1) = 0;
      *((_QWORD *)v10 + 2) = 0;
      *((_DWORD *)v10 + 6) = 0;
      *((_DWORD *)v10 + 7) = 2;
      *((_QWORD *)v10 + 4) = 0;
      *((_QWORD *)v10 + 5) = 0;
      *((_QWORD *)v10 + 6) = 0;
      *((_QWORD *)v10 + 7) = 0;
      *((_QWORD *)v10 + 8) = 0;
      *(_QWORD *)v10 = &ReAgentConfig::`vftable';
      *((_DWORD *)v10 + 18) = 0;
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v9 = pv;
      v6 = 0;
      v3 = a3;
      __eh34_try_continuation(0, std::bad_alloc `RTTI Type Descriptor', &loc_1800182BE);
LABEL_16:
      ConfigFilePathFromOsGuid = 8;
      UnattendLogW(
        2,
        L"GetReAgentConfig %s (0x%x) in file %S line %d",
        L"failed to allocate memory",
        8,
        "base\\diagnosis\\srt\\reagent2\\reagent\\installex.cpp",
        76);
      goto LABEL_18;
    }
  }
  if ( !v6 )
    goto LABEL_16;
  if ( (unsigned int)CheckRegKey(L"SYSTEM\\Setup", L"SystemSetupInProgress") )
  {
    UnattendLogW(0, L"GetReAgentConfig System setup is in progress.");
    if ( !a2 )
    {
      UnattendLogW(0, L"GetReAgentConfig Disabling update enhanced config info for legacy setup.");
      UnattendLogW(0, L"DisableUpdateEnhancedConfigInfo");
      *((_DWORD *)v6 + 18) = 1;
    }
  }
  ConfigFilePathFromOsGuid = (*(__int64 (__fastcall **)(struct ReAgentConfig *, void *, __int64))(*(_QWORD *)v6 + 8LL))(
                               v6,
                               v9,
                               1);
  if ( ConfigFilePathFromOsGuid )
    UnattendLogW(
      2,
      L"GetReAgentConfig %s (0x%x) in file %S line %d",
      L"Failed to initialize config file",
      ConfigFilePathFromOsGuid,
      "base\\diagnosis\\srt\\reagent2\\reagent\\installex.cpp",
      101);
LABEL_18:
  if ( v9 )
    CoTaskMemFree(v9);
  if ( ConfigFilePathFromOsGuid )
  {
    if ( v6 )
      (**(void (__fastcall ***)(struct ReAgentConfig *, __int64))v6)(v6, 1);
  }
  else
  {
    *v3 = v6;
  }
  return ConfigFilePathFromOsGuid;
}

```

## disassembly

```asm
0x1800180f8  mov     r11, rsp
0x1800180fb  push    r12
0x1800180fd  push    r14
0x1800180ff  push    r15
0x180018101  sub     rsp, 60h
0x180018105  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x18001810d  mov     [r11+10h], rbx
0x180018111  mov     [r11+20h], rsi
0x180018115  mov     rax, cs:__security_cookie
0x18001811c  xor     rax, rsp
0x18001811f  mov     [rsp+78h+var_28], rax
0x180018124  mov     r15, r8
0x180018127  mov     r12d, edx
0x18001812a  mov     rsi, rcx
0x18001812d  mov     [rsp+78h+var_40], r8
0x180018132  mov     qword ptr [r11-30h], 0
0x18001813a  xor     ebx, ebx
0x18001813c  lea     rdx, aGetReagentConf; "Get ReAgent config"
0x180018143  xor     ecx, ecx
0x180018145  call    UnattendLogW
0x18001814a  test    rsi, rsi
0x18001814d  jz      short loc_18001819B
0x18001814f  lea     r8, [rsp+78h+pv]
0x180018154  mov     rcx, rsi
0x180018157  call    winreGetConfigFilePathFromOsGuid
0x18001815c  mov     esi, eax
0x18001815e  test    eax, eax
0x180018160  jz      short loc_1800181B9
0x180018162  mov     [rsp+78h+var_50], 3Fh ; '?'
0x18001816a  lea     rax, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180018171  mov     [rsp+78h+var_58], rax
0x180018176  mov     r9d, esi
0x180018179  lea     r8, aFailedToGetCon_1; "Failed to get config path"
0x180018180  lea     rdx, aGetreagentconf_0; "GetReAgentConfig %s (0x%x) in file %S l"...
0x180018187  mov     ecx, 2
0x18001818c  call    UnattendLogW
0x180018191  mov     r14, [rsp+78h+pv]
0x180018196  jmp     loc_180018301
0x18001819b  lea     r9, [rsp+78h+pv]
0x1800181a0  xor     edx, edx
0x1800181a2  xor     ecx, ecx
0x1800181a4  call    winreGetConfigFilePathFromWinDir
0x1800181a9  mov     esi, eax
0x1800181ab  test    eax, eax
0x1800181ad  jz      short loc_1800181B9
0x1800181af  mov     [rsp+78h+var_50], 48h ; 'H'
0x1800181b7  jmp     short loc_18001816A
0x1800181b9  mov     r14, [rsp+78h+pv]
0x1800181be  mov     r8, r14
0x1800181c1  lea     rdx, aGetreagentconf_2; "GetReAgentConfig Config file path: %s"
0x1800181c8  xor     ecx, ecx
0x1800181ca  call    UnattendLogW
0x1800181cf  nop
0x1800181d0  mov     ecx, 50h ; 'P'; Size
0x1800181d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800181da  mov     rbx, rax
0x1800181dd  test    rbx, rbx
0x1800181e0  jz      short loc_180018239
0x1800181e2  mov     qword ptr [rax+8], 0
0x1800181ea  mov     qword ptr [rax+10h], 0
0x1800181f2  mov     dword ptr [rax+18h], 0
0x1800181f9  mov     dword ptr [rax+1Ch], 2
0x180018200  mov     qword ptr [rax+20h], 0
0x180018208  mov     qword ptr [rax+28h], 0
0x180018210  mov     qword ptr [rax+30h], 0
0x180018218  mov     qword ptr [rax+38h], 0
0x180018220  mov     qword ptr [rax+40h], 0
0x180018228  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x18001822f  mov     [rbx], rax
0x180018232  mov     dword ptr [rbx+48h], 0
0x180018239  test    rbx, rbx
0x18001823c  jz      loc_1800182CD
0x180018242  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x180018249  lea     rcx, aSystemSetup; "SYSTEM\\Setup"
0x180018250  call    CheckRegKey
0x180018255  test    eax, eax
0x180018257  jz      short loc_18001828F
0x180018259  lea     rdx, aGetreagentconf; "GetReAgentConfig System setup is in pro"...
0x180018260  xor     ecx, ecx
0x180018262  call    UnattendLogW
0x180018267  test    r12d, r12d
0x18001826a  jnz     short loc_18001828F
0x18001826c  lea     rdx, aGetreagentconf_1; "GetReAgentConfig Disabling update enhan"...
0x180018273  xor     ecx, ecx
0x180018275  call    UnattendLogW
0x18001827a  lea     rdx, aDisableupdatee; "DisableUpdateEnhancedConfigInfo"
0x180018281  xor     ecx, ecx
0x180018283  call    UnattendLogW
0x180018288  mov     dword ptr [rbx+48h], 1
0x18001828f  mov     rax, [rbx]
0x180018292  mov     r8d, 1
0x180018298  mov     rdx, r14
0x18001829b  mov     rcx, rbx
0x18001829e  mov     rax, [rax+8]
0x1800182a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182a7  mov     esi, eax
0x1800182a9  test    eax, eax
0x1800182ab  jz      short loc_180018301
0x1800182ad  mov     [rsp+78h+var_50], 65h ; 'e'
0x1800182b5  lea     r8, aFailedToInitia_0; "Failed to initialize config file"
0x1800182bc  jmp     short loc_1800182E1
0x1800182be  mov     r14, [rsp+78h+pv]
0x1800182c3  mov     rbx, [rsp+78h+var_48]
0x1800182c8  mov     r15, [rsp+78h+var_40]
0x1800182cd  mov     esi, 8
0x1800182d2  mov     [rsp+78h+var_50], 4Ch ; 'L'
0x1800182da  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x1800182e1  lea     rax, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800182e8  mov     [rsp+78h+var_58], rax
0x1800182ed  mov     r9d, esi
0x1800182f0  lea     rdx, aGetreagentconf_0; "GetReAgentConfig %s (0x%x) in file %S l"...
0x1800182f7  mov     ecx, 2
0x1800182fc  call    UnattendLogW
0x180018301  test    r14, r14
0x180018304  jz      short loc_18001830F
0x180018306  mov     rcx, r14; pv
0x180018309  call    cs:__imp_CoTaskMemFree
0x18001830f  test    esi, esi
0x180018311  jnz     short loc_180018318
0x180018313  mov     [r15], rbx
0x180018316  jmp     short loc_180018330
0x180018318  test    rbx, rbx
0x18001831b  jz      short loc_180018330
0x18001831d  mov     rax, [rbx]
0x180018320  mov     edx, 1
0x180018325  mov     rcx, rbx
0x180018328  mov     rax, [rax]
0x18001832b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018330  mov     eax, esi
0x180018332  mov     rcx, [rsp+78h+var_28]
0x180018337  xor     rcx, rsp; StackCookie
0x18001833a  call    __security_check_cookie
0x18001833f  lea     r11, [rsp+78h+var_18]
0x180018344  mov     rbx, [r11+28h]
0x180018348  mov     rsi, [r11+38h]
0x18001834c  mov     rsp, r11
0x18001834f  pop     r15
0x180018351  pop     r14
0x180018353  pop     r12
0x180018355  retn
```
