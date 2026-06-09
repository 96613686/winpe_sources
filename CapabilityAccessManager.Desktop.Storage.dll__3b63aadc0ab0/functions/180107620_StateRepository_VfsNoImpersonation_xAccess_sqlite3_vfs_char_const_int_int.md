# StateRepository::VfsNoImpersonation::xAccess(sqlite3_vfs *,char const *,int,int *)

- ea: `0x180107620`
- end: `0x180107696`
- name: `?xAccess@VfsNoImpersonation@StateRepository@@CAHPEAUsqlite3_vfs@@PEBDHPEAH@Z`
- size: `118`
- prototype: `__int64 __fastcall(struct sqlite3_vfs *, const char *, int, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800ec608`
- `0x180102320`
- `0x180107620`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18010766d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18010766d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010767f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010767f`

## pseudocode

```c
__int64 __fastcall StateRepository::VfsNoImpersonation::xAccess(
        struct sqlite3_vfs *a1,
        const char *a2,
        unsigned int a3,
        int *a4)
{
  unsigned int v8; // eax
  HANDLE v9; // rbx
  unsigned int v10; // edi
  wil::details::in1diag3 *v11; // rcx
  HANDLE Token; // [rsp+30h] [rbp-38h] BYREF

  wil::run_as_self_failfast(&Token);
  v8 = (*((__int64 (__fastcall **)(struct sqlite3_vfs *, const char *, _QWORD, int *))StateRepository::VfsNoImpersonation::vfs_win32longpath
        + 7))(
         a1,
         a2,
         a3,
         a4);
  v9 = Token;
  v10 = v8;
  if ( Token != (HANDLE)-1LL )
  {
    if ( !SetThreadToken(0, Token) )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v11);
    if ( v9 )
      CloseHandle(v9);
  }
  return v10;
}

```

## disassembly

```asm
0x180107620  push    rbx
0x180107622  push    rbp
0x180107623  push    rsi
0x180107624  push    rdi
0x180107625  sub     rsp, 48h
0x180107629  mov     rbp, rcx
0x18010762c  mov     rbx, r9
0x18010762f  lea     rcx, [rsp+68h+Token]
0x180107634  mov     edi, r8d
0x180107637  mov     rsi, rdx
0x18010763a  call    ?run_as_self_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self_failfast(void)
0x18010763f  mov     rax, cs:?vfs_win32longpath@VfsNoImpersonation@StateRepository@@0PEAUsqlite3_vfs@@EA; sqlite3_vfs * StateRepository::VfsNoImpersonation::vfs_win32longpath
0x180107646  mov     r9, rbx
0x180107649  mov     r8d, edi
0x18010764c  mov     rdx, rsi
0x18010764f  mov     rcx, rbp
0x180107652  mov     rax, [rax+38h]
0x180107656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010765b  mov     rbx, [rsp+68h+Token]
0x180107660  mov     edi, eax
0x180107662  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180107666  jz      short loc_180107685
0x180107668  mov     rdx, rbx; Token
0x18010766b  xor     ecx, ecx; Thread
0x18010766d  call    cs:__imp_SetThreadToken
0x180107673  test    eax, eax
0x180107675  jz      short loc_180107690
0x180107677  test    rbx, rbx
0x18010767a  jz      short loc_180107685
0x18010767c  mov     rcx, rbx; hObject
0x18010767f  call    cs:__imp_CloseHandle
0x180107685  mov     eax, edi
0x180107687  add     rsp, 48h
0x18010768b  pop     rdi
0x18010768c  pop     rsi
0x18010768d  pop     rbp
0x18010768e  pop     rbx
0x18010768f  retn
0x180107690  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
