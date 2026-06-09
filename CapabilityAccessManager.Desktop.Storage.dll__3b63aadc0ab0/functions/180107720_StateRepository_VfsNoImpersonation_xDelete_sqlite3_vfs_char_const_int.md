# StateRepository::VfsNoImpersonation::xDelete(sqlite3_vfs *,char const *,int)

- ea: `0x180107720`
- end: `0x18010779d`
- name: `?xDelete@VfsNoImpersonation@StateRepository@@CAHPEAUsqlite3_vfs@@PEBDH@Z`
- size: `125`
- prototype: `__int64 __fastcall(struct sqlite3_vfs *, const char *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800ec608`
- `0x180102320`
- `0x180107720`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18010776d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18010776d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010777f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010777f`

## pseudocode

```c
__int64 __fastcall StateRepository::VfsNoImpersonation::xDelete(
        struct sqlite3_vfs *a1,
        const char *a2,
        unsigned int a3)
{
  unsigned int v6; // eax
  HANDLE v7; // rbx
  unsigned int v8; // edi
  wil::details::in1diag3 *v9; // rcx
  HANDLE Token; // [rsp+48h] [rbp+20h] BYREF

  wil::run_as_self_failfast(&Token);
  v6 = (*((__int64 (__fastcall **)(struct sqlite3_vfs *, const char *, _QWORD))StateRepository::VfsNoImpersonation::vfs_win32longpath
        + 6))(
         a1,
         a2,
         a3);
  v7 = Token;
  v8 = v6;
  if ( Token != (HANDLE)-1LL )
  {
    if ( !SetThreadToken(0, Token) )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v9);
    if ( v7 )
      CloseHandle(v7);
  }
  return v8;
}

```

## disassembly

```asm
0x180107720  mov     [rsp+arg_0], rbx
0x180107725  mov     [rsp+arg_8], rsi
0x18010772a  push    rdi
0x18010772b  sub     rsp, 20h
0x18010772f  mov     rsi, rcx
0x180107732  mov     ebx, r8d
0x180107735  lea     rcx, [rsp+28h+Token]
0x18010773a  mov     rdi, rdx
0x18010773d  call    ?run_as_self_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self_failfast(void)
0x180107742  mov     rax, cs:?vfs_win32longpath@VfsNoImpersonation@StateRepository@@0PEAUsqlite3_vfs@@EA; sqlite3_vfs * StateRepository::VfsNoImpersonation::vfs_win32longpath
0x180107749  mov     r8d, ebx
0x18010774c  mov     rdx, rdi
0x18010774f  mov     rcx, rsi
0x180107752  mov     rax, [rax+30h]
0x180107756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010775b  mov     rbx, [rsp+28h+Token]
0x180107760  mov     edi, eax
0x180107762  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180107766  jz      short loc_180107785
0x180107768  mov     rdx, rbx; Token
0x18010776b  xor     ecx, ecx; Thread
0x18010776d  call    cs:__imp_SetThreadToken
0x180107773  test    eax, eax
0x180107775  jz      short loc_180107797
0x180107777  test    rbx, rbx
0x18010777a  jz      short loc_180107785
0x18010777c  mov     rcx, rbx; hObject
0x18010777f  call    cs:__imp_CloseHandle
0x180107785  mov     rbx, [rsp+28h+arg_0]
0x18010778a  mov     eax, edi
0x18010778c  mov     rsi, [rsp+28h+arg_8]
0x180107791  add     rsp, 20h
0x180107795  pop     rdi
0x180107796  retn
0x180107797  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
