# CLPInstallHandler::IsUpdateCurrentVersionOnly(bool *)

- ea: `0x1400423bc`
- end: `0x140042554`
- name: `?IsUpdateCurrentVersionOnly@CLPInstallHandler@@CAJPEA_N@Z`
- size: `408`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1400417a8`

## callees

- `0x14001f3d4`
- `0x1400412a8`
- `0x1400423bc`
- `0x14007d010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1400423f4`
- `ole32!CoCreateInstance` at `0x1400423f4`
- `ole32!CoTaskMemFree` at `0x140042521`
- `ole32!CoTaskMemFree` at `0x140042521`
- `ole32!CoSetProxyBlanket` at `0x140042423`
- `ole32!CoSetProxyBlanket` at `0x140042423`

## string_xrefs

- `0x140042478`: `Settings Language Pack Installer`
- `0x140042436`: `pcshell\shell\systemsettings\adminflows\languagepackinstaller\lib\lpinstallhandler.cpp`
- `0x140042497`: `pcshell\shell\systemsettings\adminflows\languagepackinstaller\lib\lpinstallhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CLPInstallHandler::IsUpdateCurrentVersionOnly(bool *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  IUnknown *v4; // rcx
  int v6; // eax
  IUnknown *v7; // rcx
  struct IUnknownVtbl *lpVtbl; // rax
  int v9; // ebx
  void *v10; // rcx
  IUnknown *v11; // rcx
  int ppv; // [rsp+20h] [rbp-40h]
  LPVOID *p_pv; // [rsp+40h] [rbp-20h] BYREF
  __int64 v14; // [rsp+48h] [rbp-18h] BYREF
  char v15; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  IUnknown *pProxy; // [rsp+80h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+28h] BYREF

  *a1 = 1;
  pProxy = 0;
  if ( CoCreateInstance(
         &GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed,
         0,
         0x15u,
         &GUID_f112757a_565b_4260_bd05_9fa34417349a,
         (LPVOID *)&pProxy) >= 0 )
  {
    v2 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 3u, 3u, 0, 0);
    v3 = v2;
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagepackinstaller\\lib\\lpinstallhandler.cpp",
        (const char *)(unsigned int)v2,
        ppv);
      v4 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v4->lpVtbl->Release)(v4);
      }
      return v3;
    }
    v6 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, const wchar_t *, _QWORD))pProxy->lpVtbl[1].QueryInterface)(
           pProxy,
           0,
           L"Settings Language Pack Installer",
           0);
    v3 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18E,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagepackinstaller\\lib\\lpinstallhandler.cpp",
        (const char *)(unsigned int)v6,
        0);
      v7 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v7->lpVtbl->Release)(v7);
      }
      return v3;
    }
    pv = 0;
    lpVtbl = pProxy->lpVtbl;
    p_pv = &pv;
    v14 = 0;
    v15 = 1;
    v9 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64 *))lpVtbl[4].QueryInterface)(pProxy, 27, &v14);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
    v10 = pv;
    if ( v9 >= 0 && *(_WORD *)pv == 49 && !*((_WORD *)pv + 1) )
      *a1 = 0;
    pv = 0;
    if ( v10 )
      CoTaskMemFree(v10);
  }
  v11 = pProxy;
  if ( pProxy )
  {
    pProxy = 0;
    ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
  }
  return 0;
}

