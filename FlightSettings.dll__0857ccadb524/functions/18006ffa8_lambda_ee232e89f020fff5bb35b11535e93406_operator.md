# _lambda_ee232e89f020fff5bb35b11535e93406_::operator()

- ea: `0x18006ffa8`
- end: `0x18007016b`
- name: `_lambda_ee232e89f020fff5bb35b11535e93406_::operator()`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006f4ac`

## callees

- `0x18000b19c`
- `0x18000cc8c`
- `0x180013da0`
- `0x1800177bc`
- `0x18006ffa8`
- `0x1800716c4`
- `0x1800719c4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ffcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070156`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ffcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070156`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180070094`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180070126`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180070094`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180070126`

## string_xrefs

- `0x180070001`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerclass.cpp`
- `0x180070063`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerclass.cpp`
- `0x1800700f6`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerclass.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall lambda_ee232e89f020fff5bb35b11535e93406_::operator()(__int64 a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rdi
  int *v5; // rbx
  int *v6; // rsi
  int v7; // ebx
  __int64 (__fastcall *v8)(__int64, struct Windows::Data::Json::IJsonValue **); // rdi
  int *v9; // rbx
  Windows::Management::Update::PreviewBuildsState *v10; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int PropertyValueFromJsonValue; // eax
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rdi
  unsigned __int64 v16; // rdx
  unsigned __int8 v17; // cl
  __int64 v18; // rcx
  FlightSettingsAPITelemetryClass *v19; // rax
  int v21; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  char v23; // [rsp+90h] [rbp+38h] BYREF
  HSTRING string; // [rsp+98h] [rbp+40h] BYREF
  struct Windows::Data::Json::IJsonValue *v25; // [rsp+A0h] [rbp+48h] BYREF
  struct Windows::Foundation::IPropertyValue *v26; // [rsp+A8h] [rbp+50h] BYREF

  string = 0;
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = *(int **)a1;
  *v5 = v4(a2, &string);
  v6 = *(int **)a1;
  v7 = **(_DWORD **)a1;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previewbuildsmanagerclass.cpp",
      (const char *)(unsigned int)v7,
      v21);
    goto LABEL_14;
  }
  v25 = 0;
  v8 = *(__int64 (__fastcall **)(__int64, struct Windows::Data::Json::IJsonValue **))(*(_QWORD *)a2 + 56LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  v9 = *(int **)a1;
  *v9 = v8(a2, &v25);
  v7 = **(_DWORD **)a1;
  if ( v7 >= 0 )
  {
    v26 = 0;
    v10 = *(Windows::Management::Update::PreviewBuildsState **)(a1 + 8);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    PropertyValueFromJsonValue = Windows::Management::Update::PreviewBuildsState::GetPropertyValueFromJsonValue(
                                   v10,
                                   v25,
                                   StringRawBuffer,
                                   &v26);
    v7 = PropertyValueFromJsonValue;
    if ( PropertyValueFromJsonValue >= 0 )
    {
      v23 = 0;
      **(_DWORD **)a1 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Foundation::IPropertyValue *, char *))(***(_QWORD ***)(a1 + 16) + 80LL))(
                          **(_QWORD **)(a1 + 16),
                          string,
                          v26,
                          &v23);
      v7 = **(_DWORD **)a1;
      if ( v7 >= 0 )
      {
LABEL_10:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
        goto LABEL_11;
      }
      v13 = (unsigned int)v7;
      v14 = 184;
    }
    else
    {
      v13 = (unsigned int)PropertyValueFromJsonValue;
      v14 = 180;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previewbuildsmanagerclass.cpp",
      (const char *)v13,
      v21);
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB1,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previewbuildsmanagerclass.cpp",
    (const char *)(unsigned int)v7,
    v21);
LABEL_11:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  if ( *v6 < 0 )
  {
    v15 = WindowsGetStringRawBuffer(string, 0);
    if ( FlightSettingsAPITelemetryClass::IsEnabled(v17, v16) )
    {
      v19 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                 v18,
                                                 _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
      FlightSettingsAPITelemetryClass::GetPropertyValueFromJsonValueFailed_(v19, *v6, v15);
    }
  }
LABEL_14:
  WindowsDeleteString(string);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006ffa8  push    rbp
