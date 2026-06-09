# SeComRouterDumpHooks

- ea: `0x180057338`
- end: `0x1800574e3`
- name: `SeComRouterDumpHooks`
- size: `427`
- prototype: `__int64 __fastcall(PRTL_CRITICAL_SECTION CriticalSection)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180056e90`

## callees

- `0x180008068`
- `0x18000f114`
- `0x180024a80`
- `0x180057338`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800574ca`
- `ntdll!RtlLeaveCriticalSection` at `0x1800574ca`
- `ntdll!RtlEnterCriticalSection` at `0x180057361`
- `ntdll!RtlEnterCriticalSection` at `0x180057361`
- `ntdll!RtlFreeUnicodeString` at `0x180057490`
- `ntdll!RtlFreeUnicodeString` at `0x1800574a9`
- `ntdll!RtlFreeUnicodeString` at `0x180057490`
- `ntdll!RtlFreeUnicodeString` at `0x1800574a9`
- `ntdll!RtlStringFromGUID` at `0x1800573c9`
- `ntdll!RtlStringFromGUID` at `0x1800573fe`
- `ntdll!RtlStringFromGUID` at `0x1800573c9`
- `ntdll!RtlStringFromGUID` at `0x1800573fe`

## string_xrefs

- `0x1800573e0`: `SeComRouterDumpHooks`
- `0x180057415`: `SeComRouterDumpHooks`
- `0x18005743f`: `<COMHOOK CLSID="%S" IID="%S" INDEX="%d"/>\n`
- `0x180057408`: `Failed to convert ClassId to string`

## pseudocode

```c
NTSTATUS __fastcall SeComRouterDumpHooks(PRTL_CRITICAL_SECTION CriticalSection, __int64 a2)
{
  HANDLE OwningThread; // rax
  ULONGLONG i; // rsi
  struct _RTL_CRITICAL_SECTION_DEBUG *v6; // rbx
  ULONGLONG v7; // rcx
  const GUID *Blink; // rcx
  const GUID *v9; // rcx
  struct _UNICODE_STRING GuidString; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-10h] BYREF
  ULONGLONG pullResult; // [rsp+60h] [rbp+20h] BYREF

  UnicodeString = 0;
  GuidString = 0;
  RtlEnterCriticalSection(CriticalSection);
  OwningThread = CriticalSection[1].OwningThread;
  if ( OwningThread )
  {
    for ( i = 0; i < (unsigned __int64)OwningThread; ++i )
    {
      v6 = 0;
      if ( i < (unsigned __int64)OwningThread )
      {
        v7 = *(_QWORD *)&CriticalSection[1].LockCount;
        pullResult = 0;
        if ( ULongLongMult(v7, i, &pullResult) < 0
          || (v6 = (PRTL_CRITICAL_SECTION_DEBUG)((char *)CriticalSection[2].DebugInfo + pullResult),
              v6 < CriticalSection[2].DebugInfo) )
        {
          v6 = 0;
        }
      }
      if ( a2 == *(_QWORD *)&v6->Type )
      {
        UnicodeString = 0;
        GuidString = 0;
        Blink = (const GUID *)v6->ProcessLocksList.Blink;
        if ( Blink && RtlStringFromGUID(Blink, &GuidString) < 0 )
          AslLogCallPrintf(
            1,
            "SeComRouterDumpHooks",
            1597,
            "Failed to convert InterfaceId to string",
            *(_QWORD *)&GuidString.Length);
        v9 = (const GUID *)v6->CriticalSection;
        if ( v9 )
        {
          if ( RtlStringFromGUID(v9, &UnicodeString) < 0 )
            AslLogCallPrintf(1, "SeComRouterDumpHooks", 1605, "Failed to convert ClassId to string");
          SeStatePrintf("<COMHOOK CLSID=\"%S\" IID=\"%S\" INDEX=\"%d\"/>\r\n");
        }
        if ( v6->ProcessLocksList.Flink )
          SeStatePrintf("<WINRTHOOK ACTID=\"%S\" IID=\"%S\" INDEX=\"%d\"/>\r\n");
        if ( UnicodeString.Buffer )
        {
          RtlFreeUnicodeString(&UnicodeString);
          UnicodeString.Buffer = 0;
        }
        if ( GuidString.Buffer )
        {
          RtlFreeUnicodeString(&GuidString);
          GuidString.Buffer = 0;
        }
      }
      OwningThread = CriticalSection[1].OwningThread;
    }
  }
  return RtlLeaveCriticalSection(CriticalSection);
}

