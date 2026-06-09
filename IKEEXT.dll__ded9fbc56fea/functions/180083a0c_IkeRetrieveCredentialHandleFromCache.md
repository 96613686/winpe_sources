# IkeRetrieveCredentialHandleFromCache

- ea: `0x180083a0c`
- end: `0x180083fc9`
- name: `IkeRetrieveCredentialHandleFromCache`
- size: `1469`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18002f9e4`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x18004d594`
- `0x18004d60c`
- `0x180050850`
- `0x18005bc40`
- `0x18007dde4`
- `0x18008081c`
- `0x180080d3c`
- `0x180083a0c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180083d25`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180083d25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180083c1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180083c1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180083a71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180083a71`

## string_xrefs

- `0x180083af8`: `Looking for credentials in cache`
- `0x180083a3e`: `IkeRetrieveCredentialHandleFromCache`
- `0x180083c26`: `IkeRetrieveCredentialHandleFromCache`
- `0x180083c32`: `IkeRetrieveCredentialHandleFromCache`
- `0x180083ce2`: `Found credentials in the cache, logging cache entry`
- `0x180083be5`: `Did not find credentials in the cache`
- `0x180083ea5`: `Cached entry credentials are expired, removing`
- `0x180083dcf`: `Cached entry is expired, removing`
- `0x180083f2b`: `Moving cached entry to front`

## pseudocode

```c
__int64 __fastcall IkeRetrieveCredentialHandleFromCache(unsigned int a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  __int64 v8; // r12
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  int TlsMmLuid; // eax
  __int64 v20; // rcx
  __int64 v21; // rax
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 CredCacheEntry; // r15
  LPCRITICAL_SECTION **v29; // rsi
  __int64 v30; // rdi
  __int64 v31; // rbx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rax
  int v39; // r8d
  __int64 v41; // rdi
  __int64 v42; // rbx
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // r9
  int v47; // eax
  __int64 v48; // rcx
  __int64 v49; // rax
  int v50; // r8d
  int v51; // r9d
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 v55; // rcx
  __int64 v56; // rdi
  __int64 v57; // rbx
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // r9
  int v62; // eax
  __int64 v63; // rcx
  __int64 v64; // rax
  int v65; // r8d
  int v66; // r9d
  char *v67; // rdx
  const char *v68; // rcx
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 v73; // rdi
  __int64 v74; // rbx
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r8
  __int64 v78; // r9
  int v79; // eax
  __int64 v80; // rcx
  __int64 v81; // rax
  __int64 v82; // rdi
  __int64 v83; // rbx
  __int64 v84; // rdx
  __int64 v85; // rcx
  __int64 v86; // r8
  __int64 v87; // r9
  int v88; // eax
  __int64 v89; // rcx
  __int64 v90; // rax
  int v91; // r8d
  int v92; // r9d
  LPCRITICAL_SECTION *v93; // rax
  LPCRITICAL_SECTION ***v94; // rcx
  HANDLE *p_OwningThread; // rax
  LPCRITICAL_SECTION *OwningThread; // rcx
  LPCRITICAL_SECTION **v97; // [rsp+30h] [rbp-69h] BYREF
  __int64 v98; // [rsp+38h] [rbp-61h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v100[32]; // [rsp+50h] [rbp-49h] BYREF
  __int64 *v101; // [rsp+70h] [rbp-29h]
  __int64 v102; // [rsp+78h] [rbp-21h]
  _BYTE v103[16]; // [rsp+80h] [rbp-19h] BYREF
  const char *v104; // [rsp+90h] [rbp-9h]
  __int64 v105; // [rsp+98h] [rbp-1h]

  v97 = 0;
  SystemTimeAsFileTime = 0;
  TraceLogHelper("IkeRetrieveCredentialHandleFromCache", 1);
  *a4 = 0;
  v8 = *(_QWORD *)(*(_QWORD *)(a3 + 104) + 56LL);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)gIkeExtGlobals + 3488));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v10);
    TlsMmLuid = IkeGetTlsMmLuid(v16, v15, v17, v18);
    WPP_SF_iS(v13, 82, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, TlsMmLuid, TlsPeerAddr);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v98 = IkeGetTlsMmLuid(v10, v9, v11, v12);
    v101 = &v98;
    v102 = 8;
    v21 = IkeGetTlsPeerAddr(v20);
    tlgCreate1Sz_wchar_t(v103, v21);
    v105 = 33;
    v104 = "Looking for credentials in cache";
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)byte_180154C59,
      v22,
      v23,
      5,
      (__int64)v100);
  }
  CredCacheEntry = IkeGetCredCacheEntry(a1, *(unsigned int *)(a2 + 72), v8, &v97);
  if ( !CredCacheEntry )
  {
    v29 = v97;
    if ( !v97 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v30 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v31 = IkeGetTlsPeerAddr(v25);
        v36 = IkeGetTlsMmLuid(v33, v32, v34, v35);
        WPP_SF_iS(v30, 83, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v36, v31);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v98 = IkeGetTlsMmLuid(v25, v24, v26, v27);
        v101 = &v98;
        v102 = 8;
        v38 = IkeGetTlsPeerAddr(v37);
        tlgCreate1Sz_wchar_t(v103, v38);
        v105 = 38;
        v104 = "Did not find credentials in the cache";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)byte_180154C1B,
          v39,
          (unsigned int)"Did not find credentials in the cache",
          5,
          (__int64)v100);
      }
      goto LABEL_15;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v41 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v42 = IkeGetTlsPeerAddr(v25);
      v47 = IkeGetTlsMmLuid(v44, v43, v45, v46);
      WPP_SF_iS(v41, 84, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v47, v42);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v98 = IkeGetTlsMmLuid(v25, v24, v26, v27);
      v101 = &v98;
      v102 = 8;
      v49 = IkeGetTlsPeerAddr(v48);
      tlgCreate1Sz_wchar_t(v103, v49);
      v105 = 52;
      v104 = "Found credentials in the cache, logging cache entry";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)byte_180154B61,
        v50,
        v51,
        5,
        (__int64)v100);
    }
    IkeLogCredCacheEntry(v29);
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v55 = 72000000000LL;
    if ( *(_QWORD *)&SystemTimeAsFileTime > (unsigned __int64)(v29[7] + 9000000000LL) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v56 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v57 = IkeGetTlsPeerAddr(72000000000LL);
        v62 = IkeGetTlsMmLuid(v59, v58, v60, v61);
        WPP_SF_iS(v56, 85, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v62, v57);
      }
      if ( (unsigned int)dword_180173278 <= 4 )
        goto LABEL_30;
      v98 = IkeGetTlsMmLuid(v55, v52, v53, v54);
      v101 = &v98;
      v102 = 8;
      v64 = IkeGetTlsPeerAddr(v63);
      tlgCreate1Sz_wchar_t(v103, v64);
      v67 = byte_180154B23;
      v105 = 34;
      v68 = "Cached entry is expired, removing";
