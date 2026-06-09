# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x180073a10`
- end: `0x180073b92`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `386`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18025dbe0`

## callees

- `0x1800442c0`
- `0x180046940`
- `0x180071a30`
- `0x180073a10`
- `0x180073ba0`
- `0x180073dd0`
- `0x180242120`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180073aeb`
- `KERNEL32!GetProcessHeap` at `0x180073aeb`
- `KERNEL32!HeapFree` at `0x180073af9`
- `KERNEL32!HeapFree` at `0x180073af9`
- `KERNEL32!SetLastError` at `0x180073ac0`
- `KERNEL32!SetLastError` at `0x180073ac0`
- `KERNEL32!GetLastError` at `0x180073aa5`
- `KERNEL32!GetLastError` at `0x180073aa5`
- `KERNEL32!CloseHandle` at `0x180073ae1`
- `KERNEL32!CloseHandle` at `0x180073ae1`
- `KERNEL32!ReleaseMutex` at `0x180073ab0`
- `KERNEL32!ReleaseMutex` at `0x180073b1c`
- `KERNEL32!ReleaseMutex` at `0x180073ab0`
- `KERNEL32!ReleaseMutex` at `0x180073b1c`
- `KERNEL32!WaitForSingleObjectEx` at `0x180073a54`
- `KERNEL32!WaitForSingleObjectEx` at `0x180073a54`

## string_xrefs

- `0x180073b3b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.27\inc\wil\opensource\wil\resource.h`
- `0x180073b52`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.27\inc\wil\opensource\wil\resource.h`
- `0x180073b69`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.27\inc\wil\opensource\wil\resource.h`
- `0x180073b80`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.27\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  int result; // eax
  DWORD LastError; // ebp
  const char *v7; // r9
  void *v8; // rcx
  const char *v9; // r9
  HANDLE ProcessHeap; // rax
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return --*(_DWORD *)lpMem;
  }
  else
  {
    v2 = (void *)lpMem[1];
    v3 = WaitForSingleObjectEx(v2, 0xFFFFFFFF, 0);
    if ( v3 == 258 )
    {
      v2 = 0;
    }
    else if ( (v3 & 0xFFFFFF7F) != 0 )
    {
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xC2D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.27\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    }
    result = --*(_DWORD *)lpMem;
    if ( *(_DWORD *)lpMem )
    {
      if ( v2 )
      {
        result = ReleaseMutex(v2);
        if ( !result )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x9DB,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.27\\inc\\wil\\opensource\\wil\\resource.h",
            v11);
      }
    }
    else
    {
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        lpMem + 2,
        0);
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        lpMem + 3,
        0);
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x9DB,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.27\\inc\\wil\\opensource\\wil\\resource.h",
            v7);
        SetLastError(LastError);
      }
      wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(lpMem + 5);
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      v8 = (void *)lpMem[1];
      if ( v8 )
      {
        if ( !CloseHandle(v8) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x9D1,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.27\\inc\\wil\\opensource\\wil\\resource.h",
            v9);
      }
      ProcessHeap = GetProcessHeap();
      return HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180073a10  push    rbx
0x180073a12  sub     rsp, 20h
0x180073a16  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180073a1d  mov     rbx, rcx
0x180073a20  jnz     loc_180073B28
0x180073a26  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180073a2d  test    rax, rax
0x180073a30  jz      short loc_180073A40
0x180073a32  call    cs:__guard_dispatch_icall_fptr
0x180073a38  test    al, al
0x180073a3a  jnz     loc_180073B28
0x180073a40  mov     [rsp+28h+arg_10], rdi
0x180073a45  xor     r8d, r8d; bAlertable
0x180073a48  mov     rdi, [rbx+8]
0x180073a4c  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180073a51  mov     rcx, rdi; hHandle
0x180073a54  call    cs:__imp_WaitForSingleObjectEx
0x180073a5a  cmp     eax, 102h
0x180073a5f  jz      short loc_180073A6E
0x180073a61  test    eax, 0FFFFFF7Fh
0x180073a66  jnz     loc_180073B4D
0x180073a6c  jmp     short loc_180073A70
0x180073a6e  xor     edi, edi
0x180073a70  mov     eax, [rbx]
0x180073a72  dec     eax
0x180073a74  mov     [rbx], eax
0x180073a76  mov     eax, [rbx]
0x180073a78  test    eax, eax
0x180073a7a  jnz     loc_180073B14
0x180073a80  mov     [rsp+28h+arg_8], rsi
0x180073a85  lea     rcx, [rbx+10h]
0x180073a89  xor     edx, edx
0x180073a8b  mov     [rsp+28h+arg_0], rbp
0x180073a90  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180073a95  lea     rcx, [rbx+18h]
0x180073a99  xor     edx, edx
0x180073a9b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180073aa0  test    rdi, rdi
0x180073aa3  jz      short loc_180073AC6
0x180073aa5  call    cs:__imp_GetLastError
0x180073aab  mov     rcx, rdi; hMutex
0x180073aae  mov     ebp, eax
0x180073ab0  call    cs:__imp_ReleaseMutex
0x180073ab6  test    eax, eax
0x180073ab8  jz      loc_180073B7B
0x180073abe  mov     ecx, ebp; dwErrCode
0x180073ac0  call    cs:__imp_SetLastError
0x180073ac6  lea     rcx, [rbx+28h]
0x180073aca  call    ??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)
0x180073acf  lea     rcx, [rbx+10h]; this
0x180073ad3  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180073ad8  mov     rcx, [rbx+8]; hObject
0x180073adc  test    rcx, rcx
0x180073adf  jz      short loc_180073AEB
0x180073ae1  call    cs:__imp_CloseHandle
0x180073ae7  test    eax, eax
0x180073ae9  jz      short loc_180073B36
0x180073aeb  call    cs:__imp_GetProcessHeap
0x180073af1  mov     r8, rbx; lpMem
0x180073af4  xor     edx, edx; dwFlags
0x180073af6  mov     rcx, rax; hHeap
0x180073af9  call    cs:__imp_HeapFree
0x180073aff  mov     rbp, [rsp+28h+arg_0]
0x180073b04  mov     rsi, [rsp+28h+arg_8]
0x180073b09  mov     rdi, [rsp+28h+arg_10]
0x180073b0e  add     rsp, 20h
0x180073b12  pop     rbx
0x180073b13  retn
0x180073b14  test    rdi, rdi
0x180073b17  jz      short loc_180073B09
0x180073b19  mov     rcx, rdi; hMutex
0x180073b1c  call    cs:__imp_ReleaseMutex
0x180073b22  test    eax, eax
0x180073b24  jz      short loc_180073B64
0x180073b26  jmp     short loc_180073B09
0x180073b28  mov     eax, [rbx]
0x180073b2a  dec     eax
0x180073b2c  mov     [rbx], eax
0x180073b2e  mov     eax, [rbx]
0x180073b30  add     rsp, 20h
0x180073b34  pop     rbx
0x180073b35  retn
0x180073b36  mov     rcx, [rsp+28h]; this
0x180073b3b  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180073b42  mov     edx, 9D1h; void *
0x180073b47  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180073b4d  mov     rcx, [rsp+28h]; this
0x180073b52  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180073b59  mov     edx, 0C2Dh; void *
0x180073b5e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180073b64  mov     rcx, [rsp+28h]; this
0x180073b69  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180073b70  mov     edx, 9DBh; void *
0x180073b75  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180073b7b  mov     rcx, [rsp+28h]; this
0x180073b80  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180073b87  mov     edx, 9DBh; void *
0x180073b8c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
