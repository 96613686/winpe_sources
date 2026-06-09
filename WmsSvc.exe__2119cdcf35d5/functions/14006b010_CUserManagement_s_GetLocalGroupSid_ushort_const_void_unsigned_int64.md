# CUserManagement::s_GetLocalGroupSid(ushort const *,void *,unsigned __int64)

- ea: `0x14006b010`
- end: `0x14006b2c7`
- name: `?s_GetLocalGroupSid@CUserManagement@@SAJPEBGPEAX_K@Z`
- size: `695`
- prototype: `static int(const unsigned __int16 *, void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140066310`
- `0x14006c590`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006b010`
- `0x14006ba90`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!LsaOpenPolicy` at `0x14006b09f`
- `ADVAPI32!LsaOpenPolicy` at `0x14006b09f`
- `ADVAPI32!LsaFreeMemory` at `0x14006b284`
- `ADVAPI32!LsaFreeMemory` at `0x14006b284`
- `ADVAPI32!LsaClose` at `0x14006b294`
- `ADVAPI32!LsaClose` at `0x14006b294`
- `ADVAPI32!LsaLookupNames2` at `0x14006b18e`
- `ADVAPI32!LsaLookupNames2` at `0x14006b18e`
- `ADVAPI32!LsaNtStatusToWinError` at `0x14006b0af`
- `ADVAPI32!LsaNtStatusToWinError` at `0x14006b19a`
- `ADVAPI32!LsaNtStatusToWinError` at `0x14006b0af`
- `ADVAPI32!LsaNtStatusToWinError` at `0x14006b19a`
- `ADVAPI32!CopySid` at `0x14006b1cb`
- `ADVAPI32!CopySid` at `0x14006b1cb`
- `KERNEL32!LocalFree` at `0x14006b274`
- `KERNEL32!LocalFree` at `0x14006b274`
- `KERNEL32!GetLastError` at `0x14006b1d9`
- `KERNEL32!GetLastError` at `0x14006b1d9`
- `KERNEL32!IsDebuggerPresent` at `0x14006b100`
- `KERNEL32!IsDebuggerPresent` at `0x14006b234`
- `KERNEL32!IsDebuggerPresent` at `0x14006b100`
- `KERNEL32!IsDebuggerPresent` at `0x14006b234`

## string_xrefs

