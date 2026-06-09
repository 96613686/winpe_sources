# RegKey::Create(ushort const *,ushort const *,ulong)

- ea: `0x18000e048`
- end: `0x18000e437`
- name: `?Create@RegKey@@QEAAXPEBG0K@Z`
- size: `1007`
- prototype: `void __fastcall(RegKey *this, const unsigned __int16 *, const unsigned __int16 *, REGSAM)`
- caller_count: `4`
- callee_count: `15`
- tags: `registry_config, service_task`

## callers

- `0x18000f6e0`
- `0x18001020c`
- `0x1800102c4`
- `0x180010514`

## callees

- `0x1800012e0`
- `0x1800012f0`
- `0x18000131c`
- `0x180001d9c`
- `0x180001e7c`
- `0x180002440`
- `0x180002a70`
- `0x180002fd0`
- `0x180004cfc`
- `0x18000a674`
- `0x18000def8`
- `0x18000e020`
- `0x18000e048`
- `0x18000edd8`
- `0x18000f0bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000e09f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000e0c0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000e09f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000e0c0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e124`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e1dc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e124`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e1dc`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000e169`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000e169`

## string_xrefs

- `0x18000e2b7`: `onecore\base\time\autotime\timeservice\regkey.cpp`
- `0x18000e2d3`: `onecore\base\time\autotime\timeservice\regkey.cpp`

## pseudocode

```c
void __fastcall RegKey::Create(RegKey *this, const unsigned __int16 *a2, const unsigned __int16 *a3, REGSAM a4)
{
  __int64 v8; // rax
  const unsigned __int16 *v9; // rdx
  unsigned int v10; // edi
  unsigned int v11; // r8d
  unsigned int PersistedRegistryLocationW; // edi
  unsigned int v13; // r8d
  unsigned int v14; // ebx
  unsigned int v15; // r8d
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  _QWORD *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned int v23; // eax
  _QWORD *v24; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  _QWORD *v27; // rax
  _QWORD *v28; // r8
  __int64 v29; // r9
  _QWORD *v30; // rax
  _QWORD *v31; // r8
  __int64 v32; // r9
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  unsigned int *dwOptionsb; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-E0h]
  unsigned int v37; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR *v38; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v39; // [rsp+60h] [rbp-A0h] BYREF
  RegKey *v40; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  char v42; // [rsp+78h] [rbp-88h]
  _QWORD v43[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  RegKey::Close(this);
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\regkey.cpp",
      (const char *)0x80004003LL,
      dwOptions);
  if ( (unsigned int)_o__wcsnicmp(a3, L"HKLM\\", 5) )
  {
    if ( (unsigned int)_o__wcsnicmp(a3, L"HKEY_LOCAL_MACHINE\\", 19) )
      goto LABEL_18;
    v8 = 19;
  }
  else
  {
    v8 = 5;
  }
  v9 = &a3[v8];
  if ( !&a3[v8] || !*v9 )
  {
LABEL_18:
    if ( (unsigned int)dword_18001C010 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 2) )
    {
      v19 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(v43, (__int64)a3);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v20,
        (__int64)qword_1800175A8,
        v21,
        v22,
        v19);
    }
    v23 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\regkey.cpp",
      (const char *)v23,
      dwOptions);
  }
  v40 = this;
  phkResult = 0;
  v42 = 1;
  v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0, 0, a4, 0, &phkResult, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v40);
  if ( v10 )
  {
    if ( (unsigned int)dword_18001C010 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 2) )
    {
      LODWORD(v38) = v10;
      v24 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v39, (__int64)a3);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)&v38,
        (__int64)word_18001750A,
        v25,
        v26,
        v24);
    }
    wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x59, v11, (const char *)v10, dwOptionsa);
  }
  if ( RegKey::IsStateSeparationEnabled() )
  {
    v37 = 0;
    dwOptionsb = &v37;
    PersistedRegistryLocationW = GetPersistedRegistryLocationW(a2, 0, SubKey, 520);
    if ( PersistedRegistryLocationW )
    {
      if ( (unsigned int)dword_18001C010 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 2) )
      {
        LODWORD(v38) = PersistedRegistryLocationW;
        _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v39, (__int64)a3);
        v27 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(v43, (__int64)a2);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (__int64)&v38,
          (__int64)&byte_1800171F7,
          (__int64)v28,
          v29,
          v27,
          v28);
      }
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x71,
        v13,
        (const char *)PersistedRegistryLocationW,
        (unsigned int)dwOptionsb);
    }
    v37 >>= 1;
    if ( 2 * (unsigned __int64)v37 >= 0x20A )
      _report_rangecheckfailure();
    v40 = (RegKey *)((char *)this + 8);
    SubKey[v37] = 0;
    phkResult = 0;
    v42 = 1;
    v14 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, a4, 0, &phkResult, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v40);
    if ( v14 )
    {
      if ( (unsigned int)dword_18001C010 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 2) )
      {
        LODWORD(v38) = v14;
        _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(v43, (__int64)SubKey);
        v30 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v39, (__int64)a2);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (__int64)&v38,
          (__int64)byte_1800175CB,
          (__int64)v31,
          v32,
          v30,
          v31);
      }
      wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x8D, v15, (const char *)v14, dwOptionsc);
    }
    if ( (unsigned int)dword_18001C010 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18001C010, PersistedRegistryLocationW + 2) )
      {
        v39 = a2;
        v38 = SubKey;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v16,
          (__int64)byte_180017283,
          v17,
          v18,
          &v39,
          &v38);
      }
    }
  }
}

```

