# RegistrySCDStore::GetScenarioDefinitionInfosByName(ushort const *,ushort const *,ushort const *,std::vector<std::shared_ptr<SCDScenarioInfo>,std::allocator<std::shared_ptr<SCDScenarioInfo>>> &)

- ea: `0x1800f06a0`
- end: `0x1800f0a73`
- name: `?GetScenarioDefinitionInfosByName@RegistrySCDStore@@AEAAJPEBG00AEAV?$vector@V?$shared_ptr@VSCDScenarioInfo@@@std@@V?$allocator@V?$shared_ptr@VSCDScenarioInfo@@@std@@@2@@std@@@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f0a7c`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180019208`
- `0x180019f08`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18004abf8`
- `0x1800600bc`
- `0x1800ef060`
- `0x1800f06a0`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800f099f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800f099f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800f0946`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800f0946`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f07c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f07c6`

## string_xrefs

- `0x1800f06f2`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f0779`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f07f8`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f083f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`
- `0x1800f0a4f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\scdparserreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RegistrySCDStore::GetScenarioDefinitionInfosByName(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v9; // rdx
  signed int v10; // ebx
  LSTATUS v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  _QWORD *v16; // rcx
  LSTATUS v18; // eax
  DWORD i; // esi
  LSTATUS v20; // eax
  int v21; // eax
  _QWORD *v22; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  void *p_lpSubKey; // [rsp+68h] [rbp-98h] BYREF
  HKEY v27; // [rsp+70h] [rbp-90h] BYREF
  char v28; // [rsp+78h] [rbp-88h]
  DWORD cSubKeys; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchName; // [rsp+84h] [rbp-7Ch] BYREF
  LPCWSTR lpSubKey; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  if ( a2 )
  {
    if ( !a4 )
    {
      v9 = 245;
      goto LABEL_3;
    }
    lpSubKey = 0;
    p_lpSubKey = &lpSubKey;
    v27 = 0;
    v28 = 1;
    v10 = DCStringCchPrintfAllStrings(&v27, L"%s\\%s\\%s", 3);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFE,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
        (const char *)(unsigned int)v10,
        a4);
LABEL_27:
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
      return (unsigned int)v10;
    }
    hKey = 0;
    p_lpSubKey = &hKey;
    v27 = 0;
    v28 = 1;
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &v27);
    v10 = v11;
    if ( v11 > 0 )
      v10 = (unsigned __int16)v11 | 0x80070000;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
    if ( v10 < 0 )
    {
      v12 = 262;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
        (const char *)(unsigned int)v10,
        phkResulta);
LABEL_13:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_27;
    }
    if ( a3 )
    {
      std::make_shared<SCDScenarioInfo,>(&p_lpSubKey);
      if ( !p_lpSubKey )
      {
        v10 = -2147024882;
        v13 = 2147942414LL;
        v14 = 267;
        goto LABEL_17;
      }
      phkResulta = (int)p_lpSubKey;
      v15 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)(a1 + 8) + 16LL))(
              a1 + 8,
              a2,
              a3,
              a4);
      v10 = v15;
      if ( v15 < 0 )
      {
        v13 = (unsigned int)v15;
        v14 = 268;
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
          (const char *)v13,
          phkResulta);
        if ( v27 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v27);
        goto LABEL_13;
      }
      v16 = *(_QWORD **)(a5 + 8);
      if ( v16 == *(_QWORD **)(a5 + 16) )
      {
        std::vector<std::shared_ptr<DCURI>>::_Emplace_reallocate<std::shared_ptr<DCURI> const &>(
          (__int64 *)a5,
          *(void **)(a5 + 8),
          (__int64)&p_lpSubKey);
      }
      else
      {
        std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(v16, &p_lpSubKey);
        *(_QWORD *)(a5 + 8) += 16LL;
      }
      if ( v27 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v27);
    }
    else
    {
      cSubKeys = 0;
      v18 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      v10 = v18;
      if ( v18 > 0 )
        v10 = (unsigned __int16)v18 | 0x80070000;
      if ( v10 < 0 )
      {
        v12 = 275;
        goto LABEL_12;
      }
      for ( i = 0; i < cSubKeys; ++i )
      {
        cchName = 260;
        v20 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
        v10 = v20;
        if ( v20 > 0 )
          v10 = (unsigned __int16)v20 | 0x80070000;
        if ( v10 < 0 )
        {
          v12 = 288;
          goto LABEL_12;
        }
        std::make_shared<SCDScenarioInfo,>(&p_lpSubKey);
        if ( !p_lpSubKey )
        {
          v10 = -2147024882;
          v13 = 2147942414LL;
          v14 = 290;
          goto LABEL_17;
        }
        phkResulta = (int)p_lpSubKey;
        v21 = (*(__int64 (__fastcall **)(__int64, __int64, WCHAR *, __int64))(*(_QWORD *)(a1 + 8) + 16LL))(
                a1 + 8,
                a2,
                Name,
                a4);
        v10 = v21;
        if ( v21 < 0 )
        {
          v13 = (unsigned int)v21;
          v14 = 291;
          goto LABEL_17;
        }
        v22 = *(_QWORD **)(a5 + 8);
        if ( v22 == *(_QWORD **)(a5 + 16) )
        {
          std::vector<std::shared_ptr<DCURI>>::_Emplace_reallocate<std::shared_ptr<DCURI> const &>(
            (__int64 *)a5,
            *(void **)(a5 + 8),
            (__int64)&p_lpSubKey);
        }
        else
        {
          std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(v22, &p_lpSubKey);
          *(_QWORD *)(a5 + 8) += 16LL;
        }
        if ( v27 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v27);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v10 = 0;
    goto LABEL_27;
  }
  v9 = 244;
LABEL_3:
  v10 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\scdparserreg.cpp",
    (const char *)0x80070057LL,
    phkResult);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800f06a0  push    rbp
0x1800f06a2  push    rbx
0x1800f06a3  push    rsi
0x1800f06a4  push    rdi
0x1800f06a5  push    r12
0x1800f06a7  push    r13
0x1800f06a9  push    r14
0x1800f06ab  push    r15
0x1800f06ad  lea     rbp, [rsp-1B8h]
0x1800f06b5  sub     rsp, 2B8h
0x1800f06bc  mov     rax, cs:__security_cookie
0x1800f06c3  xor     rax, rsp
0x1800f06c6  mov     [rbp+1F0h+var_50], rax
0x1800f06cd  mov     r14, r9
0x1800f06d0  mov     rsi, r8
0x1800f06d3  mov     r15, rdx
0x1800f06d6  mov     r13, rcx
0x1800f06d9  mov     rdi, [rbp+1F0h+arg_20]
0x1800f06e0  xor     r12d, r12d
0x1800f06e3  test    rdx, rdx
0x1800f06e6  jnz     short loc_1800F070D
0x1800f06e8  mov     edx, 0F4h; void *
0x1800f06ed  mov     ebx, 80070057h
0x1800f06f2  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800f06f9  mov     r9d, ebx; char *
0x1800f06fc  mov     rcx, [rbp+1F8h]; this
0x1800f0703  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0708  jmp     loc_1800F08E4
0x1800f070d  test    r14, r14
0x1800f0710  jnz     short loc_1800F0719
0x1800f0712  mov     edx, 0F5h
0x1800f0717  jmp     short loc_1800F06ED
0x1800f0719  mov     [rbp+1F0h+lpSubKey], r12
0x1800f071d  lea     r9, [rcx+10h]
0x1800f0721  cmp     qword ptr [r9+18h], 7
0x1800f0726  jbe     short loc_1800F072B
0x1800f0728  mov     r9, [r9]
0x1800f072b  lea     rax, [rbp+1F0h+lpSubKey]
0x1800f072f  mov     [rsp+2F0h+var_288], rax
0x1800f0734  mov     [rsp+2F0h+var_280], r12
0x1800f0739  mov     [rsp+2F0h+var_278], 1
0x1800f073e  mov     [rsp+2F0h+lpcbMaxSubKeyLen], r15
0x1800f0743  mov     [rsp+2F0h+phkResult], r14; int
0x1800f0748  mov     r8d, 3
0x1800f074e  lea     rdx, aSSS; "%s\\%s\\%s"
0x1800f0755  lea     rcx, [rsp+2F0h+var_280]
0x1800f075a  call    DCStringCchPrintfAllStrings
0x1800f075f  mov     ebx, eax
0x1800f0761  lea     rcx, [rsp+2F0h+var_288]
0x1800f0766  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800f076b  test    ebx, ebx
0x1800f076d  jns     short loc_1800F078F
0x1800f076f  mov     rcx, [rbp+1F8h]; this
0x1800f0776  mov     r9d, ebx; char *
0x1800f0779  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800f0780  mov     edx, 0FEh; void *
0x1800f0785  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f078a  jmp     loc_1800F08DB
0x1800f078f  mov     [rsp+2F0h+hKey], r12
0x1800f0794  lea     rax, [rsp+2F0h+hKey]
0x1800f0799  mov     [rsp+2F0h+var_288], rax
0x1800f079e  mov     [rsp+2F0h+var_280], r12
0x1800f07a3  mov     [rsp+2F0h+var_278], 1
0x1800f07a8  lea     rax, [rsp+2F0h+var_280]
0x1800f07ad  mov     [rsp+2F0h+phkResult], rax; int
0x1800f07b2  mov     r9d, 20119h; samDesired
0x1800f07b8  xor     r8d, r8d; ulOptions
0x1800f07bb  mov     rdx, [rbp+1F0h+lpSubKey]; lpSubKey
0x1800f07bf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800f07c6  call    cs:__imp_RegOpenKeyExW
0x1800f07cc  mov     ebx, eax
0x1800f07ce  test    eax, eax
0x1800f07d0  jle     short loc_1800F07DB
0x1800f07d2  movzx   ebx, ax
0x1800f07d5  or      ebx, 80070000h
0x1800f07db  lea     rcx, [rsp+2F0h+var_288]
0x1800f07e0  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800f07e5  test    ebx, ebx
0x1800f07e7  jns     short loc_1800F0814
0x1800f07e9  mov     edx, 106h; void *
0x1800f07ee  mov     rcx, [rbp+1F8h]; this
0x1800f07f5  mov     r9d, ebx; char *
0x1800f07f8  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800f07ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0804  nop
0x1800f0805  lea     rcx, [rsp+2F0h+hKey]
0x1800f080a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f080f  jmp     loc_1800F08DB
0x1800f0814  test    rsi, rsi
0x1800f0817  jz      loc_1800F0909
0x1800f081d  lea     rcx, [rsp+2F0h+var_288]
0x1800f0822  call    ??$make_shared@VSCDScenarioInfo@@$$V@std@@YA?AV?$shared_ptr@VSCDScenarioInfo@@@0@XZ; std::make_shared<SCDScenarioInfo,>(void)
0x1800f0827  nop
0x1800f0828  mov     rdx, [rsp+2F0h+var_288]
0x1800f082d  test    rdx, rdx
0x1800f0830  jnz     short loc_1800F0864
0x1800f0832  mov     ebx, 8007000Eh
0x1800f0837  mov     r9d, ebx; char *
0x1800f083a  mov     edx, 10Bh; void *
0x1800f083f  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800f0846  mov     rcx, [rbp+1F8h]; this
0x1800f084d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0852  nop
0x1800f0853  mov     rcx, [rsp+2F0h+var_280]; this
0x1800f0858  test    rcx, rcx
0x1800f085b  jz      short loc_1800F0805
0x1800f085d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f0862  jmp     short loc_1800F0805
0x1800f0864  lea     rcx, [r13+8]
0x1800f0868  mov     rax, [rcx]
0x1800f086b  mov     [rsp+2F0h+phkResult], rdx
0x1800f0870  mov     r9, r14
0x1800f0873  mov     r8, rsi
0x1800f0876  mov     rdx, r15
0x1800f0879  mov     rax, [rax+10h]
0x1800f087d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0882  mov     ebx, eax
0x1800f0884  test    eax, eax
0x1800f0886  jns     short loc_1800F0892
0x1800f0888  mov     r9d, eax
0x1800f088b  mov     edx, 10Ch
0x1800f0890  jmp     short loc_1800F083F
0x1800f0892  mov     rcx, [rdi+8]
0x1800f0896  cmp     rcx, [rdi+10h]
0x1800f089a  jz      short loc_1800F08AD
0x1800f089c  lea     rdx, [rsp+2F0h+var_288]
0x1800f08a1  call    ??0?$shared_ptr@VSCDSetting@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(std::shared_ptr<SCDSetting> const &)
0x1800f08a6  add     qword ptr [rdi+8], 10h
0x1800f08ab  jmp     short loc_1800F08BE
0x1800f08ad  lea     r8, [rsp+2F0h+var_288]
0x1800f08b2  mov     rdx, rcx
0x1800f08b5  mov     rcx, rdi
0x1800f08b8  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VDCURI@@@std@@@?$vector@V?$shared_ptr@VDCURI@@@std@@V?$allocator@V?$shared_ptr@VDCURI@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VDCURI@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<DCURI>>::_Emplace_reallocate<std::shared_ptr<DCURI> const &>(std::shared_ptr<DCURI> * const,std::shared_ptr<DCURI> const &)
0x1800f08bd  nop
0x1800f08be  mov     rcx, [rsp+2F0h+var_280]; this
0x1800f08c3  test    rcx, rcx
0x1800f08c6  jz      short loc_1800F08CE
0x1800f08c8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f08cd  nop
0x1800f08ce  lea     rcx, [rsp+2F0h+hKey]
0x1800f08d3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f08d8  mov     ebx, r12d
0x1800f08db  lea     rcx, [rbp+1F0h+lpSubKey]
0x1800f08df  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800f08e4  mov     eax, ebx
0x1800f08e6  mov     rcx, [rbp+1F0h+var_50]
0x1800f08ed  xor     rcx, rsp; StackCookie
0x1800f08f0  call    __security_check_cookie
0x1800f08f5  add     rsp, 2B8h
0x1800f08fc  pop     r15
0x1800f08fe  pop     r14
0x1800f0900  pop     r13
0x1800f0902  pop     r12
0x1800f0904  pop     rdi
0x1800f0905  pop     rsi
0x1800f0906  pop     rbx
0x1800f0907  pop     rbp
0x1800f0908  retn
0x1800f0909  mov     [rbp+1F0h+cSubKeys], r12d
0x1800f090d  mov     [rsp+2F0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800f0912  mov     [rsp+2F0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800f0917  mov     [rsp+2F0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800f091c  mov     [rsp+2F0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1800f0921  mov     [rsp+2F0h+lpcValues], r12; lpcValues
0x1800f0926  mov     [rsp+2F0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800f092b  mov     [rsp+2F0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1800f0930  lea     rax, [rbp+1F0h+cSubKeys]
0x1800f0934  mov     [rsp+2F0h+phkResult], rax; lpcSubKeys
0x1800f0939  xor     r9d, r9d; lpReserved
0x1800f093c  xor     r8d, r8d; lpcchClass
0x1800f093f  xor     edx, edx; lpClass
0x1800f0941  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800f0946  call    cs:__imp_RegQueryInfoKeyW
0x1800f094c  mov     ebx, eax
0x1800f094e  test    eax, eax
0x1800f0950  jle     short loc_1800F095B
0x1800f0952  movzx   ebx, ax
0x1800f0955  or      ebx, 80070000h
0x1800f095b  test    ebx, ebx
0x1800f095d  jns     short loc_1800F0969
0x1800f095f  mov     edx, 113h
0x1800f0964  jmp     loc_1800F07EE
0x1800f0969  mov     esi, r12d
0x1800f096c  cmp     esi, [rbp+1F0h+cSubKeys]
0x1800f096f  jnb     loc_1800F08CE
0x1800f0975  mov     [rbp+1F0h+cchName], 104h
0x1800f097c  mov     [rsp+2F0h+lpcValues], r12; lpftLastWriteTime
0x1800f0981  mov     [rsp+2F0h+lpcbMaxClassLen], r12; lpcchClass
0x1800f0986  mov     [rsp+2F0h+lpcbMaxSubKeyLen], r12; lpClass
0x1800f098b  mov     [rsp+2F0h+phkResult], r12; int
0x1800f0990  lea     r9, [rbp+1F0h+cchName]; lpcchName
0x1800f0994  lea     r8, [rbp+1F0h+Name]; lpName
0x1800f0998  mov     edx, esi; dwIndex
0x1800f099a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800f099f  call    cs:__imp_RegEnumKeyExW
0x1800f09a5  mov     ebx, eax
0x1800f09a7  test    eax, eax
0x1800f09a9  jle     short loc_1800F09B4
0x1800f09ab  movzx   ebx, ax
0x1800f09ae  or      ebx, 80070000h
0x1800f09b4  test    ebx, ebx
0x1800f09b6  js      loc_1800F0A68
0x1800f09bc  lea     rcx, [rsp+2F0h+var_288]
0x1800f09c1  call    ??$make_shared@VSCDScenarioInfo@@$$V@std@@YA?AV?$shared_ptr@VSCDScenarioInfo@@@0@XZ; std::make_shared<SCDScenarioInfo,>(void)
0x1800f09c6  nop
0x1800f09c7  mov     rdx, [rsp+2F0h+var_288]
0x1800f09cc  test    rdx, rdx
0x1800f09cf  jz      short loc_1800F0A42
0x1800f09d1  lea     rcx, [r13+8]
0x1800f09d5  mov     rax, [rcx]
0x1800f09d8  mov     [rsp+2F0h+phkResult], rdx
0x1800f09dd  mov     r9, r14
0x1800f09e0  lea     r8, [rbp+1F0h+Name]
0x1800f09e4  mov     rdx, r15
0x1800f09e7  mov     rax, [rax+10h]
0x1800f09eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f09f0  mov     ebx, eax
0x1800f09f2  test    eax, eax
0x1800f09f4  js      short loc_1800F0A38
0x1800f09f6  mov     rcx, [rdi+8]
0x1800f09fa  cmp     rcx, [rdi+10h]
0x1800f09fe  jz      short loc_1800F0A11
0x1800f0a00  lea     rdx, [rsp+2F0h+var_288]
0x1800f0a05  call    ??0?$shared_ptr@VSCDSetting@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(std::shared_ptr<SCDSetting> const &)
0x1800f0a0a  add     qword ptr [rdi+8], 10h
0x1800f0a0f  jmp     short loc_1800F0A22
0x1800f0a11  lea     r8, [rsp+2F0h+var_288]
0x1800f0a16  mov     rdx, rcx
0x1800f0a19  mov     rcx, rdi
0x1800f0a1c  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VDCURI@@@std@@@?$vector@V?$shared_ptr@VDCURI@@@std@@V?$allocator@V?$shared_ptr@VDCURI@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VDCURI@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<DCURI>>::_Emplace_reallocate<std::shared_ptr<DCURI> const &>(std::shared_ptr<DCURI> * const,std::shared_ptr<DCURI> const &)
0x1800f0a21  nop
0x1800f0a22  mov     rcx, [rsp+2F0h+var_280]; this
0x1800f0a27  test    rcx, rcx
0x1800f0a2a  jz      short loc_1800F0A31
0x1800f0a2c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f0a31  inc     esi
0x1800f0a33  jmp     loc_1800F096C
0x1800f0a38  mov     r9d, eax
0x1800f0a3b  mov     edx, 123h
0x1800f0a40  jmp     short loc_1800F0A4F
0x1800f0a42  mov     ebx, 8007000Eh
0x1800f0a47  mov     r9d, ebx; char *
0x1800f0a4a  mov     edx, 122h; void *
0x1800f0a4f  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800f0a56  mov     rcx, [rbp+1F8h]; this
0x1800f0a5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0a62  nop
0x1800f0a63  jmp     loc_1800F0853
0x1800f0a68  mov     edx, 120h
0x1800f0a6d  jmp     loc_1800F07EE
```