- `0x14006b0df`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006b209`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006b0ca`: `CUserManagement::s_GetLocalGroupSid`
- `0x14006b1fc`: `CUserManagement::s_GetLocalGroupSid`

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
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
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
      0x43Fu,
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
0x14006b010  mov     [rsp-8+arg_10], rbx
0x14006b015  mov     [rsp-8+arg_18], rsi
0x14006b01a  push    rbp
0x14006b01b  push    rdi
0x14006b01c  push    r13
0x14006b01e  push    r14
0x14006b020  push    r15
0x14006b022  lea     rbp, [rsp-1B0h]
0x14006b02a  sub     rsp, 2B0h
0x14006b031  mov     rax, cs:__security_cookie
0x14006b038  xor     rax, rsp
0x14006b03b  mov     [rbp+1D0h+var_30], rax
0x14006b042  mov     rdi, rdx
0x14006b045  mov     rbx, rcx
0x14006b048  xorps   xmm0, xmm0
0x14006b04b  lea     rcx, [rbp+1D0h+var_230]; void *
0x14006b04f  xor     edx, edx; Val
0x14006b051  mov     r8d, 200h; Size
0x14006b057  movups  xmmword ptr [rsp+2D0h+Names.Length], xmm0
0x14006b05c  call    memset_0
0x14006b061  xorps   xmm0, xmm0
0x14006b064  mov     [rsp+2D0h+var_290], 0
0x14006b06d  lea     r9, [rsp+2D0h+PolicyHandle]; PolicyHandle
0x14006b072  mov     [rsp+2D0h+PolicyHandle], 0
0x14006b07b  mov     r8d, 0F0FFFh; DesiredAccess
0x14006b081  mov     [rsp+2D0h+var_280], 0
0x14006b08a  lea     rdx, [rsp+2D0h+ObjectAttributes]; ObjectAttributes
0x14006b08f  xor     ecx, ecx; SystemName
0x14006b091  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.Length], xmm0
0x14006b096  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.ObjectName], xmm0
0x14006b09b  movups  xmmword ptr [rbp+1D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14006b09f  call    cs:__imp_LsaOpenPolicy
0x14006b0a5  test    eax, eax
0x14006b0a7  jz      loc_14006B14A
0x14006b0ad  mov     ecx, eax; Status
0x14006b0af  call    cs:__imp_LsaNtStatusToWinError
0x14006b0b5  mov     ebx, eax
0x14006b0b7  test    eax, eax
0x14006b0b9  jle     short loc_14006B0C4
0x14006b0bb  movzx   ebx, ax
0x14006b0be  or      ebx, 80070000h
0x14006b0c4  mov     r13d, 436h
0x14006b0ca  lea     rsi, aCusermanagemen_7; "CUserManagement::s_GetLocalGroupSid"
0x14006b0d1  mov     dword ptr [rsp+2D0h+Sids], ebx; int
0x14006b0d5  lea     r14, aCbraex; "CBRAEx"
0x14006b0dc  mov     r8, rsi; unsigned __int16 *
0x14006b0df  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006b0e6  mov     r9, r14; unsigned __int16 *
0x14006b0e9  lea     r15, aStatusNtstatus_0; "status == ((NTSTATUS)0x00000000L)"
0x14006b0f0  mov     rcx, rdi; unsigned __int16 *
0x14006b0f3  mov     edx, r13d; unsigned int
0x14006b0f6  mov     [rsp+2D0h+ReferencedDomains], r15; unsigned __int16 *
0x14006b0fb  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006b100  call    cs:__imp_IsDebuggerPresent
0x14006b106  test    eax, eax
0x14006b108  jz      short loc_14006B139
0x14006b10a  mov     [rsp+2D0h+var_298], ebx
0x14006b10e  mov     r9d, r13d
0x14006b111  mov     [rsp+2D0h+var_2A0], r15
0x14006b116  mov     [rsp+2D0h+Sids], r14
0x14006b11b  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006b122  mov     r8, rdi
0x14006b125  mov     [rsp+2D0h+ReferencedDomains], rsi
0x14006b12a  mov     ecx, 2; unsigned __int8
0x14006b12f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006b134  jmp     loc_14006B272
0x14006b139  mov     dword ptr [rsp+2D0h+var_2A0], ebx
0x14006b13d  mov     r8d, r13d
0x14006b140  mov     [rsp+2D0h+Sids], r15
0x14006b145  jmp     loc_14006B25B
0x14006b14a  lea     r8, [rbp+1D0h+var_230]; unsigned __int16 *
0x14006b14e  mov     rdx, rbx; unsigned __int16 *
0x14006b151  lea     rcx, [rsp+2D0h+Names]; struct _LSA_UNICODE_STRING *
0x14006b156  call    ?s_InitLsaUnicodeString@CUserManagement@@SAJPEAU_LSA_UNICODE_STRING@@PEBGPEAGG@Z; CUserManagement::s_InitLsaUnicodeString(_LSA_UNICODE_STRING *,ushort const *,ushort *,ushort)
0x14006b15b  mov     ebx, eax
0x14006b15d  test    eax, eax
0x14006b15f  js      loc_14006B272
0x14006b165  mov     rcx, [rsp+2D0h+PolicyHandle]; PolicyHandle
0x14006b16a  lea     rax, [rsp+2D0h+var_290]
0x14006b16f  mov     [rsp+2D0h+Sids], rax; Sids
0x14006b174  lea     r9, [rsp+2D0h+Names]; Names
0x14006b179  lea     rax, [rsp+2D0h+var_280]
0x14006b17e  mov     edx, 80000000h; Flags
0x14006b183  mov     r8d, 1; Count
0x14006b189  mov     [rsp+2D0h+ReferencedDomains], rax; ReferencedDomains
0x14006b18e  call    cs:__imp_LsaLookupNames2
0x14006b194  test    eax, eax
0x14006b196  jz      short loc_14006B1BA
0x14006b198  mov     ecx, eax; Status
0x14006b19a  call    cs:__imp_LsaNtStatusToWinError
0x14006b1a0  mov     ebx, eax
0x14006b1a2  test    eax, eax
0x14006b1a4  jle     short loc_14006B1AF
0x14006b1a6  movzx   ebx, ax
0x14006b1a9  or      ebx, 80070000h
0x14006b1af  mov     r13d, 43Ch
0x14006b1b5  jmp     loc_14006B0CA
0x14006b1ba  mov     r8, [rsp+2D0h+var_290]
0x14006b1bf  mov     rdx, rdi; pDestinationSid
0x14006b1c2  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x14006b1c7  mov     r8, [r8+8]; pSourceSid
0x14006b1cb  call    cs:__imp_CopySid
0x14006b1d1  test    eax, eax
0x14006b1d3  jnz     loc_14006B272
0x14006b1d9  call    cs:__imp_GetLastError
0x14006b1df  mov     ebx, eax
0x14006b1e1  test    eax, eax
0x14006b1e3  jle     short loc_14006B1EE
0x14006b1e5  movzx   ebx, ax
0x14006b1e8  or      ebx, 80070000h
0x14006b1ee  mov     eax, 80004005h
0x14006b1f3  lea     r14, aCbraex; "CBRAEx"
0x14006b1fa  test    ebx, ebx
0x14006b1fc  lea     rsi, aCusermanagemen_7; "CUserManagement::s_GetLocalGroupSid"
0x14006b203  mov     r15d, 43Fh
0x14006b209  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006b210  cmovns  ebx, eax
0x14006b213  lea     r13, aFsuccess; "fSuccess"
0x14006b21a  mov     dword ptr [rsp+2D0h+Sids], ebx; int
0x14006b21e  mov     r9, r14; unsigned __int16 *
0x14006b221  mov     r8, rsi; unsigned __int16 *
0x14006b224  mov     [rsp+2D0h+ReferencedDomains], r13; unsigned __int16 *
0x14006b229  mov     edx, r15d; unsigned int
0x14006b22c  mov     rcx, rdi; unsigned __int16 *
0x14006b22f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006b234  call    cs:__imp_IsDebuggerPresent
0x14006b23a  test    eax, eax
0x14006b23c  jz      short loc_14006B24F
0x14006b23e  mov     [rsp+2D0h+var_298], ebx
0x14006b242  mov     r9d, r15d
0x14006b245  mov     [rsp+2D0h+var_2A0], r13
0x14006b24a  jmp     loc_14006B116
0x14006b24f  mov     dword ptr [rsp+2D0h+var_2A0], ebx
0x14006b253  mov     r8d, r15d
0x14006b256  mov     [rsp+2D0h+Sids], r13
0x14006b25b  mov     r9, rsi
0x14006b25e  mov     [rsp+2D0h+ReferencedDomains], r14
0x14006b263  mov     rdx, rdi
0x14006b266  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14006b26d  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006b272  xor     ecx, ecx; hMem
0x14006b274  call    cs:__imp_LocalFree
0x14006b27a  mov     rcx, [rsp+2D0h+var_290]; Buffer
0x14006b27f  test    rcx, rcx
0x14006b282  jz      short loc_14006B28A
0x14006b284  call    cs:__imp_LsaFreeMemory
0x14006b28a  mov     rcx, [rsp+2D0h+PolicyHandle]; ObjectHandle
0x14006b28f  test    rcx, rcx
0x14006b292  jz      short loc_14006B29A
0x14006b294  call    cs:__imp_LsaClose
0x14006b29a  mov     eax, ebx
0x14006b29c  mov     rcx, [rbp+1D0h+var_30]
0x14006b2a3  xor     rcx, rsp; StackCookie
0x14006b2a6  call    __security_check_cookie
0x14006b2ab  lea     r11, [rsp+2D0h+var_20]
0x14006b2b3  mov     rbx, [r11+40h]
0x14006b2b7  mov     rsi, [r11+48h]
0x14006b2bb  mov     rsp, r11
0x14006b2be  pop     r15
0x14006b2c0  pop     r14
0x14006b2c2  pop     r13
0x14006b2c4  pop     rdi
0x14006b2c5  pop     rbp
0x14006b2c6  retn
```
