# LocalConvertSDToStringSD_Rev1

- ea: `0x18001e218`
- end: `0x18001e9fb`
- name: `LocalConvertSDToStringSD_Rev1`
- size: `2019`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002cf60`
- `0x180031d40`
- `0x180052b80`
- `0x180052d50`

## callees

- `0x18001d3d0`
- `0x18001dbb0`
- `0x18001e218`
- `0x18001ea04`
- `0x18001ea50`
- `0x18001ea7c`
- `0x18001fac0`
- `0x18001fcb0`
- `0x180020464`
- `0x180032de8`
- `0x180065042`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001e6df`
- `msvcrt!wcscpy_s` at `0x18001e786`
- `msvcrt!wcscpy_s` at `0x18001e832`
- `msvcrt!wcscpy_s` at `0x18001e6df`
- `msvcrt!wcscpy_s` at `0x18001e786`
- `msvcrt!wcscpy_s` at `0x18001e832`
- `msvcrt!swprintf_s` at `0x18001e5f2`
- `msvcrt!swprintf_s` at `0x18001e63c`
- `msvcrt!swprintf_s` at `0x18001e6a2`
- `msvcrt!swprintf_s` at `0x18001e73f`
- `msvcrt!swprintf_s` at `0x18001e7f3`
- `msvcrt!swprintf_s` at `0x18001e8a6`
- `msvcrt!swprintf_s` at `0x18001e5f2`
- `msvcrt!swprintf_s` at `0x18001e63c`
- `msvcrt!swprintf_s` at `0x18001e6a2`
- `msvcrt!swprintf_s` at `0x18001e73f`
- `msvcrt!swprintf_s` at `0x18001e7f3`
- `msvcrt!swprintf_s` at `0x18001e8a6`
- `ntdll!RtlValidSid` at `0x18001e93d`
- `ntdll!RtlValidSid` at `0x18001e94f`
- `ntdll!RtlValidSid` at `0x18001e93d`
- `ntdll!RtlValidSid` at `0x18001e94f`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18001e362`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18001e362`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x18001e33f`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x18001e33f`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18001e2b6`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18001e2b6`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x18001e300`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x18001e300`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18001e31e`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18001e31e`
- `ntdll!RtlNtStatusToDosError` at `0x18001e2c2`
- `ntdll!RtlNtStatusToDosError` at `0x18001e925`
- `ntdll!RtlNtStatusToDosError` at `0x18001e2c2`
- `ntdll!RtlNtStatusToDosError` at `0x18001e925`
- `KERNELBASE!LocalAlloc` at `0x18001e5ac`
- `KERNELBASE!LocalAlloc` at `0x18001e75f`
- `KERNELBASE!LocalAlloc` at `0x18001e860`
- `KERNELBASE!LocalAlloc` at `0x18001e983`
- `KERNELBASE!LocalAlloc` at `0x18001e5ac`
- `KERNELBASE!LocalAlloc` at `0x18001e75f`
- `KERNELBASE!LocalAlloc` at `0x18001e860`
- `KERNELBASE!LocalAlloc` at `0x18001e983`
- `KERNEL32!LocalFree` at `0x18001e2cd`
- `KERNEL32!LocalFree` at `0x18001e41c`
- `KERNEL32!LocalFree` at `0x18001e425`
- `KERNEL32!LocalFree` at `0x18001e42f`
- `KERNEL32!LocalFree` at `0x18001e439`
- `KERNEL32!LocalFree` at `0x18001e443`
- `KERNEL32!LocalFree` at `0x18001e44d`
- `KERNEL32!LocalFree` at `0x18001e457`
- `KERNEL32!LocalFree` at `0x18001e461`
- `KERNEL32!LocalFree` at `0x18001e2cd`
- `KERNEL32!LocalFree` at `0x18001e41c`
- `KERNEL32!LocalFree` at `0x18001e425`
- `KERNEL32!LocalFree` at `0x18001e42f`
- `KERNEL32!LocalFree` at `0x18001e439`
- `KERNEL32!LocalFree` at `0x18001e443`
- `KERNEL32!LocalFree` at `0x18001e44d`
- `KERNEL32!LocalFree` at `0x18001e457`
- `KERNEL32!LocalFree` at `0x18001e461`
- `KERNEL32!GetLastError` at `0x18001e9bc`
- `KERNEL32!GetLastError` at `0x18001e9bc`

## pseudocode

