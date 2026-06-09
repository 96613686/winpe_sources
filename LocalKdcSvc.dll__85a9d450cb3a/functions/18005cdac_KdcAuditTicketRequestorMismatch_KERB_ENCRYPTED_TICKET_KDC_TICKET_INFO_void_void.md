# KdcAuditTicketRequestorMismatch(KERB_ENCRYPTED_TICKET *,_KDC_TICKET_INFO *,void *,void *)

- ea: `0x18005cdac`
- end: `0x18005cf31`
- name: `?KdcAuditTicketRequestorMismatch@@YAXPEAUKERB_ENCRYPTED_TICKET@@PEAU_KDC_TICKET_INFO@@PEAX2@Z`
- size: `389`
- prototype: `void __fastcall(struct KERB_ENCRYPTED_TICKET *, struct _KDC_TICKET_INFO *, PSID pSid, PSID)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005e9ac`

## callees

- `0x18000e440`
- `0x1800206c0`
- `0x1800206e8`
- `0x180047dd0`
- `0x18005bb6c`
- `0x18005cdac`
- `0x180066988`
- `0x18007d4b0`
- `0x18007d714`

## import_xrefs

- `ntdll!RtlConvertSidToUnicodeString` at `0x18005cea9`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18005ceb9`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18005cea9`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18005ceb9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall KdcAuditTicketRequestorMismatch(
        struct KERB_ENCRYPTED_TICKET *a1,
        struct _KDC_TICKET_INFO *a2,
        PSID pSid,
        PSID a4)
{
  __int64 v8; // rax
  unsigned __int16 *LogonServerFromTgtPac; // rax
  int v10; // r8d
  __int64 v11[2]; // [rsp+60h] [rbp-59h] BYREF
  __int64 v12[2]; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING v13; // [rsp+80h] [rbp-39h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+90h] [rbp-29h] BYREF
  _BYTE v15[48]; // [rsp+A0h] [rbp-19h] BYREF
  char v16; // [rsp+D0h] [rbp+17h] BYREF
  int v17; // [rsp+120h] [rbp+67h] BYREF
  unsigned __int16 *v18; // [rsp+128h] [rbp+6Fh] BYREF

  v17 = 0;
  *(_OWORD *)v11 = 0;
  *(_OWORD *)v12 = 0;
  UnicodeString = 0;
  v13 = 0;
  v18 = 0;
  v8 = lambda_bde1109c27f1d473909aeaf58a3f4245_::_lambda_bde1109c27f1d473909aeaf58a3f4245_(
         (unsigned int)&v16,
         (unsigned int)v11,
         (unsigned int)v12,
         (unsigned int)&v18,
         (__int64)&UnicodeString,
         (__int64)&v13);
  wil::scope_exit__lambda_bde1109c27f1d473909aeaf58a3f4245___(v15, v8);
  KerbConvertPrincipalNameToString(v11, &v17, (char *)a1 + 56);
  KerbConvertRealmToUnicodeString(v12, (char *)a1 + 48);
  LogonServerFromTgtPac = KdcGetLogonServerFromTgtPac(a1);
  v18 = LogonServerFromTgtPac;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S_sid__sid_ZZZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (int)v12,
      v10,
      (int)LogonServerFromTgtPac,
      a4,
      pSid,
      (__int64)v12,
      (__int64)v11,
      (__int64)a2);
  RtlConvertSidToUnicodeString(&UnicodeString, pSid, 1u);
  RtlConvertSidToUnicodeString(&v13, a4, 1u);
  ReportServiceEvent(
    1u,
    0x80000026,
    0,
    0,
    6u,
    v18,
    v12[1],
    v11[1],
    *((_QWORD *)a2 + 1),
    UnicodeString.Buffer,
    v13.Buffer);
  wil::details::lambda_call__lambda_bc883792d872c7e5ea321be7b3de5a4e___::_lambda_call__lambda_bc883792d872c7e5ea321be7b3de5a4e___(v15);
}

