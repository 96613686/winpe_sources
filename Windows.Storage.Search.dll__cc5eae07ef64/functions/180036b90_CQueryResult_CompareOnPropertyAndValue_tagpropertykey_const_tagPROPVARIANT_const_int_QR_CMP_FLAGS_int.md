# CQueryResult::CompareOnPropertyAndValue(_tagpropertykey const &,tagPROPVARIANT const &,int,QR_CMP_FLAGS,int *)

- ea: `0x180036b90`
- end: `0x180036f0b`
- name: `?CompareOnPropertyAndValue@CQueryResult@@UEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@HW4QR_CMP_FLAGS@@PEAH@Z`
- size: `891`
- prototype: `int __high(const struct _tagpropertykey *, const struct tagPROPVARIANT *, int, enum QR_CMP_FLAGS, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180036b90`
- `0x180036f14`
- `0x180037a28`
- `0x180037f10`
- `0x180038694`
- `0x180063a68`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!__imp_SHRestricted` at `0x180036c78`
- `Windows.Storage!__imp_SHRestricted` at `0x180036c78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180036cde`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180036cde`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180036bcb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180036bcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036d8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036d98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036eaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036d8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036d98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036eaa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180036eb8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180036eb8`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x180036e0f`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x180036e0f`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x180036d4e`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x180036d6f`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x180036d4e`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x180036d6f`
- `PROPSYS!PropVariantCompareEx` at `0x180036c98`
- `PROPSYS!PropVariantCompareEx` at `0x180036c98`

## pseudocode

```c
__int64 __fastcall CQueryResult::CompareOnPropertyAndValue(
        RTL_SRWLOCK *a1,
        const PROPERTYKEY *a2,
        const PROPVARIANT *a3,
        int a4,
        unsigned int a5,
        struct IPropertyStorePriv *a6)
{
  struct IPropertyStorePriv *v6; // rdi
  RTL_SRWLOCK *v7; // r14
  RTL_SRWLOCK *v8; // r13
  __int64 (__fastcall ***Ptr)(_QWORD, GUID *, struct IPropertyStorePriv **); // rcx
  int v12; // ebx
  struct IPropertyStorePriv *v13; // rbx
  bool v14; // zf
  int (__fastcall *v15)(struct IPropertyStorePriv *, const PROPERTYKEY *, PROPVARIANT **); // r15
  const PROPERTYKEY *v16; // rdx
  __int64 v17; // rcx
  PROPVARIANT *v18; // r14
  DWORD v19; // eax
  PROPVAR_COMPARE_FLAGS v20; // r9d
  __int64 v22; // rax
  int v23; // eax
  PWSTR v24; // rcx
  __int64 v25; // rax
  ULONG v26; // r14d
  __int64 v27; // rax
  CQueryResult *v28; // rcx
  const WCHAR *FixedParsingPath; // rax
  WCHAR *v30; // rbx
  int v31; // [rsp+20h] [rbp-40h]
  PWSTR v32; // [rsp+30h] [rbp-30h] BYREF
  PWSTR ppszDisplay; // [rsp+38h] [rbp-28h] BYREF
  RTL_SRWLOCK *v34; // [rsp+40h] [rbp-20h]
  __int128 v35; // [rsp+48h] [rbp-18h] BYREF
  __int64 v36; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  PROPVARIANT *propvar1; // [rsp+A0h] [rbp+40h] BYREF
  int v39; // [rsp+B8h] [rbp+58h]

