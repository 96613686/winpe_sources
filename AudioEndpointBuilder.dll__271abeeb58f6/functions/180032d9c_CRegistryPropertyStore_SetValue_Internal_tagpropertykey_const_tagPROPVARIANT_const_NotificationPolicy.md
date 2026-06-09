# CRegistryPropertyStore::SetValue_Internal(_tagpropertykey const &,tagPROPVARIANT const &,NotificationPolicy)

- ea: `0x180032d9c`
- end: `0x180033223`
- name: `?SetValue_Internal@CRegistryPropertyStore@@IEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@W4NotificationPolicy@@@Z`
- size: `1159`
- prototype: `__int64 __fastcall(__int64, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800639a0`

## callees

- `0x180010da8`
- `0x18001deb0`
- `0x18001f230`
- `0x180022de4`
- `0x180026500`
- `0x180026fcc`
- `0x180032d9c`
- `0x180033464`
- `0x180033844`
- `0x18003e920`
- `0x18003ee30`
- `0x18003f780`
- `0x180062618`
- `0x18006262c`
- `0x18006322c`
- `0x1800633a4`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180032ea0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180032ea0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032f93`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800331bc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032f93`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800331bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033177`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800331f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033177`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800331f4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032fe2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032fe2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033142`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033142`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032f67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032f67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033011`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033027`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033071`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033011`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033027`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033071`

## string_xrefs

