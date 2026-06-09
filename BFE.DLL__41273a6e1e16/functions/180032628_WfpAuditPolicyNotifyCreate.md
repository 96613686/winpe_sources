# WfpAuditPolicyNotifyCreate

- ea: `0x180032628`
- end: `0x1800328bb`
- name: `WfpAuditPolicyNotifyCreate`
- size: `659`
- prototype: `__int64 __usercall@<rax>(PSID pSourceSid@<rcx>, int, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180031740`
- `0x180032420`

## callees

- `0x180012d8c`
- `0x1800135ac`
- `0x1800197d0`
- `0x180024880`
- `0x180024e40`
- `0x180025fe4`
- `0x180031210`
- `0x180032628`
- `0x1800328d0`
- `0x18005aa60`
- `0x18007a78c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003279b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003279b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032827`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032827`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003269a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003269a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800326ca`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800326ca`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180032812`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180032812`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x1800327d0`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x1800327d0`

## string_xrefs

- `0x1800326e6`: `CopySid`
- `0x1800327bc`: `CreateEventW`
- `0x180032883`: `WfpAuditPolicyNotifyCreate`

## pseudocode

```c
__int64 __fastcall WfpAuditPolicyNotifyCreate(
        PSID pSourceSid,
        unsigned int a2,
        char *a3,
        __int64 a4,
        int a5,
        _QWORD *a6)
{
  unsigned __int64 v7; // rbp
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rdi
  SIZE_T LengthSid; // r14
  DWORD LastError; // eax
  __int64 v15; // rcx
  const char *v16; // rdx
  __int64 v17; // rax
  int v18; // esi
  unsigned int i; // r8d
  __int64 v20; // rdx
  HANDLE EventW; // rax
  NTSTATUS v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rax
  _QWORD v26[2]; // [rsp+30h] [rbp-58h] BYREF

  v7 = a2;
  v26[0] = 0;
  *a6 = 0;
  v11 = WfpMemAlloc(0x58u, 8u);
  if ( !v11 )
  {
    v12 = v26[0];
    if ( pSourceSid )
    {
      LengthSid = GetLengthSid(pSourceSid);
      v11 = WfpMemAlloc(LengthSid, 0);
      if ( v11 )
        goto LABEL_21;
      if ( !CopySid(LengthSid, *(PSID *)v26[0], pSourceSid) )
      {
        LastError = GetLastError();
        v16 = "CopySid";
LABEL_6:
        v17 = WfpReportSysErrorAsWinError(v15, v16, LastError);
        goto LABEL_20;
      }
    }
    *(_DWORD *)(v26[0] + 16LL) = v7;
    v26[1] = 0;
    if ( !is_mul_ok(v7, 0x10u) )
    {
      v17 = WfpReportSysErrorAsHResult(v10, "ULongLongMult", 2147942934LL, 1);
      goto LABEL_20;
    }
    v11 = WfpBufferCopy(a3, 16 * v7);
    if ( !v11 )
    {
      v11 = WfpMemAllocArray(v7, 16, 8, v12 + 32);
      if ( !v11 )
      {
        v18 = 0;
        for ( i = 0; i < (unsigned int)v7; v18 |= *(_DWORD *)&a3[v20 + 8] | *(_DWORD *)&a3[v20 + 12] )
        {
          v20 = i++;
          v20 *= 16;
          *(_OWORD *)(*(_QWORD *)(v12 + 32) + v20) = *(_OWORD *)*(_QWORD *)&a3[v20];
        }
        *(_QWORD *)(v12 + 40) = a4;
        *(_QWORD *)(v12 + 48) = 0;
        EventW = CreateEventW(0, 0, 0, 0);
        *(_QWORD *)(v12 + 56) = EventW;
        if ( !EventW )
        {
          LastError = GetLastError();
          v16 = "CreateEventW";
          goto LABEL_6;
        }
        v22 = LsaRegisterPolicyChangeNotification(PolicyNotifyAuditEventsInformation, EventW);
        if ( v22 >= 0 )
        {
          *(_DWORD *)(v12 + 64) = 1;
          v24 = RegisterWaitForSingleObjectEx(
                  *(_QWORD *)(v12 + 56),
                  WfpAuditPolicyNotifyOnChange,
                  v12,
                  0xFFFFFFFFLL,
                  16);
          *(_QWORD *)(v12 + 72) = v24;
          if ( v24 )
          {
            *(_DWORD *)(v12 + 80) = ~v18;
            WfpAuditPolicyNotifyOnChange(v12, 0);
            *a6 = v12;
            return v11;
          }
          LastError = GetLastError();
          v16 = "RegisterWaitForSingleObjectEx";
          goto LABEL_6;
        }
        v17 = WfpReportSysErrorAsNtStatus(v23, "LsaRegisterPolicyChangeNotification", (unsigned int)v22);
LABEL_20:
        v11 = v17;
        if ( !v17 )
          return v11;
      }
    }
  }
LABEL_21:
  WfpAuditPolicyNotifyDestroy(v26);
  if ( v11 )
    WfpReportError(v11, "WfpAuditPolicyNotifyCreate");
  return v11;
}

