# IsModernAppRunning(IAppInfo *,ushort const *,int *,int *)

- ea: `0x18006c4f0`
- end: `0x18006caad`
- name: `?IsModernAppRunning@@YAJPEAVIAppInfo@@PEBGPEAH2@Z`
- size: `1469`
- prototype: `__int64 __fastcall(struct IAppInfo *, const unsigned __int16 *, int *, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180059a00`
- `0x18006c038`

## callees

- `0x180004e38`
- `0x18000e090`
- `0x180011618`
- `0x18006c4f0`
- `0x18006cab4`
- `0x180080a00`
- `0x1800a5b54`
- `0x1800bca24`
- `0x1800e2230`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c7a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c865`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c8e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c7a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c865`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c8e3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x18006ca29`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x18006ca29`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18006c5af`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18006ca3b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18006c5af`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18006ca3b`

## string_xrefs

- `0x18006c5c6`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnusermgrutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall IsModernAppRunning(struct IAppInfo *a1, const unsigned __int16 *a2, int *a3, int *a4)
{
  int ServiceProvider; // eax
  unsigned int v9; // ebx
  struct IServiceProvider *v10; // rdi
  HRESULT (__stdcall *QueryService)(IServiceProvider *, const GUID *const, const IID *const, void **); // rbx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  struct IServiceProvider *v15; // rcx
  _QWORD *v16; // rcx
  bool v17; // zf
  struct IServiceProvider *v18; // rcx
  __int64 v19; // rcx
  struct IServiceProvider *v20; // rcx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  struct IServiceProvider *v25; // rcx
  __int64 v27; // rcx
  struct IServiceProvider *v28; // rcx
  __int64 v29; // rcx
  struct IServiceProvider *v30; // rcx
  char v31; // bl
  int v32; // eax
  int v33; // [rsp+20h] [rbp-49h]
  int v34; // [rsp+20h] [rbp-49h]
  __int64 v35; // [rsp+30h] [rbp-39h] BYREF
  struct IServiceProvider *v36; // [rsp+38h] [rbp-31h] BYREF
  __int64 v37; // [rsp+40h] [rbp-29h] BYREF
  __int64 v38; // [rsp+48h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-19h] BYREF
  __int64 v40; // [rsp+58h] [rbp-11h]
  __int64 v41; // [rsp+60h] [rbp-9h]
  __int64 v42; // [rsp+68h] [rbp-1h] BYREF
  __int64 *v43; // [rsp+70h] [rbp+7h] BYREF
  __int64 v44; // [rsp+78h] [rbp+Fh] BYREF
  char v45; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  unsigned int v47; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_59874da8fa92327cd21a2ad2aa11dc17_Traceguids);
  }
  *a3 = 1;
  if ( a4 )
    *a4 = 0;
  v36 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  ServiceProvider = GetServiceProvider(&v36);
  v9 = ServiceProvider;
  if ( ServiceProvider < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\wpnplmhelpers.cpp",
      (const char *)(unsigned int)ServiceProvider,
      v33);
    v18 = v36;
    if ( v36 )
    {
      v36 = 0;
      ((void (__fastcall *)(struct IServiceProvider *))v18->lpVtbl->Release)(v18);
    }
    v16 = WPP_GLOBAL_Control;
    v17 = WPP_GLOBAL_Control == &WPP_GLOBAL_Control;
    goto LABEL_57;
  }
  v35 = 0;
  v10 = v36;
  QueryService = v36->lpVtbl->QueryService;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  v12 = ((__int64 (__fastcall *)(struct IServiceProvider *, SID *, GUID *, __int64 *))QueryService)(
          v10,
          &SID_ProcessLifetimeManagerControl,
          &GUID_2f3eca0f_a0a7_445b_8f88_f6260a7dac04,
          &v35);
  v9 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\wpnplmhelpers.cpp",
      (const char *)(unsigned int)v12,
      v33);
    v19 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v36;
    if ( v36 )
    {
      v36 = 0;
      ((void (__fastcall *)(struct IServiceProvider *))v20->lpVtbl->Release)(v20);
    }
    v16 = WPP_GLOBAL_Control;
    v17 = WPP_GLOBAL_Control == &WPP_GLOBAL_Control;
    goto LABEL_57;
  }
  v37 = 0;
  v13 = UMgrQueryUserContext(0, &v37);
  v9 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnusermgrutil.cpp",
      (const char *)(unsigned int)v13,
      v33);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\wpnplmhelpers.cpp",
      (const char *)v9,
      v34);
    v14 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v36;
    if ( v36 )
    {
      v36 = 0;
      ((void (__fastcall *)(struct IServiceProvider *))v15->lpVtbl->Release)(v15);
    }
    v16 = WPP_GLOBAL_Control;
    v17 = WPP_GLOBAL_Control == &WPP_GLOBAL_Control;
    goto LABEL_57;
  }
  v47 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *, unsigned int *))(*(_QWORD *)v35 + 24LL))(
          v35,
          v37,
          a2,
          &v47);
  v9 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\wpnplmhelpers.cpp",
      (const char *)(unsigned int)v21,
      v33);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    v16 = WPP_GLOBAL_Control;
    v17 = WPP_GLOBAL_Control == &WPP_GLOBAL_Control;
    goto LABEL_57;
  }
  if ( !v47 )
  {
    pv = 0;
    v40 = -1;
    v41 = -1;
    v22 = (*(__int64 (__fastcall **)(struct IAppInfo *, const unsigned __int16 *, LPVOID *))(*(_QWORD *)a1 + 24LL))(
            a1,
            a2,
            &pv);
    v9 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\wpnplmhelpers.cpp",
        (const char *)(unsigned int)v22,
        v33);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v40 = 0;
      v41 = 0;
      v29 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      v30 = v36;
      if ( v36 )
      {
        v36 = 0;
        ((void (__fastcall *)(struct IServiceProvider *))v30->lpVtbl->Release)(v30);
      }
      v16 = WPP_GLOBAL_Control;
      v17 = WPP_GLOBAL_Control == &WPP_GLOBAL_Control;
      goto LABEL_57;
    }
    v23 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID, unsigned int *))(*(_QWORD *)v35 + 32LL))(
            v35,
            v37,
            pv,
            &v47);
    v9 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\wpnplmhelpers.cpp",
        (const char *)(unsigned int)v23,
        v33);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v40 = 0;
      v41 = 0;
      v27 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      v28 = v36;
      if ( v36 )
      {
        v36 = 0;
        ((void (__fastcall *)(struct IServiceProvider *))v28->lpVtbl->Release)(v28);
      }
      v16 = WPP_GLOBAL_Control;
      v17 = WPP_GLOBAL_Control == &WPP_GLOBAL_Control;
      goto LABEL_57;
    }
    if ( v47 || !(unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent() )
      goto LABEL_28;
    v38 = 0;
    v42 = 0;
    v43 = &v38;
    v44 = 0;
    v45 = 1;
    if ( (int)UMgrQueryDefaultAccountToken(&v44) < 0 || (v31 = 1, (int)UMgrQueryUserContext(v38, &v42) < 0) )
      v31 = 0;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v43);
    if ( !v31
      || (v32 = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *, unsigned int *))(*(_QWORD *)v35 + 24LL))(
                  v35,
                  v37,
                  a2,
                  &v47),
          v9 = v32,
          v32 >= 0) )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
LABEL_28:
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_30;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\wpnplmhelpers.cpp",
      (const char *)(unsigned int)v32,
      v33);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    v16 = WPP_GLOBAL_Control;
    v17 = WPP_GLOBAL_Control == &WPP_GLOBAL_Control;
LABEL_57:
    if ( !v17 && (*((_BYTE *)v16 + 28) & 0x40) != 0 && *((_BYTE *)v16 + 25) >= 6u )
      WPP_SF_(v16[2], 11, WPP_59874da8fa92327cd21a2ad2aa11dc17_Traceguids);
    return v9;
  }
LABEL_30:
  if ( v47 > 1 )
    *a3 = 0;
  if ( a4 && v47 - 4 <= 1 )
    *a4 = 1;
  v24 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = v36;
  if ( v36 )
  {
    v36 = 0;
    ((void (__fastcall *)(struct IServiceProvider *))v25->lpVtbl->Release)(v25);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_59874da8fa92327cd21a2ad2aa11dc17_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18006c4f0  mov     [rsp-8+arg_0], rbx
0x18006c4f5  push    rbp
0x18006c4f6  push    rsi
0x18006c4f7  push    rdi
0x18006c4f8  push    r12
0x18006c4fa  push    r13
0x18006c4fc  push    r14
0x18006c4fe  push    r15
0x18006c500  lea     rbp, [rsp-27h]
0x18006c505  sub     rsp, 90h
0x18006c50c  mov     rsi, r9
0x18006c50f  mov     r14, r8
0x18006c512  mov     r12, rdx
0x18006c515  mov     r15, rcx
0x18006c518  xor     r13d, r13d
0x18006c51b  lea     rdi, WPP_GLOBAL_Control
0x18006c522  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c529  cmp     rcx, rdi
0x18006c52c  jnz     loc_18006C6DF
0x18006c532  mov     [rbp+57h+arg_11], 1
0x18006c536  mov     dword ptr [r14], 1
0x18006c53d  test    rsi, rsi
0x18006c540  jnz     loc_18006C93C
0x18006c546  mov     [rbp+57h+var_88], r13
0x18006c54a  lea     rcx, [rbp+57h+var_88]
0x18006c54e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006c553  lea     rcx, [rbp+57h+var_88]; struct IServiceProvider **
0x18006c557  call    ?GetServiceProvider@@YAJPEAPEAUIServiceProvider@@@Z; GetServiceProvider(IServiceProvider * *)
0x18006c55c  mov     ebx, eax
0x18006c55e  test    eax, eax
0x18006c560  js      loc_18006C63A
0x18006c566  mov     [rbp+57h+var_90], r13
0x18006c56a  mov     rdi, [rbp+57h+var_88]
0x18006c56e  mov     rax, [rdi]
0x18006c571  mov     rbx, [rax+18h]
0x18006c575  lea     rcx, [rbp+57h+var_90]
0x18006c579  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006c57e  lea     r9, [rbp+57h+var_90]
0x18006c582  lea     r8, _GUID_2f3eca0f_a0a7_445b_8f88_f6260a7dac04
0x18006c589  lea     rdx, SID_ProcessLifetimeManagerControl
0x18006c590  mov     rcx, rdi
0x18006c593  mov     rax, rbx
0x18006c596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c59b  mov     ebx, eax
0x18006c59d  test    eax, eax
0x18006c59f  js      loc_18006C67C
0x18006c5a5  mov     [rbp+57h+var_80], r13
0x18006c5a9  lea     rdx, [rbp+57h+var_80]
0x18006c5ad  xor     ecx, ecx
0x18006c5af  call    cs:__imp_UMgrQueryUserContext
0x18006c5b5  mov     ebx, eax
0x18006c5b7  test    eax, eax
0x18006c5b9  jns     loc_18006C70D
0x18006c5bf  mov     rcx, [rbp+5Fh]; this
0x18006c5c3  mov     r9d, eax; char *
0x18006c5c6  lea     r8, aOnecoreuapBase_105; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c5cd  mov     edx, 2Dh ; '-'; void *
0x18006c5d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c5d7  mov     rcx, [rbp+5Fh]; this
0x18006c5db  mov     r9d, ebx; char *
0x18006c5de  lea     r8, aOnecoreuapBase_141; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c5e5  mov     edx, 2Fh ; '/'; void *
0x18006c5ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c5ef  nop
0x18006c5f0  mov     rcx, [rbp+57h+var_90]
0x18006c5f4  test    rcx, rcx
0x18006c5f7  jz      short loc_18006C60A
0x18006c5f9  mov     [rbp+57h+var_90], r13
0x18006c5fd  mov     rax, [rcx]
0x18006c600  mov     rax, [rax+10h]
0x18006c604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c609  nop
0x18006c60a  mov     rcx, [rbp+57h+var_88]
0x18006c60e  test    rcx, rcx
0x18006c611  jz      short loc_18006C624
0x18006c613  mov     [rbp+57h+var_88], r13
0x18006c617  mov     rax, [rcx]
0x18006c61a  mov     rax, [rax+10h]
0x18006c61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c623  nop
0x18006c624  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c62b  lea     rax, WPP_GLOBAL_Control
0x18006c632  cmp     rcx, rax
0x18006c635  jmp     loc_18006C996
0x18006c63a  mov     rcx, [rbp+5Fh]; this
0x18006c63e  mov     r9d, ebx; char *
0x18006c641  lea     r8, aOnecoreuapBase_141; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c648  mov     edx, 26h ; '&'; void *
0x18006c64d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c652  nop
0x18006c653  mov     rcx, [rbp+57h+var_88]
0x18006c657  test    rcx, rcx
0x18006c65a  jz      short loc_18006C66D
0x18006c65c  mov     [rbp+57h+var_88], r13
0x18006c660  mov     rax, [rcx]
0x18006c663  mov     rax, [rax+10h]
0x18006c667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c66c  nop
0x18006c66d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c674  cmp     rcx, rdi
0x18006c677  jmp     loc_18006C996
0x18006c67c  mov     rcx, [rbp+5Fh]; this
0x18006c680  mov     r9d, ebx; char *
0x18006c683  lea     r8, aOnecoreuapBase_141; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c68a  mov     edx, 2Ch ; ','; void *
0x18006c68f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c694  nop
0x18006c695  mov     rcx, [rbp+57h+var_90]
0x18006c699  test    rcx, rcx
0x18006c69c  jz      short loc_18006C6AF
0x18006c69e  mov     [rbp+57h+var_90], r13
0x18006c6a2  mov     rax, [rcx]
0x18006c6a5  mov     rax, [rax+10h]
0x18006c6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c6ae  nop
0x18006c6af  mov     rcx, [rbp+57h+var_88]
0x18006c6b3  test    rcx, rcx
0x18006c6b6  jz      short loc_18006C6C9
0x18006c6b8  mov     [rbp+57h+var_88], r13
0x18006c6bc  mov     rax, [rcx]
0x18006c6bf  mov     rax, [rax+10h]
0x18006c6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c6c8  nop
0x18006c6c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c6d0  lea     rax, WPP_GLOBAL_Control
0x18006c6d7  cmp     rcx, rax
0x18006c6da  jmp     loc_18006C996
0x18006c6df  test    byte ptr [rcx+1Ch], 40h
0x18006c6e3  jz      loc_18006C532
0x18006c6e9  cmp     byte ptr [rcx+19h], 6
0x18006c6ed  jb      loc_18006C532
0x18006c6f3  mov     edx, 0Ah
0x18006c6f8  lea     r8, WPP_59874da8fa92327cd21a2ad2aa11dc17_Traceguids
0x18006c6ff  mov     rcx, [rcx+10h]
0x18006c703  call    WPP_SF_
0x18006c708  jmp     loc_18006C532
0x18006c70d  mov     [rbp+57h+arg_18], r13d
0x18006c711  mov     rcx, [rbp+57h+var_90]
0x18006c715  mov     rax, [rcx]
0x18006c718  lea     r9, [rbp+57h+arg_18]
0x18006c71c  mov     r8, r12
0x18006c71f  mov     rdx, [rbp+57h+var_80]
0x18006c723  mov     rax, [rax+18h]
0x18006c727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c72c  mov     ebx, eax
0x18006c72e  test    eax, eax
0x18006c730  js      loc_18006C9C0
0x18006c736  cmp     [rbp+57h+arg_18], r13d
0x18006c73a  jnz     short loc_18006C7AB
0x18006c73c  mov     [rbp+57h+pv], r13
0x18006c740  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006c744  mov     [rbp+57h+var_68], rax
0x18006c748  mov     [rbp+57h+var_60], rax
0x18006c74c  mov     rax, [r15]
0x18006c74f  lea     r8, [rbp+57h+pv]
0x18006c753  mov     rdx, r12
0x18006c756  mov     rcx, r15
0x18006c759  mov     rax, [rax+18h]
0x18006c75d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c762  mov     ebx, eax
0x18006c764  test    eax, eax
0x18006c766  js      loc_18006C8C1
0x18006c76c  mov     rcx, [rbp+57h+var_90]
0x18006c770  mov     rax, [rcx]
0x18006c773  lea     r9, [rbp+57h+arg_18]
0x18006c777  mov     r8, [rbp+57h+pv]
0x18006c77b  mov     rdx, [rbp+57h+var_80]
0x18006c77f  mov     rax, [rax+20h]
0x18006c783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c788  mov     ebx, eax
0x18006c78a  test    eax, eax
0x18006c78c  js      loc_18006C843
0x18006c792  cmp     [rbp+57h+arg_18], r13d
0x18006c796  jz      loc_18006CA00
0x18006c79c  mov     rcx, [rbp+57h+pv]; pv
0x18006c7a0  test    rcx, rcx
0x18006c7a3  jz      short loc_18006C7AB
0x18006c7a5  call    cs:__imp_CoTaskMemFree
0x18006c7ab  cmp     [rbp+57h+arg_18], 1
0x18006c7af  ja      loc_18006CA8A
0x18006c7b5  test    rsi, rsi
0x18006c7b8  jnz     loc_18006CA92
0x18006c7be  mov     rcx, [rbp+57h+var_90]
0x18006c7c2  test    rcx, rcx
0x18006c7c5  jz      short loc_18006C7D8
0x18006c7c7  mov     [rbp+57h+var_90], r13
0x18006c7cb  mov     rax, [rcx]
0x18006c7ce  mov     rax, [rax+10h]
0x18006c7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7d7  nop
0x18006c7d8  mov     rcx, [rbp+57h+var_88]
0x18006c7dc  test    rcx, rcx
0x18006c7df  jz      short loc_18006C7F2
0x18006c7e1  mov     [rbp+57h+var_88], r13
0x18006c7e5  mov     rax, [rcx]
0x18006c7e8  mov     rax, [rax+10h]
0x18006c7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7f1  nop
0x18006c7f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c7f9  lea     rax, WPP_GLOBAL_Control
0x18006c800  cmp     rcx, rax
0x18006c803  jz      short loc_18006C826
0x18006c805  test    byte ptr [rcx+1Ch], 40h
0x18006c809  jz      short loc_18006C826
0x18006c80b  cmp     byte ptr [rcx+19h], 6
0x18006c80f  jb      short loc_18006C826
0x18006c811  mov     edx, 0Bh
0x18006c816  lea     r8, WPP_59874da8fa92327cd21a2ad2aa11dc17_Traceguids
0x18006c81d  mov     rcx, [rcx+10h]
0x18006c821  call    WPP_SF_
0x18006c826  xor     eax, eax
0x18006c828  mov     rbx, [rsp+0C0h+arg_0]
0x18006c830  add     rsp, 90h
0x18006c837  pop     r15
0x18006c839  pop     r14
0x18006c83b  pop     r13
0x18006c83d  pop     r12
0x18006c83f  pop     rdi
0x18006c840  pop     rsi
0x18006c841  pop     rbp
0x18006c842  retn
0x18006c843  mov     rcx, [rbp+5Fh]; this
0x18006c847  mov     r9d, ebx; char *
0x18006c84a  lea     r8, aOnecoreuapBase_141; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c851  mov     edx, 42h ; 'B'; void *
0x18006c856  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c85b  nop
0x18006c85c  mov     rcx, [rbp+57h+pv]; pv
0x18006c860  test    rcx, rcx
0x18006c863  jz      short loc_18006C86F
0x18006c865  call    cs:__imp_CoTaskMemFree
0x18006c86b  mov     [rbp+57h+pv], r13
0x18006c86f  mov     [rbp+57h+var_68], r13
0x18006c873  mov     [rbp+57h+var_60], r13
0x18006c877  mov     rcx, [rbp+57h+var_90]
0x18006c87b  test    rcx, rcx
0x18006c87e  jz      short loc_18006C891
0x18006c880  mov     [rbp+57h+var_90], r13
0x18006c884  mov     rax, [rcx]
0x18006c887  mov     rax, [rax+10h]
0x18006c88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c890  nop
0x18006c891  mov     rcx, [rbp+57h+var_88]
0x18006c895  test    rcx, rcx
0x18006c898  jz      short loc_18006C8AB
0x18006c89a  mov     [rbp+57h+var_88], r13
0x18006c89e  mov     rax, [rcx]
0x18006c8a1  mov     rax, [rax+10h]
0x18006c8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c8aa  nop
0x18006c8ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c8b2  lea     rax, WPP_GLOBAL_Control
0x18006c8b9  cmp     rcx, rax
0x18006c8bc  jmp     loc_18006C996
0x18006c8c1  mov     rcx, [rbp+5Fh]; this
0x18006c8c5  mov     r9d, ebx; char *
0x18006c8c8  lea     r8, aOnecoreuapBase_141; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c8cf  mov     edx, 3Dh ; '='; void *
0x18006c8d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c8d9  nop
0x18006c8da  mov     rcx, [rbp+57h+pv]; pv
0x18006c8de  test    rcx, rcx
0x18006c8e1  jz      short loc_18006C8ED
0x18006c8e3  call    cs:__imp_CoTaskMemFree
0x18006c8e9  mov     [rbp+57h+pv], r13
0x18006c8ed  mov     [rbp+57h+var_68], r13
0x18006c8f1  mov     [rbp+57h+var_60], r13
0x18006c8f5  mov     rcx, [rbp+57h+var_90]
0x18006c8f9  test    rcx, rcx
0x18006c8fc  jz      short loc_18006C90F
0x18006c8fe  mov     [rbp+57h+var_90], r13
0x18006c902  mov     rax, [rcx]
0x18006c905  mov     rax, [rax+10h]
0x18006c909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c90e  nop
0x18006c90f  mov     rcx, [rbp+57h+var_88]
0x18006c913  test    rcx, rcx
0x18006c916  jz      short loc_18006C929
0x18006c918  mov     [rbp+57h+var_88], r13
0x18006c91c  mov     rax, [rcx]
0x18006c91f  mov     rax, [rax+10h]
0x18006c923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c928  nop
0x18006c929  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c930  lea     rax, WPP_GLOBAL_Control
0x18006c937  cmp     rcx, rax
0x18006c93a  jmp     short loc_18006C996
0x18006c93c  mov     [rsi], r13d
0x18006c93f  jmp     loc_18006C546
0x18006c944  mov     rcx, [rbp+5Fh]; this
0x18006c948  mov     r9d, ebx; char *
0x18006c94b  lea     r8, aOnecoreuapBase_141; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c952  mov     edx, 4Ch ; 'L'; void *
0x18006c957  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c95c  nop
0x18006c95d  lea     rcx, [rbp+57h+var_78]
0x18006c961  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006c966  nop
0x18006c967  lea     rcx, [rbp+57h+pv]
0x18006c96b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
  ... truncated ...
```
