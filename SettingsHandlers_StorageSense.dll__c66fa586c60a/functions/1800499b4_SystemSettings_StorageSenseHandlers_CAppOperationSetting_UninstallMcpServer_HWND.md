# SystemSettings::StorageSenseHandlers::CAppOperationSetting::_UninstallMcpServer(HWND__ *)

- ea: `0x1800499b4`
- end: `0x180049c86`
- name: `?_UninstallMcpServer@CAppOperationSetting@StorageSenseHandlers@SystemSettings@@AEAAJPEAUHWND__@@@Z`
- size: `722`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppOperationSetting *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180043ac0`

## callees

- `0x18000171c`
- `0x180001d14`
- `0x180006e50`
- `0x180014940`
- `0x180016ef4`
- `0x18001fe08`
- `0x180023578`
- `0x180023928`
- `0x1800352b4`
- `0x18003e3e4`
- `0x180044e28`
- `0x1800499b4`
- `0x18009db10`
- `0x1800a978c`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049afe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049b23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049b31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049afe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049b23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049b31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049a83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049be5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049a83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049be5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x180049aaa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x180049aaa`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppOperationSetting::_UninstallMcpServer(
        SystemSettings::StorageSenseHandlers::CAppOperationSetting *this,
        HWND a2)
{
  HWND v2; // r14
  _QWORD *v4; // rsi
  SystemSettings::StorageSenseHandlers::CAppTileData *v5; // rbx
  PCWSTR StringRawBuffer; // rax
  const WCHAR *v7; // rax
  LPWSTR ArgsW; // rax
  LPWSTR v9; // rbx
  SystemSettings::StorageSenseHandlers::CAppSizesDriveSelectionSingleton *v10; // rcx
  int v11; // ebx
  const struct _tlgProvider_t *v12; // rax
  int v13; // esi
  char *v14; // rdx
  int v15; // r8d
  int v16; // r9d
  HSTRING string; // [rsp+50h] [rbp-A8h] BYREF
  int v19; // [rsp+58h] [rbp-A0h] BYREF
  PCWSTR v20; // [rsp+60h] [rbp-98h] BYREF
  HWND v21; // [rsp+68h] [rbp-90h] BYREF
  char *v22; // [rsp+70h] [rbp-88h] BYREF
  __int128 v23; // [rsp+78h] [rbp-80h] BYREF
  __m128i si128; // [rsp+88h] [rbp-70h]
  __m128i v25[2]; // [rsp+98h] [rbp-60h] BYREF
  _BYTE v26[32]; // [rsp+B8h] [rbp-40h] BYREF

  v2 = a2;
  v20 = (PCWSTR)this;
  v21 = a2;
  v19 = 0;
  v23 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v23) = 0;
  v25[0] = 0;
  v25[1] = _mm_load_si128((const __m128i *)&_xmm);
  v25[0].m128i_i16[0] = 0;
  v4 = (_QWORD *)((char *)this + 248);
  v22 = (char *)this + 248;
  LOBYTE(a2) = 1;
  SystemSettings::StorageSenseHandlers::CPackageSizeSetting::SetIsAppBusy(*((_QWORD *)this + 31), a2, 1);
  string = 0;
  v5 = *(SystemSettings::StorageSenseHandlers::CAppTileData **)(*v4 + 240LL);
  WindowsDeleteString(0);
  string = 0;
  if ( SystemSettings::StorageSenseHandlers::CAppTileData::GetUninstallCommand(v5, &string) < 0 || !string )
  {
    v11 = -2147024809;
    WindowsDeleteString(string);
    goto LABEL_11;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(v26, StringRawBuffer);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
  ArgsW = PathGetArgsW(v7);
  v9 = ArgsW;
  if ( !ArgsW || !*ArgsW )
  {
    v11 = -2147024809;
    std::wstring::_Tidy_deallocate(v26);
    WindowsDeleteString(string);
LABEL_11:
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, HWND))(*(_QWORD *)*v4 + 232LL))(*v4, (unsigned int)v11, 1, v2);
    goto LABEL_12;
  }
  std::wstring::assign(v25, ArgsW);
  v11 = SystemSettings::StorageSenseHandlers::ExecuteOdrCommand(v9, &v23, &v19);
  if ( v11 >= 0 )
    SystemSettings::StorageSenseHandlers::CAppSizesDriveSelectionSingleton::ForceListRefresh(v10);
  std::wstring::_Tidy_deallocate(v26);
  WindowsDeleteString(string);
  if ( v11 < 0 )
    goto LABEL_11;
LABEL_12:
  SystemSettings::StorageSenseHandlers::CPackageSizeSetting::SetIsAppBusy(*v4, 0, 1);
  v12 = SettingsHandlersStorageSenseLogging::Provider();
  v13 = (int)v12;
  if ( *(_DWORD *)v12 > 3u && (unsigned __int8)tlgKeywordOn(v12, 0x200000000000LL) )
  {
    LODWORD(string) = v11;
    v14 = (char *)&v23;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v14 = (char *)v23;
    v22 = v14;
    v21 = (HWND)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
    v20 = WindowsGetStringRawBuffer(*((HSTRING *)this + 28), 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v13,
      (unsigned int)byte_18014FE0D,
      v15,
      v16,
      (__int64)&v20,
      (__int64)&v21,
      (__int64)&v19,
      (__int64)&v22,
      (__int64)&string);
  }
  std::wstring::_Tidy_deallocate(v25);
  if ( si128.m128i_i64[1] > 0xFuLL )
    std::_Deallocate<16>((void *)v23, si128.m128i_i64[1] + 1);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800499b4  mov     r11, rsp
