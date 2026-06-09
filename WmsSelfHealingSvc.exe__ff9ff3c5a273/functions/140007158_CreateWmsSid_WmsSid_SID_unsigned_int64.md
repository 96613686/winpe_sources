# CreateWmsSid(WmsSid *,_SID *,unsigned __int64)

- ea: `0x140007158`
- end: `0x1400076d8`
- name: `?CreateWmsSid@@YAJPEAUWmsSid@@PEAU_SID@@_K@Z`
- size: `1408`
- prototype: `__int64 __fastcall(struct WmsSid *, struct _SID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140006a88`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x140007158`
- `0x140007e64`
- `0x14000a61c`
- `0x14000ae32`
- `0x14000ae60`

## import_xrefs

- `ADVAPI32!CopySid` at `0x14000736b`
- `ADVAPI32!CopySid` at `0x14000741b`
- `ADVAPI32!CopySid` at `0x14000736b`
- `ADVAPI32!CopySid` at `0x14000741b`
- `ADVAPI32!CreateWellKnownSid` at `0x1400075ea`
- `ADVAPI32!CreateWellKnownSid` at `0x1400075ea`
- `ADVAPI32!OpenProcessToken` at `0x1400071ef`
- `ADVAPI32!OpenProcessToken` at `0x1400071ef`
- `ADVAPI32!LookupAccountNameW` at `0x140007558`
- `ADVAPI32!LookupAccountNameW` at `0x140007558`
- `KERNEL32!LocalFree` at `0x14000769d`
- `KERNEL32!LocalFree` at `0x1400076a6`
- `KERNEL32!LocalFree` at `0x14000769d`
- `KERNEL32!LocalFree` at `0x1400076a6`
- `KERNEL32!IsDebuggerPresent` at `0x140007254`
- `KERNEL32!IsDebuggerPresent` at `0x14000730d`
- `KERNEL32!IsDebuggerPresent` at `0x1400073d0`
- `KERNEL32!IsDebuggerPresent` at `0x140007480`
- `KERNEL32!IsDebuggerPresent` at `0x1400074ef`
- `KERNEL32!IsDebuggerPresent` at `0x1400075bd`
- `KERNEL32!IsDebuggerPresent` at `0x14000764f`
- `KERNEL32!IsDebuggerPresent` at `0x140007254`
- `KERNEL32!IsDebuggerPresent` at `0x14000730d`
- `KERNEL32!IsDebuggerPresent` at `0x1400073d0`
- `KERNEL32!IsDebuggerPresent` at `0x140007480`
- `KERNEL32!IsDebuggerPresent` at `0x1400074ef`
- `KERNEL32!IsDebuggerPresent` at `0x1400075bd`
- `KERNEL32!IsDebuggerPresent` at `0x14000764f`
- `KERNEL32!GetLastError` at `0x1400071fd`
- `KERNEL32!GetLastError` at `0x140007379`
- `KERNEL32!GetLastError` at `0x140007429`
- `KERNEL32!GetLastError` at `0x140007566`
- `KERNEL32!GetLastError` at `0x1400075f8`
- `KERNEL32!GetLastError` at `0x1400071fd`
- `KERNEL32!GetLastError` at `0x140007379`
- `KERNEL32!GetLastError` at `0x140007429`
- `KERNEL32!GetLastError` at `0x140007566`
- `KERNEL32!GetLastError` at `0x1400075f8`
- `KERNEL32!CloseHandle` at `0x140007694`
- `KERNEL32!CloseHandle` at `0x140007694`
- `KERNEL32!GetCurrentProcess` at `0x1400071dc`
- `KERNEL32!GetCurrentProcess` at `0x1400071dc`

## string_xrefs

- `0x140007227`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400072f5`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400073a3`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140007453`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400074c7`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140007590`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140007622`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140007220`: `CreateWmsSid`
- `0x1400072e3`: `CreateWmsSid`
- `0x14000739c`: `CreateWmsSid`
- `0x14000744c`: `CreateWmsSid`
- `0x1400074ba`: `CreateWmsSid`
- `0x140007589`: `CreateWmsSid`
- `0x14000761b`: `CreateWmsSid`