```

## disassembly

```asm
0x180057338  mov     [rsp-18h+arg_8], rbx
0x18005733d  mov     [rsp-18h+arg_10], rsi
0x180057342  push    rbp
0x180057343  push    rdi
0x180057344  push    r14
0x180057346  mov     rbp, rsp
0x180057349  sub     rsp, 40h
0x18005734d  xorps   xmm0, xmm0
0x180057350  xorps   xmm1, xmm1
0x180057353  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180057357  mov     r14, rdx
0x18005735a  mov     rdi, rcx
0x18005735d  movups  xmmword ptr [rbp+GuidString.Length], xmm1
0x180057361  call    cs:__imp_RtlEnterCriticalSection
0x180057367  mov     rax, [rdi+38h]
0x18005736b  test    rax, rax
0x18005736e  jz      loc_1800574C7
0x180057374  xor     esi, esi
0x180057376  xor     ebx, ebx
0x180057378  cmp     rsi, rax
0x18005737b  jnb     short loc_1800573A5
0x18005737d  mov     rcx, [rdi+30h]; ullMultiplicand
0x180057381  lea     r8, [rbp+pullResult]; pullResult
0x180057385  mov     rdx, rsi; ullMultiplier
0x180057388  mov     [rbp+pullResult], rbx
0x18005738c  call    ULongLongMult
0x180057391  test    eax, eax
0x180057393  js      short loc_1800573A3
0x180057395  mov     rbx, [rbp+pullResult]
0x180057399  add     rbx, [rdi+50h]
0x18005739d  cmp     rbx, [rdi+50h]
0x1800573a1  jnb     short loc_1800573A5
0x1800573a3  xor     ebx, ebx
0x1800573a5  cmp     r14, [rbx]
0x1800573a8  jnz     loc_1800574B7
0x1800573ae  xorps   xmm0, xmm0
0x1800573b1  xorps   xmm1, xmm1
0x1800573b4  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x1800573b8  movups  xmmword ptr [rbp+GuidString.Length], xmm1
0x1800573bc  mov     rcx, [rbx+18h]; Guid
0x1800573c0  test    rcx, rcx
0x1800573c3  jz      short loc_1800573F1
0x1800573c5  lea     rdx, [rbp+GuidString]; GuidString
0x1800573c9  call    cs:__imp_RtlStringFromGUID
0x1800573cf  test    eax, eax
0x1800573d1  jns     short loc_1800573F1
0x1800573d3  lea     r9, aFailedToConver_5; "Failed to convert InterfaceId to string"
0x1800573da  mov     r8d, 63Dh
0x1800573e0  lea     rdx, aSecomrouterdum; "SeComRouterDumpHooks"
0x1800573e7  mov     ecx, 1
0x1800573ec  call    AslLogCallPrintf
0x1800573f1  mov     rcx, [rbx+8]; Guid
0x1800573f5  test    rcx, rcx
0x1800573f8  jz      short loc_18005745A
0x1800573fa  lea     rdx, [rbp+UnicodeString]; GuidString
0x1800573fe  call    cs:__imp_RtlStringFromGUID
0x180057404  test    eax, eax
0x180057406  jns     short loc_180057426
0x180057408  lea     r9, aFailedToConver_27; "Failed to convert ClassId to string"
0x18005740f  mov     r8d, 645h
0x180057415  lea     rdx, aSecomrouterdum; "SeComRouterDumpHooks"
0x18005741c  mov     ecx, 1
0x180057421  call    AslLogCallPrintf
0x180057426  mov     rax, [rbp+GuidString.Buffer]
0x18005742a  lea     r8, aNull_0; "NULL"
0x180057431  mov     r9d, [rbx+20h]
0x180057435  lea     rdx, aNull_0; "NULL"
0x18005743c  test    rax, rax
0x18005743f  lea     rcx, aComhookClsidSI; "<COMHOOK CLSID=\"%S\" IID=\"%S\" INDEX="...
0x180057446  cmovnz  r8, rax
0x18005744a  mov     rax, [rbp+UnicodeString.Buffer]
0x18005744e  test    rax, rax
0x180057451  cmovnz  rdx, rax
0x180057455  call    SeStatePrintf
0x18005745a  mov     rdx, [rbx+10h]
0x18005745e  test    rdx, rdx
0x180057461  jz      short loc_180057485
0x180057463  mov     rax, [rbp+GuidString.Buffer]
0x180057467  lea     r8, aNull_0; "NULL"
0x18005746e  mov     r9d, [rbx+20h]
0x180057472  lea     rcx, aWinrthookActid; "<WINRTHOOK ACTID=\"%S\" IID=\"%S\" INDE"...
0x180057479  test    rax, rax
0x18005747c  cmovnz  r8, rax
0x180057480  call    SeStatePrintf
0x180057485  cmp     [rbp+UnicodeString.Buffer], 0
0x18005748a  jz      short loc_18005749E
0x18005748c  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180057490  call    cs:__imp_RtlFreeUnicodeString
0x180057496  mov     [rbp+UnicodeString.Buffer], 0
0x18005749e  cmp     [rbp+GuidString.Buffer], 0
0x1800574a3  jz      short loc_1800574B7
0x1800574a5  lea     rcx, [rbp+GuidString]; UnicodeString
0x1800574a9  call    cs:__imp_RtlFreeUnicodeString
0x1800574af  mov     [rbp+GuidString.Buffer], 0
0x1800574b7  mov     rax, [rdi+38h]
0x1800574bb  inc     rsi
0x1800574be  cmp     rsi, rax
0x1800574c1  jb      loc_180057376
0x1800574c7  mov     rcx, rdi; CriticalSection
0x1800574ca  call    cs:__imp_RtlLeaveCriticalSection
0x1800574d0  mov     rbx, [rsp+40h+arg_8]
0x1800574d5  mov     rsi, [rsp+40h+arg_10]
0x1800574da  add     rsp, 40h
0x1800574de  pop     r14
0x1800574e0  pop     rdi
0x1800574e1  pop     rbp
0x1800574e2  retn
```
