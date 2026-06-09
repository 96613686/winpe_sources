# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140071554`
- end: `0x140071773`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140071050`

## callees

- `0x140040184`
- `0x140040308`
- `0x140040364`
- `0x14004045c`
- `0x1400407f8`
- `0x140041430`
- `0x140070b54`
- `0x140071554`
- `0x140071960`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14007158f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14007158f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400716df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400716df`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14007162a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14007162a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400716c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400716c9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400715d4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400715d4`

## string_xrefs

- `0x14007172f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140071748`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140071761`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  unsigned int v7; // edi
  DWORD v9; // eax
  bool v10; // dl
  char *v11; // r9
  void *v12; // rsi
  int ValueInternal; // eax
  __int64 v14; // rdx
  _DWORD *v15; // rcx
  const char *v16; // r9
  const char *v17; // r9
  int v18; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v19 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  v6 = hHandle;
  if ( !hHandle )
    return (unsigned int)wil::details::GetLastErrorFailHr(v5);
  v9 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v9 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC2D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v11);
    v12 = v6;
  }
  v22 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v10, &v22, (bool *)v11);
  v7 = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
              Name,
              &hHandle,
              a2);
      v6 = hHandle;
      v7 = v18;
      if ( v18 < 0 )
      {
        v14 = 308;
        goto LABEL_20;
      }
    }
    v7 = 0;
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x64,
    (unsigned int)"wil",
    (const char *)(unsigned int)ValueInternal,
    120);
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, (unsigned int)"wil", (const char *)v7, v20);
  v14 = 299;
LABEL_20:
  wil::details::in1diag3::Return_Hr(retaddr, (void *)v14, (unsigned int)"wil", (const char *)v7, v19);
LABEL_13:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x9DB,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      v16);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x9D1,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      v17);
  return v7;
}