## pseudocode

```c
__int64 __fastcall CreateWmsSid(struct WmsSid *a1, struct _SID *a2)
{
  unsigned __int64 v4; // r8
  WELL_KNOWN_SID_TYPE v5; // eax
  void *v6; // r9
  void *v7; // r12
  void *v8; // r13
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // r8
  int v14; // eax
  signed int v15; // eax
  int TokenInformationWithLocalAlloc; // eax
  signed int v17; // eax
  int LocalGroupSid; // eax
  signed int v19; // eax
  signed int v20; // eax
  const unsigned __int16 *cchReferencedDomainName; // [rsp+28h] [rbp-D8h]
  PSID_NAME_USE peUse; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *peUsea; // [rsp+30h] [rbp-D0h]
  int v25; // [rsp+38h] [rbp-C8h]
  __int64 cbSid; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  void *v28; // [rsp+50h] [rbp-B0h] BYREF
  void *v29; // [rsp+58h] [rbp-A8h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(ReferencedDomainName, 0, 0x208u);
  v5 = *(_DWORD *)a1;
  v6 = 0;
  v7 = 0;
  LODWORD(v27) = 260;
  v8 = 0;
  TokenHandle = 0;
  v29 = 0;
  v28 = 0;
  cbSid = 68;
  if ( (unsigned int)(v5 - 3) <= 1 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0x34Eu,
        L"CreateWmsSid",
        L"CBRAEx",
        L"fSuccess",
        v11);
      if ( IsDebuggerPresent() )
      {
        v12 = 846;
LABEL_9:
        v25 = v11;
        peUsea = L"fSuccess";
LABEL_10:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          v12,
          L"CreateWmsSid",
          L"CBRAEx",
          peUsea,
          v25,
          cbSid,
          v27);
        goto LABEL_62;
      }
      v13 = 846;
      goto LABEL_60;
    }
    v6 = TokenHandle;
  }
  v11 = 0;
  switch ( *(_DWORD *)a1 )
  {
    case 0:
      if ( CreateWellKnownSid(*((WELL_KNOWN_SID_TYPE *)a1 + 1), 0, a2, (DWORD *)&cbSid) )
        goto LABEL_62;
      v20 = GetLastError();
      v11 = v20;
      if ( v20 > 0 )
        v11 = (unsigned __int16)v20 | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0x355u,
        L"CreateWmsSid",
        L"CBRAEx",
        L"fSuccess",
        v11);
      if ( IsDebuggerPresent() )
      {
        v12 = 853;
        goto LABEL_9;
      }
      v13 = 853;
      goto LABEL_60;
    case 1:
      if ( LookupAccountNameW(
             0,
             *((LPCWSTR *)a1 + 1),
             a2,
             (LPDWORD)&cbSid,
             ReferencedDomainName,
             (LPDWORD)&v27,
             (PSID_NAME_USE)&cbSid + 1) )
      {
        goto LABEL_62;
      }
      v19 = GetLastError();
      v11 = v19;
      if ( v19 > 0 )
        v11 = (unsigned __int16)v19 | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0x35Bu,
        L"CreateWmsSid",
        L"CBRAEx",
        L"fSuccess",
        v11);
      if ( IsDebuggerPresent() )
      {
        v12 = 859;
        goto LABEL_9;
      }
      v13 = 859;
      goto LABEL_60;
    case 2:
      LocalGroupSid = CUserManagement::s_GetLocalGroupSid(*((const unsigned __int16 **)a1 + 1), a2, v4);
      v11 = LocalGroupSid;
      if ( LocalGroupSid < 0 )
      {
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          0x360u,
          L"CreateWmsSid",
          L"CHRA",
          L"hr",
          LocalGroupSid);
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
            864,
            L"CreateWmsSid",
            L"CHRA",
            L"hr",
            v11,
            cbSid,
            v27);
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
            864,
            L"CreateWmsSid",
            L"CHRA",
            L"hr",
            v11);
      }
      goto LABEL_62;
    case 3:
      TokenInformationWithLocalAlloc = GetTokenInformationWithLocalAlloc(v6, TokenUser, &v29);
      v7 = v29;
      v11 = TokenInformationWithLocalAlloc;
      if ( TokenInformationWithLocalAlloc < 0 || CopySid(0x44u, a2, *(PSID *)v29) )
        goto LABEL_62;
      v17 = GetLastError();
      v11 = v17;
      if ( v17 > 0 )
        v11 = (unsigned __int16)v17 | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0x36Au,
        L"CreateWmsSid",
        L"CBRAEx",
        L"fSuccess",
        v11);
      if ( IsDebuggerPresent() )
      {
        v12 = 874;
        goto LABEL_9;
      }
      v13 = 874;
LABEL_60:
      LODWORD(peUse) = v11;
      cchReferencedDomainName = L"fSuccess";
      goto LABEL_61;
  }
  if ( *(_DWORD *)a1 != 4 )
  {
    v11 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x378u,
      L"CreateWmsSid",
      L"CBRAEx",
      L"0",
      -2147024809);
    if ( IsDebuggerPresent() )
    {
      v25 = -2147024809;
      v12 = 888;
      peUsea = L"0";
      goto LABEL_10;
    }
    LODWORD(peUse) = -2147024809;
    v13 = 888;
    cchReferencedDomainName = L"0";
LABEL_61:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v13,
      L"CreateWmsSid",
      L"CBRAEx",
      cchReferencedDomainName,
      peUse);
    goto LABEL_62;
  }
  v14 = GetTokenInformationWithLocalAlloc(v6, TokenPrimaryGroup, &v28);
  v8 = v28;
  v11 = v14;
  if ( v14 >= 0 && !CopySid(0x44u, a2, *(PSID *)v28) )
  {
    v15 = GetLastError();
    v11 = v15;
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x373u,
      L"CreateWmsSid",
      L"CBRAEx",
      L"fSuccess",
      v11);
    if ( IsDebuggerPresent() )
    {
      v12 = 883;
      goto LABEL_9;
    }
    v13 = 883;
    goto LABEL_60;
  }
LABEL_62:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  LocalFree(v7);
  LocalFree(v8);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140007158  mov     [rsp-8+arg_10], rbx
0x14000715d  push    rbp
0x14000715e  push    rsi
0x14000715f  push    rdi
0x140007160  push    r12
0x140007162  push    r13
0x140007164  push    r14
0x140007166  push    r15
0x140007168  lea     rbp, [rsp-190h]
0x140007170  sub     rsp, 290h
0x140007177  mov     rax, cs:__security_cookie
0x14000717e  xor     rax, rsp
0x140007181  mov     [rbp+1C0h+var_40], rax
0x140007188  mov     rsi, rdx
0x14000718b  mov     rdi, rcx
0x14000718e  xor     edx, edx; Val
0x140007190  lea     rcx, [rsp+2C0h+var_250]; void *
0x140007195  mov     r8d, 208h; Size
0x14000719b  call    memset_0
0x1400071a0  mov     eax, [rdi]
0x1400071a2  xor     r9d, r9d
0x1400071a5  xor     r12d, r12d
0x1400071a8  mov     dword ptr [rsp+2C0h+var_278], 104h
0x1400071b0  xor     r13d, r13d
0x1400071b3  mov     [rsp+2C0h+TokenHandle], r9
0x1400071b8  sub     eax, 3
0x1400071bb  mov     [rsp+2C0h+var_268], r12
0x1400071c0  mov     [rsp+2C0h+var_270], r13
0x1400071c5  lea     r14d, [r9+44h]
0x1400071c9  mov     [rsp+2C0h+cbSid], r14d
0x1400071ce  mov     [rsp+2C0h+var_27C], r9d
0x1400071d3  cmp     eax, 1
0x1400071d6  ja      loc_1400072A0
0x1400071dc  call    cs:__imp_GetCurrentProcess
0x1400071e2  mov     rcx, rax; ProcessHandle
0x1400071e5  lea     r8, [rsp+2C0h+TokenHandle]; TokenHandle
0x1400071ea  lea     edx, [r12+8]; DesiredAccess
0x1400071ef  call    cs:__imp_OpenProcessToken
0x1400071f5  test    eax, eax
0x1400071f7  jnz     loc_14000729B
0x1400071fd  call    cs:__imp_GetLastError
0x140007203  mov     ebx, eax
0x140007205  test    eax, eax
0x140007207  jle     short loc_140007212
0x140007209  movzx   ebx, ax
0x14000720c  or      ebx, 80070000h
0x140007212  mov     eax, 80004005h
0x140007217  lea     r14, aCbraex; "CBRAEx"
0x14000721e  test    ebx, ebx
0x140007220  lea     rsi, aCreatewmssid; "CreateWmsSid"
0x140007227  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x14000722e  mov     r9, r14; unsigned __int16 *
0x140007231  cmovns  ebx, eax
0x140007234  lea     r15, aFsuccess; "fSuccess"
0x14000723b  mov     dword ptr [rsp+2C0h+cchReferencedDomainName], ebx; int
0x14000723f  mov     r8, rsi; unsigned __int16 *
0x140007242  mov     edx, 34Eh; unsigned int
0x140007247  mov     [rsp+2C0h+ReferencedDomainName], r15; unsigned __int16 *
0x14000724c  mov     rcx, rdi; unsigned __int16 *
0x14000724f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007254  call    cs:__imp_IsDebuggerPresent
0x14000725a  test    eax, eax
0x14000725c  jz      short loc_140007290
0x14000725e  mov     r9d, 34Eh
0x140007264  mov     [rsp+2C0h+var_288], ebx
0x140007268  mov     [rsp+2C0h+peUse], r15
0x14000726d  mov     [rsp+2C0h+cchReferencedDomainName], r14
0x140007272  mov     r8, rdi
0x140007275  mov     [rsp+2C0h+ReferencedDomainName], rsi
0x14000727a  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140007281  mov     ecx, 2; unsigned __int8
0x140007286  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000728b  jmp     loc_14000768A
0x140007290  mov     r8d, 34Eh
0x140007296  jmp     loc_14000766A
0x14000729b  mov     r9, [rsp+2C0h+TokenHandle]
0x1400072a0  mov     ecx, [rdi]
0x1400072a2  xor     ebx, ebx
0x1400072a4  test    ecx, ecx
0x1400072a6  jz      loc_1400075DD
0x1400072ac  sub     ecx, 1
0x1400072af  jz      loc_14000752C
0x1400072b5  sub     ecx, 1
0x1400072b8  jz      loc_1400074A0
0x1400072be  sub     ecx, 1
0x1400072c1  jz      loc_1400073F0
0x1400072c7  cmp     ecx, 1
0x1400072ca  jz      short loc_140007340
0x1400072cc  lea     rax, a0; "0"
0x1400072d3  mov     ebx, 80070057h
0x1400072d8  lea     r14, aCbraex; "CBRAEx"
0x1400072df  mov     dword ptr [rsp+2C0h+cchReferencedDomainName], ebx; int
0x1400072e3  lea     rsi, aCreatewmssid; "CreateWmsSid"
0x1400072ea  mov     [rsp+2C0h+ReferencedDomainName], rax; unsigned __int16 *
0x1400072ef  mov     r15d, 378h
0x1400072f5  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400072fc  mov     r9, r14; unsigned __int16 *
0x1400072ff  mov     r8, rsi; unsigned __int16 *
0x140007302  mov     edx, r15d; unsigned int
0x140007305  mov     rcx, rdi; unsigned __int16 *
0x140007308  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000730d  call    cs:__imp_IsDebuggerPresent
0x140007313  test    eax, eax
0x140007315  lea     rax, a0; "0"
0x14000731c  jz      short loc_14000732F
0x14000731e  mov     [rsp+2C0h+var_288], ebx
0x140007322  mov     r9d, r15d
0x140007325  mov     [rsp+2C0h+peUse], rax
0x14000732a  jmp     loc_14000726D
0x14000732f  mov     dword ptr [rsp+2C0h+peUse], ebx
0x140007333  mov     r8d, r15d
0x140007336  mov     [rsp+2C0h+cchReferencedDomainName], rax
0x14000733b  jmp     loc_140007673
0x140007340  lea     r8, [rsp+2C0h+var_270]; void **
0x140007345  mov     edx, 5; TokenInformationClass
0x14000734a  mov     rcx, r9; TokenHandle
0x14000734d  call    ?GetTokenInformationWithLocalAlloc@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z; GetTokenInformationWithLocalAlloc(void *,_TOKEN_INFORMATION_CLASS,void * *)
0x140007352  mov     r13, [rsp+2C0h+var_270]
0x140007357  mov     ebx, eax
0x140007359  test    eax, eax
0x14000735b  js      loc_14000768A
0x140007361  mov     r8, [r13+0]; pSourceSid
0x140007365  mov     rdx, rsi; pDestinationSid
0x140007368  mov     ecx, r14d; nDestinationSidLength
0x14000736b  call    cs:__imp_CopySid
0x140007371  test    eax, eax
0x140007373  jnz     loc_14000768A
0x140007379  call    cs:__imp_GetLastError
0x14000737f  mov     ebx, eax
0x140007381  test    eax, eax
0x140007383  jle     short loc_14000738E
0x140007385  movzx   ebx, ax
0x140007388  or      ebx, 80070000h
0x14000738e  mov     eax, 80004005h
0x140007393  lea     r14, aCbraex; "CBRAEx"
0x14000739a  test    ebx, ebx
0x14000739c  lea     rsi, aCreatewmssid; "CreateWmsSid"
0x1400073a3  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400073aa  mov     r9, r14; unsigned __int16 *
0x1400073ad  cmovns  ebx, eax
0x1400073b0  lea     r15, aFsuccess; "fSuccess"
0x1400073b7  mov     dword ptr [rsp+2C0h+cchReferencedDomainName], ebx; int
0x1400073bb  mov     r8, rsi; unsigned __int16 *
0x1400073be  mov     edx, 373h; unsigned int
0x1400073c3  mov     [rsp+2C0h+ReferencedDomainName], r15; unsigned __int16 *
0x1400073c8  mov     rcx, rdi; unsigned __int16 *
0x1400073cb  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400073d0  call    cs:__imp_IsDebuggerPresent
0x1400073d6  test    eax, eax
0x1400073d8  jz      short loc_1400073E5
0x1400073da  mov     r9d, 373h
0x1400073e0  jmp     loc_140007264
0x1400073e5  mov     r8d, 373h
0x1400073eb  jmp     loc_14000766A
0x1400073f0  lea     r8, [rsp+2C0h+var_268]; void **
0x1400073f5  mov     edx, 1; TokenInformationClass
0x1400073fa  mov     rcx, r9; TokenHandle
0x1400073fd  call    ?GetTokenInformationWithLocalAlloc@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z; GetTokenInformationWithLocalAlloc(void *,_TOKEN_INFORMATION_CLASS,void * *)
0x140007402  mov     r12, [rsp+2C0h+var_268]
0x140007407  mov     ebx, eax
0x140007409  test    eax, eax
0x14000740b  js      loc_14000768A
0x140007411  mov     r8, [r12]; pSourceSid
0x140007415  mov     rdx, rsi; pDestinationSid
0x140007418  mov     ecx, r14d; nDestinationSidLength
0x14000741b  call    cs:__imp_CopySid
0x140007421  test    eax, eax
0x140007423  jnz     loc_14000768A
0x140007429  call    cs:__imp_GetLastError
0x14000742f  mov     ebx, eax
0x140007431  test    eax, eax
0x140007433  jle     short loc_14000743E
0x140007435  movzx   ebx, ax
0x140007438  or      ebx, 80070000h
0x14000743e  mov     eax, 80004005h
0x140007443  lea     r14, aCbraex; "CBRAEx"
0x14000744a  test    ebx, ebx
0x14000744c  lea     rsi, aCreatewmssid; "CreateWmsSid"
0x140007453  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x14000745a  mov     r9, r14; unsigned __int16 *
0x14000745d  cmovns  ebx, eax
0x140007460  lea     r15, aFsuccess; "fSuccess"
0x140007467  mov     dword ptr [rsp+2C0h+cchReferencedDomainName], ebx; int
0x14000746b  mov     r8, rsi; unsigned __int16 *
0x14000746e  mov     edx, 36Ah; unsigned int
0x140007473  mov     [rsp+2C0h+ReferencedDomainName], r15; unsigned __int16 *
0x140007478  mov     rcx, rdi; unsigned __int16 *
0x14000747b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007480  call    cs:__imp_IsDebuggerPresent
0x140007486  test    eax, eax
0x140007488  jz      short loc_140007495
0x14000748a  mov     r9d, 36Ah
0x140007490  jmp     loc_140007264
0x140007495  mov     r8d, 36Ah
0x14000749b  jmp     loc_14000766A
0x1400074a0  mov     rcx, [rdi+8]; unsigned __int16 *
0x1400074a4  mov     rdx, rsi; void *
0x1400074a7  call    ?s_GetLocalGroupSid@CUserManagement@@SAJPEBGPEAX_K@Z; CUserManagement::s_GetLocalGroupSid(ushort const *,void *,unsigned __int64)
0x1400074ac  mov     ebx, eax
0x1400074ae  test    eax, eax
0x1400074b0  jns     loc_14000768A
0x1400074b6  mov     dword ptr [rsp+2C0h+cchReferencedDomainName], eax; int
0x1400074ba  lea     rsi, aCreatewmssid; "CreateWmsSid"
0x1400074c1  mov     r14d, 360h
0x1400074c7  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400074ce  lea     r15, aHr; "hr"
0x1400074d5  mov     r8, rsi; unsigned __int16 *
0x1400074d8  mov     edx, r14d; unsigned int
0x1400074db  mov     [rsp+2C0h+ReferencedDomainName], r15; unsigned __int16 *
0x1400074e0  mov     rcx, rdi; unsigned __int16 *
0x1400074e3  lea     r9, aChra; "CHRA"
0x1400074ea  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400074ef  call    cs:__imp_IsDebuggerPresent
0x1400074f5  test    eax, eax
0x1400074f7  lea     rax, aChra; "CHRA"
0x1400074fe  jz      short loc_140007516
0x140007500  mov     [rsp+2C0h+var_288], ebx
0x140007504  mov     r9d, r14d
0x140007507  mov     [rsp+2C0h+peUse], r15
0x14000750c  mov     [rsp+2C0h+cchReferencedDomainName], rax
0x140007511  jmp     loc_140007272
0x140007516  mov     dword ptr [rsp+2C0h+peUse], ebx
0x14000751a  mov     r8d, r14d
0x14000751d  mov     [rsp+2C0h+cchReferencedDomainName], r15
0x140007522  mov     [rsp+2C0h+ReferencedDomainName], rax
0x140007527  jmp     loc_140007678
0x14000752c  mov     rdx, [rdi+8]; lpAccountName
0x140007530  lea     rax, [rsp+2C0h+var_27C]
0x140007535  mov     [rsp+2C0h+peUse], rax; peUse
0x14000753a  lea     r9, [rsp+2C0h+cbSid]; cbSid
0x14000753f  lea     rax, [rsp+2C0h+var_278]
0x140007544  mov     r8, rsi; Sid
0x140007547  mov     [rsp+2C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14000754c  xor     ecx, ecx; lpSystemName
0x14000754e  lea     rax, [rsp+2C0h+var_250]
0x140007553  mov     [rsp+2C0h+ReferencedDomainName], rax; ReferencedDomainName
0x140007558  call    cs:__imp_LookupAccountNameW
0x14000755e  test    eax, eax
0x140007560  jnz     loc_14000768A
0x140007566  call    cs:__imp_GetLastError
0x14000756c  mov     ebx, eax
0x14000756e  test    eax, eax
0x140007570  jle     short loc_14000757B
0x140007572  movzx   ebx, ax
0x140007575  or      ebx, 80070000h
0x14000757b  mov     eax, 80004005h
0x140007580  lea     r14, aCbraex; "CBRAEx"
0x140007587  test    ebx, ebx
0x140007589  lea     rsi, aCreatewmssid; "CreateWmsSid"
0x140007590  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140007597  mov     r9, r14; unsigned __int16 *
0x14000759a  cmovns  ebx, eax
0x14000759d  lea     r15, aFsuccess; "fSuccess"
0x1400075a4  mov     dword ptr [rsp+2C0h+cchReferencedDomainName], ebx; int
0x1400075a8  mov     r8, rsi; unsigned __int16 *
0x1400075ab  mov     edx, 35Bh; unsigned int
0x1400075b0  mov     [rsp+2C0h+ReferencedDomainName], r15; unsigned __int16 *
0x1400075b5  mov     rcx, rdi; unsigned __int16 *
0x1400075b8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400075bd  call    cs:__imp_IsDebuggerPresent
0x1400075c3  test    eax, eax
0x1400075c5  jz      short loc_1400075D2
0x1400075c7  mov     r9d, 35Bh
0x1400075cd  jmp     loc_140007264
0x1400075d2  mov     r8d, 35Bh
0x1400075d8  jmp     loc_14000766A
0x1400075dd  mov     ecx, [rdi+4]; WellKnownSidType
0x1400075e0  lea     r9, [rsp+2C0h+cbSid]; cbSid
0x1400075e5  mov     r8, rsi; pSid
0x1400075e8  xor     edx, edx; DomainSid
0x1400075ea  call    cs:__imp_CreateWellKnownSid
0x1400075f0  test    eax, eax
0x1400075f2  jnz     loc_14000768A
0x1400075f8  call    cs:__imp_GetLastError
0x1400075fe  mov     ebx, eax
0x140007600  test    eax, eax
0x140007602  jle     short loc_14000760D
0x140007604  movzx   ebx, ax
0x140007607  or      ebx, 80070000h
0x14000760d  mov     eax, 80004005h
0x140007612  lea     r14, aCbraex; "CBRAEx"
0x140007619  test    ebx, ebx
0x14000761b  lea     rsi, aCreatewmssid; "CreateWmsSid"
0x140007622  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140007629  mov     r9, r14; unsigned __int16 *
0x14000762c  cmovns  ebx, eax
0x14000762f  lea     r15, aFsuccess; "fSuccess"
0x140007636  mov     dword ptr [rsp+2C0h+cchReferencedDomainName], ebx; int
0x14000763a  mov     r8, rsi; unsigned __int16 *
0x14000763d  mov     edx, 355h; unsigned int
0x140007642  mov     [rsp+2C0h+ReferencedDomainName], r15; unsigned __int16 *
0x140007647  mov     rcx, rdi; unsigned __int16 *
0x14000764a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000764f  call    cs:__imp_IsDebuggerPresent
0x140007655  test    eax, eax
0x140007657  jz      short loc_140007664
0x140007659  mov     r9d, 355h
0x14000765f  jmp     loc_140007264
0x140007664  mov     r8d, 355h
0x14000766a  mov     dword ptr [rsp+2C0h+peUse], ebx
  ... truncated ...
```