  v39 = a4;
  v6 = a6;
  v7 = a1 + 12;
  v8 = a1 - 9;
  v34 = a1 + 12;
  *(_DWORD *)a6 = 0;
  AcquireSRWLockShared(a1 + 12);
  Ptr = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IPropertyStorePriv **))v8[13].Ptr;
  a6 = 0;
  v12 = (**Ptr)(Ptr, &GUID_388cec0d_4ef6_4015_a135_d96527fd84e2, &a6);
  if ( v12 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(struct IPropertyStorePriv *))(*(_QWORD *)a6 + 72LL))(a6);
    if ( v12 < 0 )
    {
LABEL_16:
      (*(void (__fastcall **)(struct IPropertyStorePriv *))(*(_QWORD *)a6 + 16LL))(a6);
      goto LABEL_17;
    }
    v13 = a6;
    v14 = a2->pid == 10;
    propvar1 = 0;
    v35 = 0;
    v36 = 0;
    v15 = *(int (__fastcall **)(struct IPropertyStorePriv *, const PROPERTYKEY *, PROPVARIANT **))(*(_QWORD *)a6 + 88LL);
    if ( v14 )
    {
      v25 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1;
      if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1 )
        v25 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_ItemNameDisplay.fmtid.Data4;
      if ( !v25 )
      {
        ppszDisplay = 0;
        if ( (*(int (__fastcall **)(struct IPropertyStorePriv *, const PROPERTYKEY *, PWSTR *))(*(_QWORD *)a6 + 88LL))(
               a6,
               &PKEY_SFGAOFlags,
               &ppszDisplay) >= 0 )
        {
          v26 = PropVariantToUInt32WithDefault((const PROPVARIANT *const)ppszDisplay, 0);
          if ( (v26 & 0x40000000) == 0 && CQueryResult::_IsWdsOrGrepDataSource((CQueryResult *)v8, v13) )
          {
            FixedParsingPath = CQueryResult::_GetFixedParsingPath(v28, v13);
            v30 = (WCHAR *)FixedParsingPath;
            if ( FixedParsingPath && PathGetDriveNumberW(FixedParsingPath) != -1 )
              v26 |= 0x40000000u;
            CoTaskMemFree(v30);
          }
          if ( (v26 & 0x40000000) != 0 && (v26 & 0x20400000) != 0x20000000 )
          {
            v13 = a6;
            v16 = &PKEY_ParsingName;
            goto LABEL_5;
          }
        }
        v13 = a6;
      }
    }
    v16 = a2;
LABEL_5:
    if ( v15(v13, v16, &propvar1) < 0 )
    {
      v18 = (PROPVARIANT *)&v35;
      propvar1 = (PROPVARIANT *)&v35;
    }
    else
    {
      v18 = propvar1;
    }
    if ( a2->pid != 100 )
      goto LABEL_8;
    v27 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_DefaultGroupOrder;
    if ( *(_QWORD *)&a2->fmtid.Data1 == PKEY_DefaultGroupOrder )
      v27 = *(_QWORD *)a2->fmtid.Data4 - 0x50011B454E1C0DB0LL;
    if ( v27 )
    {
LABEL_8:
      v14 = (a5 & 1) == 0;
      *(_DWORD *)v6 = 0;
      if ( v14 || a2->pid != 100 )
        goto LABEL_9;
      v22 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_ItemSearchLocation.fmtid.Data1;
      if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_ItemSearchLocation.fmtid.Data1 )
        v22 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_ItemSearchLocation.fmtid.Data4;
      if ( v22 )
      {
LABEL_9:
        v12 = 0;
        v19 = SHRestricted(REST_NOSTRCMPLOGICAL);
        v20 = 9;
        if ( !v19 )
          v20 = 1;
        *(_DWORD *)v6 = PropVariantCompareEx(v18, a3, PVCU_DEFAULT, v20);
      }
      else
      {
        ppszDisplay = 0;
        v12 = PSFormatForDisplayAlloc(a2, v18, PDFF_DEFAULT, &ppszDisplay);
        if ( v12 >= 0 )
        {
          v32 = 0;
          v12 = PSFormatForDisplayAlloc(a2, a3, PDFF_DEFAULT, &v32);
          if ( v12 >= 0 )
          {
            v23 = StrCmpLogicalRestricted(ppszDisplay, v32);
            v24 = v32;
            *(_DWORD *)v6 = v23;
            CoTaskMemFree(v24);
          }
          CoTaskMemFree(ppszDisplay);
          if ( v12 >= 0 )
            goto LABEL_13;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x538,
          (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
          (const char *)(unsigned int)v12,
          v31);
      }
    }
    else
    {
      v31 = (int)v6;
      v12 = CQueryResult::_CompareByGroupOrder(v17, v18, a3, a5);
    }
    if ( v12 < 0 )
    {
LABEL_15:
      (*(void (__fastcall **)(struct IPropertyStorePriv *))(*(_QWORD *)a6 + 80LL))(a6);
      v7 = v34;
      goto LABEL_16;
    }
LABEL_13:
    if ( *(_WORD *)a3 >= 2u && *(_WORD *)propvar1 >= 2u )
      *(_DWORD *)v6 *= v39;
    v12 = *(_DWORD *)v6 != 0;
    goto LABEL_15;
  }
