# SystemSettings::BatteryUsageHandlers::UsageDataSingleton::IsApp(ushort *,int *)

- ea: `0x180044aa4`
- end: `0x180044c5b`
- name: `?IsApp@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@AEAAJPEAGPEAH@Z`
- size: `439`
- prototype: `int(SystemSettings::BatteryUsageHandlers::UsageDataSingleton *__hidden this, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180044c64`

## callees

- `0x180004cfc`
- `0x180005d28`
- `0x1800063a4`
- `0x18000a13c`
- `0x18003e4f4`
- `0x180044aa4`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180044b17`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180044b17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044b60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044bed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044b60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044bed`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180044bb7`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180044bb7`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton::IsApp(
        SystemSettings::BatteryUsageHandlers::UsageDataSingleton *this,
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
      v7 = 786;
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
        v7 = 791;
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
        v7 = 792;
        goto LABEL_5;
      }
    }
    *a3 = 1;
    v5 = 0;
    goto LABEL_17;
  }
  v5 = -2147024809;
  v6 = 2147942487LL;
  v7 = 784;
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
0x180044aa4  mov     [rsp-30h+pv], rcx
0x180044aa9  push    rbp
0x180044aaa  push    rbx
0x180044aab  push    rsi
0x180044aac  push    rdi
0x180044aad  push    r14
0x180044aaf  push    r15
0x180044ab1  mov     rbp, rsp
0x180044ab4  sub     rsp, 38h
0x180044ab8  mov     rsi, r8
0x180044abb  mov     rdi, rdx
0x180044abe  mov     [rbp+arg_10], 0
0x180044ac6  mov     [rbp+pv], 0
0x180044ace  mov     [rbp+arg_8], 0
0x180044ad6  mov     dword ptr [r8], 0
0x180044add  test    rdx, rdx
0x180044ae0  jnz     short loc_180044AF1
0x180044ae2  mov     ebx, 80070057h
0x180044ae7  mov     r9d, ebx
0x180044aea  mov     edx, 310h
0x180044aef  jmp     short loc_180044B2B
0x180044af1  lea     rcx, [rbp+arg_10]
0x180044af5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044afa  lea     rax, [rbp+arg_10]
0x180044afe  mov     qword ptr [rsp+38h+ppv], rax; int
0x180044b03  lea     r9, _GUID_21cbc515_2dde_4d66_8292_ba34bd25094a; riid
0x180044b0a  xor     edx, edx; pUnkOuter
0x180044b0c  lea     r8d, [rdx+3]; dwClsContext
0x180044b10  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x180044b17  call    cs:__imp_CoCreateInstance
0x180044b1d  mov     ebx, eax
0x180044b1f  test    eax, eax
0x180044b21  jns     short loc_180044B40
0x180044b23  mov     edx, 312h; void *
0x180044b28  mov     r9d, eax; char *
0x180044b2b  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180044b32  mov     rcx, [rbp+30h]; this
0x180044b36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044b3b  jmp     loc_180044C2F
0x180044b40  mov     r14, [rbp+arg_10]
0x180044b44  mov     rax, [r14]
0x180044b47  mov     r15, [rax+48h]
0x180044b4b  mov     rbx, [rbp+pv]
0x180044b4f  test    rbx, rbx
0x180044b52  jz      short loc_180044B6F
0x180044b54  lea     rcx, [rbp+arg_18]; this
0x180044b58  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180044b5d  mov     rcx, rbx; pv
0x180044b60  call    cs:__imp_CoTaskMemFree
0x180044b66  lea     rcx, [rbp+arg_18]; this
0x180044b6a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180044b6f  mov     [rbp+pv], 0
0x180044b77  lea     rcx, [rbp+arg_8]
0x180044b7b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044b80  lea     r9, [rbp+pv]
0x180044b84  lea     r8, [rbp+arg_8]
0x180044b88  mov     rdx, rdi
0x180044b8b  mov     rcx, r14
0x180044b8e  mov     rax, r15
0x180044b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b96  test    eax, eax
0x180044b98  jns     loc_180044C27
0x180044b9e  lea     rcx, [rbp+arg_8]
0x180044ba2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044ba7  lea     r9, [rbp+arg_8]; ppv
0x180044bab  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180044bb2  xor     edx, edx; pbc
0x180044bb4  mov     rcx, rdi; pszPath
0x180044bb7  call    cs:__imp_SHCreateItemFromParsingName
0x180044bbd  mov     ebx, eax
0x180044bbf  test    eax, eax
0x180044bc1  jns     short loc_180044BCD
0x180044bc3  mov     edx, 317h
0x180044bc8  jmp     loc_180044B28
0x180044bcd  mov     rdi, [rbp+arg_10]
0x180044bd1  mov     rax, [rdi]
0x180044bd4  mov     r14, [rax+78h]
0x180044bd8  mov     rbx, [rbp+pv]
0x180044bdc  test    rbx, rbx
0x180044bdf  jz      short loc_180044BFC
0x180044be1  lea     rcx, [rbp+arg_18]; this
0x180044be5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180044bea  mov     rcx, rbx; pv
0x180044bed  call    cs:__imp_CoTaskMemFree
0x180044bf3  lea     rcx, [rbp+arg_18]; this
0x180044bf7  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180044bfc  mov     [rbp+pv], 0
0x180044c04  lea     r8, [rbp+pv]
0x180044c08  mov     rdx, [rbp+arg_8]
0x180044c0c  mov     rcx, rdi
0x180044c0f  mov     rax, r14
0x180044c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c17  mov     ebx, eax
0x180044c19  test    eax, eax
0x180044c1b  jns     short loc_180044C27
0x180044c1d  mov     edx, 318h
0x180044c22  jmp     loc_180044B28
0x180044c27  mov     dword ptr [rsi], 1
0x180044c2d  xor     ebx, ebx
0x180044c2f  lea     rcx, [rbp+arg_8]
0x180044c33  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044c38  nop
0x180044c39  lea     rcx, [rbp+pv]
0x180044c3d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180044c42  nop
0x180044c43  lea     rcx, [rbp+arg_10]
0x180044c47  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044c4c  mov     eax, ebx
0x180044c4e  add     rsp, 38h
0x180044c52  pop     r15
0x180044c54  pop     r14
0x180044c56  pop     rdi
0x180044c57  pop     rsi
0x180044c58  pop     rbx
0x180044c59  pop     rbp
0x180044c5a  retn
```