LABEL_29:
      v104 = v68;
      tlgWriteTransfer_EtwEventWriteTransfer((unsigned int)&dword_180173278, (_DWORD)v67, v65, v66, 5, (__int64)v100);
LABEL_30:
      IkeRemoveCredCacheEntry(v29);
      IkeDerefCacheEntry(v29);
      goto LABEL_15;
    }
    if ( (unsigned int)IkeIsCachedCredExpired(v29) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v73 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v74 = IkeGetTlsPeerAddr(v70);
        v79 = IkeGetTlsMmLuid(v76, v75, v77, v78);
        WPP_SF_iS(v73, 86, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v79, v74);
      }
      if ( (unsigned int)dword_180173278 <= 4 )
        goto LABEL_30;
      v98 = IkeGetTlsMmLuid(v70, v69, v71, v72);
      v101 = &v98;
      v102 = 8;
      v81 = IkeGetTlsPeerAddr(v80);
      tlgCreate1Sz_wchar_t(v103, v81);
      v67 = byte_180154BDD;
      v105 = 47;
      v68 = "Cached entry credentials are expired, removing";
      goto LABEL_29;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v82 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v83 = IkeGetTlsPeerAddr(v70);
      v88 = IkeGetTlsMmLuid(v85, v84, v86, v87);
      WPP_SF_iS(v82, 87, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v88, v83);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v98 = IkeGetTlsMmLuid(v70, v69, v71, v72);
      v101 = &v98;
      v102 = 8;
      v90 = IkeGetTlsPeerAddr(v89);
      tlgCreate1Sz_wchar_t(v103, v90);
      v105 = 29;
      v104 = "Moving cached entry to front";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_180154B9F,
        v91,
        v92,
        5,
        (__int64)v100);
    }
    v93 = *v29;
    if ( (*v29)[1] != (LPCRITICAL_SECTION)v29
      || (v94 = (LPCRITICAL_SECTION ***)v29[1], *v94 != v29)
      || (*v94 = (LPCRITICAL_SECTION **)v93,
          v93[1] = (LPCRITICAL_SECTION)v94,
          p_OwningThread = &gIkeExtGlobals[88].OwningThread,
          OwningThread = (LPCRITICAL_SECTION *)gIkeExtGlobals[88].OwningThread,
          OwningThread[1] != (LPCRITICAL_SECTION)&gIkeExtGlobals[88].OwningThread) )
    {
      __fastfail(3u);
    }
    *v29 = OwningThread;
    v29[1] = (LPCRITICAL_SECTION *)p_OwningThread;
    OwningThread[1] = (LPCRITICAL_SECTION)v29;
    *p_OwningThread = v29;
    *(_OWORD *)(a3 + 8) = *(_OWORD *)(v29 + 9);
    *(_QWORD *)(a3 + 48) = v29[11];
    *(_QWORD *)(a3 + 112) = v29;
    *a4 = 1;
  }
