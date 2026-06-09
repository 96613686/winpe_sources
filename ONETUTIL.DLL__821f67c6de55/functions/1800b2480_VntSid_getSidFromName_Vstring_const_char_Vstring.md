# VntSid::getSidFromName(Vstring const &,char,Vstring *)

- ea: `0x1800b2480`
- end: `0x1800b2f9d`
- name: `?getSidFromName@VntSid@@QEAAPEAVVstatus@@AEBVVstring@@DPEAV3@@Z`
- size: `2845`
- prototype: `struct Vstatus *__fastcall(VntSid *__hidden this, const struct Vstring *, char, struct Vstring *)`
- caller_count: `4`
- callee_count: `29`
- tags: `authz_impersonation`

## callers

- `0x1800078f0`
- `0x18000982c`
- `0x1800b31f0`
- `0x1800b32b0`

## callees

- `0x180040d60`
- `0x180040fd0`
- `0x180049560`
- `0x180049820`
- `0x180083790`
- `0x1800838f0`
- `0x180083b70`
- `0x180083bb0`
- `0x180083bf0`
- `0x180096770`
- `0x1800975d0`
- `0x1800977bc`
- `0x180097b94`
- `0x180098320`
- `0x1800b0c70`
- `0x1800b10b0`
- `0x1800b2480`
- `0x1800b30a4`
- `0x1800b33a8`
- `0x1800b3a44`
- `0x1800b3bd8`
- `0x1800b93d0`
- `0x1800ffc40`
- `0x180103634`
- `0x180103680`
- `0x180103890`
- `0x180133fd0`
- `0x180134070`
- `0x1801503e0`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x1800b2699`
- `ADVAPI32!GetLengthSid` at `0x1800b29a2`
- `ADVAPI32!GetLengthSid` at `0x1800b2c21`
- `ADVAPI32!GetLengthSid` at `0x1800b2c2d`
- `ADVAPI32!GetLengthSid` at `0x1800b2699`
- `ADVAPI32!GetLengthSid` at `0x1800b29a2`
- `ADVAPI32!GetLengthSid` at `0x1800b2c21`
- `ADVAPI32!GetLengthSid` at `0x1800b2c2d`
- `ADVAPI32!LookupAccountSidW` at `0x1800b2d3a`
- `ADVAPI32!LookupAccountSidW` at `0x1800b2d3a`
- `ADVAPI32!CopySid` at `0x1800b2c5e`
- `ADVAPI32!CopySid` at `0x1800b2c5e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2553`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b25a0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b25cd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b26ea`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b28ed`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b290e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b29f3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2ba8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2dc4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2e2a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2e92`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2ea9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2ee0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2f0e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2f3c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2f6a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2553`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b25a0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b25cd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b26ea`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b28ed`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b290e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b29f3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2ba8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2dc4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2e2a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2e92`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2ea9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2ee0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2f0e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2f3c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2f6a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b2831`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b2b05`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b2bd1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b2c49`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b2e4d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b2831`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b2b05`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b2bd1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b2c49`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b2e4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=56
struct Vstatus *__fastcall VntSid::getSidFromName(VntSid *this, const struct Vstring *a2, char a3, struct Vstring *a4)
{
  RWCString *v8; // rbx
  VgenericStatus *v9; // rdi
  char *v10; // rcx
  char *v11; // rcx
  char *v12; // rcx
  char *v13; // rcx
  unsigned int SidCache; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rax
  int *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  int v24; // ecx
  char **v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  const WCHAR *v29; // rcx
  int v30; // ecx
  VgenericStatus *v31; // rax
  _BYTE *v32; // r13
  int v33; // edi
  struct VsidCache *v34; // rax
  unsigned int v35; // eax
  enum _SID_NAME_USE *v36; // r15
  __int64 v37; // rax
  int *v38; // rcx
  int *v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  const WCHAR *v43; // rcx
  int v44; // ecx
  VgenericStatus *v45; // rax
  char *v46; // rcx
  char *v47; // r14
  VgenericStatus *v48; // rax
  void *v49; // rcx
  DWORD LengthSid; // eax
  void *v51; // rax
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  char *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // rcx
  int v59; // ecx
  __int64 v60; // rax
  struct VsidCache *v61; // rax
  __int64 v62; // rax
  int *v63; // rcx
  struct VsidCache *v64; // rax
  char *v65; // rcx
  char *v66; // rcx
  char *v67; // rcx
  char *v68; // rcx
  __int64 v69; // [rsp+48h] [rbp-C0h] BYREF
  char *v70; // [rsp+50h] [rbp-B8h] BYREF
  char v71; // [rsp+58h] [rbp-B0h]
  char IsCurrentHeapLocal; // [rsp+5Ch] [rbp-ACh]
  bool v73; // [rsp+5Dh] [rbp-ABh]
  char v74; // [rsp+60h] [rbp-A8h]
  bool v75; // [rsp+61h] [rbp-A7h]
  char *v76; // [rsp+68h] [rbp-A0h] BYREF
  char *v77; // [rsp+70h] [rbp-98h] BYREF
  void *Block; // [rsp+78h] [rbp-90h]
  wchar_t *v79; // [rsp+80h] [rbp-88h] BYREF
  LPCWSTR lpAccountName; // [rsp+88h] [rbp-80h] BYREF
  char *v81; // [rsp+90h] [rbp-78h] BYREF
  char *v82; // [rsp+98h] [rbp-70h] BYREF
  char *v83; // [rsp+A0h] [rbp-68h] BYREF
  DWORD cchReferencedDomainName; // [rsp+A8h] [rbp-60h] BYREF
  DWORD cchName; // [rsp+ACh] [rbp-5Ch] BYREF
  char *v86; // [rsp+B0h] [rbp-58h] BYREF
  wchar_t *v87; // [rsp+B8h] [rbp-50h] BYREF
  VgenericStatus *v88; // [rsp+C0h] [rbp-48h]
  _SID_NAME_USE peUse; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v90; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v91; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v92; // [rsp+E0h] [rbp-28h] BYREF
  const struct Vstring *v93; // [rsp+E8h] [rbp-20h]
  __int64 v94; // [rsp+F0h] [rbp-18h]
  char v95; // [rsp+F8h] [rbp-10h] BYREF
  WCHAR ReferencedDomainName[16]; // [rsp+118h] [rbp+10h] BYREF
  char v97; // [rsp+138h] [rbp+30h] BYREF
  WCHAR Name[264]; // [rsp+188h] [rbp+80h] BYREF

