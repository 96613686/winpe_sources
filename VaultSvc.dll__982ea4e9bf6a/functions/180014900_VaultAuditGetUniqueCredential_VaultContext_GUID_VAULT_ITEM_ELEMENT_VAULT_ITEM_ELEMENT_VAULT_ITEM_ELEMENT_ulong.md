# VaultAuditGetUniqueCredential(VaultContext *,_GUID *,_VAULT_ITEM_ELEMENT *,_VAULT_ITEM_ELEMENT *,_VAULT_ITEM_ELEMENT *,ulong,ulong)

- ea: `0x180014900`
- end: `0x1800151bc`
- name: `?VaultAuditGetUniqueCredential@@YAXPEAUVaultContext@@PEAU_GUID@@PEAU_VAULT_ITEM_ELEMENT@@22KK@Z`
- size: `2236`
- prototype: `void __fastcall(struct VaultContext *, struct _GUID *, struct _VAULT_ITEM_ELEMENT *, struct _VAULT_ITEM_ELEMENT *, struct _VAULT_ITEM_ELEMENT *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180012ae0`

## callees

- `0x180002d10`
- `0x180006610`
- `0x18000ae60`
- `0x18000f2e0`
- `0x180014900`
- `0x180027340`
- `0x18002e5d0`
- `0x1800311e0`
- `0x18003a580`
- `0x18003af10`
- `0x18004976c`
- `0x18004b430`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015110`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015110`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800150ed`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800150ed`
- `LSASRV!LsapQueryClientInfo` at `0x180014b6b`
- `LSASRV!LsapQueryClientInfo` at `0x180014b6b`
- `LSASRV!LsapAdtGetCallerProcessInfo` at `0x180014b53`
- `LSASRV!LsapAdtGetCallerProcessInfo` at `0x180014b53`
- `LSASRV!LsapAuditFailed` at `0x180014e9e`
- `LSASRV!LsapAuditFailed` at `0x180015084`
- `LSASRV!LsapAuditFailed` at `0x180014e9e`
- `LSASRV!LsapAuditFailed` at `0x180015084`
- `LSASRV!LsapAdtWriteLog` at `0x180015060`
- `LSASRV!LsapAdtWriteLog` at `0x180015060`
- `ntdll!RtlInitUnicodeString` at `0x180014e4c`
- `ntdll!RtlInitUnicodeString` at `0x180014e7f`
- `ntdll!RtlInitUnicodeString` at `0x180014eda`
- `ntdll!RtlInitUnicodeString` at `0x180014f03`
- `ntdll!RtlInitUnicodeString` at `0x180014f17`
- `ntdll!RtlInitUnicodeString` at `0x180014e4c`
- `ntdll!RtlInitUnicodeString` at `0x180014e7f`
- `ntdll!RtlInitUnicodeString` at `0x180014eda`
- `ntdll!RtlInitUnicodeString` at `0x180014f03`
- `ntdll!RtlInitUnicodeString` at `0x180014f17`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180014b31`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180014b31`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x18001504d`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x18001504d`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall VaultAuditGetUniqueCredential(
        struct VaultContext *a1,
        struct _GUID *a2,
        struct _VAULT_ITEM_ELEMENT *a3,
        struct _VAULT_ITEM_ELEMENT *a4,
        struct _VAULT_ITEM_ELEMENT *a5,
        unsigned int a6,
        unsigned int a7)
{
  void **v8; // rsi
  PCWSTR v9; // r13
  void **v10; // r12
  __int64 v11; // rdi
  __int64 v12; // rbx
  int CallerProcessInfo; // edi
  void (__fastcall ***v14)(_QWORD); // rcx
  __int64 v15; // r14
  int v16; // eax
  __int64 v17; // r15
  __int64 v18; // rbx
  int v19; // eax
  void (__fastcall ***v20)(_QWORD); // rcx
  __int64 v21; // r14
  struct _GUID *v22; // rbx
  __int64 v23; // rdx
  unsigned int Schema; // ebx
  bool v25; // sf
  int v26; // eax
  PCWSTR v27; // r14
  PCWSTR v28; // r15
  const WCHAR *v29; // rax
  _BYTE *v30; // rax
  __int64 v31; // rcx
  _BYTE *v32; // rbx
  SIZE_T v33; // rdx
  _BYTE *v34; // rax
  void (__fastcall *v35)(void **, PCWSTR); // rax
  void (__fastcall *v36)(void **, PCWSTR); // rax
  void (__fastcall *v37)(void **, PCWSTR); // rax
  char v38[4]; // [rsp+F0h] [rbp-80h] BYREF
  int v39; // [rsp+F4h] [rbp-7Ch] BYREF
  void (__fastcall *v40)(void **, PCWSTR); // [rsp+F8h] [rbp-78h] BYREF
  void **v41; // [rsp+100h] [rbp-70h]
  PCWSTR v42; // [rsp+108h] [rbp-68h]
  void (__fastcall *v43)(void **, PCWSTR); // [rsp+110h] [rbp-60h] BYREF
  void **v44; // [rsp+118h] [rbp-58h]
  PCWSTR v45; // [rsp+120h] [rbp-50h]
  __int64 (__fastcall *v46)(__int64); // [rsp+128h] [rbp-48h]
  HLOCAL hMem; // [rsp+130h] [rbp-40h] BYREF
  unsigned int v48; // [rsp+138h] [rbp-38h]
  __int64 v49; // [rsp+140h] [rbp-30h] BYREF
  char v50; // [rsp+148h] [rbp-28h]
  __int64 v51; // [rsp+150h] [rbp-20h] BYREF
  struct _GUID *v52; // [rsp+158h] [rbp-18h]
  _QWORD *v53; // [rsp+160h] [rbp-10h] BYREF
  void (__fastcall *v54)(void **, PCWSTR); // [rsp+168h] [rbp-8h] BYREF
  void **v55; // [rsp+170h] [rbp+0h]
  PCWSTR SourceString; // [rsp+178h] [rbp+8h]
  __int64 (__fastcall *v57)(__int64); // [rsp+180h] [rbp+10h] BYREF
  struct IVaultStore *v58; // [rsp+188h] [rbp+18h] BYREF
  int v59; // [rsp+190h] [rbp+20h]
  __int64 (__fastcall *v60)(__int64); // [rsp+198h] [rbp+28h] BYREF
  __int64 v61; // [rsp+1A0h] [rbp+30h]
  int v62; // [rsp+1A8h] [rbp+38h]
  __int64 v63; // [rsp+1B0h] [rbp+40h] BYREF
  struct _VAULT_ITEM_ELEMENT *v64; // [rsp+1B8h] [rbp+48h]
  struct _VAULT_ITEM_ELEMENT *v65; // [rsp+1C0h] [rbp+50h]
  struct _VAULT_ITEM_ELEMENT *v66; // [rsp+1C8h] [rbp+58h]
  _QWORD *v67; // [rsp+1D0h] [rbp+60h]
  __int64 (__fastcall *v68)(__int64); // [rsp+1D8h] [rbp+68h]
  __int64 v69; // [rsp+1E0h] [rbp+70h]
  int v70; // [rsp+1E8h] [rbp+78h]
  struct _UNICODE_STRING v71; // [rsp+1F0h] [rbp+80h] BYREF
  struct _UNICODE_STRING v72; // [rsp+200h] [rbp+90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+210h] [rbp+A0h] BYREF
  struct _UNICODE_STRING v74; // [rsp+220h] [rbp+B0h] BYREF
  struct _UNICODE_STRING v75; // [rsp+230h] [rbp+C0h] BYREF
  void (__fastcall *v76)(struct IVaultAllocator *, struct _VAULT_ITEM_SCHEMA *); // [rsp+240h] [rbp+D0h]
  void **v77; // [rsp+248h] [rbp+D8h]
  int *v78; // [rsp+250h] [rbp+E0h]
  __int128 Buf2; // [rsp+258h] [rbp+E8h] BYREF
  int v80; // [rsp+270h] [rbp+100h] BYREF
  __int128 v81; // [rsp+274h] [rbp+104h]
  __int128 v82; // [rsp+284h] [rbp+114h]
  _BYTE v83[28]; // [rsp+294h] [rbp+124h] BYREF
  _BYTE v84[1056]; // [rsp+2B0h] [rbp+140h] BYREF

  v65 = a4;
  v64 = a3;
  v52 = a2;
  v66 = a5;
  memset_0(v84, 0, 0x418u);
  v38[0] = 1;
  v39 = 0;
  v51 = 0;
  v74 = 0;
  DestinationString = 0;
  v72 = 0;
  v71 = 0;
  v54 = 0;
  v8 = VaultGlobals::g_HeapAlloc;
  v55 = VaultGlobals::g_HeapAlloc;
  v9 = 0;
  SourceString = 0;
  v43 = 0;
  v10 = VaultGlobals::g_HeapAlloc;
  v44 = VaultGlobals::g_HeapAlloc;
  v45 = 0;
  v40 = 0;
  v41 = VaultGlobals::g_HeapAlloc;
  v42 = 0;
  v75 = 0;
  v53 = 0;
  v63 = 0;
  v46 = AutoDereference<IVaultKeyManager>;
  hMem = 0;
  v48 = 0;
  v68 = AutoDereference<IVaultKeyManager>;
  v69 = 0;
  v70 = 0;
  Buf2 = 0;
  v11 = *(_QWORD *)a1;
  v12 = *(_QWORD *)(*(_QWORD *)a1 + 8LL);
  v49 = v12;
  if ( v12 )
  {
    (**(void (__fastcall ***)(__int64))v12)(v12);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 200LL))(v12, 0);
  }
  v50 = 1;
  if ( *(_DWORD *)(v11 + 108) == 2 )
  {
    if ( v12 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 208LL))(v12);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    }
    CallerProcessInfo = -2147024841;
    goto LABEL_62;
  }
  v14 = *(void (__fastcall ****)(_QWORD))(v11 + 8);
  if ( !v14 )
  {
    CVaultStoreLock::~CVaultStoreLock((CVaultStoreLock *)&v49);
    CallerProcessInfo = -2147023728;
    goto LABEL_62;
  }
  (**v14)(v14);
  v15 = *(_QWORD *)(v11 + 8);
  v69 = v15;
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 208LL))(v12);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  }
  v16 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v15 + 24LL))(v15, &Buf2);
  CallerProcessInfo = v16;
  if ( v16 )
  {
    if ( v16 > 0 )
      CallerProcessInfo = (unsigned __int16)v16 | 0x80070000;
    goto LABEL_62;
  }
  if ( memcmp_0(&Vault_DefaultVault_ID, &Buf2, 0x10u) && memcmp_0(&Vault_CredmanVault_ID, &Buf2, 0x10u) )
    goto LABEL_66;
  v67 = (_QWORD *)((char *)a1 + 76);
  CallerProcessInfo = LsapAdtAuditingEnabledByLogonId(146, (char *)a1 + 76, 8, v38);
  if ( CallerProcessInfo < 0 )
    goto LABEL_64;
  if ( !v38[0] )
    goto LABEL_66;
  CallerProcessInfo = LsapAdtGetCallerProcessInfo(&v39, &v51);
  if ( CallerProcessInfo < 0 )
    goto LABEL_64;
  CallerProcessInfo = LsapQueryClientInfo(&v53, &v63);
  if ( CallerProcessInfo < 0 )
    goto LABEL_64;
  v17 = *(_QWORD *)a1;
  v60 = AutoDereference<IVaultKeyManager>;
  v61 = 0;
  v62 = 0;
  v57 = AutoDereference<IVaultKeyManager>;
  v58 = 0;
  v59 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  memset(v83, 0, sizeof(v83));
  v76 = VaultFreeVaultSchema;
  v77 = VaultGlobals::g_HeapAlloc;
  v78 = &v80;
  v18 = *(_QWORD *)(v17 + 8);
  v49 = v18;
  if ( v18 )
  {
    (**(void (__fastcall ***)(__int64))v18)(v18);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 200LL))(v18, 0);
  }
  v50 = 1;
  v19 = *(_DWORD *)(v17 + 108);
  if ( v19 == 2 )
  {
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 208LL))(v18);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
    }
    CallerProcessInfo = 55;
    goto LABEL_42;
  }
  if ( !v19 )
  {
    CVaultStoreLock::~CVaultStoreLock((CVaultStoreLock *)&v49);
    CallerProcessInfo = 212;
LABEL_42:
    VaultFreeVaultSchema((struct IVaultAllocator *)VaultGlobals::g_HeapAlloc, (struct _VAULT_ITEM_SCHEMA *)&v80);
    goto LABEL_43;
  }
  v20 = *(void (__fastcall ****)(_QWORD))(v17 + 8);
  if ( !v20 )
  {
    CVaultStoreLock::~CVaultStoreLock((CVaultStoreLock *)&v49);
    CallerProcessInfo = 1168;
    goto LABEL_42;
  }
  (**v20)(v20);
  v21 = *(_QWORD *)(v17 + 8);
  v61 = v21;
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 208LL))(v18);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
  }
  v22 = v52;
  CallerProcessInfo = (*(__int64 (__fastcall **)(__int64, struct _GUID *, HLOCAL *))(*(_QWORD *)v21 + 80LL))(
                        v21,
                        v52,
                        &hMem);
  if ( CallerProcessInfo != 1168 )
  {
    VaultFreeVaultSchema((struct IVaultAllocator *)VaultGlobals::g_HeapAlloc, (struct _VAULT_ITEM_SCHEMA *)&v80);
    if ( v21 )
      AutoDereference<IVaultKeyManager>(v21);
    goto LABEL_43;
  }
  CallerProcessInfo = CUserVault::GetVaultStore(VaultGlobals::g_GlobalSchemaMgr, &v58, 0);
  if ( !CallerProcessInfo )
  {
    CallerProcessInfo = (*(__int64 (__fastcall **)(struct IVaultStore *, struct _GUID *, HLOCAL *))(*(_QWORD *)v58 + 80LL))(
                          v58,
                          v22,
                          &hMem);
    if ( !CallerProcessInfo )
    {
      CallerProcessInfo = VaultConvertSchema(
                            (struct IVaultAllocator *)VaultGlobals::g_HeapAlloc,
                            (struct IVaultSchema *)hMem,
                            (struct _VAULT_ITEM_SCHEMA *)&v80);
      if ( CallerProcessInfo )
        goto LABEL_35;
      Schema = VaultCreateSchema((struct CUserVault *)v17, (struct _VAULT_ITEM_SCHEMA *)&v80, 0, 1u);
      VaultFreeVaultSchema((struct IVaultAllocator *)VaultGlobals::g_HeapAlloc, (struct _VAULT_ITEM_SCHEMA *)&v80);
      CallerProcessInfo = 0;
      if ( Schema != 183 )
        CallerProcessInfo = Schema;
    }
    VaultFreeVaultSchema((struct IVaultAllocator *)VaultGlobals::g_HeapAlloc, (struct _VAULT_ITEM_SCHEMA *)&v80);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete((__int64)&v57);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete((__int64)&v60);
LABEL_43:
    if ( CallerProcessInfo )
      goto LABEL_44;
    if ( !v64 )
    {
LABEL_49:
      if ( v65 )
      {
        v26 = VaultVariantToUnicodeString(v65, v23, &v43);
        v27 = v45;
        if ( v26 < 0 )
        {
          v10 = v44;
          v28 = v42;
          LsapAuditFailed((unsigned int)v26);
          goto LABEL_67;
        }
        RtlInitUnicodeString(&v72, v45);
        v10 = v44;
      }
      else
      {
        v27 = v45;
      }
      if ( v66 )
      {
        CallerProcessInfo = VaultVariantToUnicodeString(v66, v23, &v40);
        v28 = v42;
        if ( CallerProcessInfo < 0 )
        {
LABEL_65:
          LsapAuditFailed((unsigned int)CallerProcessInfo);
          goto LABEL_67;
        }
        RtlInitUnicodeString(&v71, v42);
      }
      else
      {
        v28 = v42;
      }
      v29 = (const WCHAR *)(*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)hMem + 136LL))(hMem);
      RtlInitUnicodeString(&v74, v29);
      RtlInitUnicodeString(&v75, L"VAULT");
      CallerProcessInfo = LsapAdtInitParametersArray(
                            v84,
                            7,
                            5382,
                            146,
                            8,
                            12,
                            4,
                            *v53,
                            1,
                            &v75,
                            5,
                            *v67,
                            1,
                            &v74,
                            13,
                            v52,
                            1,
                            &DestinationString,
                            1,
                            &v72,
                            1,
                            &v71,
                            27,
                            a6,
                            27,
                            a7,
                            12,
                            v51,
                            27,
                            v39);
      if ( CallerProcessInfo >= 0 )
      {
        LsapAdtWriteLog(v84);
        goto LABEL_67;
      }
      goto LABEL_65;
    }
    CallerProcessInfo = VaultVariantToUnicodeString(v64, v23, &v54);
    v9 = SourceString;
    if ( CallerProcessInfo >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
      v8 = v55;
      goto LABEL_49;
    }
    v8 = v55;
