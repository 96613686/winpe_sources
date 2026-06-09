# SecurityLog::WriteLog(wchar_t const * * const,ushort)

- ea: `0x180063594`
- end: `0x180063695`
- name: `?WriteLog@SecurityLog@@QEAA_NQEAPEB_WG@Z`
- size: `257`
- prototype: `bool __fastcall(SecurityLog *__hidden this, const wchar_t **const, unsigned __int16)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800501c0`
- `0x1800564f0`
- `0x180056d90`

## callees

- `0x1800029cc`
- `0x180002a0c`
- `0x1800030d0`
- `0x1800633d8`
- `0x1800634a0`
- `0x180063594`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063650`
- `AUTHZ!AuthzReportSecurityEventFromParams` at `0x180063643`
- `AUTHZ!AuthzReportSecurityEventFromParams` at `0x180063643`

## pseudocode

```c
char __fastcall SecurityLog::WriteLog(SecurityLog *this, const wchar_t **const a2, __int16 a3)
{
  AUDIT_PARAM *v4; // rax
  AUDIT_PARAM *v5; // rbx
  char v6; // di
  __int64 v7; // rdx
  __int64 v8; // rcx
  const wchar_t *v9; // rax
  const struct std::nothrow_t *v10; // rdx
  struct _AUDIT_PARAMS pParams; // [rsp+30h] [rbp-28h] BYREF
  DWORD LastError; // [rsp+70h] [rbp+18h] BYREF

  LOWORD(LastError) = a3;
  memset(&pParams, 0, sizeof(pParams));
  v4 = (AUDIT_PARAM *)operator new[](0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    memset_0(v4, 0, 0x40u);
    v6 = 1;
    pParams.Length = 24;
    v7 = 0;
    pParams.Flags = 1;
    pParams.Parameters = v5;
    v8 = 0;
    pParams.Count = 2;
    do
    {
      v9 = a2[v7++];
      v5[v8].Type = APT_String;
      v5[v8].Length = 8;
      v5[v8++].Data0 = (ULONG_PTR)v9;
    }
    while ( v7 != 2 );
    if ( !AuthzReportSecurityEventFromParams(0, g_securityLog, 0xCu, 0, &pParams) )
    {
      v6 = 0;
      LastError = GetLastError();
      IsoEnvBrokerTelemetry::SecurityLogWriteEventFailure<unsigned long>((int *)&LastError);
    }
    operator delete(v5, v10);
    return v6;
  }
  else
  {
    LastError = 14;
    IsoEnvBrokerTelemetry::SecurityLogWriteEventFailure<long>((int *)&LastError);
    return 0;
  }
}

```

## disassembly

```asm
0x180063594  mov     r11, rsp
0x180063597  mov     [r11+8], rbx
0x18006359b  mov     [r11+10h], rsi
0x18006359f  mov     [r11+18h], r8w
0x1800635a4  push    rdi
0x1800635a5  sub     rsp, 50h
0x1800635a9  xor     eax, eax
0x1800635ab  xorps   xmm0, xmm0
0x1800635ae  mov     rsi, rdx
0x1800635b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800635b8  movups  xmmword ptr [rsp+58h+var_28.Length], xmm0
0x1800635bd  mov     [r11-18h], rax
0x1800635c1  lea     edi, [rax+40h]
0x1800635c4  mov     ecx, edi; unsigned __int64
0x1800635c6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800635cb  mov     rbx, rax
0x1800635ce  test    rax, rax
0x1800635d1  jz      loc_180063671
0x1800635d7  mov     r8d, edi; Size
0x1800635da  xor     edx, edx; Val
0x1800635dc  mov     rcx, rax; void *
0x1800635df  call    memset_0
0x1800635e4  mov     edi, 1
0x1800635e9  mov     [rsp+58h+var_28.Length], 18h
0x1800635f1  xor     edx, edx
0x1800635f3  mov     [rsp+58h+var_28.Flags], edi
0x1800635f7  mov     [rsp+58h+var_28.Parameters], rbx
0x1800635fc  xor     ecx, ecx
0x1800635fe  lea     r8d, [rdi+1]
0x180063602  mov     [rsp+58h+var_28.Count], r8w
0x180063608  mov     rax, [rsi+rdx*8]
0x18006360c  add     rdx, rdi
0x18006360f  mov     [rcx+rbx], r8d
0x180063613  mov     dword ptr [rcx+rbx+4], 8
0x18006361b  mov     [rcx+rbx+10h], rax
0x180063620  lea     rcx, [rcx+20h]
0x180063624  cmp     rdx, r8
0x180063627  jnz     short loc_180063608
0x180063629  mov     rdx, cs:?g_securityLog@@3VSecurityLog@@A; hEventProvider
0x180063630  lea     rax, [rsp+58h+var_28]
0x180063635  xor     r9d, r9d; pUserSid
0x180063638  mov     [rsp+58h+pParams], rax; pParams
0x18006363d  xor     ecx, ecx; dwFlags
0x18006363f  lea     r8d, [r9+0Ch]; dwAuditId
0x180063643  call    cs:__imp_AuthzReportSecurityEventFromParams
0x180063649  test    eax, eax
0x18006364b  jnz     short loc_180063664
0x18006364d  xor     dil, dil
0x180063650  call    cs:__imp_GetLastError
0x180063656  lea     rcx, [rsp+58h+arg_10]
0x18006365b  mov     [rsp+58h+arg_10], eax
0x18006365f  call    ??$SecurityLogWriteEventFailure@K@IsoEnvBrokerTelemetry@@SAX$$QEAK@Z; IsoEnvBrokerTelemetry::SecurityLogWriteEventFailure<ulong>(ulong &&)
0x180063664  mov     rcx, rbx; void *
0x180063667  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006366c  mov     al, dil
0x18006366f  jmp     short loc_180063685
0x180063671  lea     rcx, [rsp+58h+arg_10]
0x180063676  mov     [rsp+58h+arg_10], 0Eh
0x18006367e  call    ??$SecurityLogWriteEventFailure@J@IsoEnvBrokerTelemetry@@SAX$$QEAJ@Z; IsoEnvBrokerTelemetry::SecurityLogWriteEventFailure<long>(long &&)
0x180063683  xor     al, al
0x180063685  mov     rbx, [rsp+58h+arg_0]
0x18006368a  mov     rsi, [rsp+58h+arg_8]
0x18006368f  add     rsp, 50h
0x180063693  pop     rdi
0x180063694  retn
```
