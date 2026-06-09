# BINDING_OBJECT_EXTENSION::ExecuteVerb(ushort const *,ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x18002c540`
- end: `0x18002c8f7`
- name: `?ExecuteVerb@BINDING_OBJECT_EXTENSION@@UEAAJPEBG00PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `951`
- prototype: `int(BINDING_OBJECT_EXTENSION *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18002c0a8`
- `0x18002c540`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002c5af`
- `msvcrt!_wcsicmp` at `0x18002c5af`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c6e4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c6e4`
- `OLEAUT32!__imp_VariantInit` at `0x18002c76d`
- `OLEAUT32!__imp_VariantInit` at `0x18002c832`
- `OLEAUT32!__imp_VariantInit` at `0x18002c76d`
- `OLEAUT32!__imp_VariantInit` at `0x18002c832`

## pseudocode

```c
__int64 __fastcall BINDING_OBJECT_EXTENSION::ExecuteVerb(
        BINDING_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IExtensionContext *a5,
        struct ICommandParameterList *a6,
        struct ICommandObjectList *a7)
{
  struct IAppHostElement *v7; // rcx
  struct ICommandParameterList *v8; // rdi
  HRESULT v9; // ebx
  unsigned int v11; // eax
  __int64 v12; // rax
  unsigned int v13; // eax
  bool v14; // cf
  __int64 v15; // rax
  __int64 (__fastcall *v16)(__int64 *, VARIANTARG *, struct IAppHostElement **); // rax
  BINDING_OBJECT_EXTENSION *v17; // rcx
  struct IAppHostElement *v18; // [rsp+30h] [rbp-89h] BYREF
  __int64 *v19; // [rsp+38h] [rbp-81h] BYREF
  __int64 v20; // [rsp+40h] [rbp-79h] BYREF
  __int64 v21; // [rsp+48h] [rbp-71h] BYREF
  unsigned int v22; // [rsp+50h] [rbp-69h] BYREF
  __int64 *v23; // [rsp+58h] [rbp-61h] BYREF
  __int64 v24; // [rsp+60h] [rbp-59h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int16 *v26; // [rsp+70h] [rbp-49h] BYREF
  unsigned __int16 *v27; // [rsp+78h] [rbp-41h] BYREF
  VARIANTARG v28; // [rsp+80h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-21h] BYREF
  VARIANTARG v30[2]; // [rsp+B0h] [rbp-9h] BYREF
  unsigned int v31; // [rsp+108h] [rbp+4Fh] BYREF

  ppv = 0;
  v7 = 0;
  v18 = 0;
  v24 = 0;
  v23 = 0;
  v21 = 0;
  v20 = 0;
  v19 = 0;
  v31 = 0;
  v22 = 0;
  v27 = 0;
  v26 = 0;
  if ( !a2 )
    goto LABEL_9;
  if ( !a3 )
    goto LABEL_9;
  if ( !a4 )
    goto LABEL_9;
  if ( !a5 )
    goto LABEL_9;
  v8 = a6;
  if ( !a6 || !a7 )
    goto LABEL_9;
  if ( _wcsicmp(a3, L"RENEW") )
  {
    v7 = v18;
LABEL_9:
    v9 = -2147024809;
    goto LABEL_10;
  }
  v9 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const wchar_t *, unsigned __int16 **))(*(_QWORD *)v8 + 40LL))(
         v8,
         L"oldCert",
         &v27);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const wchar_t *, unsigned __int16 **))(*(_QWORD *)v8 + 40LL))(
           v8,
           L"newCert",
           &v26);
    if ( v9 >= 0 )
    {
      v9 = CoCreateInstance(&CLSID_AppHostWritableAdminManager, 0, 1u, &GUID_fa7660f6_7b3f_4237_a8bf_ed0ad0dcbbd9, &ppv);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 24LL))(
               ppv,
               L"system.applicationHost/sites",
               L"MACHINE/WEBROOT/APPHOST",
               &v24);
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v24 + 32LL))(v24, &v23);
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v23 + 24))(v23, &v31);
            if ( v9 >= 0 )
            {
              memset(&pvarg, 0, sizeof(pvarg));
              VariantInit(&pvarg);
              v11 = 0;
              pvarg.vt = 19;
              while ( 1 )
              {
                pvarg.lVal = v11;
                if ( v11 >= v31 )
                  break;
                v12 = *v23;
                v30[0] = pvarg;
                v9 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, __int64 *))(v12 + 32))(v23, v30, &v21);
                if ( v9 < 0 )
                  break;
                v9 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v21 + 80LL))(
                       v21,
                       L"bindings",
                       &v20);
                if ( v9 < 0 )
                  break;
                v9 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v20 + 32LL))(v20, &v19);
                if ( v9 < 0 )
                  break;
                v9 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v19 + 24))(v19, &v22);
                if ( v9 < 0 )
                  break;
                memset(&v28, 0, sizeof(v28));
                VariantInit(&v28);
                v13 = 0;
                v28.vt = 19;
                while ( 1 )
                {
                  v14 = v13 < v22;
                  v28.lVal = v13;
                  v15 = *v19;
                  if ( !v14 )
                    break;
                  v16 = *(__int64 (__fastcall **)(__int64 *, VARIANTARG *, struct IAppHostElement **))(v15 + 32);
                  v30[0] = v28;
                  v9 = v16(v19, v30, &v18);
                  if ( v9 < 0 )
                    goto LABEL_43;
                  v9 = BINDING_OBJECT_EXTENSION::CheckAndUpdateBinding(v17, v18, v27, v26);
                  if ( v9 < 0 )
                    goto LABEL_43;
                  ((void (__fastcall *)(struct IAppHostElement *))v18->lpVtbl->Release)(v18);
                  v13 = v28.lVal + 1;
                  v18 = 0;
                }
                (*(void (**)(void))(v15 + 16))();
                v19 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
                v20 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
                v11 = pvarg.lVal + 1;
                v21 = 0;
              }
            }
          }
        }
      }
    }
  }
