# WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTile::get_SortName(HSTRING__ * *)

- ea: `0x1800f3960`
- end: `0x1800f3b8a`
- name: `?get_SortName@PackagedUnifiedTile@UnifiedTile@Shell@WindowsInternal@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTile *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18001f0a0`
- `0x180020474`
- `0x180022100`
- `0x1800222ec`
- `0x1800f3960`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f398c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f39c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3a86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3ab6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3ac0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3b03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3b12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3b4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f398c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f39c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3a86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3ab6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3ac0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3b03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3b12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3b4c`

## string_xrefs

- `0x1800f3ae9`: `shellcommon\shell\tiles\unifiedtilemodel\lib\packagedunifiedtile.cpp`
- `0x1800f3b32`: `shellcommon\shell\tiles\unifiedtilemodel\lib\packagedunifiedtile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTile::get_SortName(
        WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTile *this,
        HSTRING *a2)
{
  int StringProperty; // eax
  unsigned int v5; // ebx
  int DisplayName; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, const struct _GUID *, GUID *, __int64 *); // rbx
  char v10; // al
  HSTRING v11; // rdi
  HSTRING v12; // rbx
  HSTRING v13; // rax
  __int64 v14; // rcx
  const char *v15; // r9
  __int64 result; // rax
  HSTRING v17; // rax
  int v18; // [rsp+20h] [rbp-78h]
  _BYTE v19[104]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  HSTRING string; // [rsp+A0h] [rbp+8h] BYREF
  HSTRING v22; // [rsp+A8h] [rbp+10h]
  __int64 v23; // [rsp+B0h] [rbp+18h] BYREF
  HSTRING v24; // [rsp+B8h] [rbp+20h] BYREF

  UnifiedTileTelemetry::WatchCurrentThread(v19, "PackagedUnifiedTile_get_SortName");
  *a2 = 0;
  WindowsDeleteString(0);
  v22 = 0;
  try
  {
    StringProperty = WindowsInternal::Shell::UnifiedTile::GetStringProperty();
    v5 = StringProperty;
    if ( StringProperty < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B7,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\packagedunifiedtile.cpp",
        (const char *)(unsigned int)StringProperty,
        v18);
      WindowsDeleteString(v22);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v19);
      result = v5;
    }
    else
    {
      WindowsDeleteString(0);
      string = 0;
      DisplayName = WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTile::get_DisplayName(this, &string);
      v7 = DisplayName;
      if ( DisplayName < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1BA,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\packagedunifiedtile.cpp",
          (const char *)(unsigned int)DisplayName,
          v18);
        WindowsDeleteString(string);
        WindowsDeleteString(v22);
        wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v19);
        result = v7;
      }
      else
      {
        v23 = 0;
        v8 = *((_QWORD *)this + 14);
        v9 = *(__int64 (__fastcall **)(__int64, const struct _GUID *, GUID *, __int64 *))(*(_QWORD *)v8 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
        v10 = v9(v8, &c_MRTTransformerId, &GUID_461218a4_e7b8_4c32_bdb8_7421111d6c4a, &v23);
        v11 = v22;
        if ( v10 )
        {
          v12 = string;
          (*(void (__fastcall **)(__int64, HSTRING *, HSTRING, HSTRING))(*(_QWORD *)v23 + 40LL))(v23, &v24, v22, string);
          v13 = v24;
          v24 = 0;
          *a2 = v13;
          WindowsDeleteString(0);
        }
        else
        {
          v17 = string;
          v12 = 0;
          string = 0;
          *a2 = v17;
        }
        v14 = v23;
        if ( v23 )
        {
          v23 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        WindowsDeleteString(v12);
        WindowsDeleteString(v11);
        wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v19);
        result = 0;
      }
    }
  }
  catch ( ... )
  {
    LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x1CA,
                        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\packagedunifiedtile.cpp",
                        v15);
    return (unsigned int)string;
  }
  return result;
}

