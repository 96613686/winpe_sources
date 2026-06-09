# EfspLocateInformationFromLogonSession(void *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x180037784`
- end: `0x1800379e8`
- name: `?EfspLocateInformationFromLogonSession@@YAJPEAXPEAU_UNICODE_STRING@@1@Z`
- size: `612`
- prototype: `__int64 __fastcall(PSID Sid, PUNICODE_STRING DestinationString, PUNICODE_STRING)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003818c`

## callees

- `0x1800102f0`
- `0x180010bf0`
- `0x1800124d8`
- `0x180037784`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003794c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003794c`
- `ntdll!RtlInitUnicodeString` at `0x1800379d4`
- `ntdll!RtlInitUnicodeString` at `0x1800379e0`
- `ntdll!RtlInitUnicodeString` at `0x1800379d4`
- `ntdll!RtlInitUnicodeString` at `0x1800379e0`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800377d3`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003793e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800377d3`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003793e`

## pseudocode

```c
__int64 __fastcall EfspLocateInformationFromLogonSession(
        PSID Sid,
        PUNICODE_STRING DestinationString,
        PUNICODE_STRING a3)
{
  unsigned int v3; // r15d
  DWORD LastError; // edi
  WCHAR *v8; // r14
  WCHAR *v9; // rsi
  DWORD v10; // r8d
  WCHAR *v11; // rax
  char cchReferencedDomainName; // [rsp+20h] [rbp-28h]
  unsigned int v14[2]; // [rsp+30h] [rbp-18h] BYREF
  DWORD v15; // [rsp+38h] [rbp-10h] BYREF
  enum _SID_NAME_USE peUse[3]; // [rsp+3Ch] [rbp-Ch] BYREF
  DWORD cchName; // [rsp+A8h] [rbp+60h] BYREF

  v3 = 0;
  v14[0] = 0;
  cchName = 0;
  v14[1] = 0;
  v15 = 0;
  peUse[0] = 0;
  LookupAccountSidLocalW(Sid, 0, &cchName, 0, &v15, peUse);
  LastError = GetLastError();
  if ( LastError != 122 )
    goto LABEL_16;
  if ( (unsigned int)ULongLongToULong(2LL * cchName, v14) )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, cchName, 1, 94);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, 534, 1, 95);
    return (unsigned int)-1073741823;
  }
  v8 = (WCHAR *)wil::details::heap_allocator::allocate(v14[0]);
  if ( !v8 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, v14[0], 1, 101);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, 8, 1, 102);
    return (unsigned int)-1073741823;
  }
  if ( (unsigned int)ULongLongToULong(2LL * v15, &v14[1]) )
  {
    v9 = 0;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, cchName, 1, 108);
    LastError = 534;
    cchReferencedDomainName = 109;
  }
  else
  {
    v11 = (WCHAR *)wil::details::heap_allocator::allocate(v14[1]);
    v9 = v11;
    if ( v11 )
    {
      if ( LookupAccountSidLocalW(Sid, v8, &cchName, v11, &v15, peUse) )
      {
        RtlInitUnicodeString(DestinationString, v8);
        RtlInitUnicodeString(a3, v9);
        return v3;
      }
      LastError = GetLastError();
      v10 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 1, 129);
      cchReferencedDomainName = -127;
      goto LABEL_14;
    }
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, v14[1], 1, 115);
    LastError = 8;
    cchReferencedDomainName = 116;
  }
  v10 = LastError;
LABEL_14:
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v10, 1, cchReferencedDomainName);
  EfsFreeHeap(v8);
  if ( v9 )
    EfsFreeHeap(v9);
LABEL_16:
  if ( LastError )
    return (unsigned int)-1073741823;
  return v3;
}

```

## disassembly

