# CActivatedEventArgsBase::v_GetActivationKind(HSTRING__ *,Windows::ApplicationModel::Activation::ActivationKind *)

- ea: `0x1800184d0`
- end: `0x1800186f0`
- name: `?v_GetActivationKind@CActivatedEventArgsBase@@EEAAJPEAUHSTRING__@@PEAW4ActivationKind@Activation@ApplicationModel@Windows@@@Z`
- size: `544`
- prototype: `int(CActivatedEventArgsBase *__hidden this, HSTRING, enum Windows::ApplicationModel::Activation::ActivationKind *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800165c4`
- `0x1800184d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800186b3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800186b3`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18001853b`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18001853b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018515`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018550`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001856e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018599`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800185a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800186cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018515`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018550`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001856e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018599`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800185a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800186cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001850a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001852b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800185b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001850a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001852b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800185b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180018566`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180018566`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001857f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001857f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800185e7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800185e7`

## string_xrefs

- `0x18001860f`: `Windows.BackgroundTasks`
- `0x18001861c`: `Windows.PreInstalledConfigTask`
- `0x180018627`: `Windows.UpdateTask`
- `0x180018632`: `Windows.AppService`
- `0x18001865e`: `Windows.UserDataTaskDataProvider`
- `0x180018669`: `Windows.PrintWorkflowBackgroundTask`
- `0x18001868a`: `Windows.PrintSupportExtension`

## pseudocode

