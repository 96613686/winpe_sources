# VntSid::getNameFromSid(Vstring &,char,char)

- ea: `0x1800b1e30`
- end: `0x1800b247f`
- name: `?getNameFromSid@VntSid@@IEAAPEAVVstatus@@AEAVVstring@@DD@Z`
- size: `1615`
- prototype: `struct Vstatus *(VntSid *__hidden this, struct Vstring *, char, char)`
- caller_count: `6`
- callee_count: `15`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18000781c`
- `0x180007a50`
- `0x18000e1f0`
- `0x1800b31f0`
- `0x1800b32b0`
- `0x180101dc0`

## callees

- `0x180040fd0`
- `0x180049560`
- `0x180049820`
- `0x180083790`
- `0x1800838f0`
- `0x180097480`
- `0x1800975d0`
- `0x1800b1e30`
- `0x1800b3554`
- `0x1800b3a44`
- `0x1800b93d0`
- `0x180101dc0`
- `0x180133fd0`
- `0x180134070`
- `0x1801503e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800b1e89`
- `KERNEL32!GetLastError` at `0x1800b1edb`
- `KERNEL32!GetLastError` at `0x1800b2170`
- `KERNEL32!GetLastError` at `0x1800b2275`
- `KERNEL32!GetLastError` at `0x1800b1e89`
- `KERNEL32!GetLastError` at `0x1800b1edb`
- `KERNEL32!GetLastError` at `0x1800b2170`
- `KERNEL32!GetLastError` at `0x1800b2275`
- `ADVAPI32!LookupAccountSidW` at `0x1800b20a1`
- `ADVAPI32!LookupAccountSidW` at `0x1800b2162`
- `ADVAPI32!LookupAccountSidW` at `0x1800b20a1`
- `ADVAPI32!LookupAccountSidW` at `0x1800b2162`
- `ADVAPI32!IsValidSid` at `0x1800b1ed1`
- `ADVAPI32!IsValidSid` at `0x1800b1ed1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b1fd0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b222c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b232b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b23c0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b23df`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2418`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b244c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b1fd0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b222c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b232b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b23c0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b23df`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b2418`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b244c`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b1ea3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b1ef7`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b20f1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b212f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b2291`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b1ea3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b1ef7`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b20f1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b212f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b2291`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
struct Vstatus *__fastcall VntSid::getNameFromSid(PSID *this, struct Vstring *a2, char a3, char a4)
{
  __int64 v8; // rdi
  VgenericStatus *v9; // r14
  DWORD LastError; // ebx
  VgenericStatus *v11; // rax
  DWORD v13; // ebx
  VgenericStatus *v14; // rax
  char **v15; // r15
  unsigned int SidCache; // eax
  __int64 v17; // rax
  int *v18; // rcx
  char *v19; // rdx
  WCHAR *v20; // r13
  WCHAR *ReferencedDomainName; // r12
  DWORD v22; // eax
  unsigned __int64 v23; // rax
  WCHAR *v24; // rax
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // kr00_8
  WCHAR *v27; // rax
  struct VwellKnownGroups *WellKnownGroups; // rbx
  struct VwellKnownGroups *v29; // rbx
  __int64 v30; // rax
  int *v31; // rcx
  char *v32; // rdx
  DWORD v33; // ebx
  VgenericStatus *v34; // rax
  __int64 v35; // rax
  int *v36; // rcx
  char *v37; // rdx
  struct VsidCache *v38; // rax
  char *v39; // rcx
  char *v40; // rcx
  char v43; // [rsp+4Ah] [rbp-BEh]
  char v44; // [rsp+4Bh] [rbp-BDh]
  char *v45; // [rsp+50h] [rbp-B8h] BYREF
  char *v46; // [rsp+58h] [rbp-B0h] BYREF
  DWORD cchName[2]; // [rsp+60h] [rbp-A8h] BYREF
  VgenericStatus *v48; // [rsp+68h] [rbp-A0h] BYREF
  VgenericStatus *v49; // [rsp+70h] [rbp-98h]
  __int64 v50; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v51[2]; // [rsp+80h] [rbp-88h] BYREF
  WCHAR Block[20]; // [rsp+90h] [rbp-78h] BYREF
  WCHAR Name[264]; // [rsp+B8h] [rbp-50h] BYREF

  v51[1] = -2;
  v8 = 0;
  v9 = 0;
  if ( !*this )
  {
    LastError = GetLastError();
    if ( dword_1802B0018 )
      v11 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v11 = (VgenericStatus *)malloc(0x20u);
    v48 = v11;
    if ( v11 )
      return VgenericStatus::VgenericStatus(v11, 0xE0024u, LastError);
    return (struct Vstatus *)v8;
  }
  if ( !IsValidSid(*this) )
  {
    v13 = GetLastError();
    if ( dword_1802B0018 )
      v14 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v14 = (VgenericStatus *)malloc(0x20u);
    v48 = v14;
    if ( v14 )
      return VgenericStatus::VgenericStatus(v14, 0xE0024u, v13);
    return (struct Vstatus *)v8;
  }
  v46 = dword_1802AFD5C;
  _InterlockedIncrement(&dword_1802AFD50);
  v45 = dword_1802AFD5C;
  _InterlockedIncrement(&dword_1802AFD50);
  v15 = (char **)(this + 2);
  if ( !*((_DWORD *)this[2] - 1) )
  {
    SidCache = (unsigned int)VprocessGlobals::getSidCache((VprocessGlobals *)&off_1802AB3C8);
    if ( (unsigned __int8)sub_1800B3554(
                            SidCache,
                            (_DWORD)this,
                            (unsigned int)&v46,
                            (unsigned int)&v45,
                            (__int64)(this + 3)) )
    {
      v17 = VmergeUserAndDomain(&v50, &v46, &v45);
      RWCString::operator=(this + 2, v17);
      v18 = (int *)(v50 - 12);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v50 - 12), 0xFFFFFFFF) == 1 && v18 != &dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v18);
        else
          free(v18);
      }
    }
LABEL_25:
    if ( *((_DWORD *)*v15 - 1) )
    {
      v19 = (char *)Class;
      if ( a3 )
      {
        if ( v45 )
          v19 = v45;
      }
      else if ( a4 )
      {
        if ( v46 )
          v19 = v46;
      }
      else if ( *v15 )
      {
        v19 = *v15;
      }
      RWCString::operator=(a2, v19);
      v9 = 0;
      goto LABEL_104;
    }
    v20 = Name;
    ReferencedDomainName = Block;
    cchName[1] = 257;
    cchName[0] = 16;
    v49 = (VgenericStatus *)(this + 3);
    *((_DWORD *)this + 6) = 7;
    v43 = 0;
    v44 = 0;
    if ( !LookupAccountSidW(0, *this, Name, &cchName[1], Block, cchName, (PSID_NAME_USE)this + 6) )
    {
      if ( cchName[1] > 0x101 )
      {
        v23 = 2LL * cchName[1];
        if ( !is_mul_ok(cchName[1], 2u) )
          v23 = -1;
        if ( dword_1802B0018 )
          v24 = (WCHAR *)COWSAllocator::AllocCurrentHeap(v23);
        else
          v24 = (WCHAR *)malloc(v23);
        v20 = v24;
        v43 = 1;
        v22 = cchName[0];
      }
      else
      {
        v22 = cchName[0];
        if ( cchName[0] <= 0x10 )
        {
LABEL_55:
          if ( GetLastError() == 1332 )
          {
            *(_DWORD *)v49 = 7;
            WellKnownGroups = VprocessGlobals::getWellKnownGroups((VprocessGlobals *)&off_1802AB3C8);
            sub_180101DC0((__int64)WellKnownGroups);
            RWCString::operator=(&v45, *((_QWORD *)WellKnownGroups + 17));
            v29 = VprocessGlobals::getWellKnownGroups((VprocessGlobals *)&off_1802AB3C8);
            sub_180101DC0((__int64)v29);
            RWCString::operator=(&v46, *((_QWORD *)v29 + 7));
            v30 = VmergeUserAndDomain(v51, &v46, &v45);
            RWCString::operator=(v15, v30);
            v31 = (int *)(v51[0] - 12LL);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v51[0] - 12LL), 0xFFFFFFFF) == 1
              && v31 != &dword_1802AFD50 )
            {
              if ( dword_1802B0018 )
                COWSAllocator::Free(v31);
              else
                free(v31);
            }
            v32 = (char *)Class;
            if ( a3 )
            {
              if ( v45 )
                v32 = v45;
            }
            else if ( a4 )
            {
              if ( v46 )
                v32 = v46;
            }
            else if ( *v15 )
            {
              v32 = *v15;
            }
            RWCString::operator=(a2, v32);
          }
          else
          {
            v33 = GetLastError();
            if ( dword_1802B0018 )
              v34 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
            else
              v34 = (VgenericStatus *)malloc(0x20u);
            v49 = v34;
            if ( v34 )
              v9 = VgenericStatus::VgenericStatus(v34, 0xE0024u, v33);
            else
              v9 = 0;
          }
LABEL_96:
          if ( v43 )
          {
            if ( dword_1802B0018 )
              COWSAllocator::Free(v20);
            else
              free(v20);
          }
          if ( v44 )
          {
            if ( dword_1802B0018 )
              COWSAllocator::Free(ReferencedDomainName);
            else
              free(ReferencedDomainName);
          }
          goto LABEL_104;
        }
      }
      if ( v22 > 0x10 )
      {
        v26 = v22;
        v25 = 2LL * v22;
        if ( !is_mul_ok(v26, 2u) )
          v25 = -1;
        if ( dword_1802B0018 )
          v27 = (WCHAR *)COWSAllocator::AllocCurrentHeap(v25);
        else
          v27 = (WCHAR *)malloc(v25);
        ReferencedDomainName = v27;
        v44 = 1;
      }
      if ( !LookupAccountSidW(0, *this, v20, &cchName[1], ReferencedDomainName, cchName, (PSID_NAME_USE)this + 6) )
        goto LABEL_55;
    }
    Vstring::InitUnicode((Vstring *)&v46, v20);
    Vstring::InitUnicode((Vstring *)&v45, ReferencedDomainName);
    v35 = VmergeUserAndDomain(&v48, &v46, &v45);
    RWCString::operator=(this + 2, v35);
    v36 = (int *)((char *)v48 - 12);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v48 - 3, 0xFFFFFFFF) == 1 && v36 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v36);
      else
        free(v36);
    }
    v37 = (char *)Class;
    if ( a3 )
    {
      if ( v45 )
        v37 = v45;
    }
    else if ( a4 )
    {
      if ( v46 )
        v37 = v46;
    }
    else if ( *v15 )
    {
      v37 = *v15;
    }
    RWCString::operator=(a2, v37);
    if ( *((_DWORD *)v45 - 1) || *((_DWORD *)this + 6) == 5 )
    {
      v38 = VprocessGlobals::getSidCache((VprocessGlobals *)&off_1802AB3C8);
      sub_1800B3A44(v38, &v46, &v45, *this, *((_DWORD *)this + 6));
    }
    goto LABEL_96;
  }
  if ( !a3 && !a4 )
    goto LABEL_25;
  v9 = VsplitUserAndDomain((const struct Vstring *)(this + 2), (struct Vstring *)&v46, (struct Vstring *)&v45);
  if ( !v9 )
    goto LABEL_25;
LABEL_104:
  v39 = v45 - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v45 - 3, 0xFFFFFFFF) == 1 && v39 != (char *)&dword_1802AFD50 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(v39);
    else
      free(v39);
  }
  v40 = v46 - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v46 - 3, 0xFFFFFFFF) == 1 && v40 != (char *)&dword_1802AFD50 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(v40);
    else
      free(v40);
  }
  return v9;
}

```

