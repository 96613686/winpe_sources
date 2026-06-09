# StateRepository::VfsNoImpersonation::xShmMap(sqlite3_file *,int,int,int,void volatile * *)

- ea: `0x1801079e0`
- end: `0x180107a74`
- name: `?xShmMap@VfsNoImpersonation@StateRepository@@CAHPEAUsqlite3_file@@HHHPEAPECX@Z`
- size: `148`
- prototype: `__int64 __fastcall(struct sqlite3_file *, int, int, int, volatile void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800ec608`
- `0x180102320`
- `0x1801079e0`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180107a41`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180107a41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180107a53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180107a53`

## pseudocode

```c
__int64 __fastcall StateRepository::VfsNoImpersonation::xShmMap(
        struct sqlite3_file *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        volatile void **a5)
{
  __int64 v9; // rbx
  unsigned int v10; // eax
  HANDLE v11; // rbx
  unsigned int v12; // edi
  wil::details::in1diag3 *v13; // rcx
  HANDLE Token; // [rsp+50h] [rbp+8h] BYREF

  v9 = *(_QWORD *)(*(_QWORD *)a1 + 152LL);
  wil::run_as_self_failfast(&Token);
  v10 = (*(__int64 (__fastcall **)(struct sqlite3_file *, _QWORD, _QWORD, _QWORD, volatile void **))(v9 + 104))(
          a1,
          a2,
          a3,
          a4,
          a5);
  v11 = Token;
  v12 = v10;
  if ( Token != (HANDLE)-1LL )
  {
    if ( !SetThreadToken(0, Token) )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
    if ( v11 )
      CloseHandle(v11);
  }
  return v12;
}

```

## disassembly

```asm
0x1801079e0  mov     [rsp+arg_8], rbx
0x1801079e5  mov     [rsp+arg_10], rbp
0x1801079ea  push    rsi
0x1801079eb  push    rdi
0x1801079ec  push    r14
0x1801079ee  sub     rsp, 30h
0x1801079f2  mov     rax, [rcx]
0x1801079f5  mov     r14, rcx
0x1801079f8  lea     rcx, [rsp+48h+Token]
0x1801079fd  mov     edi, r9d
0x180107a00  mov     esi, r8d
0x180107a03  mov     ebp, edx
0x180107a05  mov     rbx, [rax+98h]
0x180107a0c  call    ?run_as_self_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self_failfast(void)
0x180107a11  mov     r10, [rsp+48h+arg_20]
0x180107a16  mov     r9d, edi
0x180107a19  mov     rax, [rbx+68h]
0x180107a1d  mov     r8d, esi
0x180107a20  mov     edx, ebp
0x180107a22  mov     [rsp+48h+var_28], r10
0x180107a27  mov     rcx, r14
0x180107a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107a2f  mov     rbx, [rsp+48h+Token]
0x180107a34  mov     edi, eax
0x180107a36  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180107a3a  jz      short loc_180107A59
0x180107a3c  mov     rdx, rbx; Token
0x180107a3f  xor     ecx, ecx; Thread
0x180107a41  call    cs:__imp_SetThreadToken
0x180107a47  test    eax, eax
0x180107a49  jz      short loc_180107A6E
0x180107a4b  test    rbx, rbx
0x180107a4e  jz      short loc_180107A59
0x180107a50  mov     rcx, rbx; hObject
0x180107a53  call    cs:__imp_CloseHandle
0x180107a59  mov     rbx, [rsp+48h+arg_8]
0x180107a5e  mov     eax, edi
0x180107a60  mov     rbp, [rsp+48h+arg_10]
0x180107a65  add     rsp, 30h
0x180107a69  pop     r14
0x180107a6b  pop     rdi
0x180107a6c  pop     rsi
0x180107a6d  retn
0x180107a6e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
