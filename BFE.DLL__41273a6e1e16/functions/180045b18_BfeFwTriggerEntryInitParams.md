# BfeFwTriggerEntryInitParams

- ea: `0x180045b18`
- end: `0x180045d9d`
- name: `BfeFwTriggerEntryInitParams`
- size: `645`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180043168`

## callees

- `0x18000e7e0`
- `0x180012d8c`
- `0x1800135ac`
- `0x1800197d0`
- `0x180045b18`
- `0x180045da4`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b83`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045bd0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045bf0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b83`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045bd0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045bf0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180045b61`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180045b61`
- `ntdll!RtlCreateServiceSid` at `0x180045ceb`
- `ntdll!RtlCreateServiceSid` at `0x180045ceb`
- `ntdll!RtlInitUnicodeString` at `0x180045cd3`
- `ntdll!RtlInitUnicodeString` at `0x180045cd3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045ca2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045ca2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045d5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045d5c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180045c83`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180045c83`

## string_xrefs

- `0x180045cfe`: `RtlCreateServiceSid`

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
  __int64 v22; // [rsp+20h] [rbp-48h]
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
      NtPathName = BfeGetNtPathName(v12);
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
          goto LABEL_27;
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
LABEL_27:
  if ( Sid )
    LocalFree(Sid);
  if ( NtPathName )
    WfpReportError(NtPathName, "BfeFwTriggerEntryInitParams");
  return NtPathName;
}

