# _anonymous_namespace_::ApplyWin32Scale

- ea: `0x180029170`
- end: `0x18002925c`
- name: `_anonymous_namespace_::ApplyWin32Scale`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180029fc0`

## callees

- `0x180004c8c`
- `0x18000df9c`
- `0x18000ea34`
- `0x180028f9c`
- `0x180029170`
- `0x180029764`
- `0x180029790`
- `0x18002a0f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180029226`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180029226`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800291a8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800291a8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800291ee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800291ee`

## string_xrefs

- `0x1800291cb`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::ApplyWin32Scale(int a1)
{
  _DWORD *v2; // rax
  HANDLE Thread; // rbx
  const char *v4; // r9
  DWORD v5; // eax
  void *v6; // rdx
  unsigned int v7; // r8d
  const char *v8; // r9
  void *v9; // rdx
  unsigned int v10; // r8d
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD ExitCode; // [rsp+48h] [rbp+10h] BYREF
  _DWORD *v15; // [rsp+50h] [rbp+18h] BYREF
  HANDLE v16; // [rsp+58h] [rbp+20h] BYREF

  v2 = operator new(4u);
  *v2 = a1;
  v15 = v2;
  Thread = CreateThread(0, 0, anonymous_namespace_::Win32TextScaleThreadProc, v2, 0, 0);
  v16 = Thread;
  if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.uis"
                    "ettingscontroller.cpp",
      v4);
  v15 = 0;
  v5 = WaitForSingleObject(Thread, 0x2710u);
  if ( v5 == 258 )
  {
    wil::details::in1diag3::Log_Win32(retaddr, v6, v7, v8, dwCreationFlags);
  }
  else
  {
    if ( v5 != -1 )
      wil::details::in1diag3::Log_GetLastError(retaddr, v6, v7, v8);
    ExitCode = 0;
    GetExitCodeThread(Thread, &ExitCode);
    if ( (ExitCode & 0x80000000) != 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, v9, v10, (const char *)ExitCode, dwCreationFlags);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
  return std::unique_ptr<int>::~unique_ptr<int>(&v15);
}

```

## disassembly

```asm
0x180029170  push    rbx
0x180029172  sub     rsp, 30h
0x180029176  mov     ebx, ecx
0x180029178  mov     ecx, 4; Size
0x18002917d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029182  mov     [rax], ebx
0x180029184  mov     [rsp+38h+arg_10], rax
0x180029189  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180029192  mov     [rsp+38h+dwCreationFlags], 0; int
0x18002919a  mov     r9, rax; lpParameter
0x18002919d  lea     r8, _anonymous_namespace___Win32TextScaleThreadProc; lpStartAddress
0x1800291a4  xor     edx, edx; dwStackSize
0x1800291a6  xor     ecx, ecx; lpThreadAttributes
0x1800291a8  call    cs:__imp_CreateThread
0x1800291ae  mov     rbx, rax
0x1800291b1  mov     [rsp+38h+arg_18], rax
0x1800291b6  inc     rax
0x1800291b9  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800291bf  setz    al
0x1800291c2  mov     rcx, [rsp+38h]; this
0x1800291c7  test    al, al
0x1800291c9  jz      short loc_1800291DD
0x1800291cb  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x1800291d2  mov     edx, 83h; void *
0x1800291d7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800291dd  mov     [rsp+38h+arg_10], 0
0x1800291e6  mov     edx, 2710h; dwMilliseconds
0x1800291eb  mov     rcx, rbx; hHandle
0x1800291ee  call    cs:__imp_WaitForSingleObject
0x1800291f4  cmp     eax, 102h
0x1800291f9  jnz     short loc_180029207
0x1800291fb  mov     rcx, [rsp+38h]; this
0x180029200  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180029205  jmp     short loc_180029241
0x180029207  cmp     eax, 0FFFFFFFFh
0x18002920a  jz      short loc_180029216
0x18002920c  mov     rcx, [rsp+38h]; this
0x180029211  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180029216  mov     [rsp+38h+ExitCode], 0
0x18002921e  lea     rdx, [rsp+38h+ExitCode]; lpExitCode
0x180029223  mov     rcx, rbx; hThread
0x180029226  call    cs:__imp_GetExitCodeThread
0x18002922c  mov     r9d, [rsp+38h+ExitCode]; char *
0x180029231  mov     rcx, [rsp+38h]; this
0x180029236  test    r9d, r9d
0x180029239  jns     short loc_180029241
0x18002923b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029240  nop
0x180029241  lea     rcx, [rsp+38h+arg_18]
0x180029246  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002924b  nop
0x18002924c  lea     rcx, [rsp+38h+arg_10]
0x180029251  call    ??1?$unique_ptr@HU?$default_delete@H@std@@@std@@QEAA@XZ; std::unique_ptr<int>::~unique_ptr<int>(void)
0x180029256  add     rsp, 30h
0x18002925a  pop     rbx
0x18002925b  retn
```