- `0x180032e32`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180032e65`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180032f47`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180032ff6`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x1800330c9`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180033151`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CRegistryPropertyStore::SetValue_Internal(
        __int64 a1,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3)
{
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // r8
  unsigned int v9; // edi
  unsigned int v10; // ebx
  __int64 v11; // rdx
  unsigned __int64 v12; // r9
  int v13; // eax
  LSTATUS v14; // eax
  char v15; // r14
  void *pvData; // rdi
  LSTATUS ValueW; // eax
  BYTE *v18; // rbx
  DWORD v19; // r14d
  unsigned int v20; // eax
  void *v21; // rcx
  bool v22; // zf
  int v24; // eax
  unsigned __int64 v25; // r11
  __int64 v26; // rax
  unsigned int v27; // eax
  __int64 v28; // rdx
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  _BYTE v31[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *Buf2; // [rsp+48h] [rbp-B8h] BYREF
  DWORD dwFlags; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+54h] [rbp-ACh] BYREF
  SIZE_T cb; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v36[16]; // [rsp+60h] [rbp-A0h] BYREF
  void **p_Buf2; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 *v38; // [rsp+78h] [rbp-88h] BYREF
  char v39; // [rsp+80h] [rbp-80h]
  _BYTE v40[16]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v41; // [rsp+98h] [rbp-68h]
  WCHAR ValueName[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  ATL::CCritSecLock::CCritSecLock((ATL::CCritSecLock *)v40, (struct _RTL_CRITICAL_SECTION *)(a1 + 16), (bool)a3);
  v6 = lambda_fddb834c1d6a90001df23262bd46f9fd_::_lambda_fddb834c1d6a90001df23262bd46f9fd_(&cb, a2);
  wil::scope_exit__lambda_fddb834c1d6a90001df23262bd46f9fd___(v36, v6);
  v31[0] = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a1 + 80LL))(a1, v31);
  v9 = v7;
  if ( v7 < 0 )
  {
    v10 = -2147024891;
    if ( v7 != -2147024891 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4CE,
        (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
        (const char *)(unsigned int)v7,
        pdwType);
      v10 = v9;
    }
    goto LABEL_31;
  }
  if ( !v31[0] )
  {
    v10 = -2147024894;
    v11 = 1231;
LABEL_6:
    v12 = v10;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
      (const char *)v12,
      pdwType);
LABEL_31:
    wil::details::lambda_call__lambda_4d1baa61d6f633b017518b24c4c6110b___::_lambda_call__lambda_4d1baa61d6f633b017518b24c4c6110b___(v36);
    ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v40);
    return v10;
  }
  v13 = KeyRep(a2, ValueName, v8);
  v10 = v13;
  if ( v13 < 0 )
  {
    v12 = (unsigned int)v13;
    v11 = 1235;
    goto LABEL_7;
  }
  if ( a3->vt )
  {
    dwFlags = 0;
    Buf2 = 0;
    cb = 0;
    v41 = 0;
    pcbData = 0;
    p_Buf2 = &Buf2;
    v38 = 0;
    v39 = 1;
    v10 = SerializePropVariant(a3, &dwFlags, (LARGE_INTEGER **)&v38, &cb);
    wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_Buf2);
    if ( (v10 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E8,
        (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
        (const char *)v10,
        pdwType);
LABEL_29:
      v21 = Buf2;
      v22 = Buf2 == 0;
      Buf2 = 0;
      if ( !v22 )
        CoTaskMemFree(v21);
      goto LABEL_31;
    }
    pcbData = cb;
    pvData = CoTaskMemAlloc(cb);
    ValueW = RegGetValueW(*(HKEY *)(a1 + 8), 0, ValueName, dwFlags, 0, pvData, &pcbData);
    v18 = (BYTE *)Buf2;
    v19 = cb;
    if ( !ValueW && pcbData == cb && !memcmp_0(pvData, Buf2, pcbData) )
    {
      v15 = 1;
    }
    else
    {
      v20 = RegSetValueExW(*(HKEY *)(a1 + 8), ValueName, 0, dwFlags, v18, v19);
      if ( v20 )
      {
        v10 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x4F5,
                (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
                (const char *)v20,
                pdwType);
        if ( pvData )
          CoTaskMemFree(pvData);
        goto LABEL_29;
      }
      v15 = 0;
      v18 = (BYTE *)Buf2;
    }
    if ( pvData )
    {
      CoTaskMemFree(pvData);
      v18 = (BYTE *)Buf2;
    }
    Buf2 = 0;
    if ( v18 )
      CoTaskMemFree(v18);
    goto LABEL_38;
  }
  v14 = RegDeleteValueW(*(HKEY *)(a1 + 8), ValueName);
  v10 = v14;
  if ( v14 )
  {
    if ( v14 != 2 && v14 != 1018 )
    {
      if ( v14 > 0 )
        v10 = (unsigned __int16)v14 | 0x80070000;
      if ( (v10 & 0x80000000) == 0 )
        goto LABEL_31;
      v11 = 1242;
      goto LABEL_6;
    }
    v15 = 1;
  }
  else
  {
    v15 = 0;
  }
LABEL_38:
  v36[8] = 0;
  wil::details::lambda_call__lambda_4d1baa61d6f633b017518b24c4c6110b___::_lambda_call__lambda_4d1baa61d6f633b017518b24c4c6110b___(v36);
  ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v40);
  if ( *(_QWORD *)(a1 + 64) && !v15 )
  {
    v24 = StringCbCopyW(ValueName, 0x208u, (const unsigned __int16 *)(a1 + 72));
    v10 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x501,
        (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
        (const char *)(unsigned int)v24,
        pdwType);
      return v10;
    }
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)(a1 + 2 * v26 + 72) );
    while ( ValueName[v26] != 92 && v26 )
      --v26;
    if ( 2 * v26 >= v25 )
      _report_rangecheckfailure();
    ValueName[v26] = 0;
    Buf2 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &Buf2,
      0);
    v27 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, ValueName, 0, 0x20119u, (PHKEY)&Buf2);
    if ( v27 )
    {
      v28 = 1299;
      goto LABEL_51;
    }
    dwFlags = 0;
    pcbData = 4;
    v27 = RegGetValueW((HKEY)Buf2, 0, L"DeviceState", 0x10u, 0, &dwFlags, &pcbData);
    if ( v27 )
    {
      v28 = 1304;
LABEL_51:
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v28,
              (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
              (const char *)v27,
              pdwTypea);
      if ( Buf2 )
        RegCloseKey((HKEY)Buf2);
      return v10;
    }
    if ( (dwFlags & 0x40000000) == 0 )
      (*(void (__fastcall **)(__int64, const struct _tagpropertykey *))(*(_QWORD *)a1 + 88LL))(a1, a2);
    if ( Buf2 )
      RegCloseKey((HKEY)Buf2);
  }
  return 0;
}

```

