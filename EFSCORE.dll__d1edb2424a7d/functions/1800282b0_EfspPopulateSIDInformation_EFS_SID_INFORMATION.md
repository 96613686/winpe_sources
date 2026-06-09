# EfspPopulateSIDInformation(_EFS_SID_INFORMATION *)

- ea: `0x1800282b0`
- end: `0x18002861a`
- name: `?EfspPopulateSIDInformation@@YAKPEAU_EFS_SID_INFORMATION@@@Z`
- size: `874`
- prototype: `unsigned int __fastcall(struct _EFS_SID_INFORMATION *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180028d3c`

## callees

- `0x1800102f0`
- `0x180010bf0`
- `0x1800124d8`
- `0x1800282b0`
- `0x180063698`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800283ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800283d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800283ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800283d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028558`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002839e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800283c9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002839e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800283c9`
- `ntdll!RtlInitUnicodeString` at `0x1800285f2`
- `ntdll!RtlInitUnicodeString` at `0x180028602`
- `ntdll!RtlInitUnicodeString` at `0x1800285f2`
- `ntdll!RtlInitUnicodeString` at `0x180028602`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180028406`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180028545`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180028406`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180028545`

## pseudocode

```c
__int64 __fastcall EfspPopulateSIDInformation(struct _EFS_SID_INFORMATION *a1)
{
  unsigned int v1; // ebx
  void *v2; // r15
  WCHAR *v3; // r14
  WCHAR *v4; // rsi
  void *v5; // r13
  int v6; // r12d
  int v7; // r8d
  __int64 v8; // rcx
  DWORD LastError; // eax
  char v10; // bl
  __int64 v11; // rcx
  WCHAR *v12; // rax
  __int64 v13; // rcx
  char cchReferencedDomainName; // [rsp+20h] [rbp-20h]
  unsigned int peUse[4]; // [rsp+30h] [rbp-10h] BYREF
  DWORD cchName; // [rsp+80h] [rbp+40h] BYREF
  int v18; // [rsp+84h] [rbp+44h]
  DWORD v19; // [rsp+88h] [rbp+48h] BYREF
  DWORD cbSid; // [rsp+90h] [rbp+50h] BYREF
  unsigned int v21; // [rsp+98h] [rbp+58h] BYREF

  v18 = HIDWORD(a1);
  v1 = 0;
  cbSid = 68;
  v21 = 0;
  cchName = 0;
  peUse[0] = 0;
  v19 = 0;
  peUse[1] = 0;
  v2 = wil::details::heap_allocator::allocate(0x44u);
  if ( !v2 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, 68, 15, 135);
    v1 = 8;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, 8, 15, 136);
    return v1;
  }
  v3 = 0;
  v4 = 0;
  v5 = wil::details::heap_allocator::allocate(0x44u);
  if ( !v5 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, 68, 15, 143);
    cchReferencedDomainName = -112;
LABEL_5:
    v6 = 8;
    v7 = 8;
LABEL_21:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v7, 15, cchReferencedDomainName);
    goto LABEL_22;
  }
  if ( !CreateWellKnownSid(WinAnonymousSid, 0, v2, &cbSid) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v8);
    LastError = GetLastError();
    v10 = -103;
    goto LABEL_20;
  }
  if ( !CreateWellKnownSid(WinInteractiveSid, 0, v5, &cbSid) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v11);
    LastError = GetLastError();
    v10 = -91;
    goto LABEL_20;
  }
  LookupAccountSidLocalW(v2, 0, &cchName, 0, &v19, (PSID_NAME_USE)&peUse[1]);
  if ( (unsigned int)ULongLongToULong(2LL * cchName, &v21) )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, cchName, 15, 183);
    v6 = 534;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, 534, 15, 184);
  }
  else
  {
    v3 = (WCHAR *)wil::details::heap_allocator::allocate(v21);
    if ( !v3 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, 68, 15, 190);
      cchReferencedDomainName = -65;
      goto LABEL_5;
    }
    if ( !(unsigned int)ULongLongToULong(2LL * v19, peUse) )
    {
      v12 = (WCHAR *)wil::details::heap_allocator::allocate(peUse[0]);
      v4 = v12;
      if ( !v12 )
      {
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, 68, 15, 204);
        cchReferencedDomainName = -51;
        goto LABEL_5;
      }
      if ( LookupAccountSidLocalW(v2, v3, &cchName, v12, &v19, (PSID_NAME_USE)&peUse[1]) )
      {
        EfsSidInfo = v2;
        *(&EfsSidInfo + 1) = v5;
        RtlInitUnicodeString(&DestinationString, v3);
        RtlInitUnicodeString(&stru_1801171A0, v4);
        return v1;
      }
      MicrosoftTelemetryAssertTriggeredNoArgs(v13);
      LastError = GetLastError();
      v10 = -37;
LABEL_20:
      v6 = LastError;
      v7 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 15, v10);
      cchReferencedDomainName = v10;
      goto LABEL_21;
    }
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, cchName, 15, 197);
    v6 = 534;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, 534, 15, 198);
  }
LABEL_22:
  v1 = v6;
  EfsFreeHeap(v2);
  if ( v5 )
    EfsFreeHeap(v5);
  if ( v3 )
    EfsFreeHeap(v3);
  if ( v4 )
    EfsFreeHeap(v4);
  return v1;
}

```

