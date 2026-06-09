# LocalConvertSDToStringSD_Rev1

- ea: `0x18001cfb8`
- end: `0x18001d864`
- name: `LocalConvertSDToStringSD_Rev1`
- size: `2220`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002fb40`
- `0x180035390`
- `0x18005e570`
- `0x18005e790`

## callees

- `0x18001c000`
- `0x18001c890`
- `0x18001cfb8`
- `0x18001d86c`
- `0x18001d8c4`
- `0x18001d900`
- `0x18001db3c`
- `0x18001e38c`
- `0x18001f4ac`
- `0x1800368c4`
- `0x180072042`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001d4fa`
- `msvcrt!wcscpy_s` at `0x18001d5b3`
- `msvcrt!wcscpy_s` at `0x18001d66b`
- `msvcrt!wcscpy_s` at `0x18001d4fa`
- `msvcrt!wcscpy_s` at `0x18001d5b3`
- `msvcrt!wcscpy_s` at `0x18001d66b`
- `msvcrt!swprintf_s` at `0x18001d3fb`
- `msvcrt!swprintf_s` at `0x18001d44b`
- `msvcrt!swprintf_s` at `0x18001d4b7`
- `msvcrt!swprintf_s` at `0x18001d560`
- `msvcrt!swprintf_s` at `0x18001d626`
- `msvcrt!swprintf_s` at `0x18001d6eb`
- `msvcrt!swprintf_s` at `0x18001d3fb`
- `msvcrt!swprintf_s` at `0x18001d44b`
- `msvcrt!swprintf_s` at `0x18001d4b7`
- `msvcrt!swprintf_s` at `0x18001d560`
- `msvcrt!swprintf_s` at `0x18001d626`
- `msvcrt!swprintf_s` at `0x18001d6eb`
- `ntdll!RtlValidSid` at `0x18001d78e`
- `ntdll!RtlValidSid` at `0x18001d7a6`
- `ntdll!RtlValidSid` at `0x18001d78e`
- `ntdll!RtlValidSid` at `0x18001d7a6`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18001d12b`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18001d12b`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x18001d102`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x18001d102`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18001d056`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18001d056`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x18001d0b3`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x18001d0b3`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18001d0d7`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18001d0d7`
- `ntdll!RtlNtStatusToDosError` at `0x18001d068`
- `ntdll!RtlNtStatusToDosError` at `0x18001d770`
- `ntdll!RtlNtStatusToDosError` at `0x18001d068`
- `ntdll!RtlNtStatusToDosError` at `0x18001d770`
- `KERNELBASE!LocalAlloc` at `0x18001d3af`
- `KERNELBASE!LocalAlloc` at `0x18001d586`
- `KERNELBASE!LocalAlloc` at `0x18001d69f`
- `KERNELBASE!LocalAlloc` at `0x18001d7e0`
- `KERNELBASE!LocalAlloc` at `0x18001d3af`
- `KERNELBASE!LocalAlloc` at `0x18001d586`
- `KERNELBASE!LocalAlloc` at `0x18001d69f`
- `KERNELBASE!LocalAlloc` at `0x18001d7e0`
- `KERNEL32!LocalFree` at `0x18001d079`
- `KERNEL32!LocalFree` at `0x18001d1ef`
- `KERNEL32!LocalFree` at `0x18001d1fe`
- `KERNEL32!LocalFree` at `0x18001d20e`
- `KERNEL32!LocalFree` at `0x18001d21e`
- `KERNEL32!LocalFree` at `0x18001d22e`
- `KERNEL32!LocalFree` at `0x18001d23e`
- `KERNEL32!LocalFree` at `0x18001d24e`
- `KERNEL32!LocalFree` at `0x18001d25e`
- `KERNEL32!LocalFree` at `0x18001d079`
- `KERNEL32!LocalFree` at `0x18001d1ef`
- `KERNEL32!LocalFree` at `0x18001d1fe`
- `KERNEL32!LocalFree` at `0x18001d20e`
- `KERNEL32!LocalFree` at `0x18001d21e`
- `KERNEL32!LocalFree` at `0x18001d22e`
- `KERNEL32!LocalFree` at `0x18001d23e`
- `KERNEL32!LocalFree` at `0x18001d24e`
- `KERNEL32!LocalFree` at `0x18001d25e`
- `KERNEL32!GetLastError` at `0x18001d81f`
- `KERNEL32!GetLastError` at `0x18001d81f`

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
0x18001cfb8  mov     [rsp-8+arg_8], rbx
0x18001cfbd  mov     [rsp-8+Sid], rcx
0x18001cfc2  push    rbp
0x18001cfc3  push    rsi
0x18001cfc4  push    rdi
0x18001cfc5  push    r12
0x18001cfc7  push    r13
0x18001cfc9  push    r14
0x18001cfcb  push    r15
0x18001cfcd  lea     rbp, [rsp-0Fh]
0x18001cfd2  sub     rsp, 0D0h
0x18001cfd9  xor     r12d, r12d
0x18001cfdc  mov     rdi, r9
0x18001cfdf  mov     dword ptr [rbp+3Fh+uBytes], r12d
0x18001cfe3  mov     r15b, r8b
0x18001cfe6  mov     [rbp+3Fh+Owner], r12
0x18001cfea  mov     r14, rdx
0x18001cfed  mov     [rbp+3Fh+Group], r12
0x18001cff1  mov     r13d, r12d
0x18001cff4  mov     [rbp+3Fh+Dacl], r12
0x18001cff8  mov     [rbp+3Fh+Sacl], r12
0x18001cffc  mov     [rbp+3Fh+OwnerDefaulted], r12b
0x18001d000  mov     [rbp+3Fh+SaclPresent], r12b
0x18001d004  mov     [rbp+3Fh+DaclPresent], r12b
0x18001d008  mov     [rbp+3Fh+StringSid], r12
0x18001d00c  mov     [rbp+3Fh+hMem], r12
0x18001d010  mov     [rbp+3Fh+var_78], r12
0x18001d014  mov     [rbp+3Fh+var_70], r12
0x18001d018  mov     [rbp+3Fh+Control], r12w
0x18001d01d  mov     dword ptr [rbp+3Fh+uBytes+4], r12d
0x18001d021  mov     [rbp+3Fh+var_88], r12
0x18001d025  mov     [rbp+3Fh+var_90], r12
0x18001d029  test    r9, r9
0x18001d02c  jz      loc_18001D85A
0x18001d032  cmp     [rbp+3Fh+arg_28], r12
0x18001d036  jz      loc_18001D85A
0x18001d03c  mov     ebx, dword ptr [rbp+3Fh+arg_20]
0x18001d03f  mov     esi, r12d
0x18001d042  mov     [rbp+3Fh+var_48], r12
0x18001d046  test    bl, 1
0x18001d049  jz      short loc_18001D0A3
0x18001d04b  lea     r8, [rbp+3Fh+OwnerDefaulted]; OwnerDefaulted
0x18001d04f  mov     rcx, r9; SecurityDescriptor
0x18001d052  lea     rdx, [rbp+3Fh+Owner]; Owner
0x18001d056  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x18001d05d  nop     dword ptr [rax+rax+00h]
0x18001d062  test    eax, eax
0x18001d064  jns     short loc_18001D0A3
0x18001d066  mov     ecx, eax; Status
0x18001d068  call    cs:__imp_RtlNtStatusToDosError
0x18001d06f  nop     dword ptr [rax+rax+00h]
0x18001d074  mov     ebx, eax
0x18001d076  mov     rcx, rsi; hMem
0x18001d079  call    cs:__imp_LocalFree
0x18001d080  nop     dword ptr [rax+rax+00h]
0x18001d085  mov     eax, ebx
0x18001d087  mov     rbx, [rsp+100h+arg_8]
0x18001d08f  add     rsp, 0D0h
0x18001d096  pop     r15
0x18001d098  pop     r14
0x18001d09a  pop     r13
0x18001d09c  pop     r12
0x18001d09e  pop     rdi
0x18001d09f  pop     rsi
0x18001d0a0  pop     rbp
0x18001d0a1  retn
0x18001d0a3  test    bl, 2
0x18001d0a6  jz      short loc_18001D0C3
0x18001d0a8  lea     r8, [rbp+3Fh+OwnerDefaulted]; GroupDefaulted
0x18001d0ac  mov     rcx, rdi; SecurityDescriptor
0x18001d0af  lea     rdx, [rbp+3Fh+Group]; Group
0x18001d0b3  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x18001d0ba  nop     dword ptr [rax+rax+00h]
0x18001d0bf  test    eax, eax
0x18001d0c1  js      short loc_18001D066
0x18001d0c3  test    bl, 4
0x18001d0c6  jz      short loc_18001D0EB
0x18001d0c8  lea     r9, [rbp+3Fh+OwnerDefaulted]; DaclDefaulted
0x18001d0cc  mov     rcx, rdi; SecurityDescriptor
0x18001d0cf  lea     r8, [rbp+3Fh+Dacl]; Dacl
0x18001d0d3  lea     rdx, [rbp+3Fh+DaclPresent]; DaclPresent
0x18001d0d7  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18001d0de  nop     dword ptr [rax+rax+00h]
0x18001d0e3  test    eax, eax
0x18001d0e5  js      loc_18001D066
0x18001d0eb  and     ebx, 1F8h
0x18001d0f1  jz      short loc_18001D120
0x18001d0f3  lea     r9, [rbp+3Fh+OwnerDefaulted]; SaclDefaulted
0x18001d0f7  mov     rcx, rdi; SecurityDescriptor
0x18001d0fa  lea     r8, [rbp+3Fh+Sacl]; Sacl
0x18001d0fe  lea     rdx, [rbp+3Fh+SaclPresent]; SaclPresent
0x18001d102  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x18001d109  nop     dword ptr [rax+rax+00h]
0x18001d10e  test    eax, eax
0x18001d110  js      loc_18001D76E
0x18001d116  cmp     [rbp+3Fh+SaclPresent], r12b
0x18001d11a  jnz     loc_18001D67C
0x18001d120  lea     r8, [rbp+3Fh+uBytes+4]; Revision
0x18001d124  mov     rcx, rdi; SecurityDescriptor
0x18001d127  lea     rdx, [rbp+3Fh+Control]; Control
0x18001d12b  call    cs:__imp_RtlGetControlSecurityDescriptor
0x18001d132  nop     dword ptr [rax+rax+00h]
0x18001d137  test    eax, eax
0x18001d139  js      loc_18001D066
0x18001d13f  mov     rdi, [rbp+3Fh+Sid]
0x18001d143  test    rdi, rdi
0x18001d146  jnz     loc_18001D78B
0x18001d14c  test    r14, r14
0x18001d14f  jnz     loc_18001D7A3
0x18001d155  mov     [rbp+3Fh+var_40], r12
0x18001d159  mov     esi, r12d
0x18001d15c  test    rdi, rdi
0x18001d15f  jnz     loc_18001D7C4
0x18001d165  mov     cl, 1
0x18001d167  call    InitializeSidLookupTable
0x18001d16c  xor     r8d, r8d
0x18001d16f  test    r14, r14
0x18001d172  jnz     loc_18001D7D4
0x18001d178  mov     rbx, [rbp+3Fh+Owner]
0x18001d17c  test    rbx, rbx
0x18001d17f  jz      short loc_18001D1E0
0x18001d181  lea     rax, [rbp+3Fh+var_60]
0x18001d185  mov     [rbp+3Fh+var_60], r8
0x18001d189  mov     [rsp+100h+var_D0], rax; __int64
0x18001d18e  mov     esi, r8d
0x18001d191  mov     byte ptr [rsp+100h+var_D8], r15b; __int64
0x18001d196  mov     r9, r14
0x18001d199  mov     r8, rdi
0x18001d19c  mov     [rsp+100h+var_E0], r12; __int64
0x18001d1a1  mov     rdx, rbx; Sid2
0x18001d1a4  xor     ecx, ecx; String1
0x18001d1a6  call    LookupSidInTable
0x18001d1ab  mov     rdi, rax
0x18001d1ae  test    rax, rax
0x18001d1b1  jnz     loc_18001D836
0x18001d1b7  cmp     [rbp+3Fh+var_60], r13
0x18001d1bb  jnz     loc_18001D571
0x18001d1c1  lea     rdx, [rbp+3Fh+StringSid]; StringSid
0x18001d1c5  mov     rcx, rbx; Sid
0x18001d1c8  call    ConvertSidToStringSidW
0x18001d1cd  xor     r8d, r8d
0x18001d1d0  test    eax, eax
0x18001d1d2  jz      loc_18001D81F
0x18001d1d8  mov     r13, [rbp+3Fh+StringSid]
0x18001d1dc  mov     rdi, [rbp+3Fh+Sid]
0x18001d1e0  test    esi, esi
0x18001d1e2  jz      loc_18001D284
0x18001d1e8  mov     rbx, [rbp+3Fh+hMem]
0x18001d1ec  mov     rcx, r13; hMem
0x18001d1ef  call    cs:__imp_LocalFree
0x18001d1f6  nop     dword ptr [rax+rax+00h]
0x18001d1fb  mov     rcx, rbx; hMem
0x18001d1fe  call    cs:__imp_LocalFree
0x18001d205  nop     dword ptr [rax+rax+00h]
0x18001d20a  mov     rcx, [rbp+3Fh+var_78]; hMem
0x18001d20e  call    cs:__imp_LocalFree
0x18001d215  nop     dword ptr [rax+rax+00h]
0x18001d21a  mov     rcx, [rbp+3Fh+var_70]; hMem
0x18001d21e  call    cs:__imp_LocalFree
0x18001d225  nop     dword ptr [rax+rax+00h]
0x18001d22a  mov     rcx, [rbp+3Fh+var_90]; hMem
0x18001d22e  call    cs:__imp_LocalFree
0x18001d235  nop     dword ptr [rax+rax+00h]
0x18001d23a  mov     rcx, [rbp+3Fh+var_88]; hMem
0x18001d23e  call    cs:__imp_LocalFree
0x18001d245  nop     dword ptr [rax+rax+00h]
0x18001d24a  mov     rcx, [rbp+3Fh+var_48]; hMem
0x18001d24e  call    cs:__imp_LocalFree
0x18001d255  nop     dword ptr [rax+rax+00h]
0x18001d25a  mov     rcx, [rbp+3Fh+var_40]; hMem
0x18001d25e  call    cs:__imp_LocalFree
0x18001d265  nop     dword ptr [rax+rax+00h]
0x18001d26a  mov     cl, 2
0x18001d26c  call    InitializeSidLookupTable
0x18001d271  xor     eax, eax
0x18001d273  cmp     [rbp+3Fh+Sid], rax
0x18001d277  jnz     loc_18001D84A
0x18001d27d  mov     eax, esi
0x18001d27f  jmp     loc_18001D087
0x18001d284  mov     rcx, [rbp+3Fh+Group]; Sid2
0x18001d288  test    rcx, rcx
0x18001d28b  jz      short loc_18001D2B3
0x18001d28d  mov     byte ptr [rsp+100h+var_D8], r15b; __int64
0x18001d292  lea     rdx, [rbp+3Fh+hMem]; StringSid
0x18001d296  mov     r9, r14
0x18001d299  mov     [rsp+100h+var_E0], r12; __int64
0x18001d29e  mov     r8, rdi
0x18001d2a1  call    LocalGetStringForSid
0x18001d2a6  xor     r8d, r8d
0x18001d2a9  mov     esi, eax
0x18001d2ab  test    eax, eax
0x18001d2ad  jnz     loc_18001D1E8
0x18001d2b3  movzx   ecx, [rbp+3Fh+Control]
0x18001d2b7  test    cx, cx
0x18001d2ba  jz      short loc_18001D2F9
0x18001d2bc  lea     r8, [rbp+3Fh+var_88]
0x18001d2c0  mov     edx, 1
0x18001d2c5  call    LocalGetStringForControl
0x18001d2ca  xor     r8d, r8d
0x18001d2cd  mov     esi, eax
0x18001d2cf  test    eax, eax
0x18001d2d1  jnz     loc_18001D1E8
0x18001d2d7  movzx   ecx, [rbp+3Fh+Control]
0x18001d2db  test    cx, cx
0x18001d2de  jz      short loc_18001D2F9
0x18001d2e0  lea     r8, [rbp+3Fh+var_90]
0x18001d2e4  lea     edx, [rax+2]
0x18001d2e7  call    LocalGetStringForControl
0x18001d2ec  xor     r8d, r8d
0x18001d2ef  mov     esi, eax
0x18001d2f1  test    eax, eax
0x18001d2f3  jnz     loc_18001D1E8
0x18001d2f9  mov     dl, [rbp+3Fh+SaclPresent]
0x18001d2fc  mov     edi, r8d
0x18001d2ff  mov     rbx, [rbp+3Fh+Sid]
0x18001d303  test    dl, dl
0x18001d305  jnz     loc_18001D729
0x18001d30b  mov     cl, [rbp+3Fh+DaclPresent]
0x18001d30e  test    cl, cl
0x18001d310  jz      short loc_18001D357
0x18001d312  mov     [rsp+100h+var_C0], r15b
0x18001d317  lea     rax, [rbp+3Fh+uBytes]
0x18001d31b  mov     [rsp+100h+var_C8], r12
0x18001d320  lea     r9, [rbp+3Fh+var_70]
0x18001d324  mov     [rsp+100h+var_D0], r14
0x18001d329  mov     dl, cl
0x18001d32b  mov     rcx, [rbp+3Fh+Dacl]
0x18001d32f  mov     r8b, 1
0x18001d332  mov     [rsp+100h+var_D8], rbx
0x18001d337  mov     [rsp+100h+var_E0], rax
0x18001d33c  call    LocalConvertAclToString
0x18001d341  xor     r8d, r8d
0x18001d344  mov     esi, eax
0x18001d346  test    eax, eax
0x18001d348  jnz     loc_18001D1E8
0x18001d34e  add     edi, dword ptr [rbp+3Fh+uBytes]
0x18001d351  mov     dl, [rbp+3Fh+SaclPresent]
0x18001d354  mov     cl, [rbp+3Fh+DaclPresent]
0x18001d357  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001d35b  test    r13, r13
0x18001d35e  jz      short loc_18001D374
0x18001d360  mov     rax, r12
0x18001d363  inc     rax
0x18001d366  cmp     [r13+rax*2+0], r8w
0x18001d36c  jnz     short loc_18001D363
0x18001d36e  lea     edi, [rdi+rax*2]
0x18001d371  add     edi, 4
0x18001d374  mov     rbx, [rbp+3Fh+hMem]
0x18001d378  test    rbx, rbx
0x18001d37b  jz      short loc_18001D390
0x18001d37d  mov     rax, r12
0x18001d380  inc     rax
0x18001d383  cmp     [rbx+rax*2], r8w
0x18001d388  jnz     short loc_18001D380
0x18001d38a  lea     edi, [rdi+rax*2]
0x18001d38d  add     edi, 4
0x18001d390  test    cl, cl
0x18001d392  jnz     loc_18001D5C7
0x18001d398  test    dl, dl
0x18001d39a  jnz     loc_18001D6FC
0x18001d3a0  mov     r15d, edi
0x18001d3a3  mov     ecx, 40h ; '@'; uFlags
0x18001d3a8  add     r15, 2
0x18001d3ac  mov     rdx, r15; uBytes
0x18001d3af  call    cs:__imp_LocalAlloc
0x18001d3b6  nop     dword ptr [rax+rax+00h]
0x18001d3bb  mov     r14, [rbp+3Fh+arg_28]
0x18001d3bf  xor     r9d, r9d
0x18001d3c2  mov     [r14], rax
0x18001d3c5  test    rax, rax
0x18001d3c8  jz      loc_18001D547
0x18001d3ce  shr     r15, 1
0x18001d3d1  test    r13, r13
0x18001d3d4  jz      loc_18001D721
0x18001d3da  mov     [rsp+100h+var_D8], r13
0x18001d3df  lea     r9, aO; "O"
0x18001d3e6  lea     r8, aWsWcWs; "%ws%wc%ws"
0x18001d3ed  mov     dword ptr [rsp+100h+var_E0], 3Ah ; ':'
0x18001d3f5  mov     rdx, r15; BufferCount
0x18001d3f8  mov     rcx, rax; Buffer
0x18001d3fb  call    cs:__imp_swprintf_s
0x18001d402  nop     dword ptr [rax+rax+00h]
0x18001d407  mov     rax, [r14]
0x18001d40a  xor     r9d, r9d
0x18001d40d  mov     r14, r12
0x18001d410  inc     r14
0x18001d413  cmp     [rax+r14*2], r9w
0x18001d418  jnz     short loc_18001D410
0x18001d41a  mov     r8, [rbp+3Fh+hMem]
0x18001d41e  test    r8, r8
0x18001d421  jz      short loc_18001D478
0x18001d423  mov     [rsp+100h+var_D8], r8
0x18001d428  lea     r9, aG; "G"
0x18001d42f  mov     ebx, r14d
0x18001d432  lea     r8, aWsWcWs; "%ws%wc%ws"
0x18001d439  mov     rdx, r15
0x18001d43c  mov     dword ptr [rsp+100h+var_E0], 3Ah ; ':'
0x18001d444  sub     rdx, rbx; BufferCount
0x18001d447  lea     rcx, [rax+rbx*2]; Buffer
0x18001d44b  call    cs:__imp_swprintf_s
  ... truncated ...
```
