# PrintConfig::CJobEnumerationHelper::IsValidJobNotification(ulong,ulong)

- ea: `0x180098c48`
- end: `0x180098eae`
- name: `?IsValidJobNotification@CJobEnumerationHelper@PrintConfig@@QEAA_NKK@Z`
- size: `614`
- prototype: `char __fastcall(HANDLE *this, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180099540`

## callees

- `0x180004564`
- `0x18000f830`
- `0x180018f00`
- `0x180018f58`
- `0x1800197b4`
- `0x180098c48`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180098ddd`
- `KERNEL32!GetLastError` at `0x180098e46`
- `KERNEL32!GetLastError` at `0x180098ddd`
- `KERNEL32!GetLastError` at `0x180098e46`
- `WINSPOOL!FreePrinterNotifyInfo` at `0x180098cec`
- `WINSPOOL!FreePrinterNotifyInfo` at `0x180098d25`
- `WINSPOOL!FreePrinterNotifyInfo` at `0x180098db9`
- `WINSPOOL!FreePrinterNotifyInfo` at `0x180098cec`
- `WINSPOOL!FreePrinterNotifyInfo` at `0x180098d25`
- `WINSPOOL!FreePrinterNotifyInfo` at `0x180098db9`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x180098c8d`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x180098d08`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x180098c8d`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x180098d08`

## string_xrefs

- `0x180098cb8`: `Attempting to refresh job change notifications`
- `0x180098cbf`: `PrintConfig::CJobEnumerationHelper::IsValidJobNotification`
- `0x180098d69`: `New print job added inside the printer queue view.`
- `0x180098d70`: `PrintConfig::CJobEnumerationHelper::IsNotificationWithinView`
- `0x180098d87`: `PrintConfig::CJobEnumerationHelper::IsNotificationWithinView`
- `0x180098da2`: `PrintConfig::CJobEnumerationHelper::IsNotificationWithinView`
- `0x180098d80`: `New print job added outside of the printer queue view.`
- `0x180098d9b`: `"PRINTER_CHANGE_DELETE_JOB or PRINTER_CHANGE_SET_JOB" change detected.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall PrintConfig::CJobEnumerationHelper::IsValidJobNotification(HANDLE *this, int a2, int a3)
{
  __int16 v7; // di
  char v8; // bl
  unsigned int i; // edx
  __int64 v10; // r8
  signed int v11; // eax
  unsigned int v12; // ebx
  signed int LastError; // eax
  unsigned int v14; // ebx
  int pvReserved; // [rsp+28h] [rbp-48h] BYREF
  __int64 v16; // [rsp+2Ch] [rbp-44h]
  int v17; // [rsp+34h] [rbp-3Ch]
  __int64 v18; // [rsp+38h] [rbp-38h]
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-28h] BYREF
  DWORD pdwChange; // [rsp+90h] [rbp+20h] BYREF
  LPVOID ppPrinterNotifyInfo; // [rsp+A8h] [rbp+38h] BYREF

  pdwChange = 0;
  ppPrinterNotifyInfo = 0;
  if ( !FindNextPrinterChangeNotification(this[2], &pdwChange, 0, &ppPrinterNotifyInfo) )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x23u, &WPP_cdb5cd81762639951fa3d2229fdd7025_Traceguids, v14);
    }
    hr_error::hr_error((hr_error *)&pvReserved, v14);
    throw (hr_error *)&pvReserved;
  }
  if ( ppPrinterNotifyInfo && (*((_BYTE *)ppPrinterNotifyInfo + 4) & 1) != 0 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CJobEnumerationHelper::IsValidJobNotification",
      L"Attempting to refresh job change notifications");
    pvReserved = 2;
    v16 = 1;
    v17 = 0;
    v18 = 0;
    if ( ppPrinterNotifyInfo )
      FreePrinterNotifyInfo((PPRINTER_NOTIFY_INFO)ppPrinterNotifyInfo);
    if ( !FindNextPrinterChangeNotification(this[2], &pdwChange, &pvReserved, &ppPrinterNotifyInfo) )
    {
      v11 = GetLastError();
      v12 = v11;
      if ( v11 > 0 )
        v12 = (unsigned __int16)v11 | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x24u, &WPP_cdb5cd81762639951fa3d2229fdd7025_Traceguids, v12);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v12);
      throw (hr_error *)pExceptionObject;
    }
    if ( ppPrinterNotifyInfo )
      FreePrinterNotifyInfo((PPRINTER_NOTIFY_INFO)ppPrinterNotifyInfo);
    return 1;
  }
  else
  {
    v7 = pdwChange;
    v8 = 0;
    if ( (pdwChange & 0x100) != 0 )
    {
      for ( i = 0; i < *((_DWORD *)ppPrinterNotifyInfo + 2); ++i )
      {
        v10 = 32LL * i;
        if ( *(_WORD *)((char *)ppPrinterNotifyInfo + v10 + 18) == 15
          && *(_DWORD *)((char *)ppPrinterNotifyInfo + v10 + 32) <= (unsigned int)(a2 + a3) )
        {
          Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
            "PrintConfig::CJobEnumerationHelper::IsNotificationWithinView",
            L"New print job added inside the printer queue view.");
          v8 = 1;
          goto LABEL_18;
        }
      }
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::CJobEnumerationHelper::IsNotificationWithinView",
        L"New print job added outside of the printer queue view.");
    }
