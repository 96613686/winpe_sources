# PrintConfig::CJobEnumerationHelper::IsValidJobNotification(ulong,ulong)

- ea: `0x1800953c8`
- end: `0x1800955fb`
- name: `?IsValidJobNotification@CJobEnumerationHelper@PrintConfig@@QEAA_NKK@Z`
- size: `563`
- prototype: `bool __fastcall(PrintConfig::CJobEnumerationHelper *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180095c60`

## callees

- `0x180004424`
- `0x18000f380`
- `0x1800183a0`
- `0x1800183f8`
- `0x180018bbc`
- `0x1800953c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180095536`
- `KERNEL32!GetLastError` at `0x180095599`
- `KERNEL32!GetLastError` at `0x180095536`
- `KERNEL32!GetLastError` at `0x180095599`
- `WINSPOOL!FreePrinterNotifyInfo` at `0x18009545e`
- `WINSPOOL!FreePrinterNotifyInfo` at `0x18009548b`
- `WINSPOOL!FreePrinterNotifyInfo` at `0x180095519`
- `WINSPOOL!FreePrinterNotifyInfo` at `0x18009545e`
- `WINSPOOL!FreePrinterNotifyInfo` at `0x18009548b`
- `WINSPOOL!FreePrinterNotifyInfo` at `0x180095519`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x18009540d`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x180095474`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x18009540d`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x180095474`

## string_xrefs