LABEL_64:
    v27 = v45;
    v28 = v42;
    goto LABEL_65;
  }
LABEL_35:
  VaultFreeVaultSchema((struct IVaultAllocator *)VaultGlobals::g_HeapAlloc, (struct _VAULT_ITEM_SCHEMA *)&v80);
  CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete((__int64)&v57);
  CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete((__int64)&v60);
LABEL_44:
  v25 = CallerProcessInfo < 0;
  if ( CallerProcessInfo <= 0 )
    goto LABEL_63;
  CallerProcessInfo = (unsigned __int16)CallerProcessInfo | 0x80070000;
LABEL_62:
  v25 = CallerProcessInfo < 0;
LABEL_63:
  if ( v25 )
    goto LABEL_64;
LABEL_66:
  v28 = v42;
  v27 = v45;
LABEL_67:
  if ( v69 )
    AutoDereference<IVaultKeyManager>(v69);
  v30 = hMem;
  if ( hMem )
  {
    v31 = v48;
    if ( v48 )
    {
      do
      {
        *v30++ = 0;
        --v31;
      }
      while ( v31 );
    }
    if ( v46 )
    {
      v46((__int64)hMem);
    }
    else
    {
      v32 = hMem;
      if ( hMem )
      {
        v33 = LocalSize(hMem);
        if ( v33 )
        {
          v34 = v32;
          do
          {
            *v34++ = 0;
            --v33;
          }
          while ( v33 );
        }
        LocalFree(v32);
      }
    }
    hMem = 0;
  }
  v48 = 0;
  if ( v28 && v41 )
  {
    v35 = v40;
    if ( !v40 )
      v35 = (void (__fastcall *)(void **, PCWSTR))*((_QWORD *)*v41 + 1);
    v35(v41, v28);
  }
  if ( v27 && v10 )
  {
    v36 = v43;
    if ( !v43 )
      v36 = (void (__fastcall *)(void **, PCWSTR))*((_QWORD *)*v10 + 1);
    v36(v10, v27);
  }
  if ( v9 && v8 )
  {
    v37 = v54;
    if ( !v54 )
      v37 = (void (__fastcall *)(void **, PCWSTR))*((_QWORD *)*v8 + 1);
    v37(v8, v9);
  }
}

