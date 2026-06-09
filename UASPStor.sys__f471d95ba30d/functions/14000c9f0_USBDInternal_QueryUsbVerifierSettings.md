# USBDInternal_QueryUsbVerifierSettings

- ea: `0x14000c9f0`
- end: `0x14000cd61`
- name: `USBDInternal_QueryUsbVerifierSettings`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x14000cd68`

## callees

- `0x14000c6b4`
- `0x14000c9f0`
- `0x14000d830`
- `0x14000dc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000cd0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cd26`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cd0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cd26`
- `ntoskrnl!ZwClose` at `0x14000cd3b`
- `ntoskrnl!ZwClose` at `0x14000cd3b`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000ca54`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000ccac`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000ca54`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000ccac`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000cccd`
- `ntoskrnl!MmIsDriverVerifying` at `0x14000ca29`
- `ntoskrnl!MmIsDriverVerifying` at `0x14000ca29`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ca44`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cc9c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ca44`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cc9c`
- `ntoskrnl!DbgPrintEx` at `0x14000caa6`
- `ntoskrnl!DbgPrintEx` at `0x14000cb0e`
- `ntoskrnl!DbgPrintEx` at `0x14000ccf9`
- `ntoskrnl!DbgPrintEx` at `0x14000caa6`
- `ntoskrnl!DbgPrintEx` at `0x14000cb0e`
- `ntoskrnl!DbgPrintEx` at `0x14000ccf9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cae2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cae2`

## string_xrefs

- `0x14000cc73`: `RtlQueryRegistryValuesEx`
- `0x14000ca35`: `IoOpenDriverRegistryKey`
- `0x14000ca99`: `IoOpenDriverRegistryKey failed with 0x%x\n`
- `0x14000ccec`: `RtlQueryRegistrySettings failed, ignoring this error0x%x\n`

## pseudocode

```c
void __fastcall USBDInternal_QueryUsbVerifierSettings(__int64 a1, __int64 a2)
{
  __int64 v3; // r12
  struct _DRIVER_OBJECT *v4; // rcx
  PVOID v5; // r14
  PVOID SystemRoutineAddress; // rax
  PVOID v8; // r15
  int v9; // eax
  int v10; // eax
  _QWORD *PoolWithTag; // rax
  _QWORD *v12; // rsi
  __int64 v13; // rax
  HANDLE v14; // rdi
  PVOID v15; // rax
  int v16; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+40h] [rbp-10h] BYREF
  PVOID P; // [rsp+80h] [rbp+30h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+38h] BYREF

  v3 = a2 + 72;
  v4 = *(struct _DRIVER_OBJECT **)(a1 + 8);
  v5 = 0;
  P = 0;
  Handle = 0;
  DestinationString = 0;
  *(_DWORD *)(a2 + 72) = MmIsDriverVerifying(v4);
  RtlInitUnicodeString(&DestinationString, L"IoOpenDriverRegistryKey");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  v8 = SystemRoutineAddress;
  if ( SystemRoutineAddress )
  {
    v9 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, HANDLE *))SystemRoutineAddress)(
           *(_QWORD *)(a1 + 8),
           0,
           1,
           0,
           &Handle);
    if ( v9 < 0 )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "IoOpenDriverRegistryKey failed with 0x%x\n", v9);
      goto LABEL_19;
    }
    goto LABEL_6;
  }
  v10 = USBDInternal_BuildServicePath(a1, &P);
  v5 = P;
  if ( v10 >= 0 )
  {
LABEL_6:
    PoolWithTag = ExAllocatePoolWithTag(PoolType, 0x1C0u, 0x75617370u);
    v12 = PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, 0x1C0u);
      v12[3] = v3;
      *v12 = USBD_VerifierSettingsCallback;
      v12[2] = L"UsbVerifierEnabled";
      *((_DWORD *)v12 + 8) = 4;
      *((_DWORD *)v12 + 12) = 4;
      v12[5] = v3;
      v12[9] = L"UsbVerifierFailRegistration";
      v12[10] = a2 + 76;
      v12[12] = a2 + 76;
      v12[7] = USBD_VerifierSettingsCallback;
      *((_DWORD *)v12 + 22) = 4;
      *((_DWORD *)v12 + 26) = 4;
      v12[16] = L"UsbVerifierFailChainedMdlSupport";
      v12[17] = a2 + 80;
      v12[19] = a2 + 80;
      v12[14] = USBD_VerifierSettingsCallback;
      *((_DWORD *)v12 + 36) = 4;
      *((_DWORD *)v12 + 40) = 4;
      v12[23] = L"UsbVerifierFailStaticStreamSupport";
      v12[24] = a2 + 84;
      v12[26] = a2 + 84;
      v12[21] = USBD_VerifierSettingsCallback;
      *((_DWORD *)v12 + 50) = 4;
      *((_DWORD *)v12 + 54) = 4;
      v12[30] = L"UsbVerifierStaticStreamCountOverride";
      v12[31] = a2 + 88;
      v12[33] = a2 + 88;
      v12[28] = USBD_VerifierSettingsCallback;
      *((_DWORD *)v12 + 64) = 4;
      *((_DWORD *)v12 + 68) = 4;
      v12[37] = L"UsbVerifierFailEnableStaticStreams";
      v12[38] = a2 + 92;
      v12[40] = a2 + 92;
      v12[35] = USBD_VerifierSettingsCallback;
      *((_DWORD *)v12 + 78) = 4;
      *((_DWORD *)v12 + 82) = 4;
      v12[44] = L"UsbVerifierFailSecureTransferSupport";
      v13 = a2 + 160;
      v12[42] = USBD_VerifierSettingsCallback;
      v14 = v5;
      *((_DWORD *)v12 + 92) = 4;
      *((_DWORD *)v12 + 96) = 4;
      v12[45] = v13;
      v12[47] = v13;
      if ( v8 )
        v14 = Handle;
      SystemRoutineName = 0;
      RtlInitUnicodeString(&SystemRoutineName, L"RtlQueryRegistryValuesEx");
      v15 = MmGetSystemRoutineAddress(&SystemRoutineName);
      if ( !v15 )
        v15 = RtlQueryRegistryValues;
      v16 = ((__int64 (__fastcall *)(_QWORD, HANDLE, _QWORD *, _QWORD, _QWORD))v15)(
              v8 != 0 ? 0x40000000 : 1,
              v14,
              v12,
              0,
              0);
      if ( v16 < 0 && g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "RtlQueryRegistrySettings failed, ignoring this error0x%x\n", v16);
      ExFreePoolWithTag(v12, 0x75617370u);
    }
    else if ( g_EnableDbgPrints )
    {
      DbgPrintEx(0x4Du, 0, "ExAllocatePoolWithTag for USBDInternal_QueryUsbVerifierSettings failed\n");
    }
  }
  if ( v5 )
    ExFreePoolWithTag(v5, 0x75617370u);
LABEL_19:
  if ( Handle )
    ZwClose(Handle);
}

```

