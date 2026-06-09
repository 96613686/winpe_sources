# IsBackgroundExtensionContract(ushort const *)

- ea: `0x180040664`
- end: `0x180040750`
- name: `?IsBackgroundExtensionContract@@YA_NPEBG@Z`
- size: `236`
- prototype: `bool __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180042e90`

## callees

- `0x180040664`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180040727`
- `msvcrt!_wcsicmp` at `0x180040727`

## string_xrefs

- `0x18004067b`: `Windows.BackgroundTasks`
- `0x1800406a1`: `Windows.AppService`
- `0x18004068b`: `Windows.PreInstalledConfigTask`
- `0x180040696`: `Windows.UpdateTask`
- `0x1800406cd`: `Windows.UserDataTaskDataProvider`
- `0x1800406d8`: `Windows.PrintWorkflowBackgroundTask`
- `0x1800406f9`: `Windows.PrintSupportExtension`

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
0x180040664  mov     [rsp-8+arg_0], rbx
0x180040669  mov     [rsp-8+arg_8], rdi
0x18004066e  push    rbp
0x18004066f  lea     rbp, [rsp-57h]
0x180040674  sub     rsp, 90h
0x18004067b  lea     rax, aWindowsBackgro; "Windows.BackgroundTasks"
0x180040682  mov     rdi, rcx
0x180040685  mov     [rbp+57h+String2], rax
0x180040689  xor     ebx, ebx
0x18004068b  lea     rax, aWindowsPreinst; "Windows.PreInstalledConfigTask"
0x180040692  mov     [rbp+57h+var_68], rax
0x180040696  lea     rax, aWindowsUpdatet; "Windows.UpdateTask"
0x18004069d  mov     [rbp+57h+var_60], rax
0x1800406a1  lea     rax, aWindowsAppserv; "Windows.AppService"
0x1800406a8  mov     [rbp+57h+var_58], rax
0x1800406ac  lea     rax, aWindowsAppoint; "Windows.AppointmentDataProvider"
0x1800406b3  mov     [rbp+57h+var_50], rax
0x1800406b7  lea     rax, aWindowsContact_5; "Windows.ContactDataProvider"
0x1800406be  mov     [rbp+57h+var_48], rax
0x1800406c2  lea     rax, aWindowsEmailda; "Windows.EmailDataProvider"
0x1800406c9  mov     [rbp+57h+var_40], rax
0x1800406cd  lea     rax, aWindowsUserdat_0; "Windows.UserDataTaskDataProvider"
0x1800406d4  mov     [rbp+57h+var_38], rax
0x1800406d8  lea     rax, aWindowsPrintwo; "Windows.PrintWorkflowBackgroundTask"
0x1800406df  mov     [rbp+57h+var_30], rax
0x1800406e3  lea     rax, aWindowsBarcode_0; "Windows.BarcodeScannerProvider"
0x1800406ea  mov     [rbp+57h+var_28], rax
0x1800406ee  lea     rax, aWindowsPospaym; "Windows.PosPaymentConnector"
0x1800406f5  mov     [rbp+57h+var_20], rax
0x1800406f9  lea     rax, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x180040700  mov     [rbp+57h+var_18], rax
0x180040704  lea     rax, aWindowsPrintsu; "Windows.PrintSupportWorkflow"
0x18004070b  mov     [rbp+57h+var_10], rax
0x18004070f  lea     rax, aWindowsPrintsu_0; "Windows.PrintSupportVirtualPrinterWorkf"...
0x180040716  mov     [rbp+57h+var_8], rax
0x18004071a  cmp     ebx, 0Eh
0x18004071d  jnb     short loc_180040739
0x18004071f  mov     rdx, [rbp+rbx*8+57h+String2]; String2
0x180040724  mov     rcx, rdi; String1
0x180040727  call    cs:__imp__wcsicmp
0x18004072d  test    eax, eax
0x18004072f  jz      short loc_180040735
0x180040731  inc     ebx
0x180040733  jmp     short loc_18004071A
0x180040735  mov     al, 1
0x180040737  jmp     short loc_18004073B
0x180040739  xor     al, al
0x18004073b  lea     r11, [rsp+90h+var_s0]
0x180040743  mov     rbx, [r11+10h]
0x180040747  mov     rdi, [r11+18h]
0x18004074b  mov     rsp, r11
0x18004074e  pop     rbp
0x18004074f  retn
```
