# IsBackgroundExtensionContract(ushort const *)

- ea: `0x180044e64`
- end: `0x180044f50`
- name: `?IsBackgroundExtensionContract@@YA_NPEBG@Z`
- size: `236`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1800469c0`

## callees

- `0x180044e64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180044f27`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180044f27`

## string_xrefs

- `0x180044e7b`: `Windows.BackgroundTasks`
- `0x180044ea1`: `Windows.AppService`
- `0x180044e96`: `Windows.UpdateTask`
- `0x180044e8b`: `Windows.PreInstalledConfigTask`
- `0x180044ed8`: `Windows.PrintWorkflowBackgroundTask`
- `0x180044ecd`: `Windows.UserDataTaskDataProvider`
- `0x180044ef9`: `Windows.PrintSupportExtension`

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
0x180044e64  mov     [rsp-8+arg_0], rbx
0x180044e69  mov     [rsp-8+arg_8], rdi
0x180044e6e  push    rbp
0x180044e6f  lea     rbp, [rsp-57h]
0x180044e74  sub     rsp, 90h
0x180044e7b  lea     rax, aWindowsBackgro; "Windows.BackgroundTasks"
0x180044e82  mov     rdi, rcx
0x180044e85  mov     [rbp+57h+var_70], rax
0x180044e89  xor     ebx, ebx
0x180044e8b  lea     rax, aWindowsPreinst; "Windows.PreInstalledConfigTask"
0x180044e92  mov     [rbp+57h+var_68], rax
0x180044e96  lea     rax, aWindowsUpdatet; "Windows.UpdateTask"
0x180044e9d  mov     [rbp+57h+var_60], rax
0x180044ea1  lea     rax, aWindowsAppserv; "Windows.AppService"
0x180044ea8  mov     [rbp+57h+var_58], rax
0x180044eac  lea     rax, aWindowsAppoint; "Windows.AppointmentDataProvider"
0x180044eb3  mov     [rbp+57h+var_50], rax
0x180044eb7  lea     rax, aWindowsContact_5; "Windows.ContactDataProvider"
0x180044ebe  mov     [rbp+57h+var_48], rax
0x180044ec2  lea     rax, aWindowsEmailda; "Windows.EmailDataProvider"
0x180044ec9  mov     [rbp+57h+var_40], rax
0x180044ecd  lea     rax, aWindowsUserdat_0; "Windows.UserDataTaskDataProvider"
0x180044ed4  mov     [rbp+57h+var_38], rax
0x180044ed8  lea     rax, aWindowsPrintwo; "Windows.PrintWorkflowBackgroundTask"
0x180044edf  mov     [rbp+57h+var_30], rax
0x180044ee3  lea     rax, aWindowsBarcode_0; "Windows.BarcodeScannerProvider"
0x180044eea  mov     [rbp+57h+var_28], rax
0x180044eee  lea     rax, aWindowsPospaym; "Windows.PosPaymentConnector"
0x180044ef5  mov     [rbp+57h+var_20], rax
0x180044ef9  lea     rax, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x180044f00  mov     [rbp+57h+var_18], rax
0x180044f04  lea     rax, aWindowsPrintsu; "Windows.PrintSupportWorkflow"
0x180044f0b  mov     [rbp+57h+var_10], rax
0x180044f0f  lea     rax, aWindowsPrintsu_0; "Windows.PrintSupportVirtualPrinterWorkf"...
0x180044f16  mov     [rbp+57h+var_8], rax
0x180044f1a  cmp     ebx, 0Eh
0x180044f1d  jnb     short loc_180044F39
0x180044f1f  mov     rdx, [rbp+rbx*8+57h+var_70]
0x180044f24  mov     rcx, rdi
0x180044f27  call    cs:__imp__o__wcsicmp
0x180044f2d  test    eax, eax
0x180044f2f  jz      short loc_180044F35
0x180044f31  inc     ebx
0x180044f33  jmp     short loc_180044F1A
0x180044f35  mov     al, 1
0x180044f37  jmp     short loc_180044F3B
0x180044f39  xor     al, al
0x180044f3b  lea     r11, [rsp+90h+var_s0]
0x180044f43  mov     rbx, [r11+10h]
0x180044f47  mov     rdi, [r11+18h]
0x180044f4b  mov     rsp, r11
0x180044f4e  pop     rbp
0x180044f4f  retn
```
