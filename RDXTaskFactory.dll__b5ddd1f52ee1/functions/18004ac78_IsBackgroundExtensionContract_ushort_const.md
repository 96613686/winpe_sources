# IsBackgroundExtensionContract(ushort const *)

- ea: `0x18004ac78`
- end: `0x18004ad64`
- name: `?IsBackgroundExtensionContract@@YA_NPEBG@Z`
- size: `236`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18004c7a0`

## callees

- `0x18004ac78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004ad3b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004ad3b`

## string_xrefs

- `0x18004ac9f`: `Windows.PreInstalledConfigTask`
- `0x18004acaa`: `Windows.UpdateTask`
- `0x18004ac8f`: `Windows.BackgroundTasks`
- `0x18004acb5`: `Windows.AppService`
- `0x18004ace1`: `Windows.UserDataTaskDataProvider`
- `0x18004acec`: `Windows.PrintWorkflowBackgroundTask`
- `0x18004ad0d`: `Windows.PrintSupportExtension`

## pseudocode

```c
char __fastcall IsBackgroundExtensionContract(const unsigned __int16 *a1)
{
  __int64 v2; // rbx
  _QWORD v4[14]; // [rsp+20h] [rbp-19h]

  v4[0] = L"Windows.BackgroundTasks";
  v2 = 0;
  v4[1] = L"Windows.PreInstalledConfigTask";
  v4[2] = L"Windows.UpdateTask";
  v4[3] = L"Windows.AppService";
  v4[4] = L"Windows.AppointmentDataProvider";
  v4[5] = L"Windows.ContactDataProvider";
  v4[6] = L"Windows.EmailDataProvider";
  v4[7] = L"Windows.UserDataTaskDataProvider";
  v4[8] = L"Windows.PrintWorkflowBackgroundTask";
  v4[9] = L"Windows.BarcodeScannerProvider";
  v4[10] = L"Windows.PosPaymentConnector";
  v4[11] = L"Windows.PrintSupportExtension";
  v4[12] = L"Windows.PrintSupportWorkflow";
  v4[13] = L"Windows.PrintSupportVirtualPrinterWorkflow";
  while ( (unsigned int)v2 < 0xE )
  {
    if ( !(unsigned int)_o__wcsicmp(a1, v4[v2]) )
      return 1;
    v2 = (unsigned int)(v2 + 1);
  }
  return 0;
}

```

## disassembly

```asm
0x18004ac78  mov     [rsp-8+arg_0], rbx
0x18004ac7d  mov     [rsp-8+arg_8], rdi
0x18004ac82  push    rbp
0x18004ac83  lea     rbp, [rsp-57h]
0x18004ac88  sub     rsp, 90h
0x18004ac8f  lea     rax, aWindowsBackgro; "Windows.BackgroundTasks"
0x18004ac96  mov     rdi, rcx
0x18004ac99  mov     [rbp+57h+var_70], rax
0x18004ac9d  xor     ebx, ebx
0x18004ac9f  lea     rax, aWindowsPreinst; "Windows.PreInstalledConfigTask"
0x18004aca6  mov     [rbp+57h+var_68], rax
0x18004acaa  lea     rax, aWindowsUpdatet; "Windows.UpdateTask"
0x18004acb1  mov     [rbp+57h+var_60], rax
0x18004acb5  lea     rax, aWindowsAppserv; "Windows.AppService"
0x18004acbc  mov     [rbp+57h+var_58], rax
0x18004acc0  lea     rax, aWindowsAppoint; "Windows.AppointmentDataProvider"
0x18004acc7  mov     [rbp+57h+var_50], rax
0x18004accb  lea     rax, aWindowsContact_5; "Windows.ContactDataProvider"
0x18004acd2  mov     [rbp+57h+var_48], rax
0x18004acd6  lea     rax, aWindowsEmailda; "Windows.EmailDataProvider"
0x18004acdd  mov     [rbp+57h+var_40], rax
0x18004ace1  lea     rax, aWindowsUserdat_0; "Windows.UserDataTaskDataProvider"
0x18004ace8  mov     [rbp+57h+var_38], rax
0x18004acec  lea     rax, aWindowsPrintwo; "Windows.PrintWorkflowBackgroundTask"
0x18004acf3  mov     [rbp+57h+var_30], rax
0x18004acf7  lea     rax, aWindowsBarcode_0; "Windows.BarcodeScannerProvider"
0x18004acfe  mov     [rbp+57h+var_28], rax
0x18004ad02  lea     rax, aWindowsPospaym; "Windows.PosPaymentConnector"
0x18004ad09  mov     [rbp+57h+var_20], rax
0x18004ad0d  lea     rax, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x18004ad14  mov     [rbp+57h+var_18], rax
0x18004ad18  lea     rax, aWindowsPrintsu; "Windows.PrintSupportWorkflow"
0x18004ad1f  mov     [rbp+57h+var_10], rax
0x18004ad23  lea     rax, aWindowsPrintsu_0; "Windows.PrintSupportVirtualPrinterWorkf"...
0x18004ad2a  mov     [rbp+57h+var_8], rax
0x18004ad2e  cmp     ebx, 0Eh
0x18004ad31  jnb     short loc_18004AD4D
0x18004ad33  mov     rdx, [rbp+rbx*8+57h+var_70]
0x18004ad38  mov     rcx, rdi
0x18004ad3b  call    cs:__imp__o__wcsicmp
0x18004ad41  test    eax, eax
0x18004ad43  jz      short loc_18004AD49
0x18004ad45  inc     ebx
0x18004ad47  jmp     short loc_18004AD2E
0x18004ad49  mov     al, 1
0x18004ad4b  jmp     short loc_18004AD4F
0x18004ad4d  xor     al, al
0x18004ad4f  lea     r11, [rsp+90h+var_s0]
0x18004ad57  mov     rbx, [r11+10h]
0x18004ad5b  mov     rdi, [r11+18h]
0x18004ad5f  mov     rsp, r11
0x18004ad62  pop     rbp
0x18004ad63  retn
```
