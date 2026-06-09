# SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x18007bc10`
- end: `0x18007bd0b`
- name: `?SetValue@CSaveLocationsSettings@StorageSenseHandlers@SystemSettings@@UEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CSaveLocationsSettings *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x1800018bc`
- `0x18001fc0c`
- `0x18001fe08`
- `0x18007bc10`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18007bc71`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18007bc71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007bc33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007bcfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007bc33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007bcfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007bc59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007bc59`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x18007bc84`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x18007bc84`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::CSaveLocationsSettings::SetValue(
        WCHAR *this,
        struct Windows::Foundation::IPropertyValue *a2)
{
  void (__fastcall *v4)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  bool v5; // al
  SystemSettings::DataModel::CSettingBase *v6; // rcx
  const struct _tlgProvider_t *v7; // rax
  int v8; // r8d
  int v9; // r9d
  HSTRING string; // [rsp+50h] [rbp+8h] BYREF
  char *v12; // [rsp+58h] [rbp+10h] BYREF
  char *v13; // [rsp+60h] [rbp+18h] BYREF

  string = 0;
  v4 = *(void (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)a2 + 152LL);
  WindowsDeleteString(0);
  string = 0;
  v4(a2, &string);
  WindowsGetStringRawBuffer(string, 0);
  _o_wcscpy_s(this + 384, 260);
  v5 = StrCmpW(this + 384, this + 124) != 0;
  v6 = (SystemSettings::DataModel::CSettingBase *)*((_QWORD *)this + 161);
  if ( v6 )
  {
    *((_BYTE *)v6 + 224) = v5;
    SystemSettings::DataModel::CSettingBase::OnValueChanged(v6, (const unsigned __int16 *)&stru_180110918);
  }
  v7 = SettingsHandlersStorageSenseLogging::Provider();
  if ( *(_DWORD *)v7 > 4u )
  {
    v12 = (char *)(this + 124);
    v13 = (char *)(this + 384);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v7,
      (unsigned int)&unk_1801523CB,
      v8,
      v9,
      (__int64)&v13,
      (__int64)&v12);
  }
  SystemSettings::DataModel::CSettingBase::OnValueChanged(
    (SystemSettings::DataModel::CSettingBase *)this,
    (const unsigned __int16 *)&stru_1801068F0);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x18007bc10  push    rbx
0x18007bc12  push    rsi
0x18007bc13  push    rdi
0x18007bc14  sub     rsp, 30h
0x18007bc18  mov     rdi, rdx
0x18007bc1b  mov     rsi, rcx
0x18007bc1e  mov     [rsp+48h+string], 0
0x18007bc27  mov     rax, [rdx]
0x18007bc2a  mov     rbx, [rax+98h]
0x18007bc31  xor     ecx, ecx; string
0x18007bc33  call    cs:__imp_WindowsDeleteString
0x18007bc39  mov     [rsp+48h+string], 0
0x18007bc42  lea     rdx, [rsp+48h+string]
0x18007bc47  mov     rcx, rdi
0x18007bc4a  mov     rax, rbx
0x18007bc4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bc52  xor     edx, edx; length
0x18007bc54  mov     rcx, [rsp+48h+string]; string
0x18007bc59  call    cs:__imp_WindowsGetStringRawBuffer
0x18007bc5f  lea     rbx, [rsi+300h]
0x18007bc66  mov     r8, rax
0x18007bc69  mov     edx, 104h
0x18007bc6e  mov     rcx, rbx
0x18007bc71  call    cs:__imp__o_wcscpy_s
0x18007bc77  lea     rdi, [rsi+0F8h]
0x18007bc7e  mov     rdx, rdi; psz2
0x18007bc81  mov     rcx, rbx; psz1
0x18007bc84  call    cs:__imp_StrCmpW
0x18007bc8a  test    eax, eax
0x18007bc8c  setnz   al
0x18007bc8f  mov     rcx, [rsi+508h]; this
0x18007bc96  test    rcx, rcx
0x18007bc99  jz      short loc_18007BCAD
0x18007bc9b  mov     [rcx+0E0h], al
0x18007bca1  lea     rdx, stru_180110918; unsigned __int16 *
0x18007bca8  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18007bcad  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x18007bcb2  mov     ecx, [rax]
0x18007bcb4  cmp     ecx, 4
0x18007bcb7  jbe     short loc_18007BCE6
0x18007bcb9  mov     [rsp+48h+arg_8], rdi
0x18007bcbe  mov     [rsp+48h+arg_10], rbx
0x18007bcc3  lea     rcx, [rsp+48h+arg_8]
0x18007bcc8  mov     [rsp+48h+var_20], rcx
0x18007bccd  lea     rcx, [rsp+48h+arg_10]
0x18007bcd2  mov     [rsp+48h+var_28], rcx
0x18007bcd7  lea     rdx, unk_1801523CB
0x18007bcde  mov     rcx, rax
0x18007bce1  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18007bce6  lea     rdx, stru_1801068F0; unsigned __int16 *
0x18007bced  mov     rcx, rsi; this
0x18007bcf0  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18007bcf5  nop
0x18007bcf6  mov     rcx, [rsp+48h+string]; string
0x18007bcfb  call    cs:__imp_WindowsDeleteString
0x18007bd01  xor     eax, eax
0x18007bd03  add     rsp, 30h
0x18007bd07  pop     rdi
0x18007bd08  pop     rsi
0x18007bd09  pop     rbx
0x18007bd0a  retn
```
