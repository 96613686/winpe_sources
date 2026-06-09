# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::TryTerminatingSettingsProcess$_ResumeCoro$1

- ea: `0x18002c540`
- end: `0x18002c658`
- name: `winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::TryTerminatingSettingsProcess$_ResumeCoro$1`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002c660`

## callees

- `0x180003cc4`
- `0x1800166a8`
- `0x180027618`
- `0x18002c540`
- `0x18002c850`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002c5e3`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002c5e3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002c5c5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002c5c5`

## pseudocode

```c
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::TryTerminatingSettingsProcess__ResumeCoro_1(
        __int64 a1)
{
  __int64 v2; // rcx
  char *v3; // rax
  void *v4; // rdx
  unsigned int v5; // r8d
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 3:
    case 5:
      goto LABEL_7;
    case 2:
      v2 = *(unsigned int *)(*(_QWORD *)(a1 + 56) + 160LL);
      *(_DWORD *)(a1 + 32) = v2;
      *(_WORD *)(a1 + 8) = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v2, a1);
      break;
    case 4:
      v3 = (char *)OpenProcess(0x100401u, 0, *(_DWORD *)(a1 + 32));
      *(_QWORD *)(a1 + 16) = v3;
      if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !TerminateProcess(v3, 1u) )
        wil::details::in1diag3::_Log_GetLastError(retaddr, v4, v5, v6);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a1 + 16);
LABEL_7:
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)a1, 0x40u);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18002c540  mov     [rsp+arg_10], rbx
0x18002c545  mov     [rsp+arg_18], rsi
0x18002c54a  mov     [rsp+arg_0], rcx
0x18002c54f  push    rdi
0x18002c550  sub     rsp, 30h
0x18002c554  mov     rdi, [rsp+38h+arg_0]
0x18002c559  movzx   eax, word ptr [rdi+8]
0x18002c55d  mov     [rsp+38h+var_18], ax
0x18002c562  mov     ebx, 1
0x18002c567  add     ax, bx
0x18002c56a  cmp     ax, 6; switch 7 cases
0x18002c56e  ja      def_18002C589; jumptable 000000018002C589 default case, cases 1,2
0x18002c574  movsx   rax, ax
0x18002c578  lea     rdx, __ImageBase
0x18002c57f  mov     ecx, ds:(jpt_18002C589 - 180000000h)[rdx+rax*4]
0x18002c586  add     rcx, rdx
0x18002c589  jmp     rcx; switch jump
0x18002c58b  xor     ebx, ebx; jumptable 000000018002C589 case 4
0x18002c58d  jmp     loc_18002C614
0x18002c592  mov     rax, [rdi+38h]; jumptable 000000018002C589 case 3
0x18002c596  mov     ecx, [rax+0A0h]
0x18002c59c  mov     [rdi+20h], ecx
0x18002c59f  xor     ebx, ebx
0x18002c5a1  mov     byte ptr [rsp+38h+arg_8], bl
0x18002c5a5  lea     eax, [rbx+4]
0x18002c5a8  mov     [rdi+8], ax
0x18002c5ac  mov     rdx, rdi
0x18002c5af  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18002c5b4  jmp     short loc_18002C62A
0x18002c5b6  xor     ebx, ebx; jumptable 000000018002C589 case 6
0x18002c5b8  jmp     short loc_18002C614
0x18002c5ba  mov     r8d, [rdi+20h]; jumptable 000000018002C589 case 5
0x18002c5be  xor     edx, edx; bInheritHandle
0x18002c5c0  mov     ecx, 100401h; dwDesiredAccess
0x18002c5c5  call    cs:__imp_OpenProcess
0x18002c5cb  mov     [rdi+10h], rax
0x18002c5cf  lea     rcx, [rax-1]
0x18002c5d3  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002c5d7  ja      short loc_18002C5FB
0x18002c5d9  mov     [rsp+38h+arg_8], rax
0x18002c5de  mov     edx, ebx; uExitCode
0x18002c5e0  mov     rcx, rax; hProcess
0x18002c5e3  call    cs:__imp_TerminateProcess
0x18002c5e9  mov     rcx, [rsp+38h]; this
0x18002c5ee  xor     ebx, ebx
0x18002c5f0  test    eax, eax
0x18002c5f2  jnz     short loc_18002C5FD
0x18002c5f4  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002c5f9  jmp     short loc_18002C5FD
0x18002c5fb  xor     ebx, ebx
0x18002c5fd  lea     rcx, [rdi+10h]
0x18002c601  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c606  nop
0x18002c607  jmp     short loc_18002C610
0x18002c609  xor     ebx, ebx
0x18002c60b  mov     rdi, [rsp+38h+arg_0]
0x18002c610  jmp     short loc_18002C614
0x18002c612  xor     ebx, ebx; jumptable 000000018002C589 case 0
0x18002c614  cmp     [rdi+0Ah], bx
0x18002c618  jz      short loc_18002C62A
0x18002c61a  mov     edx, 40h ; '@'; unsigned __int64
0x18002c61f  mov     rcx, rdi; void *
0x18002c622  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002c627  jmp     short loc_18002C62A
0x18002c629  int     3; Trap to Debugger
0x18002c62a  mov     rbx, [rsp+38h+arg_10]
0x18002c62f  mov     rsi, [rsp+38h+arg_18]
0x18002c634  add     rsp, 30h
0x18002c638  pop     rdi
0x18002c639  retn
```
