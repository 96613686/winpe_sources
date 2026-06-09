# IsBackgroundExtensionContract(ushort const *)

- ea: `0x180068cc8`
- end: `0x180068db4`
- name: `?IsBackgroundExtensionContract@@YA_NPEBG@Z`
- size: `236`
- prototype: `bool __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180069360`

## callees

- `0x180068cc8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180068d8b`
- `msvcrt!_wcsicmp` at `0x180068d8b`

## string_xrefs

- `0x180068cfa`: `Windows.UpdateTask`
- `0x180068d05`: `Windows.AppService`
- `0x180068cdf`: `Windows.BackgroundTasks`
- `0x180068cef`: `Windows.PreInstalledConfigTask`
- `0x180068d31`: `Windows.UserDataTaskDataProvider`
- `0x180068d5d`: `Windows.PrintSupportExtension`
- `0x180068d3c`: `Windows.PrintWorkflowBackgroundTask`

## pseudocode

```c
char __fastcall IsBackgroundExtensionContract(wchar_t *String1)
{
  __int64 v2; // rbx
  wchar_t *String2[14]; // [rsp+20h] [rbp-19h]

  String2[0] = L"Windows.BackgroundTasks";
  v2 = 0;
  String2[1] = L"Windows.PreInstalledConfigTask";
  String2[2] = L"Windows.UpdateTask";
  String2[3] = L"Windows.AppService";
  String2[4] = L"Windows.AppointmentDataProvider";
  String2[5] = L"Windows.ContactDataProvider";
  String2[6] = L"Windows.EmailDataProvider";
  String2[7] = L"Windows.UserDataTaskDataProvider";
  String2[8] = L"Windows.PrintWorkflowBackgroundTask";
  String2[9] = L"Windows.BarcodeScannerProvider";
  String2[10] = L"Windows.PosPaymentConnector";
  String2[11] = L"Windows.PrintSupportExtension";
  String2[12] = L"Windows.PrintSupportWorkflow";
  String2[13] = L"Windows.PrintSupportVirtualPrinterWorkflow";
  while ( (unsigned int)v2 < 0xE )
  {
    if ( !_wcsicmp(String1, String2[v2]) )
      return 1;
    v2 = (unsigned int)(v2 + 1);
  }
  return 0;
}

```

## disassembly

```asm
0x180068cc8  mov     [rsp-8+arg_0], rbx
0x180068ccd  mov     [rsp-8+arg_8], rdi
0x180068cd2  push    rbp
0x180068cd3  lea     rbp, [rsp-57h]
0x180068cd8  sub     rsp, 90h
0x180068cdf  lea     rax, aWindowsBackgro; "Windows.BackgroundTasks"
0x180068ce6  mov     rdi, rcx
0x180068ce9  mov     [rbp+57h+String2], rax
0x180068ced  xor     ebx, ebx
0x180068cef  lea     rax, aWindowsPreinst; "Windows.PreInstalledConfigTask"
0x180068cf6  mov     [rbp+57h+var_68], rax
0x180068cfa  lea     rax, aWindowsUpdatet; "Windows.UpdateTask"
0x180068d01  mov     [rbp+57h+var_60], rax
0x180068d05  lea     rax, aWindowsAppserv; "Windows.AppService"
0x180068d0c  mov     [rbp+57h+var_58], rax
0x180068d10  lea     rax, aWindowsAppoint; "Windows.AppointmentDataProvider"
0x180068d17  mov     [rbp+57h+var_50], rax
0x180068d1b  lea     rax, aWindowsContact_5; "Windows.ContactDataProvider"
0x180068d22  mov     [rbp+57h+var_48], rax
0x180068d26  lea     rax, aWindowsEmailda; "Windows.EmailDataProvider"
0x180068d2d  mov     [rbp+57h+var_40], rax
0x180068d31  lea     rax, aWindowsUserdat_0; "Windows.UserDataTaskDataProvider"
0x180068d38  mov     [rbp+57h+var_38], rax
0x180068d3c  lea     rax, aWindowsPrintwo; "Windows.PrintWorkflowBackgroundTask"
0x180068d43  mov     [rbp+57h+var_30], rax
0x180068d47  lea     rax, aWindowsBarcode_0; "Windows.BarcodeScannerProvider"
0x180068d4e  mov     [rbp+57h+var_28], rax
0x180068d52  lea     rax, aWindowsPospaym; "Windows.PosPaymentConnector"
0x180068d59  mov     [rbp+57h+var_20], rax
0x180068d5d  lea     rax, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x180068d64  mov     [rbp+57h+var_18], rax
0x180068d68  lea     rax, aWindowsPrintsu; "Windows.PrintSupportWorkflow"
0x180068d6f  mov     [rbp+57h+var_10], rax
0x180068d73  lea     rax, aWindowsPrintsu_0; "Windows.PrintSupportVirtualPrinterWorkf"...
0x180068d7a  mov     [rbp+57h+var_8], rax
0x180068d7e  cmp     ebx, 0Eh
0x180068d81  jnb     short loc_180068D9D
0x180068d83  mov     rdx, [rbp+rbx*8+57h+String2]; String2
0x180068d88  mov     rcx, rdi; String1
0x180068d8b  call    cs:__imp__wcsicmp
0x180068d91  test    eax, eax
0x180068d93  jz      short loc_180068D99
0x180068d95  inc     ebx
0x180068d97  jmp     short loc_180068D7E
0x180068d99  mov     al, 1
0x180068d9b  jmp     short loc_180068D9F
0x180068d9d  xor     al, al
0x180068d9f  lea     r11, [rsp+90h+var_s0]
0x180068da7  mov     rbx, [r11+10h]
0x180068dab  mov     rdi, [r11+18h]
0x180068daf  mov     rsp, r11
0x180068db2  pop     rbp
0x180068db3  retn
```
