# BfeFwTriggerEntryInitParams

- ea: `0x180043b5c`
- end: `0x180043da2`
- name: `BfeFwTriggerEntryInitParams`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180041ee0`

## callees

- `0x18000e000`
- `0x18001236c`
- `0x180012b54`
- `0x180018b74`
- `0x180043b5c`
- `0x180043da8`
- `0x180058b30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043bc1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043c08`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043c22`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043bc1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043c08`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043c22`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180043ba5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180043ba5`
- `ntdll!RtlCreateServiceSid` at `0x180043cfd`
- `ntdll!RtlCreateServiceSid` at `0x180043cfd`
- `ntdll!RtlInitUnicodeString` at `0x180043ceb`
- `ntdll!RtlInitUnicodeString` at `0x180043ceb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043cc0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043cc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043d68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043d68`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180043ca7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180043ca7`

## string_xrefs

- `0x180043d0a`: `RtlCreateServiceSid`

## pseudocode

```c
__int64 __fastcall BfeFwTriggerEntryInitParams(__int64 a1)
{
  wchar_t *v1; // r14
  __int64 v2; // r15
  __int64 NtPathName; // rbx
  int v5; // r12d
  __int16 v6; // ax
  wchar_t *v7; // rcx
  char v8; // si
  __int16 v9; // r13
  int v10; // eax
  __int64 v11; // rcx
  wchar_t *v12; // rcx
  wchar_t *v13; // r14
  __int64 v14; // rax
  wchar_t *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // r8
  const char *v18; // rdx
  __int64 v19; // rax
  NTSTATUS v20; // eax
  __int64 v22; // [rsp+20h] [rbp-48h] BYREF
  wchar_t *EndPtr; // [rsp+28h] [rbp-40h] BYREF
  PSID Sid; // [rsp+30h] [rbp-38h] BYREF
  ULONG ServiceSidLength; // [rsp+38h] [rbp-30h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-28h] BYREF

  v1 = *(wchar_t **)(a1 + 40);
  v2 = *(unsigned int *)(a1 + 48);
  NtPathName = 0;
  v22 = 0;
  Sid = 0;
  v5 = 0;
  EndPtr = v1;
  v6 = wcstol(v1, &EndPtr, 10);
  v7 = EndPtr;
  v8 = 6;
  v9 = v6;
  if ( *EndPtr )
  {
    v10 = _o__wcsicmp(EndPtr, L"RPC");
    v7 = EndPtr;
    if ( !v10 )
    {
      v7 = EndPtr + 3;
      v5 = 1;
      EndPtr += 3;
    }
    if ( *v7 )
      goto LABEL_5;
  }
  EndPtr = v7 + 1;
  if ( (unsigned int)_o__wcsicmp(v7 + 1, L"TCP") )
  {
    if ( (unsigned int)_o__wcsicmp(EndPtr, L"UDP") )
    {
      v19 = WfpReportSysErrorAsWinError(v11, "BfeFwTriggerEntryInitParams", 31);
      goto LABEL_26;
    }
    v8 = 17;
    v7 = EndPtr + 3;
  }
  else
  {
    v7 = EndPtr + 3;
  }
  EndPtr = v7;
  if ( !*v7 )
  {
    v12 = v7 + 1;
    v13 = (wchar_t *)((char *)v1 + v2);
    EndPtr = v12;
    if ( v12 < v13 && *v12 )
    {
      NtPathName = BfeGetNtPathName(v12, &v22);
      if ( NtPathName )
        goto LABEL_27;
      v14 = -1;
      do
        ++v14;
      while ( EndPtr[v14] );
      v15 = &EndPtr[v14 + 1];
      EndPtr = v15;
      if ( v15 < v13 && *v15 && !ConvertStringSidToSidW(v15, &Sid) )
      {
        ServiceSidLength = 68;
        DestinationString = 0;
        Sid = LocalAlloc(0, 0x44u);
        if ( !Sid )
        {
          v17 = 3221225495LL;
          v18 = "LocalAlloc";
LABEL_21:
          v19 = WfpReportSysErrorAsNtStatus(v16, v18, v17);
LABEL_26:
          NtPathName = v19;
LABEL_27:
          if ( v22 )
            WfpMemFree(&v22);
          goto LABEL_29;
        }
        RtlInitUnicodeString(&DestinationString, EndPtr);
        v20 = RtlCreateServiceSid(&DestinationString, Sid, &ServiceSidLength);
        if ( v20 < 0 )
        {
          v17 = (unsigned int)v20;
          v18 = "RtlCreateServiceSid";
          goto LABEL_21;
        }
      }
    }
    *(_QWORD *)(a1 + 128) = v22;
    *(_QWORD *)(a1 + 136) = Sid;
    *(_DWORD *)(a1 + 120) = v5;
    *(_WORD *)(a1 + 124) = v9;
    *(_BYTE *)(a1 + 126) = v8;
    return NtPathName;
  }
LABEL_5:
  NtPathName = WfpReportSysErrorAsWinError(v7, "BfeFwTriggerEntryInitParams", 31);
LABEL_29:
  if ( Sid )
    LocalFree(Sid);
  if ( NtPathName )
    WfpReportError(NtPathName, "BfeFwTriggerEntryInitParams");
  return NtPathName;
}

```

