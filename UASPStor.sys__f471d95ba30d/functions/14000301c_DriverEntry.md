# DriverEntry

- ea: `0x14000301c`
- end: `0x140003161`
- name: `DriverEntry`
- size: `325`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x140017010`

## callees

- `0x14000301c`
- `0x14000dc00`

## import_xrefs

- `storport!StorPortInitialize` at `0x14000313f`
- `storport!StorPortInitialize` at `0x14000313f`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  _QWORD v5[26]; // [rsp+20h] [rbp-79h] BYREF

  memset(v5, 0, sizeof(v5));
  LODWORD(v5[0]) = 208;
  if ( DriverObject )
  {
    v5[3] = 0;
    v5[1] = UaspInitialize;
    v5[2] = UaspStartIo;
  }
  else
  {
    v5[1] = UaspDumpInitialize;
    v5[2] = UaspStartIo;
    v5[3] = UaspDumpHwInterrupt;
  }
  HIDWORD(v5[0]) = 0;
  v5[4] = &UaspFindAdapter;
  LOBYTE(v5[11]) = DriverObject != 0;
  v5[8] = 0x20000005B8LL;
  v5[9] = 16;
  v5[5] = UaspResetBus;
  v5[15] = UaspAdapterControl;
  gTracingEnabled = DriverObject != 0;
  *(_DWORD *)((char *)&v5[11] + 1) = 16843009;
  v5[25] = UaspUnitControl;
  LODWORD(v5[23]) = 5;
  v5[17] = UaspFreeAdapterResources;
  v5[18] = UaspProcessServiceRequest;
  v5[19] = guard_check_icall_nop;
  v5[20] = UaspInitializeTracing;
  v5[21] = UaspCleanupTracing;
  return ((__int64 (__fastcall *)(_DRIVER_OBJECT *, PUNICODE_STRING, _QWORD *, _QWORD))StorPortInitialize)(
           DriverObject,
           RegistryPath,
           v5,
           0);
}

```

## disassembly

```asm
0x14000301c  mov     [rsp-8+arg_0], rbx
0x140003021  mov     [rsp-8+arg_8], rdi
0x140003026  push    rbp
0x140003027  lea     rbp, [rsp-57h]
0x14000302c  sub     rsp, 0F0h
0x140003033  mov     rdi, rdx
0x140003036  mov     rbx, rcx
0x140003039  xor     edx, edx; Val
0x14000303b  lea     rcx, [rbp+57h+var_D0]; void *
0x14000303f  mov     r8d, 0D0h; Size
0x140003045  call    memset
0x14000304a  xor     ecx, ecx
0x14000304c  mov     [rbp+57h+var_D0], 0D0h
0x140003053  test    rbx, rbx
0x140003056  jz      short loc_140003074
0x140003058  lea     rax, UaspInitialize
0x14000305f  mov     [rbp+57h+var_B8], rcx
0x140003063  mov     [rbp+57h+var_C8], rax
0x140003067  lea     rax, UaspStartIo
0x14000306e  mov     [rbp+57h+var_C0], rax
0x140003072  jmp     short loc_140003095
0x140003074  lea     rax, UaspDumpInitialize
0x14000307b  mov     [rbp+57h+var_C8], rax
0x14000307f  lea     rax, UaspStartIo
0x140003086  mov     [rbp+57h+var_C0], rax
0x14000308a  lea     rax, UaspDumpHwInterrupt
0x140003091  mov     [rbp+57h+var_B8], rax
0x140003095  test    rbx, rbx
0x140003098  mov     [rbp+57h+var_CC], ecx
0x14000309b  lea     rax, UaspFindAdapter
0x1400030a2  mov     [rbp+57h+var_84], ecx
0x1400030a5  mov     [rbp+57h+var_B0], rax
0x1400030a9  lea     r8, [rbp+57h+var_D0]
0x1400030ad  setnz   [rbp+57h+var_78]
0x1400030b1  mov     [rbp+57h+var_90], 5B8h
0x1400030b8  lea     rax, UaspResetBus
0x1400030bf  mov     [rbp+57h+var_88], 10h
0x1400030c6  mov     [rbp+57h+var_A8], rax
0x1400030ca  test    rbx, rbx
0x1400030cd  lea     rax, UaspAdapterControl
0x1400030d4  mov     [rbp+57h+var_8C], 20h ; ' '
0x1400030db  mov     [rbp+57h+var_58], rax
0x1400030df  setnz   cs:gTracingEnabled
0x1400030e6  lea     rax, UaspUnitControl
0x1400030ed  mov     [rbp+57h+var_77], 1010101h
0x1400030f4  mov     [rbp+57h+var_8], rax
0x1400030f8  xor     r9d, r9d
0x1400030fb  lea     rax, UaspFreeAdapterResources
0x140003102  mov     [rbp+57h+var_18], 5
0x140003109  mov     [rbp+57h+var_48], rax
0x14000310d  mov     rdx, rdi
0x140003110  lea     rax, UaspProcessServiceRequest
0x140003117  mov     rcx, rbx
0x14000311a  mov     [rbp+57h+var_40], rax
0x14000311e  lea     rax, _guard_check_icall_nop
0x140003125  mov     [rbp+57h+var_38], rax
0x140003129  lea     rax, UaspInitializeTracing
0x140003130  mov     [rbp+57h+var_30], rax
0x140003134  lea     rax, UaspCleanupTracing
0x14000313b  mov     [rbp+57h+var_28], rax
0x14000313f  call    cs:__imp_StorPortInitialize
0x140003146  nop     dword ptr [rax+rax+00h]
0x14000314b  lea     r11, [rsp+0F0h+var_s0]
0x140003153  mov     rbx, [r11+10h]
0x140003157  mov     rdi, [r11+18h]
0x14000315b  mov     rsp, r11
0x14000315e  pop     rbp
0x14000315f  retn
```
