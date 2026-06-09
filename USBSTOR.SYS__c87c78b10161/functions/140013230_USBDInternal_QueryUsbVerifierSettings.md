# USBDInternal_QueryUsbVerifierSettings

- ea: `0x140013230`
- end: `0x1400135a1`
- name: `USBDInternal_QueryUsbVerifierSettings`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x14000fee8`

## callees

- `0x14000f470`
- `0x140013230`
- `0x140013990`
- `0x140013d40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140013284`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400134dc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013284`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400134dc`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140013294`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400134ec`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140013294`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400134ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001354d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013566`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001354d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013566`
- `ntoskrnl!ZwClose` at `0x14001357b`
- `ntoskrnl!ZwClose` at `0x14001357b`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14001350d`
- `ntoskrnl!MmIsDriverVerifying` at `0x140013269`
- `ntoskrnl!MmIsDriverVerifying` at `0x140013269`
- `ntoskrnl!DbgPrintEx` at `0x1400132e6`
- `ntoskrnl!DbgPrintEx` at `0x14001334e`
- `ntoskrnl!DbgPrintEx` at `0x140013539`
- `ntoskrnl!DbgPrintEx` at `0x1400132e6`
- `ntoskrnl!DbgPrintEx` at `0x14001334e`
- `ntoskrnl!DbgPrintEx` at `0x140013539`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140013322`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140013322`

## string_xrefs

- `0x1400134b3`: `RtlQueryRegistryValuesEx`
- `0x140013275`: `IoOpenDriverRegistryKey`
- `0x1400132d9`: `IoOpenDriverRegistryKey failed with 0x%x\n`
- `0x14001352c`: `RtlQueryRegistrySettings failed, ignoring this error0x%x\n`

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
    PoolWithTag = ExAllocatePoolWithTag(PoolType, 0x1C0u, 0x53414D55u);
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
      ExFreePoolWithTag(v12, 0x53414D55u);
    }
    else if ( g_EnableDbgPrints )
    {
      DbgPrintEx(0x4Du, 0, "ExAllocatePoolWithTag for USBDInternal_QueryUsbVerifierSettings failed\n");
    }
  }
  if ( v5 )
    ExFreePoolWithTag(v5, 0x53414D55u);
LABEL_19:
  if ( Handle )
    ZwClose(Handle);
}

```

## disassembly