```asm
0x180037784  push    rbp
0x180037786  push    rbx
0x180037787  push    rsi
0x180037788  push    rdi
0x180037789  push    r12
0x18003778b  push    r13
0x18003778d  push    r14
0x18003778f  push    r15
0x180037791  mov     rbp, rsp
0x180037794  sub     rsp, 48h
0x180037798  xor     r15d, r15d
0x18003779b  lea     rax, [rbp+var_C]
0x18003779f  mov     [rsp+48h+peUse], rax; peUse
0x1800377a4  mov     r12, r8
0x1800377a7  lea     rax, [rbp+var_10]
0x1800377ab  mov     [rbp+var_18], r15d
0x1800377af  mov     r13, rdx
0x1800377b2  mov     [rsp+48h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800377b7  xor     r9d, r9d; ReferencedDomainName
0x1800377ba  mov     [rbp+cchName], r15d
0x1800377be  lea     r8, [rbp+cchName]; cchName
0x1800377c2  mov     [rbp+var_18+4], r15d
0x1800377c6  xor     edx, edx; Name
0x1800377c8  mov     [rbp+var_10], r15d
0x1800377cc  mov     rbx, rcx
0x1800377cf  mov     [rbp+var_C], r15d
0x1800377d3  call    cs:__imp_LookupAccountSidLocalW
0x1800377d9  call    cs:__imp_GetLastError
0x1800377df  mov     edi, eax
0x1800377e1  cmp     eax, 7Ah ; 'z'
0x1800377e4  jnz     loc_1800379B0
0x1800377ea  mov     ecx, [rbp+cchName]
0x1800377ed  lea     rdx, [rbp+var_18]; unsigned int *
0x1800377f1  add     rcx, rcx; unsigned __int64
0x1800377f4  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800377f9  test    eax, eax
0x1800377fb  jz      short loc_18003784B
0x1800377fd  mov     r8d, [rbp+cchName]
0x180037801  lea     ebx, [rdi-79h]
0x180037804  mov     rcx, cs:g_hPublisher
0x18003780b  lea     rdx, EFS_API_ERROR
0x180037812  mov     r9d, ebx
0x180037815  mov     dword ptr [rsp+48h+cchReferencedDomainName], 0C5Eh
0x18003781d  call    fnEfsLogTrace1
0x180037822  mov     r8d, 216h
0x180037828  mov     dword ptr [rsp+48h+cchReferencedDomainName], 0C5Fh
0x180037830  mov     rcx, cs:g_hPublisher
0x180037837  lea     rdx, EFS_TRACE_ERROR
0x18003783e  mov     r9d, ebx
0x180037841  call    fnEfsLogTrace1
0x180037846  jmp     loc_1800379B4
0x18003784b  mov     ecx, [rbp+var_18]; unsigned __int64
0x18003784e  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180037853  mov     r14, rax
0x180037856  test    rax, rax
0x180037859  jnz     short loc_18003788E
0x18003785b  mov     r8d, [rbp+var_18]
0x18003785f  lea     ebx, [rax+1]
0x180037862  mov     rcx, cs:g_hPublisher
0x180037869  lea     rdx, EFS_ERROR_MEMORY
0x180037870  mov     r9d, ebx
0x180037873  mov     dword ptr [rsp+48h+cchReferencedDomainName], 0C65h
0x18003787b  call    fnEfsLogTrace1
0x180037880  lea     r8d, [r14+8]
0x180037884  mov     dword ptr [rsp+48h+cchReferencedDomainName], 0C66h
0x18003788c  jmp     short loc_180037830
0x18003788e  mov     ecx, [rbp+var_10]
0x180037891  lea     rdx, [rbp+var_18+4]; unsigned int *
0x180037895  add     rcx, rcx; unsigned __int64
0x180037898  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18003789d  test    eax, eax
0x18003789f  jz      short loc_1800378DD
0x1800378a1  mov     r8d, [rbp+cchName]
0x1800378a5  lea     rdx, EFS_API_ERROR
0x1800378ac  mov     rcx, cs:g_hPublisher
0x1800378b3  xor     esi, esi
0x1800378b5  mov     dword ptr [rsp+48h+cchReferencedDomainName], 0C6Ch
0x1800378bd  lea     ebx, [rsi+1]
0x1800378c0  mov     r9d, ebx
0x1800378c3  call    fnEfsLogTrace1
0x1800378c8  mov     edi, 216h
0x1800378cd  mov     dword ptr [rsp+48h+cchReferencedDomainName], 0C6Dh
0x1800378d5  mov     r8d, edi
0x1800378d8  jmp     loc_180037985
0x1800378dd  mov     ecx, [rbp+var_18+4]; unsigned __int64
0x1800378e0  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x1800378e5  mov     rsi, rax
0x1800378e8  test    rax, rax
0x1800378eb  jnz     short loc_18003791F
0x1800378ed  mov     r8d, [rbp+var_18+4]
0x1800378f1  lea     ebx, [rax+1]
0x1800378f4  mov     rcx, cs:g_hPublisher
0x1800378fb  lea     rdx, EFS_ERROR_MEMORY
0x180037902  mov     r9d, ebx
0x180037905  mov     dword ptr [rsp+48h+cchReferencedDomainName], 0C73h
0x18003790d  call    fnEfsLogTrace1
0x180037912  lea     edi, [rsi+8]
0x180037915  mov     dword ptr [rsp+48h+cchReferencedDomainName], 0C74h
0x18003791d  jmp     short loc_1800378D5
0x18003791f  lea     rax, [rbp+var_C]
0x180037923  mov     r9, rsi; ReferencedDomainName
0x180037926  mov     [rsp+48h+peUse], rax; peUse
0x18003792b  lea     r8, [rbp+cchName]; cchName
0x18003792f  lea     rax, [rbp+var_10]
0x180037933  mov     rdx, r14; Name
0x180037936  mov     rcx, rbx; Sid
0x180037939  mov     [rsp+48h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003793e  call    cs:__imp_LookupAccountSidLocalW
0x180037944  test    eax, eax
0x180037946  jnz     loc_1800379CE
0x18003794c  call    cs:__imp_GetLastError
0x180037952  mov     rcx, cs:g_hPublisher
0x180037959  lea     rdx, EFS_API_ERROR
0x180037960  mov     ebx, 1
0x180037965  mov     r12d, 0C81h
0x18003796b  mov     r9d, ebx
0x18003796e  mov     dword ptr [rsp+48h+cchReferencedDomainName], r12d
0x180037973  mov     r8d, eax
0x180037976  mov     edi, eax
0x180037978  call    fnEfsLogTrace1
0x18003797d  mov     r8d, eax
0x180037980  mov     dword ptr [rsp+48h+cchReferencedDomainName], r12d
0x180037985  mov     rcx, cs:g_hPublisher
0x18003798c  lea     rdx, EFS_TRACE_ERROR
0x180037993  mov     r9d, ebx
0x180037996  call    fnEfsLogTrace1
0x18003799b  mov     rcx, r14; lpMem
0x18003799e  call    EfsFreeHeap
0x1800379a3  test    rsi, rsi
0x1800379a6  jz      short loc_1800379B0
0x1800379a8  mov     rcx, rsi; lpMem
0x1800379ab  call    EfsFreeHeap
0x1800379b0  test    edi, edi
0x1800379b2  jz      short loc_1800379BA
0x1800379b4  mov     r15d, 0C0000001h
0x1800379ba  mov     eax, r15d
0x1800379bd  add     rsp, 48h
0x1800379c1  pop     r15
0x1800379c3  pop     r14
0x1800379c5  pop     r13
0x1800379c7  pop     r12
0x1800379c9  pop     rdi
0x1800379ca  pop     rsi
0x1800379cb  pop     rbx
0x1800379cc  pop     rbp
0x1800379cd  retn
0x1800379ce  mov     rdx, r14; SourceString
0x1800379d1  mov     rcx, r13; DestinationString
0x1800379d4  call    cs:__imp_RtlInitUnicodeString
0x1800379da  mov     rdx, rsi; SourceString
0x1800379dd  mov     rcx, r12; DestinationString
0x1800379e0  call    cs:__imp_RtlInitUnicodeString
0x1800379e6  jmp     short loc_1800379BA
```