## disassembly

```asm
0x1800282b0  mov     qword ptr [rsp-38h+cchName], rcx
0x1800282b5  push    rbp
0x1800282b6  push    rbx
0x1800282b7  push    rsi
0x1800282b8  push    r12
0x1800282ba  push    r13
0x1800282bc  push    r14
0x1800282be  push    r15
0x1800282c0  mov     rbp, rsp
0x1800282c3  sub     rsp, 40h
0x1800282c7  xor     ebx, ebx
0x1800282c9  mov     r12d, 44h ; 'D'
0x1800282cf  mov     ecx, r12d; unsigned __int64
0x1800282d2  mov     [rbp+cbSid], r12d
0x1800282d6  mov     [rbp+arg_18], ebx
0x1800282d9  mov     [rbp+cchName], ebx
0x1800282dc  mov     [rbp+var_10], ebx
0x1800282df  mov     [rbp+arg_8], ebx
0x1800282e2  mov     [rbp+var_10+4], ebx
0x1800282e5  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x1800282ea  mov     r15, rax
0x1800282ed  test    rax, rax
0x1800282f0  jnz     short loc_180028342
0x1800282f2  mov     rcx, cs:g_hPublisher
0x1800282f9  lea     r9d, [r12-35h]
0x1800282fe  mov     r8d, r12d
0x180028301  mov     dword ptr [rsp+40h+cchReferencedDomainName], 287h
0x180028309  lea     rdx, EFS_ERROR_MEMORY
0x180028310  call    fnEfsLogTrace1
0x180028315  mov     rcx, cs:g_hPublisher
0x18002831c  lea     ebx, [r12-3Ch]
0x180028321  mov     r8d, ebx
0x180028324  mov     dword ptr [rsp+40h+cchReferencedDomainName], 288h
0x18002832c  lea     r9d, [r12-35h]
0x180028331  lea     rdx, EFS_TRACE_ERROR
0x180028338  call    fnEfsLogTrace1
0x18002833d  jmp     loc_180028608
0x180028342  mov     rcx, r12; unsigned __int64
0x180028345  mov     r14, rbx
0x180028348  mov     rsi, rbx
0x18002834b  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180028350  mov     r13, rax
0x180028353  test    rax, rax
0x180028356  jnz     short loc_180028392
0x180028358  mov     rcx, cs:g_hPublisher
0x18002835f  lea     r9d, [rax+0Fh]
0x180028363  mov     r8d, r12d
0x180028366  mov     dword ptr [rsp+40h+cchReferencedDomainName], 28Fh
0x18002836e  lea     rdx, EFS_ERROR_MEMORY
0x180028375  call    fnEfsLogTrace1
0x18002837a  mov     dword ptr [rsp+40h+cchReferencedDomainName], 290h
0x180028382  mov     ebx, 8
0x180028387  mov     r12d, ebx
0x18002838a  mov     r8d, ebx
0x18002838d  jmp     loc_18002858D
0x180028392  xor     edx, edx; DomainSid
0x180028394  lea     r9, [rbp+cbSid]; cbSid
0x180028398  mov     r8, r15; pSid
0x18002839b  lea     ecx, [rdx+0Dh]; WellKnownSidType
0x18002839e  call    cs:__imp_CreateWellKnownSid
0x1800283a4  test    eax, eax
0x1800283a6  jnz     short loc_1800283BD
0x1800283a8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "bResult != FALSE")
0x1800283ad  call    cs:__imp_GetLastError
0x1800283b3  mov     ebx, 299h
0x1800283b8  jmp     loc_180028563
0x1800283bd  xor     edx, edx; DomainSid
0x1800283bf  lea     r9, [rbp+cbSid]; cbSid
0x1800283c3  mov     r8, r13; pSid
0x1800283c6  lea     ecx, [rdx+0Bh]; WellKnownSidType
0x1800283c9  call    cs:__imp_CreateWellKnownSid
0x1800283cf  test    eax, eax
0x1800283d1  jnz     short loc_1800283E8
0x1800283d3  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "bResult != FALSE")
0x1800283d8  call    cs:__imp_GetLastError
0x1800283de  mov     ebx, 2A5h
0x1800283e3  jmp     loc_180028563
0x1800283e8  lea     rax, [rbp+var_10+4]
0x1800283ec  xor     r9d, r9d; ReferencedDomainName
0x1800283ef  mov     [rsp+40h+peUse], rax; peUse
0x1800283f4  lea     r8, [rbp+cchName]; cchName
0x1800283f8  lea     rax, [rbp+arg_8]
0x1800283fc  xor     edx, edx; Name
0x1800283fe  mov     rcx, r15; Sid
0x180028401  mov     [rsp+40h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180028406  call    cs:__imp_LookupAccountSidLocalW
0x18002840c  mov     ecx, [rbp+cchName]
0x18002840f  lea     rdx, [rbp+arg_18]; unsigned int *
0x180028413  add     rcx, rcx; unsigned __int64
0x180028416  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002841b  test    eax, eax
0x18002841d  jz      short loc_18002845A
0x18002841f  mov     r8d, [rbp+cchName]
0x180028423  lea     rdx, EFS_API_ERROR
0x18002842a  mov     rcx, cs:g_hPublisher
0x180028431  mov     r9d, 0Fh
0x180028437  mov     dword ptr [rsp+40h+cchReferencedDomainName], 2B7h
0x18002843f  call    fnEfsLogTrace1
0x180028444  mov     r8d, 216h
0x18002844a  mov     dword ptr [rsp+40h+cchReferencedDomainName], 2B8h
0x180028452  mov     r12d, r8d
0x180028455  jmp     loc_18002858D
0x18002845a  mov     ecx, [rbp+arg_18]; unsigned __int64
0x18002845d  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180028462  mov     r14, rax
0x180028465  test    rax, rax
0x180028468  jnz     short loc_180028499
0x18002846a  mov     rcx, cs:g_hPublisher
0x180028471  lea     r9d, [rax+0Fh]
0x180028475  mov     r8d, r12d
0x180028478  mov     dword ptr [rsp+40h+cchReferencedDomainName], 2BEh
0x180028480  lea     rdx, EFS_ERROR_MEMORY
0x180028487  call    fnEfsLogTrace1
0x18002848c  mov     dword ptr [rsp+40h+cchReferencedDomainName], 2BFh
0x180028494  jmp     loc_180028382
0x180028499  mov     ecx, [rbp+arg_8]
0x18002849c  lea     rdx, [rbp+var_10]; unsigned int *
0x1800284a0  add     rcx, rcx; unsigned __int64
0x1800284a3  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800284a8  test    eax, eax
0x1800284aa  jz      short loc_1800284E7
0x1800284ac  mov     r8d, [rbp+cchName]
0x1800284b0  lea     rdx, EFS_API_ERROR
0x1800284b7  mov     rcx, cs:g_hPublisher
0x1800284be  mov     r9d, 0Fh
0x1800284c4  mov     dword ptr [rsp+40h+cchReferencedDomainName], 2C5h
0x1800284cc  call    fnEfsLogTrace1
0x1800284d1  mov     r8d, 216h
0x1800284d7  mov     dword ptr [rsp+40h+cchReferencedDomainName], 2C6h
0x1800284df  mov     r12d, r8d
0x1800284e2  jmp     loc_18002858D
0x1800284e7  mov     ecx, [rbp+var_10]; unsigned __int64
0x1800284ea  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x1800284ef  mov     rsi, rax
0x1800284f2  test    rax, rax
0x1800284f5  jnz     short loc_180028526
0x1800284f7  mov     rcx, cs:g_hPublisher
0x1800284fe  lea     r9d, [rax+0Fh]
0x180028502  mov     r8d, r12d
0x180028505  mov     dword ptr [rsp+40h+cchReferencedDomainName], 2CCh
0x18002850d  lea     rdx, EFS_ERROR_MEMORY
0x180028514  call    fnEfsLogTrace1
0x180028519  mov     dword ptr [rsp+40h+cchReferencedDomainName], 2CDh
0x180028521  jmp     loc_180028382
0x180028526  lea     rax, [rbp+var_10+4]
0x18002852a  mov     r9, rsi; ReferencedDomainName
0x18002852d  mov     [rsp+40h+peUse], rax; peUse
0x180028532  lea     r8, [rbp+cchName]; cchName
0x180028536  lea     rax, [rbp+arg_8]
0x18002853a  mov     rdx, r14; Name
0x18002853d  mov     rcx, r15; Sid
0x180028540  mov     [rsp+40h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180028545  call    cs:__imp_LookupAccountSidLocalW
0x18002854b  test    eax, eax
0x18002854d  jnz     loc_1800285DA
0x180028553  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "bResult != FALSE")
0x180028558  call    cs:__imp_GetLastError
0x18002855e  mov     ebx, 2DBh
0x180028563  mov     rcx, cs:g_hPublisher
0x18002856a  lea     rdx, EFS_API_ERROR
0x180028571  mov     r9d, 0Fh
0x180028577  mov     dword ptr [rsp+40h+cchReferencedDomainName], ebx
0x18002857b  mov     r8d, eax
0x18002857e  mov     r12d, eax
0x180028581  call    fnEfsLogTrace1
0x180028586  mov     r8d, eax
0x180028589  mov     dword ptr [rsp+40h+cchReferencedDomainName], ebx
0x18002858d  mov     rcx, cs:g_hPublisher
0x180028594  lea     rdx, EFS_TRACE_ERROR
0x18002859b  mov     r9d, 0Fh
0x1800285a1  call    fnEfsLogTrace1
0x1800285a6  mov     rcx, r15; lpMem
0x1800285a9  mov     ebx, r12d
0x1800285ac  call    EfsFreeHeap
0x1800285b1  test    r13, r13
0x1800285b4  jz      short loc_1800285BE
0x1800285b6  mov     rcx, r13; lpMem
0x1800285b9  call    EfsFreeHeap
0x1800285be  test    r14, r14
0x1800285c1  jz      short loc_1800285CB
0x1800285c3  mov     rcx, r14; lpMem
0x1800285c6  call    EfsFreeHeap
0x1800285cb  test    rsi, rsi
0x1800285ce  jz      short loc_180028608
0x1800285d0  mov     rcx, rsi; lpMem
0x1800285d3  call    EfsFreeHeap
0x1800285d8  jmp     short loc_180028608
0x1800285da  mov     rdx, r14; SourceString
0x1800285dd  mov     qword ptr cs:?EfsSidInfo@@3U_EFS_SID_INFORMATION@@A, r15; _EFS_SID_INFORMATION EfsSidInfo
0x1800285e4  lea     rcx, DestinationString; DestinationString
0x1800285eb  mov     qword ptr cs:?EfsSidInfo@@3U_EFS_SID_INFORMATION@@A+8, r13; _EFS_SID_INFORMATION EfsSidInfo
0x1800285f2  call    cs:__imp_RtlInitUnicodeString
0x1800285f8  mov     rdx, rsi; SourceString
0x1800285fb  lea     rcx, stru_1801171A0; DestinationString
0x180028602  call    cs:__imp_RtlInitUnicodeString
0x180028608  mov     eax, ebx
0x18002860a  add     rsp, 40h
0x18002860e  pop     r15
0x180028610  pop     r14
0x180028612  pop     r13
0x180028614  pop     r12
0x180028616  pop     rsi
0x180028617  pop     rbx
0x180028618  pop     rbp
0x180028619  retn
```
