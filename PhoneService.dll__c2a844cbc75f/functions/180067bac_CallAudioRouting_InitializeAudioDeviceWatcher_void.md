# CallAudioRouting::_InitializeAudioDeviceWatcher(void)

- ea: `0x180067bac`
- end: `0x180068001`
- name: `?_InitializeAudioDeviceWatcher@CallAudioRouting@@AEAAJXZ`
- size: `1109`
- prototype: `__int64 __fastcall(CallAudioRouting *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x18005f1a0`

## callees

- `0x180003db0`
- `0x1800056a0`
- `0x180006e94`
- `0x18001d890`
- `0x18005f9c0`
- `0x180067bac`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067c1d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067d8a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067ef2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067c1d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067d8a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067ef2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180067c4b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180067db8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180067c4b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180067db8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067e2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067e3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067e2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067e3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067ca6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067ce7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067d04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067d45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067fae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067fbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067ca6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067ce7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067d04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067d45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067fae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067fbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180067bfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180067d74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180067f07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180067bfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180067d74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180067f07`

## string_xrefs

- `0x180067c64`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180067cd2`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180067d30`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180067dd1`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180067e6a`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_InitializeAudioDeviceWatcher(CallAudioRouting *this)
{
  int ActivationFactory; // eax
  BackTraceCollection *v3; // rcx
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  BackTraceCollection *v10; // rcx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  BackTraceCollection *v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  BackTraceCollection *v17; // rcx
  __int64 v18; // rcx
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v20; // rax
  int v21; // eax
  BackTraceCollection *v22; // rcx
  __int64 v23; // r9
  _QWORD *v24; // rdi
  __int64 v25; // rcx
  __int64 v26; // r14
  unsigned __int64 v27; // rbx
  const WCHAR *v28; // rsi
  __int64 (__fastcall *v29)(__int64, HSTRING, _QWORD *); // r15
  int v30; // eax
  BackTraceCollection *v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rcx
  __int64 v35; // rcx
  const unsigned __int16 *v36; // [rsp+30h] [rbp-A9h] BYREF
  const char *v37; // [rsp+38h] [rbp-A1h] BYREF
  HSTRING v38; // [rsp+40h] [rbp-99h] BYREF
  HSTRING_HEADER v39; // [rsp+48h] [rbp-91h] BYREF
  __int64 v40; // [rsp+60h] [rbp-79h] BYREF
  HSTRING string; // [rsp+68h] [rbp-71h] BYREF
  HSTRING v42; // [rsp+70h] [rbp-69h] BYREF
  __int64 v43; // [rsp+78h] [rbp-61h] BYREF
  void *Block[2]; // [rsp+80h] [rbp-59h] BYREF
  __int16 v45; // [rsp+90h] [rbp-49h] BYREF
  __int64 v46; // [rsp+92h] [rbp-47h]
  int v47; // [rsp+9Ah] [rbp-3Fh]
  __int16 v48; // [rsp+9Eh] [rbp-3Bh]
  HSTRING hstringHeader[4]; // [rsp+A0h] [rbp-39h] BYREF
  HSTRING v50[4]; // [rsp+C0h] [rbp-19h] BYREF

  v40 = 0;
  memset(hstringHeader, 0, sizeof(hstringHeader));
  if ( WindowsCreateStringReference(
         L"Windows.Media.Devices.MediaDevice",
         0x21u,
         (HSTRING_HEADER *)&hstringHeader[1],
         hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(hstringHeader[0], &GUID_aa2d9a40_909f_4bba_bf8b_0c0d296f14f0, &v40);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    BackTraceCollection::Capture(v3, ActivationFactory);
    Log_HREvent_17(v4, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 306);
LABEL_5:
    v5 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    return v4;
  }
  v7 = v40;
  string = 0;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v9 = v8(v7, &string);
  v4 = v9;
  if ( v9 < 0 )
  {
    BackTraceCollection::Capture(v10, v9);
    Log_HREvent_17(v4, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 309);
LABEL_10:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_5;
  }
  v11 = v40;
  v42 = 0;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 56LL);
  WindowsDeleteString(0);
  v42 = 0;
  v13 = v12(v11, &v42);
  v4 = v13;
  if ( v13 < 0 )
  {
    BackTraceCollection::Capture(v14, v13);
    Log_HREvent_17(v4, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 312);
LABEL_13:
    WindowsDeleteString(v42);
    v42 = 0;
    goto LABEL_10;
  }
  v43 = 0;
  memset(v50, 0, sizeof(v50));
  if ( WindowsCreateStringReference(
         L"Windows.Devices.Enumeration.DeviceInformation",
         0x2Du,
         (HSTRING_HEADER *)&v50[1],
         v50) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v15 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v16 = RoGetActivationFactory(v50[0], &GUID_c17f100e_3a46_4a78_8013_769dc9b97390, &v43);
  v4 = v16;
  if ( v16 < 0 )
  {
    BackTraceCollection::Capture(v17, v16);
    Log_HREvent_17(v4, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 317);
LABEL_20:
    v18 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    goto LABEL_13;
  }
  Block[0] = &v45;
  v46 = 0;
  Block[1] = &v45;
  v47 = 0;
  v48 = 0;
  v45 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v20 = WindowsGetStringRawBuffer(v42, 0);
  v21 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
          Block,
          L"(%s) OR (%s)",
          v20,
          StringRawBuffer);
  v4 = v21;
  if ( v21 < 0 )
  {
    BackTraceCollection::Capture(v22, v21);
    v23 = 325;
    goto LABEL_24;
  }
  v24 = (_QWORD *)((char *)this + 312);
  v25 = *((_QWORD *)this + 39);
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    *v24 = 0;
  }
  v26 = v43;
  v27 = -1;
  v28 = (const WCHAR *)Block[0];
  v29 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD *))(*(_QWORD *)v43 + 112LL);
  do
    ++v27;
  while ( *((_WORD *)Block[0] + v27) );
  if ( v27 > 0xFFFFFFFF )
  {
    LODWORD(v27) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v28, v27, &v39, &v38);
  v30 = v29(v26, v38, v24);
  v4 = v30;
  if ( v30 < 0 )
  {
    BackTraceCollection::Capture(v31, v30);
    v23 = 329;
LABEL_24:
    Log_HREvent_17(v4, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v23);
    if ( Block[0] != &v45 )
      operator delete(Block[0]);
    goto LABEL_20;
  }
  if ( (unsigned int)dword_1800B3200 > 4 )
  {
    v36 = (const unsigned __int16 *)Block[0];
    v37 = "CallAudioRouting::_InitializeBluetoothDeviceWatcher";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      (__int64)v31,
      (int)word_1800AA2A2,
      v32,
      v33,
      (const unsigned __int16 **)&v37,
      &v36);
  }
  if ( Block[0] != &v45 )
    operator delete(Block[0]);
  v34 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  WindowsDeleteString(v42);
  v42 = 0;
  WindowsDeleteString(string);
  v35 = v40;
  string = 0;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  return 0;
}

```