```

## disassembly

```asm
0x1800f3960  push    rbx
0x1800f3962  push    rsi
0x1800f3963  push    rdi
0x1800f3964  sub     rsp, 80h
0x1800f396b  mov     rsi, rdx
0x1800f396e  mov     rdi, rcx
0x1800f3971  lea     rdx, aPackagedunifie_23; "PackagedUnifiedTile_get_SortName"
0x1800f3978  lea     rcx, [rsp+98h+var_68]
0x1800f397d  call    ?WatchCurrentThread@UnifiedTileTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; UnifiedTileTelemetry::WatchCurrentThread(char const *)
0x1800f3982  nop
0x1800f3983  mov     qword ptr [rsi], 0
0x1800f398a  xor     ecx, ecx; string
0x1800f398c  call    cs:__imp_WindowsDeleteString
0x1800f3992  mov     [rsp+98h+arg_8], 0
0x1800f399e  lea     r8, [rsp+98h+arg_8]
0x1800f39a6  lea     rdx, ?PhoneticName@TileStoreProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; DataStoreCache::DataStoreProperty<HSTRING__ *> const DataStoreCache::TileStoreProperties::PhoneticName
0x1800f39ad  mov     rcx, [rdi+70h]
0x1800f39b1  call    ?GetStringProperty@UnifiedTile@Shell@WindowsInternal@@YAJPEAUIDataItem@DataStoreCache@@AEBU?$DataStoreProperty@PEAUHSTRING__@@@5@PEAPEAUHSTRING__@@@Z; WindowsInternal::Shell::UnifiedTile::GetStringProperty(DataStoreCache::IDataItem *,DataStoreCache::DataStoreProperty<HSTRING__ *> const &,HSTRING__ * *)
0x1800f39b6  mov     ebx, eax
0x1800f39b8  test    eax, eax
0x1800f39ba  js      loc_1800F3B27
0x1800f39c0  xor     ecx, ecx; string
0x1800f39c2  call    cs:__imp_WindowsDeleteString
0x1800f39c8  mov     [rsp+98h+string], 0
0x1800f39d4  lea     rdx, [rsp+98h+string]; HSTRING *
0x1800f39dc  mov     rcx, rdi; this
0x1800f39df  call    ?get_DisplayName@PackagedUnifiedTile@UnifiedTile@Shell@WindowsInternal@@UEAAJPEAPEAUHSTRING__@@@Z; WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTile::get_DisplayName(HSTRING__ * *)
0x1800f39e4  mov     ebx, eax
0x1800f39e6  test    eax, eax
0x1800f39e8  js      loc_1800F3ADE
0x1800f39ee  mov     [rsp+98h+arg_10], 0
0x1800f39fa  mov     rdi, [rdi+70h]
0x1800f39fe  mov     rax, [rdi]
0x1800f3a01  mov     rbx, [rax+30h]
0x1800f3a05  lea     rcx, [rsp+98h+arg_10]
0x1800f3a0d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f3a12  lea     r9, [rsp+98h+arg_10]
0x1800f3a1a  lea     r8, _GUID_461218a4_e7b8_4c32_bdb8_7421111d6c4a
0x1800f3a21  lea     rdx, c_MRTTransformerId
0x1800f3a28  mov     rcx, rdi
0x1800f3a2b  mov     rax, rbx
0x1800f3a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3a33  mov     rdi, [rsp+98h+arg_8]
0x1800f3a3b  test    al, al
0x1800f3a3d  jz      loc_1800F3B64
0x1800f3a43  mov     rcx, [rsp+98h+arg_10]
0x1800f3a4b  mov     rax, [rcx]
0x1800f3a4e  mov     rbx, [rsp+98h+string]
0x1800f3a56  mov     r9, rbx
0x1800f3a59  mov     r8, rdi
0x1800f3a5c  lea     rdx, [rsp+98h+arg_18]
0x1800f3a64  mov     rax, [rax+28h]
0x1800f3a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3a6d  mov     rax, [rsp+98h+arg_18]
0x1800f3a75  mov     [rsp+98h+arg_18], 0
0x1800f3a81  mov     [rsi], rax
0x1800f3a84  xor     ecx, ecx; string
0x1800f3a86  call    cs:__imp_WindowsDeleteString
0x1800f3a8c  nop
0x1800f3a8d  mov     rcx, [rsp+98h+arg_10]
0x1800f3a95  test    rcx, rcx
0x1800f3a98  jz      short loc_1800F3AB3
0x1800f3a9a  mov     [rsp+98h+arg_10], 0
0x1800f3aa6  mov     rax, [rcx]
0x1800f3aa9  mov     rax, [rax+10h]
0x1800f3aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3ab2  nop
0x1800f3ab3  mov     rcx, rbx; string
0x1800f3ab6  call    cs:__imp_WindowsDeleteString
0x1800f3abc  nop
0x1800f3abd  mov     rcx, rdi; string
0x1800f3ac0  call    cs:__imp_WindowsDeleteString
0x1800f3ac6  nop
0x1800f3ac7  lea     rcx, [rsp+98h+var_68]; this
0x1800f3acc  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800f3ad1  xor     eax, eax
0x1800f3ad3  add     rsp, 80h
0x1800f3ada  pop     rdi
0x1800f3adb  pop     rsi
0x1800f3adc  pop     rbx
0x1800f3add  retn
0x1800f3ade  mov     rcx, [rsp+98h]; this
0x1800f3ae6  mov     r9d, ebx; char *
0x1800f3ae9  lea     r8, aShellcommonShe_229; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1800f3af0  mov     edx, 1BAh; void *
0x1800f3af5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f3afa  nop
0x1800f3afb  mov     rcx, [rsp+98h+string]; string
0x1800f3b03  call    cs:__imp_WindowsDeleteString
0x1800f3b09  nop
0x1800f3b0a  mov     rcx, [rsp+98h+arg_8]; string
0x1800f3b12  call    cs:__imp_WindowsDeleteString
0x1800f3b18  nop
0x1800f3b19  lea     rcx, [rsp+98h+var_68]; this
0x1800f3b1e  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800f3b23  mov     eax, ebx
0x1800f3b25  jmp     short loc_1800F3AD3
0x1800f3b27  mov     rcx, [rsp+98h]; this
0x1800f3b2f  mov     r9d, ebx; char *
0x1800f3b32  lea     r8, aShellcommonShe_229; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1800f3b39  mov     edx, 1B7h; void *
0x1800f3b3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f3b43  nop
0x1800f3b44  mov     rcx, [rsp+98h+arg_8]; string
0x1800f3b4c  call    cs:__imp_WindowsDeleteString
0x1800f3b52  nop
0x1800f3b53  lea     rcx, [rsp+98h+var_68]; this
0x1800f3b58  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800f3b5d  mov     eax, ebx
0x1800f3b5f  jmp     loc_1800F3AD3
0x1800f3b64  mov     rax, [rsp+98h+string]
0x1800f3b6c  xor     ebx, ebx
0x1800f3b6e  mov     [rsp+98h+string], rbx
0x1800f3b76  mov     [rsi], rax
0x1800f3b79  jmp     loc_1800F3A8D
0x1800f3b7e  mov     eax, dword ptr [rsp+98h+string]
0x1800f3b85  jmp     loc_1800F3AD3
```