- `0x18009542a`: `Attempting to refresh job change notifications`
- `0x180095431`: `PrintConfig::CJobEnumerationHelper::IsValidJobNotification`
- `0x1800954c9`: `New print job added inside the printer queue view.`
- `0x1800954d0`: `PrintConfig::CJobEnumerationHelper::IsNotificationWithinView`
- `0x1800954e7`: `PrintConfig::CJobEnumerationHelper::IsNotificationWithinView`
- `0x180095502`: `PrintConfig::CJobEnumerationHelper::IsNotificationWithinView`
- `0x1800954e0`: `New print job added outside of the printer queue view.`
- `0x1800954fb`: `"PRINTER_CHANGE_DELETE_JOB or PRINTER_CHANGE_SET_JOB" change detected.`

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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, &WPP_cdb5cd81762639951fa3d2229fdd7025_Traceguids, v14);
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 36, &WPP_cdb5cd81762639951fa3d2229fdd7025_Traceguids, v12);
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
0x1800953c8  mov     rax, rsp
0x1800953cb  push    rbp
0x1800953cc  push    rdi
0x1800953cd  push    r14
0x1800953cf  mov     rbp, rsp
0x1800953d2  sub     rsp, 70h
0x1800953d6  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x1800953de  mov     [rax+10h], rbx
0x1800953e2  mov     [rax+18h], rsi
0x1800953e6  mov     esi, r8d
0x1800953e9  mov     r14d, edx
0x1800953ec  mov     rbx, rcx
0x1800953ef  mov     [rbp+pdwChange], 0
0x1800953f6  mov     [rbp+ppPrinterNotifyInfo], 0
0x1800953fe  lea     r9, [rbp+ppPrinterNotifyInfo]; ppPrinterNotifyInfo
0x180095402  xor     r8d, r8d; pvReserved
0x180095405  lea     rdx, [rbp+pdwChange]; pdwChange
0x180095409  mov     rcx, [rcx+10h]; hChange
0x18009540d  call    cs:__imp_FindNextPrinterChangeNotification
0x180095413  test    eax, eax
0x180095415  jz      loc_180095599
0x18009541b  mov     rcx, [rbp+ppPrinterNotifyInfo]
0x18009541f  test    rcx, rcx
0x180095422  jz      short loc_180095498
0x180095424  test    byte ptr [rcx+4], 1
0x180095428  jz      short loc_180095498
0x18009542a  lea     rdx, aAttemptingToRe; "Attempting to refresh job change notifi"...
0x180095431  lea     rcx, aPrintconfigCjo; "PrintConfig::CJobEnumerationHelper::IsV"...
0x180095438  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18009543d  mov     [rbp+pvReserved], 2
0x180095444  mov     [rbp+var_44], 1
0x18009544c  xor     eax, eax
0x18009544e  mov     [rbp+var_3C], eax
0x180095451  mov     [rbp+var_38], rax
0x180095455  mov     rcx, [rbp+ppPrinterNotifyInfo]; pPrinterNotifyInfo
0x180095459  test    rcx, rcx
0x18009545c  jz      short loc_180095464
0x18009545e  call    cs:__imp_FreePrinterNotifyInfo
0x180095464  lea     r9, [rbp+ppPrinterNotifyInfo]; ppPrinterNotifyInfo
0x180095468  lea     r8, [rbp+pvReserved]; pvReserved
0x18009546c  lea     rdx, [rbp+pdwChange]; pdwChange
0x180095470  mov     rcx, [rbx+10h]; hChange
0x180095474  call    cs:__imp_FindNextPrinterChangeNotification
0x18009547a  test    eax, eax
0x18009547c  jz      loc_180095536
0x180095482  mov     rcx, [rbp+ppPrinterNotifyInfo]; pPrinterNotifyInfo
0x180095486  test    rcx, rcx
0x180095489  jz      short loc_180095491
0x18009548b  call    cs:__imp_FreePrinterNotifyInfo
0x180095491  mov     al, 1
0x180095493  jmp     loc_180095521
0x180095498  mov     edi, [rbp+pdwChange]
0x18009549b  xor     bl, bl
0x18009549d  bt      edi, 8
0x1800954a1  jnb     short loc_1800954F3
0x1800954a3  xor     edx, edx
0x1800954a5  cmp     edx, [rcx+8]
0x1800954a8  jnb     short loc_1800954E0
0x1800954aa  mov     r8d, edx
0x1800954ad  shl     r8, 5
0x1800954b1  cmp     word ptr [r8+rcx+12h], 0Fh
0x1800954b8  jnz     short loc_1800954C5
0x1800954ba  lea     eax, [r14+rsi]
0x1800954be  cmp     [r8+rcx+20h], eax
0x1800954c3  jbe     short loc_1800954C9
0x1800954c5  inc     edx
0x1800954c7  jmp     short loc_1800954A5
0x1800954c9  lea     rdx, aNewPrintJobAdd; "New print job added inside the printer "...
0x1800954d0  lea     rcx, aPrintconfigCjo_0; "PrintConfig::CJobEnumerationHelper::IsN"...
0x1800954d7  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800954dc  mov     bl, 1
0x1800954de  jmp     short loc_1800954F3
0x1800954e0  lea     rdx, aNewPrintJobAdd_0; "New print job added outside of the prin"...
0x1800954e7  lea     rcx, aPrintconfigCjo_0; "PrintConfig::CJobEnumerationHelper::IsN"...
0x1800954ee  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800954f3  test    edi, 600h
0x1800954f9  jz      short loc_180095510
0x1800954fb  lea     rdx, aPrinterChangeD; "\"PRINTER_CHANGE_DELETE_JOB or PRINTER_"...
0x180095502  lea     rcx, aPrintconfigCjo_0; "PrintConfig::CJobEnumerationHelper::IsN"...
0x180095509  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18009550e  mov     bl, 1
0x180095510  mov     rcx, [rbp+ppPrinterNotifyInfo]; pPrinterNotifyInfo
0x180095514  test    rcx, rcx
0x180095517  jz      short loc_18009551F
0x180095519  call    cs:__imp_FreePrinterNotifyInfo
0x18009551f  mov     al, bl
0x180095521  lea     r11, [rsp+70h+var_s0]
0x180095526  mov     rbx, [r11+28h]
0x18009552a  mov     rsi, [r11+30h]
0x18009552e  mov     rsp, r11
0x180095531  pop     r14
0x180095533  pop     rdi
0x180095534  pop     rbp
0x180095535  retn
0x180095536  call    cs:__imp_GetLastError
0x18009553c  nop
0x18009553d  mov     ebx, eax
0x18009553f  test    eax, eax
0x180095541  jle     short loc_18009554C
0x180095543  movzx   ebx, ax
0x180095546  or      ebx, 80070000h
0x18009554c  lea     rax, WPP_GLOBAL_Control
0x180095553  mov     rcx, cs:WPP_GLOBAL_Control
0x18009555a  cmp     rcx, rax
0x18009555d  jz      short loc_18009557D
0x18009555f  test    byte ptr [rcx+44h], 1
0x180095563  jz      short loc_18009557D
0x180095565  mov     edx, 24h ; '$'
0x18009556a  mov     r9d, ebx
0x18009556d  lea     r8, WPP_cdb5cd81762639951fa3d2229fdd7025_Traceguids
0x180095574  mov     rcx, [rcx+38h]
0x180095578  call    WPP_SF_d
0x18009557d  mov     edx, ebx; int
0x18009557f  lea     rcx, [rbp+pExceptionObject]; this
0x180095583  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180095588  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18009558f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180095593  call    _CxxThrowException_0
0x180095599  call    cs:__imp_GetLastError
0x18009559f  mov     ebx, eax
0x1800955a1  test    eax, eax
0x1800955a3  jle     short loc_1800955AE
0x1800955a5  movzx   ebx, ax
0x1800955a8  or      ebx, 80070000h
0x1800955ae  lea     rax, WPP_GLOBAL_Control
0x1800955b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800955bc  cmp     rcx, rax
0x1800955bf  jz      short loc_1800955DF
0x1800955c1  test    byte ptr [rcx+44h], 1
0x1800955c5  jz      short loc_1800955DF
0x1800955c7  mov     edx, 23h ; '#'
0x1800955cc  mov     r9d, ebx
0x1800955cf  lea     r8, WPP_cdb5cd81762639951fa3d2229fdd7025_Traceguids
0x1800955d6  mov     rcx, [rcx+38h]
0x1800955da  call    WPP_SF_d
0x1800955df  mov     edx, ebx; int
0x1800955e1  lea     rcx, [rbp+pvReserved]; this
0x1800955e5  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800955ea  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800955f1  lea     rcx, [rbp+pvReserved]; pExceptionObject
0x1800955f5  call    _CxxThrowException_0
```
