# ThreadPoolWaitCallback::Shutdown(void)

- ea: `0x18005d0d0`
- end: `0x18005d18f`
- name: `?Shutdown@ThreadPoolWaitCallback@@UEAAXXZ`
- size: `191`
- prototype: `void __fastcall(ThreadPoolWaitCallback *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005cf10`

## callees

- `0x18000a008`
- `0x18005d0d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d13d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d13d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d154`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d154`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d148`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d148`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005d12b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005d12b`
- `msvcp_win!_Mtx_unlock` at `0x18005d171`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005d0ef`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005d111`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005d0ef`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005d111`
- `msvcp_win!_Mtx_lock` at `0x18005d0e0`
- `msvcp_win!_Mtx_lock` at `0x18005d0e0`

## string_xrefs

- `0x18005d17d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall ThreadPoolWaitCallback::Shutdown(ThreadPoolWaitCallback *this)
{
  void *v2; // rsi
  DWORD LastError; // ebp
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( _Mtx_lock((ThreadPoolWaitCallback *)((char *)this + 80)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)this + 39) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 39) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  if ( *((_QWORD *)this + 20) )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 1), 0, 0);
    v2 = (void *)*((_QWORD *)this + 20);
    if ( v2 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v4);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 20) = 0;
  }
  _Mtx_unlock((ThreadPoolWaitCallback *)((char *)this + 80));
}

```

## disassembly

```asm
0x18005d0d0  push    rbx
0x18005d0d2  push    rbp
0x18005d0d3  push    rsi
0x18005d0d4  push    rdi
0x18005d0d5  sub     rsp, 28h
0x18005d0d9  mov     rdi, rcx
0x18005d0dc  add     rcx, 50h ; 'P'; _Mtx_t
0x18005d0e0  call    cs:__imp__Mtx_lock
0x18005d0e6  test    eax, eax
0x18005d0e8  jz      short loc_18005D0F6
0x18005d0ea  mov     ecx, 5
0x18005d0ef  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005d0f5  int     3; Trap to Debugger
0x18005d0f6  cmp     dword ptr [rdi+9Ch], 7FFFFFFFh
0x18005d100  jnz     short loc_18005D118
0x18005d102  mov     ecx, 6
0x18005d107  mov     dword ptr [rdi+9Ch], 7FFFFFFEh
0x18005d111  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005d117  int     3; Trap to Debugger
0x18005d118  cmp     qword ptr [rdi+0A0h], 0
0x18005d120  jz      short loc_18005D165
0x18005d122  mov     rcx, [rdi+8]; pwa
0x18005d126  xor     r8d, r8d; pftTimeout
0x18005d129  xor     edx, edx; h
0x18005d12b  call    cs:__imp_SetThreadpoolWait
0x18005d131  mov     rsi, [rdi+0A0h]
0x18005d138  test    rsi, rsi
0x18005d13b  jz      short loc_18005D15A
0x18005d13d  call    cs:__imp_GetLastError
0x18005d143  mov     rcx, rsi; hObject
0x18005d146  mov     ebp, eax
0x18005d148  call    cs:__imp_CloseHandle
0x18005d14e  test    eax, eax
0x18005d150  jz      short loc_18005D178
0x18005d152  mov     ecx, ebp; dwErrCode
0x18005d154  call    cs:__imp_SetLastError
0x18005d15a  mov     qword ptr [rdi+0A0h], 0
0x18005d165  lea     rcx, [rdi+50h]
0x18005d169  add     rsp, 28h
0x18005d16d  pop     rdi
0x18005d16e  pop     rsi
0x18005d16f  pop     rbp
0x18005d170  pop     rbx
0x18005d171  jmp     cs:__imp__Mtx_unlock
0x18005d178  mov     rcx, [rsp+48h]; this
0x18005d17d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005d184  mov     edx, 0A0Bh; void *
0x18005d189  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