LABEL_15:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)gIkeExtGlobals + 3488));
  TraceLogHelper("IkeRetrieveCredentialHandleFromCache", 0);
  return IkeReturnError(CredCacheEntry, "IkeRetrieveCredentialHandleFromCache");
}

```

## disassembly

```asm
0x180083a0c  push    rbp
0x180083a0e  push    rbx
0x180083a0f  push    rsi
0x180083a10  push    rdi
0x180083a11  push    r12
0x180083a13  push    r13
0x180083a15  push    r14
0x180083a17  push    r15
0x180083a19  lea     rbp, [rsp-1Fh]
0x180083a1e  sub     rsp, 0B8h
0x180083a25  mov     rax, cs:__security_cookie
0x180083a2c  xor     rax, rsp
0x180083a2f  mov     [rbp+57h+var_50], rax
0x180083a33  xor     ebx, ebx
0x180083a35  mov     r15, rdx
0x180083a38  mov     esi, ecx
0x180083a3a  mov     [rbp+57h+var_C0], rbx
0x180083a3e  lea     rcx, aIkeretrievecre; "IkeRetrieveCredentialHandleFromCache"
0x180083a45  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180083a49  mov     r13, r9
0x180083a4c  mov     r14, r8
0x180083a4f  lea     edx, [rbx+1]
0x180083a52  call    TraceLogHelper
0x180083a57  mov     [r13+0], ebx
0x180083a5b  mov     rax, [r14+68h]
0x180083a5f  mov     rcx, cs:gIkeExtGlobals
0x180083a66  add     rcx, 0DA0h; lpCriticalSection
0x180083a6d  mov     r12, [rax+38h]
0x180083a71  call    cs:__imp_EnterCriticalSection
0x180083a77  mov     rdi, cs:WPP_GLOBAL_Control
0x180083a7e  lea     rax, WPP_GLOBAL_Control
0x180083a85  cmp     rdi, rax
0x180083a88  jz      short loc_180083AC3
0x180083a8a  cmp     byte ptr [rdi+19h], 4
0x180083a8e  jb      short loc_180083AC3
0x180083a90  test    byte ptr [rdi+1Ch], 10h
0x180083a94  jz      short loc_180083AC3
0x180083a96  mov     rdi, [rdi+10h]
0x180083a9a  call    IkeGetTlsPeerAddr
0x180083a9f  mov     rbx, rax
0x180083aa2  call    IkeGetTlsMmLuid
0x180083aa7  mov     r9, rax
0x180083aaa  mov     [rsp+0F0h+var_D0], rbx
0x180083aaf  mov     edx, 52h ; 'R'
0x180083ab4  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180083abb  mov     rcx, rdi
0x180083abe  call    WPP_SF_iS
0x180083ac3  mov     eax, cs:dword_180173278
0x180083ac9  cmp     eax, 4
0x180083acc  jbe     short loc_180083B2F
0x180083ace  call    IkeGetTlsMmLuid
0x180083ad3  mov     [rbp+57h+var_B8], rax
0x180083ad7  lea     rax, [rbp+57h+var_B8]
0x180083adb  mov     [rbp+57h+var_80], rax
0x180083adf  mov     [rbp+57h+var_78], 8
0x180083ae7  call    IkeGetTlsPeerAddr
0x180083aec  mov     rdx, rax
0x180083aef  lea     rcx, [rbp+57h+var_70]
0x180083af3  call    _tlgCreate1Sz_wchar_t
0x180083af8  lea     rcx, aLookingForCred; "Looking for credentials in cache"
0x180083aff  mov     [rbp+57h+var_58], 21h ; '!'
0x180083b07  lea     rax, [rbp+57h+var_A0]
0x180083b0b  mov     [rbp+57h+var_60], rcx
0x180083b0f  mov     [rsp+0F0h+var_C8], rax
0x180083b14  lea     rcx, dword_180173278
0x180083b1b  lea     rdx, byte_180154C59
0x180083b22  mov     dword ptr [rsp+0F0h+var_D0], 5
0x180083b2a  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180083b2f  mov     edx, [r15+48h]
0x180083b33  lea     r9, [rbp+57h+var_C0]
0x180083b37  mov     r8, r12
0x180083b3a  mov     ecx, esi
0x180083b3c  call    IkeGetCredCacheEntry
0x180083b41  mov     r15, rax
0x180083b44  test    rax, rax
0x180083b47  jnz     loc_180083C10
0x180083b4d  mov     rsi, [rbp+57h+var_C0]
0x180083b51  test    rsi, rsi
0x180083b54  jnz     loc_180083C61
0x180083b5a  mov     rdi, cs:WPP_GLOBAL_Control
0x180083b61  lea     rax, WPP_GLOBAL_Control
0x180083b68  cmp     rdi, rax
0x180083b6b  jz      short loc_180083BA4
0x180083b6d  cmp     byte ptr [rdi+19h], 4
0x180083b71  jb      short loc_180083BA4
0x180083b73  test    byte ptr [rdi+1Ch], 10h
0x180083b77  jz      short loc_180083BA4
0x180083b79  mov     rdi, [rdi+10h]
0x180083b7d  call    IkeGetTlsPeerAddr
0x180083b82  mov     rbx, rax
0x180083b85  call    IkeGetTlsMmLuid
0x180083b8a  mov     r9, rax
0x180083b8d  mov     [rsp+0F0h+var_D0], rbx
0x180083b92  lea     edx, [rsi+53h]
0x180083b95  mov     rcx, rdi
0x180083b98  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180083b9f  call    WPP_SF_iS
0x180083ba4  mov     eax, cs:dword_180173278
0x180083baa  cmp     eax, 4
0x180083bad  jbe     short loc_180083C10
0x180083baf  call    IkeGetTlsMmLuid
0x180083bb4  mov     [rbp+57h+var_B8], rax
0x180083bb8  lea     rax, [rbp+57h+var_B8]
0x180083bbc  mov     [rbp+57h+var_80], rax
0x180083bc0  mov     [rbp+57h+var_78], 8
0x180083bc8  call    IkeGetTlsPeerAddr
0x180083bcd  mov     rdx, rax
0x180083bd0  lea     rcx, [rbp+57h+var_70]
0x180083bd4  call    _tlgCreate1Sz_wchar_t
0x180083bd9  lea     rax, [rbp+57h+var_A0]
0x180083bdd  mov     [rbp+57h+var_58], 26h ; '&'
0x180083be5  lea     r9, aDidNotFindCred; "Did not find credentials in the cache"
0x180083bec  mov     [rsp+0F0h+var_C8], rax
0x180083bf1  lea     rdx, byte_180154C1B
0x180083bf8  mov     dword ptr [rsp+0F0h+var_D0], 5
0x180083c00  lea     rcx, dword_180173278
0x180083c07  mov     [rbp+57h+var_60], r9
0x180083c0b  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180083c10  mov     rcx, cs:gIkeExtGlobals
0x180083c17  add     rcx, 0DA0h; lpCriticalSection
0x180083c1e  call    cs:__imp_LeaveCriticalSection
0x180083c24  xor     edx, edx
0x180083c26  lea     rcx, aIkeretrievecre; "IkeRetrieveCredentialHandleFromCache"
0x180083c2d  call    TraceLogHelper
0x180083c32  lea     rdx, aIkeretrievecre; "IkeRetrieveCredentialHandleFromCache"
0x180083c39  mov     rcx, r15
0x180083c3c  call    IkeReturnError
0x180083c41  mov     rcx, [rbp+57h+var_50]
0x180083c45  xor     rcx, rsp; StackCookie
0x180083c48  call    __security_check_cookie
0x180083c4d  add     rsp, 0B8h
0x180083c54  pop     r15
0x180083c56  pop     r14
0x180083c58  pop     r13
0x180083c5a  pop     r12
0x180083c5c  pop     rdi
0x180083c5d  pop     rsi
0x180083c5e  pop     rbx
0x180083c5f  pop     rbp
0x180083c60  retn
0x180083c61  mov     rdi, cs:WPP_GLOBAL_Control
0x180083c68  lea     r12, WPP_GLOBAL_Control
0x180083c6f  cmp     rdi, r12
0x180083c72  jz      short loc_180083CAD
0x180083c74  cmp     byte ptr [rdi+19h], 4
0x180083c78  jb      short loc_180083CAD
0x180083c7a  test    byte ptr [rdi+1Ch], 10h
0x180083c7e  jz      short loc_180083CAD
0x180083c80  mov     rdi, [rdi+10h]
0x180083c84  call    IkeGetTlsPeerAddr
0x180083c89  mov     rbx, rax
0x180083c8c  call    IkeGetTlsMmLuid
0x180083c91  mov     r9, rax
0x180083c94  mov     [rsp+0F0h+var_D0], rbx
0x180083c99  mov     edx, 54h ; 'T'
0x180083c9e  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180083ca5  mov     rcx, rdi
0x180083ca8  call    WPP_SF_iS
0x180083cad  mov     eax, cs:dword_180173278
0x180083cb3  cmp     eax, 4
0x180083cb6  jbe     short loc_180083D19
0x180083cb8  call    IkeGetTlsMmLuid
0x180083cbd  mov     [rbp+57h+var_B8], rax
0x180083cc1  lea     rax, [rbp+57h+var_B8]
0x180083cc5  mov     [rbp+57h+var_80], rax
0x180083cc9  mov     [rbp+57h+var_78], 8
0x180083cd1  call    IkeGetTlsPeerAddr
0x180083cd6  mov     rdx, rax
0x180083cd9  lea     rcx, [rbp+57h+var_70]
0x180083cdd  call    _tlgCreate1Sz_wchar_t
0x180083ce2  lea     rcx, aFoundCredentia; "Found credentials in the cache, logging"...
0x180083ce9  mov     [rbp+57h+var_58], 34h ; '4'
0x180083cf1  lea     rax, [rbp+57h+var_A0]
0x180083cf5  mov     [rbp+57h+var_60], rcx
0x180083cf9  mov     [rsp+0F0h+var_C8], rax
0x180083cfe  lea     rcx, dword_180173278
0x180083d05  lea     rdx, byte_180154B61
0x180083d0c  mov     dword ptr [rsp+0F0h+var_D0], 5
0x180083d14  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180083d19  mov     rcx, rsi
0x180083d1c  call    IkeLogCredCacheEntry
0x180083d21  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180083d25  call    cs:__imp_GetSystemTimeAsFileTime
0x180083d2b  mov     rax, [rsi+38h]
0x180083d2f  mov     rcx, 10C388D000h
0x180083d39  add     rax, rcx
0x180083d3c  cmp     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180083d40  jbe     loc_180083E0C
0x180083d46  mov     rdi, cs:WPP_GLOBAL_Control
0x180083d4d  cmp     rdi, r12
0x180083d50  jz      short loc_180083D8B
0x180083d52  cmp     byte ptr [rdi+19h], 4
0x180083d56  jb      short loc_180083D8B
0x180083d58  test    byte ptr [rdi+1Ch], 10h
0x180083d5c  jz      short loc_180083D8B
0x180083d5e  mov     rdi, [rdi+10h]
0x180083d62  call    IkeGetTlsPeerAddr
0x180083d67  mov     rbx, rax
0x180083d6a  call    IkeGetTlsMmLuid
0x180083d6f  mov     r9, rax
0x180083d72  mov     [rsp+0F0h+var_D0], rbx
0x180083d77  mov     edx, 55h ; 'U'
0x180083d7c  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180083d83  mov     rcx, rdi
0x180083d86  call    WPP_SF_iS
0x180083d8b  mov     eax, cs:dword_180173278
0x180083d91  cmp     eax, 4
0x180083d94  jbe     short loc_180083DF7
0x180083d96  call    IkeGetTlsMmLuid
0x180083d9b  mov     [rbp+57h+var_B8], rax
0x180083d9f  lea     rax, [rbp+57h+var_B8]
0x180083da3  mov     [rbp+57h+var_80], rax
0x180083da7  mov     [rbp+57h+var_78], 8
0x180083daf  call    IkeGetTlsPeerAddr
0x180083db4  mov     rdx, rax
0x180083db7  lea     rcx, [rbp+57h+var_70]
0x180083dbb  call    _tlgCreate1Sz_wchar_t
0x180083dc0  lea     rdx, byte_180154B23
0x180083dc7  mov     [rbp+57h+var_58], 22h ; '"'
0x180083dcf  lea     rcx, aCachedEntryIsE; "Cached entry is expired, removing"
0x180083dd6  lea     rax, [rbp+57h+var_A0]
0x180083dda  mov     [rbp+57h+var_60], rcx
0x180083dde  mov     [rsp+0F0h+var_C8], rax
0x180083de3  lea     rcx, dword_180173278
0x180083dea  mov     dword ptr [rsp+0F0h+var_D0], 5
0x180083df2  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180083df7  mov     rcx, rsi
0x180083dfa  call    IkeRemoveCredCacheEntry
0x180083dff  mov     rcx, rsi
0x180083e02  call    IkeDerefCacheEntry
0x180083e07  jmp     loc_180083C10
0x180083e0c  mov     rcx, rsi
0x180083e0f  call    IkeIsCachedCredExpired
0x180083e14  test    eax, eax
0x180083e16  jz      loc_180083EB1
0x180083e1c  mov     rdi, cs:WPP_GLOBAL_Control
0x180083e23  cmp     rdi, r12
0x180083e26  jz      short loc_180083E61
0x180083e28  cmp     byte ptr [rdi+19h], 4
0x180083e2c  jb      short loc_180083E61
0x180083e2e  test    byte ptr [rdi+1Ch], 10h
0x180083e32  jz      short loc_180083E61
0x180083e34  mov     rdi, [rdi+10h]
0x180083e38  call    IkeGetTlsPeerAddr
0x180083e3d  mov     rbx, rax
0x180083e40  call    IkeGetTlsMmLuid
0x180083e45  mov     r9, rax
0x180083e48  mov     [rsp+0F0h+var_D0], rbx
0x180083e4d  mov     edx, 56h ; 'V'
0x180083e52  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180083e59  mov     rcx, rdi
0x180083e5c  call    WPP_SF_iS
0x180083e61  mov     eax, cs:dword_180173278
0x180083e67  cmp     eax, 4
0x180083e6a  jbe     short loc_180083DF7
0x180083e6c  call    IkeGetTlsMmLuid
0x180083e71  mov     [rbp+57h+var_B8], rax
0x180083e75  lea     rax, [rbp+57h+var_B8]
0x180083e79  mov     [rbp+57h+var_80], rax
0x180083e7d  mov     [rbp+57h+var_78], 8
0x180083e85  call    IkeGetTlsPeerAddr
0x180083e8a  mov     rdx, rax
0x180083e8d  lea     rcx, [rbp+57h+var_70]
0x180083e91  call    _tlgCreate1Sz_wchar_t
0x180083e96  lea     rdx, byte_180154BDD
0x180083e9d  mov     [rbp+57h+var_58], 2Fh ; '/'
0x180083ea5  lea     rcx, aCachedEntryCre; "Cached entry credentials are expired, r"...
0x180083eac  jmp     loc_180083DD6
0x180083eb1  mov     rdi, cs:WPP_GLOBAL_Control
0x180083eb8  cmp     rdi, r12
0x180083ebb  jz      short loc_180083EF6
0x180083ebd  cmp     byte ptr [rdi+19h], 4
0x180083ec1  jb      short loc_180083EF6
0x180083ec3  test    byte ptr [rdi+1Ch], 10h
0x180083ec7  jz      short loc_180083EF6
0x180083ec9  mov     rdi, [rdi+10h]
0x180083ecd  call    IkeGetTlsPeerAddr
0x180083ed2  mov     rbx, rax
0x180083ed5  call    IkeGetTlsMmLuid
0x180083eda  mov     r9, rax
0x180083edd  mov     [rsp+0F0h+var_D0], rbx
0x180083ee2  mov     edx, 57h ; 'W'
0x180083ee7  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180083eee  mov     rcx, rdi
0x180083ef1  call    WPP_SF_iS
0x180083ef6  mov     eax, cs:dword_180173278
0x180083efc  cmp     eax, 4
0x180083eff  jbe     short loc_180083F62
0x180083f01  call    IkeGetTlsMmLuid
0x180083f06  mov     [rbp+57h+var_B8], rax
0x180083f0a  lea     rax, [rbp+57h+var_B8]
0x180083f0e  mov     [rbp+57h+var_80], rax
0x180083f12  mov     [rbp+57h+var_78], 8
0x180083f1a  call    IkeGetTlsPeerAddr
0x180083f1f  mov     rdx, rax
0x180083f22  lea     rcx, [rbp+57h+var_70]
0x180083f26  call    _tlgCreate1Sz_wchar_t
0x180083f2b  lea     rcx, aMovingCachedEn; "Moving cached entry to front"
0x180083f32  mov     [rbp+57h+var_58], 1Dh
0x180083f3a  lea     rax, [rbp+57h+var_A0]
  ... truncated ...
```