## disassembly

```asm
0x180067bac  push    rbp
0x180067bae  push    rbx
0x180067baf  push    rsi
0x180067bb0  push    rdi
0x180067bb1  push    r12
0x180067bb3  push    r13
0x180067bb5  push    r14
0x180067bb7  push    r15
0x180067bb9  lea     rbp, [rsp-1Fh]
0x180067bbe  sub     rsp, 0F8h
0x180067bc5  mov     rax, cs:__security_cookie
0x180067bcc  xor     rax, rsp
0x180067bcf  mov     [rbp+57h+var_50], rax
0x180067bd3  xorps   xmm0, xmm0
0x180067bd6  lea     r9, [rbp+57h+hstringHeader]; string
0x180067bda  xor     r12d, r12d
0x180067bdd  lea     r8, [rbp+57h+hstringHeader+8]; hstringHeader
0x180067be1  mov     rsi, rcx
0x180067be4  mov     [rbp+57h+var_D0], r12
0x180067be8  lea     rcx, ?RuntimeClass_Windows_Media_Devices_MediaDevice@@3QBGB; "Windows.Media.Devices.MediaDevice"
0x180067bef  movups  xmmword ptr [rbp+57h+hstringHeader], xmm0
0x180067bf3  lea     edx, [r12+21h]; length
0x180067bf8  movups  xmmword ptr [rbp+57h+hstringHeader+10h], xmm0
0x180067bfc  call    cs:__imp_WindowsCreateStringReference
0x180067c02  lea     r13d, [r12+1]
0x180067c07  mov     r14d, 0C000000Dh
0x180067c0d  test    eax, eax
0x180067c0f  jns     short loc_180067C23
0x180067c11  xor     r9d, r9d; lpArguments
0x180067c14  xor     r8d, r8d; nNumberOfArguments
0x180067c17  mov     edx, r13d; dwExceptionFlags
0x180067c1a  mov     ecx, r14d; dwExceptionCode
0x180067c1d  call    cs:__imp_RaiseException
0x180067c23  mov     rcx, [rbp+57h+var_D0]
0x180067c27  test    rcx, rcx
0x180067c2a  jz      short loc_180067C3C
0x180067c2c  mov     [rbp+57h+var_D0], r12
0x180067c30  mov     rax, [rcx]
0x180067c33  mov     rax, [rax+10h]
0x180067c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c3c  mov     rcx, qword ptr [rbp+57h+hstringHeader]
0x180067c40  lea     r8, [rbp+57h+var_D0]
0x180067c44  lea     rdx, _GUID_aa2d9a40_909f_4bba_bf8b_0c0d296f14f0
0x180067c4b  call    cs:__imp_RoGetActivationFactory
0x180067c51  mov     ebx, eax
0x180067c53  test    eax, eax
0x180067c55  jns     short loc_180067C95
0x180067c57  mov     edx, eax; int
0x180067c59  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180067c5e  mov     r9d, 132h
0x180067c64  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180067c6b  mov     edx, r13d
0x180067c6e  mov     ecx, ebx
0x180067c70  call    Log_HREvent_17
0x180067c75  mov     rcx, [rbp+57h+var_D0]
0x180067c79  test    rcx, rcx
0x180067c7c  jz      short loc_180067C8E
0x180067c7e  mov     [rbp+57h+var_D0], r12
0x180067c82  mov     rax, [rcx]
0x180067c85  mov     rax, [rax+10h]
0x180067c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c8e  mov     eax, ebx
0x180067c90  jmp     loc_180067FE1
0x180067c95  mov     rdi, [rbp+57h+var_D0]
0x180067c99  xor     ecx, ecx; string
0x180067c9b  mov     [rbp+57h+string], r12
0x180067c9f  mov     rax, [rdi]
0x180067ca2  mov     rbx, [rax+30h]
0x180067ca6  call    cs:__imp_WindowsDeleteString
0x180067cac  lea     rdx, [rbp+57h+string]
0x180067cb0  mov     [rbp+57h+string], r12
0x180067cb4  mov     rcx, rdi
0x180067cb7  mov     rax, rbx
0x180067cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067cbf  mov     ebx, eax
0x180067cc1  test    eax, eax
0x180067cc3  jns     short loc_180067CF3
0x180067cc5  mov     edx, eax; int
0x180067cc7  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180067ccc  mov     r9d, 135h
0x180067cd2  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180067cd9  mov     edx, r13d
0x180067cdc  mov     ecx, ebx
0x180067cde  call    Log_HREvent_17
0x180067ce3  mov     rcx, [rbp+57h+string]; string
0x180067ce7  call    cs:__imp_WindowsDeleteString
0x180067ced  mov     [rbp+57h+string], r12
0x180067cf1  jmp     short loc_180067C75
0x180067cf3  mov     rdi, [rbp+57h+var_D0]
0x180067cf7  xor     ecx, ecx; string
0x180067cf9  mov     [rbp+57h+var_C0], r12
0x180067cfd  mov     rax, [rdi]
0x180067d00  mov     rbx, [rax+38h]
0x180067d04  call    cs:__imp_WindowsDeleteString
0x180067d0a  lea     rdx, [rbp+57h+var_C0]
0x180067d0e  mov     [rbp+57h+var_C0], r12
0x180067d12  mov     rcx, rdi
0x180067d15  mov     rax, rbx
0x180067d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d1d  mov     ebx, eax
0x180067d1f  test    eax, eax
0x180067d21  jns     short loc_180067D51
0x180067d23  mov     edx, eax; int
0x180067d25  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180067d2a  mov     r9d, 138h
0x180067d30  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180067d37  mov     edx, r13d
0x180067d3a  mov     ecx, ebx
0x180067d3c  call    Log_HREvent_17
0x180067d41  mov     rcx, [rbp+57h+var_C0]; string
0x180067d45  call    cs:__imp_WindowsDeleteString
0x180067d4b  mov     [rbp+57h+var_C0], r12
0x180067d4f  jmp     short loc_180067CE3
0x180067d51  xorps   xmm0, xmm0
0x180067d54  mov     [rbp+57h+var_B8], r12
0x180067d58  lea     r9, [rbp+57h+var_70]; string
0x180067d5c  mov     edx, 2Dh ; '-'; length
0x180067d61  lea     r8, [rbp+57h+var_70+8]; hstringHeader
0x180067d65  lea     rcx, ?RuntimeClass_Windows_Devices_Enumeration_DeviceInformation@@3QBGB; "Windows.Devices.Enumeration.DeviceInfor"...
0x180067d6c  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180067d70  movups  xmmword ptr [rbp+57h+var_70+10h], xmm0
0x180067d74  call    cs:__imp_WindowsCreateStringReference
0x180067d7a  test    eax, eax
0x180067d7c  jns     short loc_180067D90
0x180067d7e  xor     r9d, r9d; lpArguments
0x180067d81  xor     r8d, r8d; nNumberOfArguments
0x180067d84  mov     edx, r13d; dwExceptionFlags
0x180067d87  mov     ecx, r14d; dwExceptionCode
0x180067d8a  call    cs:__imp_RaiseException
0x180067d90  mov     rcx, [rbp+57h+var_B8]
0x180067d94  test    rcx, rcx
0x180067d97  jz      short loc_180067DA9
0x180067d99  mov     [rbp+57h+var_B8], r12
0x180067d9d  mov     rax, [rcx]
0x180067da0  mov     rax, [rax+10h]
0x180067da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067da9  mov     rcx, qword ptr [rbp+57h+var_70]
0x180067dad  lea     r8, [rbp+57h+var_B8]
0x180067db1  lea     rdx, _GUID_c17f100e_3a46_4a78_8013_769dc9b97390
0x180067db8  call    cs:__imp_RoGetActivationFactory
0x180067dbe  mov     ebx, eax
0x180067dc0  test    eax, eax
0x180067dc2  jns     short loc_180067E04
0x180067dc4  mov     edx, eax; int
0x180067dc6  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180067dcb  mov     r9d, 13Dh
0x180067dd1  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180067dd8  mov     edx, r13d
0x180067ddb  mov     ecx, ebx
0x180067ddd  call    Log_HREvent_17
0x180067de2  mov     rcx, [rbp+57h+var_B8]
0x180067de6  test    rcx, rcx
0x180067de9  jz      loc_180067D41
0x180067def  mov     [rbp+57h+var_B8], r12
0x180067df3  mov     rax, [rcx]
0x180067df6  mov     rax, [rax+10h]
0x180067dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067dff  jmp     loc_180067D41
0x180067e04  mov     rcx, [rbp+57h+string]; string
0x180067e08  lea     rax, [rbp+57h+var_A0]
0x180067e0c  mov     [rbp+57h+Block], rax
0x180067e10  xor     edx, edx; length
0x180067e12  lea     rax, [rbp+57h+var_A0]
0x180067e16  mov     [rbp+57h+var_9E], r12
0x180067e1a  mov     [rbp+57h+var_A8], rax
0x180067e1e  mov     [rbp+57h+var_96], r12d
0x180067e22  mov     [rbp+57h+var_92], r12w
0x180067e27  mov     [rbp+57h+var_A0], r12w
0x180067e2c  call    cs:__imp_WindowsGetStringRawBuffer
0x180067e32  mov     rcx, [rbp+57h+var_C0]; string
0x180067e36  xor     edx, edx; length
0x180067e38  mov     rbx, rax
0x180067e3b  call    cs:__imp_WindowsGetStringRawBuffer
0x180067e41  mov     r9, rbx
0x180067e44  lea     rdx, aSOrS; "(%s) OR (%s)"
0x180067e4b  mov     r8, rax
0x180067e4e  lea     rcx, [rbp+57h+Block]
0x180067e52  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180067e57  mov     ebx, eax
0x180067e59  test    eax, eax
0x180067e5b  jns     short loc_180067E9D
0x180067e5d  mov     edx, eax; int
0x180067e5f  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180067e64  mov     r9d, 145h
0x180067e6a  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180067e71  mov     edx, r13d
0x180067e74  mov     ecx, ebx
0x180067e76  call    Log_HREvent_17
0x180067e7b  mov     rcx, [rbp+57h+Block]; Block
0x180067e7f  lea     rax, [rbp+57h+var_A0]
0x180067e83  cmp     rcx, rax
0x180067e86  jz      loc_180067DE2
0x180067e8c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180067e93  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180067e98  jmp     loc_180067DE2
0x180067e9d  lea     rdi, [rsi+138h]
0x180067ea4  mov     rcx, [rdi]
0x180067ea7  test    rcx, rcx
0x180067eaa  jz      short loc_180067EBB
0x180067eac  mov     rax, [rcx]
0x180067eaf  mov     rax, [rax+10h]
0x180067eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067eb8  mov     [rdi], r12
0x180067ebb  mov     r14, [rbp+57h+var_B8]
0x180067ebf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180067ec3  mov     rsi, [rbp+57h+Block]
0x180067ec7  mov     rax, [r14]
0x180067eca  mov     r15, [rax+70h]
0x180067ece  inc     rbx
0x180067ed1  cmp     [rsi+rbx*2], r12w
0x180067ed6  jnz     short loc_180067ECE
0x180067ed8  mov     eax, 0FFFFFFFFh
0x180067edd  cmp     rbx, rax
0x180067ee0  jbe     short loc_180067EF8
0x180067ee2  xor     r9d, r9d; lpArguments
0x180067ee5  xor     r8d, r8d; nNumberOfArguments
0x180067ee8  mov     edx, r13d; dwExceptionFlags
0x180067eeb  mov     ecx, 0C000000Dh; dwExceptionCode
0x180067ef0  mov     ebx, eax
0x180067ef2  call    cs:__imp_RaiseException
0x180067ef8  lea     r9, [rsp+130h+var_F0]; string
0x180067efd  mov     edx, ebx; length
0x180067eff  lea     r8, [rsp+130h+var_E8]; hstringHeader
0x180067f04  mov     rcx, rsi; sourceString
0x180067f07  call    cs:__imp_WindowsCreateStringReference
0x180067f0d  mov     rdx, [rsp+130h+var_F0]
0x180067f12  mov     r8, rdi
0x180067f15  mov     rcx, r14
0x180067f18  mov     rax, r15
0x180067f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f20  mov     ebx, eax
0x180067f22  test    eax, eax
0x180067f24  jns     short loc_180067F38
0x180067f26  mov     edx, eax; int
0x180067f28  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180067f2d  mov     r9d, 149h
0x180067f33  jmp     loc_180067E6A
0x180067f38  mov     eax, cs:dword_1800B3200
0x180067f3e  cmp     eax, 4
0x180067f41  jbe     short loc_180067F78
0x180067f43  mov     rax, [rbp+57h+Block]
0x180067f47  lea     rdx, word_1800AA2A2
0x180067f4e  mov     [rsp+130h+var_100], rax
0x180067f53  lea     rax, aCallaudiorouti_17; "CallAudioRouting::_InitializeBluetoothD"...
0x180067f5a  mov     [rsp+130h+var_F8], rax
0x180067f5f  lea     rax, [rsp+130h+var_100]
0x180067f64  mov     [rsp+130h+var_108], rax
0x180067f69  lea     rax, [rsp+130h+var_F8]
0x180067f6e  mov     [rsp+130h+var_110], rax
0x180067f73  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180067f78  mov     rcx, [rbp+57h+Block]; Block
0x180067f7c  lea     rax, [rbp+57h+var_A0]
0x180067f80  cmp     rcx, rax
0x180067f83  jz      short loc_180067F91
0x180067f85  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180067f8c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180067f91  mov     rcx, [rbp+57h+var_B8]
0x180067f95  test    rcx, rcx
0x180067f98  jz      short loc_180067FAA
0x180067f9a  mov     [rbp+57h+var_B8], r12
0x180067f9e  mov     rax, [rcx]
0x180067fa1  mov     rax, [rax+10h]
0x180067fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067faa  mov     rcx, [rbp+57h+var_C0]; string
0x180067fae  call    cs:__imp_WindowsDeleteString
0x180067fb4  mov     rcx, [rbp+57h+string]; string
0x180067fb8  mov     [rbp+57h+var_C0], r12
0x180067fbc  call    cs:__imp_WindowsDeleteString
0x180067fc2  mov     rcx, [rbp+57h+var_D0]
0x180067fc6  mov     [rbp+57h+string], r12
0x180067fca  test    rcx, rcx
0x180067fcd  jz      short loc_180067FDF
0x180067fcf  mov     [rbp+57h+var_D0], r12
0x180067fd3  mov     rax, [rcx]
0x180067fd6  mov     rax, [rax+10h]
0x180067fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067fdf  xor     eax, eax
0x180067fe1  mov     rcx, [rbp+57h+var_50]
0x180067fe5  xor     rcx, rsp; StackCookie
0x180067fe8  call    __security_check_cookie
0x180067fed  add     rsp, 0F8h
0x180067ff4  pop     r15
0x180067ff6  pop     r14
0x180067ff8  pop     r13
0x180067ffa  pop     r12
0x180067ffc  pop     rdi
0x180067ffd  pop     rsi
0x180067ffe  pop     rbx
0x180067fff  pop     rbp
0x180068000  retn
```