```

## disassembly

```asm
0x140071554  mov     [rsp-8+arg_10], rbx
0x140071559  mov     [rsp-8+arg_18], rsi
0x14007155e  push    rbp
0x14007155f  push    rdi
0x140071560  push    r14
0x140071562  lea     rbp, [rsp-160h]
0x14007156a  sub     rsp, 260h
0x140071571  mov     rax, cs:__security_cookie
0x140071578  xor     rax, rsp
0x14007157b  mov     [rbp+170h+var_20], rax
0x140071582  mov     r14, rdx
0x140071585  mov     qword ptr [rdx], 0
0x14007158c  mov     rbx, rcx
0x14007158f  call    cs:__imp_GetCurrentProcessId
0x140071595  mov     [rsp+270h+var_248], rbx
0x14007159a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400715a1  mov     r9d, eax
0x1400715a4  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1400715ac  mov     edx, 104h; unsigned __int64
0x1400715b1  lea     rcx, [rsp+270h+Name]; Buffer
0x1400715b6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400715bb  mov     r9d, 1F0001h; dwDesiredAccess
0x1400715c1  mov     [rsp+270h+hHandle], 0
0x1400715ca  xor     r8d, r8d; dwFlags
0x1400715cd  lea     rdx, [rsp+270h+Name]; lpName
0x1400715d2  xor     ecx, ecx; lpMutexAttributes
0x1400715d4  call    cs:__imp_CreateMutexExW
0x1400715da  mov     rdx, rax
0x1400715dd  lea     rcx, [rsp+270h+hHandle]
0x1400715e2  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400715e7  mov     rbx, [rsp+270h+hHandle]
0x1400715ec  test    rbx, rbx
0x1400715ef  jnz     short loc_140071621
0x1400715f1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400715f6  mov     edi, eax
0x1400715f8  mov     eax, edi
0x1400715fa  mov     rcx, [rbp+170h+var_20]
0x140071601  xor     rcx, rsp; StackCookie
0x140071604  call    __security_check_cookie
0x140071609  lea     r11, [rsp+270h+var_10]
0x140071611  mov     rbx, [r11+30h]
0x140071615  mov     rsi, [r11+38h]
0x140071619  mov     rsp, r11
0x14007161c  pop     r14
0x14007161e  pop     rdi
0x14007161f  pop     rbp
0x140071620  retn
0x140071621  xor     r8d, r8d; bAlertable
0x140071624  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140071627  mov     rcx, rbx; hHandle
0x14007162a  call    cs:__imp_WaitForSingleObjectEx
0x140071630  cmp     eax, 102h
0x140071635  jz      short loc_140071647
0x140071637  test    eax, 0FFFFFF7Fh
0x14007163c  jnz     loc_14007175A
0x140071642  mov     rsi, rbx
0x140071645  jmp     short loc_140071649
0x140071647  xor     esi, esi
0x140071649  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x14007164e  mov     [rsp+270h+var_238], 0
0x140071657  lea     rcx, [rsp+270h+Name]; wchar_t *
0x14007165c  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x140071661  mov     edi, eax
0x140071663  test    eax, eax
0x140071665  jns     short loc_1400716A4
0x140071667  mov     rcx, [rbp+178h]; this
0x14007166e  lea     r8, aWil; "wil"
0x140071675  mov     r9d, eax; char *
0x140071678  mov     edx, 64h ; 'd'; void *
0x14007167d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140071682  mov     rcx, [rbp+178h]; this
0x140071689  lea     r8, aWil; "wil"
0x140071690  mov     r9d, edi; char *
0x140071693  mov     edx, 6Dh ; 'm'; void *
0x140071698  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007169d  mov     edx, 12Bh
0x1400716a2  jmp     short loc_140071710
0x1400716a4  mov     rax, [rsp+270h+var_238]
0x1400716a9  lea     rcx, ds:0[rax*4]
0x1400716b1  test    rcx, rcx
0x1400716b4  jz      short loc_1400716EE
0x1400716b6  mov     [r14], rcx
0x1400716b9  mov     eax, [rcx]
0x1400716bb  inc     eax
0x1400716bd  mov     [rcx], eax
0x1400716bf  xor     edi, edi
0x1400716c1  test    rsi, rsi
0x1400716c4  jz      short loc_1400716D3
0x1400716c6  mov     rcx, rsi; hMutex
0x1400716c9  call    cs:__imp_ReleaseMutex
0x1400716cf  test    eax, eax
0x1400716d1  jz      short loc_140071728
0x1400716d3  test    rbx, rbx
0x1400716d6  jz      loc_1400715F8
0x1400716dc  mov     rcx, rbx; hObject
0x1400716df  call    cs:__imp_CloseHandle
0x1400716e5  test    eax, eax
0x1400716e7  jz      short loc_140071741
0x1400716e9  jmp     loc_1400715F8
0x1400716ee  mov     r8, r14
0x1400716f1  lea     rdx, [rsp+270h+hHandle]
0x1400716f6  lea     rcx, [rsp+270h+Name]
0x1400716fb  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140071700  mov     rbx, [rsp+270h+hHandle]
0x140071705  mov     edi, eax
0x140071707  test    eax, eax
0x140071709  jns     short loc_1400716BF
0x14007170b  mov     edx, 134h; void *
0x140071710  mov     rcx, [rbp+178h]; this
0x140071717  lea     r8, aWil; "wil"
0x14007171e  mov     r9d, edi; char *
0x140071721  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140071726  jmp     short loc_1400716C1
0x140071728  mov     rcx, [rbp+178h]; this
0x14007172f  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140071736  mov     edx, 9DBh; void *
0x14007173b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140071741  mov     rcx, [rbp+178h]; this
0x140071748  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14007174f  mov     edx, 9D1h; void *
0x140071754  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14007175a  mov     rcx, [rbp+178h]; this
0x140071761  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140071768  mov     edx, 0C2Dh; void *
0x14007176d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
