# WfpAuditPolicyNotifyCreate

- ea: `0x18003dc24`
- end: `0x18003de86`
- name: `WfpAuditPolicyNotifyCreate`
- size: `610`
- prototype: `__int64 __usercall@<rax>(PSID pSourceSid@<rcx>, int, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002fe28`
- `0x18003da38`

## callees

- `0x18001236c`
- `0x180012b54`
- `0x180018b74`
- `0x180022190`
- `0x180022730`
- `0x1800238b4`
- `0x18002f724`
- `0x18003dc24`
- `0x18003de90`
- `0x180058b30`
- `0x180077c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003dd85`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003dd85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dcca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dd94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ddf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dcca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dd94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ddf9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003dc96`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003dc96`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003dcc0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003dcc0`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18003ddea`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18003ddea`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x18003ddae`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x18003ddae`

## string_xrefs

- `0x18003dcd0`: `CopySid`
- `0x18003dd9a`: `CreateEventW`
- `0x18003de4f`: `WfpAuditPolicyNotifyCreate`

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
0x18003dc24  mov     [rsp+arg_18], rbx
0x18003dc29  push    rbp
0x18003dc2a  push    rsi
0x18003dc2b  push    rdi
0x18003dc2c  push    r12
0x18003dc2e  push    r13
0x18003dc30  push    r14
0x18003dc32  push    r15
0x18003dc34  sub     rsp, 50h
0x18003dc38  mov     rax, cs:__security_cookie
0x18003dc3f  xor     rax, rsp
0x18003dc42  mov     [rsp+88h+var_48], rax
0x18003dc47  mov     r12, [rsp+88h+arg_28]
0x18003dc4f  mov     r15, r8
0x18003dc52  mov     ebp, edx
0x18003dc54  lea     r8, [rsp+88h+var_58]
0x18003dc59  mov     edx, 8; dwFlags
0x18003dc5e  mov     [rsp+88h+var_58], 0
0x18003dc67  mov     rsi, rcx
0x18003dc6a  mov     r13, r9
0x18003dc6d  mov     qword ptr [r12], 0
0x18003dc75  lea     ecx, [rdx+50h]; dwBytes
0x18003dc78  call    WfpMemAlloc
0x18003dc7d  mov     rbx, rax
0x18003dc80  test    rax, rax
0x18003dc83  jnz     loc_18003DE40
0x18003dc89  mov     rdi, [rsp+88h+var_58]
0x18003dc8e  test    rsi, rsi
0x18003dc91  jz      short loc_18003DCE4
0x18003dc93  mov     rcx, rsi; pSid
0x18003dc96  call    cs:__imp_GetLengthSid
0x18003dc9c  mov     ecx, eax; dwBytes
0x18003dc9e  mov     r8, rdi
0x18003dca1  xor     edx, edx; dwFlags
0x18003dca3  mov     r14d, eax
0x18003dca6  call    WfpMemAlloc
0x18003dcab  mov     rbx, rax
0x18003dcae  test    rax, rax
0x18003dcb1  jnz     loc_18003DE40
0x18003dcb7  mov     rdx, [rdi]; pDestinationSid
0x18003dcba  mov     r8, rsi; pSourceSid
0x18003dcbd  mov     ecx, r14d; nDestinationSidLength
0x18003dcc0  call    cs:__imp_CopySid
0x18003dcc6  test    eax, eax
0x18003dcc8  jnz     short loc_18003DCE4
0x18003dcca  call    cs:__imp_GetLastError
0x18003dcd0  lea     rdx, aCopysid; "CopySid"
0x18003dcd7  mov     r8d, eax
0x18003dcda  call    WfpReportSysErrorAsWinError
0x18003dcdf  jmp     loc_18003DE38
0x18003dce4  mov     eax, 10h
0x18003dce9  mov     [rdi+10h], ebp
0x18003dcec  mul     rbp
0x18003dcef  mov     [rsp+88h+var_50], 0
0x18003dcf8  test    rdx, rdx
0x18003dcfb  jnz     loc_18003DE20
0x18003dd01  lea     r9, [rdi+18h]
0x18003dd05  mov     rdx, rax; dwBytes
0x18003dd08  mov     rcx, r15; Src
0x18003dd0b  call    WfpBufferCopy
0x18003dd10  mov     rbx, rax
0x18003dd13  test    rax, rax
0x18003dd16  jnz     loc_18003DE40
0x18003dd1c  lea     r9, [rdi+20h]
0x18003dd20  mov     rcx, rbp
0x18003dd23  lea     edx, [rax+10h]
0x18003dd26  lea     r8d, [rax+8]
0x18003dd2a  call    WfpMemAllocArray
0x18003dd2f  mov     rbx, rax
0x18003dd32  test    rax, rax
0x18003dd35  jnz     loc_18003DE40
0x18003dd3b  xor     esi, esi
0x18003dd3d  xor     r8d, r8d
0x18003dd40  test    ebp, ebp
0x18003dd42  jz      short loc_18003DD6F
0x18003dd44  mov     rcx, [rdi+20h]
0x18003dd48  mov     edx, r8d
0x18003dd4b  inc     r8d
0x18003dd4e  shl     rdx, 4
0x18003dd52  mov     rax, [rdx+r15]
0x18003dd56  movups  xmm0, xmmword ptr [rax]
0x18003dd59  movdqu  xmmword ptr [rcx+rdx], xmm0
0x18003dd5e  mov     eax, [rdx+r15+0Ch]
0x18003dd63  or      eax, [rdx+r15+8]
0x18003dd68  or      esi, eax
0x18003dd6a  cmp     r8d, ebp
0x18003dd6d  jb      short loc_18003DD44
0x18003dd6f  mov     [rdi+28h], r13
0x18003dd73  xor     r9d, r9d; lpName
0x18003dd76  xor     r8d, r8d; bInitialState
0x18003dd79  mov     qword ptr [rdi+30h], 0
0x18003dd81  xor     edx, edx; bManualReset
0x18003dd83  xor     ecx, ecx; lpEventAttributes
0x18003dd85  call    cs:__imp_CreateEventW
0x18003dd8b  mov     [rdi+38h], rax
0x18003dd8f  test    rax, rax
0x18003dd92  jnz     short loc_18003DDA6
0x18003dd94  call    cs:__imp_GetLastError
0x18003dd9a  lea     rdx, aCreateeventw; "CreateEventW"
0x18003dda1  jmp     loc_18003DCD7
0x18003dda6  mov     rdx, rax; NotificationEventHandle
0x18003dda9  mov     ecx, 1; InformationClass
0x18003ddae  call    cs:__imp_LsaRegisterPolicyChangeNotification
0x18003ddb4  test    eax, eax
0x18003ddb6  jns     short loc_18003DDC9
0x18003ddb8  mov     r8d, eax
0x18003ddbb  lea     rdx, aLsaregisterpol_0; "LsaRegisterPolicyChangeNotification"
0x18003ddc2  call    WfpReportSysErrorAsNtStatus
0x18003ddc7  jmp     short loc_18003DE38
0x18003ddc9  mov     dword ptr [rdi+40h], 1
0x18003ddd0  lea     rdx, WfpAuditPolicyNotifyOnChange
0x18003ddd7  mov     rcx, [rdi+38h]
0x18003dddb  or      r9d, 0FFFFFFFFh
0x18003dddf  mov     r8, rdi
0x18003dde2  mov     [rsp+88h+var_68], 10h
0x18003ddea  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18003ddf0  mov     [rdi+48h], rax
0x18003ddf4  test    rax, rax
0x18003ddf7  jnz     short loc_18003DE0B
0x18003ddf9  call    cs:__imp_GetLastError
0x18003ddff  lea     rdx, aRegisterwaitfo; "RegisterWaitForSingleObjectEx"
0x18003de06  jmp     loc_18003DCD7
0x18003de0b  not     esi
0x18003de0d  xor     edx, edx
0x18003de0f  mov     rcx, rdi
0x18003de12  mov     [rdi+50h], esi
0x18003de15  call    WfpAuditPolicyNotifyOnChange
0x18003de1a  mov     [r12], rdi
0x18003de1e  jmp     short loc_18003DE5E
0x18003de20  mov     r9d, 1
0x18003de26  lea     rdx, aUlonglongmult; "ULongLongMult"
0x18003de2d  mov     r8d, 80070216h
0x18003de33  call    WfpReportSysErrorAsHResult
0x18003de38  mov     rbx, rax
0x18003de3b  test    rax, rax
0x18003de3e  jz      short loc_18003DE5E
0x18003de40  lea     rcx, [rsp+88h+var_58]
0x18003de45  call    WfpAuditPolicyNotifyDestroy
0x18003de4a  test    rbx, rbx
0x18003de4d  jz      short loc_18003DE5E
0x18003de4f  lea     rdx, aWfpauditpolicy; "WfpAuditPolicyNotifyCreate"
0x18003de56  mov     rcx, rbx
0x18003de59  call    WfpReportError
0x18003de5e  mov     rax, rbx
0x18003de61  mov     rcx, [rsp+88h+var_48]
0x18003de66  xor     rcx, rsp; StackCookie
0x18003de69  call    __security_check_cookie
0x18003de6e  mov     rbx, [rsp+88h+arg_18]
0x18003de76  add     rsp, 50h
0x18003de7a  pop     r15
0x18003de7c  pop     r14
0x18003de7e  pop     r13
0x18003de80  pop     r12
0x18003de82  pop     rdi
0x18003de83  pop     rsi
0x18003de84  pop     rbp
0x18003de85  retn
```
