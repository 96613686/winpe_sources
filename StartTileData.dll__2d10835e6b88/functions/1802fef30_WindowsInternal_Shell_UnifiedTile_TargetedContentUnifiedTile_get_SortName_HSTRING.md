# WindowsInternal::Shell::UnifiedTile::TargetedContentUnifiedTile::get_SortName(HSTRING__ * *)

- ea: `0x1802fef30`
- end: `0x1802ff0e9`
- name: `?get_SortName@TargetedContentUnifiedTile@UnifiedTile@Shell@WindowsInternal@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(WindowsInternal::Shell::UnifiedTile::TargetedContentUnifiedTile *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18001f0a0`
- `0x180020474`
- `0x1800222ec`
- `0x18012f990`
- `0x1802fef30`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802fef5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802fef89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802fefd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802fefe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ff091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ff0b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ff0c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802fef5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802fef89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802fefd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802fefe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ff091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ff0b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ff0c1`

## string_xrefs

- `0x1802fefbc`: `shellcommon\shell\tiles\unifiedtilemodel\lib\targetedcontentunifiedtile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::TargetedContentUnifiedTile::get_SortName(
        WindowsInternal::Shell::UnifiedTile::TargetedContentUnifiedTile *this,
        HSTRING *a2)
{
  int DisplayName; // eax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, const struct _GUID *, GUID *, __int64 *); // rbx
  char v10; // al
  HSTRING v11; // rdi
  HSTRING v12; // rbx
  HSTRING v13; // rax
  int v14; // [rsp+20h] [rbp-78h]
  _BYTE v15[104]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  HSTRING string; // [rsp+A0h] [rbp+8h] BYREF
  HSTRING v18; // [rsp+A8h] [rbp+10h]
  __int64 v19; // [rsp+B0h] [rbp+18h] BYREF
  HSTRING v20; // [rsp+B8h] [rbp+20h] BYREF

  UnifiedTileTelemetry::WatchCurrentThread(v15, "TargetedContentUnifiedTile_get_SortName");
  *a2 = 0;
  WindowsDeleteString(0);
  v18 = 0;
  try
  {
    WindowsInternal::Shell::UnifiedTile::GetStringProperty();
    WindowsDeleteString(0);
    string = 0;
    DisplayName = WindowsInternal::Shell::UnifiedTile::TargetedContentUnifiedTile::get_DisplayName(this, &string);
    v5 = DisplayName;
    if ( DisplayName >= 0 )
    {
      v19 = 0;
      v8 = *((_QWORD *)this + 11);
      v9 = *(__int64 (__fastcall **)(__int64, const struct _GUID *, GUID *, __int64 *))(*(_QWORD *)v8 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
      v10 = v9(v8, &c_MRTTransformerId, &GUID_461218a4_e7b8_4c32_bdb8_7421111d6c4a, &v19);
      v11 = v18;
      if ( v10 )
      {
        v12 = string;
        (*(void (__fastcall **)(__int64, HSTRING *, HSTRING, HSTRING))(*(_QWORD *)v19 + 40LL))(v19, &v20, v18, string);
        v13 = v20;
        v20 = 0;
        *a2 = v13;
        WindowsDeleteString(0);
      }
      else
      {
        v12 = 0;
        *a2 = string;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
      WindowsDeleteString(v12);
      WindowsDeleteString(v11);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v15);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x128,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\targetedcontentunifiedtile.cpp",
        (const char *)(unsigned int)DisplayName,
        v14);
      WindowsDeleteString(string);
      WindowsDeleteString(v18);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v15);
      result = v5;
    }
  }
  catch ( ... )
  {
    LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x137,
                        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\targetedcontentunifiedtile.cpp",
                        v6);
    return (unsigned int)string;
  }
  return result;
}

