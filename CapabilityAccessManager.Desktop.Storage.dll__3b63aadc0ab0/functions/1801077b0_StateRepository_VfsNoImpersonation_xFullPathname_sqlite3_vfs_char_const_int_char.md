# StateRepository::VfsNoImpersonation::xFullPathname(sqlite3_vfs *,char const *,int,char *)

- ea: `0x1801077b0`
- end: `0x180107826`
- name: `?xFullPathname@VfsNoImpersonation@StateRepository@@CAHPEAUsqlite3_vfs@@PEBDHPEAD@Z`
- size: `118`
- prototype: `__int64 __fastcall(struct sqlite3_vfs *, const char *, int, char *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800ec608`
- `0x180102320`
- `0x1801077b0`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801077fd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801077fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010780f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010780f`

## pseudocode

```c
__int64 __fastcall StateRepository::VfsNoImpersonation::xFullPathname(
        struct sqlite3_vfs *a1,
        const char *a2,
        unsigned int a3,
        char *a4)
{
  unsigned int v8; // eax
  HANDLE v9; // rbx
  unsigned int v10; // edi
  wil::details::in1diag3 *v11; // rcx
  HANDLE Token; // [rsp+30h] [rbp-38h] BYREF

  wil::run_as_self_failfast(&Token);
  v8 = (*((__int64 (__fastcall **)(struct sqlite3_vfs *, const char *, _QWORD, char *))StateRepository::VfsNoImpersonation::vfs_win32longpath
        + 8))(
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
0x1801077b0  push    rbx
0x1801077b2  push    rbp
0x1801077b3  push    rsi
0x1801077b4  push    rdi
0x1801077b5  sub     rsp, 48h
0x1801077b9  mov     rbp, rcx
0x1801077bc  mov     rbx, r9
0x1801077bf  lea     rcx, [rsp+68h+Token]
0x1801077c4  mov     edi, r8d
0x1801077c7  mov     rsi, rdx
0x1801077ca  call    ?run_as_self_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self_failfast(void)
0x1801077cf  mov     rax, cs:?vfs_win32longpath@VfsNoImpersonation@StateRepository@@0PEAUsqlite3_vfs@@EA; sqlite3_vfs * StateRepository::VfsNoImpersonation::vfs_win32longpath
0x1801077d6  mov     r9, rbx
0x1801077d9  mov     r8d, edi
0x1801077dc  mov     rdx, rsi
0x1801077df  mov     rcx, rbp
0x1801077e2  mov     rax, [rax+40h]
0x1801077e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801077eb  mov     rbx, [rsp+68h+Token]
0x1801077f0  mov     edi, eax
0x1801077f2  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801077f6  jz      short loc_180107815
0x1801077f8  mov     rdx, rbx; Token
0x1801077fb  xor     ecx, ecx; Thread
0x1801077fd  call    cs:__imp_SetThreadToken
0x180107803  test    eax, eax
0x180107805  jz      short loc_180107820
0x180107807  test    rbx, rbx
0x18010780a  jz      short loc_180107815
0x18010780c  mov     rcx, rbx; hObject
0x18010780f  call    cs:__imp_CloseHandle
0x180107815  mov     eax, edi
0x180107817  add     rsp, 48h
0x18010781b  pop     rdi
0x18010781c  pop     rsi
0x18010781d  pop     rbp
0x18010781e  pop     rbx
0x18010781f  retn
0x180107820  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
