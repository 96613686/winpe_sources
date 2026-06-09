# CUserManagement::s_GetLocalGroupSid(ushort const *,void *,unsigned __int64)

- ea: `0x14000a61c`
- end: `0x14000a8d3`
- name: `?s_GetLocalGroupSid@CUserManagement@@SAJPEBGPEAX_K@Z`
- size: `695`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140007158`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x14000a61c`
- `0x14000a8dc`
- `0x14000ae32`
- `0x14000ae60`

## import_xrefs

- `ADVAPI32!LsaClose` at `0x14000a8a0`
- `ADVAPI32!LsaClose` at `0x14000a8a0`
- `ADVAPI32!LsaFreeMemory` at `0x14000a890`
- `ADVAPI32!LsaFreeMemory` at `0x14000a890`
- `ADVAPI32!LsaLookupNames2` at `0x14000a79a`
- `ADVAPI32!LsaLookupNames2` at `0x14000a79a`
- `ADVAPI32!LsaNtStatusToWinError` at `0x14000a6bb`
- `ADVAPI32!LsaNtStatusToWinError` at `0x14000a7a6`
- `ADVAPI32!LsaNtStatusToWinError` at `0x14000a6bb`
- `ADVAPI32!LsaNtStatusToWinError` at `0x14000a7a6`
- `ADVAPI32!LsaOpenPolicy` at `0x14000a6ab`
- `ADVAPI32!LsaOpenPolicy` at `0x14000a6ab`
- `ADVAPI32!CopySid` at `0x14000a7d7`
- `ADVAPI32!CopySid` at `0x14000a7d7`
- `KERNEL32!LocalFree` at `0x14000a880`
- `KERNEL32!LocalFree` at `0x14000a880`
- `KERNEL32!IsDebuggerPresent` at `0x14000a70c`
- `KERNEL32!IsDebuggerPresent` at `0x14000a840`
- `KERNEL32!IsDebuggerPresent` at `0x14000a70c`
- `KERNEL32!IsDebuggerPresent` at `0x14000a840`
- `KERNEL32!GetLastError` at `0x14000a7e5`
- `KERNEL32!GetLastError` at `0x14000a7e5`

## string_xrefs

- `0x14000a6eb`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14000a815`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14000a6d6`: `CUserManagement::s_GetLocalGroupSid`
- `0x14000a808`: `CUserManagement::s_GetLocalGroupSid`

## pseudocode