  v94 = -2;
  v71 = a3;
  v93 = a2;
  v8 = (VntSid *)((char *)this + 16);
  if ( (unsigned int)Vstricmp(*(const char **)a2, *((const char **)this + 2)) )
  {
    RWCString::operator=(v8, (char *)Class);
    if ( *(_QWORD *)this )
      VUserId::deleteSid(this, 0);
    v70 = dword_1802AFD5C;
    _InterlockedIncrement(&dword_1802AFD50);
    v76 = dword_1802AFD5C;
    _InterlockedIncrement(&dword_1802AFD50);
    v77 = dword_1802AFD5C;
    _InterlockedIncrement(&dword_1802AFD50);
    v9 = VsplitUserAndDomain(a2, (struct Vstring *)&v70, (struct Vstring *)&v76);
    if ( v9 )
      goto LABEL_189;
    if ( a4 )
      RWCString::operator=(a4, &v70);
    SidCache = (unsigned int)VprocessGlobals::getSidCache((VprocessGlobals *)&off_1802AB3C8);
    if ( (unsigned __int8)sub_1800B33A8(
                            SidCache,
                            (unsigned int)&v70,
                            (unsigned int)&v76,
                            (_DWORD)this,
                            (__int64)this + 24,
                            (__int64)&v70) )
    {
      *((_DWORD *)this + 2) = GetLengthSid(*(PSID *)this);
      v19 = VmergeUserAndDomain(&v90, &v70, &v76);
      RWCString::operator=((char *)this + 16, v19);
      v20 = (int *)(v90 - 12);
      if ( !_InterlockedDecrement((volatile signed __int32 *)(v90 - 12)) && v20 != &dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v20);
        else
          free(v20);
      }
      if ( a4 )
        RWCString::operator=(a4, &v70);
      v9 = 0;
LABEL_189:
      v66 = v77 - 12;
      if ( !_InterlockedDecrement((volatile signed __int32 *)v77 - 3) && v66 != (char *)&dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v66);
        else
          free(v66);
      }
      v67 = v76 - 12;
      if ( !_InterlockedDecrement((volatile signed __int32 *)v76 - 3) && v67 != (char *)&dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v67);
        else
          free(v67);
      }
      v11 = v70;
      goto LABEL_200;
    }
    if ( *((_DWORD *)v76 - 1) )
    {
      v25 = &v76;
    }
    else
    {
      if ( (unsigned __int8)sub_180096770(v17, v16, v18) )
        v23 = *(unsigned int *)(qword_1802B00B0 + 4);
      else
        v23 = 0;
      if ( (_DWORD)v23 == 2
        && (!(unsigned __int8)sub_180096770(v23, v21, v22) ? (v24 = 0) : (v24 = *(_DWORD *)(qword_1802B00B0 + 8)),
            v24 == 3) )
      {
        v25 = (char **)sub_180097B94();
      }
      else
      {
        v25 = (char **)sub_180098320();
      }
    }
    VmergeUserAndDomain(&v83, &v70, v25);
    lpAccountName = (LPCWSTR)&dword_1802B04A4;
    Vwstring::fromUtf8((Vwstring *)&lpAccountName, v83, 0xFFFFFFFF);
    Block = &v97;
    v79 = (wchar_t *)&v95;
    *((_DWORD *)this + 6) = 7;
    LOBYTE(v69) = 0;
    if ( a3 )
    {
      v29 = 0;
    }
    else
    {
      if ( (unsigned __int8)sub_180096770(v27, v26, v28) )
        v30 = *(_DWORD *)(qword_1802B00B0 + 4);
      else
        v30 = 0;
      if ( v30 == 2 )
      {
        sub_1800977BC();
      }
      else if ( !qword_1802AF450 )
      {
        if ( dword_1802B0018 )
        {
          IsCurrentHeapLocal = COWSAllocator::IsCurrentHeapLocal();
          v73 = IsCurrentHeapLocal == 1;
          if ( IsCurrentHeapLocal == 1 )
            COWSAllocator::UseGlobalHeap();
        }
        if ( dword_1802B0018 )
          v31 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(8u);
        else
          v31 = (VgenericStatus *)malloc(8u);
        v88 = v31;
        if ( v31 )
          *(_QWORD *)v31 = &dword_1802B04A4;
        else
          v31 = 0;
        _InterlockedExchange64(&qword_1802AF450, (__int64)v31);
        if ( dword_1802B0018 && v73 )
        {
          if ( IsCurrentHeapLocal )
            COWSAllocator::UseLocalHeap();
          else
            COWSAllocator::UseGlobalHeap();
        }
      }
      v29 = *(const WCHAR **)qword_1802AF450;
    }
    v32 = (char *)this + 12;
    v33 = sub_1800B30A4(v29, lpAccountName, (__int64)&v79, (__int64)&v69, (PSID_NAME_USE)this + 6);
    if ( v33 )
    {
      if ( *((_DWORD *)v76 - 1) )
      {
        v36 = (enum _SID_NAME_USE *)((char *)this + 24);
      }
      else
      {
        if ( *v32 )
        {
          if ( dword_1802B0018 )
            COWSAllocator::Free(Block);
          else
            free(Block);
        }
        if ( (_BYTE)v69 )
        {
          if ( dword_1802B0018 )
            COWSAllocator::Free(v79);
          else
            free(v79);
        }
        v82 = dword_1802AFD5C;
        _InterlockedIncrement(&dword_1802AFD50);
        v34 = VprocessGlobals::getSidCache((VprocessGlobals *)&off_1802AB3C8);
        if ( (unsigned __int8)sub_1800B0C70(v34, v70, &v82) )
        {
          v9 = VsplitUserAndDomain((const struct Vstring *)&v82, (struct Vstring *)&v70, (struct Vstring *)&v76);
          if ( v9 )
            goto LABEL_91;
          v35 = (unsigned int)VprocessGlobals::getSidCache((VprocessGlobals *)&off_1802AB3C8);
          v36 = (enum _SID_NAME_USE *)((char *)this + 24);
          if ( (unsigned __int8)sub_1800B33A8(
                                  v35,
                                  (unsigned int)&v70,
                                  (unsigned int)&v76,
                                  (_DWORD)this,
                                  (__int64)this + 24,
                                  (__int64)&v70) )
          {
            *((_DWORD *)this + 2) = GetLengthSid(*(PSID *)this);
            v37 = VmergeUserAndDomain(&v91, &v70, &v76);
            RWCString::operator=((char *)this + 16, v37);
            v38 = (int *)(v91 - 12);
            if ( !_InterlockedDecrement((volatile signed __int32 *)(v91 - 12)) && v38 != &dword_1802AFD50 )
            {
              if ( dword_1802B0018 )
                COWSAllocator::Free(v38);
              else
                free(v38);
            }
            if ( a4 )
              RWCString::operator=(a4, &v70);
            v9 = 0;
LABEL_91:
            v39 = (int *)(v82 - 12);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v82 - 3, 0xFFFFFFFF) != 1 || v39 == &dword_1802AFD50 )
            {
LABEL_184:
              Vwstring::~Vwstring((Vwstring *)&lpAccountName);
              v65 = v83 - 12;
              if ( !_InterlockedDecrement((volatile signed __int32 *)v83 - 3) && v65 != (char *)&dword_1802AFD50 )
              {
                if ( dword_1802B0018 )
                  COWSAllocator::Free(v65);
                else
                  free(v65);
              }
              goto LABEL_189;
            }
LABEL_93:
            if ( dword_1802B0018 )
              COWSAllocator::Free(v39);
            else
              free(v39);
            goto LABEL_184;
          }
        }
        else
        {
          v36 = (enum _SID_NAME_USE *)((char *)this + 24);
        }
        v87 = (wchar_t *)&dword_1802B04A4;
        Vwstring::fromUtf8((Vwstring *)&v87, v70, 0xFFFFFFFF);
        Vwstring::Set((Vwstring *)&lpAccountName, v87, *((_DWORD *)v87 - 1));
        Vwstring::~Vwstring((Vwstring *)&v87);
        if ( v71 )
        {
          v43 = 0;
        }
        else
        {
          if ( (unsigned __int8)sub_180096770(v41, v40, v42) )
            v44 = *(_DWORD *)(qword_1802B00B0 + 4);
          else
            v44 = 0;
          if ( v44 == 2 )
          {
            sub_1800977BC();
          }
          else if ( !qword_1802AF450 )
          {
            if ( dword_1802B0018 )
            {
              v74 = COWSAllocator::IsCurrentHeapLocal();
              v75 = v74 == 1;
              if ( v74 == 1 )
                COWSAllocator::UseGlobalHeap();
            }
            if ( dword_1802B0018 )
              v45 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(8u);
            else
              v45 = (VgenericStatus *)malloc(8u);
            v88 = v45;
            if ( v45 )
              *(_QWORD *)v45 = &dword_1802B04A4;
            else
              v45 = 0;
            _InterlockedExchange64(&qword_1802AF450, (__int64)v45);
            if ( dword_1802B0018 && v75 )
            {
              if ( v74 )
                COWSAllocator::UseLocalHeap();
              else
                COWSAllocator::UseGlobalHeap();
            }
          }
          v43 = *(const WCHAR **)qword_1802AF450;
        }
        v33 = sub_1800B30A4(v43, lpAccountName, (__int64)&v79, (__int64)&v69, v36);
        v46 = v82 - 12;
        if ( !_InterlockedDecrement((volatile signed __int32 *)v82 - 3) && v46 != (char *)&dword_1802AFD50 )
        {
          if ( dword_1802B0018 )
            COWSAllocator::Free(v46);
          else
            free(v46);
        }
      }
      if ( v33 )
      {
        v47 = v83;
        if ( dword_1802B0018 )
          v48 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
        else
          v48 = (VgenericStatus *)malloc(0x20u);
        v88 = v48;
        if ( !v48 )
        {
          v9 = 0;
LABEL_177:
          if ( *v32 )
          {
            if ( dword_1802B0018 )
              COWSAllocator::Free(Block);
            else
              free(Block);
          }
          if ( !(_BYTE)v69 )
            goto LABEL_184;
          v39 = (int *)v79;
          goto LABEL_93;
        }
LABEL_175:
        v9 = VgenericStatus::VgenericStatus(v48, 0xE0025u, v33, v47);
        goto LABEL_177;
      }
    }
    else
    {
      v36 = (enum _SID_NAME_USE *)((char *)this + 24);
    }
    if ( (unsigned int)(*v36 - 6) > 1 )
    {
      v49 = Block;
      if ( *v32 )
      {
        *(_QWORD *)this = Block;
        *((_DWORD *)this + 2) = GetLengthSid(v49);
      }
      else
      {
        LengthSid = GetLengthSid(Block);
        *((_DWORD *)this + 2) = LengthSid;
        if ( dword_1802B0018 )
          v51 = COWSAllocator::AllocCurrentHeap(LengthSid);
        else
          v51 = malloc(LengthSid);
        *(_QWORD *)this = v51;
        CopySid(*((_DWORD *)this + 2), v51, Block);
        *v32 = 1;
      }
      Vstring::InitUnicode((Vstring *)&v77, v79);
      Vstring::doConvertToUtf8((Vstring *)&v77, v77, *((_DWORD *)v77 - 1), 0);
      v55 = v77;
      if ( *((_DWORD *)v77 - 1) )
        goto LABEL_154;
      if ( *v36 != SidTypeWellKnownGroup )
      {
        if ( (unsigned __int8)sub_180096770(v53, v52, v54) )
          v58 = *(unsigned int *)(qword_1802B00B0 + 4);
        else
          v58 = 0;
        if ( (_DWORD)v58 == 2
          && (!(unsigned __int8)sub_180096770(v58, v56, v57) ? (v59 = 0) : (v59 = *(_DWORD *)(qword_1802B00B0 + 8)),
              v59 == 3) )
        {
          v60 = sub_180097B94();
        }
        else
        {
          v60 = sub_180098320();
        }
        RWCString::operator=(&v77, v60);
        v55 = v77;
      }
      if ( *((_DWORD *)v55 - 1) || *v36 == SidTypeWellKnownGroup )
      {
LABEL_154:
        cchName = 257;
        cchReferencedDomainName = 16;
        if ( LookupAccountSidW(0, *(PSID *)this, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
        {
          Vstring::InitUnicode((Vstring *)&v70, Name);
          v61 = VprocessGlobals::getSidCache((VprocessGlobals *)&off_1802AB3C8);
          sub_1800B3A44(v61, &v70, &v77, *(_QWORD *)this, *v36);
        }
      }
      v62 = VmergeUserAndDomain(&v92, &v70, &v77);
      RWCString::operator=((char *)this + 16, v62);
      v63 = (int *)(v92 - 12);
      if ( !_InterlockedDecrement((volatile signed __int32 *)(v92 - 12)) && v63 != &dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v63);
        else
          free(v63);
      }
      if ( a4 )
        RWCString::operator=(a4, &v70);
      if ( !*((_DWORD *)v76 - 1) && *((_DWORD *)v77 - 1) )
      {
        v64 = VprocessGlobals::getSidCache((VprocessGlobals *)&off_1802AB3C8);
        sub_1800B3BD8(v64, v93, (char *)this + 16);
      }
      if ( (_BYTE)v69 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v79);
        else
          free(v79);
      }
      v9 = 0;
      goto LABEL_184;
    }
    v47 = v83;
    if ( dword_1802B0018 )
      v48 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v48 = (VgenericStatus *)malloc(0x20u);
    v88 = v48;
    if ( !v48 )
    {
      v9 = 0;
      goto LABEL_177;
    }
    goto LABEL_175;
  }
  if ( !a4 )
    return 0;
  v81 = dword_1802AFD5C;
  _InterlockedIncrement(&dword_1802AFD50);
  v86 = dword_1802AFD5C;
  _InterlockedIncrement(&dword_1802AFD50);
  v9 = VsplitUserAndDomain(v8, (struct Vstring *)&v81, (struct Vstring *)&v86);
  if ( !v9 )
  {
    RWCString::operator=(a4, &v81);
    v12 = v86 - 12;
    if ( !_InterlockedDecrement((volatile signed __int32 *)v86 - 3) && v12 != (char *)&dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v12);
      else
        free(v12);
    }
    v13 = v81 - 12;
    if ( !_InterlockedDecrement((volatile signed __int32 *)v81 - 3) && v13 != (char *)&dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v13);
      else
        free(v13);
    }
    return 0;
  }
  v10 = v86 - 12;
  if ( !_InterlockedDecrement((volatile signed __int32 *)v86 - 3) && v10 != (char *)&dword_1802AFD50 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(v10);
    else
      free(v10);
  }
  v11 = v81;
