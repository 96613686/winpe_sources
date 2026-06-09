# CScheduleMgr::UnsubscribeWnfNotificationWaitForCompletionWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18000d840`
- end: `0x18000d8ba`
- name: `?UnsubscribeWnfNotificationWaitForCompletionWorker@CScheduleMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `122`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d840`
- `0x18000e970`
- `0x18000ea40`
- `0x180020c30`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000d869`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000d869`

## pseudocode

```c
void __fastcall CScheduleMgr::UnsubscribeWnfNotificationWaitForCompletionWorker(
        __int64 Instance,
        PVOID Context,
        __int64 Work)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-28h] BYREF

  if ( (byte_180030D07 & 8) != 0 )
    McTemplateU0q_EventWriteTransfer(Instance, UnsubscribeWnfThreadStart, (unsigned int)Context);
  if ( Context )
    RtlUnsubscribeWnfNotificationWaitForCompletion(Context);
  if ( (byte_180030D07 & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(Instance, (const EVENT_DESCRIPTOR *)UnsubscribeWnfThreadCompleted, Work, 1u, &v4);
}

```

## disassembly

```asm
0x18000d840  push    rbx
0x18000d842  sub     rsp, 50h
0x18000d846  mov     rax, cs:__security_cookie
0x18000d84d  xor     rax, rsp
0x18000d850  mov     [rsp+58h+var_18], rax
0x18000d855  test    cs:byte_180030D07, 8
0x18000d85c  mov     rbx, rdx
0x18000d85f  jnz     short loc_18000D88B
0x18000d861  test    rbx, rbx
0x18000d864  jz      short loc_18000D86F
0x18000d866  mov     rcx, rbx
0x18000d869  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000d86f  test    cs:byte_180030D07, 4
0x18000d876  jnz     short loc_18000D89C
0x18000d878  mov     rcx, [rsp+58h+var_18]
0x18000d87d  xor     rcx, rsp; StackCookie
0x18000d880  call    __security_check_cookie
0x18000d885  add     rsp, 50h
0x18000d889  pop     rbx
0x18000d88a  retn
0x18000d88b  mov     r8d, ebx
0x18000d88e  lea     rdx, UnsubscribeWnfThreadStart
0x18000d895  call    McTemplateU0q_EventWriteTransfer
0x18000d89a  jmp     short loc_18000D861
0x18000d89c  lea     rax, [rsp+58h+var_28]
0x18000d8a1  mov     r9d, 1
0x18000d8a7  lea     rdx, UnsubscribeWnfThreadCompleted
0x18000d8ae  mov     [rsp+58h+var_38], rax
0x18000d8b3  call    McGenEventWrite_EventWriteTransfer
0x18000d8b8  jmp     short loc_18000D878
```