```c
__int64 __fastcall CActivatedEventArgsBase::v_GetActivationKind(
        CActivatedEventArgsBase *this,
        HSTRING a2,
        enum Windows::ApplicationModel::Activation::ActivationKind *a3)
{
  const WCHAR *StringRawBuffer; // r12
  HSTRING v6; // rbx
  const wchar_t *v7; // rax
  size_t v8; // rax
  UINT32 v9; // esi
  HRESULT v10; // eax
  int v11; // esi
  unsigned int i; // edi
  char v13; // cl
  __int64 v14; // rdi
  __int64 v15; // rcx
  _QWORD v17[14]; // [rsp+30h] [rbp-39h]
  UINT32 length; // [rsp+E0h] [rbp+77h] BYREF
  HSTRING string; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  *(_DWORD *)a3 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  WindowsDeleteString(0);
  v6 = 0;
  string = 0;
  length = 0;
  v7 = WindowsGetStringRawBuffer(a2, &length);
  v8 = wcscspn(v7, L"+");
  v9 = v8;
  if ( v8 >= length )
  {
    WindowsDeleteString(string);
    string = 0;
    v10 = WindowsDuplicateString(a2, &string);
  }
  else
  {
    WindowsDeleteString(string);
    string = 0;
    v10 = WindowsSubstringWithSpecifiedLength(a2, 0, v9, &string);
  }
  v11 = v10;
  if ( v10 >= 0 )
  {
    v6 = string;
    string = 0;
  }
  WindowsDeleteString(0);
  WindowsDeleteString(string);
  if ( v11 >= 0 )
    StringRawBuffer = WindowsGetStringRawBuffer(v6, 0);
  for ( i = 0; ; ++i )
  {
    v13 = 0;
    if ( i >= 0x2E )
      break;
    if ( CompareStringOrdinal(StringRawBuffer, -1, (&off_18001BA00)[2 * i], -1, 0) == 2 )
    {
      v13 = 1;
      *(_DWORD *)a3 = *((_DWORD *)&off_18001BA00 + 4 * i + 2);
      break;
    }
  }
  if ( !v13 )
  {
    v14 = 0;
    v17[0] = L"Windows.BackgroundTasks";
    v17[1] = L"Windows.PreInstalledConfigTask";
    v17[2] = L"Windows.UpdateTask";
    v17[3] = L"Windows.AppService";
    v17[4] = L"Windows.AppointmentDataProvider";
    v17[5] = L"Windows.ContactDataProvider";
    v17[6] = L"Windows.EmailDataProvider";
    v17[7] = L"Windows.UserDataTaskDataProvider";
    v17[8] = L"Windows.PrintWorkflowBackgroundTask";
    v17[9] = L"Windows.BarcodeScannerProvider";
    v17[10] = L"Windows.PosPaymentConnector";
    v17[11] = L"Windows.PrintSupportExtension";
    v17[12] = L"Windows.PrintSupportWorkflow";
    v17[13] = L"Windows.PrintSupportVirtualPrinterWorkflow";
    while ( (unsigned int)_o__wcsicmp(StringRawBuffer, v17[v14]) )
    {
      v14 = (unsigned int)(v14 + 1);
      if ( (unsigned int)v14 >= 0xE )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v15);
        break;
      }
    }
  }
  WindowsDeleteString(v6);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800184d0  mov     [rsp-8+arg_0], rbx
0x1800184d5  mov     [rsp-8+arg_8], rsi
0x1800184da  push    rbp
0x1800184db  push    rdi
0x1800184dc  push    r12
0x1800184de  push    r14
0x1800184e0  push    r15
0x1800184e2  lea     rbp, [rsp-37h]
0x1800184e7  sub     rsp, 0A0h
0x1800184ee  mov     r14, r8
0x1800184f1  mov     rdi, rdx
0x1800184f4  test    r8, r8
0x1800184f7  jnz     short loc_1800184FE
0x1800184f9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800184fe  xor     edx, edx; length
0x180018500  mov     dword ptr [r14], 0
0x180018507  mov     rcx, rdi; string
0x18001850a  call    cs:__imp_WindowsGetStringRawBuffer
0x180018510  xor     ecx, ecx; string
0x180018512  mov     r12, rax
0x180018515  call    cs:__imp_WindowsDeleteString
0x18001851b  xor     ebx, ebx
0x18001851d  lea     rdx, [rbp+57h+length]; length
0x180018521  mov     rcx, rdi; string
0x180018524  mov     [rbp+57h+string], rbx
0x180018528  mov     [rbp+57h+length], ebx
0x18001852b  call    cs:__imp_WindowsGetStringRawBuffer
0x180018531  mov     rcx, rax; String
0x180018534  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; "+"
0x18001853b  call    cs:__imp_wcscspn
0x180018541  mov     ecx, [rbp+57h+length]
0x180018544  mov     rsi, rax
0x180018547  cmp     rax, rcx
0x18001854a  mov     rcx, [rbp+57h+string]; string
0x18001854e  jnb     short loc_18001856E
0x180018550  call    cs:__imp_WindowsDeleteString
0x180018556  mov     r8d, esi; length
0x180018559  mov     [rbp+57h+string], rbx
0x18001855d  lea     r9, [rbp+57h+string]; newString
0x180018561  xor     edx, edx; startIndex
0x180018563  mov     rcx, rdi; string
0x180018566  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x18001856c  jmp     short loc_180018585
0x18001856e  call    cs:__imp_WindowsDeleteString
0x180018574  lea     rdx, [rbp+57h+string]; newString
0x180018578  mov     [rbp+57h+string], rbx
0x18001857c  mov     rcx, rdi; string
0x18001857f  call    cs:__imp_WindowsDuplicateString
0x180018585  mov     esi, eax
0x180018587  test    eax, eax
0x180018589  js      short loc_180018597
0x18001858b  mov     rbx, [rbp+57h+string]
0x18001858f  mov     [rbp+57h+string], 0
0x180018597  xor     ecx, ecx; string
0x180018599  call    cs:__imp_WindowsDeleteString
0x18001859f  mov     rcx, [rbp+57h+string]; string
0x1800185a3  call    cs:__imp_WindowsDeleteString
0x1800185a9  test    esi, esi
0x1800185ab  js      short loc_1800185BB
0x1800185ad  xor     edx, edx; length
0x1800185af  mov     rcx, rbx; string
0x1800185b2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800185b8  mov     r12, rax
0x1800185bb  xor     edi, edi
0x1800185bd  lea     rax, off_18001BA00; "Windows.Launch"
0x1800185c4  xor     cl, cl
0x1800185c6  cmp     edi, 2Eh ; '.'
0x1800185c9  jnb     short loc_180018607
0x1800185cb  or      r9d, 0FFFFFFFFh; cchCount2
0x1800185cf  mov     r15d, edi
0x1800185d2  add     r15, r15
0x1800185d5  mov     [rsp+0C0h+bIgnoreCase], 0; bIgnoreCase
0x1800185dd  or      edx, r9d; cchCount1
0x1800185e0  mov     rcx, r12; lpString1
0x1800185e3  mov     r8, [rax+r15*8]; lpString2
0x1800185e7  call    cs:__imp_CompareStringOrdinal
0x1800185ed  cmp     eax, 2
0x1800185f0  lea     rax, off_18001BA00; "Windows.Launch"
0x1800185f7  jz      short loc_1800185FD
0x1800185f9  inc     edi
0x1800185fb  jmp     short loc_1800185C4
0x1800185fd  mov     eax, [rax+r15*8+8]
0x180018602  mov     cl, 1
0x180018604  mov     [r14], eax
0x180018607  test    cl, cl
0x180018609  jnz     loc_1800186C9
0x18001860f  lea     rax, aWindowsBackgro; "Windows.BackgroundTasks"
0x180018616  xor     edi, edi
0x180018618  mov     [rbp+57h+var_90], rax
0x18001861c  lea     rax, aWindowsPreinst; "Windows.PreInstalledConfigTask"
0x180018623  mov     [rbp+57h+var_88], rax
0x180018627  lea     rax, aWindowsUpdatet; "Windows.UpdateTask"
0x18001862e  mov     [rbp+57h+var_80], rax
0x180018632  lea     rax, aWindowsAppserv; "Windows.AppService"
0x180018639  mov     [rbp+57h+var_78], rax
0x18001863d  lea     rax, aWindowsAppoint; "Windows.AppointmentDataProvider"
0x180018644  mov     [rbp+57h+var_70], rax
0x180018648  lea     rax, aWindowsContact_5; "Windows.ContactDataProvider"
0x18001864f  mov     [rbp+57h+var_68], rax
0x180018653  lea     rax, aWindowsEmailda; "Windows.EmailDataProvider"
0x18001865a  mov     [rbp+57h+var_60], rax
0x18001865e  lea     rax, aWindowsUserdat_0; "Windows.UserDataTaskDataProvider"
0x180018665  mov     [rbp+57h+var_58], rax
0x180018669  lea     rax, aWindowsPrintwo; "Windows.PrintWorkflowBackgroundTask"
0x180018670  mov     [rbp+57h+var_50], rax
0x180018674  lea     rax, aWindowsBarcode_0; "Windows.BarcodeScannerProvider"
0x18001867b  mov     [rbp+57h+var_48], rax
0x18001867f  lea     rax, aWindowsPospaym; "Windows.PosPaymentConnector"
0x180018686  mov     [rbp+57h+var_40], rax
0x18001868a  lea     rax, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x180018691  mov     [rbp+57h+var_38], rax
0x180018695  lea     rax, aWindowsPrintsu; "Windows.PrintSupportWorkflow"
0x18001869c  mov     [rbp+57h+var_30], rax
0x1800186a0  lea     rax, aWindowsPrintsu_0; "Windows.PrintSupportVirtualPrinterWorkf"...
0x1800186a7  mov     [rbp+57h+var_28], rax
0x1800186ab  mov     rdx, [rbp+rdi*8+57h+var_90]
0x1800186b0  mov     rcx, r12
0x1800186b3  call    cs:__imp__o__wcsicmp
0x1800186b9  test    eax, eax
0x1800186bb  jz      short loc_1800186C9
0x1800186bd  inc     edi
0x1800186bf  cmp     edi, 0Eh
0x1800186c2  jb      short loc_1800186AB
0x1800186c4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800186c9  mov     rcx, rbx; string
0x1800186cc  call    cs:__imp_WindowsDeleteString
0x1800186d2  lea     r11, [rsp+0C0h+var_20]
0x1800186da  mov     eax, esi
0x1800186dc  mov     rbx, [r11+30h]
0x1800186e0  mov     rsi, [r11+38h]
0x1800186e4  mov     rsp, r11
0x1800186e7  pop     r15
0x1800186e9  pop     r14
0x1800186eb  pop     r12
0x1800186ed  pop     rdi
0x1800186ee  pop     rbp
0x1800186ef  retn
```
