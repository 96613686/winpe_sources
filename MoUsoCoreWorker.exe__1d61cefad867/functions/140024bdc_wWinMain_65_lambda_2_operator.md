# _wWinMain_::_65_::_lambda_2_::operator()

- ea: `0x140024bdc`
- end: `0x140024d93`
- name: `_wWinMain_::_65_::_lambda_2_::operator()`
- size: `439`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400230ec`
- `0x140028ff0`

## callees

- `0x140022afc`
- `0x140024bdc`
- `0x14002a6ac`
- `0x140040364`
- `0x14004045c`
- `0x1400433b0`
- `0x140045404`
- `0x1400730a4`
- `0x1400831b4`
- `0x14037b4b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024c57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024ce9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024c57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024ce9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140024c36`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140024cd2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140024c36`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140024cd2`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140024c9b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140024c9b`

## string_xrefs

- `0x140024d70`: `Update manager did not respond to stop`
- `0x140024d28`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140024d3a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140024d4c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140024d5e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall wWinMain_::_65_::_lambda_2_::operator()(_QWORD *a1)
{
  bool updated; // si
  const char *v3; // r9
  const char *v4; // r9
  HANDLE v5; // rbx
  __int64 v6; // rax
  HANDLE v7; // rax
  __int64 v8; // rdx
  char v9; // r14
  const char *v10; // r9
  const char *v11; // r9
  __int64 result; // rax
  HANDLE hEvent[2]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  hEvent[1] = a1;
  updated = UpdateManager::ShutdownUpdateManagerIfRunning();
  if ( g_usoSvcSupportsPrivateNamespaces )
  {
    hEvent[0] = 0;
    Windows::PrivateNamespaceHelpers::TryOpenPrivateNamespaceEvent(hEvent, L"\\UsoCoreWorkerExiting");
    if ( hEvent[0] )
    {
      if ( !SetEvent(hEvent[0]) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9C7,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v3);
      if ( hEvent[0] && !CloseHandle(hEvent[0]) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9D1,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v4);
    }
  }
  else
  {
    v5 = 0;
    hEvent[0] = 0;
    v6 = GlobalObjectName(v15, L"\\UsoCoreWorkerExiting");
    if ( *(_QWORD *)(v6 + 24) > 7u )
      v6 = *(_QWORD *)v6;
    v7 = OpenEventW(0x100002u, 0, (LPCWSTR)v6);
    if ( v7 )
    {
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        hEvent,
        v7);
      v9 = 1;
      v5 = hEvent[0];
    }
    else
    {
      v9 = 0;
    }
    std::wstring::~wstring(v15, v8);
    if ( v9 && !SetEvent(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9C7,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    if ( v5 && !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9D1,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v11);
  }
  result = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(*a1);
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
0x140024bdc  mov     [rsp+arg_8], rbx
0x140024be1  mov     [rsp+arg_10], rsi
0x140024be6  mov     [rsp+arg_18], rdi
0x140024beb  push    r14
0x140024bed  sub     rsp, 70h
0x140024bf1  mov     rdi, rcx
0x140024bf4  mov     [rsp+78h+var_48], rcx
0x140024bf9  call    ?ShutdownUpdateManagerIfRunning@UpdateManager@@SA_NXZ; UpdateManager::ShutdownUpdateManagerIfRunning(void)
0x140024bfe  mov     sil, al
0x140024c01  mov     [rsp+78h+var_58], al
0x140024c05  cmp     cs:?g_usoSvcSupportsPrivateNamespaces@@3_NA, 0; bool g_usoSvcSupportsPrivateNamespaces
0x140024c0c  jz      short loc_140024C6F
0x140024c0e  mov     [rsp+78h+hEvent], 0
0x140024c17  lea     rdx, aUsocoreworkere; "\\UsoCoreWorkerExiting"
0x140024c1e  lea     rcx, [rsp+78h+hEvent]
0x140024c23  call    ?TryOpenPrivateNamespaceEvent@PrivateNamespaceHelpers@Windows@@YA?AV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@PEB_WK_N@Z
0x140024c28  mov     rcx, [rsp+78h+hEvent]; hEvent
0x140024c2d  test    rcx, rcx
0x140024c30  jz      loc_140024CF8
0x140024c36  call    cs:__imp_SetEvent
0x140024c3c  mov     rcx, [rsp+78h]; this
0x140024c41  test    eax, eax
0x140024c43  jz      loc_140024D28
0x140024c49  mov     rcx, [rsp+78h+hEvent]; hObject
0x140024c4e  test    rcx, rcx
0x140024c51  jz      loc_140024CF8
0x140024c57  call    cs:__imp_CloseHandle
0x140024c5d  mov     rcx, [rsp+78h]; this
0x140024c62  test    eax, eax
0x140024c64  jz      loc_140024D3A
0x140024c6a  jmp     loc_140024CF8
0x140024c6f  xor     ebx, ebx
0x140024c71  mov     [rsp+78h+hEvent], rbx
0x140024c76  lea     rdx, aUsocoreworkere; "\\UsoCoreWorkerExiting"
0x140024c7d  lea     rcx, [rsp+78h+var_28]; void *
0x140024c82  call    ?GlobalObjectName@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; GlobalObjectName(wchar_t const *)
0x140024c87  cmp     qword ptr [rax+18h], 7
0x140024c8c  jbe     short loc_140024C91
0x140024c8e  mov     rax, [rax]
0x140024c91  mov     r8, rax; lpName
0x140024c94  xor     edx, edx; bInheritHandle
0x140024c96  mov     ecx, 100002h; dwDesiredAccess
0x140024c9b  call    cs:__imp_OpenEventW
0x140024ca1  test    rax, rax
0x140024ca4  jnz     short loc_140024CAB
0x140024ca6  xor     r14b, r14b
0x140024ca9  jmp     short loc_140024CC0
0x140024cab  mov     rdx, rax
0x140024cae  lea     rcx, [rsp+78h+hEvent]
0x140024cb3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140024cb8  mov     r14b, 1
0x140024cbb  mov     rbx, [rsp+78h+hEvent]
0x140024cc0  lea     rcx, [rsp+78h+var_28]
0x140024cc5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024cca  test    r14b, r14b
0x140024ccd  jz      short loc_140024CE1
0x140024ccf  mov     rcx, rbx; hEvent
0x140024cd2  call    cs:__imp_SetEvent
0x140024cd8  mov     rcx, [rsp+78h]; this
0x140024cdd  test    eax, eax
0x140024cdf  jz      short loc_140024D4C
0x140024ce1  test    rbx, rbx
0x140024ce4  jz      short loc_140024CF8
0x140024ce6  mov     rcx, rbx; hObject
0x140024ce9  call    cs:__imp_CloseHandle
0x140024cef  mov     rcx, [rsp+78h]; this
0x140024cf4  test    eax, eax
0x140024cf6  jz      short loc_140024D5E
0x140024cf8  jmp     short loc_140024D04
0x140024cfa  mov     sil, [rsp+78h+var_58]
0x140024cff  mov     rdi, [rsp+78h+var_48]
0x140024d04  mov     rcx, [rdi]
0x140024d07  call    ?Stop@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140024d0c  test    sil, sil
0x140024d0f  jz      short loc_140024D70
0x140024d11  lea     r11, [rsp+78h+var_8]
0x140024d16  mov     rbx, [r11+18h]
0x140024d1a  mov     rsi, [r11+20h]
0x140024d1e  mov     rdi, [r11+28h]
0x140024d22  mov     rsp, r11
0x140024d25  pop     r14
0x140024d27  retn
0x140024d28  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140024d2f  mov     edx, 9C7h; void *
0x140024d34  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140024d3a  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140024d41  mov     edx, 9D1h; void *
0x140024d46  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140024d4c  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140024d53  mov     edx, 9C7h; void *
0x140024d58  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140024d5e  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140024d65  mov     edx, 9D1h; void *
0x140024d6a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140024d70  lea     rdx, aUpdateManagerD; "Update manager did not respond to stop"
0x140024d77  lea     rcx, [rsp+78h+pExceptionObject]; this
0x140024d7c  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x140024d81  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x140024d88  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x140024d8d  call    _CxxThrowException
```
