# CTSSDFarmRpc::ConvertSidToAccountName(ushort const *,ushort * *,ushort * *)

- ea: `0x180038a78`
- end: `0x180038c3c`
- name: `?ConvertSidToAccountName@CTSSDFarmRpc@@AEAAJPEBGPEAPEAG1@Z`
- size: `452`
- prototype: `__int64 __fastcall(CTSSDFarmRpc *this, const unsigned __int16 *, unsigned __int16 **, HLOCAL *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039afc`

## callees

- `0x180003f30`
- `0x180038a78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038abc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038bbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038abc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038bbc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038b43`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038b6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038b43`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038b6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038bf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038c0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038c20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038bf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038c0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038c20`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180038ab2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180038ab2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180038b09`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180038bb2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180038b09`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180038bb2`

## string_xrefs

- `0x180038bdf`: `CTSSDFarmRpc::ConvertSidToAccountName`
- `0x180038ad5`: `ConvertStringSidToSid failed: 0x%x in %s`
- `0x180038b2c`: `LookupAccountSid failed: 0x%x in %s`
- `0x180038bd5`: `LookupAccountSid final failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSDFarmRpc::ConvertSidToAccountName(
        CTSSDFarmRpc *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        HLOCAL *a4)
{
  signed int v4; // ebx
  signed int LastError; // eax
  const char *v8; // rdx
  signed int v9; // eax
  unsigned __int16 *v10; // rax
  unsigned __int16 *ReferencedDomainName; // rax
  signed int v12; // eax
  PSID Sid; // [rsp+40h] [rbp-10h] BYREF
  DWORD cchReferencedDomainName; // [rsp+70h] [rbp+20h] BYREF
  int v16; // [rsp+74h] [rbp+24h]
  DWORD cchName; // [rsp+80h] [rbp+30h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+88h] [rbp+38h] BYREF

  v16 = HIDWORD(this);
  v4 = 0;
  peUse = SidTypeGroup;
  cchName = 0;
  cchReferencedDomainName = 0;
  Sid = 0;
  *a3 = 0;
  *a4 = 0;
  if ( !ConvertStringSidToSidW(a2, &Sid) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      v8 = "ConvertStringSidToSid failed: 0x%x in %s";
LABEL_20:
      _DbgPrintMessage(8, v8, (unsigned int)v4, "CTSSDFarmRpc::ConvertSidToAccountName");
      goto LABEL_21;
    }
  }
  if ( LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
  {
    v9 = GetLastError();
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    if ( v4 < 0 )
    {
      v8 = "LookupAccountSid failed: 0x%x in %s";
      goto LABEL_20;
    }
  }
  v10 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * cchName);
  *a3 = v10;
  if ( !v10 )
  {
    v4 = -2147024882;
    _DbgPrintMessage(
      8,
      "LocalAlloc pszAccountName failed: 0x%x in %s",
      2147942414LL,
      "CTSSDFarmRpc::ConvertSidToAccountName");
    goto LABEL_21;
  }
  ReferencedDomainName = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * cchReferencedDomainName);
  *a4 = ReferencedDomainName;
  if ( !ReferencedDomainName )
  {
    v4 = -2147024882;
    _DbgPrintMessage(
      8,
      "LocalAlloc pszAccountDomain failed: 0x%x in %s",
      2147942414LL,
      "CTSSDFarmRpc::ConvertSidToAccountName");
    goto LABEL_21;
  }
  if ( !LookupAccountSidW(0, Sid, *a3, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v12 = GetLastError();
    v4 = v12;
    if ( v12 > 0 )
      v4 = (unsigned __int16)v12 | 0x80070000;
    if ( v4 < 0 )
    {
      v8 = "LookupAccountSid final failed: 0x%x in %s";
      goto LABEL_20;
    }
  }
LABEL_21:
  if ( Sid )
    LocalFree(Sid);
  if ( v4 < 0 )
  {
    if ( *a3 )
    {
      LocalFree(*a3);
      *a3 = 0;
    }
    if ( *a4 )
    {
      LocalFree(*a4);
      *a4 = 0;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180038a78  mov     [rsp-18h+arg_8], rbx
0x180038a7d  mov     qword ptr [rsp-18h+arg_0], rcx
0x180038a82  push    rbp
0x180038a83  push    rsi
0x180038a84  push    rdi
0x180038a85  mov     rbp, rsp
0x180038a88  sub     rsp, 50h
0x180038a8c  xor     ebx, ebx
0x180038a8e  mov     [rbp+arg_18], 2
0x180038a95  mov     rcx, rdx; StringSid
0x180038a98  mov     [rbp+cchName], ebx
0x180038a9b  lea     rdx, [rbp+Sid]; Sid
0x180038a9f  mov     [rbp+arg_0], ebx
0x180038aa2  mov     [rbp+Sid], rbx
0x180038aa6  mov     rsi, r9
0x180038aa9  mov     [r8], rbx
0x180038aac  mov     rdi, r8
0x180038aaf  mov     [r9], rbx
0x180038ab2  call    cs:__imp_ConvertStringSidToSidW
0x180038ab8  test    eax, eax
0x180038aba  jnz     short loc_180038AE1
0x180038abc  call    cs:__imp_GetLastError
0x180038ac2  mov     ebx, eax
0x180038ac4  test    eax, eax
0x180038ac6  jle     short loc_180038AD1
0x180038ac8  movzx   ebx, ax
0x180038acb  or      ebx, 80070000h
0x180038ad1  test    ebx, ebx
0x180038ad3  jns     short loc_180038AE1
0x180038ad5  lea     rdx, aConvertstrings_1; "ConvertStringSidToSid failed: 0x%x in %"...
0x180038adc  jmp     loc_180038BDC
0x180038ae1  mov     rdx, [rbp+Sid]; Sid
0x180038ae5  lea     rax, [rbp+arg_18]
0x180038ae9  mov     [rsp+50h+peUse], rax; peUse
0x180038aee  lea     r9, [rbp+cchName]; cchName
0x180038af2  lea     rax, [rbp+arg_0]
0x180038af6  xor     r8d, r8d; Name
0x180038af9  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180038afe  xor     ecx, ecx; lpSystemName
0x180038b00  mov     [rsp+50h+ReferencedDomainName], 0; ReferencedDomainName
0x180038b09  call    cs:__imp_LookupAccountSidW
0x180038b0f  test    eax, eax
0x180038b11  jz      short loc_180038B38
0x180038b13  call    cs:__imp_GetLastError
0x180038b19  mov     ebx, eax
0x180038b1b  test    eax, eax
0x180038b1d  jle     short loc_180038B28
0x180038b1f  movzx   ebx, ax
0x180038b22  or      ebx, 80070000h
0x180038b28  test    ebx, ebx
0x180038b2a  jns     short loc_180038B38
0x180038b2c  lea     rdx, aLookupaccounts_2; "LookupAccountSid failed: 0x%x in %s"
0x180038b33  jmp     loc_180038BDC
0x180038b38  mov     edx, [rbp+cchName]
0x180038b3b  mov     ecx, 40h ; '@'; uFlags
0x180038b40  add     rdx, rdx; uBytes
0x180038b43  call    cs:__imp_LocalAlloc
0x180038b49  mov     [rdi], rax
0x180038b4c  test    rax, rax
0x180038b4f  jnz     short loc_180038B63
0x180038b51  mov     r8d, 8007000Eh
0x180038b57  lea     rdx, aLocalallocPsza; "LocalAlloc pszAccountName failed: 0x%x "...
0x180038b5e  mov     ebx, r8d
0x180038b61  jmp     short loc_180038BDF
0x180038b63  mov     edx, [rbp+arg_0]
0x180038b66  mov     ecx, 40h ; '@'; uFlags
0x180038b6b  add     rdx, rdx; uBytes
0x180038b6e  call    cs:__imp_LocalAlloc
0x180038b74  mov     [rsi], rax
0x180038b77  test    rax, rax
0x180038b7a  jnz     short loc_180038B8E
0x180038b7c  mov     r8d, 8007000Eh
0x180038b82  lea     rdx, aLocalallocPsza_0; "LocalAlloc pszAccountDomain failed: 0x%"...
0x180038b89  mov     ebx, r8d
0x180038b8c  jmp     short loc_180038BDF
0x180038b8e  mov     r8, [rdi]; Name
0x180038b91  lea     rcx, [rbp+arg_18]
0x180038b95  mov     rdx, [rbp+Sid]; Sid
0x180038b99  lea     r9, [rbp+cchName]; cchName
0x180038b9d  mov     [rsp+50h+peUse], rcx; peUse
0x180038ba2  lea     rcx, [rbp+arg_0]
0x180038ba6  mov     [rsp+50h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180038bab  xor     ecx, ecx; lpSystemName
0x180038bad  mov     [rsp+50h+ReferencedDomainName], rax; ReferencedDomainName
0x180038bb2  call    cs:__imp_LookupAccountSidW
0x180038bb8  test    eax, eax
0x180038bba  jnz     short loc_180038BF0
0x180038bbc  call    cs:__imp_GetLastError
0x180038bc2  mov     ebx, eax
0x180038bc4  test    eax, eax
0x180038bc6  jle     short loc_180038BD1
0x180038bc8  movzx   ebx, ax
0x180038bcb  or      ebx, 80070000h
0x180038bd1  test    ebx, ebx
0x180038bd3  jns     short loc_180038BF0
0x180038bd5  lea     rdx, aLookupaccounts_1; "LookupAccountSid final failed: 0x%x in "...
0x180038bdc  mov     r8d, ebx
0x180038bdf  lea     r9, aCtssdfarmrpcCo; "CTSSDFarmRpc::ConvertSidToAccountName"
0x180038be6  mov     ecx, 8; int
0x180038beb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180038bf0  mov     rcx, [rbp+Sid]; hMem
0x180038bf4  test    rcx, rcx
0x180038bf7  jz      short loc_180038BFF
0x180038bf9  call    cs:__imp_LocalFree
0x180038bff  test    ebx, ebx
0x180038c01  jns     short loc_180038C2D
0x180038c03  mov     rcx, [rdi]; hMem
0x180038c06  test    rcx, rcx
0x180038c09  jz      short loc_180038C18
0x180038c0b  call    cs:__imp_LocalFree
0x180038c11  mov     qword ptr [rdi], 0
0x180038c18  mov     rcx, [rsi]; hMem
0x180038c1b  test    rcx, rcx
0x180038c1e  jz      short loc_180038C2D
0x180038c20  call    cs:__imp_LocalFree
0x180038c26  mov     qword ptr [rsi], 0
0x180038c2d  mov     eax, ebx
0x180038c2f  mov     rbx, [rsp+50h+arg_8]
0x180038c34  add     rsp, 50h
0x180038c38  pop     rdi
0x180038c39  pop     rsi
0x180038c3a  pop     rbp
0x180038c3b  retn
```