## disassembly

```asm
0x18000e048  push    rbp
0x18000e04a  push    rbx
0x18000e04b  push    rsi
0x18000e04c  push    rdi
0x18000e04d  push    r12
0x18000e04f  push    r14
0x18000e051  push    r15
0x18000e053  lea     rbp, [rsp-1B0h]
0x18000e05b  sub     rsp, 2B0h
0x18000e062  mov     rax, cs:__security_cookie
0x18000e069  xor     rax, rsp
0x18000e06c  mov     [rbp+1E0h+var_40], rax
0x18000e073  mov     r15d, r9d
0x18000e076  mov     rbx, r8
0x18000e079  mov     rsi, rdx
0x18000e07c  mov     r14, rcx
0x18000e07f  call    ?Close@RegKey@@QEAAXXZ; RegKey::Close(void)
0x18000e084  xor     r12d, r12d
0x18000e087  test    rbx, rbx
0x18000e08a  jz      loc_18000E2CC
0x18000e090  lea     r8d, [r12+5]
0x18000e095  mov     rcx, rbx
0x18000e098  lea     rdx, aHklm; "HKLM\\"
0x18000e09f  call    cs:__imp__o__wcsnicmp
0x18000e0a5  test    eax, eax
0x18000e0a7  jnz     short loc_18000E0B0
0x18000e0a9  lea     eax, [r12+0Ah]
0x18000e0ae  jmp     short loc_18000E0D3
0x18000e0b0  mov     r8d, 13h
0x18000e0b6  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\"
0x18000e0bd  mov     rcx, rbx
0x18000e0c0  call    cs:__imp__o__wcsnicmp
0x18000e0c6  test    eax, eax
0x18000e0c8  jnz     loc_18000E269
0x18000e0ce  mov     eax, 26h ; '&'
0x18000e0d3  lea     rdx, [rbx+rax]; lpSubKey
0x18000e0d7  test    rdx, rdx
0x18000e0da  jz      loc_18000E269
0x18000e0e0  cmp     [rdx], r12w
0x18000e0e4  jz      loc_18000E269
0x18000e0ea  mov     [rsp+2E0h+lpdwDisposition], r12; lpdwDisposition
0x18000e0ef  lea     rax, [rsp+2E0h+var_270]
0x18000e0f4  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18000e0f9  xor     r9d, r9d; lpClass
0x18000e0fc  mov     [rsp+2E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18000e101  xor     r8d, r8d; Reserved
0x18000e104  mov     [rsp+2E0h+samDesired], r15d; samDesired
0x18000e109  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e110  mov     [rsp+2E0h+dwOptions], r12d; dwOptions
0x18000e115  mov     [rsp+2E0h+var_278], r14
0x18000e11a  mov     [rsp+2E0h+var_270], r12
0x18000e11f  mov     [rsp+2E0h+var_268], 1
0x18000e124  call    cs:__imp_RegCreateKeyExW
0x18000e12a  lea     rcx, [rsp+2E0h+var_278]
0x18000e12f  mov     edi, eax
0x18000e131  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18000e136  test    edi, edi
0x18000e138  jnz     loc_18000E2EB
0x18000e13e  call    ?IsStateSeparationEnabled@RegKey@@SA_NXZ; RegKey::IsStateSeparationEnabled(void)
0x18000e143  test    al, al
0x18000e145  jz      loc_18000E242
0x18000e14b  lea     rax, [rsp+2E0h+var_290]
0x18000e150  mov     [rsp+2E0h+var_290], r12d
0x18000e155  mov     r9d, 208h
0x18000e15b  mov     qword ptr [rsp+2E0h+dwOptions], rax
0x18000e160  lea     r8, [rbp+1E0h+SubKey]
0x18000e164  xor     edx, edx
0x18000e166  mov     rcx, rsi
0x18000e169  call    cs:__imp_GetPersistedRegistryLocationW
0x18000e16f  mov     edi, eax
0x18000e171  test    eax, eax
0x18000e173  jnz     loc_18000E34C
0x18000e179  mov     eax, [rsp+2E0h+var_290]
0x18000e17d  shr     eax, 1
0x18000e17f  mov     [rsp+2E0h+var_290], eax
0x18000e183  lea     rcx, [rax+rax]
0x18000e187  cmp     rcx, 20Ah
0x18000e18e  jnb     loc_18000E263
0x18000e194  mov     [rsp+2E0h+lpdwDisposition], r12; lpdwDisposition
0x18000e199  lea     rax, [r14+8]
0x18000e19d  mov     [rsp+2E0h+var_278], rax
0x18000e1a2  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x18000e1a6  lea     rax, [rsp+2E0h+var_270]
0x18000e1ab  mov     [rbp+rcx+1E0h+SubKey], r12w
0x18000e1b1  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18000e1b6  xor     r9d, r9d; lpClass
0x18000e1b9  mov     [rsp+2E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18000e1be  xor     r8d, r8d; Reserved
0x18000e1c1  mov     [rsp+2E0h+samDesired], r15d; samDesired
0x18000e1c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e1cd  mov     [rsp+2E0h+dwOptions], r12d; dwOptions
0x18000e1d2  mov     [rsp+2E0h+var_270], r12
0x18000e1d7  mov     [rsp+2E0h+var_268], 1
0x18000e1dc  call    cs:__imp_RegCreateKeyExW
0x18000e1e2  lea     rcx, [rsp+2E0h+var_278]
0x18000e1e7  mov     ebx, eax
0x18000e1e9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18000e1ee  test    ebx, ebx
0x18000e1f0  jnz     loc_18000E3C1
0x18000e1f6  mov     eax, cs:dword_18001C010
0x18000e1fc  cmp     eax, 5
0x18000e1ff  jbe     short loc_18000E242
0x18000e201  lea     edx, [rdi+2]
0x18000e204  lea     rcx, dword_18001C010
0x18000e20b  call    _tlgKeywordOn
0x18000e210  test    al, al
0x18000e212  jz      short loc_18000E242
0x18000e214  lea     rax, [rbp+1E0h+SubKey]
0x18000e218  mov     [rsp+2E0h+var_280], rsi
0x18000e21d  mov     [rsp+2E0h+var_288], rax
0x18000e222  lea     rdx, byte_180017283
0x18000e229  lea     rax, [rsp+2E0h+var_288]
0x18000e22e  mov     qword ptr [rsp+2E0h+samDesired], rax
0x18000e233  lea     rax, [rsp+2E0h+var_280]
0x18000e238  mov     qword ptr [rsp+2E0h+dwOptions], rax
0x18000e23d  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000e242  mov     rcx, [rbp+1E0h+var_40]
0x18000e249  xor     rcx, rsp; StackCookie
0x18000e24c  call    __security_check_cookie
0x18000e251  add     rsp, 2B0h
0x18000e258  pop     r15
0x18000e25a  pop     r14
0x18000e25c  pop     r12
0x18000e25e  pop     rdi
0x18000e25f  pop     rsi
0x18000e260  pop     rbx
0x18000e261  pop     rbp
0x18000e262  retn
0x18000e263  call    __report_rangecheckfailure
0x18000e269  mov     eax, cs:dword_18001C010
0x18000e26f  cmp     eax, 2
0x18000e272  jbe     short loc_18000E2A6
0x18000e274  mov     edx, 2
0x18000e279  lea     rcx, dword_18001C010
0x18000e280  call    _tlgKeywordOn
0x18000e285  test    al, al
0x18000e287  jz      short loc_18000E2A6
0x18000e289  mov     rdx, rbx
0x18000e28c  lea     rcx, [rbp+1E0h+var_260]
0x18000e290  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000e295  lea     rdx, qword_1800175A8
0x18000e29c  mov     qword ptr [rsp+2E0h+dwOptions], rax; int
0x18000e2a1  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000e2a6  mov     ecx, 80070057h
0x18000e2ab  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000e2b0  mov     rcx, [rbp+1E8h]; this
0x18000e2b7  lea     r8, aOnecoreBaseTim_5; "onecore\\base\\time\\autotime\\timeserv"...
0x18000e2be  mov     r9d, eax; char *
0x18000e2c1  mov     edx, 42h ; 'B'; void *
0x18000e2c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e2cc  mov     rcx, [rbp+1E8h]; this
0x18000e2d3  lea     r8, aOnecoreBaseTim_5; "onecore\\base\\time\\autotime\\timeserv"...
0x18000e2da  mov     r9d, 80004003h; char *
0x18000e2e0  mov     edx, 2Bh ; '+'; void *
0x18000e2e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e2eb  mov     ecx, cs:dword_18001C010
0x18000e2f1  cmp     ecx, 2
0x18000e2f4  jbe     short loc_18000E337
0x18000e2f6  mov     edx, 2
0x18000e2fb  lea     rcx, dword_18001C010
0x18000e302  call    _tlgKeywordOn
0x18000e307  test    al, al
0x18000e309  jz      short loc_18000E337
0x18000e30b  mov     rdx, rbx
0x18000e30e  mov     dword ptr [rsp+2E0h+var_288], edi
0x18000e312  lea     rcx, [rsp+2E0h+var_280]
0x18000e317  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000e31c  lea     rcx, [rsp+2E0h+var_288]
0x18000e321  mov     qword ptr [rsp+2E0h+samDesired], rcx
0x18000e326  lea     rdx, word_18001750A
0x18000e32d  mov     qword ptr [rsp+2E0h+dwOptions], rax; unsigned int
0x18000e332  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e337  mov     rcx, [rbp+1E8h]; this
0x18000e33e  mov     r9d, edi; char *
0x18000e341  mov     edx, 59h ; 'Y'; void *
0x18000e346  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000e34c  mov     ecx, cs:dword_18001C010
0x18000e352  cmp     ecx, 2
0x18000e355  jbe     short loc_18000E3AC
0x18000e357  mov     edx, 2
0x18000e35c  lea     rcx, dword_18001C010
0x18000e363  call    _tlgKeywordOn
0x18000e368  test    al, al
0x18000e36a  jz      short loc_18000E3AC
0x18000e36c  mov     rdx, rbx
0x18000e36f  mov     dword ptr [rsp+2E0h+var_288], edi
0x18000e373  lea     rcx, [rsp+2E0h+var_280]
0x18000e378  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000e37d  mov     rdx, rsi
0x18000e380  lea     rcx, [rbp+1E0h+var_260]
0x18000e384  mov     r8, rax
0x18000e387  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000e38c  lea     rcx, [rsp+2E0h+var_288]
0x18000e391  mov     [rsp+2E0h+lpSecurityAttributes], rcx
0x18000e396  lea     rdx, byte_1800171F7
0x18000e39d  mov     qword ptr [rsp+2E0h+samDesired], r8
0x18000e3a2  mov     qword ptr [rsp+2E0h+dwOptions], rax; unsigned int
0x18000e3a7  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e3ac  mov     rcx, [rbp+1E8h]; this
0x18000e3b3  mov     r9d, edi; char *
0x18000e3b6  mov     edx, 71h ; 'q'; void *
0x18000e3bb  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000e3c1  mov     ecx, cs:dword_18001C010
0x18000e3c7  cmp     ecx, 2
0x18000e3ca  jbe     short loc_18000E422
0x18000e3cc  mov     edx, 2
0x18000e3d1  lea     rcx, dword_18001C010
0x18000e3d8  call    _tlgKeywordOn
0x18000e3dd  test    al, al
0x18000e3df  jz      short loc_18000E422
0x18000e3e1  lea     rdx, [rbp+1E0h+SubKey]
0x18000e3e5  mov     dword ptr [rsp+2E0h+var_288], ebx
0x18000e3e9  lea     rcx, [rbp+1E0h+var_260]
0x18000e3ed  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000e3f2  mov     rdx, rsi
0x18000e3f5  lea     rcx, [rsp+2E0h+var_280]
0x18000e3fa  mov     r8, rax
0x18000e3fd  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000e402  lea     rcx, [rsp+2E0h+var_288]
0x18000e407  mov     [rsp+2E0h+lpSecurityAttributes], rcx
0x18000e40c  lea     rdx, byte_1800175CB
0x18000e413  mov     qword ptr [rsp+2E0h+samDesired], r8
0x18000e418  mov     qword ptr [rsp+2E0h+dwOptions], rax; unsigned int
0x18000e41d  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e422  mov     rcx, [rbp+1E8h]; this
0x18000e429  mov     r9d, ebx; char *
0x18000e42c  mov     edx, 8Dh; void *
0x18000e431  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
