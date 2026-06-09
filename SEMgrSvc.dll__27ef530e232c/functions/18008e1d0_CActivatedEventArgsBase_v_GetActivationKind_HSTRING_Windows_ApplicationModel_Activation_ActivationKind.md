# CActivatedEventArgsBase::v_GetActivationKind(HSTRING__ *,Windows::ApplicationModel::Activation::ActivationKind *)

- ea: `0x18008e1d0`
- end: `0x18008e3f0`
- name: `?v_GetActivationKind@CActivatedEventArgsBase@@EEAAJPEAUHSTRING__@@PEAW4ActivationKind@Activation@ApplicationModel@Windows@@@Z`
- size: `544`
- prototype: `int(CActivatedEventArgsBase *__hidden this, HSTRING, enum Windows::ApplicationModel::Activation::ActivationKind *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18008b778`
- `0x18008e1d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e3b3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e3b3`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18008e23b`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18008e23b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e215`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e250`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e26e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e299`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e2a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e3cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e215`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e250`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e26e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e299`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e2a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e3cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x18008e266`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x18008e266`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e20a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e22b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e2b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e20a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e22b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e2b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008e27f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008e27f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008e2e7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008e2e7`

## string_xrefs

- `0x18008e30f`: `Windows.BackgroundTasks`
- `0x18008e31c`: `Windows.PreInstalledConfigTask`
- `0x18008e327`: `Windows.UpdateTask`
- `0x18008e332`: `Windows.AppService`
- `0x18008e35e`: `Windows.UserDataTaskDataProvider`
- `0x18008e369`: `Windows.PrintWorkflowBackgroundTask`
- `0x18008e38a`: `Windows.PrintSupportExtension`

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
    if ( CompareStringOrdinal(StringRawBuffer, -1, (&off_1800A1E90)[2 * i], -1, 0) == 2 )
    {
      v13 = 1;
      *(_DWORD *)a3 = *((_DWORD *)&off_1800A1E90 + 4 * i + 2);
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
0x18008e1d0  mov     [rsp-8+arg_0], rbx
0x18008e1d5  mov     [rsp-8+arg_8], rsi
0x18008e1da  push    rbp
0x18008e1db  push    rdi
0x18008e1dc  push    r12
0x18008e1de  push    r14
0x18008e1e0  push    r15
0x18008e1e2  lea     rbp, [rsp-37h]
0x18008e1e7  sub     rsp, 0A0h
0x18008e1ee  mov     r14, r8
0x18008e1f1  mov     rdi, rdx
0x18008e1f4  test    r8, r8
0x18008e1f7  jnz     short loc_18008E1FE
0x18008e1f9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008e1fe  xor     edx, edx; length
0x18008e200  mov     dword ptr [r14], 0
0x18008e207  mov     rcx, rdi; string
0x18008e20a  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e210  xor     ecx, ecx; string
0x18008e212  mov     r12, rax
0x18008e215  call    cs:__imp_WindowsDeleteString
0x18008e21b  xor     ebx, ebx
0x18008e21d  lea     rdx, [rbp+57h+length]; length
0x18008e221  mov     rcx, rdi; string
0x18008e224  mov     [rbp+57h+string], rbx
0x18008e228  mov     [rbp+57h+length], ebx
0x18008e22b  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e231  mov     rcx, rax; String
0x18008e234  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; "+"
0x18008e23b  call    cs:__imp_wcscspn
0x18008e241  mov     ecx, [rbp+57h+length]
0x18008e244  mov     rsi, rax
0x18008e247  cmp     rax, rcx
0x18008e24a  mov     rcx, [rbp+57h+string]; string
0x18008e24e  jnb     short loc_18008E26E
0x18008e250  call    cs:__imp_WindowsDeleteString
0x18008e256  mov     r8d, esi; length
0x18008e259  mov     [rbp+57h+string], rbx
0x18008e25d  lea     r9, [rbp+57h+string]; newString
0x18008e261  xor     edx, edx; startIndex
0x18008e263  mov     rcx, rdi; string
0x18008e266  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x18008e26c  jmp     short loc_18008E285
0x18008e26e  call    cs:__imp_WindowsDeleteString
0x18008e274  lea     rdx, [rbp+57h+string]; newString
0x18008e278  mov     [rbp+57h+string], rbx
0x18008e27c  mov     rcx, rdi; string
0x18008e27f  call    cs:__imp_WindowsDuplicateString
0x18008e285  mov     esi, eax
0x18008e287  test    eax, eax
0x18008e289  js      short loc_18008E297
0x18008e28b  mov     rbx, [rbp+57h+string]
0x18008e28f  mov     [rbp+57h+string], 0
0x18008e297  xor     ecx, ecx; string
0x18008e299  call    cs:__imp_WindowsDeleteString
0x18008e29f  mov     rcx, [rbp+57h+string]; string
0x18008e2a3  call    cs:__imp_WindowsDeleteString
0x18008e2a9  test    esi, esi
0x18008e2ab  js      short loc_18008E2BB
0x18008e2ad  xor     edx, edx; length
0x18008e2af  mov     rcx, rbx; string
0x18008e2b2  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e2b8  mov     r12, rax
0x18008e2bb  xor     edi, edi
0x18008e2bd  lea     rax, off_1800A1E90; "Windows.Launch"
0x18008e2c4  xor     cl, cl
0x18008e2c6  cmp     edi, 2Eh ; '.'
0x18008e2c9  jnb     short loc_18008E307
0x18008e2cb  or      r9d, 0FFFFFFFFh; cchCount2
0x18008e2cf  mov     r15d, edi
0x18008e2d2  add     r15, r15
0x18008e2d5  mov     [rsp+0C0h+bIgnoreCase], 0; bIgnoreCase
0x18008e2dd  or      edx, r9d; cchCount1
0x18008e2e0  mov     rcx, r12; lpString1
0x18008e2e3  mov     r8, [rax+r15*8]; lpString2
0x18008e2e7  call    cs:__imp_CompareStringOrdinal
0x18008e2ed  cmp     eax, 2
0x18008e2f0  lea     rax, off_1800A1E90; "Windows.Launch"
0x18008e2f7  jz      short loc_18008E2FD
0x18008e2f9  inc     edi
0x18008e2fb  jmp     short loc_18008E2C4
0x18008e2fd  mov     eax, [rax+r15*8+8]
0x18008e302  mov     cl, 1
0x18008e304  mov     [r14], eax
0x18008e307  test    cl, cl
0x18008e309  jnz     loc_18008E3C9
0x18008e30f  lea     rax, aWindowsBackgro; "Windows.BackgroundTasks"
0x18008e316  xor     edi, edi
0x18008e318  mov     [rbp+57h+var_90], rax
0x18008e31c  lea     rax, aWindowsPreinst; "Windows.PreInstalledConfigTask"
0x18008e323  mov     [rbp+57h+var_88], rax
0x18008e327  lea     rax, aWindowsUpdatet; "Windows.UpdateTask"
0x18008e32e  mov     [rbp+57h+var_80], rax
0x18008e332  lea     rax, aWindowsAppserv; "Windows.AppService"
0x18008e339  mov     [rbp+57h+var_78], rax
0x18008e33d  lea     rax, aWindowsAppoint; "Windows.AppointmentDataProvider"
0x18008e344  mov     [rbp+57h+var_70], rax
0x18008e348  lea     rax, aWindowsContact_5; "Windows.ContactDataProvider"
0x18008e34f  mov     [rbp+57h+var_68], rax
0x18008e353  lea     rax, aWindowsEmailda; "Windows.EmailDataProvider"
0x18008e35a  mov     [rbp+57h+var_60], rax
0x18008e35e  lea     rax, aWindowsUserdat_0; "Windows.UserDataTaskDataProvider"
0x18008e365  mov     [rbp+57h+var_58], rax
0x18008e369  lea     rax, aWindowsPrintwo; "Windows.PrintWorkflowBackgroundTask"
0x18008e370  mov     [rbp+57h+var_50], rax
0x18008e374  lea     rax, aWindowsBarcode_0; "Windows.BarcodeScannerProvider"
0x18008e37b  mov     [rbp+57h+var_48], rax
0x18008e37f  lea     rax, aWindowsPospaym; "Windows.PosPaymentConnector"
0x18008e386  mov     [rbp+57h+var_40], rax
0x18008e38a  lea     rax, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x18008e391  mov     [rbp+57h+var_38], rax
0x18008e395  lea     rax, aWindowsPrintsu; "Windows.PrintSupportWorkflow"
0x18008e39c  mov     [rbp+57h+var_30], rax
0x18008e3a0  lea     rax, aWindowsPrintsu_0; "Windows.PrintSupportVirtualPrinterWorkf"...
0x18008e3a7  mov     [rbp+57h+var_28], rax
0x18008e3ab  mov     rdx, [rbp+rdi*8+57h+var_90]
0x18008e3b0  mov     rcx, r12
0x18008e3b3  call    cs:__imp__o__wcsicmp
0x18008e3b9  test    eax, eax
0x18008e3bb  jz      short loc_18008E3C9
0x18008e3bd  inc     edi
0x18008e3bf  cmp     edi, 0Eh
0x18008e3c2  jb      short loc_18008E3AB
0x18008e3c4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008e3c9  mov     rcx, rbx; string
0x18008e3cc  call    cs:__imp_WindowsDeleteString
0x18008e3d2  lea     r11, [rsp+0C0h+var_20]
0x18008e3da  mov     eax, esi
0x18008e3dc  mov     rbx, [r11+30h]
0x18008e3e0  mov     rsi, [r11+38h]
0x18008e3e4  mov     rsp, r11
0x18008e3e7  pop     r15
0x18008e3e9  pop     r14
0x18008e3eb  pop     r12
0x18008e3ed  pop     rdi
0x18008e3ee  pop     rbp
0x18008e3ef  retn
```
