# _lambda_fc052fb5b01799398d8427155ac1e7d5_::operator()_std::shared_ptr_EventsPair___

- ea: `0x180055220`
- end: `0x1800552b5`
- name: `_lambda_fc052fb5b01799398d8427155ac1e7d5_::operator()_std::shared_ptr_EventsPair___`
- size: `149`
- prototype: `void __fastcall(unsigned int ***, void ***)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005aeb8`

## callees

- `0x18000c008`
- `0x18001896c`
- `0x180055220`
- `0x18006bf5c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005528a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005528a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005529c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005529c`

## string_xrefs

- `0x180055268`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall lambda_fc052fb5b01799398d8427155ac1e7d5_::operator()_std::shared_ptr_EventsPair___(
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
    v5 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)(*a2)[1] + 32LL))((*a2)[1], ***a1);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x31C,
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
0x180055220  mov     [rsp+arg_0], rbx
0x180055225  push    rdi; int
0x180055226  sub     rsp, 20h
0x18005522a  mov     rbx, rdx
0x18005522d  mov     rdi, rcx
0x180055230  mov     rdx, [rdx]
0x180055233  mov     rdx, [rdx]
0x180055236  lea     rcx, [rsp+28h+Token]
0x18005523b  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x180055240  nop
0x180055241  mov     rax, [rbx]
0x180055244  mov     rcx, [rax+8]
0x180055248  mov     r8, [rcx]
0x18005524b  mov     rax, [rdi]
0x18005524e  mov     rdx, [rax]
0x180055251  mov     edx, [rdx]
0x180055253  mov     rax, [r8+20h]
0x180055257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005525c  mov     rcx, [rsp+28h]; this
0x180055261  test    eax, eax
0x180055263  jns     short loc_18005527A
0x180055265  mov     r9d, eax; char *
0x180055268  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x18005526f  mov     edx, 31Ch; void *
0x180055274  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180055279  nop
0x18005527a  mov     rbx, [rsp+28h+Token]
0x18005527f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180055283  jz      short loc_1800552A3
0x180055285  mov     rdx, rbx; Token
0x180055288  xor     ecx, ecx; Thread
0x18005528a  call    cs:__imp_SetThreadToken
0x180055290  test    eax, eax
0x180055292  jz      short loc_1800552AE
0x180055294  test    rbx, rbx
0x180055297  jz      short loc_1800552A3
0x180055299  mov     rcx, rbx; hObject
0x18005529c  call    cs:__imp_CloseHandle
0x1800552a2  nop
0x1800552a3  mov     rbx, [rsp+28h+arg_0]
0x1800552a8  add     rsp, 20h
0x1800552ac  pop     rdi
0x1800552ad  retn
0x1800552ae  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
