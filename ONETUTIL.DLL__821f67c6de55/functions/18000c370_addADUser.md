# addADUser

- ea: `0x18000c370`
- end: `0x18000cbef`
- name: `addADUser`
- size: `2175`
- prototype: `__int64 __usercall@<rax>(wchar_t *@<rcx>, LPCWSTR DomainName@<rdx>, wchar_t *@<r8>, __int64, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x18000b47c`
- `0x18000bcd0`
- `0x18000bd90`
- `0x18000bea8`
- `0x18000c370`
- `0x18000cbf0`
- `0x180040c10`
- `0x180083790`
- `0x1800838f0`
- `0x1800b6760`
- `0x1800b93d0`
- `0x1800d9fd0`
- `0x1800da020`
- `0x1801503e0`
- `0x18015197d`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x18000c410`
- `KERNEL32!TlsGetValue` at `0x18000ca1f`
- `KERNEL32!TlsGetValue` at `0x18000c410`
- `KERNEL32!TlsGetValue` at `0x18000ca1f`
- `NETAPI32!NetUserSetInfo` at `0x18000c943`
- `NETAPI32!NetUserSetInfo` at `0x18000c943`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000c9ee`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000cb66`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000cb94`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000cbc2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000c9ee`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000cb66`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000cb94`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000cbc2`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000caa5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000caa5`
- `ACTIVEDS!ADsGetObject` at `0x18000c7f8`
- `ACTIVEDS!ADsGetObject` at `0x18000c7f8`
- `OLEAUT32!SysAllocString` at `0x18000c868`
- `OLEAUT32!SysAllocString` at `0x18000c868`
- `OLEAUT32!SysFreeString` at `0x18000c80c`
- `OLEAUT32!SysFreeString` at `0x18000c899`
- `OLEAUT32!SysFreeString` at `0x18000c9bb`
- `OLEAUT32!SysFreeString` at `0x18000ca4e`
- `OLEAUT32!SysFreeString` at `0x18000c80c`
- `OLEAUT32!SysFreeString` at `0x18000c899`
- `OLEAUT32!SysFreeString` at `0x18000c9bb`
- `OLEAUT32!SysFreeString` at `0x18000ca4e`
- `OLEAUT32!VariantInit` at `0x18000c688`
- `OLEAUT32!VariantInit` at `0x18000c688`
- `onetnative!ULSTemplate_` at `0x18000c799`
- `onetnative!ULSTemplate_` at `0x18000c799`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall addADUser(wchar_t *a1, LPCWSTR DomainName, wchar_t *a3, __int64 a4, OLECHAR *a5, __int64 a6)
{
  wchar_t *v6; // rdi
  const WCHAR *v7; // r14
  wchar_t *v8; // r13
  int v9; // esi
  int v10; // r15d
  VthreadContext *Value; // rax
  struct Vstatus *v12; // rax
  __int64 result; // rax
  int Object; // edi
  struct IADsContainer *v15; // r12
  struct _RTL_CRITICAL_SECTION *v16; // r14
  __int64 v17; // rcx
  const wchar_t *v18; // rdi
  __int64 v19; // rdi
  __int64 v20; // rcx
  wchar_t *v21; // rdi
  __int64 v22; // rdi
  __int64 v23; // rax
  wchar_t *v24; // r15
  __int64 v25; // rax
  OLECHAR *v26; // rdi
  VthreadContext *v27; // rax
  struct Vstatus *v28; // rax
  VgenericStatus *v29; // rax
  VgenericStatus *v30; // rdi
  WCHAR *v31; // rcx
  wchar_t *v32; // rcx
  OLECHAR *v33; // rcx
  unsigned int v34; // [rsp+40h] [rbp-558h]
  void *ppObject; // [rsp+48h] [rbp-550h] BYREF
  wchar_t *v36; // [rsp+50h] [rbp-548h] BYREF
  LPCWSTR DomainNamea; // [rsp+58h] [rbp-540h] BYREF
  int v38; // [rsp+60h] [rbp-538h]
  LPCWSTR servername; // [rsp+68h] [rbp-530h] BYREF
  OLECHAR *psz; // [rsp+70h] [rbp-528h] BYREF
  __int64 v41; // [rsp+78h] [rbp-520h] BYREF
  LPCWSTR lpszPathName; // [rsp+80h] [rbp-518h] BYREF
  BYTE buf[8]; // [rsp+88h] [rbp-510h] BYREF
  __int64 v44; // [rsp+90h] [rbp-508h]
  struct IADsContainer *v45; // [rsp+98h] [rbp-500h]
  wchar_t *v46; // [rsp+A0h] [rbp-4F8h]
  int v47; // [rsp+A8h] [rbp-4F0h]
  int v48; // [rsp+B0h] [rbp-4E8h]
  const wchar_t *v49; // [rsp+B8h] [rbp-4E0h]
  wchar_t *v50; // [rsp+C0h] [rbp-4D8h]
  wchar_t *v51; // [rsp+C8h] [rbp-4D0h]
  LPCWSTR v52; // [rsp+D0h] [rbp-4C8h]
  VARIANTARG pvarg; // [rsp+D8h] [rbp-4C0h] BYREF
  __int64 v54; // [rsp+F0h] [rbp-4A8h]
  struct _RTL_CRITICAL_SECTION *v55; // [rsp+F8h] [rbp-4A0h]
  wchar_t *v56; // [rsp+100h] [rbp-498h]
  OLECHAR *v57; // [rsp+108h] [rbp-490h]
  VARIANTARG v58; // [rsp+110h] [rbp-488h] BYREF
  void *Block; // [rsp+130h] [rbp-468h] BYREF
  _BYTE v60[1028]; // [rsp+138h] [rbp-460h] BYREF
  unsigned int v61; // [rsp+53Ch] [rbp-5Ch]
  unsigned int v62; // [rsp+540h] [rbp-58h]

  v54 = -2;
  *(_QWORD *)buf = a4;
  v6 = a3;
  v36 = a3;
  v7 = DomainName;
  DomainNamea = DomainName;
  v8 = a1;
  v51 = a1;
  v52 = DomainName;
  v46 = a3;
  psz = a5;
  v44 = a6;
  v9 = 1;
  v10 = 1;
  v38 = 1;
  servername = 0;
  Value = (VthreadContext *)TlsGetValue(dwTlsIndex);
  v12 = VthreadContext::suspendImpersonation(Value);
  if ( v12 )
  {
    (**(void (__fastcall ***)(struct Vstatus *, __int64))v12)(v12, 1);
    return 2147500037LL;
  }
  try
  {
    Block = v60;
    v61 = 0;
    v62 = 512;
    while ( 1 )
    {
      v45 = 0;
      v41 = 0;
      ppObject = 0;
      lpszPathName = 0;
      Object = sub_18000BD90(v7, v6, (__int64)&servername);
      v34 = Object;
      if ( Object >= 0 && (v15 = v45) != 0 )
      {
        v16 = (struct _RTL_CRITICAL_SECTION *)sub_18000B47C();
        v55 = v16;
        v17 = 0;
        v61 = 0;
        v18 = L"CN=";
        v49 = L"CN=";
        while ( *v18 )
          v49 = ++v18;
        v19 = v18 - L"CN=";
        v47 = v19;
        if ( (unsigned int)v19 > v62 )
        {
          VwstackBuffer512::reallocate((VwstackBuffer512 *)&Block, v19);
          v17 = v61;
        }
        memcpy((char *)Block + 2 * v17, L"CN=", 2LL * (unsigned int)v19);
        v20 = (unsigned int)v19 + v61;
        v61 += v19;
        v21 = v8;
        v50 = v8;
        v56 = v8;
        while ( *v21 )
          v50 = ++v21;
        v22 = v21 - v8;
        v48 = v22;
        if ( (int)v20 + (int)v22 > v62 )
        {
          VwstackBuffer512::reallocate((VwstackBuffer512 *)&Block, v22);
          v20 = v61;
        }
        memcpy((char *)Block + 2 * v20, v8, 2LL * (unsigned int)v22);
        v61 += v22;
        *((_WORD *)Block + v61) = 0;
        Object = ((__int64 (__fastcall *)(struct IADsContainer *, const wchar_t *, void *, __int64 *))v15->lpVtbl->Create)(
                   v15,
                   L"User",
                   Block,
                   &v41);
        v34 = Object;
        ((void (__fastcall *)(struct IADsContainer *))v15->lpVtbl->Release)(v15);
        if ( Object >= 0 && v41 )
        {
          Object = (**(__int64 (__fastcall ***)(__int64, const IID *, void **))v41)(v41, &stru_180176A90, &ppObject);
          v34 = Object;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
          if ( Object < 0 || !ppObject )
            goto LABEL_21;
          VariantInit(&pvarg);
          pvarg.llVal = (LONGLONG)v8;
          pvarg.vt = 8;
          v58 = pvarg;
          Object = (*(__int64 (__fastcall **)(void *, const wchar_t *, VARIANTARG *))(*(_QWORD *)ppObject + 128LL))(
                     ppObject,
                     L"samAccountName",
                     &v58);
          v34 = Object;
          v23 = *(_QWORD *)ppObject;
          if ( Object < 0 )
          {
            (*(void (**)(void))(v23 + 16))();
            goto LABEL_21;
          }
          Object = (*(__int64 (**)(void))(v23 + 112))();
          v34 = Object;
          v25 = *(_QWORD *)ppObject;
          if ( Object >= 0 )
          {
            Object = (*(__int64 (__fastcall **)(void *, LPCWSTR *))(v25 + 80))(ppObject, &lpszPathName);
            v34 = Object;
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
            if ( Object < 0
              || !lpszPathName
              || (ppObject = 0,
                  Object = ADsGetObject(lpszPathName, &stru_180176A90, &ppObject),
                  v34 = Object,
                  SysFreeString((BSTR)lpszPathName),
                  Object < 0)
              || !ppObject )
            {
              if ( v16 )
                CADObjectsPool::ReleaseADObject(v16, v15);
LABEL_52:
              v9 = 0;
              goto LABEL_53;
            }
            Object = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppObject + 552LL))(ppObject, 0);
            v34 = Object;
            if ( Object < 0 )
            {
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
              goto LABEL_52;
            }
            if ( psz )
            {
              v26 = SysAllocString(psz);
              v57 = v26;
              if ( v26 )
              {
                (*(void (__fastcall **)(void *, OLECHAR *))(*(_QWORD *)ppObject + 760LL))(ppObject, v26);
                SysFreeString(v26);
              }
            }
            Object = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppObject + 112LL))(ppObject);
            v34 = Object;
            if ( Object < 0 )
            {
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
LABEL_44:
              if ( v16 )
                CADObjectsPool::ReleaseADObject(v16, v15);
LABEL_53:
              v24 = v36;
              v7 = DomainNamea;
              deleteADUser(v8, DomainNamea, v36);
LABEL_24:
              if ( Block != v60 )
              {
                if ( dword_1802B0018 )
                  COWSAllocator::Free(Block);
                else
                  free(Block);
              }
              goto LABEL_98;
            }
            Object = sub_18000BEA8((__int64)ppObject, v44);
            v34 = Object;
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
            if ( Object < 0 )
              goto LABEL_44;
            if ( *(_QWORD *)buf )
            {
              LODWORD(v44) = NetUserSetInfo(servername, v8, 0x3EBu, buf, 0);
              if ( (_DWORD)v44 )
              {
                Object = -2147467259;
                v34 = -2147467259;
                goto LABEL_53;
              }
            }
LABEL_22:
            v7 = DomainNamea;
LABEL_23:
            v24 = v36;
            goto LABEL_24;
          }
          (*(void (**)(void))(v25 + 16))();
          if ( v16 )
            CADObjectsPool::ReleaseADObject(v16, v15);
          if ( !v10 )
          {
            if ( Object == -2147024891 )
              ULSTemplate_(3359, 117141517);
LABEL_21:
            v9 = 0;
            goto LABEL_22;
          }
        }
        else
        {
          if ( v16 )
            CADObjectsPool::ReleaseADObject(v16, v15);
          if ( !v10 )
            goto LABEL_21;
        }
        v10 = 0;
        v38 = 0;
        SysFreeString((BSTR)servername);
        servername = 0;
        v7 = DomainNamea;
      }
      else
      {
        if ( !v10 )
        {
          v9 = 0;
          goto LABEL_23;
        }
        v10 = 0;
        v38 = 0;
      }
      v6 = v36;
    }
  }
  catch ( ... )
  {
    if ( dword_1802B0018 )
      COWSAllocator::SetThreadCrashed(1);
    Object = v34;
    v9 = 0;
    v8 = v51;
    v7 = v52;
    v24 = v46;
  }
LABEL_98:
  v27 = (VthreadContext *)TlsGetValue(dwTlsIndex);
  v28 = VthreadContext::resumeImpersonation(v27);
  if ( v28 )
    (**(void (__fastcall ***)(struct Vstatus *, __int64))v28)(v28, 1);
  SysFreeString((BSTR)servername);
  if ( Object < 0 )
  {
    Vstring::Vstring((Vstring *)&psz, v8);
    Vstring::Vstring((Vstring *)&v36, v24);
    Vstring::Vstring((Vstring *)&DomainNamea, v7);
    if ( dword_1802B0018 )
      v29 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v29 = (VgenericStatus *)malloc(0x20u);
    v46 = (wchar_t *)v29;
    if ( v29 )
      v30 = VgenericStatus::VgenericStatus(v29, 0x1E0046u, 0, psz, v36, DomainNamea, Object);
    else
      v30 = 0;
    if ( v30 )
    {
      (*(void (__fastcall **)(void *, __int64, __int64, __int64, VgenericStatus *))(off_1802AB3C8 + 32LL))(
        &off_1802AB3C8,
        946501219,
        117141511,
        65534,
        v30);
      (**(void (__fastcall ***)(VgenericStatus *, __int64))v30)(v30, 1);
    }
    v31 = (WCHAR *)(DomainNamea - 6);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)DomainNamea - 3, 0xFFFFFFFF) == 1
      && v31 != (WCHAR *)&dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v31);
      else
        free(v31);
    }
    v32 = v36 - 6;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v36 - 3, 0xFFFFFFFF) == 1
      && v32 != (wchar_t *)&dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v32);
      else
        free(v32);
    }
    v33 = psz - 6;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)psz - 3, 0xFFFFFFFF) == 1
      && v33 != (OLECHAR *)&dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v33);
      else
        free(v33);
    }
    return v34;
  }
  else
  {
    result = 2147549183LL;
    if ( v9 )
      return (unsigned int)Object;
  }
  return result;
}

```