LABEL_18:
    if ( (v7 & 0x600) != 0 )
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::CJobEnumerationHelper::IsNotificationWithinView",
        L"\"PRINTER_CHANGE_DELETE_JOB or PRINTER_CHANGE_SET_JOB\" change detected.");
      v8 = 1;
    }
    if ( ppPrinterNotifyInfo )
      FreePrinterNotifyInfo((PPRINTER_NOTIFY_INFO)ppPrinterNotifyInfo);
    return v8;
  }
}

```

## disassembly

```asm
0x180098c48  mov     rax, rsp
0x180098c4b  push    rbp
0x180098c4c  push    rdi
0x180098c4d  push    r14
0x180098c4f  mov     rbp, rsp
0x180098c52  sub     rsp, 70h
0x180098c56  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x180098c5e  mov     [rax+10h], rbx
0x180098c62  mov     [rax+18h], rsi
0x180098c66  mov     esi, r8d
0x180098c69  mov     r14d, edx
0x180098c6c  mov     rbx, rcx
0x180098c6f  mov     [rbp+pdwChange], 0
0x180098c76  mov     [rbp+ppPrinterNotifyInfo], 0
0x180098c7e  lea     r9, [rbp+ppPrinterNotifyInfo]; ppPrinterNotifyInfo
0x180098c82  xor     r8d, r8d; pvReserved
0x180098c85  lea     rdx, [rbp+pdwChange]; pdwChange
0x180098c89  mov     rcx, [rcx+10h]; hChange
0x180098c8d  call    cs:__imp_FindNextPrinterChangeNotification
0x180098c94  nop     dword ptr [rax+rax+00h]
0x180098c99  test    eax, eax
0x180098c9b  jz      loc_180098E46
0x180098ca1  mov     rcx, [rbp+ppPrinterNotifyInfo]
0x180098ca5  test    rcx, rcx
0x180098ca8  jz      loc_180098D38
0x180098cae  test    byte ptr [rcx+4], 1
0x180098cb2  jz      loc_180098D38
0x180098cb8  lea     rdx, aAttemptingToRe; "Attempting to refresh job change notifi"...
0x180098cbf  lea     rcx, aPrintconfigCjo; "PrintConfig::CJobEnumerationHelper::IsV"...
0x180098cc6  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180098ccb  mov     [rbp+pvReserved], 2
0x180098cd2  mov     [rbp+var_44], 1
0x180098cda  xor     eax, eax
0x180098cdc  mov     [rbp+var_3C], eax
0x180098cdf  mov     [rbp+var_38], rax
0x180098ce3  mov     rcx, [rbp+ppPrinterNotifyInfo]; pPrinterNotifyInfo
0x180098ce7  test    rcx, rcx
0x180098cea  jz      short loc_180098CF8
0x180098cec  call    cs:__imp_FreePrinterNotifyInfo
0x180098cf3  nop     dword ptr [rax+rax+00h]
0x180098cf8  lea     r9, [rbp+ppPrinterNotifyInfo]; ppPrinterNotifyInfo
0x180098cfc  lea     r8, [rbp+pvReserved]; pvReserved
0x180098d00  lea     rdx, [rbp+pdwChange]; pdwChange
0x180098d04  mov     rcx, [rbx+10h]; hChange
0x180098d08  call    cs:__imp_FindNextPrinterChangeNotification
0x180098d0f  nop     dword ptr [rax+rax+00h]
0x180098d14  test    eax, eax
0x180098d16  jz      loc_180098DDD
0x180098d1c  mov     rcx, [rbp+ppPrinterNotifyInfo]; pPrinterNotifyInfo
0x180098d20  test    rcx, rcx
0x180098d23  jz      short loc_180098D31
0x180098d25  call    cs:__imp_FreePrinterNotifyInfo
0x180098d2c  nop     dword ptr [rax+rax+00h]
0x180098d31  mov     al, 1
0x180098d33  jmp     loc_180098DC7
0x180098d38  mov     edi, [rbp+pdwChange]
0x180098d3b  xor     bl, bl
0x180098d3d  bt      edi, 8
0x180098d41  jnb     short loc_180098D93
0x180098d43  xor     edx, edx
0x180098d45  cmp     edx, [rcx+8]
0x180098d48  jnb     short loc_180098D80
0x180098d4a  mov     r8d, edx
0x180098d4d  shl     r8, 5
0x180098d51  cmp     word ptr [r8+rcx+12h], 0Fh
0x180098d58  jnz     short loc_180098D65
0x180098d5a  lea     eax, [r14+rsi]
0x180098d5e  cmp     [r8+rcx+20h], eax
0x180098d63  jbe     short loc_180098D69
0x180098d65  inc     edx
0x180098d67  jmp     short loc_180098D45
0x180098d69  lea     rdx, aNewPrintJobAdd; "New print job added inside the printer "...
0x180098d70  lea     rcx, aPrintconfigCjo_0; "PrintConfig::CJobEnumerationHelper::IsN"...
0x180098d77  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180098d7c  mov     bl, 1
0x180098d7e  jmp     short loc_180098D93
0x180098d80  lea     rdx, aNewPrintJobAdd_0; "New print job added outside of the prin"...
0x180098d87  lea     rcx, aPrintconfigCjo_0; "PrintConfig::CJobEnumerationHelper::IsN"...
0x180098d8e  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180098d93  test    edi, 600h
0x180098d99  jz      short loc_180098DB0
0x180098d9b  lea     rdx, aPrinterChangeD; "\"PRINTER_CHANGE_DELETE_JOB or PRINTER_"...
0x180098da2  lea     rcx, aPrintconfigCjo_0; "PrintConfig::CJobEnumerationHelper::IsN"...
0x180098da9  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180098dae  mov     bl, 1
0x180098db0  mov     rcx, [rbp+ppPrinterNotifyInfo]; pPrinterNotifyInfo
0x180098db4  test    rcx, rcx
0x180098db7  jz      short loc_180098DC5
0x180098db9  call    cs:__imp_FreePrinterNotifyInfo
0x180098dc0  nop     dword ptr [rax+rax+00h]
0x180098dc5  mov     al, bl
0x180098dc7  lea     r11, [rsp+70h+var_s0]
0x180098dcc  mov     rbx, [r11+28h]
0x180098dd0  mov     rsi, [r11+30h]
0x180098dd4  mov     rsp, r11
0x180098dd7  pop     r14
0x180098dd9  pop     rdi
0x180098dda  pop     rbp
0x180098ddb  retn
0x180098ddd  call    cs:__imp_GetLastError
0x180098de4  nop     dword ptr [rax+rax+00h]
0x180098de9  nop
0x180098dea  mov     ebx, eax
0x180098dec  test    eax, eax
0x180098dee  jle     short loc_180098DF9
0x180098df0  movzx   ebx, ax
0x180098df3  or      ebx, 80070000h
0x180098df9  lea     rax, WPP_GLOBAL_Control
0x180098e00  mov     rcx, cs:WPP_GLOBAL_Control
0x180098e07  cmp     rcx, rax
0x180098e0a  jz      short loc_180098E2A
0x180098e0c  test    byte ptr [rcx+44h], 1
0x180098e10  jz      short loc_180098E2A
0x180098e12  mov     edx, 24h ; '$'
0x180098e17  mov     r9d, ebx
0x180098e1a  lea     r8, WPP_cdb5cd81762639951fa3d2229fdd7025_Traceguids
0x180098e21  mov     rcx, [rcx+38h]
0x180098e25  call    WPP_SF_d
0x180098e2a  mov     edx, ebx; int
0x180098e2c  lea     rcx, [rbp+pExceptionObject]; this
0x180098e30  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180098e35  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180098e3c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180098e40  call    _CxxThrowException_0
0x180098e46  call    cs:__imp_GetLastError
0x180098e4d  nop     dword ptr [rax+rax+00h]
0x180098e52  mov     ebx, eax
0x180098e54  test    eax, eax
0x180098e56  jle     short loc_180098E61
0x180098e58  movzx   ebx, ax
0x180098e5b  or      ebx, 80070000h
0x180098e61  lea     rax, WPP_GLOBAL_Control
0x180098e68  mov     rcx, cs:WPP_GLOBAL_Control
0x180098e6f  cmp     rcx, rax
0x180098e72  jz      short loc_180098E92
0x180098e74  test    byte ptr [rcx+44h], 1
0x180098e78  jz      short loc_180098E92
0x180098e7a  mov     edx, 23h ; '#'
0x180098e7f  mov     r9d, ebx
0x180098e82  lea     r8, WPP_cdb5cd81762639951fa3d2229fdd7025_Traceguids
0x180098e89  mov     rcx, [rcx+38h]
0x180098e8d  call    WPP_SF_d
0x180098e92  mov     edx, ebx; int
0x180098e94  lea     rcx, [rbp+pvReserved]; this
0x180098e98  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180098e9d  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180098ea4  lea     rcx, [rbp+pvReserved]; pExceptionObject
0x180098ea8  call    _CxxThrowException_0
```