```

## disassembly

```asm
0x180045b18  push    rbp
0x180045b1a  push    rbx
0x180045b1b  push    rsi
0x180045b1c  push    rdi
0x180045b1d  push    r12
0x180045b1f  push    r13
0x180045b21  push    r14
0x180045b23  push    r15
0x180045b25  mov     rbp, rsp
0x180045b28  sub     rsp, 68h
0x180045b2c  mov     rax, cs:__security_cookie
0x180045b33  xor     rax, rsp
0x180045b36  mov     [rbp+var_18], rax
0x180045b3a  mov     r14, [rcx+28h]
0x180045b3e  lea     rdx, [rbp+EndPtr]; EndPtr
0x180045b42  mov     r15d, [rcx+30h]
0x180045b46  xor     ebx, ebx
0x180045b48  mov     rdi, rcx
0x180045b4b  mov     [rbp+var_48], rbx
0x180045b4f  mov     rcx, r14; String
0x180045b52  mov     [rbp+Sid], rbx
0x180045b56  mov     r12d, ebx
0x180045b59  mov     [rbp+EndPtr], r14
0x180045b5d  lea     r8d, [rbx+0Ah]; Radix
0x180045b61  call    cs:__imp_wcstol
0x180045b68  nop     dword ptr [rax+rax+00h]
0x180045b6d  mov     rcx, [rbp+EndPtr]
0x180045b71  lea     esi, [rbx+6]
0x180045b74  mov     r13d, eax
0x180045b77  cmp     [rcx], bx
0x180045b7a  jz      short loc_180045BC1
0x180045b7c  lea     rdx, aRpc; "RPC"
0x180045b83  call    cs:__imp__o__wcsicmp
0x180045b8a  nop     dword ptr [rax+rax+00h]
0x180045b8f  mov     rcx, [rbp+EndPtr]
0x180045b93  test    eax, eax
0x180045b95  jnz     short loc_180045BA2
0x180045b97  add     rcx, rsi
0x180045b9a  lea     r12d, [rbx+1]
0x180045b9e  mov     [rbp+EndPtr], rcx
0x180045ba2  cmp     [rcx], bx
0x180045ba5  jz      short loc_180045BC1
0x180045ba7  mov     r8d, 1Fh
0x180045bad  lea     rdx, aBfefwtriggeren_0; "BfeFwTriggerEntryInitParams"
0x180045bb4  call    WfpReportSysErrorAsWinError
0x180045bb9  mov     rbx, rax
0x180045bbc  jmp     loc_180045D53
0x180045bc1  add     rcx, 2
0x180045bc5  lea     rdx, aTcp; "TCP"
0x180045bcc  mov     [rbp+EndPtr], rcx
0x180045bd0  call    cs:__imp__o__wcsicmp
0x180045bd7  nop     dword ptr [rax+rax+00h]
0x180045bdc  mov     rcx, [rbp+EndPtr]
0x180045be0  test    eax, eax
0x180045be2  jnz     short loc_180045BE9
0x180045be4  add     rcx, rsi
0x180045be7  jmp     short loc_180045C0F
0x180045be9  lea     rdx, aUdp; "UDP"
0x180045bf0  call    cs:__imp__o__wcsicmp
0x180045bf7  nop     dword ptr [rax+rax+00h]
0x180045bfc  test    eax, eax
0x180045bfe  jnz     loc_180045D2C
0x180045c04  mov     rcx, [rbp+EndPtr]
0x180045c08  mov     sil, 11h
0x180045c0b  add     rcx, 6
0x180045c0f  mov     [rbp+EndPtr], rcx
0x180045c13  cmp     [rcx], bx
0x180045c16  jnz     short loc_180045BA7
0x180045c18  add     rcx, 2; lpSrc
0x180045c1c  add     r14, r15
0x180045c1f  mov     [rbp+EndPtr], rcx
0x180045c23  cmp     rcx, r14
0x180045c26  jnb     loc_180045D07
0x180045c2c  xor     r15d, r15d
0x180045c2f  cmp     [rcx], r15w
0x180045c33  jz      loc_180045D07
0x180045c39  lea     rdx, [rbp+var_48]
0x180045c3d  call    BfeGetNtPathName
0x180045c42  mov     rbx, rax
0x180045c45  test    rax, rax
0x180045c48  jnz     loc_180045D44
0x180045c4e  mov     rcx, [rbp+EndPtr]
0x180045c52  or      rax, 0FFFFFFFFFFFFFFFFh
0x180045c56  inc     rax
0x180045c59  cmp     [rcx+rax*2], r15w
0x180045c5e  jnz     short loc_180045C56
0x180045c60  lea     rcx, [rcx+rax*2]
0x180045c64  add     rcx, 2; StringSid
0x180045c68  mov     [rbp+EndPtr], rcx
0x180045c6c  cmp     rcx, r14
0x180045c6f  jnb     loc_180045D07
0x180045c75  cmp     [rcx], r15w
0x180045c79  jz      loc_180045D07
0x180045c7f  lea     rdx, [rbp+Sid]; Sid
0x180045c83  call    cs:__imp_ConvertStringSidToSidW
0x180045c8a  nop     dword ptr [rax+rax+00h]
0x180045c8f  test    eax, eax
0x180045c91  jnz     short loc_180045D07
0x180045c93  xorps   xmm0, xmm0
0x180045c96  lea     edx, [rax+44h]; uBytes
0x180045c99  xor     ecx, ecx; uFlags
0x180045c9b  mov     [rbp+ServiceSidLength], edx
0x180045c9e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180045ca2  call    cs:__imp_LocalAlloc
0x180045ca9  nop     dword ptr [rax+rax+00h]
0x180045cae  mov     [rbp+Sid], rax
0x180045cb2  test    rax, rax
0x180045cb5  jnz     short loc_180045CCB
0x180045cb7  mov     r8d, 0C0000017h
0x180045cbd  lea     rdx, aLocalalloc; "LocalAlloc"
0x180045cc4  call    WfpReportSysErrorAsNtStatus
0x180045cc9  jmp     short loc_180045D41
0x180045ccb  mov     rdx, [rbp+EndPtr]; SourceString
0x180045ccf  lea     rcx, [rbp+DestinationString]; DestinationString
0x180045cd3  call    cs:__imp_RtlInitUnicodeString
0x180045cda  nop     dword ptr [rax+rax+00h]
0x180045cdf  mov     rdx, [rbp+Sid]; ServiceSid
0x180045ce3  lea     r8, [rbp+ServiceSidLength]; ServiceSidLength
0x180045ce7  lea     rcx, [rbp+DestinationString]; ServiceName
0x180045ceb  call    cs:__imp_RtlCreateServiceSid
0x180045cf2  nop     dword ptr [rax+rax+00h]
0x180045cf7  test    eax, eax
0x180045cf9  jns     short loc_180045D07
0x180045cfb  mov     r8d, eax
0x180045cfe  lea     rdx, aRtlcreateservi; "RtlCreateServiceSid"
0x180045d05  jmp     short loc_180045CC4
0x180045d07  mov     rax, [rbp+var_48]
0x180045d0b  mov     [rdi+80h], rax
0x180045d12  mov     rax, [rbp+Sid]
0x180045d16  mov     [rdi+88h], rax
0x180045d1d  mov     [rdi+78h], r12d
0x180045d21  mov     [rdi+7Ch], r13w
0x180045d26  mov     [rdi+7Eh], sil
0x180045d2a  jmp     short loc_180045D7C
0x180045d2c  mov     r8d, 1Fh
0x180045d32  lea     rdx, aBfefwtriggeren_0; "BfeFwTriggerEntryInitParams"
0x180045d39  call    WfpReportSysErrorAsWinError
0x180045d3e  xor     r15d, r15d
0x180045d41  mov     rbx, rax
0x180045d44  cmp     [rbp+var_48], r15
0x180045d48  jz      short loc_180045D53
0x180045d4a  lea     rcx, [rbp+var_48]
0x180045d4e  call    WfpMemFree
0x180045d53  mov     rcx, [rbp+Sid]; hMem
0x180045d57  test    rcx, rcx
0x180045d5a  jz      short loc_180045D68
0x180045d5c  call    cs:__imp_LocalFree
0x180045d63  nop     dword ptr [rax+rax+00h]
0x180045d68  test    rbx, rbx
0x180045d6b  jz      short loc_180045D7C
0x180045d6d  lea     rdx, aBfefwtriggeren_0; "BfeFwTriggerEntryInitParams"
0x180045d74  mov     rcx, rbx
0x180045d77  call    WfpReportError
0x180045d7c  mov     rax, rbx
0x180045d7f  mov     rcx, [rbp+var_18]
0x180045d83  xor     rcx, rsp; StackCookie
0x180045d86  call    __security_check_cookie
0x180045d8b  add     rsp, 68h
0x180045d8f  pop     r15
0x180045d91  pop     r14
0x180045d93  pop     r13
0x180045d95  pop     r12
0x180045d97  pop     rdi
0x180045d98  pop     rsi
0x180045d99  pop     rbx
0x180045d9a  pop     rbp
0x180045d9b  retn
```
