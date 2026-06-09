# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionInitializationBackgroundTask::InstallAppsIfNecessary(Windows::ApplicationModel::Background::IBackgroundTaskInstance *,PlaceholderTileTaskType,DataStoreCache::PlaceholderTileTransformer::InstallDelayType *)

- ea: `0x180191d9c`
- end: `0x180191ffa`
- name: `?InstallAppsIfNecessary@CollectionInitializationBackgroundTask@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@AEAAXPEAUIBackgroundTaskInstance@Background@ApplicationModel@Windows@@W4PlaceholderTileTaskType@@PEAW4InstallDelayType@PlaceholderTileTransformer@DataStoreCache@@@Z`
- size: `606`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180175950`

## callees

- `0x18001ac50`
- `0x18001dac0`
- `0x18002dde0`
- `0x18003b500`
- `0x180191d9c`
- `0x180192000`
- `0x1801920a4`
- `0x180192bac`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180191ebd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180191eef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180191f22`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180191ebd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180191eef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180191f22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180191e60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180191f57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180191e60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180191f57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180191ea0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180191ed5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180191f08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180191ea0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180191ed5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180191f08`

## string_xrefs

- `0x180191e01`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\collectioninitializationbackgroundtask.cpp`
- `0x180191e39`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\collectioninitializationbackgroundtask.cpp`
- `0x180191e88`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\collectioninitializationbackgroundtask.cpp`
- `0x180191f3f`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\collectioninitializationbackgroundtask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionInitializationBackgroundTask::InstallAppsIfNecessary(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        _DWORD *a4)
{
  _QWORD *v5; // r9
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v13; // rax
  const WCHAR *v14; // rax
  __int64 v15; // rax
  __int64 (__fastcall ***v16)(_QWORD, _BYTE *, _QWORD); // rdi
  std::_Ref_count_base *v17; // rbx
  __int64 v18; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-39h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-39h]
  _QWORD v21[2]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v22[8]; // [rsp+40h] [rbp-19h] BYREF
  std::_Ref_count_base *v23; // [rsp+48h] [rbp-11h]
  _BYTE v24[96]; // [rsp+50h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  HSTRING string; // [rsp+D8h] [rbp+7Fh] BYREF

  v5 = a2;
  *a4 = 1;
  if ( (_DWORD)a3 != 2 )
  {
    if ( (_DWORD)a3 == 4 )
    {
      *a4 = 6;
    }
    else if ( (_DWORD)a3 == 3 )
    {
      *a4 = 5;
    }
    else
    {
      if ( (_DWORD)a3 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x95,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\"
                        "collectioninitializationbackgroundtask.cpp",
          (const char *)0x80070057LL,
          bIgnoreCase);
      v7 = *a2;
      v21[0] = 0;
      v8 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))(v7 + 56))(a2, v21);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x98,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\"
                        "collectioninitializationbackgroundtask.cpp",
          (const char *)(unsigned int)v8,
          bIgnoreCase);
      string = 0;
      v9 = v21[0];
      v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v21[0] + 56LL);
      WindowsDeleteString(0);
      string = 0;
      v11 = v10(v9, &string);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x9B,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\"
                        "collectioninitializationbackgroundtask.cpp",
          (const char *)(unsigned int)v11,
          bIgnoreCase);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(L"Placeholder tile fast delay initialization", -1, StringRawBuffer, -1, 1) == 2 )
      {
        *a4 = 2;
      }
      else
      {
        v13 = WindowsGetStringRawBuffer(string, 0);
        if ( CompareStringOrdinal(L"Placeholder tile medium delay initialization", -1, v13, -1, 1) == 2 )
        {
          *a4 = 3;
        }
        else
        {
          v14 = WindowsGetStringRawBuffer(string, 0);
          if ( CompareStringOrdinal(L"Placeholder tile long delay initialization", -1, v14, -1, 1) == 2 )
          {
            *a4 = 4;
          }
          else
          {
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0xAB,
              (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\l"
                            "ib\\collectioninitializationbackgroundtask.cpp",
              (const char *)0x8000FFFFLL,
              bIgnoreCasea);
            *a4 = 1;
          }
        }
      }
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v21);
    }
  }
  v15 = std::make_shared<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderInstallerInternal,std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionContext> const &>(
          v22,
          a1 + 112,
          a3,
          v5);
  v16 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *, _QWORD))v15;
  v21[0] = *(_QWORD *)v15;
  v17 = *(std::_Ref_count_base **)(v15 + 8);
  v21[1] = v17;
  *(_QWORD *)v15 = 0;
  *(_QWORD *)(v15 + 8) = 0;
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  v18 = (**v16)(v16, v24, (unsigned int)*a4);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::operator=(
    a1 + 128,
    v18);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v24);
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
}