## disassembly

```asm
0x180032d9c  push    rbp
0x180032d9e  push    rbx
0x180032d9f  push    rsi
0x180032da0  push    rdi
0x180032da1  push    r12
0x180032da3  push    r14
0x180032da5  push    r15
0x180032da7  lea     rbp, [rsp-1C0h]
0x180032daf  sub     rsp, 2C0h
0x180032db6  mov     rax, cs:__security_cookie
0x180032dbd  xor     rax, rsp
0x180032dc0  mov     [rbp+1F0h+var_40], rax
0x180032dc7  mov     r14, r8
0x180032dca  mov     r15, rdx
0x180032dcd  mov     rsi, rcx
0x180032dd0  lea     rdx, [rcx+10h]; struct _RTL_CRITICAL_SECTION *
0x180032dd4  lea     rcx, [rbp+1F0h+var_268]; this
0x180032dd8  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x180032ddd  nop
0x180032dde  mov     rdx, r15
0x180032de1  lea     rcx, [rsp+2F0h+cb]
0x180032de6  call    _lambda_fddb834c1d6a90001df23262bd46f9fd____lambda_fddb834c1d6a90001df23262bd46f9fd_
0x180032deb  mov     rdx, rax
0x180032dee  lea     rcx, [rsp+2F0h+var_290]
0x180032df3  call    wil__scope_exit__lambda_fddb834c1d6a90001df23262bd46f9fd___
0x180032df8  nop
0x180032df9  xor     r12d, r12d
0x180032dfc  mov     [rsp+2F0h+var_2B0], r12b
0x180032e01  mov     rax, [rsi]
0x180032e04  lea     rdx, [rsp+2F0h+var_2B0]
0x180032e09  mov     rcx, rsi
0x180032e0c  mov     rax, [rax+50h]
0x180032e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e15  mov     edi, eax
0x180032e17  test    eax, eax
0x180032e19  jns     short loc_180032E4A
0x180032e1b  mov     ebx, 80070005h
0x180032e20  cmp     eax, ebx
0x180032e22  jz      loc_18003302E
0x180032e28  mov     rcx, [rbp+1F8h]; this
0x180032e2f  mov     r9d, eax; char *
0x180032e32  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180032e39  mov     edx, 4CEh; void *
0x180032e3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032e43  mov     ebx, edi
0x180032e45  jmp     loc_18003302E
0x180032e4a  cmp     [rsp+2F0h+var_2B0], r12b
0x180032e4f  jnz     short loc_180032E76
0x180032e51  mov     ebx, 80070002h
0x180032e56  mov     edx, 4CFh; void *
0x180032e5b  mov     r9d, ebx; char *
0x180032e5e  mov     rcx, [rbp+1F8h]; this
0x180032e65  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180032e6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032e71  jmp     loc_18003302E
0x180032e76  lea     rdx, [rbp+1F0h+ValueName]; unsigned __int16 *
0x180032e7a  mov     rcx, r15; struct _tagpropertykey *
0x180032e7d  call    ?KeyRep@@YAJAEBU_tagpropertykey@@PEAG_K@Z; KeyRep(_tagpropertykey const &,ushort *,unsigned __int64)
0x180032e82  mov     ebx, eax
0x180032e84  test    eax, eax
0x180032e86  jns     short loc_180032E92
0x180032e88  mov     r9d, eax
0x180032e8b  mov     edx, 4D3h
0x180032e90  jmp     short loc_180032E5E
0x180032e92  cmp     [r14], r12w
0x180032e96  jnz     short loc_180032EEB
0x180032e98  lea     rdx, [rbp+1F0h+ValueName]; lpValueName
0x180032e9c  mov     rcx, [rsi+8]; hKey
0x180032ea0  call    cs:__imp_RegDeleteValueW
0x180032ea6  mov     ebx, eax
0x180032ea8  test    eax, eax
0x180032eaa  jz      short loc_180032ED4
0x180032eac  cmp     eax, 2
0x180032eaf  jz      short loc_180032EE3
0x180032eb1  cmp     eax, 3FAh
0x180032eb6  jz      short loc_180032EE3
0x180032eb8  test    eax, eax
0x180032eba  jle     short loc_180032EC5
0x180032ebc  movzx   ebx, ax
0x180032ebf  or      ebx, 80070000h
0x180032ec5  test    ebx, ebx
0x180032ec7  jns     loc_18003302E
0x180032ecd  mov     edx, 4DAh
0x180032ed2  jmp     short loc_180032E5B
0x180032ed4  cmp     eax, 3FAh
0x180032ed9  jz      short loc_180032EE3
0x180032edb  mov     r14b, r12b
0x180032ede  jmp     loc_180033077
0x180032ee3  mov     r14b, 1
0x180032ee6  jmp     loc_180033077
0x180032eeb  mov     [rsp+2F0h+dwFlags], r12d
0x180032ef0  mov     [rsp+2F0h+Buf2], r12
0x180032ef5  mov     [rsp+2F0h+cb], r12
0x180032efa  mov     [rbp+1F0h+var_258], r12
0x180032efe  mov     [rsp+2F0h+var_29C], r12d
0x180032f03  lea     rax, [rsp+2F0h+Buf2]
0x180032f08  mov     [rsp+2F0h+var_280], rax
0x180032f0d  mov     [rsp+2F0h+var_278], r12
0x180032f12  mov     [rbp+1F0h+var_270], 1
0x180032f16  lea     r9, [rsp+2F0h+cb]; unsigned __int64 *
0x180032f1b  lea     r8, [rsp+2F0h+var_278]; unsigned __int8 **
0x180032f20  lea     rdx, [rsp+2F0h+dwFlags]; unsigned int *
0x180032f25  mov     rcx, r14; struct tagPROPVARIANT *
0x180032f28  call    ?SerializePropVariant@@YAJPEBUtagPROPVARIANT@@PEAKPEAPEAEPEA_K@Z; SerializePropVariant(tagPROPVARIANT const *,ulong *,uchar * *,unsigned __int64 *)
0x180032f2d  mov     ebx, eax
0x180032f2f  lea     rcx, [rsp+2F0h+var_280]
0x180032f34  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180032f39  test    ebx, ebx
0x180032f3b  jns     short loc_180032F5E
0x180032f3d  mov     rcx, [rbp+1F8h]; this
0x180032f44  mov     r9d, ebx; char *
0x180032f47  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180032f4e  mov     edx, 4E8h; void *
0x180032f53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032f58  nop
0x180032f59  jmp     loc_180033018
0x180032f5e  mov     rcx, [rsp+2F0h+cb]; cb
0x180032f63  mov     [rsp+2F0h+var_29C], ecx
0x180032f67  call    cs:__imp_CoTaskMemAlloc
0x180032f6d  mov     rdi, rax
0x180032f70  lea     rax, [rsp+2F0h+var_29C]
0x180032f75  mov     [rsp+2F0h+pcbData], rax; pcbData
0x180032f7a  mov     [rsp+2F0h+pvData], rdi; pvData
0x180032f7f  mov     [rsp+2F0h+pdwType], r12; pdwType
0x180032f84  mov     r9d, [rsp+2F0h+dwFlags]; dwFlags
0x180032f89  lea     r8, [rbp+1F0h+ValueName]; lpValue
0x180032f8d  xor     edx, edx; lpSubKey
0x180032f8f  mov     rcx, [rsi+8]; hkey
0x180032f93  call    cs:__imp_RegGetValueW
0x180032f99  mov     rbx, [rsp+2F0h+Buf2]
0x180032f9e  mov     r14, [rsp+2F0h+cb]
0x180032fa3  test    eax, eax
0x180032fa5  jnz     short loc_180032FC8
0x180032fa7  mov     r8d, [rsp+2F0h+var_29C]; Size
0x180032fac  cmp     r8, r14
0x180032faf  jnz     short loc_180032FC8
0x180032fb1  mov     rdx, rbx; Buf2
0x180032fb4  mov     rcx, rdi; Buf1
0x180032fb7  call    memcmp_0
0x180032fbc  test    eax, eax
0x180032fbe  jnz     short loc_180032FC8
0x180032fc0  mov     r14b, 1
0x180032fc3  jmp     loc_180033051
0x180032fc8  mov     dword ptr [rsp+2F0h+pvData], r14d; cbData
0x180032fcd  mov     [rsp+2F0h+pdwType], rbx; int
0x180032fd2  mov     r9d, [rsp+2F0h+dwFlags]; dwType
0x180032fd7  xor     r8d, r8d; Reserved
0x180032fda  lea     rdx, [rbp+1F0h+ValueName]; lpValueName
0x180032fde  mov     rcx, [rsi+8]; hKey
0x180032fe2  call    cs:__imp_RegSetValueExW
0x180032fe8  test    eax, eax
0x180032fea  jz      short loc_180033049
0x180032fec  mov     rcx, [rbp+1F8h]; this
0x180032ff3  mov     r9d, eax; char *
0x180032ff6  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180032ffd  mov     edx, 4F5h; void *
0x180033002  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033007  mov     ebx, eax
0x180033009  test    rdi, rdi
0x18003300c  jz      short loc_180033018
0x18003300e  mov     rcx, rdi; pv
0x180033011  call    cs:__imp_CoTaskMemFree
0x180033017  nop
0x180033018  mov     rcx, [rsp+2F0h+Buf2]; pv
0x18003301d  test    rcx, rcx
0x180033020  mov     [rsp+2F0h+Buf2], r12
0x180033025  jz      short loc_18003302E
0x180033027  call    cs:__imp_CoTaskMemFree
0x18003302d  nop
0x18003302e  lea     rcx, [rsp+2F0h+var_290]
0x180033033  call    wil__details__lambda_call__lambda_4d1baa61d6f633b017518b24c4c6110b______lambda_call__lambda_4d1baa61d6f633b017518b24c4c6110b___
0x180033038  nop
0x180033039  lea     rcx, [rbp+1F0h+var_268]; this
0x18003303d  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x180033042  mov     eax, ebx
0x180033044  jmp     loc_1800331FC
0x180033049  mov     r14b, r12b
0x18003304c  mov     rbx, [rsp+2F0h+Buf2]
0x180033051  test    rdi, rdi
0x180033054  jz      short loc_180033064
0x180033056  mov     rcx, rdi; pv
0x180033059  call    cs:__imp_CoTaskMemFree
0x18003305f  mov     rbx, [rsp+2F0h+Buf2]
0x180033064  mov     [rsp+2F0h+Buf2], r12
0x180033069  test    rbx, rbx
0x18003306c  jz      short loc_180033077
0x18003306e  mov     rcx, rbx; pv
0x180033071  call    cs:__imp_CoTaskMemFree
0x180033077  mov     [rsp+2F0h+var_288], r12b
0x18003307c  lea     rcx, [rsp+2F0h+var_290]
0x180033081  call    wil__details__lambda_call__lambda_4d1baa61d6f633b017518b24c4c6110b______lambda_call__lambda_4d1baa61d6f633b017518b24c4c6110b___
0x180033086  nop
0x180033087  lea     rcx, [rbp+1F0h+var_268]; this
0x18003308b  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x180033090  cmp     [rsi+40h], r12
0x180033094  jz      loc_1800331FA
0x18003309a  test    r14b, r14b
0x18003309d  jnz     loc_1800331FA
0x1800330a3  lea     r8, [rsi+48h]; unsigned __int16 *
0x1800330a7  mov     r11d, 208h
0x1800330ad  mov     edx, r11d; unsigned __int64
0x1800330b0  lea     rcx, [rbp+1F0h+ValueName]; unsigned __int16 *
0x1800330b4  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800330b9  mov     ebx, eax
0x1800330bb  test    eax, eax
0x1800330bd  jns     short loc_1800330DF
0x1800330bf  mov     rcx, [rbp+1F8h]; this
0x1800330c6  mov     r9d, eax; char *
0x1800330c9  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x1800330d0  mov     edx, 501h; void *
0x1800330d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800330da  jmp     loc_180033042
0x1800330df  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800330e3  inc     rax
0x1800330e6  cmp     [rsi+rax*2+48h], r12w
0x1800330ec  jnz     short loc_1800330E3
0x1800330ee  jmp     short loc_1800330F8
0x1800330f0  test    rax, rax
0x1800330f3  jz      short loc_180033100
0x1800330f5  dec     rax
0x1800330f8  cmp     [rbp+rax*2+1F0h+ValueName], 5Ch ; '\'
0x1800330fe  jnz     short loc_1800330F0
0x180033100  lea     rcx, [rax+rax]
0x180033104  cmp     rcx, r11
0x180033107  jnb     loc_18003321D
0x18003310d  mov     [rbp+rcx+1F0h+ValueName], r12w
0x180033113  mov     [rsp+2F0h+Buf2], r12
0x180033118  xor     edx, edx
0x18003311a  lea     rcx, [rsp+2F0h+Buf2]
0x18003311f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180033124  lea     rax, [rsp+2F0h+Buf2]
0x180033129  mov     [rsp+2F0h+pdwType], rax; unsigned int
0x18003312e  mov     r9d, 20119h; samDesired
0x180033134  xor     r8d, r8d; ulOptions
0x180033137  lea     rdx, [rbp+1F0h+ValueName]; lpSubKey
0x18003313b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033142  call    cs:__imp_RegOpenKeyExW
0x180033148  test    eax, eax
0x18003314a  jz      short loc_180033182
0x18003314c  mov     edx, 513h; void *
0x180033151  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180033158  mov     r9d, eax; char *
0x18003315b  mov     rcx, [rbp+1F8h]; this
0x180033162  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033167  mov     ebx, eax
0x180033169  mov     rcx, [rsp+2F0h+Buf2]; hKey
0x18003316e  test    rcx, rcx
0x180033171  jz      loc_180033042
0x180033177  call    cs:__imp_RegCloseKey
0x18003317d  jmp     loc_180033042
0x180033182  mov     [rsp+2F0h+dwFlags], r12d
0x180033187  mov     [rsp+2F0h+var_29C], 4
0x18003318f  lea     rax, [rsp+2F0h+var_29C]
0x180033194  mov     [rsp+2F0h+pcbData], rax; pcbData
0x180033199  lea     rax, [rsp+2F0h+dwFlags]
0x18003319e  mov     [rsp+2F0h+pvData], rax; pvData
0x1800331a3  mov     [rsp+2F0h+pdwType], r12; pdwType
0x1800331a8  mov     r9d, 10h; dwFlags
0x1800331ae  lea     r8, aDevicestate; "DeviceState"
0x1800331b5  xor     edx, edx; lpSubKey
0x1800331b7  mov     rcx, [rsp+2F0h+Buf2]; hkey
0x1800331bc  call    cs:__imp_RegGetValueW
0x1800331c2  test    eax, eax
0x1800331c4  jz      short loc_1800331CD
0x1800331c6  mov     edx, 518h
0x1800331cb  jmp     short loc_180033151
0x1800331cd  test    [rsp+2F0h+dwFlags], 40000000h
0x1800331d5  jnz     short loc_1800331EA
0x1800331d7  mov     rax, [rsi]
0x1800331da  mov     rdx, r15
0x1800331dd  mov     rcx, rsi
0x1800331e0  mov     rax, [rax+58h]
0x1800331e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331e9  nop
0x1800331ea  mov     rcx, [rsp+2F0h+Buf2]; hKey
0x1800331ef  test    rcx, rcx
0x1800331f2  jz      short loc_1800331FA
0x1800331f4  call    cs:__imp_RegCloseKey
0x1800331fa  xor     eax, eax
0x1800331fc  mov     rcx, [rbp+1F0h+var_40]
0x180033203  xor     rcx, rsp; StackCookie
0x180033206  call    __security_check_cookie
0x18003320b  add     rsp, 2C0h
0x180033212  pop     r15
0x180033214  pop     r14
0x180033216  pop     r12
0x180033218  pop     rdi
0x180033219  pop     rsi
0x18003321a  pop     rbx
0x18003321b  pop     rbp
0x18003321c  retn
0x18003321d  call    __report_rangecheckfailure
```
