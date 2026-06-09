# Windows::Internal::DialogBlocking::HookProcess::ResetHookProcess(void)

- ea: `0x180009010`
- end: `0x180009097`
- name: `?ResetHookProcess@HookProcess@DialogBlocking@Internal@Windows@@QEAAXXZ`
- size: `135`
- prototype: `void __fastcall(Windows::Internal::DialogBlocking::HookProcess *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000899c`
- `0x180008a58`
- `0x1800099d8`

## callees

- `0x180007d1c`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000903f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000903f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000902e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000902e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009066`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009066`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000905e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000905e`

## pseudocode

```c
void __fastcall Windows::Internal::DialogBlocking::HookProcess::ResetHookProcess(
        Windows::Internal::DialogBlocking::HookProcess *this)
{
  __int64 v2; // r8
  const char *v3; // r9
  char *v4; // rsi
  DWORD LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_BYTE *)this )
  {
    if ( !SetEvent(**((HANDLE **)this + 3)) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v2, v3);
    WaitForSingleObject(*((HANDLE *)this + 2), 0xFFFFFFFF);
    v4 = (char *)*((_QWORD *)this + 2);
    if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v4);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 2) = 0;
    *(_BYTE *)this = 0;
  }
}

```

## disassembly

```asm
0x180009010  mov     [rsp+arg_0], rbx
0x180009015  mov     [rsp+arg_8], rsi
0x18000901a  push    rdi
0x18000901b  sub     rsp, 20h
0x18000901f  cmp     byte ptr [rcx], 0
0x180009022  mov     rdi, rcx
0x180009025  jz      short loc_180009077
0x180009027  mov     rcx, [rcx+18h]
0x18000902b  mov     rcx, [rcx]; hEvent
0x18000902e  call    cs:__imp_SetEvent
0x180009034  test    eax, eax
0x180009036  jz      short loc_180009087
0x180009038  mov     rcx, [rdi+10h]; hHandle
0x18000903c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000903f  call    cs:__imp_WaitForSingleObject
0x180009045  mov     rsi, [rdi+10h]
0x180009049  lea     rax, [rsi-1]
0x18000904d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009051  ja      short loc_18000906C
0x180009053  call    cs:__imp_GetLastError
0x180009059  mov     rcx, rsi; hObject
0x18000905c  mov     ebx, eax
0x18000905e  call    cs:__imp_CloseHandle
0x180009064  mov     ecx, ebx; dwErrCode
0x180009066  call    cs:__imp_SetLastError
0x18000906c  mov     qword ptr [rdi+10h], 0
0x180009074  mov     byte ptr [rdi], 0
0x180009077  mov     rbx, [rsp+28h+arg_0]
0x18000907c  mov     rsi, [rsp+28h+arg_8]
0x180009081  add     rsp, 20h
0x180009085  pop     rdi
0x180009086  retn
0x180009087  mov     rcx, [rsp+28h]; this
0x18000908c  mov     edx, 0A01h; void *
0x180009091  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