```c
__int64 __fastcall CUserManagement::s_GetLocalGroupSid(const unsigned __int16 *a1, void *a2)
{
  NTSTATUS v4; // eax
  unsigned __int16 v5; // r9
  signed int v6; // eax
  signed int inited; // ebx
  unsigned int v8; // r13d
  NTSTATUS v9; // eax
  signed int v10; // eax
  signed int LastError; // eax
  PLSA_TRANSLATED_SID2 Sids; // [rsp+40h] [rbp-C0h] BYREF
  PVOID PolicyHandle; // [rsp+48h] [rbp-B8h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+50h] [rbp-B0h] BYREF
  struct _LSA_UNICODE_STRING Names; // [rsp+58h] [rbp-A8h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v18[256]; // [rsp+A0h] [rbp-60h] BYREF

  Names = 0;
  memset_0(v18, 0, sizeof(v18));
  Sids = 0;
  PolicyHandle = 0;
  ReferencedDomains = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v4 = LsaOpenPolicy(0, &ObjectAttributes, 0xF0FFFu, &PolicyHandle);
  if ( v4 )
  {
    v6 = LsaNtStatusToWinError(v4);
    inited = v6;
    if ( v6 > 0 )
      inited = (unsigned __int16)v6 | 0x80070000;
    v8 = 1078;
LABEL_5:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      v8,
      L"CUserManagement::s_GetLocalGroupSid",
      L"CBRAEx",
      L"status == ((NTSTATUS)0x00000000L)",
      inited);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        v8,
        L"CUserManagement::s_GetLocalGroupSid",
        L"CBRAEx",
        L"status == ((NTSTATUS)0x00000000L)",
        inited);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        v8,
        L"CUserManagement::s_GetLocalGroupSid",
        L"CBRAEx",
        L"status == ((NTSTATUS)0x00000000L)",
        inited);
    goto LABEL_22;
  }
  inited = CUserManagement::s_InitLsaUnicodeString(&Names, a1, v18, v5);
  if ( inited < 0 )
    goto LABEL_22;
  v9 = LsaLookupNames2(PolicyHandle, 0x80000000, 1u, &Names, &ReferencedDomains, &Sids);
  if ( v9 )
  {
    v10 = LsaNtStatusToWinError(v9);
    inited = v10;
    if ( v10 > 0 )
      inited = (unsigned __int16)v10 | 0x80070000;
    v8 = 1084;
    goto LABEL_5;
  }
  if ( !CopySid(0x44u, a2, Sids->Sid) )
  {
    LastError = GetLastError();
    inited = LastError;
    if ( LastError > 0 )
      inited = (unsigned __int16)LastError | 0x80070000;
    if ( inited >= 0 )
      inited = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      1087,
      L"CUserManagement::s_GetLocalGroupSid",
      L"CBRAEx",
      L"fSuccess",
      inited);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        1087,
        L"CUserManagement::s_GetLocalGroupSid",
        L"CBRAEx",
        L"fSuccess",
        inited);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        1087,
        L"CUserManagement::s_GetLocalGroupSid",
        L"CBRAEx",
        L"fSuccess",
        inited);
  }
LABEL_22:
  LocalFree(0);
  if ( Sids )
    LsaFreeMemory(Sids);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14000a61c  mov     [rsp-8+arg_10], rbx
0x14000a621  mov     [rsp-8+arg_18], rsi
0x14000a626  push    rbp
0x14000a627  push    rdi
0x14000a628  push    r13
0x14000a62a  push    r14
0x14000a62c  push    r15
0x14000a62e  lea     rbp, [rsp-1B0h]
0x14000a636  sub     rsp, 2B0h
0x14000a63d  mov     rax, cs:__security_cookie
0x14000a644  xor     rax, rsp
0x14000a647  mov     [rbp+1D0h+var_30], rax
0x14000a64e  mov     rdi, rdx
0x14000a651  mov     rbx, rcx
0x14000a654  xorps   xmm0, xmm0
0x14000a657  lea     rcx, [rbp+1D0h+var_230]; void *
0x14000a65b  xor     edx, edx; Val
0x14000a65d  mov     r8d, 200h; Size
0x14000a663  movups  xmmword ptr [rsp+2D0h+Names.Length], xmm0
0x14000a668  call    memset_0
0x14000a66d  xorps   xmm0, xmm0
0x14000a670  mov     [rsp+2D0h+var_290], 0
0x14000a679  lea     r9, [rsp+2D0h+PolicyHandle]; PolicyHandle
0x14000a67e  mov     [rsp+2D0h+PolicyHandle], 0
0x14000a687  mov     r8d, 0F0FFFh; DesiredAccess
0x14000a68d  mov     [rsp+2D0h+var_280], 0
0x14000a696  lea     rdx, [rsp+2D0h+ObjectAttributes]; ObjectAttributes
0x14000a69b  xor     ecx, ecx; SystemName
0x14000a69d  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.Length], xmm0
0x14000a6a2  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.ObjectName], xmm0
0x14000a6a7  movups  xmmword ptr [rbp+1D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000a6ab  call    cs:__imp_LsaOpenPolicy
0x14000a6b1  test    eax, eax
0x14000a6b3  jz      loc_14000A756
0x14000a6b9  mov     ecx, eax; Status
0x14000a6bb  call    cs:__imp_LsaNtStatusToWinError
0x14000a6c1  mov     ebx, eax
0x14000a6c3  test    eax, eax
0x14000a6c5  jle     short loc_14000A6D0
0x14000a6c7  movzx   ebx, ax
0x14000a6ca  or      ebx, 80070000h
0x14000a6d0  mov     r13d, 436h
0x14000a6d6  lea     rsi, aCusermanagemen_0; "CUserManagement::s_GetLocalGroupSid"
0x14000a6dd  mov     dword ptr [rsp+2D0h+Sids], ebx; int
0x14000a6e1  lea     r14, aCbraex; "CBRAEx"
0x14000a6e8  mov     r8, rsi; unsigned __int16 *
0x14000a6eb  lea     rdi, aTermsrvWmsSrcC_2; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14000a6f2  mov     r9, r14; unsigned __int16 *
0x14000a6f5  lea     r15, aStatusNtstatus; "status == ((NTSTATUS)0x00000000L)"
0x14000a6fc  mov     rcx, rdi; unsigned __int16 *
0x14000a6ff  mov     edx, r13d; unsigned int
0x14000a702  mov     [rsp+2D0h+ReferencedDomains], r15; unsigned __int16 *
0x14000a707  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000a70c  call    cs:__imp_IsDebuggerPresent
0x14000a712  test    eax, eax
0x14000a714  jz      short loc_14000A745
0x14000a716  mov     [rsp+2D0h+var_298], ebx
0x14000a71a  mov     r9d, r13d
0x14000a71d  mov     [rsp+2D0h+var_2A0], r15
0x14000a722  mov     [rsp+2D0h+Sids], r14
0x14000a727  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000a72e  mov     r8, rdi
0x14000a731  mov     [rsp+2D0h+ReferencedDomains], rsi
0x14000a736  mov     ecx, 2; unsigned __int8
0x14000a73b  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000a740  jmp     loc_14000A87E
0x14000a745  mov     dword ptr [rsp+2D0h+var_2A0], ebx
0x14000a749  mov     r8d, r13d
0x14000a74c  mov     [rsp+2D0h+Sids], r15
0x14000a751  jmp     loc_14000A867
0x14000a756  lea     r8, [rbp+1D0h+var_230]; unsigned __int16 *
0x14000a75a  mov     rdx, rbx; unsigned __int16 *
0x14000a75d  lea     rcx, [rsp+2D0h+Names]; struct _LSA_UNICODE_STRING *
0x14000a762  call    ?s_InitLsaUnicodeString@CUserManagement@@SAJPEAU_LSA_UNICODE_STRING@@PEBGPEAGG@Z; CUserManagement::s_InitLsaUnicodeString(_LSA_UNICODE_STRING *,ushort const *,ushort *,ushort)
0x14000a767  mov     ebx, eax
0x14000a769  test    eax, eax
0x14000a76b  js      loc_14000A87E
0x14000a771  mov     rcx, [rsp+2D0h+PolicyHandle]; PolicyHandle
0x14000a776  lea     rax, [rsp+2D0h+var_290]
0x14000a77b  mov     [rsp+2D0h+Sids], rax; Sids
0x14000a780  lea     r9, [rsp+2D0h+Names]; Names
0x14000a785  lea     rax, [rsp+2D0h+var_280]
0x14000a78a  mov     edx, 80000000h; Flags
0x14000a78f  mov     r8d, 1; Count
0x14000a795  mov     [rsp+2D0h+ReferencedDomains], rax; ReferencedDomains
0x14000a79a  call    cs:__imp_LsaLookupNames2
0x14000a7a0  test    eax, eax
0x14000a7a2  jz      short loc_14000A7C6
0x14000a7a4  mov     ecx, eax; Status
0x14000a7a6  call    cs:__imp_LsaNtStatusToWinError
0x14000a7ac  mov     ebx, eax
0x14000a7ae  test    eax, eax
0x14000a7b0  jle     short loc_14000A7BB
0x14000a7b2  movzx   ebx, ax
0x14000a7b5  or      ebx, 80070000h
0x14000a7bb  mov     r13d, 43Ch
0x14000a7c1  jmp     loc_14000A6D6
0x14000a7c6  mov     r8, [rsp+2D0h+var_290]
0x14000a7cb  mov     rdx, rdi; pDestinationSid
0x14000a7ce  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x14000a7d3  mov     r8, [r8+8]; pSourceSid
0x14000a7d7  call    cs:__imp_CopySid
0x14000a7dd  test    eax, eax
0x14000a7df  jnz     loc_14000A87E
0x14000a7e5  call    cs:__imp_GetLastError
0x14000a7eb  mov     ebx, eax
0x14000a7ed  test    eax, eax
0x14000a7ef  jle     short loc_14000A7FA
0x14000a7f1  movzx   ebx, ax
0x14000a7f4  or      ebx, 80070000h
0x14000a7fa  mov     eax, 80004005h
0x14000a7ff  lea     r14, aCbraex; "CBRAEx"
0x14000a806  test    ebx, ebx
0x14000a808  lea     rsi, aCusermanagemen_0; "CUserManagement::s_GetLocalGroupSid"
0x14000a80f  mov     r15d, 43Fh
0x14000a815  lea     rdi, aTermsrvWmsSrcC_2; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14000a81c  cmovns  ebx, eax
0x14000a81f  lea     r13, aFsuccess; "fSuccess"
0x14000a826  mov     dword ptr [rsp+2D0h+Sids], ebx; int
0x14000a82a  mov     r9, r14; unsigned __int16 *
0x14000a82d  mov     r8, rsi; unsigned __int16 *
0x14000a830  mov     [rsp+2D0h+ReferencedDomains], r13; unsigned __int16 *
0x14000a835  mov     edx, r15d; unsigned int
0x14000a838  mov     rcx, rdi; unsigned __int16 *
0x14000a83b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000a840  call    cs:__imp_IsDebuggerPresent
0x14000a846  test    eax, eax
0x14000a848  jz      short loc_14000A85B
0x14000a84a  mov     [rsp+2D0h+var_298], ebx
0x14000a84e  mov     r9d, r15d
0x14000a851  mov     [rsp+2D0h+var_2A0], r13
0x14000a856  jmp     loc_14000A722
0x14000a85b  mov     dword ptr [rsp+2D0h+var_2A0], ebx
0x14000a85f  mov     r8d, r15d
0x14000a862  mov     [rsp+2D0h+Sids], r13
0x14000a867  mov     r9, rsi
0x14000a86a  mov     [rsp+2D0h+ReferencedDomains], r14
0x14000a86f  mov     rdx, rdi
0x14000a872  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000a879  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000a87e  xor     ecx, ecx; hMem
0x14000a880  call    cs:__imp_LocalFree
0x14000a886  mov     rcx, [rsp+2D0h+var_290]; Buffer
0x14000a88b  test    rcx, rcx
0x14000a88e  jz      short loc_14000A896
0x14000a890  call    cs:__imp_LsaFreeMemory
0x14000a896  mov     rcx, [rsp+2D0h+PolicyHandle]; ObjectHandle
0x14000a89b  test    rcx, rcx
0x14000a89e  jz      short loc_14000A8A6
0x14000a8a0  call    cs:__imp_LsaClose
0x14000a8a6  mov     eax, ebx
0x14000a8a8  mov     rcx, [rbp+1D0h+var_30]
0x14000a8af  xor     rcx, rsp; StackCookie
0x14000a8b2  call    __security_check_cookie
0x14000a8b7  lea     r11, [rsp+2D0h+var_20]
0x14000a8bf  mov     rbx, [r11+40h]
0x14000a8c3  mov     rsi, [r11+48h]
0x14000a8c7  mov     rsp, r11
0x14000a8ca  pop     r15
0x14000a8cc  pop     r14
0x14000a8ce  pop     r13
0x14000a8d0  pop     rdi
0x14000a8d1  pop     rbp
0x14000a8d2  retn
```
