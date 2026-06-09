# CUninstallCbsClient::Initialize(wchar_t const * const,wchar_t const * const,wchar_t const * const,wchar_t const * const,wchar_t const * const,ICbsUIHandler *)

- ea: `0x18007c9e8`
- end: `0x18007cd16`
- name: `?Initialize@CUninstallCbsClient@@QEAAJQEB_W0000PEAUICbsUIHandler@@@Z`
- size: `814`
- prototype: `__int64 __fastcall(CUninstallCbsClient *this, const wchar_t *const, const wchar_t *, const wchar_t *const, const wchar_t *, const wchar_t *const, struct ICbsUIHandler *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007bdb0`

## callees

- `0x18001e51c`
- `0x18001fd10`
- `0x180022d80`
- `0x1800293a0`
- `0x18003e810`
- `0x18003eca0`
- `0x18003ed90`
- `0x18004d3a0`
- `0x18007c9e8`
- `0x18007d6ec`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!Sleep` at `0x18007cad0`
- `KERNEL32!Sleep` at `0x18007cad0`
- `OLE32!CoSetProxyBlanket` at `0x18007cb24`
- `OLE32!CoSetProxyBlanket` at `0x18007cb24`
- `OLE32!CoCreateInstance` at `0x18007caa8`
- `OLE32!CoCreateInstance` at `0x18007caa8`
- `OLE32!CoGetMalloc` at `0x18007ca30`
- `OLE32!CoGetMalloc` at `0x18007ca30`

## string_xrefs

- `0x18007cc6f`: `UninstallClient`
- `0x18007ca4b`: `onecore\base\cbs\uninstall\cbsclient.cpp`
- `0x18007cae0`: `onecore\base\cbs\uninstall\cbsclient.cpp`
- `0x18007cb9e`: `onecore\base\cbs\uninstall\cbsclient.cpp`

## pseudocode

```c
__int64 __fastcall CUninstallCbsClient::Initialize(
        CUninstallCbsClient *this,
        const wchar_t *const a2,
        const wchar_t *a3,
        const wchar_t *const a4,
        const wchar_t *a5,
        const wchar_t *const a6,
        struct ICbsUIHandler *a7)
{
  LPMALLOC *InitPointer; // rax
  HRESULT Malloc; // ebx
  __int64 v11; // rdx
  void (*v12)(void); // rax
  unsigned int v14; // esi
  LPVOID *v15; // rdi
  HRESULT Instance; // eax
  void *v17; // rdx
  unsigned int v18; // r8d
  struct ICbsSession **v19; // rax
  __int64 v20; // rdx
  struct ICbsSession **v21; // rax
  __int64 (__fastcall ***v22)(LPVOID, GUID *, __int64); // rdi
  __int64 (__fastcall *v23)(LPVOID, GUID *, __int64); // rbx
  __int64 v24; // rax
  int ppv; // [rsp+20h] [rbp-40h]
  int ppva; // [rsp+20h] [rbp-40h]
  wchar_t *v27; // [rsp+40h] [rbp-20h] BYREF
  __int64 v28; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v28 = 0;
  InitPointer = (LPMALLOC *)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer((char *)this + 16);
  Malloc = CoGetMalloc(1u, InitPointer);
  if ( Malloc < 0 )
  {
    v11 = 67;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\cbs\\uninstall\\cbsclient.cpp",
      (const char *)(unsigned int)Malloc,
      ppv);
    if ( !v28 )
      return (unsigned int)Malloc;
    v12 = *(void (**)(void))(*(_QWORD *)v28 + 16LL);
LABEL_5:
    v12();
    return (unsigned int)Malloc;
  }
  if ( a5 )
  {
    if ( !a3 )
    {
      v27 = 0;
      Malloc = SczAllocFromSz(&v27, a5);
      if ( Malloc >= 0 )
      {
        v15 = (LPVOID *)((char *)this + 8);
        v21 = (struct ICbsSession **)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(v15);
        Malloc = CbsOfflineUtil::CbsCreateOfflineSessionFromStackInImage(
                   (CbsOfflineUtil *)&vCbsOfflineUtil,
                   1,
                   v27,
                   v21);
        if ( Malloc >= 0 )
        {
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v27);
          goto LABEL_27;
        }
        v20 = 89;
      }
      else
      {
        v20 = 87;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\base\\cbs\\uninstall\\cbsclient.cpp",
        (const char *)(unsigned int)Malloc,
        ppv);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v27);