```

## disassembly

```asm
0x180191d9c  mov     [rsp-8+arg_0], rbx
0x180191da1  push    rbp
0x180191da2  push    rsi
0x180191da3  push    rdi
0x180191da4  push    r13
0x180191da6  push    r14
0x180191da8  lea     rbp, [rsp-37h]
0x180191dad  sub     rsp, 90h
0x180191db4  mov     rsi, r9
0x180191db7  mov     r9, rdx
0x180191dba  mov     r14, rcx
0x180191dbd  mov     r13d, 1
0x180191dc3  mov     [rsi], r13d
0x180191dc6  cmp     r8d, 2
0x180191dca  jz      loc_180191F6E
0x180191dd0  cmp     r8d, 4
0x180191dd4  jnz     short loc_180191DE1
0x180191dd6  mov     dword ptr [rsi], 6
0x180191ddc  jmp     loc_180191F6E
0x180191de1  cmp     r8d, 3
0x180191de5  jnz     short loc_180191DF2
0x180191de7  mov     dword ptr [rsi], 5
0x180191ded  jmp     loc_180191F6E
0x180191df2  mov     rcx, [rbp+5Fh]; this
0x180191df6  test    r8d, r8d
0x180191df9  jz      short loc_180191E13
0x180191dfb  mov     r9d, 80070057h; char *
0x180191e01  lea     r8, aShellcommonShe_149; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180191e08  mov     edx, 95h; void *
0x180191e0d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180191e13  mov     rax, [rdx]
0x180191e16  mov     [rbp+57h+var_80], 0
0x180191e1e  lea     rdx, [rbp+57h+var_80]
0x180191e22  mov     rcx, r9
0x180191e25  mov     rax, [rax+38h]
0x180191e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180191e2e  mov     rcx, [rbp+5Fh]; this
0x180191e32  test    eax, eax
0x180191e34  jns     short loc_180191E4B
0x180191e36  mov     r9d, eax; char *
0x180191e39  lea     r8, aShellcommonShe_149; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180191e40  mov     edx, 98h; void *
0x180191e45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180191e4b  mov     [rbp+57h+string], 0
0x180191e53  mov     rdi, [rbp+57h+var_80]
0x180191e57  mov     rax, [rdi]
0x180191e5a  mov     rbx, [rax+38h]
0x180191e5e  xor     ecx, ecx; string
0x180191e60  call    cs:__imp_WindowsDeleteString
0x180191e66  mov     [rbp+57h+string], 0
0x180191e6e  lea     rdx, [rbp+57h+string]
0x180191e72  mov     rcx, rdi
0x180191e75  mov     rax, rbx
0x180191e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180191e7d  mov     rcx, [rbp+5Fh]; this
0x180191e81  test    eax, eax
0x180191e83  jns     short loc_180191E9A
0x180191e85  mov     r9d, eax; char *
0x180191e88  lea     r8, aShellcommonShe_149; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180191e8f  mov     edx, 9Bh; void *
0x180191e94  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180191e9a  xor     edx, edx; length
0x180191e9c  mov     rcx, [rbp+57h+string]; string
0x180191ea0  call    cs:__imp_WindowsGetStringRawBuffer
0x180191ea6  mov     [rsp+0B0h+bIgnoreCase], r13d; bIgnoreCase
0x180191eab  or      ebx, 0FFFFFFFFh
0x180191eae  mov     r9d, ebx; cchCount2
0x180191eb1  mov     r8, rax; lpString2
0x180191eb4  mov     edx, ebx; cchCount1
0x180191eb6  lea     rcx, aPlaceholderTil; "Placeholder tile fast delay initializat"...
0x180191ebd  call    cs:__imp_CompareStringOrdinal
0x180191ec3  cmp     eax, 2
0x180191ec6  jnz     short loc_180191ECF
0x180191ec8  mov     [rsi], eax
0x180191eca  jmp     loc_180191F53
0x180191ecf  xor     edx, edx; length
0x180191ed1  mov     rcx, [rbp+57h+string]; string
0x180191ed5  call    cs:__imp_WindowsGetStringRawBuffer
0x180191edb  mov     [rsp+0B0h+bIgnoreCase], r13d; bIgnoreCase
0x180191ee0  mov     r9d, ebx; cchCount2
0x180191ee3  mov     r8, rax; lpString2
0x180191ee6  mov     edx, ebx; cchCount1
0x180191ee8  lea     rcx, aPlaceholderTil_2; "Placeholder tile medium delay initializ"...
0x180191eef  call    cs:__imp_CompareStringOrdinal
0x180191ef5  cmp     eax, 2
0x180191ef8  jnz     short loc_180191F02
0x180191efa  mov     dword ptr [rsi], 3
0x180191f00  jmp     short loc_180191F53
0x180191f02  xor     edx, edx; length
0x180191f04  mov     rcx, [rbp+57h+string]; string
0x180191f08  call    cs:__imp_WindowsGetStringRawBuffer
0x180191f0e  mov     [rsp+0B0h+bIgnoreCase], r13d; int
0x180191f13  mov     r9d, ebx; cchCount2
0x180191f16  mov     r8, rax; lpString2
0x180191f19  mov     edx, ebx; cchCount1
0x180191f1b  lea     rcx, aPlaceholderTil_1; "Placeholder tile long delay initializat"...
0x180191f22  call    cs:__imp_CompareStringOrdinal
0x180191f28  cmp     eax, 2
0x180191f2b  jnz     short loc_180191F35
0x180191f2d  mov     dword ptr [rsi], 4
0x180191f33  jmp     short loc_180191F53
0x180191f35  mov     rcx, [rbp+5Fh]; this
0x180191f39  mov     r9d, 8000FFFFh; char *
0x180191f3f  lea     r8, aShellcommonShe_149; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180191f46  mov     edx, 0ABh; void *
0x180191f4b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180191f50  mov     [rsi], r13d
0x180191f53  mov     rcx, [rbp+57h+string]; string
0x180191f57  call    cs:__imp_WindowsDeleteString
0x180191f5d  mov     [rbp+57h+string], 0
0x180191f65  lea     rcx, [rbp+57h+var_80]; void *
0x180191f69  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180191f6e  lea     rdx, [r14+70h]
0x180191f72  lea     rcx, [rbp+57h+var_70]
0x180191f76  call    ??$make_shared@VPlaceholderInstallerInternal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@AEBV?$shared_ptr@UCollectionContext@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@std@@YA?AV?$shared_ptr@VPlaceholderInstallerInternal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@0@AEBV?$shared_ptr@UCollectionContext@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@0@@Z; std::make_shared<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderInstallerInternal,std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionContext> const &>(std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionContext> const &)
0x180191f7b  mov     rdi, [rax]
0x180191f7e  mov     [rbp+57h+var_80], rdi
0x180191f82  mov     rbx, [rax+8]
0x180191f86  mov     [rbp+57h+var_78], rbx
0x180191f8a  mov     qword ptr [rax], 0
0x180191f91  mov     qword ptr [rax+8], 0
0x180191f99  mov     rcx, [rbp+57h+var_68]; this
0x180191f9d  test    rcx, rcx
0x180191fa0  jz      short loc_180191FA8
0x180191fa2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180191fa7  nop
0x180191fa8  mov     rax, [rdi]
0x180191fab  mov     r8d, [rsi]
0x180191fae  lea     rdx, [rbp+57h+var_60]
0x180191fb2  mov     rcx, rdi
0x180191fb5  mov     rax, [rax]
0x180191fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180191fbd  lea     rcx, [r14+80h]
0x180191fc4  mov     rdx, rax
0x180191fc7  call    ??4?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::operator=(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>> &&)
0x180191fcc  lea     rcx, [rbp+57h+var_60]
0x180191fd0  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180191fd5  nop
0x180191fd6  test    rbx, rbx
0x180191fd9  jz      short loc_180191FE3
0x180191fdb  mov     rcx, rbx; this
0x180191fde  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180191fe3  mov     rbx, [rsp+0B0h+arg_0]
0x180191feb  add     rsp, 90h
0x180191ff2  pop     r14
0x180191ff4  pop     r13
0x180191ff6  pop     rdi
0x180191ff7  pop     rsi
0x180191ff8  pop     rbp
0x180191ff9  retn
```
