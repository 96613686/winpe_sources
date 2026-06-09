# StagedWork::_ExecuteWorkCallback(void)

- ea: `0x18005a990`
- end: `0x18005aa6a`
- name: `?_ExecuteWorkCallback@StagedWork@@MEAA_NXZ`
- size: `218`
- prototype: `bool __fastcall(StagedWork *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18005a690`

## callees

- `0x18000a008`
- `0x180011318`
- `0x18005a990`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a9c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a9c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a9d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a9d4`
- `api-ms-win-core-fibers-l2-1-0!SwitchToFiber` at `0x18005a9fd`
- `api-ms-win-core-fibers-l2-1-0!SwitchToFiber` at `0x18005a9fd`
- `api-ms-win-core-fibers-l2-1-0!ConvertFiberToThread` at `0x18005aa03`
- `api-ms-win-core-fibers-l2-1-0!ConvertFiberToThread` at `0x18005aa03`
- `api-ms-win-core-fibers-l2-1-0!CreateFiber` at `0x18005a9af`
- `api-ms-win-core-fibers-l2-1-0!CreateFiber` at `0x18005a9af`
- `api-ms-win-core-fibers-l2-1-0!DeleteFiber` at `0x18005a9cc`
- `api-ms-win-core-fibers-l2-1-0!DeleteFiber` at `0x18005a9cc`
- `api-ms-win-core-fibers-l2-1-1!ConvertThreadToFiberEx` at `0x18005a9ea`
- `api-ms-win-core-fibers-l2-1-1!ConvertThreadToFiberEx` at `0x18005a9ea`

## string_xrefs

- `0x18005aa2a`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\stagedwork.cpp`
- `0x18005aa41`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\stagedwork.cpp`
- `0x18005aa58`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\stagedwork.cpp`

## pseudocode

```c
bool __fastcall StagedWork::_ExecuteWorkCallback(LPVOID *this)
{
  LPVOID Fiber; // rax
  const char *v3; // r9
  void *v4; // rbp
  void *v5; // rsi
  DWORD LastError; // ebx
  LPVOID v7; // rax
  const char *v8; // r9
  const char *v9; // r9
  bool v10; // zf
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !this[14] )
  {
    Fiber = CreateFiber(0, StagedWork::_FiberProc, this);
    v4 = this[14];
    v5 = Fiber;
    if ( v4 )
    {
      LastError = GetLastError();
      DeleteFiber(v4);
      SetLastError(LastError);
    }
    this[14] = v5;
    if ( !v5 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\stagedwork.cpp",
        v3);
  }
  v7 = ConvertThreadToFiberEx(0, 1u);
  this[15] = v7;
  if ( !v7 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\stagedwork.cpp",
      v8);
  SwitchToFiber(this[14]);
  if ( !ConvertFiberToThread() )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\stagedwork.cpp",
      v9);
  v10 = *((_DWORD *)this + 26) == 3;
  this[15] = 0;
  return v10;
}

```

## disassembly

```asm
0x18005a990  push    rbx
0x18005a992  push    rbp
0x18005a993  push    rsi
0x18005a994  push    rdi
0x18005a995  sub     rsp, 28h
0x18005a999  cmp     qword ptr [rcx+70h], 0
0x18005a99e  mov     rdi, rcx
0x18005a9a1  jnz     short loc_18005A9E3
0x18005a9a3  mov     r8, rcx; lpParameter
0x18005a9a6  lea     rdx, ?_FiberProc@StagedWork@@CAXPEAX@Z; lpStartAddress
0x18005a9ad  xor     ecx, ecx; dwStackSize
0x18005a9af  call    cs:__imp_CreateFiber
0x18005a9b5  mov     rbp, [rdi+70h]
0x18005a9b9  mov     rsi, rax
0x18005a9bc  test    rbp, rbp
0x18005a9bf  jz      short loc_18005A9DA
0x18005a9c1  call    cs:__imp_GetLastError
0x18005a9c7  mov     rcx, rbp; lpFiber
0x18005a9ca  mov     ebx, eax
0x18005a9cc  call    cs:__imp_DeleteFiber
0x18005a9d2  mov     ecx, ebx; dwErrCode
0x18005a9d4  call    cs:__imp_SetLastError
0x18005a9da  mov     [rdi+70h], rsi
0x18005a9de  test    rsi, rsi
0x18005a9e1  jz      short loc_18005AA3C
0x18005a9e3  mov     edx, 1; dwFlags
0x18005a9e8  xor     ecx, ecx; lpParameter
0x18005a9ea  call    cs:__imp_ConvertThreadToFiberEx
0x18005a9f0  mov     [rdi+78h], rax
0x18005a9f4  test    rax, rax
0x18005a9f7  jz      short loc_18005AA53
0x18005a9f9  mov     rcx, [rdi+70h]; lpFiber
0x18005a9fd  call    cs:__imp_SwitchToFiber
0x18005aa03  call    cs:__imp_ConvertFiberToThread
0x18005aa09  test    eax, eax
0x18005aa0b  jz      short loc_18005AA25
0x18005aa0d  cmp     dword ptr [rdi+68h], 3
0x18005aa11  mov     qword ptr [rdi+78h], 0
0x18005aa19  setz    al
0x18005aa1c  add     rsp, 28h
0x18005aa20  pop     rdi
0x18005aa21  pop     rsi
0x18005aa22  pop     rbp
0x18005aa23  pop     rbx
0x18005aa24  retn
0x18005aa25  mov     rcx, [rsp+48h]; this
0x18005aa2a  lea     r8, aOnecoreBaseLan_18; "onecore\\base\\languageoverlay\\service"...
0x18005aa31  mov     edx, 57h ; 'W'; void *
0x18005aa36  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18005aa3c  mov     rcx, [rsp+48h]; this
0x18005aa41  lea     r8, aOnecoreBaseLan_18; "onecore\\base\\languageoverlay\\service"...
0x18005aa48  mov     edx, 4Ch ; 'L'; void *
0x18005aa4d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005aa53  mov     rcx, [rsp+48h]; this
0x18005aa58  lea     r8, aOnecoreBaseLan_18; "onecore\\base\\languageoverlay\\service"...
0x18005aa5f  mov     edx, 53h ; 'S'; void *
0x18005aa64  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
