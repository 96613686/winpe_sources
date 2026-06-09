# SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::IsApp(ushort *,int *)

- ea: `0x180044698`
- end: `0x18004484f`
- name: `?IsApp@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@AEAAJPEAGPEAH@Z`
- size: `439`
- prototype: `int(SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 *__hidden this, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180044858`

## callees

- `0x180004cfc`
- `0x180005d28`
- `0x1800063a4`
- `0x18000a13c`
- `0x18003e4f4`
- `0x180044698`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004470b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004470b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044754`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800447e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044754`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800447e1`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x1800447ab`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x1800447ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::IsApp(
        SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 *this,
        unsigned __int16 *a2,
        int *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  HRESULT v8; // eax
  LPVOID v9; // r14
  int (__fastcall *v10)(LPVOID, unsigned __int16 *, void **, LPVOID *); // r15
  void *v11; // rbx
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, void *, LPVOID *); // r14
  void *v14; // rbx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+30h]
  LPVOID pv; // [rsp+70h] [rbp+38h] BYREF
  void *v19; // [rsp+78h] [rbp+40h] BYREF
  LPVOID v20; // [rsp+80h] [rbp+48h] BYREF
  char v21; // [rsp+88h] [rbp+50h] BYREF

  v20 = 0;
  pv = 0;
  v19 = 0;
  *a3 = 0;
  if ( a2 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    v8 = CoCreateInstance(&CLSID_StartMenuCacheAndAppResolver, 0, 3u, &GUID_21cbc515_2dde_4d66_8292_ba34bd25094a, &v20);
    v5 = v8;
    if ( v8 < 0 )
    {
      v7 = 2256;
LABEL_5:
      v6 = (unsigned int)v8;
      goto LABEL_6;
    }
    v9 = v20;
    v10 = *(int (__fastcall **)(LPVOID, unsigned __int16 *, void **, LPVOID *))(*(_QWORD *)v20 + 72LL);
    v11 = pv;
    if ( pv )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v21);
      CoTaskMemFree(v11);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v21);
    }
    pv = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    if ( v10(v9, a2, &v19, &pv) < 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
      v8 = SHCreateItemFromParsingName(a2, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v19);
      v5 = v8;
      if ( v8 < 0 )
      {
        v7 = 2261;
        goto LABEL_5;
      }
      v12 = v20;
      v13 = *(__int64 (__fastcall **)(LPVOID, void *, LPVOID *))(*(_QWORD *)v20 + 120LL);
      v14 = pv;
      if ( pv )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v21);
        CoTaskMemFree(v14);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v21);
      }
      pv = 0;
      v8 = v13(v12, v19, &pv);
      v5 = v8;
      if ( v8 < 0 )
      {
        v7 = 2262;
        goto LABEL_5;
      }
    }
    *a3 = 1;
    v5 = 0;
    goto LABEL_17;
  }
  v5 = -2147024809;
  v6 = 2147942487LL;
  v7 = 2254;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
    (const char *)v6,
    ppv);
LABEL_17:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  return v5;
}