## disassembly

```asm
0x14000c9f0  mov     [rsp-28h+arg_10], rbx
0x14000c9f5  mov     [rsp-28h+arg_18], rsi
0x14000c9fa  push    rbp
0x14000c9fb  push    rdi
0x14000c9fc  push    r12
0x14000c9fe  push    r14
0x14000ca00  push    r15
0x14000ca02  mov     rbp, rsp
0x14000ca05  sub     rsp, 50h
0x14000ca09  mov     rbx, rcx
0x14000ca0c  lea     r12, [rdx+48h]
0x14000ca10  mov     rcx, [rcx+8]; DriverObject
0x14000ca14  xor     r14d, r14d
0x14000ca17  xorps   xmm0, xmm0
0x14000ca1a  mov     [rbp+P], r14
0x14000ca1e  mov     [rbp+Handle], r14
0x14000ca22  mov     rdi, rdx
0x14000ca25  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000ca29  call    cs:__imp_MmIsDriverVerifying
0x14000ca30  nop     dword ptr [rax+rax+00h]
0x14000ca35  lea     rdx, aIoopendriverre_0; "IoOpenDriverRegistryKey"
0x14000ca3c  mov     [r12], eax
0x14000ca40  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000ca44  call    cs:__imp_RtlInitUnicodeString
0x14000ca4b  nop     dword ptr [rax+rax+00h]
0x14000ca50  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000ca54  call    cs:__imp_MmGetSystemRoutineAddress
0x14000ca5b  nop     dword ptr [rax+rax+00h]
0x14000ca60  mov     r15, rax
0x14000ca63  test    rax, rax
0x14000ca66  jz      short loc_14000CAB7
0x14000ca68  mov     rcx, [rbx+8]
0x14000ca6c  lea     rax, [rbp+Handle]
0x14000ca70  mov     [rsp+50h+var_30], rax
0x14000ca75  lea     r8d, [r14+1]
0x14000ca79  mov     rax, r15
0x14000ca7c  xor     r9d, r9d
0x14000ca7f  xor     edx, edx
0x14000ca81  call    _guard_dispatch_icall
0x14000ca86  test    eax, eax
0x14000ca88  jns     short loc_14000CACF
0x14000ca8a  cmp     cs:g_EnableDbgPrints, r14b
0x14000ca91  jz      loc_14000CD32
0x14000ca97  xor     edx, edx; Level
0x14000ca99  lea     r8, aIoopendriverre; "IoOpenDriverRegistryKey failed with 0x%"...
0x14000caa0  mov     r9d, eax
0x14000caa3  lea     ecx, [rdx+4Dh]; ComponentId
0x14000caa6  call    cs:__imp_DbgPrintEx
0x14000caad  nop     dword ptr [rax+rax+00h]
0x14000cab2  jmp     loc_14000CD32
0x14000cab7  lea     rdx, [rbp+P]
0x14000cabb  mov     rcx, rbx
0x14000cabe  call    USBDInternal_BuildServicePath
0x14000cac3  mov     r14, [rbp+P]
0x14000cac7  test    eax, eax
0x14000cac9  js      loc_14000CD19
0x14000cacf  mov     ecx, cs:PoolType; PoolType
0x14000cad5  mov     ebx, 1C0h
0x14000cada  mov     edx, ebx; NumberOfBytes
0x14000cadc  mov     r8d, 75617370h; Tag
0x14000cae2  call    cs:__imp_ExAllocatePoolWithTag
0x14000cae9  nop     dword ptr [rax+rax+00h]
0x14000caee  mov     rsi, rax
0x14000caf1  test    rax, rax
0x14000caf4  jnz     short loc_14000CB1F
0x14000caf6  cmp     cs:g_EnableDbgPrints, al
0x14000cafc  jz      loc_14000CD19
0x14000cb02  lea     r8, aExallocatepool; "ExAllocatePoolWithTag for USBDInternal_"...
0x14000cb09  xor     edx, edx; Level
0x14000cb0b  lea     ecx, [rax+4Dh]; ComponentId
0x14000cb0e  call    cs:__imp_DbgPrintEx
0x14000cb15  nop     dword ptr [rax+rax+00h]
0x14000cb1a  jmp     loc_14000CD19
0x14000cb1f  mov     r8, rbx; Size
0x14000cb22  xor     edx, edx; Val
0x14000cb24  mov     rcx, rsi; void *
0x14000cb27  call    memset
0x14000cb2c  mov     [rsi+18h], r12
0x14000cb30  lea     rcx, USBD_VerifierSettingsCallback
0x14000cb37  mov     [rsi], rcx
0x14000cb3a  lea     rax, aUsbverifierena; "UsbVerifierEnabled"
0x14000cb41  mov     [rsi+10h], rax
0x14000cb45  mov     edx, 4
0x14000cb4a  mov     [rsi+20h], edx
0x14000cb4d  lea     rax, aUsbverifierfai_3; "UsbVerifierFailRegistration"
0x14000cb54  mov     [rsi+30h], edx
0x14000cb57  test    r15, r15
0x14000cb5a  mov     [rsi+28h], r12
0x14000cb5e  xorps   xmm0, xmm0
0x14000cb61  mov     [rsi+48h], rax
0x14000cb65  lea     rax, [rdi+4Ch]
0x14000cb69  mov     [rsi+50h], rax
0x14000cb6d  mov     [rsi+60h], rax
0x14000cb71  lea     rax, aUsbverifierfai_1; "UsbVerifierFailChainedMdlSupport"
0x14000cb78  mov     [rsi+38h], rcx
0x14000cb7c  mov     [rsi+58h], edx
0x14000cb7f  mov     [rsi+68h], edx
0x14000cb82  mov     [rsi+80h], rax
0x14000cb89  lea     rax, [rdi+50h]
0x14000cb8d  mov     [rsi+88h], rax
0x14000cb94  mov     [rsi+98h], rax
0x14000cb9b  lea     rax, aUsbverifierfai_2; "UsbVerifierFailStaticStreamSupport"
0x14000cba2  mov     [rsi+70h], rcx
0x14000cba6  mov     [rsi+90h], edx
0x14000cbac  mov     [rsi+0A0h], edx
0x14000cbb2  mov     [rsi+0B8h], rax
0x14000cbb9  lea     rax, [rdi+54h]
0x14000cbbd  mov     [rsi+0C0h], rax
0x14000cbc4  mov     [rsi+0D0h], rax
0x14000cbcb  lea     rax, aUsbverifiersta; "UsbVerifierStaticStreamCountOverride"
0x14000cbd2  mov     [rsi+0A8h], rcx
0x14000cbd9  mov     [rsi+0C8h], edx
0x14000cbdf  mov     [rsi+0D8h], edx
0x14000cbe5  mov     [rsi+0F0h], rax
0x14000cbec  lea     rax, [rdi+58h]
0x14000cbf0  mov     [rsi+0F8h], rax
0x14000cbf7  mov     [rsi+108h], rax
0x14000cbfe  lea     rax, aUsbverifierfai_0; "UsbVerifierFailEnableStaticStreams"
0x14000cc05  mov     [rsi+0E0h], rcx
0x14000cc0c  mov     [rsi+100h], edx
0x14000cc12  mov     [rsi+110h], edx
0x14000cc18  mov     [rsi+128h], rax
0x14000cc1f  lea     rax, [rdi+5Ch]
0x14000cc23  mov     [rsi+130h], rax
0x14000cc2a  mov     [rsi+140h], rax
0x14000cc31  lea     rax, aUsbverifierfai; "UsbVerifierFailSecureTransferSupport"
0x14000cc38  mov     [rsi+118h], rcx
0x14000cc3f  mov     [rsi+138h], edx
0x14000cc45  mov     [rsi+148h], edx
0x14000cc4b  mov     [rsi+160h], rax
0x14000cc52  lea     rax, [rdi+0A0h]
0x14000cc59  mov     [rsi+150h], rcx
0x14000cc60  mov     rdi, r14
0x14000cc63  mov     [rsi+170h], edx
0x14000cc69  lea     rcx, [rbp+SystemRoutineName]; DestinationString
0x14000cc6d  mov     [rsi+180h], edx
0x14000cc73  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14000cc7a  mov     [rsi+168h], rax
0x14000cc81  mov     [rsi+178h], rax
0x14000cc88  cmovnz  rdi, [rbp+Handle]
0x14000cc8d  neg     r15
0x14000cc90  movups  xmmword ptr [rbp+SystemRoutineName.Length], xmm0
0x14000cc94  sbb     ebx, ebx
0x14000cc96  and     ebx, 3FFFFFFFh
0x14000cc9c  call    cs:__imp_RtlInitUnicodeString
0x14000cca3  nop     dword ptr [rax+rax+00h]
0x14000cca8  lea     rcx, [rbp+SystemRoutineName]; SystemRoutineName
0x14000ccac  call    cs:__imp_MmGetSystemRoutineAddress
0x14000ccb3  nop     dword ptr [rax+rax+00h]
0x14000ccb8  mov     [rsp+50h+var_30], 0
0x14000ccc1  lea     ecx, [rbx+1]
0x14000ccc4  test    rax, rax
0x14000ccc7  mov     r8, rsi
0x14000ccca  mov     rdx, rdi
0x14000cccd  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14000ccd5  xor     r9d, r9d
0x14000ccd8  call    _guard_dispatch_icall
0x14000ccdd  test    eax, eax
0x14000ccdf  jns     short loc_14000CD05
0x14000cce1  cmp     cs:g_EnableDbgPrints, 0
0x14000cce8  jz      short loc_14000CD05
0x14000ccea  xor     edx, edx; Level
0x14000ccec  lea     r8, aRtlqueryregist_0; "RtlQueryRegistrySettings failed, ignori"...
0x14000ccf3  mov     r9d, eax
0x14000ccf6  lea     ecx, [rdx+4Dh]; ComponentId
0x14000ccf9  call    cs:__imp_DbgPrintEx
0x14000cd00  nop     dword ptr [rax+rax+00h]
0x14000cd05  mov     edx, 75617370h; Tag
0x14000cd0a  mov     rcx, rsi; P
0x14000cd0d  call    cs:__imp_ExFreePoolWithTag
0x14000cd14  nop     dword ptr [rax+rax+00h]
0x14000cd19  test    r14, r14
0x14000cd1c  jz      short loc_14000CD32
0x14000cd1e  mov     edx, 75617370h; Tag
0x14000cd23  mov     rcx, r14; P
0x14000cd26  call    cs:__imp_ExFreePoolWithTag
0x14000cd2d  nop     dword ptr [rax+rax+00h]
0x14000cd32  mov     rcx, [rbp+Handle]; Handle
0x14000cd36  test    rcx, rcx
0x14000cd39  jz      short loc_14000CD47
0x14000cd3b  call    cs:__imp_ZwClose
0x14000cd42  nop     dword ptr [rax+rax+00h]
0x14000cd47  lea     r11, [rsp+50h+var_s0]
0x14000cd4c  mov     rbx, [r11+40h]
0x14000cd50  mov     rsi, [r11+48h]
0x14000cd54  mov     rsp, r11
0x14000cd57  pop     r15
0x14000cd59  pop     r14
0x14000cd5b  pop     r12
0x14000cd5d  pop     rdi
0x14000cd5e  pop     rbp
0x14000cd5f  retn
```