LABEL_200:
  v68 = v11 - 12;
  if ( !_InterlockedDecrement((volatile signed __int32 *)v68) && v68 != (char *)&dword_1802AFD50 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(v68);
    else
      free(v68);
  }
  return v9;
}

```

## disassembly

```asm
0x1800b2480  mov     rax, rsp
0x1800b2483  push    rbp
0x1800b2484  push    rsi
0x1800b2485  push    rdi
0x1800b2486  push    r12
0x1800b2488  push    r13
0x1800b248a  push    r14
0x1800b248c  push    r15
0x1800b248e  lea     rbp, [rax-2D8h]
0x1800b2495  sub     rsp, 3A0h
0x1800b249c  mov     [rbp+2D0h+var_2E8], 0FFFFFFFFFFFFFFFEh
0x1800b24a4  mov     [rax+18h], rbx
0x1800b24a8  mov     rax, cs:__security_cookie
0x1800b24af  xor     rax, rsp
0x1800b24b2  mov     [rbp+2D0h+var_40], rax
0x1800b24b9  mov     r12, r9
0x1800b24bc  mov     r13b, r8b
0x1800b24bf  mov     [rsp+3D0h+var_380], r8b
0x1800b24c4  mov     rdi, rdx
0x1800b24c7  mov     [rbp+2D0h+var_2F0], rdx
0x1800b24cb  mov     r14, rcx
0x1800b24ce  lea     rbx, [rcx+10h]
0x1800b24d2  mov     rdx, [rbx]; char *
0x1800b24d5  mov     rcx, [rdi]; char *
0x1800b24d8  call    ?Vstricmp@@YAJPEBD0@Z; Vstricmp(char const *,char const *)
0x1800b24dd  test    eax, eax
0x1800b24df  jnz     loc_1800B25DA
0x1800b24e5  test    r12, r12
0x1800b24e8  jz      loc_1800B25D3
0x1800b24ee  lea     r15, dword_1802AFD5C
0x1800b24f5  mov     [rbp+2D0h+var_348], r15
0x1800b24f9  lock inc cs:dword_1802AFD50
0x1800b2500  mov     [rbp+2D0h+var_328], r15
0x1800b2504  lock inc cs:dword_1802AFD50
0x1800b250b  lea     r8, [rbp+2D0h+var_328]; struct Vstring *
0x1800b250f  lea     rdx, [rbp+2D0h+var_348]; struct Vstring *
0x1800b2513  mov     rcx, rbx; struct Vstring *
0x1800b2516  call    ?VsplitUserAndDomain@@YAPEAVVstatus@@AEBVVstring@@AEAV2@1@Z; VsplitUserAndDomain(Vstring const &,Vstring &,Vstring &)
0x1800b251b  mov     rdi, rax
0x1800b251e  test    rax, rax
0x1800b2521  jz      short loc_1800B2563
0x1800b2523  mov     rcx, [rbp+2D0h+var_328]
0x1800b2527  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800b252b  or      ebx, 0FFFFFFFFh
0x1800b252e  mov     edx, ebx
0x1800b2530  lock xadd [rcx], edx
0x1800b2534  lea     rsi, dword_1802AFD50
0x1800b253b  add     edx, ebx
0x1800b253d  jnz     short loc_1800B255A
0x1800b253f  cmp     rcx, rsi
0x1800b2542  jz      short loc_1800B255A
0x1800b2544  cmp     cs:dword_1802B0018, edx
0x1800b254a  jz      short loc_1800B2553
0x1800b254c  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800b2551  jmp     short loc_1800B255A
0x1800b2553  call    cs:free
0x1800b2559  nop
0x1800b255a  mov     rcx, [rbp+2D0h+var_348]
0x1800b255e  jmp     loc_1800B2F48
0x1800b2563  lea     rdx, [rbp+2D0h+var_348]
0x1800b2567  mov     rcx, r12
0x1800b256a  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x1800b256f  nop
0x1800b2570  mov     rcx, [rbp+2D0h+var_328]
0x1800b2574  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800b2578  or      ebx, 0FFFFFFFFh
0x1800b257b  mov     eax, ebx
0x1800b257d  lock xadd [rcx], eax
0x1800b2581  lea     rsi, dword_1802AFD50
0x1800b2588  add     eax, ebx
0x1800b258a  jnz     short loc_1800B25A7
0x1800b258c  cmp     rcx, rsi
0x1800b258f  jz      short loc_1800B25A7
0x1800b2591  cmp     cs:dword_1802B0018, eax
0x1800b2597  jz      short loc_1800B25A0
0x1800b2599  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800b259e  jmp     short loc_1800B25A7
0x1800b25a0  call    cs:free
0x1800b25a6  nop
0x1800b25a7  mov     rcx, [rbp+2D0h+var_348]
0x1800b25ab  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800b25af  mov     eax, ebx
0x1800b25b1  lock xadd [rcx], eax
0x1800b25b5  add     eax, ebx
0x1800b25b7  jnz     short loc_1800B25D3
0x1800b25b9  cmp     rcx, rsi
0x1800b25bc  jz      short loc_1800B25D3
0x1800b25be  cmp     cs:dword_1802B0018, eax
0x1800b25c4  jz      short loc_1800B25CD
0x1800b25c6  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800b25cb  jmp     short loc_1800B25D3
0x1800b25cd  call    cs:free
0x1800b25d3  xor     eax, eax
0x1800b25d5  jmp     loc_1800B2F73
0x1800b25da  lea     rdx, Class; char *
0x1800b25e1  mov     rcx, rbx; this
0x1800b25e4  call    ??4RWCString@@QEAAAEAV0@PEBD@Z; RWCString::operator=(char const *)
0x1800b25e9  cmp     qword ptr [r14], 0
0x1800b25ed  jz      short loc_1800B25F9
0x1800b25ef  xor     edx, edx; char
0x1800b25f1  mov     rcx, r14; this
0x1800b25f4  call    ?deleteSid@VUserId@@QEAAXD@Z; VUserId::deleteSid(char)
0x1800b25f9  lea     r15, dword_1802AFD5C
0x1800b2600  mov     [rsp+3D0h+var_388], r15
0x1800b2605  lock inc cs:dword_1802AFD50
0x1800b260c  mov     [rsp+3D0h+var_370], r15
0x1800b2611  lock inc cs:dword_1802AFD50
0x1800b2618  mov     [rsp+3D0h+var_368], r15
0x1800b261d  lock inc cs:dword_1802AFD50
0x1800b2624  lea     r8, [rsp+3D0h+var_370]; struct Vstring *
0x1800b2629  lea     rdx, [rsp+3D0h+var_388]; struct Vstring *
0x1800b262e  mov     rcx, rdi; struct Vstring *
0x1800b2631  call    ?VsplitUserAndDomain@@YAPEAVVstatus@@AEBVVstring@@AEAV2@1@Z; VsplitUserAndDomain(Vstring const &,Vstring &,Vstring &)
0x1800b2636  mov     rdi, rax
0x1800b2639  or      ebx, 0FFFFFFFFh
0x1800b263c  lea     rsi, dword_1802AFD50
0x1800b2643  test    rax, rax
0x1800b2646  jnz     loc_1800B2EE7
0x1800b264c  test    r12, r12
0x1800b264f  jz      short loc_1800B265E
0x1800b2651  lea     rdx, [rsp+3D0h+var_388]
0x1800b2656  mov     rcx, r12
0x1800b2659  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x1800b265e  lea     rcx, off_1802AB3C8; this
0x1800b2665  call    ?getSidCache@VprocessGlobals@@QEAAPEAVVsidCache@@XZ; VprocessGlobals::getSidCache(void)
0x1800b266a  lea     rdi, [r14+18h]
0x1800b266e  lea     rcx, [rsp+3D0h+var_388]
0x1800b2673  mov     [rsp+3D0h+cchReferencedDomainName], rcx
0x1800b2678  mov     [rsp+3D0h+ReferencedDomainName], rdi
0x1800b267d  mov     r9, r14
0x1800b2680  lea     r8, [rsp+3D0h+var_370]
0x1800b2685  lea     rdx, [rsp+3D0h+var_388]
0x1800b268a  mov     rcx, rax
0x1800b268d  call    sub_1800B33A8
0x1800b2692  test    al, al
0x1800b2694  jz      short loc_1800B2709
0x1800b2696  mov     rcx, [r14]; pSid
0x1800b2699  call    cs:GetLengthSid
0x1800b269f  mov     [r14+8], eax
0x1800b26a3  lea     r8, [rsp+3D0h+var_370]
0x1800b26a8  lea     rdx, [rsp+3D0h+var_388]
0x1800b26ad  lea     rcx, [rbp+2D0h+var_308]
0x1800b26b1  call    ?VmergeUserAndDomain@@YA?AVVstring@@AEBV1@0@Z; VmergeUserAndDomain(Vstring const &,Vstring const &)
0x1800b26b6  nop
0x1800b26b7  mov     rdx, rax
0x1800b26ba  lea     rcx, [r14+10h]
0x1800b26be  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x1800b26c3  nop
0x1800b26c4  mov     rcx, [rbp+2D0h+var_308]
0x1800b26c8  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800b26cc  mov     eax, ebx
0x1800b26ce  lock xadd [rcx], eax
0x1800b26d2  add     eax, ebx
0x1800b26d4  jnz     short loc_1800B26F0
0x1800b26d6  cmp     rcx, rsi
0x1800b26d9  jz      short loc_1800B26F0
0x1800b26db  cmp     cs:dword_1802B0018, eax
0x1800b26e1  jz      short loc_1800B26EA
0x1800b26e3  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800b26e8  jmp     short loc_1800B26F0
0x1800b26ea  call    cs:free
0x1800b26f0  test    r12, r12
0x1800b26f3  jz      short loc_1800B2702
0x1800b26f5  lea     rdx, [rsp+3D0h+var_388]
0x1800b26fa  mov     rcx, r12
0x1800b26fd  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x1800b2702  xor     edi, edi
0x1800b2704  jmp     loc_1800B2EE7
0x1800b2709  mov     rax, [rsp+3D0h+var_370]
0x1800b270e  xor     ebx, ebx
0x1800b2710  cmp     [rax-4], ebx
0x1800b2713  jnz     short loc_1800B275B
0x1800b2715  call    sub_180096770
0x1800b271a  test    al, al
0x1800b271c  jz      short loc_1800B272A
0x1800b271e  mov     rax, cs:qword_1802B00B0
0x1800b2725  mov     ecx, [rax+4]
0x1800b2728  jmp     short loc_1800B272C
0x1800b272a  mov     ecx, ebx
0x1800b272c  cmp     ecx, 2
0x1800b272f  jnz     short loc_1800B2754
0x1800b2731  call    sub_180096770
0x1800b2736  test    al, al
0x1800b2738  jz      short loc_1800B2746
0x1800b273a  mov     rax, cs:qword_1802B00B0
0x1800b2741  mov     ecx, [rax+8]
0x1800b2744  jmp     short loc_1800B2748
0x1800b2746  mov     ecx, ebx
0x1800b2748  cmp     ecx, 3
0x1800b274b  jnz     short loc_1800B2754
0x1800b274d  call    sub_180097B94
0x1800b2752  jmp     short loc_1800B2760
0x1800b2754  call    sub_180098320
0x1800b2759  jmp     short loc_1800B2760
0x1800b275b  lea     rax, [rsp+3D0h+var_370]
0x1800b2760  mov     r8, rax
0x1800b2763  lea     rdx, [rsp+3D0h+var_388]
0x1800b2768  lea     rcx, [rbp+2D0h+var_338]
0x1800b276c  call    ?VmergeUserAndDomain@@YA?AVVstring@@AEBV1@0@Z; VmergeUserAndDomain(Vstring const &,Vstring const &)
0x1800b2771  nop
0x1800b2772  lea     rax, dword_1802B04A4
0x1800b2779  mov     [rbp+2D0h+lpAccountName], rax
0x1800b277d  or      r8d, 0FFFFFFFFh; unsigned int
0x1800b2781  mov     rdx, [rbp+2D0h+var_338]; char *
0x1800b2785  lea     rcx, [rbp+2D0h+lpAccountName]; this
0x1800b2789  call    ?fromUtf8@Vwstring@@QEAAXPEBDK@Z; Vwstring::fromUtf8(char const *,ulong)
0x1800b278e  nop
0x1800b278f  lea     rax, [rbp+2D0h+var_2A0]
0x1800b2793  mov     [rsp+3D0h+Block], rax
0x1800b2798  lea     rax, [rbp+2D0h+var_2E0]
0x1800b279c  mov     [rsp+3D0h+var_358], rax
0x1800b27a1  mov     dword ptr [rdi], 7
0x1800b27a7  mov     byte ptr [rsp+3D0h+var_390], bl
0x1800b27ab  mov     esi, 8
0x1800b27b0  test    r13b, r13b
0x1800b27b3  jz      short loc_1800B27BD
0x1800b27b5  mov     rcx, rbx
0x1800b27b8  jmp     loc_1800B2880
0x1800b27bd  call    sub_180096770
0x1800b27c2  test    al, al
0x1800b27c4  jz      short loc_1800B27D2
0x1800b27c6  mov     rax, cs:qword_1802B00B0
0x1800b27cd  mov     ecx, [rax+4]
0x1800b27d0  jmp     short loc_1800B27D4
0x1800b27d2  mov     ecx, ebx
0x1800b27d4  cmp     ecx, 2
0x1800b27d7  jnz     short loc_1800B27E3
0x1800b27d9  call    sub_1800977BC
0x1800b27de  jmp     loc_1800B2876
0x1800b27e3  cmp     cs:qword_1802AF450, rbx
0x1800b27ea  jnz     loc_1800B2876
0x1800b27f0  cmp     cs:dword_1802B0018, ebx
0x1800b27f6  jz      short loc_1800B281F
0x1800b27f8  call    ?IsCurrentHeapLocal@COWSAllocator@@SADXZ; COWSAllocator::IsCurrentHeapLocal(void)
0x1800b27fd  mov     [rsp+3D0h+var_37C], al
0x1800b2801  cmp     al, 1
0x1800b2803  setz    cl
0x1800b2806  mov     [rsp+3D0h+var_37B], cl
0x1800b280a  test    cl, cl
0x1800b280c  jz      short loc_1800B281F
0x1800b280e  test    al, al
0x1800b2810  jz      short loc_1800B2819
0x1800b2812  call    ?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x1800b2817  jmp     short loc_1800B281F
0x1800b2819  call    ?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x1800b281e  nop
0x1800b281f  mov     rcx, rsi; unsigned __int64
0x1800b2822  cmp     cs:dword_1802B0018, ebx
0x1800b2828  jz      short loc_1800B2831
0x1800b282a  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800b282f  jmp     short loc_1800B2837
0x1800b2831  call    cs:malloc
0x1800b2837  mov     [rbp+2D0h+var_318], rax
0x1800b283b  test    rax, rax
0x1800b283e  jz      short loc_1800B284C
0x1800b2840  lea     rcx, dword_1802B04A4
0x1800b2847  mov     [rax], rcx
0x1800b284a  jmp     short loc_1800B284F
0x1800b284c  mov     rax, rbx
0x1800b284f  xchg    rax, cs:qword_1802AF450
0x1800b2856  cmp     cs:dword_1802B0018, ebx
0x1800b285c  jz      short loc_1800B2876
0x1800b285e  cmp     [rsp+3D0h+var_37B], bl
0x1800b2862  jz      short loc_1800B2876
0x1800b2864  cmp     [rsp+3D0h+var_37C], bl
0x1800b2868  jz      short loc_1800B2871
0x1800b286a  call    ?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x1800b286f  jmp     short loc_1800B2876
0x1800b2871  call    ?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x1800b2876  mov     rax, cs:qword_1802AF450
0x1800b287d  mov     rcx, [rax]; lpSystemName
0x1800b2880  lea     r13, [r14+0Ch]
0x1800b2884  mov     [rsp+30h], rdi; PSID_NAME_USE
0x1800b2889  lea     rax, [rsp+3D0h+var_390]
0x1800b288e  mov     [rsp+3D0h+cchReferencedDomainName], rax; __int64
0x1800b2893  lea     rax, [rsp+3D0h+var_358]
0x1800b2898  mov     [rsp+3D0h+ReferencedDomainName], rax; __int64
0x1800b289d  mov     r9, r13
0x1800b28a0  lea     r8, [rsp+3D0h+Block]
0x1800b28a5  mov     rdx, [rbp+2D0h+lpAccountName]; lpAccountName
0x1800b28a9  call    sub_1800B30A4
0x1800b28ae  mov     edi, eax
0x1800b28b0  or      ebx, 0FFFFFFFFh
0x1800b28b3  lea     rsi, dword_1802AFD50
0x1800b28ba  test    eax, eax
0x1800b28bc  jz      loc_1800B2BFF
0x1800b28c2  mov     rcx, [rsp+3D0h+var_370]
0x1800b28c7  cmp     dword ptr [rcx-4], 0
0x1800b28cb  jnz     loc_1800B2BB0
0x1800b28d1  xor     edi, edi
0x1800b28d3  cmp     [r13+0], dil
0x1800b28d7  jz      short loc_1800B28F3
0x1800b28d9  mov     rcx, [rsp+3D0h+Block]; void *
0x1800b28de  cmp     cs:dword_1802B0018, edi
0x1800b28e4  jz      short loc_1800B28ED
0x1800b28e6  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800b28eb  jmp     short loc_1800B28F3
0x1800b28ed  call    cs:free
0x1800b28f3  cmp     byte ptr [rsp+3D0h+var_390], dil
0x1800b28f8  jz      short loc_1800B2914
  ... truncated ...
```
