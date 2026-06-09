# _lambda_3c58c1e976bd7fe17c7d6033093ce910_::operator()_std::shared_ptr_EventsPair___

- ea: `0x18005517c`
- end: `0x180055218`
- name: `_lambda_3c58c1e976bd7fe17c7d6033093ce910_::operator()_std::shared_ptr_EventsPair___`
- size: `156`
- prototype: `void __fastcall(unsigned int ***, void ***)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180055078`

## callees

- `0x18000c008`
- `0x18001896c`
- `0x18005517c`
- `0x18006bf5c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800551ed`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800551ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800551ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800551ff`

## string_xrefs

- `0x1800551cb`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall lambda_3c58c1e976bd7fe17c7d6033093ce910_::operator()_std::shared_ptr_EventsPair___(
        unsigned int ***a1,
        void ***a2)
{
  void *v4; // rdx
  int v5; // eax
  const char *v6; // r9
  HANDLE v7; // rbx
  wil::details::in1diag3 *v8; // rcx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HANDLE Token; // [rsp+38h] [rbp+10h] BYREF

  v4 = **a2;
  try
  {
    wil::impersonate_token(&Token, v4);
    v5 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)(*a2)[1] + 24LL))((*a2)[1], ***a1, *(*a1)[1]);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x318,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
        (const char *)(unsigned int)v5,
        v9);
    v7 = Token;
    if ( Token != (HANDLE)-1LL )
    {
      if ( !SetThreadToken(0, Token) )
        wil::details::in1diag3::_FailFastImmediate_Unexpected(v8);
      if ( v7 )
        CloseHandle(v7);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x32E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      v6);
  }
}

```

## disassembly

```asm
0x18005517c  mov     [rsp+arg_0], rbx
0x180055181  push    rdi; int
0x180055182  sub     rsp, 20h
0x180055186  mov     rbx, rdx
0x180055189  mov     rdi, rcx
0x18005518c  mov     rdx, [rdx]
0x18005518f  mov     rdx, [rdx]
0x180055192  lea     rcx, [rsp+28h+Token]
0x180055197  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x18005519c  nop
0x18005519d  mov     rdx, [rdi]
0x1800551a0  mov     rax, [rbx]
0x1800551a3  mov     rcx, [rax+8]
0x1800551a7  mov     rax, [rcx]
0x1800551aa  mov     r8, [rdx+8]
0x1800551ae  mov     rdx, [rdx]
0x1800551b1  mov     r8d, [r8]
0x1800551b4  mov     edx, [rdx]
0x1800551b6  mov     rax, [rax+18h]
0x1800551ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551bf  mov     rcx, [rsp+28h]; this
0x1800551c4  test    eax, eax
0x1800551c6  jns     short loc_1800551DD
0x1800551c8  mov     r9d, eax; char *
0x1800551cb  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800551d2  mov     edx, 318h; void *
0x1800551d7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800551dc  nop
0x1800551dd  mov     rbx, [rsp+28h+Token]
0x1800551e2  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800551e6  jz      short loc_180055206
0x1800551e8  mov     rdx, rbx; Token
0x1800551eb  xor     ecx, ecx; Thread
0x1800551ed  call    cs:__imp_SetThreadToken
0x1800551f3  test    eax, eax
0x1800551f5  jz      short loc_180055211
0x1800551f7  test    rbx, rbx
0x1800551fa  jz      short loc_180055206
0x1800551fc  mov     rcx, rbx; hObject
0x1800551ff  call    cs:__imp_CloseHandle
0x180055205  nop
0x180055206  mov     rbx, [rsp+28h+arg_0]
0x18005520b  add     rsp, 20h
0x18005520f  pop     rdi
0x180055210  retn
0x180055211  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
