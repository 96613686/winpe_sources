# _lambda_7d85c6fafbd7d5d8be22d9bc65ba599d_::operator()

- ea: `0x1800a2184`
- end: `0x1800a229d`
- name: `_lambda_7d85c6fafbd7d5d8be22d9bc65ba599d_::operator()`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800aab70`

## callees

- `0x1800017e8`
- `0x18000c964`
- `0x18001fe08`
- `0x1800a2184`
- `0x1800abbf0`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2219`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2272`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2219`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2272`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a224b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a224b`

## pseudocode

```c
__int64 __fastcall lambda_7d85c6fafbd7d5d8be22d9bc65ba599d_::operator()(
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
      (unsigned int)&byte_180155327,
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
0x1800a2184  mov     [rsp-18h+string], rdx
0x1800a2189  push    rbp
0x1800a218a  push    rbx
0x1800a218b  push    rdi
0x1800a218c  mov     rbp, rsp
0x1800a218f  sub     rsp, 30h
0x1800a2193  mov     rdi, r8
0x1800a2196  mov     rcx, [rcx]; this
0x1800a2199  test    rcx, rcx
0x1800a219c  jz      short loc_1800A21A3
0x1800a219e  call    ?OnListChange@CAppNotificationSink@StorageSenseHandlers@SystemSettings@@QEAAXXZ; SystemSettings::StorageSenseHandlers::CAppNotificationSink::OnListChange(void)
0x1800a21a3  mov     [rbp+arg_10], 0
0x1800a21ab  mov     [rbp+arg_0], 0
0x1800a21b3  mov     [rbp+string], 0
0x1800a21bb  test    rdi, rdi
0x1800a21be  jz      short loc_1800A2236
0x1800a21c0  mov     rax, [rdi]
0x1800a21c3  mov     rbx, [rax+38h]
0x1800a21c7  lea     rcx, [rbp+arg_10]
0x1800a21cb  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a21d0  lea     rdx, [rbp+arg_10]
0x1800a21d4  mov     rcx, rdi
0x1800a21d7  mov     rax, rbx
0x1800a21da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a21df  test    eax, eax
0x1800a21e1  js      short loc_1800A2236
0x1800a21e3  mov     rdi, [rbp+arg_10]
0x1800a21e7  mov     rax, [rdi]
0x1800a21ea  mov     rbx, [rax+30h]
0x1800a21ee  lea     rcx, [rbp+arg_0]
0x1800a21f2  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a21f7  lea     rdx, [rbp+arg_0]
0x1800a21fb  mov     rcx, rdi
0x1800a21fe  mov     rax, rbx
0x1800a2201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2206  test    eax, eax
0x1800a2208  js      short loc_1800A2236
0x1800a220a  mov     rdi, [rbp+arg_0]
0x1800a220e  mov     rax, [rdi]
0x1800a2211  mov     rbx, [rax+60h]
0x1800a2215  mov     rcx, [rbp+string]; string
0x1800a2219  call    cs:__imp_WindowsDeleteString
0x1800a221f  mov     [rbp+string], 0
0x1800a2227  lea     rdx, [rbp+string]
0x1800a222b  mov     rcx, rdi
0x1800a222e  mov     rax, rbx
0x1800a2231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2236  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x1800a223b  mov     rbx, rax
0x1800a223e  mov     ecx, [rax]
0x1800a2240  cmp     ecx, 4
0x1800a2243  jbe     short loc_1800A226E
0x1800a2245  xor     edx, edx; length
0x1800a2247  mov     rcx, [rbp+string]; string
0x1800a224b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a2251  mov     [rbp+arg_18], rax
0x1800a2255  lea     rax, [rbp+arg_18]
0x1800a2259  mov     [rsp+30h+var_10], rax
0x1800a225e  lea     rdx, byte_180155327
0x1800a2265  mov     rcx, rbx
0x1800a2268  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800a226d  nop
0x1800a226e  mov     rcx, [rbp+string]; string
0x1800a2272  call    cs:__imp_WindowsDeleteString
0x1800a2278  mov     [rbp+string], 0
0x1800a2280  lea     rcx, [rbp+arg_0]
0x1800a2284  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a2289  nop
0x1800a228a  lea     rcx, [rbp+arg_10]
0x1800a228e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a2293  xor     eax, eax
0x1800a2295  add     rsp, 30h
0x1800a2299  pop     rdi
0x1800a229a  pop     rbx
0x1800a229b  pop     rbp
0x1800a229c  retn
```
