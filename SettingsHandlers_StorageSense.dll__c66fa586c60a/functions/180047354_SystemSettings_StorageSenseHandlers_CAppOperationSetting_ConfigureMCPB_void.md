# SystemSettings::StorageSenseHandlers::CAppOperationSetting::_ConfigureMCPB(void)

- ea: `0x180047354`
- end: `0x180047621`
- name: `?_ConfigureMCPB@CAppOperationSetting@StorageSenseHandlers@SystemSettings@@AEAAJXZ`
- size: `717`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppOperationSetting *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180043ac0`

## callees

- `0x18000171c`
- `0x180001998`
- `0x180006e50`
- `0x180016ef4`
- `0x18001fe08`
- `0x180023928`
- `0x180047354`
- `0x18009e44c`
- `0x1800a7770`
- `0x1800a8404`
- `0x1800a8a88`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004739c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800473da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047418`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800474d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800474e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800474f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004750a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004751a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004752a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004753d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004754d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004755d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047580`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047590`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004739c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800473da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047418`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800474d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800474e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800474f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004750a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004751a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004752a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004753d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004754d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004755d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047580`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047590`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047448`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047468`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047485`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800475d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047448`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047468`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047485`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800475d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppOperationSetting::_ConfigureMCPB(
        SystemSettings::StorageSenseHandlers::CAppOperationSetting *this)
{
  SystemSettings::StorageSenseHandlers::CAppOperationSetting *v1; // rsi
  SystemSettings::StorageSenseHandlers::CAppTileData *v2; // rbx
  SystemSettings::StorageSenseHandlers::CAppTileData *v3; // rbx
  SystemSettings::StorageSenseHandlers::CAppTileData *v4; // rbx
  PCWSTR StringRawBuffer; // rax
  int v6; // r14d
  PCWSTR v7; // rax
  int v8; // ebx
  PCWSTR v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  const struct _tlgProvider_t *v12; // rax
  int v13; // r14d
  int v14; // r8d
  int v15; // r9d
  HSTRING string; // [rsp+30h] [rbp-B8h] BYREF
  HSTRING v18; // [rsp+38h] [rbp-B0h] BYREF
  HSTRING v19; // [rsp+40h] [rbp-A8h] BYREF
  PCWSTR v20; // [rsp+48h] [rbp-A0h] BYREF
  _BYTE v21[32]; // [rsp+50h] [rbp-98h] BYREF
  _BYTE v22[32]; // [rsp+70h] [rbp-78h] BYREF
  _BYTE v23[32]; // [rsp+90h] [rbp-58h] BYREF

  v1 = this;
  v20 = (PCWSTR)this;
  v19 = 0;
  string = 0;
  v18 = 0;
  v2 = *(SystemSettings::StorageSenseHandlers::CAppTileData **)(*((_QWORD *)this + 31) + 240LL);
  WindowsDeleteString(0);
  try
  {
    v19 = 0;
    if ( SystemSettings::StorageSenseHandlers::CAppTileData::GetInstallPath(v2, &v19) >= 0 && v19 )
    {
      v3 = *(SystemSettings::StorageSenseHandlers::CAppTileData **)(*((_QWORD *)v1 + 31) + 240LL);
      WindowsDeleteString(string);
      string = 0;
      if ( SystemSettings::StorageSenseHandlers::CAppTileData::GetManifestPath(v3, &string) >= 0
        && string
        && (v4 = *(SystemSettings::StorageSenseHandlers::CAppTileData **)(*((_QWORD *)v1 + 31) + 240LL),
            WindowsDeleteString(v18),
            v18 = 0,
            SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFamilyName(v4, &v18) >= 0)
        && v18 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(v18, 0);
        v6 = std::wstring::wstring(v23, StringRawBuffer);
        v7 = WindowsGetStringRawBuffer(string, 0);
        v8 = std::wstring::wstring(v22, v7);
        v9 = WindowsGetStringRawBuffer(v19, 0);
        v10 = std::wstring::wstring(v21, v9);
        v11 = SystemSettings::StorageSenseHandlers::LaunchMcpbInstallerConfigureUri(v10, v8, v6, 0, 0);
        std::wstring::_Tidy_deallocate(v21);
        std::wstring::_Tidy_deallocate(v22);
        std::wstring::_Tidy_deallocate(v23);
        WindowsDeleteString(v18);
        v18 = 0;
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v19);
      }
      else
      {
        v11 = -2147024809;
        WindowsDeleteString(v18);
        v18 = 0;
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v19);
      }
    }
    else
    {
      v11 = -2147024809;
      WindowsDeleteString(v18);
      v18 = 0;
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v19);
    }
  }
  catch ( ... )
  {
    LODWORD(string) = -2147467259;
    v11 = -2147467259;
    v1 = (SystemSettings::StorageSenseHandlers::CAppOperationSetting *)v20;
  }
  v12 = SettingsHandlersStorageSenseLogging::Provider();
  v13 = (int)v12;
  if ( *(_DWORD *)v12 > 3u && (unsigned __int8)tlgKeywordOn(v12, 0x200000000000LL) )
  {
    LODWORD(string) = v11;
    v20 = WindowsGetStringRawBuffer(*((HSTRING *)v1 + 28), 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v13,
      (unsigned int)&byte_18014FDC7,
      v14,
      v15,
      (__int64)&v20,
      (__int64)&string);
  }
  return v11;
}

```

