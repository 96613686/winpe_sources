# BaseBrokerCallbackWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800187f0`
- end: `0x18001889e`
- name: `?BaseBrokerCallbackWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `174`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e9c8`
- `0x18000ea40`
- `0x1800187f0`
- `0x1800188cc`
- `0x180020c30`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180018855`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001885e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018855`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001885e`

## pseudocode

```c
void __fastcall BaseBrokerCallbackWorker(PTP_CALLBACK_INSTANCE Instance, unsigned int *Context, __int64 Work)
{
  void *v4; // rcx
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-28h] BYREF

  if ( Context )
  {
    if ( (byte_180030D03 & 2) != 0 )
      McTemplateU0qqq_EventWriteTransfer(
        (__int64)Instance,
        (const EVENT_DESCRIPTOR *)BaseBrokerWorker,
        *Context,
        Context[1],
        Context[2]);
    CScheduleMgr::BrokerCallback(
      Instance,
      (struct _WNF_STATE_NAME *)Context,
      Work,
      *((struct _GUID **)Context + 2),
      *((void *const *)Context + 3));
    v4 = (void *)*((_QWORD *)Context + 3);
    if ( v4 )
      operator delete(v4);
    operator delete(Context);
  }
  else if ( (byte_180030D04 & 1) != 0 )
  {
    McGenEventWrite_EventWriteTransfer((__int64)Instance, (const EVENT_DESCRIPTOR *)ErrorNullPointer, Work, 1u, &v5);
  }
}

```

## disassembly

```asm
0x1800187f0  push    rbx
0x1800187f2  sub     rsp, 50h
0x1800187f6  mov     rax, cs:__security_cookie
0x1800187fd  xor     rax, rsp
0x180018800  mov     [rsp+58h+var_18], rax
0x180018805  mov     rbx, rdx
0x180018808  test    rdx, rdx
0x18001880b  jz      short loc_180018866
0x18001880d  test    cs:byte_180030D03, 2
0x180018814  jz      short loc_180018830
0x180018816  mov     eax, [rdx+8]
0x180018819  mov     r9d, [rdx+4]
0x18001881d  mov     r8d, [rdx]
0x180018820  lea     rdx, BaseBrokerWorker
0x180018827  mov     dword ptr [rsp+58h+var_38], eax
0x18001882b  call    McTemplateU0qqq_EventWriteTransfer
0x180018830  mov     eax, [rbx+20h]
0x180018833  mov     rdx, rbx; struct _WNF_STATE_NAME *
0x180018836  mov     r9, [rbx+10h]; void *
0x18001883a  mov     [rsp+58h+var_30], eax; unsigned int
0x18001883e  mov     rax, [rbx+18h]
0x180018842  mov     [rsp+58h+var_38], rax; void *
0x180018847  call    ?BrokerCallback@CScheduleMgr@@QEAAXPEAU_WNF_STATE_NAME@@KPEAXQEAXK@Z; CScheduleMgr::BrokerCallback(_WNF_STATE_NAME *,ulong,void *,void * const,ulong)
0x18001884c  mov     rcx, [rbx+18h]
0x180018850  test    rcx, rcx
0x180018853  jz      short loc_18001885B
0x180018855  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001885b  mov     rcx, rbx
0x18001885e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018864  jmp     short loc_18001888B
0x180018866  mov     r9d, 1
0x18001886c  test    cs:byte_180030D04, r9b
0x180018873  jz      short loc_18001888B
0x180018875  lea     rax, [rsp+58h+var_28]
0x18001887a  lea     rdx, ErrorNullPointer
0x180018881  mov     [rsp+58h+var_38], rax
0x180018886  call    McGenEventWrite_EventWriteTransfer
0x18001888b  mov     rcx, [rsp+58h+var_18]
0x180018890  xor     rcx, rsp; StackCookie
0x180018893  call    __security_check_cookie
0x180018898  add     rsp, 50h
0x18001889c  pop     rbx
0x18001889d  retn
```