```asm
0x140013230  mov     [rsp-28h+arg_10], rbx
0x140013235  mov     [rsp-28h+arg_18], rsi
0x14001323a  push    rbp
0x14001323b  push    rdi
0x14001323c  push    r12
0x14001323e  push    r14
0x140013240  push    r15
0x140013242  mov     rbp, rsp
0x140013245  sub     rsp, 50h
0x140013249  mov     rbx, rcx
0x14001324c  lea     r12, [rdx+48h]
0x140013250  mov     rcx, [rcx+8]; DriverObject
0x140013254  xor     r14d, r14d
0x140013257  xorps   xmm0, xmm0
0x14001325a  mov     [rbp+P], r14
0x14001325e  mov     [rbp+Handle], r14
0x140013262  mov     rdi, rdx
0x140013265  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140013269  call    cs:__imp_MmIsDriverVerifying
0x140013270  nop     dword ptr [rax+rax+00h]
0x140013275  lea     rdx, aIoopendriverre_0; "IoOpenDriverRegistryKey"
0x14001327c  mov     [r12], eax
0x140013280  lea     rcx, [rbp+DestinationString]; DestinationString
0x140013284  call    cs:__imp_RtlInitUnicodeString
0x14001328b  nop     dword ptr [rax+rax+00h]
0x140013290  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140013294  call    cs:__imp_MmGetSystemRoutineAddress
0x14001329b  nop     dword ptr [rax+rax+00h]
0x1400132a0  mov     r15, rax
0x1400132a3  test    rax, rax
0x1400132a6  jz      short loc_1400132F7
0x1400132a8  mov     rcx, [rbx+8]
0x1400132ac  lea     rax, [rbp+Handle]
0x1400132b0  mov     [rsp+50h+var_30], rax
0x1400132b5  lea     r8d, [r14+1]
0x1400132b9  mov     rax, r15
0x1400132bc  xor     r9d, r9d
0x1400132bf  xor     edx, edx
0x1400132c1  call    _guard_dispatch_icall
0x1400132c6  test    eax, eax
0x1400132c8  jns     short loc_14001330F
0x1400132ca  cmp     cs:g_EnableDbgPrints, r14b
0x1400132d1  jz      loc_140013572
0x1400132d7  xor     edx, edx; Level
0x1400132d9  lea     r8, aIoopendriverre; "IoOpenDriverRegistryKey failed with 0x%"...
0x1400132e0  mov     r9d, eax
0x1400132e3  lea     ecx, [rdx+4Dh]; ComponentId
0x1400132e6  call    cs:__imp_DbgPrintEx
0x1400132ed  nop     dword ptr [rax+rax+00h]
0x1400132f2  jmp     loc_140013572
0x1400132f7  lea     rdx, [rbp+P]
0x1400132fb  mov     rcx, rbx
0x1400132fe  call    USBDInternal_BuildServicePath
0x140013303  mov     r14, [rbp+P]
0x140013307  test    eax, eax
0x140013309  js      loc_140013559
0x14001330f  mov     ecx, cs:PoolType; PoolType
0x140013315  mov     ebx, 1C0h
0x14001331a  mov     edx, ebx; NumberOfBytes
0x14001331c  mov     r8d, 53414D55h; Tag
0x140013322  call    cs:__imp_ExAllocatePoolWithTag
0x140013329  nop     dword ptr [rax+rax+00h]
0x14001332e  mov     rsi, rax
0x140013331  test    rax, rax
0x140013334  jnz     short loc_14001335F
0x140013336  cmp     cs:g_EnableDbgPrints, al
0x14001333c  jz      loc_140013559
0x140013342  lea     r8, aExallocatepool; "ExAllocatePoolWithTag for USBDInternal_"...
0x140013349  xor     edx, edx; Level
0x14001334b  lea     ecx, [rax+4Dh]; ComponentId
0x14001334e  call    cs:__imp_DbgPrintEx
0x140013355  nop     dword ptr [rax+rax+00h]
0x14001335a  jmp     loc_140013559
0x14001335f  mov     r8, rbx; Size
0x140013362  xor     edx, edx; Val
0x140013364  mov     rcx, rsi; void *
0x140013367  call    memset
0x14001336c  mov     [rsi+18h], r12
0x140013370  lea     rcx, USBD_VerifierSettingsCallback
0x140013377  mov     [rsi], rcx
0x14001337a  lea     rax, aUsbverifierena; "UsbVerifierEnabled"
0x140013381  mov     [rsi+10h], rax
0x140013385  mov     edx, 4
0x14001338a  mov     [rsi+20h], edx
0x14001338d  lea     rax, aUsbverifierfai_3; "UsbVerifierFailRegistration"
0x140013394  mov     [rsi+30h], edx
0x140013397  test    r15, r15
0x14001339a  mov     [rsi+28h], r12
0x14001339e  xorps   xmm0, xmm0
0x1400133a1  mov     [rsi+48h], rax
0x1400133a5  lea     rax, [rdi+4Ch]
0x1400133a9  mov     [rsi+50h], rax
0x1400133ad  mov     [rsi+60h], rax
0x1400133b1  lea     rax, aUsbverifierfai_1; "UsbVerifierFailChainedMdlSupport"
0x1400133b8  mov     [rsi+38h], rcx
0x1400133bc  mov     [rsi+58h], edx
0x1400133bf  mov     [rsi+68h], edx
0x1400133c2  mov     [rsi+80h], rax
0x1400133c9  lea     rax, [rdi+50h]
0x1400133cd  mov     [rsi+88h], rax
0x1400133d4  mov     [rsi+98h], rax
0x1400133db  lea     rax, aUsbverifierfai_2; "UsbVerifierFailStaticStreamSupport"
0x1400133e2  mov     [rsi+70h], rcx
0x1400133e6  mov     [rsi+90h], edx
0x1400133ec  mov     [rsi+0A0h], edx
0x1400133f2  mov     [rsi+0B8h], rax
0x1400133f9  lea     rax, [rdi+54h]
0x1400133fd  mov     [rsi+0C0h], rax
0x140013404  mov     [rsi+0D0h], rax
0x14001340b  lea     rax, aUsbverifiersta; "UsbVerifierStaticStreamCountOverride"
0x140013412  mov     [rsi+0A8h], rcx
0x140013419  mov     [rsi+0C8h], edx
0x14001341f  mov     [rsi+0D8h], edx
0x140013425  mov     [rsi+0F0h], rax
0x14001342c  lea     rax, [rdi+58h]
0x140013430  mov     [rsi+0F8h], rax
0x140013437  mov     [rsi+108h], rax
0x14001343e  lea     rax, aUsbverifierfai_0; "UsbVerifierFailEnableStaticStreams"
0x140013445  mov     [rsi+0E0h], rcx
0x14001344c  mov     [rsi+100h], edx
0x140013452  mov     [rsi+110h], edx
0x140013458  mov     [rsi+128h], rax
0x14001345f  lea     rax, [rdi+5Ch]
0x140013463  mov     [rsi+130h], rax
0x14001346a  mov     [rsi+140h], rax
0x140013471  lea     rax, aUsbverifierfai; "UsbVerifierFailSecureTransferSupport"
0x140013478  mov     [rsi+118h], rcx
0x14001347f  mov     [rsi+138h], edx
0x140013485  mov     [rsi+148h], edx
0x14001348b  mov     [rsi+160h], rax
0x140013492  lea     rax, [rdi+0A0h]
0x140013499  mov     [rsi+150h], rcx
0x1400134a0  mov     rdi, r14
0x1400134a3  mov     [rsi+170h], edx
0x1400134a9  lea     rcx, [rbp+SystemRoutineName]; DestinationString
0x1400134ad  mov     [rsi+180h], edx
0x1400134b3  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x1400134ba  mov     [rsi+168h], rax
0x1400134c1  mov     [rsi+178h], rax
0x1400134c8  cmovnz  rdi, [rbp+Handle]
0x1400134cd  neg     r15
0x1400134d0  movups  xmmword ptr [rbp+SystemRoutineName.Length], xmm0
0x1400134d4  sbb     ebx, ebx
0x1400134d6  and     ebx, 3FFFFFFFh
0x1400134dc  call    cs:__imp_RtlInitUnicodeString
0x1400134e3  nop     dword ptr [rax+rax+00h]
0x1400134e8  lea     rcx, [rbp+SystemRoutineName]; SystemRoutineName
0x1400134ec  call    cs:__imp_MmGetSystemRoutineAddress
0x1400134f3  nop     dword ptr [rax+rax+00h]
0x1400134f8  mov     [rsp+50h+var_30], 0
0x140013501  lea     ecx, [rbx+1]
0x140013504  test    rax, rax
0x140013507  mov     r8, rsi
0x14001350a  mov     rdx, rdi
0x14001350d  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140013515  xor     r9d, r9d
0x140013518  call    _guard_dispatch_icall
0x14001351d  test    eax, eax
0x14001351f  jns     short loc_140013545
0x140013521  cmp     cs:g_EnableDbgPrints, 0
0x140013528  jz      short loc_140013545
0x14001352a  xor     edx, edx; Level
0x14001352c  lea     r8, aRtlqueryregist_0; "RtlQueryRegistrySettings failed, ignori"...
0x140013533  mov     r9d, eax
0x140013536  lea     ecx, [rdx+4Dh]; ComponentId
0x140013539  call    cs:__imp_DbgPrintEx
0x140013540  nop     dword ptr [rax+rax+00h]
0x140013545  mov     edx, 53414D55h; Tag
0x14001354a  mov     rcx, rsi; P
0x14001354d  call    cs:__imp_ExFreePoolWithTag
0x140013554  nop     dword ptr [rax+rax+00h]
0x140013559  test    r14, r14
0x14001355c  jz      short loc_140013572
0x14001355e  mov     edx, 53414D55h; Tag
0x140013563  mov     rcx, r14; P
0x140013566  call    cs:__imp_ExFreePoolWithTag
0x14001356d  nop     dword ptr [rax+rax+00h]
0x140013572  mov     rcx, [rbp+Handle]; Handle
0x140013576  test    rcx, rcx
0x140013579  jz      short loc_140013587
0x14001357b  call    cs:__imp_ZwClose
0x140013582  nop     dword ptr [rax+rax+00h]
0x140013587  lea     r11, [rsp+50h+var_s0]
0x14001358c  mov     rbx, [r11+40h]
0x140013590  mov     rsi, [r11+48h]
0x140013594  mov     rsp, r11
0x140013597  pop     r15
0x140013599  pop     r14
0x14001359b  pop     r12
0x14001359d  pop     rdi
0x14001359e  pop     rbp
0x14001359f  retn
```