## disassembly

```asm
0x180047354  push    rbx
0x180047356  push    rsi
0x180047357  push    rdi
0x180047358  push    r14
0x18004735a  sub     rsp, 0C8h
0x180047361  mov     rax, cs:__security_cookie
0x180047368  xor     rax, rsp
0x18004736b  mov     [rsp+0E8h+var_38], rax
0x180047373  mov     rsi, rcx
0x180047376  mov     [rsp+0E8h+var_A0], rcx
0x18004737b  xor     edi, edi
0x18004737d  mov     [rsp+0E8h+var_A8], rdi
0x180047382  mov     [rsp+0E8h+string], rdi
0x180047387  mov     [rsp+0E8h+var_B0], rdi
0x18004738c  mov     rax, [rcx+0F8h]
0x180047393  mov     rbx, [rax+0F0h]
0x18004739a  xor     ecx, ecx; string
0x18004739c  call    cs:__imp_WindowsDeleteString
0x1800473a2  mov     [rsp+0E8h+var_A8], rdi
0x1800473a7  lea     rdx, [rsp+0E8h+var_A8]; HSTRING *
0x1800473ac  mov     rcx, rbx; this
0x1800473af  call    ?GetInstallPath@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetInstallPath(HSTRING__ * *)
0x1800473b4  test    eax, eax
0x1800473b6  js      loc_180047566
0x1800473bc  cmp     [rsp+0E8h+var_A8], rdi
0x1800473c1  jz      loc_180047566
0x1800473c7  mov     rax, [rsi+0F8h]
0x1800473ce  mov     rbx, [rax+0F0h]
0x1800473d5  mov     rcx, [rsp+0E8h+string]; string
0x1800473da  call    cs:__imp_WindowsDeleteString
0x1800473e0  mov     [rsp+0E8h+string], rdi
0x1800473e5  lea     rdx, [rsp+0E8h+string]; HSTRING *
0x1800473ea  mov     rcx, rbx; this
0x1800473ed  call    ?GetManifestPath@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetManifestPath(HSTRING__ * *)
0x1800473f2  test    eax, eax
0x1800473f4  js      loc_180047533
0x1800473fa  cmp     [rsp+0E8h+string], rdi
0x1800473ff  jz      loc_180047533
0x180047405  mov     rax, [rsi+0F8h]
0x18004740c  mov     rbx, [rax+0F0h]
0x180047413  mov     rcx, [rsp+0E8h+var_B0]; string
0x180047418  call    cs:__imp_WindowsDeleteString
0x18004741e  mov     [rsp+0E8h+var_B0], rdi
0x180047423  lea     rdx, [rsp+0E8h+var_B0]; HSTRING *
0x180047428  mov     rcx, rbx; this
0x18004742b  call    ?GetPackageFamilyName@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFamilyName(HSTRING__ * *)
0x180047430  mov     rcx, [rsp+0E8h+var_B0]; string
0x180047435  test    eax, eax
0x180047437  js      loc_180047505
0x18004743d  test    rcx, rcx
0x180047440  jz      loc_180047505
0x180047446  xor     edx, edx; length
0x180047448  call    cs:__imp_WindowsGetStringRawBuffer
0x18004744e  mov     rdx, rax
0x180047451  lea     rcx, [rsp+0E8h+var_58]
0x180047459  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004745e  mov     r14, rax
0x180047461  xor     edx, edx; length
0x180047463  mov     rcx, [rsp+0E8h+string]; string
0x180047468  call    cs:__imp_WindowsGetStringRawBuffer
0x18004746e  mov     rdx, rax
0x180047471  lea     rcx, [rsp+0E8h+var_78]
0x180047476  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004747b  mov     rbx, rax
0x18004747e  xor     edx, edx; length
0x180047480  mov     rcx, [rsp+0E8h+var_A8]; string
0x180047485  call    cs:__imp_WindowsGetStringRawBuffer
0x18004748b  mov     rdx, rax
0x18004748e  lea     rcx, [rsp+0E8h+var_98]
0x180047493  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180047498  mov     [rsp+0E8h+var_C8], rdi
0x18004749d  xor     r9d, r9d
0x1800474a0  mov     r8, r14
0x1800474a3  mov     rdx, rbx
0x1800474a6  mov     rcx, rax
0x1800474a9  call    ?LaunchMcpbInstallerConfigureUri@StorageSenseHandlers@SystemSettings@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEBV34@1@Z; SystemSettings::StorageSenseHandlers::LaunchMcpbInstallerConfigureUri(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const *,std::wstring const *)
0x1800474ae  mov     ebx, eax
0x1800474b0  lea     rcx, [rsp+0E8h+var_98]
0x1800474b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800474ba  nop
0x1800474bb  lea     rcx, [rsp+0E8h+var_78]
0x1800474c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800474c5  nop
0x1800474c6  lea     rcx, [rsp+0E8h+var_58]
0x1800474ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800474d3  nop
0x1800474d4  mov     rcx, [rsp+0E8h+var_B0]; string
0x1800474d9  call    cs:__imp_WindowsDeleteString
0x1800474df  mov     [rsp+0E8h+var_B0], rdi
0x1800474e4  mov     rcx, [rsp+0E8h+string]; string
0x1800474e9  call    cs:__imp_WindowsDeleteString
0x1800474ef  mov     [rsp+0E8h+string], rdi
0x1800474f4  mov     rcx, [rsp+0E8h+var_A8]; string
0x1800474f9  call    cs:__imp_WindowsDeleteString
0x1800474ff  nop
0x180047500  jmp     loc_1800475A2
0x180047505  mov     ebx, 80070057h
0x18004750a  call    cs:__imp_WindowsDeleteString
0x180047510  mov     [rsp+0E8h+var_B0], rdi
0x180047515  mov     rcx, [rsp+0E8h+string]; string
0x18004751a  call    cs:__imp_WindowsDeleteString
0x180047520  mov     [rsp+0E8h+string], rdi
0x180047525  mov     rcx, [rsp+0E8h+var_A8]; string
0x18004752a  call    cs:__imp_WindowsDeleteString
0x180047530  nop
0x180047531  jmp     short loc_1800475A2
0x180047533  mov     ebx, 80070057h
0x180047538  mov     rcx, [rsp+0E8h+var_B0]; string
0x18004753d  call    cs:__imp_WindowsDeleteString
0x180047543  mov     [rsp+0E8h+var_B0], rdi
0x180047548  mov     rcx, [rsp+0E8h+string]; string
0x18004754d  call    cs:__imp_WindowsDeleteString
0x180047553  mov     [rsp+0E8h+string], rdi
0x180047558  mov     rcx, [rsp+0E8h+var_A8]; string
0x18004755d  call    cs:__imp_WindowsDeleteString
0x180047563  nop
0x180047564  jmp     short loc_1800475A2
0x180047566  mov     ebx, 80070057h
0x18004756b  mov     rcx, [rsp+0E8h+var_B0]; string
0x180047570  call    cs:__imp_WindowsDeleteString
0x180047576  mov     [rsp+0E8h+var_B0], rdi
0x18004757b  mov     rcx, [rsp+0E8h+string]; string
0x180047580  call    cs:__imp_WindowsDeleteString
0x180047586  mov     [rsp+0E8h+string], rdi
0x18004758b  mov     rcx, [rsp+0E8h+var_A8]; string
0x180047590  call    cs:__imp_WindowsDeleteString
0x180047596  nop
0x180047597  jmp     short loc_1800475A2
0x180047599  mov     ebx, dword ptr [rsp+0E8h+string]
0x18004759d  mov     rsi, [rsp+0E8h+var_A0]
0x1800475a2  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x1800475a7  mov     r14, rax
0x1800475aa  mov     edx, [rax]
0x1800475ac  cmp     edx, 3
0x1800475af  jbe     short loc_180047602
0x1800475b1  mov     rdx, 200000000000h
0x1800475bb  mov     rcx, rax
0x1800475be  call    _tlgKeywordOn
0x1800475c3  test    al, al
0x1800475c5  jz      short loc_180047602
0x1800475c7  mov     dword ptr [rsp+0E8h+string], ebx
0x1800475cb  xor     edx, edx; length
0x1800475cd  mov     rcx, [rsi+0E0h]; string
0x1800475d4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800475da  mov     [rsp+0E8h+var_A0], rax
0x1800475df  lea     rax, [rsp+0E8h+string]
0x1800475e4  mov     [rsp+0E8h+var_C0], rax
0x1800475e9  lea     rax, [rsp+0E8h+var_A0]
0x1800475ee  mov     [rsp+0E8h+var_C8], rax
0x1800475f3  lea     rdx, byte_18014FDC7
0x1800475fa  mov     rcx, r14
0x1800475fd  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180047602  mov     eax, ebx
0x180047604  mov     rcx, [rsp+0E8h+var_38]
0x18004760c  xor     rcx, rsp; StackCookie
0x18004760f  call    __security_check_cookie
0x180047614  add     rsp, 0C8h
0x18004761b  pop     r14
0x18004761d  pop     rdi
0x18004761e  pop     rsi
0x18004761f  pop     rbx
0x180047620  retn
```