LABEL_43:
  v7 = v18;
LABEL_10:
  if ( v7 )
  {
    ((void (__fastcall *)(struct IAppHostElement *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))v7->lpVtbl->Release)(
      v7,
      a2,
      a3,
      a4);
    v18 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(*v19 + 16))(
      v19,
      a2,
      a3,
      a4);
    v19 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v20 + 16LL))(
      v20,
      a2,
      a3,
      a4);
    v20 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v21 + 16LL))(
      v21,
      a2,
      a3,
      a4);
    v21 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(*v23 + 16))(
      v23,
      a2,
      a3,
      a4);
    v23 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v24 + 16LL))(
      v24,
      a2,
      a3,
      a4);
    v24 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)ppv + 16LL))(
      ppv,
      a2,
      a3,
      a4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002c540  push    rbp
0x18002c542  push    rbx
0x18002c543  push    rsi
0x18002c544  push    rdi
0x18002c545  lea     rbp, [rsp-1Fh]
0x18002c54a  sub     rsp, 0D8h
0x18002c551  xor     esi, esi
0x18002c553  mov     [rbp+37h+var_88], rsi
0x18002c557  mov     ecx, esi
0x18002c559  mov     [rsp+0F0h+var_C0], rcx
0x18002c55e  mov     [rbp+37h+var_90], rsi
0x18002c562  mov     [rbp+37h+var_98], rsi
0x18002c566  mov     [rbp+37h+var_A8], rsi
0x18002c56a  mov     [rbp+37h+var_B0], rsi
0x18002c56e  mov     [rsp+0F0h+var_B8], rsi
0x18002c573  mov     [rbp+37h+arg_8], esi
0x18002c576  mov     [rbp+37h+var_A0], esi
0x18002c579  mov     [rbp+37h+var_78], rsi
0x18002c57d  mov     [rbp+37h+var_80], rsi
0x18002c581  test    rdx, rdx
0x18002c584  jz      short loc_18002C5C2
0x18002c586  test    r8, r8
0x18002c589  jz      short loc_18002C5C2
0x18002c58b  test    r9, r9
0x18002c58e  jz      short loc_18002C5C2
0x18002c590  cmp     [rbp+37h+arg_20], rsi
0x18002c594  jz      short loc_18002C5C2
0x18002c596  mov     rdi, [rbp+37h+arg_28]
0x18002c59a  test    rdi, rdi
0x18002c59d  jz      short loc_18002C5C2
0x18002c59f  cmp     [rbp+37h+arg_30], rsi
0x18002c5a3  jz      short loc_18002C5C2
0x18002c5a5  lea     rdx, aRenew_0; "RENEW"
0x18002c5ac  mov     rcx, r8; String1
0x18002c5af  call    cs:__imp__wcsicmp
0x18002c5b5  test    eax, eax
0x18002c5b7  jz      loc_18002C67F
0x18002c5bd  mov     rcx, [rsp+0F0h+var_C0]
0x18002c5c2  mov     ebx, 80070057h
0x18002c5c7  test    rcx, rcx
0x18002c5ca  jz      short loc_18002C5DD
0x18002c5cc  mov     rax, [rcx]
0x18002c5cf  mov     rax, [rax+10h]
0x18002c5d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5d8  mov     [rsp+0F0h+var_C0], rsi
0x18002c5dd  mov     rcx, [rsp+0F0h+var_B8]
0x18002c5e2  test    rcx, rcx
0x18002c5e5  jz      short loc_18002C5F8
0x18002c5e7  mov     rax, [rcx]
0x18002c5ea  mov     rax, [rax+10h]
0x18002c5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5f3  mov     [rsp+0F0h+var_B8], rsi
0x18002c5f8  mov     rcx, [rbp+37h+var_B0]
0x18002c5fc  test    rcx, rcx
0x18002c5ff  jz      short loc_18002C611
0x18002c601  mov     rax, [rcx]
0x18002c604  mov     rax, [rax+10h]
0x18002c608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c60d  mov     [rbp+37h+var_B0], rsi
0x18002c611  mov     rcx, [rbp+37h+var_A8]
0x18002c615  test    rcx, rcx
0x18002c618  jz      short loc_18002C62A
0x18002c61a  mov     rax, [rcx]
0x18002c61d  mov     rax, [rax+10h]
0x18002c621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c626  mov     [rbp+37h+var_A8], rsi
0x18002c62a  mov     rcx, [rbp+37h+var_98]
0x18002c62e  test    rcx, rcx
0x18002c631  jz      short loc_18002C643
0x18002c633  mov     rax, [rcx]
0x18002c636  mov     rax, [rax+10h]
0x18002c63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c63f  mov     [rbp+37h+var_98], rsi
0x18002c643  mov     rcx, [rbp+37h+var_90]
0x18002c647  test    rcx, rcx
0x18002c64a  jz      short loc_18002C65C
0x18002c64c  mov     rax, [rcx]
0x18002c64f  mov     rax, [rax+10h]
0x18002c653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c658  mov     [rbp+37h+var_90], rsi
0x18002c65c  mov     rcx, [rbp+37h+var_88]
0x18002c660  test    rcx, rcx
0x18002c663  jz      short loc_18002C671
0x18002c665  mov     rax, [rcx]
0x18002c668  mov     rax, [rax+10h]
0x18002c66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c671  mov     eax, ebx
0x18002c673  add     rsp, 0D8h
0x18002c67a  pop     rdi
0x18002c67b  pop     rsi
0x18002c67c  pop     rbx
0x18002c67d  pop     rbp
0x18002c67e  retn
0x18002c67f  mov     rax, [rdi]
0x18002c682  lea     r8, [rbp+37h+var_78]
0x18002c686  lea     rdx, aOldcert; "oldCert"
0x18002c68d  mov     rcx, rdi
0x18002c690  mov     rax, [rax+28h]
0x18002c694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c699  mov     ebx, eax
0x18002c69b  test    eax, eax
0x18002c69d  js      loc_18002C8ED
0x18002c6a3  mov     rax, [rdi]
0x18002c6a6  lea     r8, [rbp+37h+var_80]
0x18002c6aa  lea     rdx, aNewcert; "newCert"
0x18002c6b1  mov     rcx, rdi
0x18002c6b4  mov     rax, [rax+28h]
0x18002c6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6bd  mov     ebx, eax
0x18002c6bf  test    eax, eax
0x18002c6c1  js      loc_18002C8ED
0x18002c6c7  xor     edx, edx; pUnkOuter
0x18002c6c9  lea     rax, [rbp+37h+var_88]
0x18002c6cd  lea     r9, _GUID_fa7660f6_7b3f_4237_a8bf_ed0ad0dcbbd9; riid
0x18002c6d4  mov     [rsp+0F0h+ppv], rax; ppv
0x18002c6d9  lea     rcx, CLSID_AppHostWritableAdminManager; rclsid
0x18002c6e0  lea     r8d, [rdx+1]; dwClsContext
0x18002c6e4  call    cs:__imp_CoCreateInstance
0x18002c6ea  mov     ebx, eax
0x18002c6ec  test    eax, eax
0x18002c6ee  js      loc_18002C8ED
0x18002c6f4  mov     rcx, [rbp+37h+var_88]
0x18002c6f8  lea     r9, [rbp+37h+var_90]
0x18002c6fc  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18002c703  lea     rdx, aSystemApplicat_2; "system.applicationHost/sites"
0x18002c70a  mov     rax, [rcx]
0x18002c70d  mov     rax, [rax+18h]
0x18002c711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c716  mov     ebx, eax
0x18002c718  test    eax, eax
0x18002c71a  js      loc_18002C8ED
0x18002c720  mov     rcx, [rbp+37h+var_90]
0x18002c724  lea     rdx, [rbp+37h+var_98]
0x18002c728  mov     rax, [rcx]
0x18002c72b  mov     rax, [rax+20h]
0x18002c72f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c734  mov     ebx, eax
0x18002c736  test    eax, eax
0x18002c738  js      loc_18002C8ED
0x18002c73e  mov     rcx, [rbp+37h+var_98]
0x18002c742  lea     rdx, [rbp+37h+arg_8]
0x18002c746  mov     rax, [rcx]
0x18002c749  mov     rax, [rax+18h]
0x18002c74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c752  mov     ebx, eax
0x18002c754  test    eax, eax
0x18002c756  js      loc_18002C8ED
0x18002c75c  xorps   xmm0, xmm0
0x18002c75f  lea     rcx, [rbp+37h+pvarg]; pvarg
0x18002c763  xor     eax, eax
0x18002c765  movups  xmmword ptr [rbp+37h+pvarg], xmm0
0x18002c769  mov     qword ptr [rbp+37h+pvarg+10h], rax
0x18002c76d  call    cs:__imp_VariantInit
0x18002c773  mov     edi, 13h
0x18002c778  mov     eax, esi
0x18002c77a  mov     word ptr [rbp+37h+pvarg], di
0x18002c77e  mov     dword ptr [rbp+37h+pvarg+8], eax
0x18002c781  cmp     eax, [rbp+37h+arg_8]
0x18002c784  jnb     loc_18002C8ED
0x18002c78a  mov     rcx, [rbp+37h+var_98]
0x18002c78e  lea     r8, [rbp+37h+var_A8]
0x18002c792  movups  xmm0, xmmword ptr [rbp+37h+pvarg]
0x18002c796  lea     rdx, [rbp+37h+var_40]
0x18002c79a  movsd   xmm1, qword ptr [rbp+37h+pvarg+10h]
0x18002c79f  mov     rax, [rcx]
0x18002c7a2  movaps  [rbp+37h+var_40], xmm0
0x18002c7a6  movsd   [rbp+37h+var_30], xmm1
0x18002c7ab  mov     rax, [rax+20h]
0x18002c7af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7b4  mov     ebx, eax
0x18002c7b6  test    eax, eax
0x18002c7b8  js      loc_18002C8ED
0x18002c7be  mov     rcx, [rbp+37h+var_A8]
0x18002c7c2  lea     r8, [rbp+37h+var_B0]
0x18002c7c6  lea     rdx, aBindings_0; "bindings"
0x18002c7cd  mov     rax, [rcx]
0x18002c7d0  mov     rax, [rax+50h]
0x18002c7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7d9  mov     ebx, eax
0x18002c7db  test    eax, eax
0x18002c7dd  js      loc_18002C8ED
0x18002c7e3  mov     rcx, [rbp+37h+var_B0]
0x18002c7e7  lea     rdx, [rsp+0F0h+var_B8]
0x18002c7ec  mov     rax, [rcx]
0x18002c7ef  mov     rax, [rax+20h]
0x18002c7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7f8  mov     ebx, eax
0x18002c7fa  test    eax, eax
0x18002c7fc  js      loc_18002C8ED
0x18002c802  mov     rcx, [rsp+0F0h+var_B8]
0x18002c807  lea     rdx, [rbp+37h+var_A0]
0x18002c80b  mov     rax, [rcx]
0x18002c80e  mov     rax, [rax+18h]
0x18002c812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c817  mov     ebx, eax
0x18002c819  test    eax, eax
0x18002c81b  js      loc_18002C8ED
0x18002c821  xorps   xmm0, xmm0
0x18002c824  lea     rcx, [rbp+37h+var_70]; pvarg
0x18002c828  xor     eax, eax
0x18002c82a  movups  xmmword ptr [rbp+37h+var_70], xmm0
0x18002c82e  mov     qword ptr [rbp+37h+var_70+10h], rax
0x18002c832  call    cs:__imp_VariantInit
0x18002c838  mov     eax, esi
0x18002c83a  mov     word ptr [rbp+37h+var_70], di
0x18002c83e  mov     rcx, [rsp+0F0h+var_B8]
0x18002c843  cmp     eax, [rbp+37h+var_A0]
0x18002c846  mov     dword ptr [rbp+37h+var_70+8], eax
0x18002c849  mov     rax, [rcx]
0x18002c84c  jnb     short loc_18002C8AD
0x18002c84e  movups  xmm0, xmmword ptr [rbp+37h+var_70]
0x18002c852  lea     r8, [rsp+0F0h+var_C0]
0x18002c857  mov     rax, [rax+20h]
0x18002c85b  movsd   xmm1, qword ptr [rbp+37h+var_70+10h]
0x18002c860  lea     rdx, [rbp+37h+var_40]
0x18002c864  movaps  [rbp+37h+var_40], xmm0
0x18002c868  movsd   [rbp+37h+var_30], xmm1
0x18002c86d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c872  mov     ebx, eax
0x18002c874  test    eax, eax
0x18002c876  js      short loc_18002C8ED
0x18002c878  mov     r9, [rbp+37h+var_80]; unsigned __int16 *
0x18002c87c  mov     r8, [rbp+37h+var_78]; unsigned __int16 *
0x18002c880  mov     rdx, [rsp+0F0h+var_C0]; struct IAppHostElement *
0x18002c885  call    ?CheckAndUpdateBinding@BINDING_OBJECT_EXTENSION@@AEAAJPEAUIAppHostElement@@PEBG1@Z; BINDING_OBJECT_EXTENSION::CheckAndUpdateBinding(IAppHostElement *,ushort const *,ushort const *)
0x18002c88a  mov     ebx, eax
0x18002c88c  test    eax, eax
0x18002c88e  js      short loc_18002C8ED
0x18002c890  mov     rcx, [rsp+0F0h+var_C0]
0x18002c895  mov     rax, [rcx]
0x18002c898  mov     rax, [rax+10h]
0x18002c89c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8a1  mov     eax, dword ptr [rbp+37h+var_70+8]
0x18002c8a4  inc     eax
0x18002c8a6  mov     [rsp+0F0h+var_C0], rsi
0x18002c8ab  jmp     short loc_18002C83E
0x18002c8ad  mov     rax, [rax+10h]
0x18002c8b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8b6  mov     rcx, [rbp+37h+var_B0]
0x18002c8ba  mov     [rsp+0F0h+var_B8], rsi
0x18002c8bf  mov     rax, [rcx]
0x18002c8c2  mov     rax, [rax+10h]
0x18002c8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8cb  mov     rcx, [rbp+37h+var_A8]
0x18002c8cf  mov     [rbp+37h+var_B0], rsi
0x18002c8d3  mov     rax, [rcx]
0x18002c8d6  mov     rax, [rax+10h]
0x18002c8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8df  mov     eax, dword ptr [rbp+37h+pvarg+8]
0x18002c8e2  inc     eax
0x18002c8e4  mov     [rbp+37h+var_A8], rsi
0x18002c8e8  jmp     loc_18002C77E
0x18002c8ed  mov     rcx, [rsp+0F0h+var_C0]
0x18002c8f2  jmp     loc_18002C5C7
```
