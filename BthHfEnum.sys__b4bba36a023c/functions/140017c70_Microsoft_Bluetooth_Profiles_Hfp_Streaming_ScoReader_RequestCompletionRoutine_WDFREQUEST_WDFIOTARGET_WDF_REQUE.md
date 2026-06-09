# Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::RequestCompletionRoutine(WDFREQUEST__ *,WDFIOTARGET__ *,_WDF_REQUEST_COMPLETION_PARAMS *,void *)

- ea: `0x140017c70`
- end: `0x140017caf`
- name: `?RequestCompletionRoutine@ScoReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@CAXPEAUWDFREQUEST__@@PEAUWDFIOTARGET__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@PEAX@Z`
- size: `63`
- prototype: `static void(struct WDFREQUEST__ *, struct WDFIOTARGET__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140017ba4`
- `0x14001ae00`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::RequestCompletionRoutine(
        struct WDFREQUEST__ *a1,
        struct WDFIOTARGET__ *a2,
        struct _WDF_REQUEST_COMPLETION_PARAMS *a3,
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader *a4)
{
  Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::DecrementPendingRequestCounter(a4);
  (***((void (__fastcall ****)(_QWORD, struct WDFREQUEST__ *, struct WDFIOTARGET__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *))a4
     + 1))(
    *((_QWORD *)a4 + 1),
    a1,
    a2,
    a3);
}

```

## disassembly

```asm
0x140017c70  push    rbx
0x140017c72  push    rbp
0x140017c73  push    rsi
0x140017c74  push    rdi
0x140017c75  sub     rsp, 38h
0x140017c79  mov     rbp, rcx
0x140017c7c  mov     rbx, r9
0x140017c7f  mov     rcx, r9; this
0x140017c82  mov     rdi, r8
0x140017c85  mov     rsi, rdx
0x140017c88  call    ?DecrementPendingRequestCounter@ScoReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEAAXXZ; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::DecrementPendingRequestCounter(void)
0x140017c8d  mov     rcx, [rbx+8]
0x140017c91  mov     r9, rdi
0x140017c94  mov     r8, rsi
0x140017c97  mov     rdx, rbp
0x140017c9a  mov     rax, [rcx]
0x140017c9d  mov     rax, [rax]
0x140017ca0  call    _guard_dispatch_icall
0x140017ca5  add     rsp, 38h
0x140017ca9  pop     rdi
0x140017caa  pop     rsi
0x140017cab  pop     rbp
0x140017cac  pop     rbx
0x140017cad  retn
```
