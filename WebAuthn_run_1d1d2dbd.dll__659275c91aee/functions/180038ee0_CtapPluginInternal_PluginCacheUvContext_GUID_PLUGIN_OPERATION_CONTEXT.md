# CtapPluginInternal::PluginCacheUvContext(_GUID,_PLUGIN_OPERATION_CONTEXT)

- ea: `0x180038ee0`
- end: `0x18003928c`
- name: `?PluginCacheUvContext@CtapPluginInternal@@YAJU_GUID@@U_PLUGIN_OPERATION_CONTEXT@@@Z`
- size: `940`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a76f8`

## callees

- `0x180017a88`
- `0x1800205e4`
- `0x180021878`
- `0x180023bc8`
- `0x1800288c8`
- `0x180036da4`
- `0x180037f6c`
- `0x180038ee0`
- `0x180039980`
- `0x180043a18`
- `0x180043ab4`
- `0x18004d8f4`
- `0x18005378c`
- `0x1800537a4`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039099`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039099`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180038f22`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800390cd`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180038f22`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800390cd`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180039123`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180039123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039251`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039251`

## string_xrefs

- `0x180038f39`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800390e4`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180039138`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CtapPluginInternal::PluginCacheUvContext(const IID *a1, __int64 a2)
{
  HRESULT v4; // eax
  unsigned int v5; // edi
  __int64 *v7; // rax
  __int64 v8; // rcx
  __int64 *v9; // rax
  __int64 v10; // rcx
  __int64 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  void **v17; // rax
  void *v18; // rcx
  void **unique; // rax
  void *v20; // rcx
  HLOCAL v21; // rax
  HRESULT v22; // eax
  unsigned int v23; // ebx
  HRESULT v24; // eax
  __int64 v25; // rax
  LPOLESTR lpsz; // [rsp+20h] [rbp-138h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-130h] BYREF
  char v28; // [rsp+30h] [rbp-128h]
  LPOLESTR v29; // [rsp+38h] [rbp-120h] BYREF
  __int128 v30; // [rsp+40h] [rbp-118h] BYREF
  __int128 v31; // [rsp+50h] [rbp-108h]
  __int128 v32; // [rsp+60h] [rbp-F8h]
  void *v33[2]; // [rsp+70h] [rbp-E8h]
  GUID pclsid; // [rsp+80h] [rbp-D8h] BYREF
  __int64 v35; // [rsp+90h] [rbp-C8h]
  _BYTE v36[32]; // [rsp+A0h] [rbp-B8h] BYREF
  __int128 v37; // [rsp+C0h] [rbp-98h]
  __int128 v38; // [rsp+D0h] [rbp-88h]
  __int128 v39; // [rsp+E0h] [rbp-78h]
  __int128 v40; // [rsp+F0h] [rbp-68h]
  GUID v41; // [rsp+100h] [rbp-58h]
  __int64 v42; // [rsp+110h] [rbp-48h]
  _BYTE v43[32]; // [rsp+120h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  lpsz = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpsz,
    0);
  v4 = StringFromCLSID(a1, &lpsz);
  v5 = v4;
  if ( v4 >= 0 )
  {
    memset_0(&v30, 0, 0x58u);
    v30 = *(_OWORD *)a2;
    v7 = (__int64 *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      &hMem,
                      *(_QWORD *)(a2 + 16),
                      -1);
    v8 = *v7;
    *v7 = 0;
    *(_QWORD *)&v31 = v8;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&hMem);
    v9 = (__int64 *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      &hMem,
                      *(_QWORD *)(a2 + 24),
                      -1);
    v10 = *v9;
    *v9 = 0;
    *((_QWORD *)&v31 + 1) = v10;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&hMem);
    v11 = (__int64 *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                       &hMem,
                       *(_QWORD *)(a2 + 40),
                       -1);
    v12 = *v11;
    *v11 = 0;
    *((_QWORD *)&v32 + 1) = v12;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&hMem);
    *(_DWORD *)&pclsid.Data2 = *(_DWORD *)(a2 + 68);
    v13 = *(_QWORD *)(a2 + 32);
    if ( v13 )
    {
      v14 = (__int64 *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                         &hMem,
                         v13,
                         -1);
      v15 = *v14;
      *v14 = 0;
      *(_QWORD *)&v32 = v15;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&hMem);
    }
    v16 = *(_QWORD *)(a2 + 48);
    if ( v16 )
    {
      v17 = (void **)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                       &hMem,
                       v16,
                       -1);
      v18 = *v17;
      *v17 = 0;
      v33[0] = v18;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&hMem);
    }
    unique = (void **)wil::make_unique_hlocal<unsigned char [0]>(&hMem, *(unsigned int *)(a2 + 64));
    v20 = *unique;
    *unique = 0;
    v33[1] = v20;
    v21 = hMem;
    hMem = 0;
    if ( v21 )
    {
      LocalFree(v21);
      v20 = v33[1];
    }
    memcpy_0(v20, *(const void **)(a2 + 56), *(unsigned int *)(a2 + 64));
    pclsid.Data1 = *(_DWORD *)(a2 + 64);
    v29 = 0;
    v22 = StringFromCLSID((const IID *const)(a2 + 72), &v29);
    v23 = v22;
    if ( v22 >= 0 )
    {
      hMem = &v29;
      v28 = 1;
      v24 = CLSIDFromString(v29, (LPCLSID)pclsid.Data4);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x48F,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)(unsigned int)v24,
          (int)lpsz);
      v25 = std::wstring::wstring(v43, lpsz);
      std::wstring::wstring(v36, v25);
      v37 = v30;
      v38 = v31;
      v39 = v32;
      v40 = *(_OWORD *)v33;
      v41 = pclsid;
      v42 = v35;
      std::wstring::operator=(&qword_1801AD070, v36);
      xmmword_1801AD090 = v37;
      xmmword_1801AD0A0 = v38;
      xmmword_1801AD0B0 = v39;
      xmmword_1801AD0C0 = v40;
      xmmword_1801AD0D0 = (__int128)v41;
      qword_1801AD0E0 = v42;
      std::wstring::_Tidy_deallocate(v36);
      std::wstring::_Tidy_deallocate(v43);
      CoTaskMemFree(v29);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48D,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)v22,
        (int)lpsz);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
      return v23;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x473,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)v4,
      (int)lpsz);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
    return v5;
  }
}