```c
ULONG __fastcall LocalConvertSDToStringSD_Rev1(
        _BYTE *a1,
        _BYTE *a2,
        char a3,
        void *a4,
        __int16 a5,
        wchar_t **a6,
        unsigned int *a7)
{
  __int64 v7; // r12
  LPWSTR v11; // r13
  __int16 v12; // bx
  ACL *v13; // rsi
  int OwnerSecurityDescriptor; // eax
  ULONG v15; // ebx
  unsigned int v17; // ebx
  int SaclSecurityDescriptor; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  int StringForSid; // esi
  PSID v24; // rbx
  __int64 *v25; // rax
  __int64 *v26; // rdi
  HLOCAL v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  unsigned __int8 v36; // dl
  unsigned int v37; // edi
  unsigned __int8 v38; // cl
  __int64 v39; // r12
  __int64 v40; // rax
  __int64 v41; // rax
  wchar_t *v42; // rax
  wchar_t **v43; // r14
  size_t v44; // r15
  __int64 v45; // r14
  __int64 v46; // rcx
  size_t v47; // rdx
  wchar_t *v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rax
  SIZE_T v52; // rbx
  wchar_t *v53; // rax
  const wchar_t *v54; // r8
  __int64 v55; // rax
  size_t v56; // rdx
  wchar_t *v57; // rcx
  wchar_t *v58; // rdx
  ACL *v59; // rax
  __int64 v60; // rax
  HLOCAL v61; // rax
  DWORD LastError; // eax
  __int64 v63; // [rsp+20h] [rbp-A1h]
  HLOCAL v64; // [rsp+28h] [rbp-99h]
  __int64 v65; // [rsp+30h] [rbp-91h]
  __int64 v66; // [rsp+40h] [rbp-81h]
  unsigned __int8 OwnerDefaulted; // [rsp+50h] [rbp-71h] BYREF
  unsigned __int8 DaclPresent[3]; // [rsp+51h] [rbp-70h] BYREF
  WORD Control; // [rsp+54h] [rbp-6Dh] BYREF
  SIZE_T uBytes; // [rsp+58h] [rbp-69h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-61h] BYREF
  PACL Sacl; // [rsp+68h] [rbp-59h] BYREF
  HLOCAL v73; // [rsp+70h] [rbp-51h] BYREF
  HLOCAL v74; // [rsp+78h] [rbp-49h] BYREF
  LPWSTR StringSid; // [rsp+80h] [rbp-41h] BYREF
  HLOCAL v76; // [rsp+88h] [rbp-39h] BYREF
  HLOCAL v77; // [rsp+90h] [rbp-31h] BYREF
  PSID Owner; // [rsp+98h] [rbp-29h] BYREF
  __int64 v79; // [rsp+A0h] [rbp-21h] BYREF
  PSID Group; // [rsp+A8h] [rbp-19h] BYREF
  PACL Dacl; // [rsp+B0h] [rbp-11h] BYREF
  HLOCAL v82; // [rsp+B8h] [rbp-9h]
  HLOCAL v83; // [rsp+C0h] [rbp-1h]
  unsigned __int8 SaclPresent; // [rsp+128h] [rbp+67h] BYREF

  v7 = 0;
  uBytes = 0;
  Owner = 0;
  Group = 0;
  v11 = 0;
  Dacl = 0;
  Sacl = 0;
  OwnerDefaulted = 0;
  SaclPresent = 0;
  DaclPresent[0] = 0;
  StringSid = 0;
  hMem = 0;
  v76 = 0;
  v77 = 0;
  Control = 0;
  v74 = 0;
  v73 = 0;
  if ( !a4 || !a6 )
    return 87;
  v12 = a5;
  v13 = 0;
  v82 = 0;
  if ( (a5 & 1) != 0 )
  {
    OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(a4, &Owner, &OwnerDefaulted);
    if ( OwnerSecurityDescriptor < 0 )
      goto LABEL_5;
  }
  if ( (v12 & 2) != 0 )
  {
    OwnerSecurityDescriptor = RtlGetGroupSecurityDescriptor(a4, &Group, &OwnerDefaulted);
    if ( OwnerSecurityDescriptor < 0 )
      goto LABEL_5;
  }
  if ( (v12 & 4) != 0 )
  {
    OwnerSecurityDescriptor = RtlGetDaclSecurityDescriptor(a4, DaclPresent, &Dacl, &OwnerDefaulted);
    if ( OwnerSecurityDescriptor < 0 )
      goto LABEL_5;
  }
  v17 = v12 & 0x1F8;
  if ( v17 )
  {
    SaclSecurityDescriptor = RtlGetSaclSecurityDescriptor(a4, &SaclPresent, &Sacl, &OwnerDefaulted);
    if ( SaclSecurityDescriptor < 0 )
      return RtlNtStatusToDosError(SaclSecurityDescriptor);
    if ( SaclPresent && Sacl )
    {
      SddlFilterSacl(Sacl, 0, &uBytes, v17);
      v59 = (ACL *)LocalAlloc(0x40u, (unsigned int)uBytes);
      v82 = v59;
      v13 = v59;
      if ( !v59 )
      {
        OwnerSecurityDescriptor = -1073741801;
        goto LABEL_5;
      }
      SddlFilterSacl(Sacl, v59, &uBytes, v17);
      Sacl = v13;
    }
  }
  OwnerSecurityDescriptor = RtlGetControlSecurityDescriptor(a4, &Control, (PULONG)&uBytes + 1);
  if ( OwnerSecurityDescriptor < 0 )
  {
LABEL_5:
    v15 = RtlNtStatusToDosError(OwnerSecurityDescriptor);
LABEL_6:
    LocalFree(v13);
    return v15;
  }
  if ( a1 && !RtlValidSid(a1) || a2 && !RtlValidSid(a2) )
  {
    v15 = 1337;
    goto LABEL_6;
  }
  v83 = 0;
  StringForSid = 0;
  if ( a1 )
  {
    EnterWaitSddlSidLookup();
    gbLookupTableInitialized = 0;
  }
  LOBYTE(v20) = 1;
  InitializeSidLookupTable(v20, v19, v21, v22);
  if ( a2 )
  {
    v61 = LocalAlloc(0x40u, 0x618u);
    v83 = v61;
    v7 = (__int64)v61;
    if ( v61 )
      memcpy_0(v61, SidLookupDomOrRootDomRelative, 0x618u);
    else
      StringForSid = 8;
  }
  v24 = Owner;
  if ( Owner )
  {
    v79 = 0;
    StringForSid = 0;
    LOBYTE(v64) = a3;
    v25 = LookupSidInTable(0, Owner, a1, a2, v7, (__int64)v64, (PSID *)&v79);
    v26 = v25;
    if ( v25 )
    {
      v51 = *((unsigned int *)v25 + 3);
    }
    else
    {
      if ( !v79 )
      {
        if ( ConvertSidToStringSidW(v24, &StringSid) )
        {
          v11 = StringSid;
        }
        else
        {
          LastError = GetLastError();
          v11 = StringSid;
          StringForSid = LastError;
        }
        goto LABEL_25;
      }
      v51 = 2;
    }
    v52 = 2 * v51 + 2;
    v53 = (wchar_t *)LocalAlloc(0x40u, v52);
    v11 = v53;
    if ( v53 )
    {
      v54 = (const wchar_t *)v26 + 1;
      if ( !v26 )
        v54 = L"SA";
      wcscpy_s(v53, v52 >> 1, v54);
    }
    else
    {
      StringForSid = 8;
    }
  }
LABEL_25:
  if ( StringForSid )
    goto LABEL_26;
  if ( Group )
  {
    LOBYTE(v64) = a3;
    StringForSid = LocalGetStringForSid(Group, (LPWSTR *)&hMem, v7, (__int64)v64);
    if ( StringForSid )
      goto LABEL_26;
  }
  if ( Control )
  {
    StringForSid = LocalGetStringForControl(Control, 1, &v74);
    if ( StringForSid )
      goto LABEL_26;
    if ( Control )
    {
      StringForSid = LocalGetStringForControl(Control, 2, &v73);
      if ( StringForSid )
        goto LABEL_26;
    }
  }
  v36 = SaclPresent;
  v37 = 0;
  if ( SaclPresent )
  {
    LOBYTE(v66) = a3;
    StringForSid = LocalConvertAclToString((__int64)Sacl, SaclPresent, 0, (wchar_t **)&v76, &uBytes, a1, a2, v7, v66);
    if ( StringForSid )
      goto LABEL_26;
    v37 = uBytes;
    v36 = SaclPresent;
  }
  v38 = DaclPresent[0];
  if ( DaclPresent[0] )
  {
    LOBYTE(v66) = a3;
    StringForSid = LocalConvertAclToString((__int64)Dacl, DaclPresent[0], 1, (wchar_t **)&v77, &uBytes, a1, a2, v7, v66);
    if ( StringForSid )
      goto LABEL_26;
    v37 += uBytes;
    v36 = SaclPresent;
    v38 = DaclPresent[0];
  }
  v39 = -1;
  if ( v11 )
  {
    v40 = -1;
    do
      ++v40;
    while ( v11[v40] );
    v37 += 2 * v40 + 4;
  }
  v27 = hMem;
  if ( hMem )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_WORD *)hMem + v41) );
    v37 += 2 * v41 + 4;
  }
  if ( v38 )
  {
    v37 += 4;
    if ( v74 )
    {
      v55 = -1;
      do
        ++v55;
      while ( *((_WORD *)v74 + v55) );
      v37 += 2 * v55;
    }
  }
  if ( v36 )
  {
    v37 += 4;
    if ( v73 )
    {
      v60 = -1;
      do
        ++v60;
      while ( *((_WORD *)v73 + v60) );
      v37 += 2 * v60;
    }
  }
  v42 = (wchar_t *)LocalAlloc(0x40u, v37 + 2LL);
  v43 = a6;
  *a6 = v42;
  if ( !v42 )
  {
    StringForSid = 8;
    goto LABEL_27;
  }
  v44 = ((unsigned __int64)v37 + 2) >> 1;
  if ( v11 )
  {
    v64 = v11;
    LODWORD(v63) = 58;
    swprintf_s(v42, v44, L"%ws%wc%ws", L"O");
    v42 = *v43;
    v45 = -1;
    do
      ++v45;
    while ( v42[v45] );
  }
  else
  {
    LODWORD(v45) = 0;
  }
  if ( hMem )
  {
    v64 = hMem;
    LODWORD(v63) = 58;
    swprintf_s(&v42[(unsigned int)v45], v44 - (unsigned int)v45, L"%ws%wc%ws", L"G");
    v42 = *a6;
    v46 = -1;
    do
      ++v46;
    while ( (*a6)[(unsigned int)v45 + v46] );
    HIDWORD(uBytes) = v46;
    LODWORD(v45) = v46 + v45;
  }
  if ( DaclPresent[0] )
  {
    v47 = v44 - (unsigned int)v45;
    v48 = &v42[(unsigned int)v45];
    if ( v74 )
    {
      v64 = v74;
      LODWORD(v63) = 58;
      swprintf_s(v48, v47, L"%ws%wc%ws", L"D");
    }
    else
    {
      LODWORD(v63) = 58;
      swprintf_s(v48, v47, L"%ws%wc", L"D");
    }
    v49 = -1;
    v42 = *a6;
    do
      ++v49;
    while ( (*a6)[(unsigned int)v45 + v49] );
    v45 = (unsigned int)(v49 + v45);
    HIDWORD(uBytes) = v49;
    if ( v77 )
    {
      wcscpy_s(&v42[v45], v44 - (unsigned int)v45, (const wchar_t *)v77);
      v42 = *a6;
      v50 = -1;
      do
        ++v50;
      while ( (*a6)[v45 + v50] );
      HIDWORD(uBytes) = v50;
      LODWORD(v45) = v50 + v45;
    }
  }
  if ( SaclPresent )
  {
    v56 = v44 - (unsigned int)v45;
    v57 = &v42[(unsigned int)v45];
    if ( v73 )
    {
      v64 = v73;
      LODWORD(v63) = 58;
      swprintf_s(v57, v56, L"%ws%wc%ws", L"S");
    }
    else
    {
      LODWORD(v63) = 58;
      swprintf_s(v57, v56, L"%ws%wc", L"S");
    }
    v58 = *a6;
    do
      ++v39;
    while ( (*a6)[(unsigned int)v45 + v39] );
    HIDWORD(uBytes) = v39;
    if ( v76 )
      wcscpy_s(&v58[(unsigned int)(v39 + v45)], v44 - (unsigned int)(v39 + v45), (const wchar_t *)v76);
  }
  if ( a7 )
    *a7 = v37 >> 1;
LABEL_26:
  v27 = hMem;
LABEL_27:
  LocalFree(v11);
  LocalFree(v27);
  LocalFree(v76);
  LocalFree(v77);
  LocalFree(v73);
  LocalFree(v74);
  LocalFree(v82);
  LocalFree(v83);
  LOBYTE(v28) = 2;
  InitializeSidLookupTable(v28, v29, v30, v31);
  if ( a1 )
  {
    gbLookupTableInitialized = 0;
    LeaveWaitSddlSidLookup(v33, v32, v34, v35, v63, v64, v65);
  }
  return StringForSid;
}

```

