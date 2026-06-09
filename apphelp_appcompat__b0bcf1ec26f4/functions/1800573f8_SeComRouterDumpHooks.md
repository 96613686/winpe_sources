# SeComRouterDumpHooks

- ea: `0x1800573f8`
- end: `0x1800575a3`
- name: `SeComRouterDumpHooks`
- size: `427`
- prototype: `__int64 __fastcall(PRTL_CRITICAL_SECTION CriticalSection)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180056f50`

## callees

- `0x180008068`
- `0x18000f114`
- `0x180024a80`
- `0x1800573f8`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18005758a`
- `ntdll!RtlLeaveCriticalSection` at `0x18005758a`
- `ntdll!RtlEnterCriticalSection` at `0x180057421`
- `ntdll!RtlEnterCriticalSection` at `0x180057421`
- `ntdll!RtlFreeUnicodeString` at `0x180057550`
- `ntdll!RtlFreeUnicodeString` at `0x180057569`
- `ntdll!RtlFreeUnicodeString` at `0x180057550`
- `ntdll!RtlFreeUnicodeString` at `0x180057569`
- `ntdll!RtlStringFromGUID` at `0x180057489`
- `ntdll!RtlStringFromGUID` at `0x1800574be`
- `ntdll!RtlStringFromGUID` at `0x180057489`
- `ntdll!RtlStringFromGUID` at `0x1800574be`

## string_xrefs

- `0x1800574a0`: `SeComRouterDumpHooks`
- `0x1800574d5`: `SeComRouterDumpHooks`
- `0x1800574ff`: `<COMHOOK CLSID="%S" IID="%S" INDEX="%d"/>\n`
- `0x1800574c8`: `Failed to convert ClassId to string`

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
0x1800573f8  mov     [rsp-18h+arg_8], rbx
0x1800573fd  mov     [rsp-18h+arg_10], rsi
0x180057402  push    rbp
0x180057403  push    rdi
0x180057404  push    r14
0x180057406  mov     rbp, rsp
0x180057409  sub     rsp, 40h
0x18005740d  xorps   xmm0, xmm0
0x180057410  xorps   xmm1, xmm1
0x180057413  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180057417  mov     r14, rdx
0x18005741a  mov     rdi, rcx
0x18005741d  movups  xmmword ptr [rbp+GuidString.Length], xmm1
0x180057421  call    cs:__imp_RtlEnterCriticalSection
0x180057427  mov     rax, [rdi+38h]
0x18005742b  test    rax, rax
0x18005742e  jz      loc_180057587
0x180057434  xor     esi, esi
0x180057436  xor     ebx, ebx
0x180057438  cmp     rsi, rax
0x18005743b  jnb     short loc_180057465
0x18005743d  mov     rcx, [rdi+30h]; ullMultiplicand
0x180057441  lea     r8, [rbp+pullResult]; pullResult
0x180057445  mov     rdx, rsi; ullMultiplier
0x180057448  mov     [rbp+pullResult], rbx
0x18005744c  call    ULongLongMult
0x180057451  test    eax, eax
0x180057453  js      short loc_180057463
0x180057455  mov     rbx, [rbp+pullResult]
0x180057459  add     rbx, [rdi+50h]
0x18005745d  cmp     rbx, [rdi+50h]
0x180057461  jnb     short loc_180057465
0x180057463  xor     ebx, ebx
0x180057465  cmp     r14, [rbx]
0x180057468  jnz     loc_180057577
0x18005746e  xorps   xmm0, xmm0
0x180057471  xorps   xmm1, xmm1
0x180057474  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180057478  movups  xmmword ptr [rbp+GuidString.Length], xmm1
0x18005747c  mov     rcx, [rbx+18h]; Guid
0x180057480  test    rcx, rcx
0x180057483  jz      short loc_1800574B1
0x180057485  lea     rdx, [rbp+GuidString]; GuidString
0x180057489  call    cs:__imp_RtlStringFromGUID
0x18005748f  test    eax, eax
0x180057491  jns     short loc_1800574B1
0x180057493  lea     r9, aFailedToConver_5; "Failed to convert InterfaceId to string"
0x18005749a  mov     r8d, 63Dh
0x1800574a0  lea     rdx, aSecomrouterdum; "SeComRouterDumpHooks"
0x1800574a7  mov     ecx, 1
0x1800574ac  call    AslLogCallPrintf
0x1800574b1  mov     rcx, [rbx+8]; Guid
0x1800574b5  test    rcx, rcx
0x1800574b8  jz      short loc_18005751A
0x1800574ba  lea     rdx, [rbp+UnicodeString]; GuidString
0x1800574be  call    cs:__imp_RtlStringFromGUID
0x1800574c4  test    eax, eax
0x1800574c6  jns     short loc_1800574E6
0x1800574c8  lea     r9, aFailedToConver_27; "Failed to convert ClassId to string"
0x1800574cf  mov     r8d, 645h
0x1800574d5  lea     rdx, aSecomrouterdum; "SeComRouterDumpHooks"
0x1800574dc  mov     ecx, 1
0x1800574e1  call    AslLogCallPrintf
0x1800574e6  mov     rax, [rbp+GuidString.Buffer]
0x1800574ea  lea     r8, aNull_0; "NULL"
0x1800574f1  mov     r9d, [rbx+20h]
0x1800574f5  lea     rdx, aNull_0; "NULL"
0x1800574fc  test    rax, rax
0x1800574ff  lea     rcx, aComhookClsidSI; "<COMHOOK CLSID=\"%S\" IID=\"%S\" INDEX="...
0x180057506  cmovnz  r8, rax
0x18005750a  mov     rax, [rbp+UnicodeString.Buffer]
0x18005750e  test    rax, rax
0x180057511  cmovnz  rdx, rax
0x180057515  call    SeStatePrintf
0x18005751a  mov     rdx, [rbx+10h]
0x18005751e  test    rdx, rdx
0x180057521  jz      short loc_180057545
0x180057523  mov     rax, [rbp+GuidString.Buffer]
0x180057527  lea     r8, aNull_0; "NULL"
0x18005752e  mov     r9d, [rbx+20h]
0x180057532  lea     rcx, aWinrthookActid; "<WINRTHOOK ACTID=\"%S\" IID=\"%S\" INDE"...
0x180057539  test    rax, rax
0x18005753c  cmovnz  r8, rax
0x180057540  call    SeStatePrintf
0x180057545  cmp     [rbp+UnicodeString.Buffer], 0
0x18005754a  jz      short loc_18005755E
0x18005754c  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180057550  call    cs:__imp_RtlFreeUnicodeString
0x180057556  mov     [rbp+UnicodeString.Buffer], 0
0x18005755e  cmp     [rbp+GuidString.Buffer], 0
0x180057563  jz      short loc_180057577
0x180057565  lea     rcx, [rbp+GuidString]; UnicodeString
0x180057569  call    cs:__imp_RtlFreeUnicodeString
0x18005756f  mov     [rbp+GuidString.Buffer], 0
0x180057577  mov     rax, [rdi+38h]
0x18005757b  inc     rsi
0x18005757e  cmp     rsi, rax
0x180057581  jb      loc_180057436
0x180057587  mov     rcx, rdi; CriticalSection
0x18005758a  call    cs:__imp_RtlLeaveCriticalSection
0x180057590  mov     rbx, [rsp+40h+arg_8]
0x180057595  mov     rsi, [rsp+40h+arg_10]
0x18005759a  add     rsp, 40h
0x18005759e  pop     r14
0x1800575a0  pop     rdi
0x1800575a1  pop     rbp
0x1800575a2  retn
```