0x18006ffaa  push    rbx
0x18006ffab  push    rsi
0x18006ffac  push    rdi
0x18006ffad  push    r14
0x18006ffaf  push    r15
0x18006ffb1  mov     rbp, rsp
0x18006ffb4  sub     rsp, 58h
0x18006ffb8  mov     r15, rdx
0x18006ffbb  mov     r14, rcx
0x18006ffbe  mov     [rbp+string], 0
0x18006ffc6  mov     rax, [rdx]
0x18006ffc9  mov     rdi, [rax+30h]
0x18006ffcd  xor     ecx, ecx; string
0x18006ffcf  call    cs:__imp_WindowsDeleteString
0x18006ffd5  mov     [rbp+string], 0
0x18006ffdd  mov     rbx, [r14]
0x18006ffe0  lea     rdx, [rbp+string]
0x18006ffe4  mov     rcx, r15
0x18006ffe7  mov     rax, rdi
0x18006ffea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ffef  mov     [rbx], eax
0x18006fff1  mov     rsi, [r14]
0x18006fff4  mov     ebx, [rsi]
0x18006fff6  test    ebx, ebx
0x18006fff8  jns     short loc_180070017
0x18006fffa  mov     rcx, [rbp+30h]; this
0x18006fffe  mov     r9d, ebx; char *
0x180070001  lea     r8, aOnecoreBaseFli_92; "onecore\\base\\flighting\\flightsetting"...
0x180070008  mov     edx, 0ABh; void *
0x18007000d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070012  jmp     loc_180070152
0x180070017  mov     [rbp+var_28], rsi
0x18007001b  lea     rax, [rbp+string]
0x18007001f  mov     [rbp+var_20], rax
0x180070023  mov     [rbp+var_18], 1
0x180070027  mov     [rbp+arg_10], 0
0x18007002f  mov     rax, [r15]
0x180070032  mov     rdi, [rax+38h]
0x180070036  lea     rcx, [rbp+arg_10]
0x18007003a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007003f  mov     rbx, [r14]
0x180070042  lea     rdx, [rbp+arg_10]
0x180070046  mov     rcx, r15
0x180070049  mov     rax, rdi
0x18007004c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070051  mov     [rbx], eax
0x180070053  mov     rax, [r14]
0x180070056  mov     ebx, [rax]
0x180070058  test    ebx, ebx
0x18007005a  jns     short loc_180070079
0x18007005c  mov     rcx, [rbp+30h]; this
0x180070060  mov     r9d, ebx; char *
0x180070063  lea     r8, aOnecoreBaseFli_92; "onecore\\base\\flighting\\flightsetting"...
0x18007006a  mov     edx, 0B1h; void *
0x18007006f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070074  jmp     loc_180070111
0x180070079  mov     [rbp+arg_18], 0
0x180070081  mov     rbx, [r14+8]
0x180070085  lea     rcx, [rbp+arg_18]
0x180070089  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007008e  xor     edx, edx; length
0x180070090  mov     rcx, [rbp+string]; string
0x180070094  call    cs:__imp_WindowsGetStringRawBuffer
0x18007009a  lea     r9, [rbp+arg_18]; struct Windows::Foundation::IPropertyValue **
0x18007009e  mov     r8, rax; unsigned __int16 *
0x1800700a1  mov     rdx, [rbp+arg_10]; struct Windows::Data::Json::IJsonValue *
0x1800700a5  mov     rcx, rbx; this
0x1800700a8  call    ?GetPropertyValueFromJsonValue@PreviewBuildsState@Update@Management@Windows@@AEAAJPEAUIJsonValue@Json@Data@4@PEBGPEAPEAUIPropertyValue@Foundation@4@@Z; Windows::Management::Update::PreviewBuildsState::GetPropertyValueFromJsonValue(Windows::Data::Json::IJsonValue *,ushort const *,Windows::Foundation::IPropertyValue * *)
0x1800700ad  mov     ebx, eax
0x1800700af  test    eax, eax
0x1800700b1  jns     short loc_1800700BD
0x1800700b3  mov     r9d, eax
0x1800700b6  mov     edx, 0B4h
0x1800700bb  jmp     short loc_1800700F6
0x1800700bd  mov     [rbp+arg_0], 0
0x1800700c1  mov     rax, [r14+10h]
0x1800700c5  mov     rcx, [rax]
0x1800700c8  mov     rax, [rcx]
0x1800700cb  lea     r9, [rbp+arg_0]
0x1800700cf  mov     r8, [rbp+arg_18]
0x1800700d3  mov     rdx, [rbp+string]
0x1800700d7  mov     rax, [rax+50h]
0x1800700db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800700e0  mov     rcx, [r14]
0x1800700e3  mov     [rcx], eax
0x1800700e5  mov     rax, [r14]
0x1800700e8  mov     ebx, [rax]
0x1800700ea  test    ebx, ebx
0x1800700ec  jns     short loc_180070107
0x1800700ee  mov     r9d, ebx; char *
0x1800700f1  mov     edx, 0B8h; void *
0x1800700f6  lea     r8, aOnecoreBaseFli_92; "onecore\\base\\flighting\\flightsetting"...
0x1800700fd  mov     rcx, [rbp+30h]; this
0x180070101  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070106  nop
0x180070107  lea     rcx, [rbp+arg_18]
0x18007010b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180070110  nop
0x180070111  lea     rcx, [rbp+arg_10]
0x180070115  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007011a  nop
0x18007011b  cmp     dword ptr [rsi], 0
0x18007011e  jge     short loc_180070152
0x180070120  xor     edx, edx; length
0x180070122  mov     rcx, [rbp+string]; string
0x180070126  call    cs:__imp_WindowsGetStringRawBuffer
0x18007012c  mov     rdi, rax
0x18007012f  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x180070134  test    al, al
0x180070136  jz      short loc_180070152
0x180070138  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x18007013f  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x180070144  mov     r8, rdi; unsigned __int16 *
0x180070147  mov     edx, [rsi]; int
0x180070149  mov     rcx, rax; this
0x18007014c  call    ?GetPropertyValueFromJsonValueFailed_@FlightSettingsAPITelemetryClass@@QEAAXJPEBG@Z; FlightSettingsAPITelemetryClass::GetPropertyValueFromJsonValueFailed_(long,ushort const *)
0x180070151  nop
0x180070152  mov     rcx, [rbp+string]; string
0x180070156  call    cs:__imp_WindowsDeleteString
0x18007015c  mov     eax, ebx
0x18007015e  add     rsp, 58h
0x180070162  pop     r15
0x180070164  pop     r14
0x180070166  pop     rdi
0x180070167  pop     rsi
0x180070168  pop     rbx
0x180070169  pop     rbp
0x18007016a  retn
```
