# I_CheckWebAccountProviderDetails

- ea: `0x18002cf90`
- end: `0x18002d18e`
- name: `I_CheckWebAccountProviderDetails`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002cc4c`

## callees

- `0x1800205e4`
- `0x18002bbc8`
- `0x18002cf90`
- `0x180031708`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d06f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d132`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d06f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d132`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d01e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d0e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d14e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d16a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d01e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d0e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d14e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d16a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d050`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d117`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d050`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d117`

## string_xrefs

- `0x18002cffb`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18002d07f`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18002d062`: `https://login.microsoft.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall I_CheckWebAccountProviderDetails(__int64 a1, __int64 a2, const WCHAR *a3, _BYTE *a4)
{
  __int64 (__fastcall *v7)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)); // rbx
  int v8; // eax
  wil::details::in1diag3 *v9; // rcx
  __int64 v10; // rdx
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v12)(_QWORD, _QWORD); // rbx
  const WCHAR *StringRawBuffer; // rax
  __int64 v14; // rdx
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v16)(_QWORD, GUID *, _QWORD *); // rdi
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  const WCHAR *v19; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-20h]
  _QWORD v22[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  HSTRING string; // [rsp+70h] [rbp+30h] BYREF
  HSTRING v25; // [rsp+78h] [rbp+38h] BYREF
  __int64 (__fastcall ***v26)(_QWORD, GUID *, _QWORD *); // [rsp+88h] [rbp+48h] BYREF

  v26 = 0;
  string = 0;
  v22[0] = 0;
  v25 = 0;
  *a4 = 0;
  v7 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)))(*(_QWORD *)a1 + 48LL);
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v26);
  v8 = v7(a1, &v26);
  v9 = retaddr;
  if ( v8 >= 0 )
  {
    v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v26;
    v12 = (__int64 (__fastcall *)(_QWORD, _QWORD))(*v26)[6];
    WindowsDeleteString(string);
    string = 0;
    v8 = v12(v11, &string);
    v9 = retaddr;
    if ( v8 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(StringRawBuffer, -1, L"https://login.microsoft.com", -1, 1) == 2 )
      {
        v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v26;
        v16 = **v26;
        _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(v22);
        v8 = v16(v15, &GUID_4a01eb05_4e42_41d4_b518_e008a5163614, v22);
        v9 = retaddr;
        if ( v8 < 0 )
        {
          v10 = 415;
          goto LABEL_3;
        }
        v17 = v22[0];
        v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22[0] + 56LL);
        WindowsDeleteString(v25);
        v25 = 0;
        v8 = v18(v17, &v25);
        v9 = retaddr;
        if ( v8 < 0 )
        {
          v10 = 417;
          goto LABEL_3;
        }
        v19 = WindowsGetStringRawBuffer(v25, 0);
        if ( CompareStringOrdinal(v19, -1, a3, -1, 1) == 2 )
        {
          *a4 = 1;
          goto LABEL_16;
        }
        v14 = 419;
      }
      else
      {
        v14 = 413;
      }
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
        0,
        bIgnoreCase);
      goto LABEL_16;
    }
    v10 = 411;
  }
  else
  {
    v10 = 409;
  }
LABEL_3:
  wil::details::in1diag3::_Log_Hr(
    v9,
    (void *)v10,
    (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
    (const char *)(unsigned int)v8,
    bIgnoreCase);
LABEL_16:
  WindowsDeleteString(v25);
  v25 = 0;
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(v22);
  WindowsDeleteString(string);
  string = 0;
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v26);
  return 0;
}

