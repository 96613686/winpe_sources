# _wWinMain_::_22_::_lambda_1_::operator()

- ea: `0x1400249a4`
- end: `0x140024bd3`
- name: `_wWinMain_::_22_::_lambda_1_::operator()`
- size: `559`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400230ec`
- `0x1400295c4`

## callees

- `0x1400220b4`
- `0x140022afc`
- `0x1400249a4`
- `0x140040184`
- `0x140040364`
- `0x14004045c`
- `0x1400433b0`
- `0x140045404`
- `0x140057920`
- `0x1400730a4`
- `0x1400831b4`
- `0x14037b4b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024a25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024ac1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024a25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024ac1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140024a01`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140024aa3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140024a01`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140024aa3`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140024a6c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140024a6c`

## string_xrefs

- `0x140024b96`: `Update manager did not respond to stop`
- `0x140024b4e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140024b60`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140024b72`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140024b84`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140024bc1`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall wWinMain_::_22_::_lambda_1_::operator()(__int64 a1)
{
  bool updated; // si
  const char *v2; // r9
  const char *v3; // r9
  HANDLE v4; // rbx
  __int64 v5; // rax
  HANDLE v6; // rax
  __int64 v7; // rdx
  char v8; // di
  const char *v9; // r9
  const char *v10; // r9
  __int16 *traits_1_unsigned_char; // rax
  const char *v12; // r9
  __int64 v13; // r11
  signed __int64 v14; // rax
  __int64 result; // rax
  HANDLE hEvent; // [rsp+28h] [rbp-60h] BYREF
  _QWORD v17[2]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v19[40]; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v17[0] = a1;
  updated = UpdateManager::ShutdownUpdateManagerIfRunning();
  if ( g_usoSvcSupportsPrivateNamespaces )
  {
    hEvent = 0;
    Windows::PrivateNamespaceHelpers::TryOpenPrivateNamespaceEvent(&hEvent, L"\\UsoCoreWorkerExiting");
    if ( hEvent )
    {
      if ( !SetEvent(hEvent) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9C7,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v2);
      if ( hEvent && !CloseHandle(hEvent) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9D1,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v3);
    }
  }
  else
  {
    v4 = 0;
    hEvent = 0;
    v5 = GlobalObjectName(v19, L"\\UsoCoreWorkerExiting");
    if ( *(_QWORD *)(v5 + 24) > 7u )
      v5 = *(_QWORD *)v5;
    v6 = OpenEventW(0x100002u, 0, (LPCWSTR)v5);
    if ( v6 )
    {
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        &hEvent,
        v6);
      v8 = 1;
      v4 = hEvent;
    }
    else
    {
      v8 = 0;
    }
    std::wstring::~wstring(v19, v7);
    if ( v8 && !SetEvent(v4) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9C7,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v9);
    if ( v4 && !CloseHandle(v4) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9D1,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
  }
  traits_1_unsigned_char = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                                        "1507.2603.28012.0",
                                        word_1403BDC42,
                                        0);
  if ( traits_1_unsigned_char == word_1403BDC42
    || (v14 = (char *)traits_1_unsigned_char - "1507.2603.28012.0", v14 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v12);
  }
  v17[0] = "1507.2603.28012.0";
  v17[1] = v14;
  result = Windows::Telemetry::Worker::MoUsoCoreWorkerRunning::Stop(v13, v17);
  if ( !updated )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Update manager did not respond to stop");
    throw (std::runtime_error *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x1400249a4  mov     [rsp+arg_8], rbx
0x1400249a9  mov     [rsp+arg_10], rsi
0x1400249ae  mov     [rsp+arg_18], rdi
0x1400249b3  push    r14
0x1400249b5  sub     rsp, 80h
0x1400249bc  mov     r14, rcx
0x1400249bf  mov     [rsp+88h+var_58], rcx
0x1400249c4  call    ?ShutdownUpdateManagerIfRunning@UpdateManager@@SA_NXZ; UpdateManager::ShutdownUpdateManagerIfRunning(void)
0x1400249c9  mov     sil, al
0x1400249cc  mov     [rsp+88h+var_68], al
0x1400249d0  cmp     cs:?g_usoSvcSupportsPrivateNamespaces@@3_NA, 0; bool g_usoSvcSupportsPrivateNamespaces
0x1400249d7  jz      short loc_140024A40
0x1400249d9  mov     [rsp+88h+hEvent], 0
0x1400249e2  lea     rdx, aUsocoreworkere; "\\UsoCoreWorkerExiting"
0x1400249e9  lea     rcx, [rsp+88h+hEvent]
0x1400249ee  call    ?TryOpenPrivateNamespaceEvent@PrivateNamespaceHelpers@Windows@@YA?AV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@PEB_WK_N@Z
0x1400249f3  mov     rcx, [rsp+88h+hEvent]; hEvent
0x1400249f8  test    rcx, rcx
0x1400249fb  jz      loc_140024AD7
0x140024a01  call    cs:__imp_SetEvent
0x140024a07  mov     rcx, [rsp+88h]; this
0x140024a0f  test    eax, eax
0x140024a11  jz      loc_140024B4E
0x140024a17  mov     rcx, [rsp+88h+hEvent]; hObject
0x140024a1c  test    rcx, rcx
0x140024a1f  jz      loc_140024AD7
0x140024a25  call    cs:__imp_CloseHandle
0x140024a2b  mov     rcx, [rsp+88h]; this
0x140024a33  test    eax, eax
0x140024a35  jz      loc_140024B60
0x140024a3b  jmp     loc_140024AD7
0x140024a40  xor     ebx, ebx
0x140024a42  mov     [rsp+88h+hEvent], rbx
0x140024a47  lea     rdx, aUsocoreworkere; "\\UsoCoreWorkerExiting"
0x140024a4e  lea     rcx, [rsp+88h+var_30]; void *
0x140024a53  call    ?GlobalObjectName@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; GlobalObjectName(wchar_t const *)
0x140024a58  cmp     qword ptr [rax+18h], 7
0x140024a5d  jbe     short loc_140024A62
0x140024a5f  mov     rax, [rax]
0x140024a62  mov     r8, rax; lpName
0x140024a65  xor     edx, edx; bInheritHandle
0x140024a67  mov     ecx, 100002h; dwDesiredAccess
0x140024a6c  call    cs:__imp_OpenEventW
0x140024a72  test    rax, rax
0x140024a75  jnz     short loc_140024A7C
0x140024a77  xor     dil, dil
0x140024a7a  jmp     short loc_140024A91
0x140024a7c  mov     rdx, rax
0x140024a7f  lea     rcx, [rsp+88h+hEvent]
0x140024a84  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140024a89  mov     dil, 1
0x140024a8c  mov     rbx, [rsp+88h+hEvent]
0x140024a91  lea     rcx, [rsp+88h+var_30]
0x140024a96  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024a9b  test    dil, dil
0x140024a9e  jz      short loc_140024AB9
0x140024aa0  mov     rcx, rbx; hEvent
0x140024aa3  call    cs:__imp_SetEvent
0x140024aa9  mov     rcx, [rsp+88h]; this
0x140024ab1  test    eax, eax
0x140024ab3  jz      loc_140024B72
0x140024ab9  test    rbx, rbx
0x140024abc  jz      short loc_140024AD7
0x140024abe  mov     rcx, rbx; hObject
0x140024ac1  call    cs:__imp_CloseHandle
0x140024ac7  mov     rcx, [rsp+88h]; this
0x140024acf  test    eax, eax
0x140024ad1  jz      loc_140024B84
0x140024ad7  jmp     short loc_140024AE3
0x140024ad9  mov     sil, [rsp+88h+var_68]
0x140024ade  mov     r14, [rsp+88h+var_58]
0x140024ae3  mov     r11, [r14]
0x140024ae6  xor     r8d, r8d
0x140024ae9  lea     rbx, word_1403BDC42
0x140024af0  mov     rdx, rbx
0x140024af3  lea     rdi, a15072603280120; "1507.2603.28012.0"
0x140024afa  mov     rcx, rdi
0x140024afd  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x140024b02  cmp     rax, rbx
0x140024b05  jz      loc_140024BB9
0x140024b0b  sub     rax, rdi
0x140024b0e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140024b12  jz      loc_140024BB9
0x140024b18  mov     [rsp+88h+var_58], rdi
0x140024b1d  mov     [rsp+88h+var_50], rax
0x140024b22  lea     rdx, [rsp+88h+var_58]
0x140024b27  mov     rcx, r11
0x140024b2a  call    ?Stop@MoUsoCoreWorkerRunning@Worker@Telemetry@Windows@@QEAAXV?$basic_zstring_view@D@wil@@@Z; Windows::Telemetry::Worker::MoUsoCoreWorkerRunning::Stop(wil::basic_zstring_view<char>)
0x140024b2f  test    sil, sil
0x140024b32  jz      short loc_140024B96
0x140024b34  lea     r11, [rsp+88h+var_8]
0x140024b3c  mov     rbx, [r11+18h]
0x140024b40  mov     rsi, [r11+20h]
0x140024b44  mov     rdi, [r11+28h]
0x140024b48  mov     rsp, r11
0x140024b4b  pop     r14
0x140024b4d  retn
0x140024b4e  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140024b55  mov     edx, 9C7h; void *
0x140024b5a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140024b60  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140024b67  mov     edx, 9D1h; void *
0x140024b6c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140024b72  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140024b79  mov     edx, 9C7h; void *
0x140024b7e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140024b84  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140024b8b  mov     edx, 9D1h; void *
0x140024b90  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140024b96  lea     rdx, aUpdateManagerD; "Update manager did not respond to stop"
0x140024b9d  lea     rcx, [rsp+88h+pExceptionObject]; this
0x140024ba2  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x140024ba7  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x140024bae  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x140024bb3  call    _CxxThrowException
0x140024bb9  mov     rcx, [rsp+88h]; this
0x140024bc1  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140024bc8  mov     edx, 0C9h; void *
0x140024bcd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