```

## disassembly

```asm
0x180044698  mov     [rsp-30h+pv], rcx
0x18004469d  push    rbp
0x18004469e  push    rbx
0x18004469f  push    rsi
0x1800446a0  push    rdi
0x1800446a1  push    r14
0x1800446a3  push    r15
0x1800446a5  mov     rbp, rsp
0x1800446a8  sub     rsp, 38h
0x1800446ac  mov     rsi, r8
0x1800446af  mov     rdi, rdx
0x1800446b2  mov     [rbp+arg_10], 0
0x1800446ba  mov     [rbp+pv], 0
0x1800446c2  mov     [rbp+arg_8], 0
0x1800446ca  mov     dword ptr [r8], 0
0x1800446d1  test    rdx, rdx
0x1800446d4  jnz     short loc_1800446E5
0x1800446d6  mov     ebx, 80070057h
0x1800446db  mov     r9d, ebx
0x1800446de  mov     edx, 8CEh
0x1800446e3  jmp     short loc_18004471F
0x1800446e5  lea     rcx, [rbp+arg_10]
0x1800446e9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800446ee  lea     rax, [rbp+arg_10]
0x1800446f2  mov     qword ptr [rsp+38h+ppv], rax; int
0x1800446f7  lea     r9, _GUID_21cbc515_2dde_4d66_8292_ba34bd25094a; riid
0x1800446fe  xor     edx, edx; pUnkOuter
0x180044700  lea     r8d, [rdx+3]; dwClsContext
0x180044704  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x18004470b  call    cs:__imp_CoCreateInstance
0x180044711  mov     ebx, eax
0x180044713  test    eax, eax
0x180044715  jns     short loc_180044734
0x180044717  mov     edx, 8D0h; void *
0x18004471c  mov     r9d, eax; char *
0x18004471f  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180044726  mov     rcx, [rbp+30h]; this
0x18004472a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004472f  jmp     loc_180044823
0x180044734  mov     r14, [rbp+arg_10]
0x180044738  mov     rax, [r14]
0x18004473b  mov     r15, [rax+48h]
0x18004473f  mov     rbx, [rbp+pv]
0x180044743  test    rbx, rbx
0x180044746  jz      short loc_180044763
0x180044748  lea     rcx, [rbp+arg_18]; this
0x18004474c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180044751  mov     rcx, rbx; pv
0x180044754  call    cs:__imp_CoTaskMemFree
0x18004475a  lea     rcx, [rbp+arg_18]; this
0x18004475e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180044763  mov     [rbp+pv], 0
0x18004476b  lea     rcx, [rbp+arg_8]
0x18004476f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044774  lea     r9, [rbp+pv]
0x180044778  lea     r8, [rbp+arg_8]
0x18004477c  mov     rdx, rdi
0x18004477f  mov     rcx, r14
0x180044782  mov     rax, r15
0x180044785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004478a  test    eax, eax
0x18004478c  jns     loc_18004481B
0x180044792  lea     rcx, [rbp+arg_8]
0x180044796  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004479b  lea     r9, [rbp+arg_8]; ppv
0x18004479f  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800447a6  xor     edx, edx; pbc
0x1800447a8  mov     rcx, rdi; pszPath
0x1800447ab  call    cs:__imp_SHCreateItemFromParsingName
0x1800447b1  mov     ebx, eax
0x1800447b3  test    eax, eax
0x1800447b5  jns     short loc_1800447C1
0x1800447b7  mov     edx, 8D5h
0x1800447bc  jmp     loc_18004471C
0x1800447c1  mov     rdi, [rbp+arg_10]
0x1800447c5  mov     rax, [rdi]
0x1800447c8  mov     r14, [rax+78h]
0x1800447cc  mov     rbx, [rbp+pv]
0x1800447d0  test    rbx, rbx
0x1800447d3  jz      short loc_1800447F0
0x1800447d5  lea     rcx, [rbp+arg_18]; this
0x1800447d9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800447de  mov     rcx, rbx; pv
0x1800447e1  call    cs:__imp_CoTaskMemFree
0x1800447e7  lea     rcx, [rbp+arg_18]; this
0x1800447eb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800447f0  mov     [rbp+pv], 0
0x1800447f8  lea     r8, [rbp+pv]
0x1800447fc  mov     rdx, [rbp+arg_8]
0x180044800  mov     rcx, rdi
0x180044803  mov     rax, r14
0x180044806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004480b  mov     ebx, eax
0x18004480d  test    eax, eax
0x18004480f  jns     short loc_18004481B
0x180044811  mov     edx, 8D6h
0x180044816  jmp     loc_18004471C
0x18004481b  mov     dword ptr [rsi], 1
0x180044821  xor     ebx, ebx
0x180044823  lea     rcx, [rbp+arg_8]
0x180044827  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004482c  nop
0x18004482d  lea     rcx, [rbp+pv]
0x180044831  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180044836  nop
0x180044837  lea     rcx, [rbp+arg_10]
0x18004483b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044840  mov     eax, ebx
0x180044842  add     rsp, 38h
0x180044846  pop     r15
0x180044848  pop     r14
0x18004484a  pop     rdi
0x18004484b  pop     rsi
0x18004484c  pop     rbx
0x18004484d  pop     rbp
0x18004484e  retn
```
