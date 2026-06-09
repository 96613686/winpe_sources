# TransmitQueue::EvtRequestCompletionRoutineThunk(WDFREQUEST__ *,WDFIOTARGET__ *,_WDF_REQUEST_COMPLETION_PARAMS *,void *)

- ea: `0x14000a6b0`
- end: `0x14000a894`
- name: `?EvtRequestCompletionRoutineThunk@TransmitQueue@@CAXPEAUWDFREQUEST__@@PEAUWDFIOTARGET__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@PEAX@Z`
- size: `484`
- prototype: `void __fastcall(struct WDFREQUEST__ *, struct WDFIOTARGET__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000a6b0`
- `0x14000a960`
- `0x14000aa48`
- `0x14000ab3c`
- `0x14000de00`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x14000a872`
- `ntoskrnl!ExFreePool` at `0x14000a872`

## pseudocode

```c
void __fastcall TransmitQueue::EvtRequestCompletionRoutineThunk(
        struct WDFREQUEST__ *a1,
        struct WDFIOTARGET__ *a2,
        struct _WDF_REQUEST_COMPLETION_PARAMS *a3,
        unsigned int *a4)
{
  __int64 v7; // rax
  __int64 v8; // rbp
  int Status; // ebx
  int v10; // edx
  int v11; // r8d
  __int64 v12; // r8
  __int64 v13; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v14; // [rsp+A8h] [rbp+20h] BYREF

  v7 = ((__int64 (__fastcall *)(_LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[141].Flink)(
         WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
         a1);
  v8 = ((__int64 (__fastcall *)(_LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[101].Flink)(
         WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
         v7,
         off_1400130B0);
  Status = a3->IoStatus.Status;
  ((void (__fastcall *)(__int64, struct WDFREQUEST__ *))qword_1400132B8)(BthDriverGlobals, a1);
  v14 = 0;
  v13 = 0;
  ((void (__fastcall *)(__int64, struct WDFREQUEST__ *, __int64 *, __int64 *))qword_1400132C0)(
    BthDriverGlobals,
    a1,
    &v14,
    &v13);
  if ( Status < 0 )
  {
    LOBYTE(v10) = 1;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      LOBYTE(v10) = 0;
    WPP_RECORDER_AND_TRACE_SF_qqLdD(
      WPP_GLOBAL_Control->AttachedDevice,
      v10,
      v11,
      *(_QWORD *)(*(_QWORD *)(v8 + 8) + 8LL));
  }
  else
  {
    v12 = a4[9];
    if ( v13 == v12 )
    {
      LOBYTE(v10) = 1;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        LOBYTE(v10) = 0;
      WPP_RECORDER_AND_TRACE_SF_qqL(
        WPP_GLOBAL_Control->AttachedDevice,
        v10,
        v12,
        *(_QWORD *)(*(_QWORD *)(v8 + 8) + 8LL));
    }
    else
    {
      LOBYTE(v10) = 1;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        LOBYTE(v10) = 0;
      WPP_RECORDER_AND_TRACE_SF_qqLD(
        WPP_GLOBAL_Control->AttachedDevice,
        v10,
        v12,
        *(_QWORD *)(*(_QWORD *)(v8 + 8) + 8LL));
      Status = -1073741762;
    }
  }
  ((void (__fastcall *)(_LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[131].Blink)(
    WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
    a1,
    (unsigned int)Status);
  ExFreePool(a4);
}

```

## disassembly

```asm
0x14000a6b0  mov     [rsp+arg_0], rbx
0x14000a6b5  mov     [rsp+arg_8], rbp
0x14000a6ba  push    rsi
0x14000a6bb  push    rdi
0x14000a6bc  push    r14
0x14000a6be  sub     rsp, 70h
0x14000a6c2  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x14000a6c9  mov     rdi, rcx
0x14000a6cc  mov     rdx, rcx
0x14000a6cf  mov     rsi, r9
0x14000a6d2  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14000a6d9  mov     rbx, r8
0x14000a6dc  mov     rax, [rax+8D0h]
0x14000a6e3  call    _guard_dispatch_icall
0x14000a6e8  mov     rdx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x14000a6ef  mov     r10, rax
0x14000a6f2  mov     r8, cs:off_1400130B0
0x14000a6f9  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14000a700  mov     rax, [rdx+650h]
0x14000a707  mov     rdx, r10
0x14000a70a  call    _guard_dispatch_icall
0x14000a70f  mov     rcx, cs:BthDriverGlobals
0x14000a716  mov     rbp, rax
0x14000a719  mov     rax, cs:qword_1400132B8
0x14000a720  mov     rdx, rdi
0x14000a723  mov     ebx, [rbx+8]
0x14000a726  call    _guard_dispatch_icall
0x14000a72b  mov     rcx, cs:BthDriverGlobals
0x14000a732  lea     r9, [rsp+88h+arg_10]
0x14000a73a  mov     r14d, eax
0x14000a73d  mov     [rsp+88h+arg_18], 0
0x14000a749  mov     rax, cs:qword_1400132C0
0x14000a750  lea     r8, [rsp+88h+arg_18]
0x14000a758  mov     rdx, rdi
0x14000a75b  mov     [rsp+88h+arg_10], 0
0x14000a767  call    _guard_dispatch_icall
0x14000a76c  test    ebx, ebx
0x14000a76e  js      loc_14000A809
0x14000a774  mov     r8d, [rsi+24h]
0x14000a778  cmp     [rsp+88h+arg_10], r8
0x14000a780  jz      short loc_14000A7CC
0x14000a782  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a789  mov     dl, 1
0x14000a78b  mov     eax, [rcx+2Ch]
0x14000a78e  test    dl, al
0x14000a790  jz      short loc_14000A798
0x14000a792  cmp     byte ptr [rcx+29h], 2
0x14000a796  jnb     short loc_14000A79A
0x14000a798  xor     dl, dl
0x14000a79a  mov     r9, [rbp+8]
0x14000a79e  mov     rcx, [rcx+18h]
0x14000a7a2  mov     [rsp+88h+var_30], r8d
0x14000a7a7  mov     [rsp+88h+var_38], r14d
0x14000a7ac  mov     rax, [r9]
0x14000a7af  mov     r9, [r9+8]
0x14000a7b3  mov     [rsp+88h+var_40], rdi
0x14000a7b8  mov     [rsp+88h+var_48], rax
0x14000a7bd  call    WPP_RECORDER_AND_TRACE_SF_qqLD
0x14000a7c2  mov     ebx, 0C000003Eh
0x14000a7c7  jmp     loc_14000A84F
0x14000a7cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a7d3  mov     dl, 1
0x14000a7d5  mov     eax, [rcx+2Ch]
0x14000a7d8  test    dl, al
0x14000a7da  jz      short loc_14000A7E2
0x14000a7dc  cmp     byte ptr [rcx+29h], 4
0x14000a7e0  jnb     short loc_14000A7E4
0x14000a7e2  xor     dl, dl
0x14000a7e4  mov     r9, [rbp+8]
0x14000a7e8  mov     rcx, [rcx+18h]
0x14000a7ec  mov     [rsp+88h+var_38], r14d
0x14000a7f1  mov     [rsp+88h+var_40], rdi
0x14000a7f6  mov     rax, [r9]
0x14000a7f9  mov     r9, [r9+8]
0x14000a7fd  mov     [rsp+88h+var_48], rax
0x14000a802  call    WPP_RECORDER_AND_TRACE_SF_qqL
0x14000a807  jmp     short loc_14000A84F
0x14000a809  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a810  mov     dl, 1
0x14000a812  mov     eax, [rcx+2Ch]
0x14000a815  test    dl, al
0x14000a817  jz      short loc_14000A81F
0x14000a819  cmp     byte ptr [rcx+29h], 2
0x14000a81d  jnb     short loc_14000A821
0x14000a81f  xor     dl, dl
0x14000a821  mov     r9, [rbp+8]
0x14000a825  mov     eax, [rsi+4]
0x14000a828  mov     rcx, [rcx+18h]
0x14000a82c  mov     [rsp+88h+var_28], eax
0x14000a830  mov     rax, [r9]
0x14000a833  mov     r9, [r9+8]
0x14000a837  mov     [rsp+88h+var_30], ebx
0x14000a83b  mov     [rsp+88h+var_38], r14d
0x14000a840  mov     [rsp+88h+var_40], rdi
0x14000a845  mov     [rsp+88h+var_48], rax
0x14000a84a  call    WPP_RECORDER_AND_TRACE_SF_qqLdD
0x14000a84f  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x14000a856  mov     r8d, ebx
0x14000a859  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14000a860  mov     rdx, rdi
0x14000a863  mov     rax, [rax+838h]
0x14000a86a  call    _guard_dispatch_icall
0x14000a86f  mov     rcx, rsi; P
0x14000a872  call    cs:__imp_ExFreePool
0x14000a879  nop     dword ptr [rax+rax+00h]
0x14000a87e  lea     r11, [rsp+88h+var_18]
0x14000a883  mov     rbx, [r11+20h]
0x14000a887  mov     rbp, [r11+28h]
0x14000a88b  mov     rsp, r11
0x14000a88e  pop     r14
0x14000a890  pop     rdi
0x14000a891  pop     rsi
0x14000a892  retn
```
