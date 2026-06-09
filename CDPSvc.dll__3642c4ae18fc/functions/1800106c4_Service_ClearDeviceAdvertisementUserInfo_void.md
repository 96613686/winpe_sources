# Service::ClearDeviceAdvertisementUserInfo(void)

- ea: `0x1800106c4`
- end: `0x18001087a`
- name: `?ClearDeviceAdvertisementUserInfo@Service@@AEAAJXZ`
- size: `438`
- prototype: `__int64 __fastcall(Service *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800407c0`

## callees

- `0x18000e9c8`
- `0x1800106c4`
- `0x180010880`
- `0x18003ded8`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010750`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800106f7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800106f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Service::ClearDeviceAdvertisementUserInfo(Service *this)
{
  HRESULT v1; // eax
  __int64 v2; // rcx
  __int64 v3; // r9
  LPVOID v4; // rcx
  __int64 v6; // rcx
  _QWORD *v7; // rbx
  __int64 v8; // r9
  LPVOID v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r9
  LPVOID v14; // rcx
  LPVOID v15; // rcx
  _QWORD v16[3]; // [rsp+30h] [rbp-18h] BYREF
  Service *v17; // [rsp+60h] [rbp+18h] BYREF
  int v18; // [rsp+68h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+28h] BYREF
  __int64 v20; // [rsp+78h] [rbp+30h] BYREF

  v17 = this;
  ppv = 0;
  v1 = CoCreateInstance(
         &GUID_edbb66ee_73ae_4ef7_b40d_16656c814e10,
         0,
         4u,
         &GUID_e96c4986_7a6b_4ed1_b55f_5945b735ebd0,
         &ppv);
  if ( v1 < 0 )
  {
    LODWORD(v17) = v1;
    v18 = 792;
    Log<long &,char const (&)[14],int>(
      v2,
      "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int *)&v17,
      v3,
      &v18);
    v4 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return (unsigned int)v17;
  }
  v7 = CoTaskMemAlloc(0x20u);
  v16[0] = v7;
  if ( !v7 )
  {
    LODWORD(v17) = -2147024882;
    v18 = 795;
    Log<long &,char const (&)[14],int>(
      v6,
      "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int *)&v17,
      v8,
      &v18);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v16);
    v9 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return (unsigned int)v17;
  }
  wil::make_unique_ansistring_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(&v20);
  v10 = v20;
  *v7 = v20;
  v7[1] = v10;
  v7[2] = v10;
  v7[3] = v10;
  v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)ppv + 24LL))(ppv, v7);
  if ( v11 < 0 )
  {
    LODWORD(v17) = v11;
    v18 = 804;
    Log<long &,char const (&)[14],int>(
      v12,
      "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int *)&v17,
      v13,
      &v18);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v20);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v16);
    v14 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)v17;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v20);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v16);
  v15 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x1800106c4  mov     [rsp-10h+arg_0], rcx
0x1800106c9  push    rbp
0x1800106ca  push    rbx
0x1800106cb  mov     rbp, rsp
0x1800106ce  sub     rsp, 48h
0x1800106d2  mov     [rbp+arg_10], 0
0x1800106da  lea     rax, [rbp+arg_10]
0x1800106de  mov     [rsp+48h+ppv], rax; ppv
0x1800106e3  lea     r9, _GUID_e96c4986_7a6b_4ed1_b55f_5945b735ebd0; riid
0x1800106ea  xor     edx, edx; pUnkOuter
0x1800106ec  lea     r8d, [rdx+4]; dwClsContext
0x1800106f0  lea     rcx, _GUID_edbb66ee_73ae_4ef7_b40d_16656c814e10; rclsid
0x1800106f7  call    cs:__imp_CoCreateInstance
0x1800106fd  test    eax, eax
0x1800106ff  jns     short loc_18001074B
0x180010701  mov     dword ptr [rbp+arg_0], eax
0x180010704  mov     [rbp+arg_8], 318h
0x18001070b  lea     rax, [rbp+arg_8]
0x18001070f  mov     [rsp+48h+ppv], rax
0x180010714  lea     r8, [rbp+arg_0]
0x180010718  lea     rdx, aHr0x08xFileSLi_1; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18001071f  call    ??$Log@AEAJAEAY0O@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0O@$$CBD$$QEAH@Z; Log<long &,char const (&)[14],int>(CDPLogLevel,char const *,long &,char const (&)[14],int &&)
0x180010724  nop
0x180010725  mov     rcx, [rbp+arg_10]
0x180010729  test    rcx, rcx
0x18001072c  jz      short loc_180010743
0x18001072e  mov     [rbp+arg_10], 0
0x180010736  mov     rdx, [rcx]
0x180010739  mov     rax, [rdx+10h]
0x18001073d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010742  nop
0x180010743  mov     eax, dword ptr [rbp+arg_0]
0x180010746  jmp     loc_180010873
0x18001074b  mov     ecx, 20h ; ' '; cb
0x180010750  call    cs:__imp_CoTaskMemAlloc
0x180010756  mov     rbx, rax
0x180010759  mov     [rbp+var_18], rax
0x18001075d  test    rax, rax
0x180010760  jnz     short loc_1800107B0
0x180010762  mov     dword ptr [rbp+arg_0], 8007000Eh
0x180010769  mov     [rbp+arg_8], 31Bh
0x180010770  lea     rax, [rbp+arg_8]
0x180010774  mov     [rsp+48h+ppv], rax
0x180010779  lea     r8, [rbp+arg_0]
0x18001077d  lea     rdx, aHr0x08xFileSLi_1; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180010784  call    ??$Log@AEAJAEAY0O@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0O@$$CBD$$QEAH@Z; Log<long &,char const (&)[14],int>(CDPLogLevel,char const *,long &,char const (&)[14],int &&)
0x180010789  nop
0x18001078a  lea     rcx, [rbp+var_18]
0x18001078e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180010793  nop
0x180010794  mov     rcx, [rbp+arg_10]
0x180010798  test    rcx, rcx
0x18001079b  jz      short loc_1800107AE
0x18001079d  mov     [rbp+arg_10], rbx
0x1800107a1  mov     rdx, [rcx]
0x1800107a4  mov     rax, [rdx+10h]
0x1800107a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107ad  nop
0x1800107ae  jmp     short loc_180010743
0x1800107b0  lea     rcx, [rbp+arg_18]
0x1800107b4  call    ??$make_unique_ansistring_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@0@PEBD_K@Z; wil::make_unique_ansistring_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(char const *,unsigned __int64)
0x1800107b9  nop
0x1800107ba  mov     rax, [rbp+arg_18]
0x1800107be  mov     [rbx], rax
0x1800107c1  mov     [rbx+8], rax
0x1800107c5  mov     [rbx+10h], rax
0x1800107c9  mov     [rbx+18h], rax
0x1800107cd  mov     rcx, [rbp+arg_10]
0x1800107d1  mov     rax, [rcx]
0x1800107d4  mov     rdx, rbx
0x1800107d7  mov     rax, [rax+18h]
0x1800107db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107e0  test    eax, eax
0x1800107e2  jns     short loc_18001083F
0x1800107e4  mov     dword ptr [rbp+arg_0], eax
0x1800107e7  mov     [rbp+arg_8], 324h
0x1800107ee  lea     rax, [rbp+arg_8]
0x1800107f2  mov     [rsp+48h+ppv], rax
0x1800107f7  lea     r8, [rbp+arg_0]
0x1800107fb  lea     rdx, aHr0x08xFileSLi_1; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180010802  call    ??$Log@AEAJAEAY0O@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0O@$$CBD$$QEAH@Z; Log<long &,char const (&)[14],int>(CDPLogLevel,char const *,long &,char const (&)[14],int &&)
0x180010807  nop
0x180010808  lea     rcx, [rbp+arg_18]
0x18001080c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180010811  nop
0x180010812  lea     rcx, [rbp+var_18]
0x180010816  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18001081b  nop
0x18001081c  mov     rcx, [rbp+arg_10]
0x180010820  test    rcx, rcx
0x180010823  jz      short loc_18001083A
0x180010825  mov     [rbp+arg_10], 0
0x18001082d  mov     rdx, [rcx]
0x180010830  mov     rax, [rdx+10h]
0x180010834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010839  nop
0x18001083a  jmp     loc_180010743
0x18001083f  lea     rcx, [rbp+arg_18]
0x180010843  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180010848  nop
0x180010849  lea     rcx, [rbp+var_18]
0x18001084d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180010852  nop
0x180010853  mov     rcx, [rbp+arg_10]
0x180010857  test    rcx, rcx
0x18001085a  jz      short loc_180010871
0x18001085c  mov     [rbp+arg_10], 0
0x180010864  mov     rax, [rcx]
0x180010867  mov     rax, [rax+10h]
0x18001086b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010870  nop
0x180010871  xor     eax, eax
0x180010873  add     rsp, 48h
0x180010877  pop     rbx
0x180010878  pop     rbp
0x180010879  retn
```