## disassembly

```asm
0x1800b1e30  mov     rax, rsp
0x1800b1e33  push    rbp
0x1800b1e34  push    rsi
0x1800b1e35  push    rdi
0x1800b1e36  push    r12
0x1800b1e38  push    r13
0x1800b1e3a  push    r14
0x1800b1e3c  push    r15
0x1800b1e3e  lea     rbp, [rax-208h]
0x1800b1e45  sub     rsp, 2D0h
0x1800b1e4c  mov     [rbp+200h+var_280], 0FFFFFFFFFFFFFFFEh
0x1800b1e54  mov     [rax+18h], rbx
0x1800b1e58  mov     rax, cs:__security_cookie
0x1800b1e5f  xor     rax, rsp
0x1800b1e62  mov     [rbp+200h+var_40], rax
0x1800b1e69  mov     r13b, r9b
0x1800b1e6c  mov     byte ptr [rsp+300h+var_2C0+1], r9b
0x1800b1e71  mov     r12b, r8b
0x1800b1e74  mov     byte ptr [rsp+300h+var_2C0], r8b
0x1800b1e79  mov     rsi, rdx
0x1800b1e7c  mov     rbx, rcx
0x1800b1e7f  xor     edi, edi
0x1800b1e81  mov     r14d, edi
0x1800b1e84  cmp     [rcx], rdi
0x1800b1e87  jnz     short loc_1800B1ECE
0x1800b1e89  call    cs:GetLastError
0x1800b1e8f  mov     ebx, eax
0x1800b1e91  lea     ecx, [rdi+20h]; unsigned __int64
0x1800b1e94  cmp     cs:dword_1802B0018, edi
0x1800b1e9a  jz      short loc_1800B1EA3
0x1800b1e9c  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800b1ea1  jmp     short loc_1800B1EA9
0x1800b1ea3  call    cs:malloc
0x1800b1ea9  mov     [rsp+300h+var_2A0], rax
0x1800b1eae  test    rax, rax
0x1800b1eb1  jz      short loc_1800B1EC6
0x1800b1eb3  mov     r8d, ebx; int
0x1800b1eb6  mov     edx, 0E0024h; unsigned int
0x1800b1ebb  mov     rcx, rax; this
0x1800b1ebe  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1800b1ec3  mov     rdi, rax
0x1800b1ec6  mov     rax, rdi
0x1800b1ec9  jmp     loc_1800B2455
0x1800b1ece  mov     rcx, [rcx]; pSid
0x1800b1ed1  call    cs:IsValidSid
0x1800b1ed7  test    eax, eax
0x1800b1ed9  jnz     short loc_1800B1F1C
0x1800b1edb  call    cs:GetLastError
0x1800b1ee1  mov     ebx, eax
0x1800b1ee3  mov     ecx, 20h ; ' '; unsigned __int64
0x1800b1ee8  cmp     cs:dword_1802B0018, edi
0x1800b1eee  jz      short loc_1800B1EF7
0x1800b1ef0  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800b1ef5  jmp     short loc_1800B1EFD
0x1800b1ef7  call    cs:malloc
0x1800b1efd  mov     [rsp+300h+var_2A0], rax
0x1800b1f02  test    rax, rax
0x1800b1f05  jz      short loc_1800B1F1A
0x1800b1f07  mov     r8d, ebx; int
0x1800b1f0a  mov     edx, 0E0024h; unsigned int
0x1800b1f0f  mov     rcx, rax; this
0x1800b1f12  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1800b1f17  mov     rdi, rax
0x1800b1f1a  jmp     short loc_1800B1EC6
0x1800b1f1c  lea     rax, dword_1802AFD5C
0x1800b1f23  mov     qword ptr [rsp+300h+var_2B0], rax
0x1800b1f28  lock inc cs:dword_1802AFD50
0x1800b1f2f  mov     [rsp+300h+var_2B8], rax
0x1800b1f34  lock inc cs:dword_1802AFD50
0x1800b1f3b  lea     r15, [rbx+10h]
0x1800b1f3f  mov     rax, [r15]
0x1800b1f42  cmp     [rax-4], edi
0x1800b1f45  jnz     loc_1800B1FD8
0x1800b1f4b  lea     rcx, off_1802AB3C8; this
0x1800b1f52  call    ?getSidCache@VprocessGlobals@@QEAAPEAVVsidCache@@XZ; VprocessGlobals::getSidCache(void)
0x1800b1f57  lea     rcx, [rbx+18h]
0x1800b1f5b  mov     [rsp+300h+ReferencedDomainName], rcx
0x1800b1f60  lea     r9, [rsp+300h+var_2B8]
0x1800b1f65  lea     r8, [rsp+300h+var_2B0]
0x1800b1f6a  mov     rdx, rbx
0x1800b1f6d  mov     rcx, rax
0x1800b1f70  call    sub_1800B3554
0x1800b1f75  test    al, al
0x1800b1f77  jz      loc_1800B2000
0x1800b1f7d  lea     r8, [rsp+300h+var_2B8]
0x1800b1f82  lea     rdx, [rsp+300h+var_2B0]
0x1800b1f87  lea     rcx, [rsp+300h+var_290]
0x1800b1f8c  call    ?VmergeUserAndDomain@@YA?AVVstring@@AEBV1@0@Z; VmergeUserAndDomain(Vstring const &,Vstring const &)
0x1800b1f91  nop
0x1800b1f92  mov     rdx, rax
0x1800b1f95  mov     rcx, r15
0x1800b1f98  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x1800b1f9d  nop
0x1800b1f9e  mov     rcx, [rsp+300h+var_290]
0x1800b1fa3  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800b1fa7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800b1fab  mov     eax, edx
0x1800b1fad  lock xadd [rcx], eax
0x1800b1fb1  add     eax, edx
0x1800b1fb3  jnz     short loc_1800B2000
0x1800b1fb5  lea     rax, dword_1802AFD50
0x1800b1fbc  cmp     rcx, rax
0x1800b1fbf  jz      short loc_1800B2000
0x1800b1fc1  cmp     cs:dword_1802B0018, edi
0x1800b1fc7  jz      short loc_1800B1FD0
0x1800b1fc9  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800b1fce  jmp     short loc_1800B2000
0x1800b1fd0  call    cs:free
0x1800b1fd6  jmp     short loc_1800B2000
0x1800b1fd8  test    r12b, r12b
0x1800b1fdb  jnz     short loc_1800B1FE2
0x1800b1fdd  test    r13b, r13b
0x1800b1fe0  jz      short loc_1800B2000
0x1800b1fe2  lea     r8, [rsp+300h+var_2B8]; struct Vstring *
0x1800b1fe7  lea     rdx, [rsp+300h+var_2B0]; struct Vstring *
0x1800b1fec  mov     rcx, r15; struct Vstring *
0x1800b1fef  call    ?VsplitUserAndDomain@@YAPEAVVstatus@@AEBVVstring@@AEAV2@1@Z; VsplitUserAndDomain(Vstring const &,Vstring &,Vstring &)
0x1800b1ff4  mov     r14, rax
0x1800b1ff7  test    rax, rax
0x1800b1ffa  jnz     loc_1800B23E6
0x1800b2000  mov     rax, [r15]
0x1800b2003  cmp     [rax-4], edi
0x1800b2006  jz      short loc_1800B204A
0x1800b2008  lea     rdx, Class
0x1800b200f  test    r12b, r12b
0x1800b2012  jz      short loc_1800B2021
0x1800b2014  cmp     [rsp+300h+var_2B8], rdi
0x1800b2019  cmovnz  rdx, [rsp+300h+var_2B8]
0x1800b201f  jmp     short loc_1800B203A
0x1800b2021  test    r13b, r13b
0x1800b2024  jz      short loc_1800B2033
0x1800b2026  cmp     qword ptr [rsp+300h+var_2B0], rdi
0x1800b202b  cmovnz  rdx, qword ptr [rsp+300h+var_2B0]
0x1800b2031  jmp     short loc_1800B203A
0x1800b2033  test    rax, rax
0x1800b2036  cmovnz  rdx, rax; char *
0x1800b203a  mov     rcx, rsi; this
0x1800b203d  call    ??4RWCString@@QEAAAEAV0@PEBD@Z; RWCString::operator=(char const *)
0x1800b2042  mov     r14, rdi
0x1800b2045  jmp     loc_1800B23E6
0x1800b204a  lea     r13, [rbp+200h+Name]
0x1800b204e  lea     r12, [rbp+200h+Block]
0x1800b2052  mov     [rsp+300h+cchName+4], 101h
0x1800b205a  mov     [rsp+300h+cchName], 10h
0x1800b2062  lea     rax, [rbx+18h]
0x1800b2066  mov     [rsp+300h+var_298], rax
0x1800b206b  mov     dword ptr [rax], 7
0x1800b2071  mov     byte ptr [rsp+300h+var_2C0+2], dil
0x1800b2076  mov     byte ptr [rsp+300h+var_2C0+3], dil
0x1800b207b  mov     [rsp+30h], rax; peUse
0x1800b2080  lea     rax, [rsp+300h+cchName]
0x1800b2085  mov     [rsp+300h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800b208a  lea     rax, [rbp+200h+Block]
0x1800b208e  mov     [rsp+300h+ReferencedDomainName], rax; ReferencedDomainName
0x1800b2093  lea     r9, [rsp+300h+cchName+4]; cchName
0x1800b2098  lea     r8, [rbp+200h+Name]; Name
0x1800b209c  mov     rdx, [rbx]; Sid
0x1800b209f  xor     ecx, ecx; lpSystemName
0x1800b20a1  call    cs:LookupAccountSidW
0x1800b20a7  test    al, al
0x1800b20a9  jnz     loc_1800B22BE
0x1800b20af  cmp     [rsp+300h+cchName+4], 101h
0x1800b20b7  ja      short loc_1800B20C8
0x1800b20b9  mov     eax, [rsp+300h+cchName]
0x1800b20bd  cmp     eax, 10h
0x1800b20c0  jbe     loc_1800B2170
0x1800b20c6  jmp     short loc_1800B2103
0x1800b20c8  mov     ecx, [rsp+300h+cchName+4]
0x1800b20cc  mov     eax, 2
0x1800b20d1  mul     rcx
0x1800b20d4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b20db  cmovo   rax, rcx
0x1800b20df  mov     rcx, rax; unsigned __int64
0x1800b20e2  cmp     cs:dword_1802B0018, edi
0x1800b20e8  jz      short loc_1800B20F1
0x1800b20ea  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800b20ef  jmp     short loc_1800B20F7
0x1800b20f1  call    cs:malloc
0x1800b20f7  mov     r13, rax
0x1800b20fa  mov     byte ptr [rsp+300h+var_2C0+2], 1
0x1800b20ff  mov     eax, [rsp+300h+cchName]
0x1800b2103  cmp     eax, 10h
0x1800b2106  jbe     short loc_1800B213D
0x1800b2108  mov     ecx, eax
0x1800b210a  mov     eax, 2
0x1800b210f  mul     rcx
0x1800b2112  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b2119  cmovo   rax, rcx
0x1800b211d  mov     rcx, rax; unsigned __int64
0x1800b2120  cmp     cs:dword_1802B0018, edi
0x1800b2126  jz      short loc_1800B212F
0x1800b2128  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800b212d  jmp     short loc_1800B2135
0x1800b212f  call    cs:malloc
0x1800b2135  mov     r12, rax
0x1800b2138  mov     byte ptr [rsp+300h+var_2C0+3], 1
0x1800b213d  lea     rax, [rbx+18h]
0x1800b2141  mov     [rsp+30h], rax; peUse
0x1800b2146  lea     rax, [rsp+300h+cchName]
0x1800b214b  mov     [rsp+300h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800b2150  mov     [rsp+300h+ReferencedDomainName], r12; ReferencedDomainName
0x1800b2155  lea     r9, [rsp+300h+cchName+4]; cchName
0x1800b215a  mov     r8, r13; Name
0x1800b215d  mov     rdx, [rbx]; Sid
0x1800b2160  xor     ecx, ecx; lpSystemName
0x1800b2162  call    cs:LookupAccountSidW
0x1800b2168  test    al, al
0x1800b216a  jnz     loc_1800B22BE
0x1800b2170  call    cs:GetLastError
0x1800b2176  cmp     eax, 534h
0x1800b217b  jnz     loc_1800B2275
0x1800b2181  mov     rax, [rsp+300h+var_298]
0x1800b2186  mov     dword ptr [rax], 7
0x1800b218c  lea     rcx, off_1802AB3C8; this
0x1800b2193  call    ?getWellKnownGroups@VprocessGlobals@@QEAAPEAVVwellKnownGroups@@XZ; VprocessGlobals::getWellKnownGroups(void)
0x1800b2198  mov     rbx, rax
0x1800b219b  mov     rcx, rax
0x1800b219e  call    sub_180101DC0
0x1800b21a3  mov     rdx, [rbx+88h]
0x1800b21aa  lea     rcx, [rsp+300h+var_2B8]
0x1800b21af  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x1800b21b4  lea     rcx, off_1802AB3C8; this
0x1800b21bb  call    ?getWellKnownGroups@VprocessGlobals@@QEAAPEAVVwellKnownGroups@@XZ; VprocessGlobals::getWellKnownGroups(void)
0x1800b21c0  mov     rbx, rax
0x1800b21c3  mov     rcx, rax
0x1800b21c6  call    sub_180101DC0
0x1800b21cb  mov     rdx, [rbx+38h]
0x1800b21cf  lea     rcx, [rsp+300h+var_2B0]
0x1800b21d4  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x1800b21d9  lea     r8, [rsp+300h+var_2B8]
0x1800b21de  lea     rdx, [rsp+300h+var_2B0]
0x1800b21e3  lea     rcx, [rsp+78h]
0x1800b21e8  call    ?VmergeUserAndDomain@@YA?AVVstring@@AEBV1@0@Z; VmergeUserAndDomain(Vstring const &,Vstring const &)
0x1800b21ed  nop
0x1800b21ee  mov     rdx, rax
0x1800b21f1  mov     rcx, r15
0x1800b21f4  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x1800b21f9  nop
0x1800b21fa  mov     rcx, [rsp+78h]
0x1800b21ff  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x1800b2203  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800b2207  mov     eax, edx
0x1800b2209  lock xadd [rcx], eax
0x1800b220d  add     eax, edx
0x1800b220f  jnz     short loc_1800B2232
0x1800b2211  lea     rax, dword_1802AFD50
0x1800b2218  cmp     rcx, rax
0x1800b221b  jz      short loc_1800B2232
0x1800b221d  cmp     cs:dword_1802B0018, edi
0x1800b2223  jz      short loc_1800B222C
0x1800b2225  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800b222a  jmp     short loc_1800B2232
0x1800b222c  call    cs:free
0x1800b2232  lea     rdx, Class
0x1800b2239  mov     rcx, rsi; this
0x1800b223c  cmp     byte ptr [rsp+300h+var_2C0], dil
0x1800b2241  jz      short loc_1800B2250
0x1800b2243  cmp     [rsp+300h+var_2B8], rdi
0x1800b2248  cmovnz  rdx, [rsp+300h+var_2B8]
0x1800b224e  jmp     short loc_1800B226B
0x1800b2250  cmp     byte ptr [rsp+300h+var_2C0+1], dil
0x1800b2255  jz      short loc_1800B2264
0x1800b2257  cmp     qword ptr [rsp+300h+var_2B0], rdi
0x1800b225c  cmovnz  rdx, qword ptr [rsp+300h+var_2B0]
0x1800b2262  jmp     short loc_1800B226B
0x1800b2264  cmp     [r15], rdi
0x1800b2267  cmovnz  rdx, [r15]; char *
0x1800b226b  call    ??4RWCString@@QEAAAEAV0@PEBD@Z; RWCString::operator=(char const *)
0x1800b2270  jmp     loc_1800B23A7
0x1800b2275  call    cs:GetLastError
0x1800b227b  mov     ebx, eax
0x1800b227d  mov     ecx, 20h ; ' '; unsigned __int64
0x1800b2282  cmp     cs:dword_1802B0018, edi
0x1800b2288  jz      short loc_1800B2291
0x1800b228a  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800b228f  jmp     short loc_1800B2297
0x1800b2291  call    cs:malloc
0x1800b2297  mov     [rsp+300h+var_298], rax
0x1800b229c  test    rax, rax
0x1800b229f  jz      short loc_1800B22B6
0x1800b22a1  mov     r8d, ebx; int
0x1800b22a4  mov     edx, 0E0024h; unsigned int
0x1800b22a9  mov     rcx, rax; this
0x1800b22ac  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1800b22b1  mov     r14, rax
0x1800b22b4  jmp     short loc_1800B22B9
0x1800b22b6  mov     r14, rdi
0x1800b22b9  jmp     loc_1800B23A7
0x1800b22be  mov     rdx, r13; wchar_t *
0x1800b22c1  lea     rcx, [rsp+300h+var_2B0]; this
0x1800b22c6  call    ?InitUnicode@Vstring@@AEAAXPEB_W@Z; Vstring::InitUnicode(wchar_t const *)
0x1800b22cb  mov     rdx, r12; wchar_t *
0x1800b22ce  lea     rcx, [rsp+300h+var_2B8]; this
0x1800b22d3  call    ?InitUnicode@Vstring@@AEAAXPEB_W@Z; Vstring::InitUnicode(wchar_t const *)
0x1800b22d8  lea     r8, [rsp+300h+var_2B8]
0x1800b22dd  lea     rdx, [rsp+300h+var_2B0]
0x1800b22e2  lea     rcx, [rsp+300h+var_2A0]
0x1800b22e7  call    ?VmergeUserAndDomain@@YA?AVVstring@@AEBV1@0@Z; VmergeUserAndDomain(Vstring const &,Vstring const &)
0x1800b22ec  nop
0x1800b22ed  mov     rdx, rax
  ... truncated ...
```