LABEL_22:
      if ( !v28 )
        return (unsigned int)Malloc;
      v12 = *(void (**)(void))(*(_QWORD *)v28 + 16LL);
      goto LABEL_5;
    }
    v15 = (LPVOID *)((char *)this + 8);
    v19 = (struct ICbsSession **)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(v15);
    Malloc = CbsOfflineUtil::CbsCreateOfflineSessionFromExternalStack((CbsOfflineUtil *)&vCbsOfflineUtil, a3, v19);
    if ( Malloc < 0 )
    {
      v11 = 73;
      goto LABEL_3;
    }
  }
  else
  {
    v14 = 0;
    v15 = (LPVOID *)((char *)this + 8);
    while ( 1 )
    {
      if ( *v15 )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x18007CD15LL);
      }
      Instance = CoCreateInstance(
                   &GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed,
                   0,
                   0x15u,
                   &GUID_75207391_23f2_4396_85f0_8fdb879ed0ed,
                   v15);
      Malloc = Instance;
      if ( Instance >= 0 )
        break;
      if ( v14 >= 0xA )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6C,
          (unsigned int)"onecore\\base\\cbs\\uninstall\\cbsclient.cpp",
          (const char *)(unsigned int)Instance,
          ppva);
        goto LABEL_22;
      }
      wil::details::in1diag3::_Log_Hr(retaddr, v17, v18, (const char *)(unsigned int)Instance, ppva);
      Sleep(0x3E8u);
      ++v14;
    }
    Malloc = CoSetProxyBlanket((IUnknown *)*v15, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 5u, 3u, 0, 0);
    if ( Malloc < 0 )
    {
      v11 = 129;
      goto LABEL_3;
    }
  }
LABEL_27:
  v22 = (__int64 (__fastcall ***)(LPVOID, GUID *, __int64))*v15;
  v23 = **v22;
  v24 = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v28);
  Malloc = v23(v22, &GUID_f112757a_565b_4260_bd05_9fa34417349a, v24);
  if ( Malloc < 0 )
  {
    v11 = 132;
    goto LABEL_3;
  }
  if ( a7 )
  {
    Malloc = (*(__int64 (__fastcall **)(__int64, struct ICbsUIHandler *))(*(_QWORD *)v28 + 128LL))(v28, a7);
    if ( Malloc < 0 )
    {
      v11 = 136;
      goto LABEL_3;
    }
  }
  ppv = (int)a5;
  Malloc = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, _QWORD))(*(_QWORD *)v28 + 152LL))(
             v28,
             0x1000000,
             L"UninstallClient",
             0);
  if ( Malloc < 0 )
  {
    v11 = 139;
    goto LABEL_3;
  }
  Malloc = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 184LL))(v28, 4);
  if ( Malloc < 0 )
  {
    v11 = 143;
    goto LABEL_3;
  }
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  return 0;
}

