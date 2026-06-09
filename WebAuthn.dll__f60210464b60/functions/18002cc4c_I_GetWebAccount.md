# I_GetWebAccount

- ea: `0x18002cc4c`
- end: `0x18002cf05`
- name: `I_GetWebAccount`
- size: `697`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c5fc`
- `0x18002c92c`

## callees

- `0x1800205e4`
- `0x18002bbc8`
- `0x18002c444`
- `0x18002cbfc`
- `0x18002cc4c`
- `0x18002cf0c`
- `0x18002cf90`
- `0x18013c090`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ce53`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ce53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cdd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ce62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ceb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cdd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ce62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ceb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002ce36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002ce36`

## string_xrefs

- `0x18002ccac`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18002cd38`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18002ce15`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall I_GetWebAccount(__int64 a1, const WCHAR *a2, const WCHAR *a3, const WCHAR *a4, __int64 a5)
{
  unsigned int v6; // r15d
  int AllTokenBrokerAccounts; // eax
  wil::details::in1diag3 *v8; // rcx
  __int64 v9; // rdx
  unsigned int i; // r14d
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, _QWORD); // rbx
  int v13; // eax
  __int64 v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, PVOID, HSTRING *); // rbx
  HSTRING_HEADER *v21; // rax
  int v22; // eax
  char v23; // al
  const WCHAR *StringRawBuffer; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-61h]
  _BYTE v27[8]; // [rsp+30h] [rbp-51h] BYREF
  HSTRING string; // [rsp+38h] [rbp-49h] BYREF
  __int64 v29; // [rsp+40h] [rbp-41h] BYREF
  __int64 v30; // [rsp+48h] [rbp-39h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64); // [rsp+50h] [rbp-31h] BYREF
  unsigned int v32; // [rsp+58h] [rbp-29h] BYREF
  __int64 v33; // [rsp+60h] [rbp-21h] BYREF
  const WCHAR *v34; // [rsp+68h] [rbp-19h] BYREF
  LPCWCH lpString2; // [rsp+70h] [rbp-11h]
  HSTRING_HEADER v36; // [rsp+78h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  lpString2 = a4;
  v34 = a3;
  v6 = -2146893807;
  v33 = 0;
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v33);
  AllTokenBrokerAccounts = I_GetAllTokenBrokerAccounts(&v33);
  v8 = retaddr;
  if ( AllTokenBrokerAccounts >= 0 )
  {
    v32 = 0;
    AllTokenBrokerAccounts = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 56LL))(v33, &v32);
    v8 = retaddr;
    if ( AllTokenBrokerAccounts < 0 )
    {
      v9 = 441;
      goto LABEL_3;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= v32 )
        goto LABEL_25;
      v31 = 0;
      v30 = 0;
      v29 = 0;
      string = 0;
      v11 = v33;
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v33 + 48LL);
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v31);
      v13 = v12(v11, i, &v31);
      v15 = retaddr;
      if ( v13 < 0 )
        break;
      v27[0] = 0;
      v13 = I_CheckWebAccountProviderDetails((__int64)v31, v14, a2, v27);
      v15 = retaddr;
      if ( v13 < 0 )
      {
        v16 = 456;
        goto LABEL_10;
      }
      if ( v27[0] )
      {
        v13 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
                &v31,
                (__int64)&v30);
        v15 = retaddr;
        if ( v13 < 0 )
        {
          v16 = 463;
          goto LABEL_10;
        }
        v17 = v30;
        v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 56LL);
        _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v29);
        v13 = v18(v17, &v29);
        v15 = retaddr;
        if ( v13 < 0 )
        {
          v16 = 465;
          goto LABEL_10;
        }
        v19 = v29;
        v20 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v29 + 48LL);
        WindowsDeleteString(string);
        string = 0;
        v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v36, &v34);
        v22 = v20(v19, v21[1].Reserved.Reserved1, &string);
        if ( v22 >= 0 )
        {
          v23 = 0;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1D5,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
            (const char *)(unsigned int)v22,
            bIgnoreCase);
          v23 = 1;
        }
        if ( !v23 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          if ( CompareStringOrdinal(StringRawBuffer, -1, lpString2, -1, 1) == 2 )
          {
            (**v31)(v31, &GUID_69473eb2_8031_49be_80bb_96cb46d99aba, a5);
            v6 = 0;
            WindowsDeleteString(string);
            string = 0;
            _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v29);
            _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v30);
            _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v31);
            goto LABEL_25;
          }
        }
      }
LABEL_23:
      WindowsDeleteString(string);
      string = 0;
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v29);
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v30);
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v31);
    }
    v16 = 449;
LABEL_10:
    wil::details::in1diag3::_Log_Hr(
      v15,
      (void *)v16,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
    goto LABEL_23;
  }
  v9 = 438;
LABEL_3:
  wil::details::in1diag3::_Log_Hr(
    v8,
    (void *)v9,
    (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
    (const char *)(unsigned int)AllTokenBrokerAccounts,
    bIgnoreCase);
LABEL_25:
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v33);
  return v6;
}

```