0x1800499b7  mov     [r11+18h], rbx
0x1800499bb  mov     [r11+20h], rsi
0x1800499bf  push    rdi
0x1800499c0  push    r14
0x1800499c2  push    r15
0x1800499c4  sub     rsp, 0E0h
0x1800499cb  mov     rax, cs:__security_cookie
0x1800499d2  xor     rax, rsp
0x1800499d5  mov     [rsp+0F8h+var_20], rax
0x1800499dd  mov     r14, rdx
0x1800499e0  mov     r15, rcx
0x1800499e3  mov     [rsp+0F8h+var_98], rcx
0x1800499e8  mov     [rsp+0F8h+var_90], rdx
0x1800499ed  xor     edi, edi
0x1800499ef  mov     [rsp+0F8h+var_A0], edi
0x1800499f3  xorps   xmm0, xmm0
0x1800499f6  movups  [rsp+0F8h+var_80], xmm0
0x1800499fb  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180049a03  movdqu  xmmword ptr [r11-70h], xmm1
0x180049a09  mov     byte ptr [rsp+0F8h+var_80], dil
0x180049a0e  movups  xmmword ptr [r11-60h], xmm0
0x180049a13  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180049a1b  movdqu  xmmword ptr [r11-50h], xmm1
0x180049a21  mov     [r11-60h], di
0x180049a26  lea     rsi, [rcx+0F8h]
0x180049a2d  mov     [rsp+0F8h+var_88], rsi
0x180049a32  lea     r8d, [rdi+1]
0x180049a36  mov     dl, r8b
0x180049a39  mov     rcx, [rsi]
0x180049a3c  call    ?SetIsAppBusy@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAX_NW4AppOperationType@23@@Z; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::SetIsAppBusy(bool,SystemSettings::StorageSenseHandlers::AppOperationType)
0x180049a41  nop
0x180049a42  mov     [rsp+0F8h+string], rdi
0x180049a47  mov     rax, [rsi]
0x180049a4a  mov     rbx, [rax+0F0h]
0x180049a51  xor     ecx, ecx; string
0x180049a53  call    cs:__imp_WindowsDeleteString
0x180049a59  mov     [rsp+0F8h+string], rdi
0x180049a5e  lea     rdx, [rsp+0F8h+string]; HSTRING *
0x180049a63  mov     rcx, rbx; this
0x180049a66  call    ?GetUninstallCommand@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetUninstallCommand(HSTRING__ * *)
0x180049a6b  mov     rcx, [rsp+0F8h+string]; string
0x180049a70  test    eax, eax
0x180049a72  js      loc_180049B2C
0x180049a78  test    rcx, rcx
0x180049a7b  jz      loc_180049B2C
0x180049a81  xor     edx, edx; length
0x180049a83  call    cs:__imp_WindowsGetStringRawBuffer
0x180049a89  mov     rdx, rax
0x180049a8c  lea     rcx, [rsp+0F8h+var_40]
0x180049a94  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180049a99  nop
0x180049a9a  lea     rcx, [rsp+0F8h+var_40]
0x180049aa2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049aa7  mov     rcx, rax; pszPath
0x180049aaa  call    cs:__imp_PathGetArgsW
0x180049ab0  mov     rbx, rax
0x180049ab3  test    rax, rax
0x180049ab6  jz      short loc_180049B0B
0x180049ab8  cmp     [rax], di
0x180049abb  jz      short loc_180049B0B
0x180049abd  mov     rdx, rax
0x180049ac0  lea     rcx, [rsp+0F8h+var_60]
0x180049ac8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180049acd  lea     r8, [rsp+0F8h+var_A0]
0x180049ad2  lea     rdx, [rsp+0F8h+var_80]
0x180049ad7  mov     rcx, rbx
0x180049ada  call    ?ExecuteOdrCommand@StorageSenseHandlers@SystemSettings@@YAJPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAK@Z; SystemSettings::StorageSenseHandlers::ExecuteOdrCommand(ushort const *,std::string &,ulong *)
0x180049adf  mov     ebx, eax
0x180049ae1  test    eax, eax
0x180049ae3  js      short loc_180049AEB
0x180049ae5  call    ?ForceListRefresh@CAppSizesDriveSelectionSingleton@StorageSenseHandlers@SystemSettings@@QEAAXXZ; SystemSettings::StorageSenseHandlers::CAppSizesDriveSelectionSingleton::ForceListRefresh(void)
0x180049aea  nop
0x180049aeb  lea     rcx, [rsp+0F8h+var_40]
0x180049af3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049af8  nop
0x180049af9  mov     rcx, [rsp+0F8h+string]; string
0x180049afe  call    cs:__imp_WindowsDeleteString
0x180049b04  nop
0x180049b05  test    ebx, ebx
0x180049b07  js      short loc_180049B4D
0x180049b09  jmp     short loc_180049B6A
0x180049b0b  mov     ebx, 80070057h
0x180049b10  lea     rcx, [rsp+0F8h+var_40]
0x180049b18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049b1d  nop
0x180049b1e  mov     rcx, [rsp+0F8h+string]; string
0x180049b23  call    cs:__imp_WindowsDeleteString
0x180049b29  nop
0x180049b2a  jmp     short loc_180049B4D
0x180049b2c  mov     ebx, 80070057h
0x180049b31  call    cs:__imp_WindowsDeleteString
0x180049b37  nop
0x180049b38  jmp     short loc_180049B4D
0x180049b3a  mov     ebx, dword ptr [rsp+0F8h+string]
0x180049b3e  mov     r15, [rsp+0F8h+var_98]
0x180049b43  mov     r14, [rsp+0F8h+var_90]
0x180049b48  mov     rsi, [rsp+0F8h+var_88]
0x180049b4d  mov     rcx, [rsi]
0x180049b50  mov     rax, [rcx]
0x180049b53  mov     r9, r14
0x180049b56  mov     r8d, 1
0x180049b5c  mov     edx, ebx
0x180049b5e  mov     rax, [rax+0E8h]
0x180049b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b6a  xor     edx, edx
0x180049b6c  lea     r8d, [rdx+1]
0x180049b70  mov     rcx, [rsi]
0x180049b73  call    ?SetIsAppBusy@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAX_NW4AppOperationType@23@@Z; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::SetIsAppBusy(bool,SystemSettings::StorageSenseHandlers::AppOperationType)
0x180049b78  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x180049b7d  mov     rsi, rax
0x180049b80  mov     ecx, [rax]
0x180049b82  cmp     ecx, 3
0x180049b85  jbe     loc_180049C32
0x180049b8b  mov     rdx, 200000000000h
0x180049b95  mov     rcx, rax
0x180049b98  call    _tlgKeywordOn
0x180049b9d  test    al, al
0x180049b9f  jz      loc_180049C32
0x180049ba5  mov     dword ptr [rsp+0F8h+string], ebx
0x180049ba9  lea     rdx, [rsp+0F8h+var_80]
0x180049bae  cmp     [rsp+0F8h+var_68], 0Fh
0x180049bb7  cmova   rdx, qword ptr [rsp+0F8h+var_80]
0x180049bbd  mov     [rsp+0F8h+var_88], rdx
0x180049bc2  mov     eax, [rsp+0F8h+var_A0]
0x180049bc6  mov     [rsp+0F8h+var_A0], eax
0x180049bca  lea     rcx, [rsp+0F8h+var_60]
0x180049bd2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049bd7  mov     [rsp+0F8h+var_90], rax
0x180049bdc  xor     edx, edx; length
0x180049bde  mov     rcx, [r15+0E0h]; string
0x180049be5  call    cs:__imp_WindowsGetStringRawBuffer
0x180049beb  mov     [rsp+0F8h+var_98], rax
0x180049bf0  lea     rax, [rsp+0F8h+string]
0x180049bf5  mov     [rsp+0F8h+var_B8], rax
0x180049bfa  lea     rax, [rsp+0F8h+var_88]
0x180049bff  mov     [rsp+0F8h+var_C0], rax
0x180049c04  lea     rax, [rsp+0F8h+var_A0]
0x180049c09  mov     [rsp+0F8h+var_C8], rax
0x180049c0e  lea     rax, [rsp+0F8h+var_90]
0x180049c13  mov     [rsp+0F8h+var_D0], rax
0x180049c18  lea     rax, [rsp+0F8h+var_98]
0x180049c1d  mov     [rsp+0F8h+var_D8], rax
0x180049c22  lea     rdx, byte_18014FE0D
0x180049c29  mov     rcx, rsi
0x180049c2c  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180049c31  nop
0x180049c32  lea     rcx, [rsp+0F8h+var_60]
0x180049c3a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049c3f  nop
0x180049c40  mov     rdx, [rsp+0F8h+var_68]
0x180049c48  cmp     rdx, 0Fh
0x180049c4c  jbe     short loc_180049C5B
0x180049c4e  inc     rdx
0x180049c51  mov     rcx, qword ptr [rsp+0F8h+var_80]
0x180049c56  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180049c5b  mov     eax, ebx
0x180049c5d  mov     rcx, [rsp+0F8h+var_20]
0x180049c65  xor     rcx, rsp; StackCookie
0x180049c68  call    __security_check_cookie
0x180049c6d  lea     r11, [rsp+0F8h+var_18]
0x180049c75  mov     rbx, [r11+30h]
0x180049c79  mov     rsi, [r11+38h]
0x180049c7d  mov     rsp, r11
0x180049c80  pop     r15
0x180049c82  pop     r14
0x180049c84  pop     rdi
0x180049c85  retn
```