```

## disassembly

```asm
0x18007c9e8  mov     [rsp-28h+arg_8], rbx
0x18007c9ed  push    rbp
0x18007c9ee  push    rsi
0x18007c9ef  push    rdi
0x18007c9f0  push    r14
0x18007c9f2  push    r15
0x18007c9f4  mov     rbp, rsp
0x18007c9f7  sub     rsp, 60h
0x18007c9fb  mov     rax, cs:__security_cookie
0x18007ca02  xor     rax, rsp
0x18007ca05  mov     [rbp+var_10], rax
0x18007ca09  mov     r14, [rbp+arg_20]
0x18007ca0d  mov     rdi, rcx
0x18007ca10  mov     r15, [rbp+arg_30]
0x18007ca14  add     rcx, 10h
0x18007ca18  mov     rsi, r8
0x18007ca1b  mov     [rbp+var_18], 0
0x18007ca23  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007ca28  mov     rdx, rax; ppMalloc
0x18007ca2b  mov     ecx, 1; dwMemContext
0x18007ca30  call    cs:__imp_CoGetMalloc
0x18007ca37  nop     dword ptr [rax+rax+00h]
0x18007ca3c  mov     ebx, eax
0x18007ca3e  test    eax, eax
0x18007ca40  jns     short loc_18007CA76
0x18007ca42  mov     edx, 43h ; 'C'; void *
0x18007ca47  mov     rcx, [rbp+28h]; this
0x18007ca4b  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\uninstall\\cbsclien"...
0x18007ca52  mov     r9d, ebx; char *
0x18007ca55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ca5a  mov     rcx, [rbp+var_18]
0x18007ca5e  test    rcx, rcx
0x18007ca61  jz      short loc_18007CA6F
0x18007ca63  mov     rdx, [rcx]
0x18007ca66  mov     rax, [rdx+10h]
0x18007ca6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ca6f  mov     eax, ebx
0x18007ca71  jmp     loc_18007CCEA
0x18007ca76  test    r14, r14
0x18007ca79  jnz     loc_18007CB44
0x18007ca7f  xor     esi, esi
0x18007ca81  add     rdi, 8
0x18007ca85  cmp     qword ptr [rdi], 0
0x18007ca89  jnz     loc_18007CD0B
0x18007ca8f  xor     edx, edx; pUnkOuter
0x18007ca91  mov     [rsp+60h+ppv], rdi; int
0x18007ca96  lea     r9, _GUID_75207391_23f2_4396_85f0_8fdb879ed0ed; riid
0x18007ca9d  lea     rcx, _GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed; rclsid
0x18007caa4  lea     r8d, [rdx+15h]; dwClsContext
0x18007caa8  call    cs:__imp_CoCreateInstance
0x18007caaf  nop     dword ptr [rax+rax+00h]
0x18007cab4  mov     ebx, eax
0x18007cab6  test    eax, eax
0x18007cab8  jns     short loc_18007CAF6
0x18007caba  mov     rcx, [rbp+28h]; this
0x18007cabe  mov     r9d, eax; char *
0x18007cac1  cmp     esi, 0Ah
0x18007cac4  jnb     short loc_18007CAE0
0x18007cac6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007cacb  mov     ecx, 3E8h; dwMilliseconds
0x18007cad0  call    cs:__imp_Sleep
0x18007cad7  nop     dword ptr [rax+rax+00h]
0x18007cadc  inc     esi
0x18007cade  jmp     short loc_18007CA85
0x18007cae0  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\uninstall\\cbsclien"...
0x18007cae7  mov     edx, 6Ch ; 'l'; void *
0x18007caec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007caf1  jmp     loc_18007CBB6
0x18007caf6  mov     rcx, [rdi]; pProxy
0x18007caf9  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18007cafc  mov     [rsp+60h+dwCapabilities], 0; dwCapabilities
0x18007cb04  mov     r8d, edx; dwAuthzSvc
0x18007cb07  mov     [rsp+60h+pAuthInfo], 0; pAuthInfo
0x18007cb10  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18007cb14  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x18007cb1c  mov     dword ptr [rsp+60h+ppv], 5; dwAuthnLevel
0x18007cb24  call    cs:__imp_CoSetProxyBlanket
0x18007cb2b  nop     dword ptr [rax+rax+00h]
0x18007cb30  mov     ebx, eax
0x18007cb32  test    eax, eax
0x18007cb34  jns     loc_18007CC09
0x18007cb3a  mov     edx, 81h
0x18007cb3f  jmp     loc_18007CA47
0x18007cb44  test    rsi, rsi
0x18007cb47  jz      short loc_18007CB7B
0x18007cb49  add     rdi, 8
0x18007cb4d  mov     rcx, rdi
0x18007cb50  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007cb55  mov     r8, rax; struct ICbsSession **
0x18007cb58  lea     rcx, ?vCbsOfflineUtil@@3VCbsOfflineUtil@@A; this
0x18007cb5f  mov     rdx, rsi; wchar_t *
0x18007cb62  call    ?CbsCreateOfflineSessionFromExternalStack@CbsOfflineUtil@@UEAAJPEB_WPEAPEAUICbsSession@@@Z; CbsOfflineUtil::CbsCreateOfflineSessionFromExternalStack(wchar_t const *,ICbsSession * *)
0x18007cb67  mov     ebx, eax
0x18007cb69  test    eax, eax
0x18007cb6b  jns     loc_18007CC09
0x18007cb71  mov     edx, 49h ; 'I'
0x18007cb76  jmp     loc_18007CA47
0x18007cb7b  mov     rdx, r14
0x18007cb7e  mov     [rbp+var_20], 0
0x18007cb86  lea     rcx, [rbp+var_20]
0x18007cb8a  call    SczAllocFromSz
0x18007cb8f  mov     ebx, eax
0x18007cb91  test    eax, eax
0x18007cb93  jns     short loc_18007CBCF
0x18007cb95  mov     edx, 57h ; 'W'; void *
0x18007cb9a  mov     rcx, [rbp+28h]; this
0x18007cb9e  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\uninstall\\cbsclien"...
0x18007cba5  mov     r9d, ebx; char *
0x18007cba8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cbad  lea     rcx, [rbp+var_20]
0x18007cbb1  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18007cbb6  mov     rcx, [rbp+var_18]
0x18007cbba  test    rcx, rcx
0x18007cbbd  jz      loc_18007CA6F
0x18007cbc3  mov     rax, [rcx]
0x18007cbc6  mov     rax, [rax+10h]
0x18007cbca  jmp     loc_18007CA6A
0x18007cbcf  add     rdi, 8
0x18007cbd3  mov     rcx, rdi
0x18007cbd6  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007cbdb  mov     r8, [rbp+var_20]; wchar_t *
0x18007cbdf  lea     rcx, ?vCbsOfflineUtil@@3VCbsOfflineUtil@@A; this
0x18007cbe6  mov     r9, rax; struct ICbsSession **
0x18007cbe9  mov     edx, 1; int
0x18007cbee  call    ?CbsCreateOfflineSessionFromStackInImage@CbsOfflineUtil@@UEAAJHPEB_WPEAPEAUICbsSession@@@Z; CbsOfflineUtil::CbsCreateOfflineSessionFromStackInImage(int,wchar_t const *,ICbsSession * *)
0x18007cbf3  mov     ebx, eax
0x18007cbf5  test    eax, eax
0x18007cbf7  jns     short loc_18007CC00
0x18007cbf9  mov     edx, 59h ; 'Y'
0x18007cbfe  jmp     short loc_18007CB9A
0x18007cc00  lea     rcx, [rbp+var_20]
0x18007cc04  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18007cc09  mov     rdi, [rdi]
0x18007cc0c  lea     rcx, [rbp+var_18]
0x18007cc10  mov     rax, [rdi]
0x18007cc13  mov     rbx, [rax]
0x18007cc16  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007cc1b  mov     r8, rax
0x18007cc1e  lea     rdx, _GUID_f112757a_565b_4260_bd05_9fa34417349a
0x18007cc25  mov     rax, rbx
0x18007cc28  mov     rcx, rdi
0x18007cc2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cc30  mov     ebx, eax
0x18007cc32  test    eax, eax
0x18007cc34  jns     short loc_18007CC40
0x18007cc36  mov     edx, 84h
0x18007cc3b  jmp     loc_18007CA47
0x18007cc40  test    r15, r15
0x18007cc43  jz      short loc_18007CC6B
0x18007cc45  mov     rcx, [rbp+var_18]
0x18007cc49  mov     rdx, r15
0x18007cc4c  mov     rax, [rcx]
0x18007cc4f  mov     rax, [rax+80h]
0x18007cc56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cc5b  mov     ebx, eax
0x18007cc5d  test    eax, eax
0x18007cc5f  jns     short loc_18007CC6B
0x18007cc61  mov     edx, 88h
0x18007cc66  jmp     loc_18007CA47
0x18007cc6b  mov     rcx, [rbp+var_18]
0x18007cc6f  lea     r8, aUninstallclien; "UninstallClient"
0x18007cc76  mov     qword ptr [rsp+60h+dwImpLevel], 0
0x18007cc7f  xor     r9d, r9d
0x18007cc82  mov     edx, 1000000h
0x18007cc87  mov     [rsp+60h+ppv], r14
0x18007cc8c  mov     rax, [rcx]
0x18007cc8f  mov     rax, [rax+98h]
0x18007cc96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cc9b  mov     ebx, eax
0x18007cc9d  test    eax, eax
0x18007cc9f  jns     short loc_18007CCAB
0x18007cca1  mov     edx, 8Bh
0x18007cca6  jmp     loc_18007CA47
0x18007ccab  mov     rcx, [rbp+var_18]
0x18007ccaf  mov     edx, 4
0x18007ccb4  mov     rax, [rcx]
0x18007ccb7  mov     rax, [rax+0B8h]
0x18007ccbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ccc3  mov     ebx, eax
0x18007ccc5  test    eax, eax
0x18007ccc7  jns     short loc_18007CCD3
0x18007ccc9  mov     edx, 8Fh
0x18007ccce  jmp     loc_18007CA47
0x18007ccd3  mov     rcx, [rbp+var_18]
0x18007ccd7  test    rcx, rcx
0x18007ccda  jz      short loc_18007CCE8
0x18007ccdc  mov     rax, [rcx]
0x18007ccdf  mov     rax, [rax+10h]
0x18007cce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cce8  xor     eax, eax
0x18007ccea  mov     rcx, [rbp+var_10]
0x18007ccee  xor     rcx, rsp; StackCookie
0x18007ccf1  call    __security_check_cookie
0x18007ccf6  mov     rbx, [rsp+60h+arg_8]
0x18007ccfe  add     rsp, 60h
0x18007cd02  pop     r15
0x18007cd04  pop     r14
0x18007cd06  pop     rdi
0x18007cd07  pop     rsi
0x18007cd08  pop     rbp
0x18007cd09  retn
0x18007cd0b  mov     ecx, 0C00000E5h; int
0x18007cd10  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
