# SystemSettings::BatteryUsageHandlers::AppList::_UpdateAppVisibility(SystemSettings::BatteryUsageHandlers::AppListEntry *,HSTRING__ *)

- ea: `0x180030ec8`
- end: `0x180030fa6`
- name: `?_UpdateAppVisibility@AppList@BatteryUsageHandlers@SystemSettings@@AEAA_NPEAVAppListEntry@23@PEAUHSTRING__@@@Z`
- size: `222`
- prototype: `bool(SystemSettings::BatteryUsageHandlers::AppList *__hidden this, struct SystemSettings::BatteryUsageHandlers::AppListEntry *, HSTRING)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002f25c`
- `0x180032d04`

## callees

- `0x18000fbe8`
- `0x18002e2b0`
- `0x180030ec8`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180030f55`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180030f55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030f0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030f7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030f90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030f0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030f7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030f90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030f3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030f49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030f3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030f49`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall SystemSettings::BatteryUsageHandlers::AppList::_UpdateAppVisibility(
        SystemSettings::BatteryUsageHandlers::AppList *this,
        struct SystemSettings::BatteryUsageHandlers::AppListEntry *a2,
        HSTRING a3)
{
  bool v4; // si
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v6; // rax
  HSTRING string; // [rsp+40h] [rbp+20h] BYREF
  HSTRING newString; // [rsp+48h] [rbp+28h] BYREF
  HSTRING v10; // [rsp+50h] [rbp+30h] BYREF

  v10 = a3;
  newString = 0;
  string = 0;
  v4 = 1;
  Microsoft::WRL::Wrappers::HString::Set(&newString, &v10);
  if ( newString )
  {
    WindowsDeleteString(string);
    string = 0;
    if ( (*(int (__fastcall **)(struct SystemSettings::BatteryUsageHandlers::AppListEntry *, HSTRING *))(*(_QWORD *)a2 + 88LL))(
           a2,
           &string) >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(newString, 0);
      v6 = WindowsGetStringRawBuffer(string, 0);
      v4 = StrStrIW(v6, StringRawBuffer) != 0;
    }
  }
  *((_BYTE *)a2 + 392) = v4;
  SystemSettings::DataModel::CSettingBase::OnValueChanged(a2, (const unsigned __int16 *)&stru_180069760);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(newString);
  return v4;
}

```

## disassembly

```asm
0x180030ec8  mov     [rsp-18h+arg_18], rbx
0x180030ecd  mov     [rsp-18h+arg_10], r8
0x180030ed2  mov     [rsp-18h+string], rcx
0x180030ed7  push    rbp
0x180030ed8  push    rsi
0x180030ed9  push    rdi
0x180030eda  mov     rbp, rsp
0x180030edd  sub     rsp, 20h
0x180030ee1  mov     rdi, rdx
0x180030ee4  mov     [rbp+newString], 0
0x180030eec  mov     [rbp+string], 0
0x180030ef4  mov     sil, 1
0x180030ef7  lea     rdx, [rbp+arg_10]; HSTRING *
0x180030efb  lea     rcx, [rbp+newString]; newString
0x180030eff  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180030f04  cmp     [rbp+newString], 0
0x180030f09  jz      short loc_180030F63
0x180030f0b  mov     rcx, [rbp+string]; string
0x180030f0f  call    cs:__imp_WindowsDeleteString
0x180030f15  mov     [rbp+string], 0
0x180030f1d  mov     rax, [rdi]
0x180030f20  lea     rdx, [rbp+string]
0x180030f24  mov     rcx, rdi
0x180030f27  mov     rax, [rax+58h]
0x180030f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f30  test    eax, eax
0x180030f32  js      short loc_180030F63
0x180030f34  xor     edx, edx; length
0x180030f36  mov     rcx, [rbp+newString]; string
0x180030f3a  call    cs:__imp_WindowsGetStringRawBuffer
0x180030f40  mov     rbx, rax
0x180030f43  xor     edx, edx; length
0x180030f45  mov     rcx, [rbp+string]; string
0x180030f49  call    cs:__imp_WindowsGetStringRawBuffer
0x180030f4f  mov     rdx, rbx; pszSrch
0x180030f52  mov     rcx, rax; pszFirst
0x180030f55  call    cs:__imp_StrStrIW
0x180030f5b  neg     rax
0x180030f5e  sbb     cl, cl
0x180030f60  and     sil, cl
0x180030f63  mov     [rdi+188h], sil
0x180030f6a  lea     rdx, stru_180069760; unsigned __int16 *
0x180030f71  mov     rcx, rdi; this
0x180030f74  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180030f79  nop
0x180030f7a  mov     rcx, [rbp+string]; string
0x180030f7e  call    cs:__imp_WindowsDeleteString
0x180030f84  mov     [rbp+string], 0
0x180030f8c  mov     rcx, [rbp+newString]; string
0x180030f90  call    cs:__imp_WindowsDeleteString
0x180030f96  mov     al, sil
0x180030f99  mov     rbx, [rsp+20h+arg_18]
0x180030f9e  add     rsp, 20h
0x180030fa2  pop     rdi
0x180030fa3  pop     rsi
0x180030fa4  pop     rbp
0x180030fa5  retn
```