```

## disassembly

```asm
0x18002cf90  mov     [rsp-28h+arg_8], rdx
0x18002cf95  push    rbp
0x18002cf96  push    rbx
0x18002cf97  push    rsi
0x18002cf98  push    rdi
0x18002cf99  push    r14
0x18002cf9b  mov     rbp, rsp
0x18002cf9e  sub     rsp, 40h
0x18002cfa2  mov     rsi, r9
0x18002cfa5  mov     r14, r8
0x18002cfa8  mov     rdi, rcx
0x18002cfab  mov     [rbp+arg_18], 0
0x18002cfb3  mov     [rbp+string], 0
0x18002cfbb  mov     [rbp+var_10], 0
0x18002cfc3  mov     [rbp+arg_8], 0
0x18002cfcb  mov     byte ptr [r9], 0
0x18002cfcf  mov     rax, [rcx]
0x18002cfd2  mov     rbx, [rax+30h]
0x18002cfd6  lea     rcx, [rbp+arg_18]
0x18002cfda  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002cfdf  lea     rdx, [rbp+arg_18]
0x18002cfe3  mov     rcx, rdi
0x18002cfe6  mov     rax, rbx
0x18002cfe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfee  mov     rcx, [rbp+28h]; this
0x18002cff2  test    eax, eax
0x18002cff4  jns     short loc_18002D00F
0x18002cff6  mov     edx, 199h; void *
0x18002cffb  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18002d002  mov     r9d, eax; char *
0x18002d005  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d00a  jmp     loc_18002D14A
0x18002d00f  mov     rdi, [rbp+arg_18]
0x18002d013  mov     rax, [rdi]
0x18002d016  mov     rbx, [rax+30h]
0x18002d01a  mov     rcx, [rbp+string]; string
0x18002d01e  call    cs:__imp_WindowsDeleteString
0x18002d024  mov     [rbp+string], 0
0x18002d02c  lea     rdx, [rbp+string]
0x18002d030  mov     rcx, rdi
0x18002d033  mov     rax, rbx
0x18002d036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d03b  mov     rcx, [rbp+28h]
0x18002d03f  test    eax, eax
0x18002d041  jns     short loc_18002D04A
0x18002d043  mov     edx, 19Bh
0x18002d048  jmp     short loc_18002CFFB
0x18002d04a  xor     edx, edx; length
0x18002d04c  mov     rcx, [rbp+string]; string
0x18002d050  call    cs:__imp_WindowsGetStringRawBuffer
0x18002d056  mov     [rsp+40h+bIgnoreCase], 1; int
0x18002d05e  or      r9d, 0FFFFFFFFh; cchCount2
0x18002d062  lea     r8, aHttpsLoginMicr; "https://login.microsoft.com"
0x18002d069  or      edx, r9d; cchCount1
0x18002d06c  mov     rcx, rax; lpString1
0x18002d06f  call    cs:__imp_CompareStringOrdinal
0x18002d075  cmp     eax, 2
0x18002d078  jz      short loc_18002D097
0x18002d07a  mov     edx, 19Dh; void *
0x18002d07f  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18002d086  xor     r9d, r9d; char *
0x18002d089  mov     rcx, [rbp+28h]; this
0x18002d08d  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18002d092  jmp     loc_18002D14A
0x18002d097  mov     rbx, [rbp+arg_18]
0x18002d09b  mov     rax, [rbx]
0x18002d09e  mov     rdi, [rax]
0x18002d0a1  lea     rcx, [rbp+var_10]
0x18002d0a5  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002d0aa  lea     r8, [rbp+var_10]
0x18002d0ae  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x18002d0b5  mov     rcx, rbx
0x18002d0b8  mov     rax, rdi
0x18002d0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0c0  nop
0x18002d0c1  mov     rcx, [rbp+28h]
0x18002d0c5  test    eax, eax
0x18002d0c7  jns     short loc_18002D0D3
0x18002d0c9  mov     edx, 19Fh
0x18002d0ce  jmp     loc_18002CFFB
0x18002d0d3  mov     rdi, [rbp+var_10]
0x18002d0d7  mov     rax, [rdi]
0x18002d0da  mov     rbx, [rax+38h]
0x18002d0de  mov     rcx, [rbp+arg_8]; string
0x18002d0e2  call    cs:__imp_WindowsDeleteString
0x18002d0e8  mov     [rbp+arg_8], 0
0x18002d0f0  lea     rdx, [rbp+arg_8]
0x18002d0f4  mov     rcx, rdi
0x18002d0f7  mov     rax, rbx
0x18002d0fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0ff  mov     rcx, [rbp+28h]
0x18002d103  test    eax, eax
0x18002d105  jns     short loc_18002D111
0x18002d107  mov     edx, 1A1h
0x18002d10c  jmp     loc_18002CFFB
0x18002d111  xor     edx, edx; length
0x18002d113  mov     rcx, [rbp+arg_8]; string
0x18002d117  call    cs:__imp_WindowsGetStringRawBuffer
0x18002d11d  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x18002d125  or      r9d, 0FFFFFFFFh; cchCount2
0x18002d129  mov     r8, r14; lpString2
0x18002d12c  or      edx, r9d; cchCount1
0x18002d12f  mov     rcx, rax; lpString1
0x18002d132  call    cs:__imp_CompareStringOrdinal
0x18002d138  cmp     eax, 2
0x18002d13b  jz      short loc_18002D147
0x18002d13d  mov     edx, 1A3h
0x18002d142  jmp     loc_18002D07F
0x18002d147  mov     byte ptr [rsi], 1
0x18002d14a  mov     rcx, [rbp+arg_8]; string
0x18002d14e  call    cs:__imp_WindowsDeleteString
0x18002d154  mov     [rbp+arg_8], 0
0x18002d15c  lea     rcx, [rbp+var_10]
0x18002d160  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002d165  nop
0x18002d166  mov     rcx, [rbp+string]; string
0x18002d16a  call    cs:__imp_WindowsDeleteString
0x18002d170  mov     [rbp+string], 0
0x18002d178  lea     rcx, [rbp+arg_18]
0x18002d17c  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002d181  xor     eax, eax
0x18002d183  add     rsp, 40h
0x18002d187  pop     r14
0x18002d189  pop     rdi
0x18002d18a  pop     rsi
0x18002d18b  pop     rbx
0x18002d18c  pop     rbp
0x18002d18d  retn
```