```

## disassembly

```asm
0x180014900  push    rbp
0x180014902  push    rbx
0x180014903  push    rsi
0x180014904  push    rdi
0x180014905  push    r12
0x180014907  push    r13
0x180014909  push    r14
0x18001490b  push    r15
0x18001490d  lea     rbp, [rsp-578h]
0x180014915  sub     rsp, 6E8h
0x18001491c  mov     rax, cs:__security_cookie
0x180014923  xor     rax, rsp
0x180014926  mov     [rbp+5B0h+var_50], rax
0x18001492d  mov     [rbp+5B0h+var_560], r9
0x180014931  mov     [rbp+5B0h+var_568], r8
0x180014935  mov     [rbp+5B0h+var_5C8], rdx
0x180014939  mov     r15, rcx
0x18001493c  mov     rax, [rbp+5B0h+arg_20]
0x180014943  mov     [rbp+5B0h+var_558], rax
0x180014947  xor     edx, edx; Val
0x180014949  mov     r8d, 418h; Size
0x18001494f  lea     rcx, [rbp+5B0h+var_470]; void *
0x180014956  call    memset_0
0x18001495b  mov     [rbp+5B0h+var_630], 1
0x18001495f  xor     ecx, ecx
0x180014961  mov     [rbp+5B0h+var_62C], ecx
0x180014964  mov     [rbp+5B0h+var_5D0], rcx
0x180014968  xorps   xmm0, xmm0
0x18001496b  movups  xmmword ptr [rbp+5B0h+var_500.Length], xmm0
0x180014972  xorps   xmm1, xmm1
0x180014975  movups  xmmword ptr [rbp+5B0h+DestinationString.Length], xmm1
0x18001497c  movups  xmmword ptr [rbp+5B0h+var_520.Length], xmm0
0x180014983  movups  xmmword ptr [rbp+5B0h+var_530.Length], xmm1
0x18001498a  mov     [rbp+5B0h+var_5B8], rcx
0x18001498e  lea     rsi, ?g_HeapAlloc@VaultGlobals@@3VCVaultHeapAllocator@@A; CVaultHeapAllocator VaultGlobals::g_HeapAlloc
0x180014995  mov     [rbp+5B0h+var_5B0], rsi
0x180014999  mov     r13d, ecx
0x18001499c  mov     [rbp+5B0h+SourceString], rcx
0x1800149a0  mov     [rbp+5B0h+var_610], rcx
0x1800149a4  mov     r12, rsi
0x1800149a7  mov     [rbp+5B0h+var_608], rsi
0x1800149ab  mov     [rbp+5B0h+var_600], rcx
0x1800149af  mov     [rbp+5B0h+var_628], rcx
0x1800149b3  mov     [rbp+5B0h+var_620], rsi
0x1800149b7  mov     [rbp+5B0h+var_618], rcx
0x1800149bb  movups  xmmword ptr [rbp+5B0h+var_4F0.Length], xmm0
0x1800149c2  mov     [rbp+5B0h+var_5C0], rcx
0x1800149c6  mov     [rbp+5B0h+var_570], rcx
0x1800149ca  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x1800149d1  mov     [rbp+5B0h+var_5F8], rax
0x1800149d5  mov     [rbp+5B0h+hMem], rcx
0x1800149d9  mov     [rbp+5B0h+var_5E8], ecx
0x1800149dc  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x1800149e3  mov     [rbp+5B0h+var_548], rax
0x1800149e7  mov     [rbp+5B0h+var_540], rcx
0x1800149eb  mov     [rbp+5B0h+var_538], ecx
0x1800149ee  movups  [rbp+5B0h+Buf2], xmm0
0x1800149f5  mov     rdi, [r15]
0x1800149f8  mov     rbx, [rdi+8]
0x1800149fc  mov     [rbp+5B0h+var_5E0], rbx
0x180014a00  test    rbx, rbx
0x180014a03  jz      short loc_180014A27
0x180014a05  mov     rax, [rbx]
0x180014a08  mov     rcx, rbx
0x180014a0b  mov     rax, [rax]
0x180014a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a13  mov     rax, [rbx]
0x180014a16  xor     edx, edx
0x180014a18  mov     rcx, rbx
0x180014a1b  mov     rax, [rax+0C8h]
0x180014a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a27  mov     [rbp+5B0h+var_5D8], 1
0x180014a2b  cmp     dword ptr [rdi+6Ch], 2
0x180014a2f  jnz     short loc_180014A62
0x180014a31  test    rbx, rbx
0x180014a34  jz      short loc_180014A58
0x180014a36  mov     rax, [rbx]
0x180014a39  mov     rcx, rbx
0x180014a3c  mov     rax, [rax+0D0h]
0x180014a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a48  mov     rax, [rbx]
0x180014a4b  mov     rcx, rbx
0x180014a4e  mov     rax, [rax+8]
0x180014a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a57  nop
0x180014a58  mov     edi, 80070037h
0x180014a5d  jmp     loc_180015076
0x180014a62  mov     rcx, [rdi+8]
0x180014a66  test    rcx, rcx
0x180014a69  jz      loc_180015068
0x180014a6f  mov     rax, [rcx]
0x180014a72  mov     rax, [rax]
0x180014a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a7a  mov     r14, [rdi+8]
0x180014a7e  mov     [rbp+5B0h+var_540], r14
0x180014a82  test    rbx, rbx
0x180014a85  jz      short loc_180014AA9
0x180014a87  mov     rax, [rbx]
0x180014a8a  mov     rcx, rbx
0x180014a8d  mov     rax, [rax+0D0h]
0x180014a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a99  mov     rax, [rbx]
0x180014a9c  mov     rcx, rbx
0x180014a9f  mov     rax, [rax+8]
0x180014aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aa8  nop
0x180014aa9  mov     rax, [r14]
0x180014aac  lea     rdx, [rbp+5B0h+Buf2]
0x180014ab3  mov     rcx, r14
0x180014ab6  mov     rax, [rax+18h]
0x180014aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014abf  mov     edi, eax
0x180014ac1  test    eax, eax
0x180014ac3  jz      short loc_180014AD9
0x180014ac5  jle     loc_180015076
0x180014acb  movzx   edi, ax
0x180014ace  or      edi, 80070000h
0x180014ad4  jmp     loc_180015076
0x180014ad9  mov     r8d, 10h; Size
0x180014adf  lea     rdx, [rbp+5B0h+Buf2]; Buf2
0x180014ae6  lea     rcx, Vault_DefaultVault_ID; Buf1
0x180014aed  call    memcmp_0
0x180014af2  test    eax, eax
0x180014af4  jz      short loc_180014B17
0x180014af6  mov     r8d, 10h; Size
0x180014afc  lea     rdx, [rbp+5B0h+Buf2]; Buf2
0x180014b03  lea     rcx, Vault_CredmanVault_ID; Buf1
0x180014b0a  call    memcmp_0
0x180014b0f  test    eax, eax
0x180014b11  jnz     loc_18001508C
0x180014b17  lea     rax, [r15+4Ch]
0x180014b1b  mov     [rbp+5B0h+var_550], rax
0x180014b1f  lea     r9, [rbp+5B0h+var_630]
0x180014b23  mov     r8d, 8
0x180014b29  mov     rdx, rax
0x180014b2c  mov     ecx, 92h
0x180014b31  call    cs:__imp_LsapAdtAuditingEnabledByLogonId
0x180014b37  mov     edi, eax
0x180014b39  test    eax, eax
0x180014b3b  js      loc_18001507A
0x180014b41  cmp     [rbp+5B0h+var_630], 0
0x180014b45  jz      loc_18001508C
0x180014b4b  lea     rdx, [rbp+5B0h+var_5D0]
0x180014b4f  lea     rcx, [rbp+5B0h+var_62C]
0x180014b53  call    cs:__imp_LsapAdtGetCallerProcessInfo
0x180014b59  mov     edi, eax
0x180014b5b  test    eax, eax
0x180014b5d  js      loc_18001507A
0x180014b63  lea     rdx, [rbp+5B0h+var_570]
0x180014b67  lea     rcx, [rbp+5B0h+var_5C0]
0x180014b6b  call    cs:__imp_LsapQueryClientInfo
0x180014b71  mov     edi, eax
0x180014b73  test    eax, eax
0x180014b75  js      loc_18001507A
0x180014b7b  mov     r15, [r15]
0x180014b7e  lea     rcx, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180014b85  mov     [rbp+5B0h+var_588], rcx
0x180014b89  xor     eax, eax
0x180014b8b  mov     [rbp+5B0h+var_580], rax
0x180014b8f  mov     [rbp+5B0h+var_578], eax
0x180014b92  mov     [rbp+5B0h+var_5A0], rcx
0x180014b96  mov     [rbp+5B0h+var_598], rax
0x180014b9a  mov     [rbp+5B0h+var_590], eax
0x180014b9d  mov     [rbp+5B0h+var_4B0], eax
0x180014ba3  xorps   xmm0, xmm0
0x180014ba6  movups  [rbp+5B0h+var_4AC], xmm0
0x180014bad  movups  [rbp+5B0h+var_49C], xmm0
0x180014bb4  movups  xmmword ptr [rbp+5B0h+var_48C], xmm0
0x180014bbb  movups  xmmword ptr [rbp+5B0h+var_48C+0Ch], xmm0
0x180014bc2  lea     rax, ?VaultFreeVaultSchema@@YAXPEAUIVaultAllocator@@PEAU_VAULT_ITEM_SCHEMA@@@Z; VaultFreeVaultSchema(IVaultAllocator *,_VAULT_ITEM_SCHEMA *)
0x180014bc9  mov     [rbp+5B0h+var_4E0], rax
0x180014bd0  mov     [rbp+5B0h+var_4D8], rsi
0x180014bd7  lea     rax, [rbp+5B0h+var_4B0]
0x180014bde  mov     [rbp+5B0h+var_4D0], rax
0x180014be5  mov     rbx, [r15+8]
0x180014be9  mov     [rbp+5B0h+var_5E0], rbx
0x180014bed  test    rbx, rbx
0x180014bf0  jz      short loc_180014C14
0x180014bf2  mov     rax, [rbx]
0x180014bf5  mov     rcx, rbx
0x180014bf8  mov     rax, [rax]
0x180014bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c00  mov     rax, [rbx]
0x180014c03  xor     edx, edx
0x180014c05  mov     rcx, rbx
0x180014c08  mov     rax, [rax+0C8h]
0x180014c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c14  mov     [rbp+5B0h+var_5D8], 1
0x180014c18  mov     eax, [r15+6Ch]
0x180014c1c  cmp     eax, 2
0x180014c1f  jnz     short loc_180014C52
0x180014c21  test    rbx, rbx
0x180014c24  jz      short loc_180014C48
0x180014c26  mov     rax, [rbx]
0x180014c29  mov     rcx, rbx
0x180014c2c  mov     rax, [rax+0D0h]
0x180014c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c38  mov     rax, [rbx]
0x180014c3b  mov     rcx, rbx
0x180014c3e  mov     rax, [rax+8]
0x180014c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c47  nop
0x180014c48  mov     edi, 37h ; '7'
0x180014c4d  jmp     loc_180014DF9
0x180014c52  test    eax, eax
0x180014c54  jnz     short loc_180014C69
0x180014c56  lea     rcx, [rbp+5B0h+var_5E0]; this
0x180014c5a  call    ??1CVaultStoreLock@@QEAA@XZ; CVaultStoreLock::~CVaultStoreLock(void)
0x180014c5f  mov     edi, 0D4h
0x180014c64  jmp     loc_180014DF9
0x180014c69  mov     rcx, [r15+8]
0x180014c6d  test    rcx, rcx
0x180014c70  jz      loc_180014DEB
0x180014c76  mov     rax, [rcx]
0x180014c79  mov     rax, [rax]
0x180014c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c81  mov     r14, [r15+8]
0x180014c85  mov     [rbp+5B0h+var_580], r14
0x180014c89  test    rbx, rbx
0x180014c8c  jz      short loc_180014CB0
0x180014c8e  mov     rax, [rbx]
0x180014c91  mov     rcx, rbx
0x180014c94  mov     rax, [rax+0D0h]
0x180014c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ca0  mov     rax, [rbx]
0x180014ca3  mov     rcx, rbx
0x180014ca6  mov     rax, [rax+8]
0x180014caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014caf  nop
0x180014cb0  mov     rax, [r14]
0x180014cb3  lea     r8, [rbp+5B0h+hMem]
0x180014cb7  mov     rbx, [rbp+5B0h+var_5C8]
0x180014cbb  mov     rdx, rbx
0x180014cbe  mov     rcx, r14
0x180014cc1  mov     rax, [rax+50h]
0x180014cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cca  mov     edi, eax
0x180014ccc  cmp     eax, 490h
0x180014cd1  jz      short loc_180014CF6
0x180014cd3  lea     rdx, [rbp+5B0h+var_4B0]; struct _VAULT_ITEM_SCHEMA *
0x180014cda  mov     rcx, rsi; struct IVaultAllocator *
0x180014cdd  call    ?VaultFreeVaultSchema@@YAXPEAUIVaultAllocator@@PEAU_VAULT_ITEM_SCHEMA@@@Z; VaultFreeVaultSchema(IVaultAllocator *,_VAULT_ITEM_SCHEMA *)
0x180014ce2  nop
0x180014ce3  test    r14, r14
0x180014ce6  jz      short loc_180014CF1
0x180014ce8  mov     rcx, r14
0x180014ceb  call    ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180014cf0  nop
0x180014cf1  jmp     loc_180014E09
0x180014cf6  xor     r8d, r8d; unsigned __int8
0x180014cf9  lea     rdx, [rbp+5B0h+var_598]; struct IVaultStore **
0x180014cfd  mov     rcx, cs:?g_GlobalSchemaMgr@VaultGlobals@@3VCVaultGlobalSchemaMgr@@A; this
0x180014d04  call    ?GetVaultStore@CUserVault@@QEAAKPEAPEAUIVaultStore@@E@Z; CUserVault::GetVaultStore(IVaultStore * *,uchar)
0x180014d09  mov     edi, eax
0x180014d0b  test    eax, eax
0x180014d0d  jz      short loc_180014D38
0x180014d0f  lea     rdx, [rbp+5B0h+var_4B0]; struct _VAULT_ITEM_SCHEMA *
0x180014d16  mov     rcx, rsi; struct IVaultAllocator *
0x180014d19  call    ?VaultFreeVaultSchema@@YAXPEAUIVaultAllocator@@PEAU_VAULT_ITEM_SCHEMA@@@Z; VaultFreeVaultSchema(IVaultAllocator *,_VAULT_ITEM_SCHEMA *)
0x180014d1e  nop
0x180014d1f  lea     rcx, [rbp+5B0h+var_5A0]
0x180014d23  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180014d28  nop
0x180014d29  lea     rcx, [rbp+5B0h+var_588]
0x180014d2d  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180014d32  nop
0x180014d33  jmp     loc_180014E0D
0x180014d38  mov     rcx, [rbp+5B0h+var_598]
0x180014d3c  mov     rax, [rcx]
0x180014d3f  lea     r8, [rbp+5B0h+hMem]
0x180014d43  mov     rdx, rbx
0x180014d46  mov     rax, [rax+50h]
0x180014d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d4f  mov     edi, eax
0x180014d51  test    eax, eax
0x180014d53  jnz     short loc_180014DC5
0x180014d55  lea     r8, [rbp+5B0h+var_4B0]; struct _VAULT_ITEM_SCHEMA *
0x180014d5c  mov     rdx, [rbp+5B0h+hMem]; struct IVaultSchema *
0x180014d60  mov     rcx, rsi; struct IVaultAllocator *
0x180014d63  call    ?VaultConvertSchema@@YAKPEAUIVaultAllocator@@PEAUIVaultSchema@@PEAU_VAULT_ITEM_SCHEMA@@@Z; VaultConvertSchema(IVaultAllocator *,IVaultSchema *,_VAULT_ITEM_SCHEMA *)
0x180014d68  mov     edi, eax
0x180014d6a  test    eax, eax
0x180014d6c  jz      short loc_180014D94
0x180014d6e  lea     rdx, [rbp+5B0h+var_4B0]; struct _VAULT_ITEM_SCHEMA *
0x180014d75  mov     rcx, rsi; struct IVaultAllocator *
0x180014d78  call    ?VaultFreeVaultSchema@@YAXPEAUIVaultAllocator@@PEAU_VAULT_ITEM_SCHEMA@@@Z; VaultFreeVaultSchema(IVaultAllocator *,_VAULT_ITEM_SCHEMA *)
0x180014d7d  nop
0x180014d7e  lea     rcx, [rbp+5B0h+var_5A0]
0x180014d82  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180014d87  nop
0x180014d88  lea     rcx, [rbp+5B0h+var_588]
0x180014d8c  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180014d91  nop
0x180014d92  jmp     short loc_180014E0D
0x180014d94  mov     r9b, 1; unsigned __int8
0x180014d97  xor     r8d, r8d; unsigned int
0x180014d9a  lea     rdx, [rbp+5B0h+var_4B0]; struct _VAULT_ITEM_SCHEMA *
0x180014da1  mov     rcx, r15; this
0x180014da4  call    ?VaultCreateSchema@@YAKPEAVCUserVault@@PEAU_VAULT_ITEM_SCHEMA@@KE@Z; VaultCreateSchema(CUserVault *,_VAULT_ITEM_SCHEMA *,ulong,uchar)
0x180014da9  mov     ebx, eax
  ... truncated ...
```