```

## disassembly

```asm
0x180038ee0  mov     [rsp+arg_10], rbx
0x180038ee5  push    rdi
0x180038ee6  sub     rsp, 150h
0x180038eed  mov     rax, cs:__security_cookie
0x180038ef4  xor     rax, rsp
0x180038ef7  mov     [rsp+158h+var_18], rax
0x180038eff  mov     rbx, rdx
0x180038f02  mov     rdi, rcx
0x180038f05  mov     [rsp+158h+lpsz], 0; int
0x180038f0e  xor     edx, edx
0x180038f10  lea     rcx, [rsp+158h+lpsz]
0x180038f15  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180038f1a  lea     rdx, [rsp+158h+lpsz]; lplpsz
0x180038f1f  mov     rcx, rdi; rclsid
0x180038f22  call    cs:__imp_StringFromCLSID
0x180038f28  mov     edi, eax
0x180038f2a  test    eax, eax
0x180038f2c  jns     short loc_180038F5C
0x180038f2e  mov     rcx, [rsp+158h]; this
0x180038f36  mov     r9d, eax; char *
0x180038f39  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180038f40  mov     edx, 473h; void *
0x180038f45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038f4a  nop
0x180038f4b  lea     rcx, [rsp+158h+lpsz]
0x180038f50  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180038f55  mov     eax, edi
0x180038f57  jmp     loc_18003926A
0x180038f5c  xor     edx, edx; Val
0x180038f5e  lea     r8d, [rdx+58h]; Size
0x180038f62  lea     rcx, [rsp+158h+var_118]; void *
0x180038f67  call    memset_0
0x180038f6c  mov     rax, [rbx]
0x180038f6f  mov     qword ptr [rsp+158h+var_118], rax
0x180038f74  mov     rax, [rbx+8]
0x180038f78  mov     qword ptr [rsp+158h+var_118+8], rax
0x180038f7d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180038f81  mov     r8, rdi
0x180038f84  mov     rdx, [rbx+10h]
0x180038f88  lea     rcx, [rsp+158h+hMem]
0x180038f8d  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180038f92  mov     rcx, [rax]
0x180038f95  mov     qword ptr [rax], 0
0x180038f9c  mov     qword ptr [rsp+158h+var_108], rcx
0x180038fa1  lea     rcx, [rsp+158h+hMem]
0x180038fa6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180038fab  mov     r8, rdi
0x180038fae  mov     rdx, [rbx+18h]
0x180038fb2  lea     rcx, [rsp+158h+hMem]
0x180038fb7  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180038fbc  mov     rcx, [rax]
0x180038fbf  mov     qword ptr [rax], 0
0x180038fc6  mov     qword ptr [rsp+158h+var_108+8], rcx
0x180038fcb  lea     rcx, [rsp+158h+hMem]
0x180038fd0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180038fd5  mov     r8, rdi
0x180038fd8  mov     rdx, [rbx+28h]
0x180038fdc  lea     rcx, [rsp+158h+hMem]
0x180038fe1  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180038fe6  mov     rcx, [rax]
0x180038fe9  mov     qword ptr [rax], 0
0x180038ff0  mov     qword ptr [rsp+158h+var_F8+8], rcx
0x180038ff5  lea     rcx, [rsp+158h+hMem]
0x180038ffa  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180038fff  mov     eax, [rbx+44h]
0x180039002  mov     dword ptr [rsp+158h+pclsid.Data2], eax
0x180039009  mov     rdx, [rbx+20h]
0x18003900d  test    rdx, rdx
0x180039010  jz      short loc_180039038
0x180039012  mov     r8, rdi
0x180039015  lea     rcx, [rsp+158h+hMem]
0x18003901a  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003901f  mov     rcx, [rax]
0x180039022  mov     qword ptr [rax], 0
0x180039029  mov     qword ptr [rsp+158h+var_F8], rcx
0x18003902e  lea     rcx, [rsp+158h+hMem]
0x180039033  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180039038  mov     rdx, [rbx+30h]
0x18003903c  test    rdx, rdx
0x18003903f  jz      short loc_180039067
0x180039041  mov     r8, rdi
0x180039044  lea     rcx, [rsp+158h+hMem]
0x180039049  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003904e  mov     rcx, [rax]
0x180039051  mov     qword ptr [rax], 0
0x180039058  mov     [rsp+158h+var_E8], rcx
0x18003905d  lea     rcx, [rsp+158h+hMem]
0x180039062  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180039067  mov     edx, [rbx+40h]
0x18003906a  lea     rcx, [rsp+158h+hMem]
0x18003906f  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x180039074  mov     rcx, [rax]
0x180039077  mov     qword ptr [rax], 0
0x18003907e  mov     [rsp+158h+var_E8+8], rcx
0x180039083  mov     rax, [rsp+158h+hMem]
0x180039088  mov     [rsp+158h+hMem], 0
0x180039091  test    rax, rax
0x180039094  jz      short loc_1800390A4
0x180039096  mov     rcx, rax; hMem
0x180039099  call    cs:__imp_LocalFree
0x18003909f  mov     rcx, [rsp+158h+var_E8+8]; void *
0x1800390a4  mov     r8d, [rbx+40h]; Size
0x1800390a8  mov     rdx, [rbx+38h]; Src
0x1800390ac  call    memcpy_0
0x1800390b1  mov     eax, [rbx+40h]
0x1800390b4  mov     [rsp+158h+pclsid.Data1], eax
0x1800390bb  mov     [rsp+158h+var_120], 0
0x1800390c4  lea     rcx, [rbx+48h]; rclsid
0x1800390c8  lea     rdx, [rsp+158h+var_120]; lplpsz
0x1800390cd  call    cs:__imp_StringFromCLSID
0x1800390d3  mov     ebx, eax
0x1800390d5  test    eax, eax
0x1800390d7  jns     short loc_180039107
0x1800390d9  mov     rcx, [rsp+158h]; this
0x1800390e1  mov     r9d, eax; char *
0x1800390e4  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800390eb  mov     edx, 48Dh; void *
0x1800390f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800390f5  nop
0x1800390f6  lea     rcx, [rsp+158h+lpsz]
0x1800390fb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180039100  mov     eax, ebx
0x180039102  jmp     loc_18003926A
0x180039107  lea     rax, [rsp+158h+var_120]
0x18003910c  mov     [rsp+158h+hMem], rax
0x180039111  mov     [rsp+158h+var_128], 1
0x180039116  lea     rdx, [rsp+158h+pclsid.Data4]; pclsid
0x18003911e  mov     rcx, [rsp+158h+var_120]; lpsz
0x180039123  call    cs:__imp_CLSIDFromString
0x180039129  mov     rcx, [rsp+158h]; this
0x180039131  test    eax, eax
0x180039133  jns     short loc_180039149
0x180039135  mov     r9d, eax; char *
0x180039138  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18003913f  mov     edx, 48Fh; void *
0x180039144  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039149  mov     rdx, [rsp+158h+lpsz]
0x18003914e  lea     rcx, [rsp+158h+var_38]
0x180039156  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003915b  mov     rdx, rax
0x18003915e  lea     rcx, [rsp+158h+var_B8]
0x180039166  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18003916b  movaps  xmm2, [rsp+158h+var_118]
0x180039170  movaps  [rsp+158h+var_98], xmm2
0x180039178  movaps  xmm3, [rsp+158h+var_108]
0x18003917d  movaps  [rsp+158h+var_88], xmm3
0x180039185  movaps  xmm0, [rsp+158h+var_F8]
0x18003918a  movaps  [rsp+158h+var_78], xmm0
0x180039192  movaps  xmm1, xmmword ptr [rsp+158h+var_E8]
0x180039197  movaps  [rsp+158h+var_68], xmm1
0x18003919f  movaps  xmm0, xmmword ptr [rsp+158h+pclsid.Data1]
0x1800391a7  movaps  [rsp+158h+var_58], xmm0
0x1800391af  movsd   xmm1, [rsp+158h+var_C8]
0x1800391b8  movsd   [rsp+158h+var_48], xmm1
0x1800391c1  lea     rdx, [rsp+158h+var_B8]
0x1800391c9  lea     rcx, qword_1801AD070
0x1800391d0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800391d5  movaps  xmm0, [rsp+158h+var_98]
0x1800391dd  movaps  cs:xmmword_1801AD090, xmm0
0x1800391e4  movaps  xmm1, [rsp+158h+var_88]
0x1800391ec  movaps  cs:xmmword_1801AD0A0, xmm1
0x1800391f3  movaps  xmm0, [rsp+158h+var_78]
0x1800391fb  movaps  cs:xmmword_1801AD0B0, xmm0
0x180039202  movaps  xmm1, [rsp+158h+var_68]
0x18003920a  movaps  cs:xmmword_1801AD0C0, xmm1
0x180039211  movaps  xmm0, [rsp+158h+var_58]
0x180039219  movaps  cs:xmmword_1801AD0D0, xmm0
0x180039220  movsd   xmm1, [rsp+158h+var_48]
0x180039229  movsd   cs:qword_1801AD0E0, xmm1
0x180039231  lea     rcx, [rsp+158h+var_B8]
0x180039239  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003923e  lea     rcx, [rsp+158h+var_38]
0x180039246  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003924b  nop
0x18003924c  mov     rcx, [rsp+158h+var_120]; pv
0x180039251  call    cs:__imp_CoTaskMemFree
0x180039257  nop
0x180039258  lea     rcx, [rsp+158h+lpsz]
0x18003925d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180039262  xor     eax, eax
0x180039264  jmp     short loc_18003926A
0x180039266  mov     eax, dword ptr [rsp+158h+lpsz]
0x18003926a  mov     rcx, [rsp+158h+var_18]
0x180039272  xor     rcx, rsp; StackCookie
0x180039275  call    __security_check_cookie
0x18003927a  mov     rbx, [rsp+158h+arg_10]
0x180039282  add     rsp, 150h
0x180039289  pop     rdi
0x18003928a  retn
```