## disassembly

```asm
0x18000c370  push    rbx
0x18000c372  push    rsi
0x18000c373  push    rdi
0x18000c374  push    r12
0x18000c376  push    r13
0x18000c378  push    r14
0x18000c37a  push    r15
0x18000c37c  sub     rsp, 560h
0x18000c383  mov     [rsp+598h+var_4A8], 0FFFFFFFFFFFFFFFEh
0x18000c38f  mov     rax, cs:__security_cookie
0x18000c396  xor     rax, rsp
0x18000c399  mov     [rsp+598h+var_48], rax
0x18000c3a1  mov     qword ptr [rsp+598h+buf], r9
0x18000c3a9  mov     rdi, r8
0x18000c3ac  mov     [rsp+598h+var_548], r8
0x18000c3b1  mov     r14, rdx
0x18000c3b4  mov     [rsp+598h+DomainName], rdx
0x18000c3b9  mov     r13, rcx
0x18000c3bc  mov     [rsp+598h+var_4D0], rcx
0x18000c3c4  mov     [rsp+598h+var_4C8], rdx
0x18000c3cc  mov     [rsp+598h+var_4F8], r8
0x18000c3d4  mov     rax, [rsp+598h+arg_20]
0x18000c3dc  mov     [rsp+598h+psz], rax
0x18000c3e1  mov     rax, [rsp+598h+arg_28]
0x18000c3e9  mov     [rsp+598h+var_508], rax
0x18000c3f1  xor     ebx, ebx
0x18000c3f3  mov     [rsp+598h+var_558], ebx
0x18000c3f7  lea     esi, [rbx+1]
0x18000c3fa  mov     [rsp+598h+var_554], esi
0x18000c3fe  mov     r15d, esi
0x18000c401  mov     [rsp+598h+var_538], esi
0x18000c405  mov     [rsp+598h+servername], rbx
0x18000c40a  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000c410  call    cs:TlsGetValue
0x18000c416  mov     rcx, rax; this
0x18000c419  call    ?suspendImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ; VthreadContext::suspendImpersonation(void)
0x18000c41e  mov     r8, rax
0x18000c421  test    rax, rax
0x18000c424  jz      short loc_18000C441
0x18000c426  mov     rcx, [rax]
0x18000c429  mov     rax, [rcx]
0x18000c42c  mov     edx, esi
0x18000c42e  mov     rcx, r8
0x18000c431  call    cs:__guard_dispatch_icall_fptr
0x18000c437  mov     eax, 80004005h
0x18000c43c  jmp     loc_18000CBCC
0x18000c441  lea     rax, [rsp+598h+var_460]
0x18000c449  mov     [rsp+598h+Block], rax
0x18000c451  mov     [rsp+598h+var_5C], ebx
0x18000c458  mov     [rsp+598h+var_58], 200h
0x18000c463  mov     [rsp+598h+var_500], rbx
0x18000c46b  mov     [rsp+598h+var_520], rbx
0x18000c470  mov     [rsp+598h+ppObject], rbx
0x18000c475  mov     [rsp+598h+lpszPathName], rbx
0x18000c47d  mov     r8d, ebx
0x18000c480  test    r15d, r15d
0x18000c483  setz    r8b
0x18000c487  lea     rax, [rsp+598h+servername]
0x18000c48c  mov     [rsp+598h+parm_err], rax; __int64
0x18000c491  lea     r9, [rsp+598h+var_500]
0x18000c499  mov     rdx, rdi; wchar_t *
0x18000c49c  mov     rcx, r14; DomainName
0x18000c49f  call    sub_18000BD90
0x18000c4a4  mov     edi, eax
0x18000c4a6  mov     [rsp+598h+var_558], eax
0x18000c4aa  test    eax, eax
0x18000c4ac  js      loc_18000C9CD
0x18000c4b2  mov     r12, [rsp+598h+var_500]
0x18000c4ba  test    r12, r12
0x18000c4bd  jz      loc_18000C9CD
0x18000c4c3  call    sub_18000B47C
0x18000c4c8  mov     r14, rax
0x18000c4cb  mov     [rsp+598h+var_4A0], rax
0x18000c4d3  mov     ecx, ebx
0x18000c4d5  mov     [rsp+598h+var_5C], ecx
0x18000c4dc  lea     rax, aCn; "CN="
0x18000c4e3  mov     rdi, rax
0x18000c4e6  mov     [rsp+598h+var_4E0], rax
0x18000c4ee  cmp     [rdi], bx
0x18000c4f1  jz      short loc_18000C501
0x18000c4f3  add     rdi, 2
0x18000c4f7  mov     [rsp+598h+var_4E0], rdi
0x18000c4ff  jmp     short loc_18000C4EE
0x18000c501  sub     rdi, rax
0x18000c504  sar     rdi, 1
0x18000c507  mov     [rsp+598h+var_4F0], edi
0x18000c50e  lea     eax, [rcx+rdi]
0x18000c511  cmp     eax, [rsp+598h+var_58]
0x18000c518  jbe     short loc_18000C530
0x18000c51a  mov     edx, edi; unsigned int
0x18000c51c  lea     rcx, [rsp+598h+Block]; this
0x18000c524  call    ?reallocate@VwstackBuffer512@@AEAAXI@Z; VwstackBuffer512::reallocate(uint)
0x18000c529  mov     ecx, [rsp+598h+var_5C]
0x18000c530  mov     r8d, edi
0x18000c533  add     r8, r8; Size
0x18000c536  mov     rax, [rsp+598h+Block]
0x18000c53e  lea     rcx, [rax+rcx*2]; void *
0x18000c542  lea     rdx, aCn; "CN="
0x18000c549  call    memcpy
0x18000c54e  mov     ecx, [rsp+598h+var_5C]
0x18000c555  add     ecx, edi
0x18000c557  mov     [rsp+598h+var_5C], ecx
0x18000c55e  mov     rdi, r13
0x18000c561  mov     [rsp+598h+var_4D8], r13
0x18000c569  mov     [rsp+598h+var_498], r13
0x18000c571  cmp     [rdi], bx
0x18000c574  jz      short loc_18000C584
0x18000c576  add     rdi, 2
0x18000c57a  mov     [rsp+598h+var_4D8], rdi
0x18000c582  jmp     short loc_18000C571
0x18000c584  sub     rdi, r13
0x18000c587  sar     rdi, 1
0x18000c58a  mov     [rsp+598h+var_4E8], edi
0x18000c591  lea     eax, [rcx+rdi]
0x18000c594  cmp     eax, [rsp+598h+var_58]
0x18000c59b  jbe     short loc_18000C5B3
0x18000c59d  mov     edx, edi; unsigned int
0x18000c59f  lea     rcx, [rsp+598h+Block]; this
0x18000c5a7  call    ?reallocate@VwstackBuffer512@@AEAAXI@Z; VwstackBuffer512::reallocate(uint)
0x18000c5ac  mov     ecx, [rsp+598h+var_5C]
0x18000c5b3  mov     r8d, edi
0x18000c5b6  add     r8, r8; Size
0x18000c5b9  mov     rax, [rsp+598h+Block]
0x18000c5c1  lea     rcx, [rax+rcx*2]; void *
0x18000c5c5  mov     rdx, r13; Src
0x18000c5c8  call    memcpy
0x18000c5cd  mov     eax, [rsp+598h+var_5C]
0x18000c5d4  add     eax, edi
0x18000c5d6  mov     [rsp+598h+var_5C], eax
0x18000c5dd  mov     ecx, eax
0x18000c5df  mov     rax, [rsp+598h+Block]
0x18000c5e7  mov     [rax+rcx*2], bx
0x18000c5eb  mov     rax, [r12]
0x18000c5ef  lea     r9, [rsp+598h+var_520]
0x18000c5f4  mov     r8, [rsp+598h+Block]
0x18000c5fc  lea     rdx, aUser; "User"
0x18000c603  mov     rcx, r12
0x18000c606  mov     rax, [rax+70h]
0x18000c60a  call    cs:__guard_dispatch_icall_fptr
0x18000c610  mov     edi, eax
0x18000c612  mov     [rsp+598h+var_558], eax
0x18000c616  mov     rax, [r12]
0x18000c61a  mov     rcx, r12
0x18000c61d  mov     rax, [rax+10h]
0x18000c621  call    cs:__guard_dispatch_icall_fptr
0x18000c627  test    edi, edi
0x18000c629  js      loc_18000C996
0x18000c62f  mov     rcx, [rsp+598h+var_520]
0x18000c634  test    rcx, rcx
0x18000c637  jz      loc_18000C996
0x18000c63d  mov     rax, [rcx]
0x18000c640  lea     r8, [rsp+598h+ppObject]
0x18000c645  lea     rdx, stru_180176A90
0x18000c64c  mov     rax, [rax]
0x18000c64f  call    cs:__guard_dispatch_icall_fptr
0x18000c655  mov     edi, eax
0x18000c657  mov     [rsp+598h+var_558], eax
0x18000c65b  mov     rcx, [rsp+598h+var_520]
0x18000c660  mov     rax, [rcx]
0x18000c663  mov     rax, [rax+10h]
0x18000c667  call    cs:__guard_dispatch_icall_fptr
0x18000c66d  test    edi, edi
0x18000c66f  js      loc_18000C705
0x18000c675  cmp     [rsp+598h+ppObject], rbx
0x18000c67a  jz      loc_18000C705
0x18000c680  lea     rcx, [rsp+598h+pvarg]; pvarg
0x18000c688  call    cs:VariantInit
0x18000c68e  mov     qword ptr [rsp+598h+pvarg+8], r13
0x18000c696  mov     eax, 8
0x18000c69b  mov     word ptr [rsp+598h+pvarg], ax
0x18000c6a3  movups  xmm0, xmmword ptr [rsp+598h+pvarg]
0x18000c6ab  movaps  [rsp+598h+var_488], xmm0
0x18000c6b3  movsd   xmm1, qword ptr [rsp+598h+pvarg+10h]
0x18000c6bc  movsd   [rsp+598h+var_478], xmm1
0x18000c6c5  mov     rcx, [rsp+598h+ppObject]
0x18000c6ca  mov     rax, [rcx]
0x18000c6cd  lea     r8, [rsp+598h+var_488]
0x18000c6d5  lea     rdx, aSamaccountname; "samAccountName"
0x18000c6dc  mov     rax, [rax+80h]
0x18000c6e3  call    cs:__guard_dispatch_icall_fptr
0x18000c6e9  mov     edi, eax
0x18000c6eb  mov     [rsp+598h+var_558], eax
0x18000c6ef  mov     rcx, [rsp+598h+ppObject]
0x18000c6f4  test    eax, eax
0x18000c6f6  mov     rax, [rcx]
0x18000c6f9  jns     short loc_18000C744
0x18000c6fb  mov     rax, [rax+10h]
0x18000c6ff  call    cs:__guard_dispatch_icall_fptr
0x18000c705  mov     esi, ebx
0x18000c707  mov     [rsp+598h+var_554], ebx
0x18000c70b  mov     r14, [rsp+598h+DomainName]
0x18000c710  mov     r15, [rsp+598h+var_548]
0x18000c715  lea     rax, [rsp+598h+var_460]
0x18000c71d  mov     rcx, [rsp+598h+Block]; void *
0x18000c725  cmp     rcx, rax
0x18000c728  jz      loc_18000C9F5
0x18000c72e  cmp     cs:dword_1802B0018, ebx
0x18000c734  jz      loc_18000C9EE
0x18000c73a  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18000c73f  jmp     loc_18000C9F5
0x18000c744  mov     rax, [rax+70h]
0x18000c748  call    cs:__guard_dispatch_icall_fptr
0x18000c74e  mov     edi, eax
0x18000c750  mov     [rsp+598h+var_558], eax
0x18000c754  mov     rcx, [rsp+598h+ppObject]
0x18000c759  test    eax, eax
0x18000c75b  mov     rax, [rcx]
0x18000c75e  jns     short loc_18000C7A4
0x18000c760  mov     rax, [rax+10h]
0x18000c764  call    cs:__guard_dispatch_icall_fptr
0x18000c76a  test    r14, r14
0x18000c76d  jz      short loc_18000C77A
0x18000c76f  mov     rdx, r12; struct IADsContainer *
0x18000c772  mov     rcx, r14; lpCriticalSection
0x18000c775  call    ?ReleaseADObject@CADObjectsPool@@QEAAXPEAUIADsContainer@@@Z; CADObjectsPool::ReleaseADObject(IADsContainer *)
0x18000c77a  test    r15d, r15d
0x18000c77d  jnz     loc_18000C9AF
0x18000c783  cmp     edi, 80070005h
0x18000c789  jnz     loc_18000C705
0x18000c78f  mov     edx, 6FB700Dh
0x18000c794  mov     ecx, 0D1Fh
0x18000c799  call    cs:ULSTemplate_
0x18000c79f  jmp     loc_18000C705
0x18000c7a4  lea     rdx, [rsp+598h+lpszPathName]
0x18000c7ac  mov     rax, [rax+50h]
0x18000c7b0  call    cs:__guard_dispatch_icall_fptr
0x18000c7b6  mov     edi, eax
0x18000c7b8  mov     [rsp+598h+var_558], eax
0x18000c7bc  mov     rcx, [rsp+598h+ppObject]
0x18000c7c1  mov     rax, [rcx]
0x18000c7c4  mov     rax, [rax+10h]
0x18000c7c8  call    cs:__guard_dispatch_icall_fptr
0x18000c7ce  test    edi, edi
0x18000c7d0  js      loc_18000C963
0x18000c7d6  mov     rcx, [rsp+598h+lpszPathName]; lpszPathName
0x18000c7de  test    rcx, rcx
0x18000c7e1  jz      loc_18000C963
0x18000c7e7  mov     [rsp+598h+ppObject], rbx
0x18000c7ec  lea     r8, [rsp+598h+ppObject]; ppObject
0x18000c7f1  lea     rdx, stru_180176A90; riid
0x18000c7f8  call    cs:ADsGetObject
0x18000c7fe  mov     edi, eax
0x18000c800  mov     [rsp+598h+var_558], eax
0x18000c804  mov     rcx, [rsp+598h+lpszPathName]; bstrString
0x18000c80c  call    cs:SysFreeString
0x18000c812  test    edi, edi
0x18000c814  js      loc_18000C963
0x18000c81a  mov     rcx, [rsp+598h+ppObject]
0x18000c81f  test    rcx, rcx
0x18000c822  jz      loc_18000C963
0x18000c828  mov     rax, [rcx]
0x18000c82b  xor     edx, edx
0x18000c82d  mov     rax, [rax+228h]
0x18000c834  call    cs:__guard_dispatch_icall_fptr
0x18000c83a  mov     edi, eax
0x18000c83c  mov     [rsp+598h+var_558], eax
0x18000c840  test    eax, eax
0x18000c842  jns     short loc_18000C85B
0x18000c844  mov     rcx, [rsp+598h+ppObject]
0x18000c849  mov     rax, [rcx]
0x18000c84c  mov     rax, [rax+10h]
0x18000c850  call    cs:__guard_dispatch_icall_fptr
0x18000c856  jmp     loc_18000C973
0x18000c85b  mov     rax, [rsp+598h+psz]
0x18000c860  test    rax, rax
0x18000c863  jz      short loc_18000C89F
0x18000c865  mov     rcx, rax; psz
0x18000c868  call    cs:SysAllocString
0x18000c86e  mov     rdi, rax
0x18000c871  mov     [rsp+598h+var_490], rax
0x18000c879  test    rax, rax
0x18000c87c  jz      short loc_18000C89F
0x18000c87e  mov     rcx, [rsp+598h+ppObject]
0x18000c883  mov     rdx, [rcx]
0x18000c886  mov     rax, [rdx+2F8h]
0x18000c88d  mov     rdx, rdi
0x18000c890  call    cs:__guard_dispatch_icall_fptr
0x18000c896  mov     rcx, rdi; bstrString
0x18000c899  call    cs:SysFreeString
0x18000c89f  mov     rcx, [rsp+598h+ppObject]
0x18000c8a4  mov     rax, [rcx]
0x18000c8a7  mov     rax, [rax+70h]
0x18000c8ab  call    cs:__guard_dispatch_icall_fptr
0x18000c8b1  mov     edi, eax
0x18000c8b3  mov     [rsp+598h+var_558], eax
0x18000c8b7  mov     rcx, [rsp+598h+ppObject]
0x18000c8bc  test    eax, eax
0x18000c8be  jns     short loc_18000C8E6
0x18000c8c0  mov     rax, [rcx]
0x18000c8c3  mov     rax, [rax+10h]
0x18000c8c7  call    cs:__guard_dispatch_icall_fptr
0x18000c8cd  test    r14, r14
0x18000c8d0  jz      loc_18000C979
0x18000c8d6  mov     rdx, r12; struct IADsContainer *
0x18000c8d9  mov     rcx, r14; lpCriticalSection
0x18000c8dc  call    ?ReleaseADObject@CADObjectsPool@@QEAAXPEAUIADsContainer@@@Z; CADObjectsPool::ReleaseADObject(IADsContainer *)
0x18000c8e1  jmp     loc_18000C979
0x18000c8e6  mov     rdx, [rsp+598h+var_508]
0x18000c8ee  call    sub_18000BEA8
0x18000c8f3  mov     edi, eax
  ... truncated ...
```
