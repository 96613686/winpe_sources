# FwpmSecureSocketDeleteByKeyAsync0

- ea: `0x180056a30`
- end: `0x180056b35`
- name: `FwpmSecureSocketDeleteByKeyAsync0`
- size: `261`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180004904`
- `0x1800050cc`
- `0x180008480`
- `0x180008f10`
- `0x18000c524`
- `0x18000dfac`
- `0x180011830`
- `0x180056a30`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180056a52`
- `ntoskrnl!KeGetCurrentIrql` at `0x180056a52`
- `msrpc!RpcAsyncInitializeHandle` at `0x180056aad`
- `msrpc!RpcAsyncInitializeHandle` at `0x180056aad`

## string_xrefs

- `0x180056a68`: `FwpmSecureSocketDeleteByKeyAsync0`
- `0x180056b01`: `FwppProxySecureSocketDeleteByKey`

## pseudocode

```c
__int64 __fastcall FwpmSecureSocketDeleteByKeyAsync0(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rbx
  PRPC_ASYNC_STATE v15; // rdi
  RPC_STATUS v16; // eax
  __int64 v17; // rcx
  int Pointer; // eax
  CLIENT_CALL_RETURN v19; // rcx
  PRPC_ASYNC_STATE pAsync[9]; // [rsp+30h] [rbp-48h] BYREF

  pAsync[0] = 0;
  if ( KeGetCurrentIrql() )
  {
    v11 = 3221225659LL;
LABEL_3:
    v12 = WfpReportAppErrorAsNtStatus(v9, (__int64)"FwpmSecureSocketDeleteByKeyAsync0", v11);
    goto LABEL_12;
  }
  if ( !a1 || !a3 )
  {
    v11 = 3223453724LL;
    goto LABEL_3;
  }
  v14 = WfpPoolAllocQualified(104, v8, v10, (__int64 *)pAsync);
  if ( v14 )
  {
LABEL_13:
    WfpNamedPoolFree(v13, (PVOID *)pAsync);
    return WfpErrorToFwpErr(v14);
  }
  v15 = pAsync[0];
  v16 = RpcAsyncInitializeHandle(pAsync[0], 0x58u);
  if ( v16 )
  {
    v12 = WfpReportSysErrorAsRpcStatus(v17, (int)"RpcAsyncInitializeHandle", v16);
  }
  else
  {
    v15->NotificationType = RpcNotificationTypeCallback;
    v15->u.Event = (PKEVENT)FwppSecureSocketDeleteNotify;
    *(_QWORD *)&v15[1].Size = a3;
    *(_QWORD *)&v15[1].Lock = a4;
    Pointer = (unsigned int)FwppProxySecureSocketDeleteByKey((__int64)v15, *a1, a1[1], a2).Pointer;
    if ( Pointer >= 0 )
      return WfpErrorToFwpErr(v14);
    v12 = WfpReportSysErrorAsNtStatus(v19.Simple, (int)"FwppProxySecureSocketDeleteByKey", Pointer);
  }
LABEL_12:
  v14 = v12;
  if ( v12 )
    goto LABEL_13;
  return WfpErrorToFwpErr(v14);
}

```

## disassembly

```asm
0x180056a30  push    rbx
0x180056a32  push    rbp
0x180056a33  push    rsi
0x180056a34  push    rdi
0x180056a35  push    r14
0x180056a37  push    r15
0x180056a39  sub     rsp, 48h
0x180056a3d  mov     r14, r9
0x180056a40  mov     [rsp+78h+pAsync], 0
0x180056a49  mov     rbp, r8
0x180056a4c  mov     r15, rdx
0x180056a4f  mov     rsi, rcx
0x180056a52  call    cs:__imp_KeGetCurrentIrql
0x180056a59  nop     dword ptr [rax+rax+00h]
0x180056a5e  test    al, al
0x180056a60  jz      short loc_180056A79
0x180056a62  mov     r8d, 0C00000BBh
0x180056a68  lea     rdx, aFwpmsecuresock; "FwpmSecureSocketDeleteByKeyAsync0"
0x180056a6f  call    WfpReportAppErrorAsNtStatus
0x180056a74  jmp     loc_180056B0D
0x180056a79  test    rsi, rsi
0x180056a7c  jnz     short loc_180056A86
0x180056a7e  mov     r8d, 0C022001Ch
0x180056a84  jmp     short loc_180056A68
0x180056a86  test    rbp, rbp
0x180056a89  jz      short loc_180056A7E
0x180056a8b  lea     r9, [rsp+78h+pAsync]
0x180056a90  mov     ecx, 68h ; 'h'
0x180056a95  call    WfpPoolAllocQualified
0x180056a9a  mov     rbx, rax
0x180056a9d  test    rax, rax
0x180056aa0  jnz     short loc_180056B15
0x180056aa2  mov     rdi, [rsp+78h+pAsync]
0x180056aa7  lea     edx, [rax+58h]; Size
0x180056aaa  mov     rcx, rdi; pAsync
0x180056aad  call    cs:__imp_RpcAsyncInitializeHandle
0x180056ab4  nop     dword ptr [rax+rax+00h]
0x180056ab9  test    eax, eax
0x180056abb  jz      short loc_180056ACE
0x180056abd  mov     r8d, eax
0x180056ac0  lea     rdx, aRpcasyncinitia; "RpcAsyncInitializeHandle"
0x180056ac7  call    WfpReportSysErrorAsRpcStatus
0x180056acc  jmp     short loc_180056B0D
0x180056ace  mov     dword ptr [rdi+2Ch], 2
0x180056ad5  lea     rax, FwppSecureSocketDeleteNotify
0x180056adc  mov     [rdi+30h], rax
0x180056ae0  mov     r9, r15
0x180056ae3  mov     [rdi+58h], rbp
0x180056ae7  mov     rcx, rdi
0x180056aea  mov     [rdi+60h], r14
0x180056aee  mov     r8, [rsi+8]
0x180056af2  mov     rdx, [rsi]
0x180056af5  call    FwppProxySecureSocketDeleteByKey
0x180056afa  test    eax, eax
0x180056afc  jns     short loc_180056B1F
0x180056afe  mov     r8d, eax
0x180056b01  lea     rdx, aFwppproxysecur; "FwppProxySecureSocketDeleteByKey"
0x180056b08  call    WfpReportSysErrorAsNtStatus
0x180056b0d  mov     rbx, rax
0x180056b10  test    rax, rax
0x180056b13  jz      short loc_180056B1F
0x180056b15  lea     rdx, [rsp+78h+pAsync]
0x180056b1a  call    WfpNamedPoolFree
0x180056b1f  mov     rcx, rbx
0x180056b22  call    WfpErrorToFwpErr
0x180056b27  add     rsp, 48h
0x180056b2b  pop     r15
0x180056b2d  pop     r14
0x180056b2f  pop     rdi
0x180056b30  pop     rsi
0x180056b31  pop     rbp
0x180056b32  pop     rbx
0x180056b33  retn
```
