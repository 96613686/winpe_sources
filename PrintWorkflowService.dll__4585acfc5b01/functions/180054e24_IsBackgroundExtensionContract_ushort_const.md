# IsBackgroundExtensionContract(ushort const *)

- ea: `0x180054e24`
- end: `0x180054f10`
- name: `?IsBackgroundExtensionContract@@YA_NPEBG@Z`
- size: `236`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180055520`

## callees

- `0x180054e24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180054ee7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180054ee7`

## string_xrefs

- `0x180054e98`: `Windows.PrintWorkflowBackgroundTask`
- `0x180054eb9`: `Windows.PrintSupportExtension`
- `0x180054e4b`: `Windows.PreInstalledConfigTask`
- `0x180054e3b`: `Windows.BackgroundTasks`
- `0x180054e61`: `Windows.AppService`
- `0x180054e56`: `Windows.UpdateTask`
- `0x180054e8d`: `Windows.UserDataTaskDataProvider`

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
0x180054e24  mov     [rsp-8+arg_0], rbx
0x180054e29  mov     [rsp-8+arg_8], rdi
0x180054e2e  push    rbp
0x180054e2f  lea     rbp, [rsp-57h]
0x180054e34  sub     rsp, 90h
0x180054e3b  lea     rax, aWindowsBackgro; "Windows.BackgroundTasks"
0x180054e42  mov     rdi, rcx
0x180054e45  mov     [rbp+57h+var_70], rax
0x180054e49  xor     ebx, ebx
0x180054e4b  lea     rax, aWindowsPreinst; "Windows.PreInstalledConfigTask"
0x180054e52  mov     [rbp+57h+var_68], rax
0x180054e56  lea     rax, aWindowsUpdatet; "Windows.UpdateTask"
0x180054e5d  mov     [rbp+57h+var_60], rax
0x180054e61  lea     rax, aWindowsAppserv; "Windows.AppService"
0x180054e68  mov     [rbp+57h+var_58], rax
0x180054e6c  lea     rax, aWindowsAppoint; "Windows.AppointmentDataProvider"
0x180054e73  mov     [rbp+57h+var_50], rax
0x180054e77  lea     rax, aWindowsContact_5; "Windows.ContactDataProvider"
0x180054e7e  mov     [rbp+57h+var_48], rax
0x180054e82  lea     rax, aWindowsEmailda; "Windows.EmailDataProvider"
0x180054e89  mov     [rbp+57h+var_40], rax
0x180054e8d  lea     rax, aWindowsUserdat_0; "Windows.UserDataTaskDataProvider"
0x180054e94  mov     [rbp+57h+var_38], rax
0x180054e98  lea     rax, SourceString; "Windows.PrintWorkflowBackgroundTask"
0x180054e9f  mov     [rbp+57h+var_30], rax
0x180054ea3  lea     rax, aWindowsBarcode_0; "Windows.BarcodeScannerProvider"
0x180054eaa  mov     [rbp+57h+var_28], rax
0x180054eae  lea     rax, aWindowsPospaym; "Windows.PosPaymentConnector"
0x180054eb5  mov     [rbp+57h+var_20], rax
0x180054eb9  lea     rax, aWindowsPrintsu_3; "Windows.PrintSupportExtension"
0x180054ec0  mov     [rbp+57h+var_18], rax
0x180054ec4  lea     rax, aWindowsPrintsu; "Windows.PrintSupportWorkflow"
0x180054ecb  mov     [rbp+57h+var_10], rax
0x180054ecf  lea     rax, aWindowsPrintsu_1; "Windows.PrintSupportVirtualPrinterWorkf"...
0x180054ed6  mov     [rbp+57h+var_8], rax
0x180054eda  cmp     ebx, 0Eh
0x180054edd  jnb     short loc_180054EF9
0x180054edf  mov     rdx, [rbp+rbx*8+57h+var_70]
0x180054ee4  mov     rcx, rdi
0x180054ee7  call    cs:__imp__o__wcsicmp
0x180054eed  test    eax, eax
0x180054eef  jz      short loc_180054EF5
0x180054ef1  inc     ebx
0x180054ef3  jmp     short loc_180054EDA
0x180054ef5  mov     al, 1
0x180054ef7  jmp     short loc_180054EFB
0x180054ef9  xor     al, al
0x180054efb  lea     r11, [rsp+90h+var_s0]
0x180054f03  mov     rbx, [r11+10h]
0x180054f07  mov     rdi, [r11+18h]
0x180054f0b  mov     rsp, r11
0x180054f0e  pop     rbp
0x180054f0f  retn
```