## disassembly

```asm
0x18001e218  mov     [rsp-8+arg_8], rbx
0x18001e21d  mov     [rsp-8+Sid], rcx
0x18001e222  push    rbp
0x18001e223  push    rsi
0x18001e224  push    rdi
0x18001e225  push    r12
0x18001e227  push    r13
0x18001e229  push    r14
0x18001e22b  push    r15
0x18001e22d  lea     rbp, [rsp-0Fh]
0x18001e232  sub     rsp, 0D0h
0x18001e239  xor     r12d, r12d
0x18001e23c  mov     rdi, r9
0x18001e23f  mov     dword ptr [rbp+3Fh+uBytes], r12d
0x18001e243  mov     r15b, r8b
0x18001e246  mov     [rbp+3Fh+Owner], r12
0x18001e24a  mov     r14, rdx
0x18001e24d  mov     [rbp+3Fh+Group], r12
0x18001e251  mov     r13d, r12d
0x18001e254  mov     [rbp+3Fh+Dacl], r12
0x18001e258  mov     [rbp+3Fh+Sacl], r12
0x18001e25c  mov     [rbp+3Fh+OwnerDefaulted], r12b
0x18001e260  mov     [rbp+3Fh+SaclPresent], r12b
0x18001e264  mov     [rbp+3Fh+DaclPresent], r12b
0x18001e268  mov     [rbp+3Fh+StringSid], r12
0x18001e26c  mov     [rbp+3Fh+hMem], r12
0x18001e270  mov     [rbp+3Fh+var_78], r12
0x18001e274  mov     [rbp+3Fh+var_70], r12
0x18001e278  mov     [rbp+3Fh+Control], r12w
0x18001e27d  mov     dword ptr [rbp+3Fh+uBytes+4], r12d
0x18001e281  mov     [rbp+3Fh+var_88], r12
0x18001e285  mov     [rbp+3Fh+var_90], r12
0x18001e289  test    r9, r9
0x18001e28c  jz      loc_18001E9F1
0x18001e292  cmp     [rbp+3Fh+arg_28], r12
0x18001e296  jz      loc_18001E9F1
0x18001e29c  mov     ebx, dword ptr [rbp+3Fh+arg_20]
0x18001e29f  mov     esi, r12d
0x18001e2a2  mov     [rbp+3Fh+var_48], r12
0x18001e2a6  test    bl, 1
0x18001e2a9  jz      short loc_18001E2F0
0x18001e2ab  lea     r8, [rbp+3Fh+OwnerDefaulted]; OwnerDefaulted
0x18001e2af  mov     rcx, r9; SecurityDescriptor
0x18001e2b2  lea     rdx, [rbp+3Fh+Owner]; Owner
0x18001e2b6  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x18001e2bc  test    eax, eax
0x18001e2be  jns     short loc_18001E2F0
0x18001e2c0  mov     ecx, eax; Status
0x18001e2c2  call    cs:__imp_RtlNtStatusToDosError
0x18001e2c8  mov     ebx, eax
0x18001e2ca  mov     rcx, rsi; hMem
0x18001e2cd  call    cs:__imp_LocalFree
0x18001e2d3  mov     eax, ebx
0x18001e2d5  mov     rbx, [rsp+100h+arg_8]
0x18001e2dd  add     rsp, 0D0h
0x18001e2e4  pop     r15
0x18001e2e6  pop     r14
0x18001e2e8  pop     r13
0x18001e2ea  pop     r12
0x18001e2ec  pop     rdi
0x18001e2ed  pop     rsi
0x18001e2ee  pop     rbp
0x18001e2ef  retn
0x18001e2f0  test    bl, 2
0x18001e2f3  jz      short loc_18001E30A
0x18001e2f5  lea     r8, [rbp+3Fh+OwnerDefaulted]; GroupDefaulted
0x18001e2f9  mov     rcx, rdi; SecurityDescriptor
0x18001e2fc  lea     rdx, [rbp+3Fh+Group]; Group
0x18001e300  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x18001e306  test    eax, eax
0x18001e308  js      short loc_18001E2C0
0x18001e30a  test    bl, 4
0x18001e30d  jz      short loc_18001E328
0x18001e30f  lea     r9, [rbp+3Fh+OwnerDefaulted]; DaclDefaulted
0x18001e313  mov     rcx, rdi; SecurityDescriptor
0x18001e316  lea     r8, [rbp+3Fh+Dacl]; Dacl
0x18001e31a  lea     rdx, [rbp+3Fh+DaclPresent]; DaclPresent
0x18001e31e  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18001e324  test    eax, eax
0x18001e326  js      short loc_18001E2C0
0x18001e328  and     ebx, 1F8h
0x18001e32e  jz      short loc_18001E357
0x18001e330  lea     r9, [rbp+3Fh+OwnerDefaulted]; SaclDefaulted
0x18001e334  mov     rcx, rdi; SecurityDescriptor
0x18001e337  lea     r8, [rbp+3Fh+Sacl]; Sacl
0x18001e33b  lea     rdx, [rbp+3Fh+SaclPresent]; SaclPresent
0x18001e33f  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x18001e345  test    eax, eax
0x18001e347  js      loc_18001E923
0x18001e34d  cmp     [rbp+3Fh+SaclPresent], r12b
0x18001e351  jnz     loc_18001E83D
0x18001e357  lea     r8, [rbp+3Fh+uBytes+4]; Revision
0x18001e35b  mov     rcx, rdi; SecurityDescriptor
0x18001e35e  lea     rdx, [rbp+3Fh+Control]; Control
0x18001e362  call    cs:__imp_RtlGetControlSecurityDescriptor
0x18001e368  test    eax, eax
0x18001e36a  js      loc_18001E2C0
0x18001e370  mov     rdi, [rbp+3Fh+Sid]
0x18001e374  test    rdi, rdi
0x18001e377  jnz     loc_18001E93A
0x18001e37d  test    r14, r14
0x18001e380  jnz     loc_18001E94C
0x18001e386  mov     [rbp+3Fh+var_40], r12
0x18001e38a  mov     esi, r12d
0x18001e38d  test    rdi, rdi
0x18001e390  jnz     loc_18001E967
0x18001e396  mov     cl, 1
0x18001e398  call    InitializeSidLookupTable
0x18001e39d  xor     r8d, r8d
0x18001e3a0  test    r14, r14
0x18001e3a3  jnz     loc_18001E977
0x18001e3a9  mov     rbx, [rbp+3Fh+Owner]
0x18001e3ad  test    rbx, rbx
0x18001e3b0  jz      short loc_18001E411
0x18001e3b2  lea     rax, [rbp+3Fh+var_60]
0x18001e3b6  mov     [rbp+3Fh+var_60], r8
0x18001e3ba  mov     [rsp+100h+var_D0], rax; __int64
0x18001e3bf  mov     esi, r8d
0x18001e3c2  mov     byte ptr [rsp+100h+var_D8], r15b; __int64
0x18001e3c7  mov     r9, r14
0x18001e3ca  mov     r8, rdi
0x18001e3cd  mov     [rsp+100h+var_E0], r12; __int64
0x18001e3d2  mov     rdx, rbx; Sid2
0x18001e3d5  xor     ecx, ecx; String1
0x18001e3d7  call    LookupSidInTable
0x18001e3dc  mov     rdi, rax
0x18001e3df  test    rax, rax
0x18001e3e2  jnz     loc_18001E9CD
0x18001e3e8  cmp     [rbp+3Fh+var_60], r13
0x18001e3ec  jnz     loc_18001E74A
0x18001e3f2  lea     rdx, [rbp+3Fh+StringSid]; StringSid
0x18001e3f6  mov     rcx, rbx; Sid
0x18001e3f9  call    ConvertSidToStringSidW
0x18001e3fe  xor     r8d, r8d
0x18001e401  test    eax, eax
0x18001e403  jz      loc_18001E9BC
0x18001e409  mov     r13, [rbp+3Fh+StringSid]
0x18001e40d  mov     rdi, [rbp+3Fh+Sid]
0x18001e411  test    esi, esi
0x18001e413  jz      short loc_18001E481
0x18001e415  mov     rbx, [rbp+3Fh+hMem]
0x18001e419  mov     rcx, r13; hMem
0x18001e41c  call    cs:__imp_LocalFree
0x18001e422  mov     rcx, rbx; hMem
0x18001e425  call    cs:__imp_LocalFree
0x18001e42b  mov     rcx, [rbp+3Fh+var_78]; hMem
0x18001e42f  call    cs:__imp_LocalFree
0x18001e435  mov     rcx, [rbp+3Fh+var_70]; hMem
0x18001e439  call    cs:__imp_LocalFree
0x18001e43f  mov     rcx, [rbp+3Fh+var_90]; hMem
0x18001e443  call    cs:__imp_LocalFree
0x18001e449  mov     rcx, [rbp+3Fh+var_88]; hMem
0x18001e44d  call    cs:__imp_LocalFree
0x18001e453  mov     rcx, [rbp+3Fh+var_48]; hMem
0x18001e457  call    cs:__imp_LocalFree
0x18001e45d  mov     rcx, [rbp+3Fh+var_40]; hMem
0x18001e461  call    cs:__imp_LocalFree
0x18001e467  mov     cl, 2
0x18001e469  call    InitializeSidLookupTable
0x18001e46e  xor     eax, eax
0x18001e470  cmp     [rbp+3Fh+Sid], rax
0x18001e474  jnz     loc_18001E9E1
0x18001e47a  mov     eax, esi
0x18001e47c  jmp     loc_18001E2D5
0x18001e481  mov     rcx, [rbp+3Fh+Group]; Sid2
0x18001e485  test    rcx, rcx
0x18001e488  jz      short loc_18001E4B0
0x18001e48a  mov     byte ptr [rsp+100h+var_D8], r15b; __int64
0x18001e48f  lea     rdx, [rbp+3Fh+hMem]; StringSid
0x18001e493  mov     r9, r14
0x18001e496  mov     [rsp+100h+var_E0], r12; __int64
0x18001e49b  mov     r8, rdi
0x18001e49e  call    LocalGetStringForSid
0x18001e4a3  xor     r8d, r8d
0x18001e4a6  mov     esi, eax
0x18001e4a8  test    eax, eax
0x18001e4aa  jnz     loc_18001E415
0x18001e4b0  movzx   ecx, [rbp+3Fh+Control]
0x18001e4b4  test    cx, cx
0x18001e4b7  jz      short loc_18001E4F6
0x18001e4b9  lea     r8, [rbp+3Fh+var_88]
0x18001e4bd  mov     edx, 1
0x18001e4c2  call    LocalGetStringForControl
0x18001e4c7  xor     r8d, r8d
0x18001e4ca  mov     esi, eax
0x18001e4cc  test    eax, eax
0x18001e4ce  jnz     loc_18001E415
0x18001e4d4  movzx   ecx, [rbp+3Fh+Control]
0x18001e4d8  test    cx, cx
0x18001e4db  jz      short loc_18001E4F6
0x18001e4dd  lea     r8, [rbp+3Fh+var_90]
0x18001e4e1  lea     edx, [rax+2]
0x18001e4e4  call    LocalGetStringForControl
0x18001e4e9  xor     r8d, r8d
0x18001e4ec  mov     esi, eax
0x18001e4ee  test    eax, eax
0x18001e4f0  jnz     loc_18001E415
0x18001e4f6  mov     dl, [rbp+3Fh+SaclPresent]
0x18001e4f9  mov     edi, r8d
0x18001e4fc  mov     rbx, [rbp+3Fh+Sid]
0x18001e500  test    dl, dl
0x18001e502  jnz     loc_18001E8DE
0x18001e508  mov     cl, [rbp+3Fh+DaclPresent]
0x18001e50b  test    cl, cl
0x18001e50d  jz      short loc_18001E554
0x18001e50f  mov     [rsp+100h+var_C0], r15b
0x18001e514  lea     rax, [rbp+3Fh+uBytes]
0x18001e518  mov     [rsp+100h+var_C8], r12
0x18001e51d  lea     r9, [rbp+3Fh+var_70]
0x18001e521  mov     [rsp+100h+var_D0], r14
0x18001e526  mov     dl, cl
0x18001e528  mov     rcx, [rbp+3Fh+Dacl]
0x18001e52c  mov     r8b, 1
0x18001e52f  mov     [rsp+100h+var_D8], rbx
0x18001e534  mov     [rsp+100h+var_E0], rax
0x18001e539  call    LocalConvertAclToString
0x18001e53e  xor     r8d, r8d
0x18001e541  mov     esi, eax
0x18001e543  test    eax, eax
0x18001e545  jnz     loc_18001E415
0x18001e54b  add     edi, dword ptr [rbp+3Fh+uBytes]
0x18001e54e  mov     dl, [rbp+3Fh+SaclPresent]
0x18001e551  mov     cl, [rbp+3Fh+DaclPresent]
0x18001e554  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001e558  test    r13, r13
0x18001e55b  jz      short loc_18001E571
0x18001e55d  mov     rax, r12
0x18001e560  inc     rax
0x18001e563  cmp     [r13+rax*2+0], r8w
0x18001e569  jnz     short loc_18001E560
0x18001e56b  lea     edi, [rdi+rax*2]
0x18001e56e  add     edi, 4
0x18001e571  mov     rbx, [rbp+3Fh+hMem]
0x18001e575  test    rbx, rbx
0x18001e578  jz      short loc_18001E58D
0x18001e57a  mov     rax, r12
0x18001e57d  inc     rax
0x18001e580  cmp     [rbx+rax*2], r8w
0x18001e585  jnz     short loc_18001E57D
0x18001e587  lea     edi, [rdi+rax*2]
0x18001e58a  add     edi, 4
0x18001e58d  test    cl, cl
0x18001e58f  jnz     loc_18001E794
0x18001e595  test    dl, dl
0x18001e597  jnz     loc_18001E8B1
0x18001e59d  mov     r15d, edi
0x18001e5a0  mov     ecx, 40h ; '@'; uFlags
0x18001e5a5  add     r15, 2
0x18001e5a9  mov     rdx, r15; uBytes
0x18001e5ac  call    cs:__imp_LocalAlloc
0x18001e5b2  mov     r14, [rbp+3Fh+arg_28]
0x18001e5b6  xor     r9d, r9d
0x18001e5b9  mov     [r14], rax
0x18001e5bc  test    rax, rax
0x18001e5bf  jz      loc_18001E726
0x18001e5c5  shr     r15, 1
0x18001e5c8  test    r13, r13
0x18001e5cb  jz      loc_18001E8D6
0x18001e5d1  mov     [rsp+100h+var_D8], r13
0x18001e5d6  lea     r9, aO; "O"
0x18001e5dd  lea     r8, aWsWcWs; "%ws%wc%ws"
0x18001e5e4  mov     dword ptr [rsp+100h+var_E0], 3Ah ; ':'
0x18001e5ec  mov     rdx, r15; BufferCount
0x18001e5ef  mov     rcx, rax; Buffer
0x18001e5f2  call    cs:__imp_swprintf_s
0x18001e5f8  mov     rax, [r14]
0x18001e5fb  xor     r9d, r9d
0x18001e5fe  mov     r14, r12
0x18001e601  inc     r14
0x18001e604  cmp     [rax+r14*2], r9w
0x18001e609  jnz     short loc_18001E601
0x18001e60b  mov     r8, [rbp+3Fh+hMem]
0x18001e60f  test    r8, r8
0x18001e612  jz      short loc_18001E663
0x18001e614  mov     [rsp+100h+var_D8], r8
0x18001e619  lea     r9, aG; "G"
0x18001e620  mov     ebx, r14d
0x18001e623  lea     r8, aWsWcWs; "%ws%wc%ws"
0x18001e62a  mov     rdx, r15
0x18001e62d  mov     dword ptr [rsp+100h+var_E0], 3Ah ; ':'
0x18001e635  sub     rdx, rbx; BufferCount
0x18001e638  lea     rcx, [rax+rbx*2]; Buffer
0x18001e63c  call    cs:__imp_swprintf_s
0x18001e642  mov     rcx, [rbp+3Fh+arg_28]
0x18001e646  xor     r9d, r9d
0x18001e649  mov     rax, [rcx]
0x18001e64c  mov     rcx, r12
0x18001e64f  lea     rdx, [rax+rbx*2]
0x18001e653  inc     rcx
0x18001e656  cmp     [rdx+rcx*2], r9w
0x18001e65b  jnz     short loc_18001E653
0x18001e65d  mov     dword ptr [rbp+3Fh+uBytes+4], ecx
0x18001e660  add     r14d, ecx
0x18001e663  cmp     [rbp+3Fh+DaclPresent], r9b
0x18001e667  jz      loc_18001E706
0x18001e66d  mov     ebx, r14d
0x18001e670  lea     r9, aD_1; "D"
0x18001e677  mov     rdx, r15
0x18001e67a  sub     rdx, rbx; BufferCount
0x18001e67d  lea     rcx, [rax+rbx*2]; Buffer
  ... truncated ...
```