LABEL_17:
  ReleaseSRWLockShared(v7);
  if ( v12 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5BF,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)v12,
      v31);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180036b90  mov     [rsp-38h+arg_8], rbx
0x180036b95  mov     [rsp-38h+arg_18], r9d
0x180036b9a  push    rbp
0x180036b9b  push    rsi
0x180036b9c  push    rdi
0x180036b9d  push    r12
0x180036b9f  push    r13
0x180036ba1  push    r14
0x180036ba3  push    r15
0x180036ba5  mov     rbp, rsp
0x180036ba8  sub     rsp, 60h
0x180036bac  mov     rdi, [rbp+arg_28]
0x180036bb0  lea     r14, [rcx+60h]
0x180036bb4  lea     r13, [rcx-48h]
0x180036bb8  mov     [rbp+var_20], r14
0x180036bbc  xor     r15d, r15d
0x180036bbf  mov     rcx, r14; SRWLock
0x180036bc2  mov     r12, r8
0x180036bc5  mov     rsi, rdx
0x180036bc8  mov     [rdi], r15d
0x180036bcb  call    cs:__imp_AcquireSRWLockShared
0x180036bd1  mov     rcx, [r13+68h]
0x180036bd5  lea     r8, [rbp+arg_28]
0x180036bd9  mov     [rbp+arg_28], r15
0x180036bdd  lea     rdx, _GUID_388cec0d_4ef6_4015_a135_d96527fd84e2
0x180036be4  mov     rax, [rcx]
0x180036be7  mov     rax, [rax]
0x180036bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036bef  mov     ebx, eax
0x180036bf1  test    eax, eax
0x180036bf3  js      loc_180036CDB
0x180036bf9  mov     rcx, [rbp+arg_28]
0x180036bfd  mov     rax, [rcx]
0x180036c00  mov     rax, [rax+48h]
0x180036c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c09  mov     ebx, eax
0x180036c0b  test    eax, eax
0x180036c0d  js      loc_180036CCB
0x180036c13  mov     rbx, [rbp+arg_28]
0x180036c17  xor     eax, eax
0x180036c19  cmp     dword ptr [rsi+10h], 0Ah
0x180036c1d  xorps   xmm0, xmm0
0x180036c20  mov     [rbp+propvar1], r15
0x180036c24  movups  [rbp+var_18], xmm0
0x180036c28  mov     [rbp+var_8], rax
0x180036c2c  mov     rax, [rbx]
0x180036c2f  mov     r15, [rax+58h]
0x180036c33  jz      loc_180036DC3
0x180036c39  mov     rdx, rsi
0x180036c3c  lea     r8, [rbp+propvar1]
0x180036c40  mov     rcx, rbx
0x180036c43  mov     rax, r15
0x180036c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c4b  test    eax, eax
0x180036c4d  js      loc_180036D06
0x180036c53  mov     r14, [rbp+propvar1]
0x180036c57  cmp     dword ptr [rsi+10h], 64h ; 'd'
0x180036c5b  jz      loc_180036E4D
0x180036c61  test    byte ptr [rbp+arg_20], 1
0x180036c65  mov     dword ptr [rdi], 0
0x180036c6b  jnz     loc_180036D13
0x180036c71  mov     ecx, 4000007Eh; rest
0x180036c76  xor     ebx, ebx
0x180036c78  call    cs:__imp_SHRestricted
0x180036c7e  mov     ecx, 1
0x180036c83  mov     r9d, 9
0x180036c89  test    eax, eax
0x180036c8b  mov     rdx, r12; propvar2
0x180036c8e  cmovz   r9d, ecx; flags
0x180036c92  xor     r8d, r8d; unit
0x180036c95  mov     rcx, r14; propvar1
0x180036c98  call    cs:__imp_PropVariantCompareEx
0x180036c9e  mov     [rdi], eax
0x180036ca0  test    ebx, ebx
0x180036ca2  js      short loc_180036CB7
0x180036ca4  cmp     word ptr [r12], 2
0x180036caa  jnb     loc_180036ED3
0x180036cb0  xor     ebx, ebx
0x180036cb2  cmp     [rdi], ebx
0x180036cb4  setnz   bl
0x180036cb7  mov     rcx, [rbp+arg_28]
0x180036cbb  mov     rax, [rcx]
0x180036cbe  mov     rax, [rax+50h]
0x180036cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036cc7  mov     r14, [rbp+var_20]
0x180036ccb  mov     rcx, [rbp+arg_28]
0x180036ccf  mov     rax, [rcx]
0x180036cd2  mov     rax, [rax+10h]
0x180036cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036cdb  mov     rcx, r14; SRWLock
0x180036cde  call    cs:__imp_ReleaseSRWLockShared
0x180036ce4  test    ebx, ebx
0x180036ce6  js      loc_180036EEE
0x180036cec  mov     eax, ebx
0x180036cee  mov     rbx, [rsp+60h+arg_8]
0x180036cf6  add     rsp, 60h
0x180036cfa  pop     r15
0x180036cfc  pop     r14
0x180036cfe  pop     r13
0x180036d00  pop     r12
0x180036d02  pop     rdi
0x180036d03  pop     rsi
0x180036d04  pop     rbp
0x180036d05  retn
0x180036d06  lea     r14, [rbp+var_18]
0x180036d0a  mov     [rbp+propvar1], r14
0x180036d0e  jmp     loc_180036C57
0x180036d13  cmp     dword ptr [rsi+10h], 64h ; 'd'
0x180036d17  jnz     loc_180036C71
0x180036d1d  mov     rax, [rsi]
0x180036d20  sub     rax, qword ptr cs:PKEY_ItemSearchLocation.fmtid.Data1
0x180036d27  jnz     short loc_180036D34
0x180036d29  mov     rax, [rsi+8]
0x180036d2d  sub     rax, qword ptr cs:PKEY_ItemSearchLocation.fmtid.Data4
0x180036d34  test    rax, rax
0x180036d37  jnz     loc_180036C71
0x180036d3d  lea     r9, [rbp+ppszDisplay]; ppszDisplay
0x180036d41  mov     [rbp+ppszDisplay], rax
0x180036d45  xor     r8d, r8d; pdff
0x180036d48  mov     rdx, r14; propvar
0x180036d4b  mov     rcx, rsi; key
0x180036d4e  call    cs:__imp_PSFormatForDisplayAlloc
0x180036d54  mov     ebx, eax
0x180036d56  test    eax, eax
0x180036d58  js      short loc_180036DA6
0x180036d5a  lea     r9, [rbp+var_30]; ppszDisplay
0x180036d5e  mov     [rbp+var_30], 0
0x180036d66  xor     r8d, r8d; pdff
0x180036d69  mov     rdx, r12; propvar
0x180036d6c  mov     rcx, rsi; key
0x180036d6f  call    cs:__imp_PSFormatForDisplayAlloc
0x180036d75  mov     ebx, eax
0x180036d77  test    eax, eax
0x180036d79  js      short loc_180036D94
0x180036d7b  mov     rdx, [rbp+var_30]; psz2
0x180036d7f  mov     rcx, [rbp+ppszDisplay]; psz1
0x180036d83  call    ?StrCmpLogicalRestricted@@YAHPEBG0@Z; StrCmpLogicalRestricted(ushort const *,ushort const *)
0x180036d88  mov     rcx, [rbp+var_30]; pv
0x180036d8c  mov     [rdi], eax
0x180036d8e  call    cs:__imp_CoTaskMemFree
0x180036d94  mov     rcx, [rbp+ppszDisplay]; pv
0x180036d98  call    cs:__imp_CoTaskMemFree
0x180036d9e  test    ebx, ebx
0x180036da0  jns     loc_180036CA4
0x180036da6  mov     rcx, [rbp+38h]; this
0x180036daa  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x180036db1  mov     r9d, ebx; char *
0x180036db4  mov     edx, 538h; void *
0x180036db9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036dbe  jmp     loc_180036CA0
0x180036dc3  mov     rax, [rsi]
0x180036dc6  sub     rax, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x180036dcd  jnz     short loc_180036DDA
0x180036dcf  mov     rax, [rsi+8]
0x180036dd3  sub     rax, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data4
0x180036dda  test    rax, rax
0x180036ddd  jnz     loc_180036C39
0x180036de3  mov     [rbp+ppszDisplay], rax
0x180036de7  lea     r8, [rbp+ppszDisplay]
0x180036deb  mov     rax, [rbx]
0x180036dee  lea     rdx, PKEY_SFGAOFlags
0x180036df5  mov     rcx, rbx
0x180036df8  mov     rax, [rax+58h]
0x180036dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e01  test    eax, eax
0x180036e03  js      loc_180036ECA
0x180036e09  mov     rcx, [rbp+ppszDisplay]; propvarIn
0x180036e0d  xor     edx, edx; ulDefault
0x180036e0f  call    cs:__imp_PropVariantToUInt32WithDefault
0x180036e15  mov     r14d, eax
0x180036e18  bt      eax, 1Eh
0x180036e1c  jnb     short loc_180036E88
0x180036e1e  bt      r14d, 1Eh
0x180036e23  jnb     loc_180036ECA
0x180036e29  and     r14d, 20400000h
0x180036e30  cmp     r14d, 20000000h
0x180036e37  jz      loc_180036ECA
0x180036e3d  mov     rbx, [rbp+arg_28]
0x180036e41  lea     rdx, PKEY_ParsingName
0x180036e48  jmp     loc_180036C3C
0x180036e4d  mov     rax, [rsi]
0x180036e50  sub     rax, cs:PKEY_DefaultGroupOrder
0x180036e57  jnz     short loc_180036E64
0x180036e59  mov     rax, [rsi+8]
0x180036e5d  sub     rax, cs:qword_1800F84B0
0x180036e64  test    rax, rax
0x180036e67  jnz     loc_180036C61
0x180036e6d  mov     r9d, [rbp+arg_20]
0x180036e71  mov     r8, r12
0x180036e74  mov     rdx, r14
0x180036e77  mov     qword ptr [rsp+60h+var_40], rdi
0x180036e7c  call    ?_CompareByGroupOrder@CQueryResult@@AEAAJAEBUtagPROPVARIANT@@0W4QR_CMP_FLAGS@@PEAH@Z; CQueryResult::_CompareByGroupOrder(tagPROPVARIANT const &,tagPROPVARIANT const &,QR_CMP_FLAGS,int *)
0x180036e81  mov     ebx, eax
0x180036e83  jmp     loc_180036CA0
0x180036e88  mov     rdx, rbx; struct IPropertyStorePriv *
0x180036e8b  mov     rcx, r13; this
0x180036e8e  call    ?_IsWdsOrGrepDataSource@CQueryResult@@AEAA_NPEAUIPropertyStorePriv@@@Z; CQueryResult::_IsWdsOrGrepDataSource(IPropertyStorePriv *)
0x180036e93  test    al, al
0x180036e95  jz      short loc_180036E1E
0x180036e97  mov     rdx, rbx; struct IPropertyStorePriv *
0x180036e9a  call    ?_GetFixedParsingPath@CQueryResult@@AEAAPEAGPEAUIPropertyStorePriv@@@Z; CQueryResult::_GetFixedParsingPath(IPropertyStorePriv *)
0x180036e9f  mov     rbx, rax
0x180036ea2  test    rax, rax
0x180036ea5  jnz     short loc_180036EB5
0x180036ea7  mov     rcx, rbx; pv
0x180036eaa  call    cs:__imp_CoTaskMemFree
0x180036eb0  jmp     loc_180036E1E
0x180036eb5  mov     rcx, rbx; pszPath
0x180036eb8  call    cs:__imp_PathGetDriveNumberW
0x180036ebe  cmp     eax, 0FFFFFFFFh
0x180036ec1  jz      short loc_180036EA7
0x180036ec3  bts     r14d, 1Eh
0x180036ec8  jmp     short loc_180036EA7
0x180036eca  mov     rbx, [rbp+arg_28]
0x180036ece  jmp     loc_180036C39
0x180036ed3  mov     rax, [rbp+propvar1]
0x180036ed7  cmp     word ptr [rax], 2
0x180036edb  jb      loc_180036CB0
0x180036ee1  mov     eax, [rbp+arg_18]
0x180036ee4  imul    eax, [rdi]
0x180036ee7  mov     [rdi], eax
0x180036ee9  jmp     loc_180036CB0
0x180036eee  mov     rcx, [rbp+38h]; this
0x180036ef2  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x180036ef9  mov     r9d, ebx; char *
0x180036efc  mov     edx, 5BFh; void *
0x180036f01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036f06  jmp     loc_180036CEC
```