```

## disassembly

```asm
0x180032628  mov     [rsp+arg_18], rbx
0x18003262d  push    rbp
0x18003262e  push    rsi
0x18003262f  push    rdi
0x180032630  push    r12
0x180032632  push    r13
0x180032634  push    r14
0x180032636  push    r15
0x180032638  sub     rsp, 50h
0x18003263c  mov     rax, cs:__security_cookie
0x180032643  xor     rax, rsp
0x180032646  mov     [rsp+88h+var_48], rax
0x18003264b  mov     r12, [rsp+88h+arg_28]
0x180032653  mov     r15, r8
0x180032656  mov     ebp, edx
0x180032658  lea     r8, [rsp+88h+var_58]
0x18003265d  mov     edx, 8; dwFlags
0x180032662  mov     [rsp+88h+var_58], 0
0x18003266b  mov     rsi, rcx
0x18003266e  mov     r13, r9
0x180032671  mov     qword ptr [r12], 0
0x180032679  lea     ecx, [rdx+50h]; dwBytes
0x18003267c  call    WfpMemAlloc
0x180032681  mov     rbx, rax
0x180032684  test    rax, rax
0x180032687  jnz     loc_180032874
0x18003268d  mov     rdi, [rsp+88h+var_58]
0x180032692  test    rsi, rsi
0x180032695  jz      short loc_1800326FA
0x180032697  mov     rcx, rsi; pSid
0x18003269a  call    cs:__imp_GetLengthSid
0x1800326a1  nop     dword ptr [rax+rax+00h]
0x1800326a6  mov     ecx, eax; dwBytes
0x1800326a8  mov     r8, rdi
0x1800326ab  xor     edx, edx; dwFlags
0x1800326ad  mov     r14d, eax
0x1800326b0  call    WfpMemAlloc
0x1800326b5  mov     rbx, rax
0x1800326b8  test    rax, rax
0x1800326bb  jnz     loc_180032874
0x1800326c1  mov     rdx, [rdi]; pDestinationSid
0x1800326c4  mov     r8, rsi; pSourceSid
0x1800326c7  mov     ecx, r14d; nDestinationSidLength
0x1800326ca  call    cs:__imp_CopySid
0x1800326d1  nop     dword ptr [rax+rax+00h]
0x1800326d6  test    eax, eax
0x1800326d8  jnz     short loc_1800326FA
0x1800326da  call    cs:__imp_GetLastError
0x1800326e1  nop     dword ptr [rax+rax+00h]
0x1800326e6  lea     rdx, aCopysid; "CopySid"
0x1800326ed  mov     r8d, eax
0x1800326f0  call    WfpReportSysErrorAsWinError
0x1800326f5  jmp     loc_18003286C
0x1800326fa  mov     eax, 10h
0x1800326ff  mov     [rdi+10h], ebp
0x180032702  mul     rbp
0x180032705  mov     [rsp+88h+var_50], 0
0x18003270e  test    rdx, rdx
0x180032711  jnz     loc_180032854
0x180032717  lea     r9, [rdi+18h]
0x18003271b  mov     rdx, rax; dwBytes
0x18003271e  mov     rcx, r15; Src
0x180032721  call    WfpBufferCopy
0x180032726  mov     rbx, rax
0x180032729  test    rax, rax
0x18003272c  jnz     loc_180032874
0x180032732  lea     r9, [rdi+20h]
0x180032736  mov     rcx, rbp
0x180032739  lea     edx, [rax+10h]
0x18003273c  lea     r8d, [rax+8]
0x180032740  call    WfpMemAllocArray
0x180032745  mov     rbx, rax
0x180032748  test    rax, rax
0x18003274b  jnz     loc_180032874
0x180032751  xor     esi, esi
0x180032753  xor     r8d, r8d
0x180032756  test    ebp, ebp
0x180032758  jz      short loc_180032785
0x18003275a  mov     rcx, [rdi+20h]
0x18003275e  mov     edx, r8d
0x180032761  inc     r8d
0x180032764  shl     rdx, 4
0x180032768  mov     rax, [rdx+r15]
0x18003276c  movups  xmm0, xmmword ptr [rax]
0x18003276f  movdqu  xmmword ptr [rcx+rdx], xmm0
0x180032774  mov     eax, [rdx+r15+0Ch]
0x180032779  or      eax, [rdx+r15+8]
0x18003277e  or      esi, eax
0x180032780  cmp     r8d, ebp
0x180032783  jb      short loc_18003275A
0x180032785  mov     [rdi+28h], r13
0x180032789  xor     r9d, r9d; lpName
0x18003278c  xor     r8d, r8d; bInitialState
0x18003278f  mov     qword ptr [rdi+30h], 0
0x180032797  xor     edx, edx; bManualReset
0x180032799  xor     ecx, ecx; lpEventAttributes
0x18003279b  call    cs:__imp_CreateEventW
0x1800327a2  nop     dword ptr [rax+rax+00h]
0x1800327a7  mov     [rdi+38h], rax
0x1800327ab  test    rax, rax
0x1800327ae  jnz     short loc_1800327C8
0x1800327b0  call    cs:__imp_GetLastError
0x1800327b7  nop     dword ptr [rax+rax+00h]
0x1800327bc  lea     rdx, aCreateeventw; "CreateEventW"
0x1800327c3  jmp     loc_1800326ED
0x1800327c8  mov     rdx, rax; NotificationEventHandle
0x1800327cb  mov     ecx, 1; InformationClass
0x1800327d0  call    cs:__imp_LsaRegisterPolicyChangeNotification
0x1800327d7  nop     dword ptr [rax+rax+00h]
0x1800327dc  test    eax, eax
0x1800327de  jns     short loc_1800327F1
0x1800327e0  mov     r8d, eax
0x1800327e3  lea     rdx, aLsaregisterpol_0; "LsaRegisterPolicyChangeNotification"
0x1800327ea  call    WfpReportSysErrorAsNtStatus
0x1800327ef  jmp     short loc_18003286C
0x1800327f1  mov     dword ptr [rdi+40h], 1
0x1800327f8  lea     rdx, WfpAuditPolicyNotifyOnChange
0x1800327ff  mov     rcx, [rdi+38h]
0x180032803  or      r9d, 0FFFFFFFFh
0x180032807  mov     r8, rdi
0x18003280a  mov     [rsp+88h+var_68], 10h
0x180032812  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180032819  nop     dword ptr [rax+rax+00h]
0x18003281e  mov     [rdi+48h], rax
0x180032822  test    rax, rax
0x180032825  jnz     short loc_18003283F
0x180032827  call    cs:__imp_GetLastError
0x18003282e  nop     dword ptr [rax+rax+00h]
0x180032833  lea     rdx, aRegisterwaitfo; "RegisterWaitForSingleObjectEx"
0x18003283a  jmp     loc_1800326ED
0x18003283f  not     esi
0x180032841  xor     edx, edx
0x180032843  mov     rcx, rdi
0x180032846  mov     [rdi+50h], esi
0x180032849  call    WfpAuditPolicyNotifyOnChange
0x18003284e  mov     [r12], rdi
0x180032852  jmp     short loc_180032892
0x180032854  mov     r9d, 1
0x18003285a  lea     rdx, aUlonglongmult; "ULongLongMult"
0x180032861  mov     r8d, 80070216h
0x180032867  call    WfpReportSysErrorAsHResult
0x18003286c  mov     rbx, rax
0x18003286f  test    rax, rax
0x180032872  jz      short loc_180032892
0x180032874  lea     rcx, [rsp+88h+var_58]
0x180032879  call    WfpAuditPolicyNotifyDestroy
0x18003287e  test    rbx, rbx
0x180032881  jz      short loc_180032892
0x180032883  lea     rdx, aWfpauditpolicy; "WfpAuditPolicyNotifyCreate"
0x18003288a  mov     rcx, rbx
0x18003288d  call    WfpReportError
0x180032892  mov     rax, rbx
0x180032895  mov     rcx, [rsp+88h+var_48]
0x18003289a  xor     rcx, rsp; StackCookie
0x18003289d  call    __security_check_cookie
0x1800328a2  mov     rbx, [rsp+88h+arg_18]
0x1800328aa  add     rsp, 50h
0x1800328ae  pop     r15
0x1800328b0  pop     r14
0x1800328b2  pop     r13
0x1800328b4  pop     r12
0x1800328b6  pop     rdi
0x1800328b7  pop     rsi
0x1800328b8  pop     rbp
0x1800328b9  retn
```
