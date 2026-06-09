# ProcessConnection::Destroy(void)

- ea: `0x18004e7a0`
- end: `0x18004e869`
- name: `?Destroy@ProcessConnection@@UEAAXXZ`
- size: `201`
- prototype: `void __fastcall(ProcessConnection *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004e494`
- `0x18004f4f0`

## callees

- `0x1800075e4`
- `0x18004e7a0`
- `0x18004f080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e7e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e7e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e812`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e7f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e825`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e7f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e825`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e7b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e7b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e7ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e7ec`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18004e81d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18004e81d`

## string_xrefs

- `0x18004e857`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`

## pseudocode

```c
void __fastcall ProcessConnection::Destroy(ProcessConnection *this)
{
  int v1; // ebx
  __int64 v3; // rcx
  const char *v4; // r9
  void *v5; // rsi
  DWORD LastError; // ebx
  void *v7; // rsi
  DWORD v8; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  ProcessConnection *v10; // [rsp+38h] [rbp+10h] BYREF

  v1 = dword_1800B9160;
  if ( v1 != GetCurrentThreadId() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x15D,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
      v4);
  if ( !*((_BYTE *)this + 88) )
  {
    *((_BYTE *)this + 88) = 1;
    *((_QWORD *)this + 10) = 0;
    v5 = (void *)*((_QWORD *)this + 3);
    if ( v5 )
    {
      LastError = GetLastError();
      CloseHandle(v5);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 3) = 0;
    *((_DWORD *)this + 16) = 0;
    v7 = (void *)*((_QWORD *)this + 9);
    if ( v7 )
    {
      v8 = GetLastError();
      UnregisterWait(v7);
      SetLastError(v8);
    }
    *((_QWORD *)this + 9) = 0;
    v10 = this;
    std::_Hash<std::_Umap_traits<void *,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>,0>>::erase(
      v3,
      &v10);
  }
}

```

## disassembly

```asm
0x18004e7a0  mov     [rsp+arg_0], rbx
0x18004e7a5  mov     [rsp+arg_10], rsi
0x18004e7aa  push    rdi
0x18004e7ab  sub     rsp, 20h
0x18004e7af  mov     ebx, cs:dword_1800B9160
0x18004e7b5  mov     rdi, rcx
0x18004e7b8  call    cs:__imp_GetCurrentThreadId
0x18004e7be  cmp     ebx, eax
0x18004e7c0  jnz     loc_18004E852
0x18004e7c6  cmp     byte ptr [rdi+58h], 0
0x18004e7ca  jnz     short loc_18004E842
0x18004e7cc  mov     byte ptr [rdi+58h], 1
0x18004e7d0  mov     qword ptr [rdi+50h], 0
0x18004e7d8  mov     rsi, [rdi+18h]
0x18004e7dc  test    rsi, rsi
0x18004e7df  jz      short loc_18004E7FA
0x18004e7e1  call    cs:__imp_GetLastError
0x18004e7e7  mov     rcx, rsi; hObject
0x18004e7ea  mov     ebx, eax
0x18004e7ec  call    cs:__imp_CloseHandle
0x18004e7f2  mov     ecx, ebx; dwErrCode
0x18004e7f4  call    cs:__imp_SetLastError
0x18004e7fa  mov     qword ptr [rdi+18h], 0
0x18004e802  mov     dword ptr [rdi+40h], 0
0x18004e809  mov     rsi, [rdi+48h]
0x18004e80d  test    rsi, rsi
0x18004e810  jz      short loc_18004E82B
0x18004e812  call    cs:__imp_GetLastError
0x18004e818  mov     rcx, rsi; WaitHandle
0x18004e81b  mov     ebx, eax
0x18004e81d  call    cs:__imp_UnregisterWait
0x18004e823  mov     ecx, ebx; dwErrCode
0x18004e825  call    cs:__imp_SetLastError
0x18004e82b  lea     rdx, [rsp+28h+arg_8]
0x18004e830  mov     qword ptr [rdi+48h], 0
0x18004e838  mov     [rsp+28h+arg_8], rdi
0x18004e83d  call    ?erase@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBQEAX@Z; std::_Hash<std::_Umap_traits<void *,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>,0>>::erase(void * const &)
0x18004e842  mov     rbx, [rsp+28h+arg_0]
0x18004e847  mov     rsi, [rsp+28h+arg_10]
0x18004e84c  add     rsp, 20h
0x18004e850  pop     rdi
0x18004e851  retn
0x18004e852  mov     rcx, [rsp+28h]; this
0x18004e857  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004e85e  mov     edx, 15Dh; void *
0x18004e863  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
