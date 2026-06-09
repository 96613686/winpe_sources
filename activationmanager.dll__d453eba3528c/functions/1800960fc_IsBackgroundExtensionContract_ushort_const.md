# IsBackgroundExtensionContract(ushort const *)

- ea: `0x1800960fc`
- end: `0x1800961e8`
- name: `?IsBackgroundExtensionContract@@YA_NPEBG@Z`
- size: `236`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180039180`

## callees

- `0x1800960fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800961bf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800961bf`

## string_xrefs

- `0x180096123`: `Windows.PreInstalledConfigTask`
- `0x180096113`: `Windows.BackgroundTasks`
- `0x180096139`: `Windows.AppService`
- `0x18009612e`: `Windows.UpdateTask`
- `0x180096170`: `Windows.PrintWorkflowBackgroundTask`
- `0x180096165`: `Windows.UserDataTaskDataProvider`
- `0x180096191`: `Windows.PrintSupportExtension`

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
0x1800960fc  mov     [rsp-8+arg_0], rbx
0x180096101  mov     [rsp-8+arg_8], rdi
0x180096106  push    rbp
0x180096107  lea     rbp, [rsp-57h]
0x18009610c  sub     rsp, 90h
0x180096113  lea     rax, aWindowsBackgro; "Windows.BackgroundTasks"
0x18009611a  mov     rdi, rcx
0x18009611d  mov     [rbp+57h+var_70], rax
0x180096121  xor     ebx, ebx
0x180096123  lea     rax, aWindowsPreinst; "Windows.PreInstalledConfigTask"
0x18009612a  mov     [rbp+57h+var_68], rax
0x18009612e  lea     rax, aWindowsUpdatet; "Windows.UpdateTask"
0x180096135  mov     [rbp+57h+var_60], rax
0x180096139  lea     rax, aWindowsAppserv; "Windows.AppService"
0x180096140  mov     [rbp+57h+var_58], rax
0x180096144  lea     rax, aWindowsAppoint; "Windows.AppointmentDataProvider"
0x18009614b  mov     [rbp+57h+var_50], rax
0x18009614f  lea     rax, aWindowsContact_5; "Windows.ContactDataProvider"
0x180096156  mov     [rbp+57h+var_48], rax
0x18009615a  lea     rax, aWindowsEmailda; "Windows.EmailDataProvider"
0x180096161  mov     [rbp+57h+var_40], rax
0x180096165  lea     rax, aWindowsUserdat_0; "Windows.UserDataTaskDataProvider"
0x18009616c  mov     [rbp+57h+var_38], rax
0x180096170  lea     rax, aWindowsPrintwo; "Windows.PrintWorkflowBackgroundTask"
0x180096177  mov     [rbp+57h+var_30], rax
0x18009617b  lea     rax, aWindowsBarcode_0; "Windows.BarcodeScannerProvider"
0x180096182  mov     [rbp+57h+var_28], rax
0x180096186  lea     rax, aWindowsPospaym; "Windows.PosPaymentConnector"
0x18009618d  mov     [rbp+57h+var_20], rax
0x180096191  lea     rax, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x180096198  mov     [rbp+57h+var_18], rax
0x18009619c  lea     rax, aWindowsPrintsu; "Windows.PrintSupportWorkflow"
0x1800961a3  mov     [rbp+57h+var_10], rax
0x1800961a7  lea     rax, aWindowsPrintsu_0; "Windows.PrintSupportVirtualPrinterWorkf"...
0x1800961ae  mov     [rbp+57h+var_8], rax
0x1800961b2  cmp     ebx, 0Eh
0x1800961b5  jnb     short loc_1800961D1
0x1800961b7  mov     rdx, [rbp+rbx*8+57h+var_70]
0x1800961bc  mov     rcx, rdi
0x1800961bf  call    cs:__imp__o__wcsicmp
0x1800961c5  test    eax, eax
0x1800961c7  jz      short loc_1800961CD
0x1800961c9  inc     ebx
0x1800961cb  jmp     short loc_1800961B2
0x1800961cd  mov     al, 1
0x1800961cf  jmp     short loc_1800961D3
0x1800961d1  xor     al, al
0x1800961d3  lea     r11, [rsp+90h+var_s0]
0x1800961db  mov     rbx, [r11+10h]
0x1800961df  mov     rdi, [r11+18h]
0x1800961e3  mov     rsp, r11
0x1800961e6  pop     rbp
0x1800961e7  retn
```
