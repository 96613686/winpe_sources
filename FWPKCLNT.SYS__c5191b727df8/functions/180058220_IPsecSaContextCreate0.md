# IPsecSaContextCreate0

- ea: `0x180058220`
- end: `0x180058324`
- name: `IPsecSaContextCreate0`
- size: `260`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, const IPSEC_TRAFFIC0 *outboundTraffic, UINT64 *inboundFilterId, UINT64 *id)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180004904`
- `0x1800050cc`
- `0x18000891c`
- `0x180008f10`
- `0x18000c9b4`
- `0x1800208c0`
- `0x180058220`
- `0x180058330`
- `0x180063c78`
- `0x180065180`

## string_xrefs

- `0x180058247`: `IPsecSaContextCreate0`
- `0x1800582f6`: `IPsecSaContextCreate1`
- `0x1800582c6`: `FwppAllocAndDeepCopyToVerIndependent_IPSEC_TRAFFIC0`

## pseudocode

```c
NTSTATUS __stdcall IPsecSaContextCreate0(
        HANDLE engineHandle,
        const IPSEC_TRAFFIC0 *outboundTraffic,
        UINT64 *inboundFilterId,
        UINT64 *id)
{
  IPSEC_TRAFFIC1 *v4; // rsi
  __int64 v9; // rax
  __int64 v10; // rbx
  NTSTATUS v11; // eax
  __int64 v12; // rcx
  IPSEC_TRAFFIC1 *outboundTraffica; // [rsp+88h] [rbp+20h] BYREF

  v4 = 0;
  if ( !id )
  {
    v9 = WfpReportAppErrorAsNtStatus((__int64)engineHandle, (__int64)"IPsecSaContextCreate0", 3223453724LL);
LABEL_11:
    v10 = v9;
    goto LABEL_12;
  }
  outboundTraffica = 0;
  if ( outboundTraffic )
  {
    v10 = WfpPoolAllocNonPaged(72, 1886418758, &outboundTraffica);
    if ( v10
      || (memset(outboundTraffica, 0, sizeof(IPSEC_TRAFFIC1)),
          (v10 = FwppDeepCopyToVerIndependent_IPSEC_TRAFFIC0(outboundTraffic, outboundTraffica)) != 0) )
    {
      FwppDeepFree_IPSEC_TRAFFIC1(outboundTraffica);
      WfpReportError(v10, (int)"FwppAllocAndDeepCopyToVerIndependent_IPSEC_TRAFFIC0");
      goto LABEL_12;
    }
    v4 = outboundTraffica;
  }
  else
  {
    v10 = 0;
  }
  v11 = IPsecSaContextCreate1(engineHandle, v4, 0, inboundFilterId, id);
  if ( v11 < 0 )
  {
    v9 = WfpReportSysErrorAsNtStatus(v12, (int)"IPsecSaContextCreate1", v11);
    goto LABEL_11;
  }
LABEL_12:
  FwppDeepFree_IPSEC_TRAFFIC1(v4);
  return WfpErrorToFwpErr(v10);
}

```

## disassembly

```asm
0x180058220  push    rbx
0x180058222  push    rbp
0x180058223  push    rsi
0x180058224  push    r12
0x180058226  push    r14
0x180058228  push    r15
0x18005822a  sub     rsp, 38h
0x18005822e  xor     esi, esi
0x180058230  mov     r14, r9
0x180058233  mov     r15, r8
0x180058236  mov     rbp, rdx
0x180058239  mov     r12, rcx
0x18005823c  test    r9, r9
0x18005823f  jnz     short loc_180058258
0x180058241  mov     r8d, 0C022001Ch
0x180058247  lea     rdx, aIpsecsacontext_6; "IPsecSaContextCreate0"
0x18005824e  call    WfpReportAppErrorAsNtStatus
0x180058253  jmp     loc_180058302
0x180058258  mov     [rsp+68h+outboundTraffic], rsi
0x180058260  test    rbp, rbp
0x180058263  jz      short loc_1800582D7
0x180058265  lea     r8, [rsp+68h+outboundTraffic]
0x18005826d  mov     edx, 70707746h
0x180058272  mov     ecx, 48h ; 'H'
0x180058277  call    WfpPoolAllocNonPaged
0x18005827c  mov     rbx, rax
0x18005827f  test    rax, rax
0x180058282  jnz     short loc_1800582B9
0x180058284  mov     rcx, [rsp+68h+outboundTraffic]; void *
0x18005828c  lea     r8d, [rax+48h]; Size
0x180058290  xor     edx, edx; Val
0x180058292  call    memset
0x180058297  mov     rdx, [rsp+68h+outboundTraffic]
0x18005829f  mov     rcx, rbp
0x1800582a2  call    FwppDeepCopyToVerIndependent_IPSEC_TRAFFIC0
0x1800582a7  mov     rbx, rax
0x1800582aa  test    rax, rax
0x1800582ad  jnz     short loc_1800582B9
0x1800582af  mov     rsi, [rsp+68h+outboundTraffic]
0x1800582b7  jmp     short loc_1800582D9
0x1800582b9  mov     rcx, [rsp+68h+outboundTraffic]
0x1800582c1  call    FwppDeepFree_IPSEC_TRAFFIC1
0x1800582c6  lea     rdx, aFwppallocandde_60; "FwppAllocAndDeepCopyToVerIndependent_IP"...
0x1800582cd  mov     rcx, rbx
0x1800582d0  call    WfpReportError
0x1800582d5  jmp     short loc_180058305
0x1800582d7  xor     ebx, ebx
0x1800582d9  mov     r9, r15; inboundFilterId
0x1800582dc  mov     [rsp+68h+id], r14; id
0x1800582e1  xor     r8d, r8d; virtualIfTunnelInfo
0x1800582e4  mov     rdx, rsi; outboundTraffic
0x1800582e7  mov     rcx, r12; engineHandle
0x1800582ea  call    IPsecSaContextCreate1
0x1800582ef  test    eax, eax
0x1800582f1  jns     short loc_180058305
0x1800582f3  mov     r8d, eax
0x1800582f6  lea     rdx, aIpsecsacontext_0; "IPsecSaContextCreate1"
0x1800582fd  call    WfpReportSysErrorAsNtStatus
0x180058302  mov     rbx, rax
0x180058305  mov     rcx, rsi
0x180058308  call    FwppDeepFree_IPSEC_TRAFFIC1
0x18005830d  mov     rcx, rbx
0x180058310  call    WfpErrorToFwpErr
0x180058315  add     rsp, 38h
0x180058319  pop     r15
0x18005831b  pop     r14
0x18005831d  pop     r12
0x18005831f  pop     rsi
0x180058320  pop     rbp
0x180058321  pop     rbx
0x180058322  retn
```