```

## disassembly

```asm
0x18005cdac  mov     [rsp-8+arg_10], rbx
0x18005cdb1  mov     [rsp-8+arg_18], rsi
0x18005cdb6  push    rbp
0x18005cdb7  push    rdi
0x18005cdb8  push    r14
0x18005cdba  lea     rbp, [rsp-47h]
0x18005cdbf  sub     rsp, 100h
0x18005cdc6  mov     rdi, r9
0x18005cdc9  mov     rsi, r8
0x18005cdcc  mov     r14, rdx
0x18005cdcf  mov     rbx, rcx
0x18005cdd2  mov     [rbp+57h+arg_0], 0
0x18005cdd9  xorps   xmm0, xmm0
0x18005cddc  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x18005cde0  xorps   xmm1, xmm1
0x18005cde3  movups  xmmword ptr [rbp+57h+var_A0], xmm1
0x18005cde7  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x18005cdeb  movups  xmmword ptr [rbp+57h+var_90.Length], xmm1
0x18005cdef  mov     [rbp+57h+arg_8], 0
0x18005cdf7  lea     rax, [rbp+57h+var_90]
0x18005cdfb  mov     [rsp+110h+pSid], rax
0x18005ce00  lea     rax, [rbp+57h+UnicodeString]
0x18005ce04  mov     [rsp+110h+var_F0], rax
0x18005ce09  lea     r9, [rbp+57h+arg_8]
0x18005ce0d  lea     r8, [rbp+57h+var_A0]
0x18005ce11  lea     rdx, [rbp+57h+var_B0]
0x18005ce15  lea     rcx, [rbp+57h+var_40]
0x18005ce19  call    _lambda_bde1109c27f1d473909aeaf58a3f4245____lambda_bde1109c27f1d473909aeaf58a3f4245_
0x18005ce1e  mov     rdx, rax
0x18005ce21  lea     rcx, [rbp+57h+var_70]
0x18005ce25  call    wil__scope_exit__lambda_bde1109c27f1d473909aeaf58a3f4245___
0x18005ce2a  nop
0x18005ce2b  lea     r8, [rbx+38h]
0x18005ce2f  lea     rdx, [rbp+57h+arg_0]
0x18005ce33  lea     rcx, [rbp+57h+var_B0]
0x18005ce37  call    KerbConvertPrincipalNameToString
0x18005ce3c  lea     rdx, [rbx+30h]
0x18005ce40  lea     rcx, [rbp+57h+var_A0]
0x18005ce44  call    KerbConvertRealmToUnicodeString
0x18005ce49  mov     rcx, rbx; struct KERB_ENCRYPTED_TICKET *
0x18005ce4c  call    ?KdcGetLogonServerFromTgtPac@@YAPEAGPEAUKERB_ENCRYPTED_TICKET@@@Z; KdcGetLogonServerFromTgtPac(KERB_ENCRYPTED_TICKET *)
0x18005ce51  mov     [rbp+57h+arg_8], rax
0x18005ce55  lea     rdx, WPP_GLOBAL_Control
0x18005ce5c  mov     ebx, 1
0x18005ce61  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ce68  cmp     rcx, rdx
0x18005ce6b  jz      short loc_18005CE9F
0x18005ce6d  test    [rcx+1Ch], bl
0x18005ce70  jz      short loc_18005CE9F
0x18005ce72  mov     [rsp+110h+var_D0], r14; __int64
0x18005ce77  lea     rdx, [rbp+57h+var_B0]
0x18005ce7b  mov     [rsp+110h+var_D8], rdx; __int64
0x18005ce80  lea     rdx, [rbp+57h+var_A0]; int
0x18005ce84  mov     [rsp+110h+var_E0], rdx; __int64
0x18005ce89  mov     [rsp+110h+pSid], rsi; pSid
0x18005ce8e  mov     [rsp+110h+var_F0], rdi; PSID
0x18005ce93  mov     r9, rax; int
0x18005ce96  mov     rcx, [rcx+10h]; int
0x18005ce9a  call    WPP_SF_S_sid__sid_ZZZ
0x18005ce9f  mov     r8b, bl; AllocateDestinationString
0x18005cea2  mov     rdx, rsi; Sid
0x18005cea5  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18005cea9  call    cs:__imp_RtlConvertSidToUnicodeString
0x18005ceaf  mov     r8b, bl; AllocateDestinationString
0x18005ceb2  mov     rdx, rdi; Sid
0x18005ceb5  lea     rcx, [rbp+57h+var_90]; UnicodeString
0x18005ceb9  call    cs:__imp_RtlConvertSidToUnicodeString
0x18005cebf  mov     rax, [rbp+57h+var_90.Buffer]
0x18005cec3  mov     [rsp+110h+var_C0], rax
0x18005cec8  mov     rax, [rbp+57h+UnicodeString.Buffer]
0x18005cecc  mov     [rsp+110h+var_C8], rax
0x18005ced1  mov     rax, [r14+8]
0x18005ced5  mov     [rsp+110h+var_D0], rax
0x18005ceda  mov     rax, [rbp+57h+var_B0+8]
0x18005cede  mov     [rsp+110h+var_D8], rax
0x18005cee3  mov     rax, [rbp+57h+var_A0+8]
0x18005cee7  mov     [rsp+110h+var_E0], rax
0x18005ceec  mov     rax, [rbp+57h+arg_8]
0x18005cef0  mov     [rsp+110h+pSid], rax
0x18005cef5  mov     dword ptr [rsp+110h+var_F0], 6; unsigned int
0x18005cefd  xor     r9d, r9d; void *
0x18005cf00  xor     r8d, r8d; unsigned int
0x18005cf03  mov     edx, 80000026h; unsigned int
0x18005cf08  mov     ecx, ebx; unsigned __int16
0x18005cf0a  call    ?ReportServiceEvent@@YAKGKKPEAXKZZ; ReportServiceEvent(ushort,ulong,ulong,void *,ulong,...)
0x18005cf0f  nop
0x18005cf10  lea     rcx, [rbp+57h+var_70]
0x18005cf14  call    wil__details__lambda_call__lambda_bc883792d872c7e5ea321be7b3de5a4e______lambda_call__lambda_bc883792d872c7e5ea321be7b3de5a4e___
0x18005cf19  lea     r11, [rsp+110h+var_10]
0x18005cf21  mov     rbx, [r11+30h]
0x18005cf25  mov     rsi, [r11+38h]
0x18005cf29  mov     rsp, r11
0x18005cf2c  pop     r14
0x18005cf2e  pop     rdi
0x18005cf2f  pop     rbp
0x18005cf30  retn
```