```

## disassembly

```asm
0x1802fef30  push    rbx
0x1802fef32  push    rsi
0x1802fef33  push    rdi
0x1802fef34  sub     rsp, 80h
0x1802fef3b  mov     rsi, rdx
0x1802fef3e  mov     rdi, rcx
0x1802fef41  lea     rdx, aTargetedconten_49; "TargetedContentUnifiedTile_get_SortName"
0x1802fef48  lea     rcx, [rsp+98h+var_68]
0x1802fef4d  call    ?WatchCurrentThread@UnifiedTileTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; UnifiedTileTelemetry::WatchCurrentThread(char const *)
0x1802fef52  nop
0x1802fef53  mov     qword ptr [rsi], 0
0x1802fef5a  xor     ecx, ecx; string
0x1802fef5c  call    cs:__imp_WindowsDeleteString
0x1802fef62  mov     [rsp+98h+arg_8], 0
0x1802fef6e  lea     r8, [rsp+98h+arg_8]
0x1802fef76  lea     rdx, ?PhoneticName@TargetedContentProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; DataStoreCache::DataStoreProperty<HSTRING__ *> const DataStoreCache::TargetedContentProperties::PhoneticName
0x1802fef7d  mov     rcx, [rdi+58h]
0x1802fef81  call    ?GetStringProperty@UnifiedTile@Shell@WindowsInternal@@YAJPEAUIDataItem@DataStoreCache@@AEBU?$DataStoreProperty@PEAUHSTRING__@@@5@PEAPEAUHSTRING__@@@Z; WindowsInternal::Shell::UnifiedTile::GetStringProperty(DataStoreCache::IDataItem *,DataStoreCache::DataStoreProperty<HSTRING__ *> const &,HSTRING__ * *)
0x1802fef86  nop
0x1802fef87  xor     ecx, ecx; string
0x1802fef89  call    cs:__imp_WindowsDeleteString
0x1802fef8f  mov     [rsp+98h+string], 0
0x1802fef9b  lea     rdx, [rsp+98h+string]; HSTRING *
0x1802fefa3  mov     rcx, rdi; this
0x1802fefa6  call    ?get_DisplayName@TargetedContentUnifiedTile@UnifiedTile@Shell@WindowsInternal@@UEAAJPEAPEAUHSTRING__@@@Z; WindowsInternal::Shell::UnifiedTile::TargetedContentUnifiedTile::get_DisplayName(HSTRING__ * *)
0x1802fefab  mov     ebx, eax
0x1802fefad  test    eax, eax
0x1802fefaf  jns     short loc_1802FEFFD
0x1802fefb1  mov     rcx, [rsp+98h]; this
0x1802fefb9  mov     r9d, eax; char *
0x1802fefbc  lea     r8, aShellcommonShe_168; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1802fefc3  mov     edx, 128h; void *
0x1802fefc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802fefcd  nop
0x1802fefce  mov     rcx, [rsp+98h+string]; string
0x1802fefd6  call    cs:__imp_WindowsDeleteString
0x1802fefdc  nop
0x1802fefdd  mov     rcx, [rsp+98h+arg_8]; string
0x1802fefe5  call    cs:__imp_WindowsDeleteString
0x1802fefeb  nop
0x1802fefec  lea     rcx, [rsp+98h+var_68]; this
0x1802feff1  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1802feff6  mov     eax, ebx
0x1802feff8  jmp     loc_1802FF0DD
0x1802feffd  mov     [rsp+98h+arg_10], 0
0x1802ff009  mov     rdi, [rdi+58h]
0x1802ff00d  mov     rax, [rdi]
0x1802ff010  mov     rbx, [rax+30h]
0x1802ff014  lea     rcx, [rsp+98h+arg_10]
0x1802ff01c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802ff021  lea     r9, [rsp+98h+arg_10]
0x1802ff029  lea     r8, _GUID_461218a4_e7b8_4c32_bdb8_7421111d6c4a
0x1802ff030  lea     rdx, c_MRTTransformerId
0x1802ff037  mov     rcx, rdi
0x1802ff03a  mov     rax, rbx
0x1802ff03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802ff042  mov     rdi, [rsp+98h+arg_8]
0x1802ff04a  test    al, al
0x1802ff04c  jz      short loc_1802FF099
0x1802ff04e  mov     rcx, [rsp+98h+arg_10]
0x1802ff056  mov     rax, [rcx]
0x1802ff059  mov     rbx, [rsp+98h+string]
0x1802ff061  mov     r9, rbx
0x1802ff064  mov     r8, rdi
0x1802ff067  lea     rdx, [rsp+98h+arg_18]
0x1802ff06f  mov     rax, [rax+28h]
0x1802ff073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802ff078  mov     rax, [rsp+98h+arg_18]
0x1802ff080  mov     [rsp+98h+arg_18], 0
0x1802ff08c  mov     [rsi], rax
0x1802ff08f  xor     ecx, ecx; string
0x1802ff091  call    cs:__imp_WindowsDeleteString
0x1802ff097  jmp     short loc_1802FF0A6
0x1802ff099  mov     rax, [rsp+98h+string]
0x1802ff0a1  xor     ebx, ebx
0x1802ff0a3  mov     [rsi], rax
0x1802ff0a6  lea     rcx, [rsp+98h+arg_10]
0x1802ff0ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802ff0b3  nop
0x1802ff0b4  mov     rcx, rbx; string
0x1802ff0b7  call    cs:__imp_WindowsDeleteString
0x1802ff0bd  nop
0x1802ff0be  mov     rcx, rdi; string
0x1802ff0c1  call    cs:__imp_WindowsDeleteString
0x1802ff0c7  nop
0x1802ff0c8  lea     rcx, [rsp+98h+var_68]; this
0x1802ff0cd  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1802ff0d2  xor     eax, eax
0x1802ff0d4  jmp     short loc_1802FF0DD
0x1802ff0d6  mov     eax, dword ptr [rsp+98h+string]
0x1802ff0dd  add     rsp, 80h
0x1802ff0e4  pop     rdi
0x1802ff0e5  pop     rsi
0x1802ff0e6  pop     rbx
0x1802ff0e7  retn
```
