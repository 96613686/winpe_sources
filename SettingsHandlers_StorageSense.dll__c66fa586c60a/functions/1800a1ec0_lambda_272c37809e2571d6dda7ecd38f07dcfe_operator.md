# _lambda_272c37809e2571d6dda7ecd38f07dcfe_::operator()

- ea: `0x1800a1ec0`
- end: `0x1800a1fd9`
- name: `_lambda_272c37809e2571d6dda7ecd38f07dcfe_::operator()`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800aaba0`

## callees

- `0x1800017e8`
- `0x18000c964`
- `0x18001fe08`
- `0x1800a1ec0`
- `0x1800abbf0`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1f55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1fae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1f55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1fae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1f87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1f87`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_272c37809e2571d6dda7ecd38f07dcfe_::operator()(
        SystemSettings::StorageSenseHandlers::CAppNotificationSink **a1,
        HSTRING a2,
        __int64 a3)
{
  SystemSettings::StorageSenseHandlers::CAppNotificationSink *v4; // rcx
  int (__fastcall *v5)(__int64, __int64 *); // rbx
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, __int64 *); // rbx
  __int64 v8; // rdi
  void (__fastcall *v9)(__int64, HSTRING *); // rbx
  const struct _tlgProvider_t *v10; // rax
  int v11; // ebx
  int v12; // r8d
  int v13; // r9d
  __int64 v15; // [rsp+50h] [rbp+20h] BYREF
  HSTRING string; // [rsp+58h] [rbp+28h] BYREF
  __int64 v17; // [rsp+60h] [rbp+30h] BYREF
  PCWSTR StringRawBuffer; // [rsp+68h] [rbp+38h] BYREF

  string = a2;
  v4 = *a1;
  if ( v4 )
    SystemSettings::StorageSenseHandlers::CAppNotificationSink::OnListChange(v4);
  v17 = 0;
  v15 = 0;
  string = 0;
  if ( a3 )
  {
    v5 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 56LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v17);
    if ( v5(a3, &v17) >= 0 )
    {
      v6 = v17;
      v7 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 48LL);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v15);
      if ( v7(v6, &v15) >= 0 )
      {
        v8 = v15;
        v9 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 96LL);
        WindowsDeleteString(string);
        string = 0;
        v9(v8, &string);
      }
    }
  }
  v10 = SettingsHandlersStorageSenseLogging::Provider();
  v11 = (int)v10;
  if ( *(_DWORD *)v10 > 4u )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v11,
      (unsigned int)&dword_1801552EC,
      v12,
      v13,
      (__int64)&StringRawBuffer);
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v17);
  return 0;
}

```

## disassembly

```asm
0x1800a1ec0  mov     [rsp-18h+string], rdx
0x1800a1ec5  push    rbp
0x1800a1ec6  push    rbx
0x1800a1ec7  push    rdi
0x1800a1ec8  mov     rbp, rsp
0x1800a1ecb  sub     rsp, 30h
0x1800a1ecf  mov     rdi, r8
0x1800a1ed2  mov     rcx, [rcx]; this
0x1800a1ed5  test    rcx, rcx
0x1800a1ed8  jz      short loc_1800A1EDF
0x1800a1eda  call    ?OnListChange@CAppNotificationSink@StorageSenseHandlers@SystemSettings@@QEAAXXZ; SystemSettings::StorageSenseHandlers::CAppNotificationSink::OnListChange(void)
0x1800a1edf  mov     [rbp+arg_10], 0
0x1800a1ee7  mov     [rbp+arg_0], 0
0x1800a1eef  mov     [rbp+string], 0
0x1800a1ef7  test    rdi, rdi
0x1800a1efa  jz      short loc_1800A1F72
0x1800a1efc  mov     rax, [rdi]
0x1800a1eff  mov     rbx, [rax+38h]
0x1800a1f03  lea     rcx, [rbp+arg_10]
0x1800a1f07  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a1f0c  lea     rdx, [rbp+arg_10]
0x1800a1f10  mov     rcx, rdi
0x1800a1f13  mov     rax, rbx
0x1800a1f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1f1b  test    eax, eax
0x1800a1f1d  js      short loc_1800A1F72
0x1800a1f1f  mov     rdi, [rbp+arg_10]
0x1800a1f23  mov     rax, [rdi]
0x1800a1f26  mov     rbx, [rax+30h]
0x1800a1f2a  lea     rcx, [rbp+arg_0]
0x1800a1f2e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a1f33  lea     rdx, [rbp+arg_0]
0x1800a1f37  mov     rcx, rdi
0x1800a1f3a  mov     rax, rbx
0x1800a1f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1f42  test    eax, eax
0x1800a1f44  js      short loc_1800A1F72
0x1800a1f46  mov     rdi, [rbp+arg_0]
0x1800a1f4a  mov     rax, [rdi]
0x1800a1f4d  mov     rbx, [rax+60h]
0x1800a1f51  mov     rcx, [rbp+string]; string
0x1800a1f55  call    cs:__imp_WindowsDeleteString
0x1800a1f5b  mov     [rbp+string], 0
0x1800a1f63  lea     rdx, [rbp+string]
0x1800a1f67  mov     rcx, rdi
0x1800a1f6a  mov     rax, rbx
0x1800a1f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1f72  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x1800a1f77  mov     rbx, rax
0x1800a1f7a  mov     ecx, [rax]
0x1800a1f7c  cmp     ecx, 4
0x1800a1f7f  jbe     short loc_1800A1FAA
0x1800a1f81  xor     edx, edx; length
0x1800a1f83  mov     rcx, [rbp+string]; string
0x1800a1f87  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a1f8d  mov     [rbp+arg_18], rax
0x1800a1f91  lea     rax, [rbp+arg_18]
0x1800a1f95  mov     [rsp+30h+var_10], rax
0x1800a1f9a  lea     rdx, dword_1801552EC
0x1800a1fa1  mov     rcx, rbx
0x1800a1fa4  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800a1fa9  nop
0x1800a1faa  mov     rcx, [rbp+string]; string
0x1800a1fae  call    cs:__imp_WindowsDeleteString
0x1800a1fb4  mov     [rbp+string], 0
0x1800a1fbc  lea     rcx, [rbp+arg_0]
0x1800a1fc0  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a1fc5  nop
0x1800a1fc6  lea     rcx, [rbp+arg_10]
0x1800a1fca  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a1fcf  xor     eax, eax
0x1800a1fd1  add     rsp, 30h
0x1800a1fd5  pop     rdi
0x1800a1fd6  pop     rbx
0x1800a1fd7  pop     rbp
0x1800a1fd8  retn
```