## disassembly

```asm
0x18002cc4c  push    rbp
0x18002cc4e  push    rbx
0x18002cc4f  push    rdi
0x18002cc50  push    r12
0x18002cc52  push    r13
0x18002cc54  push    r14
0x18002cc56  push    r15
0x18002cc58  lea     rbp, [rsp-1Fh]
0x18002cc5d  sub     rsp, 0A0h
0x18002cc64  mov     rax, cs:__security_cookie
0x18002cc6b  xor     rax, rsp
0x18002cc6e  mov     [rbp+4Fh+var_38], rax
0x18002cc72  mov     [rbp+4Fh+lpString2], r9
0x18002cc76  mov     r12, rdx
0x18002cc79  mov     [rbp+4Fh+var_68], r8
0x18002cc7d  mov     r13, [rbp+4Fh+arg_20]
0x18002cc81  xor     ebx, ebx
0x18002cc83  mov     r15d, 80090011h
0x18002cc89  mov     [rbp+4Fh+var_70], rbx
0x18002cc8d  lea     rcx, [rbp+4Fh+var_70]
0x18002cc91  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002cc96  lea     rcx, [rbp+4Fh+var_70]
0x18002cc9a  call    I_GetAllTokenBrokerAccounts
0x18002cc9f  mov     rcx, [rbp+57h]; this
0x18002cca3  test    eax, eax
0x18002cca5  jns     short loc_18002CCC0
0x18002cca7  mov     edx, 1B6h; void *
0x18002ccac  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18002ccb3  mov     r9d, eax; char *
0x18002ccb6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ccbb  jmp     loc_18002CEDA
0x18002ccc0  mov     [rbp+4Fh+var_78], ebx
0x18002ccc3  mov     rcx, [rbp+4Fh+var_70]
0x18002ccc7  mov     rax, [rcx]
0x18002ccca  lea     rdx, [rbp+4Fh+var_78]
0x18002ccce  mov     rax, [rax+38h]
0x18002ccd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccd7  mov     rcx, [rbp+57h]
0x18002ccdb  test    eax, eax
0x18002ccdd  jns     short loc_18002CCE6
0x18002ccdf  mov     edx, 1B9h
0x18002cce4  jmp     short loc_18002CCAC
0x18002cce6  mov     r14d, ebx
0x18002cce9  cmp     r14d, [rbp+4Fh+var_78]
0x18002cced  jnb     loc_18002CEDA
0x18002ccf3  mov     [rbp+4Fh+var_80], rbx
0x18002ccf7  mov     [rbp+4Fh+var_88], rbx
0x18002ccfb  mov     [rbp+4Fh+var_90], rbx
0x18002ccff  mov     [rbp+4Fh+string], rbx
0x18002cd03  mov     rdi, [rbp+4Fh+var_70]
0x18002cd07  mov     rax, [rdi]
0x18002cd0a  mov     rbx, [rax+30h]
0x18002cd0e  lea     rcx, [rbp+4Fh+var_80]
0x18002cd12  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002cd17  lea     r8, [rbp+4Fh+var_80]
0x18002cd1b  mov     edx, r14d
0x18002cd1e  mov     rcx, rdi
0x18002cd21  mov     rax, rbx
0x18002cd24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd29  mov     rcx, [rbp+57h]; this
0x18002cd2d  xor     ebx, ebx
0x18002cd2f  test    eax, eax
0x18002cd31  jns     short loc_18002CD4C
0x18002cd33  mov     edx, 1C1h; void *
0x18002cd38  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18002cd3f  mov     r9d, eax; char *
0x18002cd42  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002cd47  jmp     loc_18002CE5E
0x18002cd4c  mov     [rbp+4Fh+var_A0], bl
0x18002cd4f  lea     r9, [rbp+4Fh+var_A0]
0x18002cd53  mov     r8, r12
0x18002cd56  mov     rcx, [rbp+4Fh+var_80]
0x18002cd5a  call    I_CheckWebAccountProviderDetails
0x18002cd5f  mov     rcx, [rbp+57h]
0x18002cd63  test    eax, eax
0x18002cd65  jns     short loc_18002CD6E
0x18002cd67  mov     edx, 1C8h
0x18002cd6c  jmp     short loc_18002CD38
0x18002cd6e  cmp     [rbp+4Fh+var_A0], bl
0x18002cd71  jz      loc_18002CE5E
0x18002cd77  lea     rdx, [rbp+4Fh+var_88]
0x18002cd7b  lea     rcx, [rbp+4Fh+var_80]
0x18002cd7f  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x18002cd84  mov     rcx, [rbp+57h]
0x18002cd88  test    eax, eax
0x18002cd8a  jns     short loc_18002CD93
0x18002cd8c  mov     edx, 1CFh
0x18002cd91  jmp     short loc_18002CD38
0x18002cd93  mov     rdi, [rbp+4Fh+var_88]
0x18002cd97  mov     rax, [rdi]
0x18002cd9a  mov     rbx, [rax+38h]
0x18002cd9e  lea     rcx, [rbp+4Fh+var_90]
0x18002cda2  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002cda7  lea     rdx, [rbp+4Fh+var_90]
0x18002cdab  mov     rcx, rdi
0x18002cdae  mov     rax, rbx
0x18002cdb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdb6  mov     rcx, [rbp+57h]
0x18002cdba  xor     ebx, ebx
0x18002cdbc  test    eax, eax
0x18002cdbe  jns     short loc_18002CDCA
0x18002cdc0  mov     edx, 1D1h
0x18002cdc5  jmp     loc_18002CD38
0x18002cdca  mov     rdi, [rbp+4Fh+var_90]
0x18002cdce  mov     rax, [rdi]
0x18002cdd1  mov     rbx, [rax+30h]
0x18002cdd5  mov     rcx, [rbp+4Fh+string]; string
0x18002cdd9  call    cs:__imp_WindowsDeleteString
0x18002cddf  mov     [rbp+4Fh+string], 0
0x18002cde7  lea     rdx, [rbp+4Fh+var_68]
0x18002cdeb  lea     rcx, [rbp+4Fh+var_58]
0x18002cdef  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002cdf4  nop
0x18002cdf5  lea     r8, [rbp+4Fh+string]
0x18002cdf9  mov     rdx, [rax+18h]
0x18002cdfd  mov     rcx, rdi
0x18002ce00  mov     rax, rbx
0x18002ce03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce08  mov     rcx, [rbp+57h]; this
0x18002ce0c  xor     ebx, ebx
0x18002ce0e  test    eax, eax
0x18002ce10  jns     short loc_18002CE2A
0x18002ce12  mov     r9d, eax; char *
0x18002ce15  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18002ce1c  mov     edx, 1D5h; void *
0x18002ce21  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ce26  mov     al, 1
0x18002ce28  jmp     short loc_18002CE2C
0x18002ce2a  mov     al, bl
0x18002ce2c  test    al, al
0x18002ce2e  jnz     short loc_18002CE5E
0x18002ce30  xor     edx, edx; length
0x18002ce32  mov     rcx, [rbp+4Fh+string]; string
0x18002ce36  call    cs:__imp_WindowsGetStringRawBuffer
0x18002ce3c  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x18002ce44  or      edi, 0FFFFFFFFh
0x18002ce47  mov     r9d, edi; cchCount2
0x18002ce4a  mov     r8, [rbp+4Fh+lpString2]; lpString2
0x18002ce4e  mov     edx, edi; cchCount1
0x18002ce50  mov     rcx, rax; lpString1
0x18002ce53  call    cs:__imp_CompareStringOrdinal
0x18002ce59  cmp     eax, 2
0x18002ce5c  jz      short loc_18002CE91
0x18002ce5e  mov     rcx, [rbp+4Fh+string]; string
0x18002ce62  call    cs:__imp_WindowsDeleteString
0x18002ce68  mov     [rbp+4Fh+string], rbx
0x18002ce6c  lea     rcx, [rbp+4Fh+var_90]
0x18002ce70  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002ce75  nop
0x18002ce76  lea     rcx, [rbp+4Fh+var_88]
0x18002ce7a  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002ce7f  nop
0x18002ce80  lea     rcx, [rbp+4Fh+var_80]
0x18002ce84  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002ce89  inc     r14d
0x18002ce8c  jmp     loc_18002CCE9
0x18002ce91  mov     rcx, [rbp+4Fh+var_80]
0x18002ce95  mov     rax, [rcx]
0x18002ce98  mov     r8, r13
0x18002ce9b  lea     rdx, _GUID_69473eb2_8031_49be_80bb_96cb46d99aba
0x18002cea2  mov     rax, [rax]
0x18002cea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ceaa  nop
0x18002ceab  mov     r15d, ebx
0x18002ceae  mov     rcx, [rbp+4Fh+string]; string
0x18002ceb2  call    cs:__imp_WindowsDeleteString
0x18002ceb8  mov     [rbp+4Fh+string], rbx
0x18002cebc  lea     rcx, [rbp+4Fh+var_90]
0x18002cec0  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002cec5  nop
0x18002cec6  lea     rcx, [rbp+4Fh+var_88]
0x18002ceca  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002cecf  nop
0x18002ced0  lea     rcx, [rbp+4Fh+var_80]
0x18002ced4  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002ced9  nop
0x18002ceda  lea     rcx, [rbp+4Fh+var_70]
0x18002cede  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002cee3  mov     eax, r15d
0x18002cee6  mov     rcx, [rbp+4Fh+var_38]
0x18002ceea  xor     rcx, rsp; StackCookie
0x18002ceed  call    __security_check_cookie
0x18002cef2  add     rsp, 0A0h
0x18002cef9  pop     r15
0x18002cefb  pop     r14
0x18002cefd  pop     r13
0x18002ceff  pop     r12
0x18002cf01  pop     rdi
0x18002cf02  pop     rbx
0x18002cf03  pop     rbp
0x18002cf04  retn
```
