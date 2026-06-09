# CResultSetFactory::_AdjustShape(IResultShape *,int,_tagpropertykey const &,PROVIDER_CAPABILITIES,ICondition *,int *,IResultShape * *,IResultShape * *)

- ea: `0x18003986c`
- end: `0x180039ea1`
- name: `?_AdjustShape@CResultSetFactory@@AEAAJPEAUIResultShape@@HAEBU_tagpropertykey@@W4PROVIDER_CAPABILITIES@@PEAUICondition@@PEAHPEAPEAU2@5@Z`
- size: `1589`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003986c`
- `0x180062e9c`
- `0x1800a5b40`
- `0x1800af670`

## callees

- `0x18003986c`
- `0x180039eb0`
- `0x18003a490`
- `0x180063a68`
- `0x180071dc0`
- `0x1800afaa8`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x180039bf7`
- `SHCORE!IUnknown_Set` at `0x180039d15`
- `SHCORE!IUnknown_Set` at `0x180039bf7`
- `SHCORE!IUnknown_Set` at `0x180039d15`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180039a78`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180039b77`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180039a78`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180039b77`
- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x180039991`
- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x180039991`

## pseudocode

```c
__int64 __fastcall CResultSetFactory::_AdjustShape(
        __int64 a1,
        struct IResultShape *a2,
        unsigned int a3,
        const struct _tagpropertykey *a4,
        int a5,
        struct ICondition *a6,
        struct _GUID *a7,
        IUnknown **a8,
        IUnknown **a9)
{
  __int64 v13; // rax
  int (__fastcall *v14)(struct IResultShape *, struct _tagpropertykey *, GUID *, struct IResultShape **); // rax
  HRESULT v15; // ebx
  __int64 v16; // rax
  int v17; // edi
  __int64 v18; // rax
  struct IPropertyKeyStore *v19; // r15
  __int64 v20; // r13
  int v21; // eax
  int v22; // edx
  __int64 v23; // r14
  void *v24; // r15
  struct IPropertyKeyStore *v25; // rcx
  IUnknown *v26; // rcx
  __int64 v27; // rcx
  struct IUnknown *v28; // rcx
  IUnknown *v30; // rdx
  struct IConditionVtbl *lpVtbl; // rax
  CResultSetFactory *v32; // rcx
  void **ppv; // [rsp+20h] [rbp-D1h]
  const struct _GUID *v34; // [rsp+30h] [rbp-C1h]
  void *v35; // [rsp+50h] [rbp-A1h] BYREF
  struct IPropertyKeyStore *v36; // [rsp+58h] [rbp-99h] BYREF
  struct IUnknown *v37; // [rsp+60h] [rbp-91h] BYREF
  __int64 v38; // [rsp+68h] [rbp-89h]
  void *v39; // [rsp+70h] [rbp-81h] BYREF
  IUnknown *v40; // [rsp+78h] [rbp-79h]
  IUnknown *punk; // [rsp+80h] [rbp-71h] BYREF
  __int64 v42; // [rsp+88h] [rbp-69h] BYREF
  void *v43[2]; // [rsp+90h] [rbp-61h] BYREF
  struct IResultShape *v44; // [rsp+A0h] [rbp-51h] BYREF
  struct _GUID *v45; // [rsp+A8h] [rbp-49h]
  IUnknown **ppunk; // [rsp+B0h] [rbp-41h]
  struct _tagpropertykey v47; // [rsp+B8h] [rbp-39h] BYREF
  struct _tagpropertykey v48; // [rsp+D0h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+47h]

  a7->Data1 = 0;
  v45 = a7;
  *a8 = 0;
  *a9 = 0;
  v13 = *(_QWORD *)a2;
  ppunk = a9;
  v40 = 0;
  v38 = 0;
  v14 = *(int (__fastcall **)(struct IResultShape *, struct _tagpropertykey *, GUID *, struct IResultShape **))(v13 + 56);
  v44 = 0;
  v37 = 0;
  memset(&v47, 0, sizeof(v47));
  if ( v14(a2, &v47, &GUID_6bc63938_8254_4965_9680_565933185060, &v44) < 0 )
    goto LABEL_2;
  (*(void (__fastcall **)(struct IResultShape *, GUID *, struct IUnknown **))(*(_QWORD *)a2 + 64LL))(
    a2,
    &GUID_00000000_0000_0000_c000_000000000046,
    &v37);
  if ( a6 )
  {
    if ( v37 )
    {
      lpVtbl = a6->lpVtbl;
      *(_OWORD *)v43 = 0;
      if ( ((int (__fastcall *)(struct ICondition *, GUID *, void **))lpVtbl->QueryInterface)(
             a6,
             &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
             v43) >= 0 )
      {
        CResultSetFactory::_AdjustData(v32, &v47, (const struct CResultSetFactory::CONDITIONDATA *)v43, v37);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v43[0] + 16LL))(v43[0]);
      }
    }
  }
  v34 = v45;
  LODWORD(ppv) = a5;
  v15 = CResultSetFactory::_AdjustShape(a1, v44, a3, &v47);
  (*(void (__fastcall **)(struct IResultShape *))(*(_QWORD *)v44 + 16LL))(v44);
  if ( v15 >= 0 )
  {
LABEL_2:
    v43[0] = 0;
    v15 = CResultSetFactory::_EnsureRequiredColumns((CResultSetFactory *)v43, a2, a3, a4, a6, v38 != 0, v34, v43);
    if ( v15 < 0 )
    {
LABEL_30:
      v26 = v40;
      v40 = 0;
      if ( v26 )
        ((void (__fastcall *)(IUnknown *))v26->lpVtbl->Release)(v26);
      v27 = v38;
      v38 = 0;
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      goto LABEL_34;
    }
    v16 = *(_QWORD *)a2;
    v42 = 0;
    v35 = 0;
    v15 = (*(__int64 (__fastcall **)(struct IResultShape *, GUID *, void **))(v16 + 32))(
            a2,
            &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
            &v35);
    if ( v15 < 0 )
      goto LABEL_59;
    v36 = 0;
    v15 = PSCreatePropertyKeyStore(0, 0, &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b, &v36);
    if ( v15 >= 0 )
    {
      LODWORD(v39) = 0;
      v15 = (*(__int64 (__fastcall **)(void *, void **))(*(_QWORD *)v35 + 24LL))(v35, &v39);
      v17 = 0;
      if ( v15 >= 0 )
      {
        while ( v17 < (int)v39 )
        {
          memset(&v48, 0, sizeof(v48));
          v15 = (*(__int64 (__fastcall **)(void *, _QWORD, struct _tagpropertykey *))(*(_QWORD *)v35 + 32LL))(
                  v35,
                  (unsigned int)v17,
                  &v48);
          if ( v15 >= 0 )
            v15 = AddPropertyAndDependencies(v36, &v48);
          ++v17;
          if ( v15 < 0 )
            goto LABEL_8;
        }
        v15 = (**(__int64 (__fastcall ***)(struct IPropertyKeyStore *, GUID *, __int64 *))v36)(
                v36,
                &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
                &v42);
      }
LABEL_8:
      (*(void (__fastcall **)(struct IPropertyKeyStore *))(*(_QWORD *)v36 + 16LL))(v36);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v35 + 16LL))(v35);
    if ( v15 < 0 )
    {
LABEL_59:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26EA,
        (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
        (const char *)(unsigned int)v15,
        (int)ppv);
LABEL_29:
      (*(void (__fastcall **)(void *))(*(_QWORD *)v43[0] + 16LL))(v43[0]);
      goto LABEL_30;
    }
    v18 = *(_QWORD *)a2;
    v36 = 0;
    (*(void (__fastcall **)(struct IResultShape *, GUID *, struct IPropertyKeyStore **))(v18 + 80))(
      a2,
      &GUID_6dfc60fb_f2e9_459b_beb5_288f1a7c7d54,
      &v36);
    v19 = v36;
    v20 = v42;
    v39 = v43[0];
    punk = 0;
    v35 = 0;
    v15 = SHCoCreateInstance(0, &CLSID_ResultShape, 0, &GUID_42c9f529_ac7b_45d3_a320_c2f23f250b94, &v35);
    if ( v15 < 0 )
      goto LABEL_58;
    ppv = (void **)&v47;
    v15 = (*(__int64 (__fastcall **)(void *, void *, __int64, struct IPropertyKeyStore *))(*(_QWORD *)v35 + 24LL))(
            v35,
            v39,
            v20,
            v19);
    if ( v15 >= 0 )
      v15 = (**(__int64 (__fastcall ***)(void *, GUID *, IUnknown **))v35)(
              v35,
              &GUID_6bc63938_8254_4965_9680_565933185060,
              &punk);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v35 + 16LL))(v35);
    if ( v15 < 0 )
    {
LABEL_58:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2704,
        (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
        (const char *)(unsigned int)v15,
        (int)ppv);
      goto LABEL_26;
    }
    if ( !v36 || (v21 = a5 & 1, (a5 & 1) != 0) )
    {
      if ( !v38 || (a5 & 2) != 0 )
      {
        v30 = punk;
        goto LABEL_45;
      }
      v22 = 0;
      v21 = a5 & 1;
    }
    else
    {
      v22 = a5 & 2;
    }
    if ( !v38 || v22 )
    {
      if ( v36 && !v21 )
      {
        v23 = v42;
        v24 = v43[0];
        v45->Data1 = 1;
        *a8 = 0;
        v35 = 0;
        v15 = SHCoCreateInstance(0, &CLSID_ResultShape, 0, &GUID_42c9f529_ac7b_45d3_a320_c2f23f250b94, &v35);
        if ( v15 < 0 )
          goto LABEL_48;
        ppv = (void **)&v47;
        v15 = (*(__int64 (__fastcall **)(void *, void *, __int64, _QWORD))(*(_QWORD *)v35 + 24LL))(v35, v24, v23, 0);
        if ( v15 >= 0 )
          v15 = (**(__int64 (__fastcall ***)(void *, GUID *, IUnknown **))v35)(
                  v35,
                  &GUID_6bc63938_8254_4965_9680_565933185060,
                  a8);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v35 + 16LL))(v35);
        if ( v15 < 0 )
        {
LABEL_48:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2704,
            (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
            (const char *)(unsigned int)v15,
            (int)ppv);
          goto LABEL_25;
        }
      }
LABEL_24:
      IUnknown_Set(ppunk, punk);
LABEL_25:
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
LABEL_26:
      v25 = v36;
      v36 = 0;
      if ( v25 )
        (*(void (__fastcall **)(struct IPropertyKeyStore *))(*(_QWORD *)v25 + 16LL))(v25);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      goto LABEL_29;
    }
    v30 = v40;
    v45->Data1 = 1;
LABEL_45:
    IUnknown_Set(a8, v30);
    goto LABEL_24;
  }
LABEL_34:
  v28 = v37;
  v37 = 0;
  if ( v28 )
    ((void (__fastcall *)(struct IUnknown *))v28->lpVtbl->Release)(v28);
  if ( v15 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2850,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)v15,
      (int)ppv);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18003986c  push    rbp
0x18003986e  push    rbx
0x18003986f  push    rsi
0x180039870  push    rdi
0x180039871  push    r12
0x180039873  push    r13
0x180039875  push    r14
0x180039877  push    r15
0x180039879  lea     rbp, [rsp-7]
0x18003987e  sub     rsp, 0F8h
0x180039885  mov     rax, cs:__security_cookie
0x18003988c  xor     rax, rsp
0x18003988f  mov     [rbp+3Fh+var_48], rax
0x180039893  mov     rax, [rbp+3Fh+arg_30]
0x180039897  mov     rsi, rdx
0x18003989a  mov     r12, [rbp+3Fh+arg_38]
0x1800398a1  xor     edx, edx
0x1800398a3  mov     rdi, [rbp+3Fh+arg_28]
0x1800398a7  mov     rbx, rcx
0x1800398aa  mov     rcx, [rbp+3Fh+arg_40]
0x1800398b1  mov     r13, r9
0x1800398b4  mov     [rax], edx
0x1800398b6  lea     r9, [rbp+3Fh+var_90]
0x1800398ba  mov     [rbp+3Fh+var_88], rax
0x1800398be  mov     r15d, r8d
0x1800398c1  xor     eax, eax
0x1800398c3  mov     [r12], rdx
0x1800398c7  mov     [rcx], rdx
0x1800398ca  lea     r8, _GUID_6bc63938_8254_4965_9680_565933185060
0x1800398d1  mov     [rbp+3Fh+var_78.pid], eax
0x1800398d4  xorps   xmm0, xmm0
0x1800398d7  mov     rax, [rsi]
0x1800398da  mov     [rbp+3Fh+ppunk], rcx
0x1800398de  mov     rcx, rsi
0x1800398e1  mov     [rbp+3Fh+var_B8], rdx
0x1800398e5  mov     [rsp+130h+var_C8], rdx
0x1800398ea  mov     rax, [rax+38h]
0x1800398ee  mov     [rbp+3Fh+var_90], rdx
0x1800398f2  mov     [rsp+130h+var_D0], rdx
0x1800398f7  lea     rdx, [rbp+3Fh+var_78]
0x1800398fb  movups  xmmword ptr [rbp+3Fh+var_78.fmtid.Data1], xmm0
0x1800398ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039904  mov     r14d, [rbp+3Fh+arg_20]
0x180039908  test    eax, eax
0x18003990a  jns     loc_180039D5A
0x180039910  xor     eax, eax
0x180039912  mov     [rbp+3Fh+var_A0], 0
0x18003991a  cmp     [rsp+130h+var_C8], rax
0x18003991f  lea     rcx, [rbp+3Fh+var_A0]; this
0x180039923  mov     [rsp+130h+var_F8], rcx; void **
0x180039928  mov     r9, r13; struct _tagpropertykey *
0x18003992b  setnz   al
0x18003992e  mov     r8d, r15d; int
0x180039931  mov     [rsp+130h+var_108], eax; int
0x180039935  mov     rdx, rsi; struct IResultShape *
0x180039938  mov     [rsp+130h+ppv], rdi; int
0x18003993d  call    ?_EnsureRequiredColumns@CResultSetFactory@@AEAAJPEAUIResultShape@@HAEBU_tagpropertykey@@PEAUICondition@@HAEBU_GUID@@PEAPEAX@Z; CResultSetFactory::_EnsureRequiredColumns(IResultShape *,int,_tagpropertykey const &,ICondition *,int,_GUID const &,void * *)
0x180039942  xor     r13d, r13d
0x180039945  mov     ebx, eax
0x180039947  test    eax, eax
0x180039949  js      loc_180039C48
0x18003994f  mov     rax, [rsi]
0x180039952  lea     r15, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x180039959  lea     r8, [rsp+130h+var_E0]
0x18003995e  mov     [rbp+3Fh+var_A8], r13
0x180039962  mov     rdx, r15
0x180039965  mov     [rsp+130h+var_E0], r13
0x18003996a  mov     rcx, rsi
0x18003996d  mov     rax, [rax+20h]
0x180039971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039976  mov     ebx, eax
0x180039978  test    eax, eax
0x18003997a  js      loc_180039E67
0x180039980  lea     r9, [rsp+130h+var_D8]
0x180039985  mov     [rsp+130h+var_D8], r13
0x18003998a  mov     r8, r15
0x18003998d  xor     edx, edx
0x18003998f  xor     ecx, ecx
0x180039991  call    cs:__imp_PSCreatePropertyKeyStore
0x180039997  mov     ebx, eax
0x180039999  test    eax, eax
0x18003999b  js      short loc_1800399F5
0x18003999d  mov     rcx, [rsp+130h+var_E0]
0x1800399a2  lea     rdx, [rsp+130h+var_C0]
0x1800399a7  mov     dword ptr [rsp+130h+var_C0], r13d
0x1800399ac  mov     rax, [rcx]
0x1800399af  mov     rax, [rax+18h]
0x1800399b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399b8  mov     ebx, eax
0x1800399ba  mov     edi, r13d
0x1800399bd  test    eax, eax
0x1800399bf  js      short loc_1800399E4
0x1800399c1  cmp     edi, dword ptr [rsp+130h+var_C0]
0x1800399c5  jl      loc_180039CC1
0x1800399cb  mov     rcx, [rsp+130h+var_D8]
0x1800399d0  lea     r8, [rbp+3Fh+var_A8]
0x1800399d4  mov     rdx, r15
0x1800399d7  mov     rax, [rcx]
0x1800399da  mov     rax, [rax]
0x1800399dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399e2  mov     ebx, eax
0x1800399e4  mov     rcx, [rsp+130h+var_D8]
0x1800399e9  mov     rax, [rcx]
0x1800399ec  mov     rax, [rax+10h]
0x1800399f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399f5  mov     rcx, [rsp+130h+var_E0]
0x1800399fa  mov     rax, [rcx]
0x1800399fd  mov     rax, [rax+10h]
0x180039a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a06  test    ebx, ebx
0x180039a08  js      loc_180039E67
0x180039a0e  mov     rax, [rsi]
0x180039a11  lea     r8, [rsp+130h+var_D8]
0x180039a16  lea     rdx, _GUID_6dfc60fb_f2e9_459b_beb5_288f1a7c7d54
0x180039a1d  mov     [rsp+130h+var_D8], r13
0x180039a22  mov     rcx, rsi
0x180039a25  mov     rax, [rax+50h]
0x180039a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a2e  mov     rax, [rbp+3Fh+var_A0]
0x180039a32  lea     r9, _GUID_42c9f529_ac7b_45d3_a320_c2f23f250b94; riid
0x180039a39  mov     rdi, [rsp+130h+var_D0]
0x180039a3e  lea     rdx, CLSID_ResultShape; pclsid
0x180039a45  mov     rsi, [rsp+130h+var_C8]
0x180039a4a  xor     r8d, r8d; pUnkOuter
0x180039a4d  mov     r15, [rsp+130h+var_D8]
0x180039a52  xor     ecx, ecx; pszCLSID
0x180039a54  mov     r13, [rbp+3Fh+var_A8]
0x180039a58  mov     [rsp+130h+var_C0], rax
0x180039a5d  lea     rax, [rsp+130h+var_E0]
0x180039a62  mov     [rsp+130h+ppv], rax; int
0x180039a67  mov     [rbp+3Fh+punk], 0
0x180039a6f  mov     [rsp+130h+var_E0], 0
0x180039a78  call    cs:__imp_SHCoCreateInstance
0x180039a7e  mov     ebx, eax
0x180039a80  test    eax, eax
0x180039a82  js      loc_180039E47
0x180039a88  mov     rcx, [rsp+130h+var_E0]
0x180039a8d  lea     rdx, [rbp+3Fh+var_78]
0x180039a91  mov     [rsp+130h+var_100], rdi
0x180039a96  mov     r9, r15
0x180039a99  mov     qword ptr [rsp+130h+var_108], rsi
0x180039a9e  mov     r8, r13
0x180039aa1  mov     [rsp+130h+ppv], rdx
0x180039aa6  mov     rax, [rcx]
0x180039aa9  mov     rdx, [rsp+130h+var_C0]
0x180039aae  mov     rax, [rax+18h]
0x180039ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ab7  xor     r13d, r13d
0x180039aba  mov     ebx, eax
0x180039abc  test    eax, eax
0x180039abe  js      short loc_180039ADD
0x180039ac0  mov     rcx, [rsp+130h+var_E0]
0x180039ac5  lea     r8, [rbp+3Fh+punk]
0x180039ac9  lea     rdx, _GUID_6bc63938_8254_4965_9680_565933185060
0x180039ad0  mov     rax, [rcx]
0x180039ad3  mov     rax, [rax]
0x180039ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039adb  mov     ebx, eax
0x180039add  mov     rcx, [rsp+130h+var_E0]
0x180039ae2  mov     rax, [rcx]
0x180039ae5  mov     rax, [rax+10h]
0x180039ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039aee  test    ebx, ebx
0x180039af0  js      loc_180039E4A
0x180039af6  mov     r8, [rsp+130h+var_D8]
0x180039afb  mov     rcx, [rsp+130h+var_C8]
0x180039b00  test    r8, r8
0x180039b03  jz      loc_180039D09
0x180039b09  mov     eax, r14d
0x180039b0c  and     eax, 1
0x180039b0f  jnz     loc_180039D09
0x180039b15  and     r14d, 2
0x180039b19  mov     edx, r14d
0x180039b1c  test    rcx, rcx
0x180039b1f  jnz     loc_180039E2C
0x180039b25  test    r8, r8
0x180039b28  jz      loc_180039BEF
0x180039b2e  test    eax, eax
0x180039b30  jnz     loc_180039BEF
0x180039b36  mov     rax, [rbp+3Fh+var_88]
0x180039b3a  lea     r9, _GUID_42c9f529_ac7b_45d3_a320_c2f23f250b94; riid
0x180039b41  mov     rdi, [rsp+130h+var_D0]
0x180039b46  lea     rdx, CLSID_ResultShape; pclsid
0x180039b4d  mov     rsi, [rbp+3Fh+var_B8]
0x180039b51  xor     r8d, r8d; pUnkOuter
0x180039b54  mov     r14, [rbp+3Fh+var_A8]
0x180039b58  xor     ecx, ecx; pszCLSID
0x180039b5a  mov     r15, [rbp+3Fh+var_A0]
0x180039b5e  mov     dword ptr [rax], 1
0x180039b64  lea     rax, [rsp+130h+var_E0]
0x180039b69  mov     [rsp+130h+ppv], rax; int
0x180039b6e  mov     [r12], r13
0x180039b72  mov     [rsp+130h+var_E0], r13
0x180039b77  call    cs:__imp_SHCoCreateInstance
0x180039b7d  mov     ebx, eax
0x180039b7f  test    eax, eax
0x180039b81  js      loc_180039D35
0x180039b87  mov     rcx, [rsp+130h+var_E0]
0x180039b8c  lea     rdx, [rbp+3Fh+var_78]
0x180039b90  mov     [rsp+130h+var_100], rdi
0x180039b95  xor     r9d, r9d
0x180039b98  mov     qword ptr [rsp+130h+var_108], rsi
0x180039b9d  mov     r8, r14
0x180039ba0  mov     [rsp+130h+ppv], rdx; int
0x180039ba5  mov     rdx, r15
0x180039ba8  mov     rax, [rcx]
0x180039bab  mov     rax, [rax+18h]
0x180039baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039bb4  mov     ebx, eax
0x180039bb6  test    eax, eax
0x180039bb8  js      short loc_180039BD6
0x180039bba  mov     rcx, [rsp+130h+var_E0]
0x180039bbf  lea     rdx, _GUID_6bc63938_8254_4965_9680_565933185060
0x180039bc6  mov     r8, r12
0x180039bc9  mov     rax, [rcx]
0x180039bcc  mov     rax, [rax]
0x180039bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039bd4  mov     ebx, eax
0x180039bd6  mov     rcx, [rsp+130h+var_E0]
0x180039bdb  mov     rax, [rcx]
0x180039bde  mov     rax, [rax+10h]
0x180039be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039be7  test    ebx, ebx
0x180039be9  js      loc_180039D35
0x180039bef  mov     rdx, [rbp+3Fh+punk]; punk
0x180039bf3  mov     rcx, [rbp+3Fh+ppunk]; ppunk
0x180039bf7  call    cs:__imp_IUnknown_Set
0x180039bfd  mov     rcx, [rbp+3Fh+punk]
0x180039c01  mov     rax, [rcx]
0x180039c04  mov     rax, [rax+10h]
0x180039c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c0d  mov     rcx, [rsp+130h+var_D8]
0x180039c12  mov     [rsp+130h+var_D8], r13
0x180039c17  test    rcx, rcx
0x180039c1a  jz      short loc_180039C28
0x180039c1c  mov     rax, [rcx]
0x180039c1f  mov     rax, [rax+10h]
0x180039c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c28  mov     rcx, [rbp+3Fh+var_A8]
0x180039c2c  mov     rax, [rcx]
0x180039c2f  mov     rax, [rax+10h]
0x180039c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c38  mov     rcx, [rbp+3Fh+var_A0]
0x180039c3c  mov     rax, [rcx]
0x180039c3f  mov     rax, [rax+10h]
0x180039c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c48  mov     rcx, [rbp+3Fh+var_B8]
0x180039c4c  mov     [rbp+3Fh+var_B8], r13
0x180039c50  test    rcx, rcx
0x180039c53  jz      short loc_180039C61
0x180039c55  mov     rax, [rcx]
0x180039c58  mov     rax, [rax+10h]
0x180039c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c61  mov     rcx, [rsp+130h+var_C8]
0x180039c66  mov     [rsp+130h+var_C8], r13
0x180039c6b  test    rcx, rcx
0x180039c6e  jz      short loc_180039C7C
0x180039c70  mov     rax, [rcx]
0x180039c73  mov     rax, [rax+10h]
0x180039c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c7c  mov     rcx, [rsp+130h+var_D0]
0x180039c81  mov     [rsp+130h+var_D0], r13
0x180039c86  test    rcx, rcx
0x180039c89  jz      short loc_180039C97
0x180039c8b  mov     rax, [rcx]
0x180039c8e  mov     rax, [rax+10h]
0x180039c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c97  test    ebx, ebx
0x180039c99  js      loc_180039E84
0x180039c9f  mov     eax, ebx
0x180039ca1  mov     rcx, [rbp+3Fh+var_48]
0x180039ca5  xor     rcx, rsp; StackCookie
0x180039ca8  call    __security_check_cookie
0x180039cad  add     rsp, 0F8h
0x180039cb4  pop     r15
0x180039cb6  pop     r14
0x180039cb8  pop     r13
0x180039cba  pop     r12
0x180039cbc  pop     rdi
0x180039cbd  pop     rsi
0x180039cbe  pop     rbx
0x180039cbf  pop     rbp
0x180039cc0  retn
0x180039cc1  mov     rcx, [rsp+130h+var_E0]
0x180039cc6  lea     r8, [rbp+3Fh+var_60]
0x180039cca  xor     eax, eax
0x180039ccc  xorps   xmm0, xmm0
0x180039ccf  mov     [rbp+3Fh+var_60.pid], eax
0x180039cd2  mov     edx, edi
0x180039cd4  movups  xmmword ptr [rbp+3Fh+var_60.fmtid.Data1], xmm0
0x180039cd8  mov     rax, [rcx]
0x180039cdb  mov     rax, [rax+20h]
0x180039cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ce4  mov     ebx, eax
0x180039ce6  test    eax, eax
0x180039ce8  js      short loc_180039CFA
0x180039cea  mov     rcx, [rsp+130h+var_D8]; struct IPropertyKeyStore *
0x180039cef  lea     rdx, [rbp+3Fh+var_60]; struct _tagpropertykey *
0x180039cf3  call    ?AddPropertyAndDependencies@@YAJPEAUIPropertyKeyStore@@AEBU_tagpropertykey@@@Z; AddPropertyAndDependencies(IPropertyKeyStore *,_tagpropertykey const &)
0x180039cf8  mov     ebx, eax
  ... truncated ...
```