```

## disassembly

```asm
0x1400423bc  mov     [rsp-18h+arg_10], rbx
0x1400423c1  push    rbp
0x1400423c2  push    rsi
0x1400423c3  push    rdi
0x1400423c4  mov     rbp, rsp
0x1400423c7  sub     rsp, 60h
0x1400423cb  mov     rdi, rcx
0x1400423ce  mov     byte ptr [rcx], 1
0x1400423d1  xor     esi, esi
0x1400423d3  mov     [rbp+pProxy], rsi
0x1400423d7  lea     rax, [rbp+pProxy]
0x1400423db  mov     [rsp+60h+ppv], rax; ppv
0x1400423e0  lea     r9, _GUID_f112757a_565b_4260_bd05_9fa34417349a; riid
0x1400423e7  xor     edx, edx; pUnkOuter
0x1400423e9  lea     r8d, [rsi+15h]; dwClsContext
0x1400423ed  lea     rcx, _GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed; rclsid
0x1400423f4  call    cs:__imp_CoCreateInstance
0x1400423fa  test    eax, eax
0x1400423fc  js      loc_140042528
0x140042402  mov     [rsp+60h+dwCapabilities], esi; dwCapabilities
0x140042406  mov     [rsp+60h+pAuthInfo], rsi; pAuthInfo
0x14004240b  lea     eax, [rsi+3]
0x14004240e  mov     [rsp+60h+dwImpLevel], eax; dwImpLevel
0x140042412  mov     dword ptr [rsp+60h+ppv], eax; int
0x140042416  xor     r9d, r9d; pServerPrincName
0x140042419  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x14004241c  mov     r8d, edx; dwAuthzSvc
0x14004241f  mov     rcx, [rbp+pProxy]; pProxy
0x140042423  call    cs:__imp_CoSetProxyBlanket
0x140042429  mov     ebx, eax
0x14004242b  test    eax, eax
0x14004242d  jns     short loc_140042469
0x14004242f  mov     rcx, [rbp+18h]; this
0x140042433  mov     r9d, eax; char *
0x140042436  lea     r8, aPcshellShellSy_24; "pcshell\\shell\\systemsettings\\adminfl"...
0x14004243d  mov     edx, 18Ch; void *
0x140042442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140042447  nop
0x140042448  mov     rcx, [rbp+pProxy]
0x14004244c  test    rcx, rcx
0x14004244f  jz      short loc_140042462
0x140042451  mov     [rbp+pProxy], rsi
0x140042455  mov     rax, [rcx]
0x140042458  mov     rax, [rax+10h]
0x14004245c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042461  nop
0x140042462  mov     eax, ebx
0x140042464  jmp     loc_140042544
0x140042469  mov     rcx, [rbp+pProxy]
0x14004246d  mov     rax, [rcx]
0x140042470  mov     [rsp+60h+ppv], rsi; int
0x140042475  xor     r9d, r9d
0x140042478  lea     r8, aSettingsLangua; "Settings Language Pack Installer"
0x14004247f  xor     edx, edx
0x140042481  mov     rax, [rax+18h]
0x140042485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004248a  mov     ebx, eax
0x14004248c  test    eax, eax
0x14004248e  jns     short loc_1400424C5
0x140042490  mov     rcx, [rbp+18h]; this
0x140042494  mov     r9d, eax; char *
0x140042497  lea     r8, aPcshellShellSy_24; "pcshell\\shell\\systemsettings\\adminfl"...
0x14004249e  mov     edx, 18Eh; void *
0x1400424a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400424a8  nop
0x1400424a9  mov     rcx, [rbp+pProxy]
0x1400424ad  test    rcx, rcx
0x1400424b0  jz      short loc_1400424C3
0x1400424b2  mov     [rbp+pProxy], rsi
0x1400424b6  mov     rax, [rcx]
0x1400424b9  mov     rax, [rax+10h]
0x1400424bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400424c2  nop
0x1400424c3  jmp     short loc_140042462
0x1400424c5  mov     [rbp+pv], rsi
0x1400424c9  mov     rcx, [rbp+pProxy]
0x1400424cd  mov     rax, [rcx]
0x1400424d0  lea     rdx, [rbp+pv]
0x1400424d4  mov     [rbp+var_20], rdx
0x1400424d8  mov     [rbp+var_18], rsi
0x1400424dc  mov     [rbp+var_10], 1
0x1400424e0  lea     r8, [rbp+var_18]
0x1400424e4  mov     edx, 1Bh
0x1400424e9  mov     rax, [rax+60h]
0x1400424ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400424f2  mov     ebx, eax
0x1400424f4  lea     rcx, [rbp+var_20]
0x1400424f8  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1400424fd  shr     ebx, 1Fh
0x140042500  mov     rcx, [rbp+pv]; pv
0x140042504  xor     bl, 1
0x140042507  jz      short loc_140042518
0x140042509  cmp     word ptr [rcx], 31h ; '1'
0x14004250d  jnz     short loc_140042518
0x14004250f  cmp     [rcx+2], si
0x140042513  jnz     short loc_140042518
0x140042515  mov     [rdi], sil
0x140042518  mov     [rbp+pv], rsi
0x14004251c  test    rcx, rcx
0x14004251f  jz      short loc_140042528
0x140042521  call    cs:__imp_CoTaskMemFree
0x140042527  nop
0x140042528  mov     rcx, [rbp+pProxy]
0x14004252c  test    rcx, rcx
0x14004252f  jz      short loc_140042542
0x140042531  mov     [rbp+pProxy], rsi
0x140042535  mov     rax, [rcx]
0x140042538  mov     rax, [rax+10h]
0x14004253c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042541  nop
0x140042542  xor     eax, eax
0x140042544  mov     rbx, [rsp+60h+arg_10]
0x14004254c  add     rsp, 60h
0x140042550  pop     rdi
0x140042551  pop     rsi
0x140042552  pop     rbp
0x140042553  retn
```