## disassembly

```asm
0x180043b5c  push    rbp
0x180043b5e  push    rbx
0x180043b5f  push    rsi
0x180043b60  push    rdi
0x180043b61  push    r12
0x180043b63  push    r13
0x180043b65  push    r14
0x180043b67  push    r15
0x180043b69  mov     rbp, rsp
0x180043b6c  sub     rsp, 68h
0x180043b70  mov     rax, cs:__security_cookie
0x180043b77  xor     rax, rsp
0x180043b7a  mov     [rbp+var_18], rax
0x180043b7e  mov     r14, [rcx+28h]
0x180043b82  lea     rdx, [rbp+EndPtr]; EndPtr
0x180043b86  mov     r15d, [rcx+30h]
0x180043b8a  xor     ebx, ebx
0x180043b8c  mov     rdi, rcx
0x180043b8f  mov     [rbp+var_48], rbx
0x180043b93  mov     rcx, r14; String
0x180043b96  mov     [rbp+Sid], rbx
0x180043b9a  mov     r12d, ebx
0x180043b9d  mov     [rbp+EndPtr], r14
0x180043ba1  lea     r8d, [rbx+0Ah]; Radix
0x180043ba5  call    cs:__imp_wcstol
0x180043bab  mov     rcx, [rbp+EndPtr]
0x180043baf  lea     esi, [rbx+6]
0x180043bb2  mov     r13d, eax
0x180043bb5  cmp     [rcx], bx
0x180043bb8  jz      short loc_180043BF9
0x180043bba  lea     rdx, aRpc; "RPC"
0x180043bc1  call    cs:__imp__o__wcsicmp
0x180043bc7  mov     rcx, [rbp+EndPtr]
0x180043bcb  test    eax, eax
0x180043bcd  jnz     short loc_180043BDA
0x180043bcf  add     rcx, rsi
0x180043bd2  lea     r12d, [rbx+1]
0x180043bd6  mov     [rbp+EndPtr], rcx
0x180043bda  cmp     [rcx], bx
0x180043bdd  jz      short loc_180043BF9
0x180043bdf  mov     r8d, 1Fh
0x180043be5  lea     rdx, aBfefwtriggeren_0; "BfeFwTriggerEntryInitParams"
0x180043bec  call    WfpReportSysErrorAsWinError
0x180043bf1  mov     rbx, rax
0x180043bf4  jmp     loc_180043D5F
0x180043bf9  add     rcx, 2
0x180043bfd  lea     rdx, aTcp; "TCP"
0x180043c04  mov     [rbp+EndPtr], rcx
0x180043c08  call    cs:__imp__o__wcsicmp
0x180043c0e  mov     rcx, [rbp+EndPtr]
0x180043c12  test    eax, eax
0x180043c14  jnz     short loc_180043C1B
0x180043c16  add     rcx, rsi
0x180043c19  jmp     short loc_180043C3B
0x180043c1b  lea     rdx, aUdp; "UDP"
0x180043c22  call    cs:__imp__o__wcsicmp
0x180043c28  test    eax, eax
0x180043c2a  jnz     loc_180043D38
0x180043c30  mov     rcx, [rbp+EndPtr]
0x180043c34  mov     sil, 11h
0x180043c37  add     rcx, 6
0x180043c3b  mov     [rbp+EndPtr], rcx
0x180043c3f  cmp     [rcx], bx
0x180043c42  jnz     short loc_180043BDF
0x180043c44  add     rcx, 2; lpSrc
0x180043c48  add     r14, r15
0x180043c4b  mov     [rbp+EndPtr], rcx
0x180043c4f  cmp     rcx, r14
0x180043c52  jnb     loc_180043D13
0x180043c58  xor     r15d, r15d
0x180043c5b  cmp     [rcx], r15w
0x180043c5f  jz      loc_180043D13
0x180043c65  lea     rdx, [rbp+var_48]
0x180043c69  call    BfeGetNtPathName
0x180043c6e  mov     rbx, rax
0x180043c71  test    rax, rax
0x180043c74  jnz     loc_180043D50
0x180043c7a  mov     rcx, [rbp+EndPtr]
0x180043c7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043c82  inc     rax
0x180043c85  cmp     [rcx+rax*2], r15w
0x180043c8a  jnz     short loc_180043C82
0x180043c8c  lea     rcx, [rcx+rax*2]
0x180043c90  add     rcx, 2; StringSid
0x180043c94  mov     [rbp+EndPtr], rcx
0x180043c98  cmp     rcx, r14
0x180043c9b  jnb     short loc_180043D13
0x180043c9d  cmp     [rcx], r15w
0x180043ca1  jz      short loc_180043D13
0x180043ca3  lea     rdx, [rbp+Sid]; Sid
0x180043ca7  call    cs:__imp_ConvertStringSidToSidW
0x180043cad  test    eax, eax
0x180043caf  jnz     short loc_180043D13
0x180043cb1  xorps   xmm0, xmm0
0x180043cb4  lea     edx, [rax+44h]; uBytes
0x180043cb7  xor     ecx, ecx; uFlags
0x180043cb9  mov     [rbp+ServiceSidLength], edx
0x180043cbc  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180043cc0  call    cs:__imp_LocalAlloc
0x180043cc6  mov     [rbp+Sid], rax
0x180043cca  test    rax, rax
0x180043ccd  jnz     short loc_180043CE3
0x180043ccf  mov     r8d, 0C0000017h
0x180043cd5  lea     rdx, aLocalalloc; "LocalAlloc"
0x180043cdc  call    WfpReportSysErrorAsNtStatus
0x180043ce1  jmp     short loc_180043D4D
0x180043ce3  mov     rdx, [rbp+EndPtr]; SourceString
0x180043ce7  lea     rcx, [rbp+DestinationString]; DestinationString
0x180043ceb  call    cs:__imp_RtlInitUnicodeString
0x180043cf1  mov     rdx, [rbp+Sid]; ServiceSid
0x180043cf5  lea     r8, [rbp+ServiceSidLength]; ServiceSidLength
0x180043cf9  lea     rcx, [rbp+DestinationString]; ServiceName
0x180043cfd  call    cs:__imp_RtlCreateServiceSid
0x180043d03  test    eax, eax
0x180043d05  jns     short loc_180043D13
0x180043d07  mov     r8d, eax
0x180043d0a  lea     rdx, aRtlcreateservi; "RtlCreateServiceSid"
0x180043d11  jmp     short loc_180043CDC
0x180043d13  mov     rax, [rbp+var_48]
0x180043d17  mov     [rdi+80h], rax
0x180043d1e  mov     rax, [rbp+Sid]
0x180043d22  mov     [rdi+88h], rax
0x180043d29  mov     [rdi+78h], r12d
0x180043d2d  mov     [rdi+7Ch], r13w
0x180043d32  mov     [rdi+7Eh], sil
0x180043d36  jmp     short loc_180043D82
0x180043d38  mov     r8d, 1Fh
0x180043d3e  lea     rdx, aBfefwtriggeren_0; "BfeFwTriggerEntryInitParams"
0x180043d45  call    WfpReportSysErrorAsWinError
0x180043d4a  xor     r15d, r15d
0x180043d4d  mov     rbx, rax
0x180043d50  cmp     [rbp+var_48], r15
0x180043d54  jz      short loc_180043D5F
0x180043d56  lea     rcx, [rbp+var_48]
0x180043d5a  call    WfpMemFree
0x180043d5f  mov     rcx, [rbp+Sid]; hMem
0x180043d63  test    rcx, rcx
0x180043d66  jz      short loc_180043D6E
0x180043d68  call    cs:__imp_LocalFree
0x180043d6e  test    rbx, rbx
0x180043d71  jz      short loc_180043D82
0x180043d73  lea     rdx, aBfefwtriggeren_0; "BfeFwTriggerEntryInitParams"
0x180043d7a  mov     rcx, rbx
0x180043d7d  call    WfpReportError
0x180043d82  mov     rax, rbx
0x180043d85  mov     rcx, [rbp+var_18]
0x180043d89  xor     rcx, rsp; StackCookie
0x180043d8c  call    __security_check_cookie
0x180043d91  add     rsp, 68h
0x180043d95  pop     r15
0x180043d97  pop     r14
0x180043d99  pop     r13
0x180043d9b  pop     r12
0x180043d9d  pop     rdi
0x180043d9e  pop     rsi
0x180043d9f  pop     rbx
0x180043da0  pop     rbp
0x180043da1  retn
```
