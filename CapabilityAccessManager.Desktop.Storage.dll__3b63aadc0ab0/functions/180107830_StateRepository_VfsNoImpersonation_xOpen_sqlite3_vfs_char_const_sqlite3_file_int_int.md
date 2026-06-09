# StateRepository::VfsNoImpersonation::xOpen(sqlite3_vfs *,char const *,sqlite3_file *,int,int *)

- ea: `0x180107830`
- end: `0x1801079d9`
- name: `?xOpen@VfsNoImpersonation@StateRepository@@CAHPEAUsqlite3_vfs@@PEBDPEAUsqlite3_file@@HPEAH@Z`
- size: `425`
- prototype: `__int64 __fastcall(struct sqlite3_vfs *, const char *, struct sqlite3_file *, int, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180005700`
- `0x180016970`
- `0x1800ec608`
- `0x180102320`
- `0x1801073b0`
- `0x180107830`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801079af`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801079af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801079c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801079c1`

## string_xrefs

- `0x18010788a`: `onecore\base\appmodel\staterepository\dataaccesslayer\vfsnoimpersonation.cpp`
- `0x1801078ca`: `onecore\base\appmodel\staterepository\dataaccesslayer\vfsnoimpersonation.cpp`
- `0x180107912`: `[vfs:xOpen] #%u sqlite3_malloc() failed`

## pseudocode

```c
__int64 __fastcall StateRepository::VfsNoImpersonation::xOpen(
        struct sqlite3_vfs *a1,
        const char *a2,
        struct sqlite3_file *a3,
        unsigned int a4,
        int *a5)
{
  unsigned int v9; // edi
  __int64 v10; // rax
  _DWORD *v11; // rcx
  HANDLE v12; // rbx
  wil::details::in1diag3 *v13; // rcx
  int v15; // [rsp+20h] [rbp-38h]
  int v16; // [rsp+20h] [rbp-38h]
  const char *v17; // [rsp+30h] [rbp-28h]
  const char *v18; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HANDLE Token; // [rsp+70h] [rbp+18h] BYREF

  wil::run_as_self_failfast(&Token);
  v9 = (*((__int64 (__fastcall **)(struct sqlite3_vfs *, const char *, struct sqlite3_file *, _QWORD, int *))StateRepository::VfsNoImpersonation::vfs_win32longpath
        + 5))(
         a1,
         a2,
         a3,
         a4,
         a5);
  if ( *(_QWORD *)a3 )
  {
    LOBYTE(v15) = **(_DWORD **)a3 < 2;
    wil::details::in1diag3::FailFast_HrIfMsg(
      retaddr,
      (void *)0x75,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\vfsnoimpersonation.cpp",
      (const char *)0x8000FFFFLL,
      v15,
      (bool)"sqlite3_io_methods too old; lacks xShmMap",
      v17);
    LOBYTE(v16) = **(_DWORD **)a3 < 3;
    wil::details::in1diag3::FailFast_HrIfMsg(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\vfsnoimpersonation.cpp",
      (const char *)0x8000FFFFLL,
      v16,
      (bool)"sqlite3_io_methods too old; lacks xFetch",
      v18);
    v10 = sqlite3_malloc(160);
    if ( v10 )
    {
      v11 = *(_DWORD **)a3;
      *(_OWORD *)v10 = *(_OWORD *)*(_QWORD *)a3;
      *(_OWORD *)(v10 + 16) = *((_OWORD *)v11 + 1);
      *(_OWORD *)(v10 + 32) = *((_OWORD *)v11 + 2);
      *(_OWORD *)(v10 + 48) = *((_OWORD *)v11 + 3);
      *(_OWORD *)(v10 + 64) = *((_OWORD *)v11 + 4);
      *(_OWORD *)(v10 + 80) = *((_OWORD *)v11 + 5);
      *(_OWORD *)(v10 + 96) = *((_OWORD *)v11 + 6);
      *(_OWORD *)(v10 + 112) = *((_OWORD *)v11 + 7);
      *(_OWORD *)(v10 + 128) = *((_OWORD *)v11 + 8);
      *(_QWORD *)(v10 + 144) = *((_QWORD *)v11 + 18);
      *(_QWORD *)(v10 + 8) = StateRepository::VfsNoImpersonation::xClose;
      *(_QWORD *)(v10 + 104) = StateRepository::VfsNoImpersonation::xShmMap;
      *(_QWORD *)(v10 + 152) = v11;
      *(_QWORD *)a3 = v10;
    }
    else
    {
      v9 = 7;
      sqlite3_log(7, "[vfs:xOpen] #%u sqlite3_malloc() failed", _InterlockedIncrement(&dword_180140410));
    }
  }
  v12 = Token;
  if ( Token != (HANDLE)-1LL )
  {
    if ( !SetThreadToken(0, Token) )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
    if ( v12 )
      CloseHandle(v12);
  }
  return v9;
}

```

## disassembly

```asm
0x180107830  push    rbx
0x180107832  push    rsi
0x180107833  push    rdi
0x180107834  push    r14
0x180107836  sub     rsp, 38h
0x18010783a  mov     rsi, rcx
0x18010783d  mov     ebx, r9d
0x180107840  lea     rcx, [rsp+58h+Token]
0x180107845  mov     r14, r8
0x180107848  mov     rdi, rdx
0x18010784b  call    ?run_as_self_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self_failfast(void)
0x180107850  mov     rax, cs:?vfs_win32longpath@VfsNoImpersonation@StateRepository@@0PEAUsqlite3_vfs@@EA; sqlite3_vfs * StateRepository::VfsNoImpersonation::vfs_win32longpath
0x180107857  mov     r9d, ebx
0x18010785a  mov     r10, [rsp+58h+arg_20]
0x180107862  mov     r8, r14
0x180107865  mov     rdx, rdi
0x180107868  mov     qword ptr [rsp+58h+var_38], r10
0x18010786d  mov     rcx, rsi
0x180107870  mov     rax, [rax+28h]
0x180107874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107879  mov     edi, eax
0x18010787b  mov     rax, [r14]
0x18010787e  test    rax, rax
0x180107881  jz      loc_18010799F
0x180107887  cmp     dword ptr [rax], 2
0x18010788a  lea     r8, aOnecoreBaseApp_6; "onecore\\base\\appmodel\\staterepositor"...
0x180107891  mov     rcx, [rsp+58h]; this
0x180107896  lea     rax, aSqlite3IoMetho; "sqlite3_io_methods too old; lacks xShmM"...
0x18010789d  setl    dl
0x1801078a0  mov     qword ptr [rsp+58h+var_30], rax; bool
0x1801078a5  mov     byte ptr [rsp+58h+var_38], dl; int
0x1801078a9  mov     ebx, 8000FFFFh
0x1801078ae  mov     edx, 75h ; 'u'; void *
0x1801078b3  mov     r9d, ebx; char *
0x1801078b6  call    ?FailFast_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::FailFast_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801078bb  mov     rax, [r14]
0x1801078be  lea     rdx, aSqlite3IoMetho_0; "sqlite3_io_methods too old; lacks xFetc"...
0x1801078c5  mov     rcx, [rsp+58h]; this
0x1801078ca  lea     r8, aOnecoreBaseApp_6; "onecore\\base\\appmodel\\staterepositor"...
0x1801078d1  mov     qword ptr [rsp+58h+var_30], rdx; bool
0x1801078d6  mov     r9d, ebx; char *
0x1801078d9  mov     edx, 76h ; 'v'; void *
0x1801078de  cmp     dword ptr [rax], 3
0x1801078e1  setl    al
0x1801078e4  mov     byte ptr [rsp+58h+var_38], al; int
0x1801078e8  call    ?FailFast_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::FailFast_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801078ed  mov     ecx, 0A0h
0x1801078f2  call    sqlite3_malloc
0x1801078f7  mov     rdx, rax
0x1801078fa  test    rax, rax
0x1801078fd  jnz     short loc_180107922
0x1801078ff  lea     edi, [rax+7]
0x180107902  lea     r8d, [rax+1]
0x180107906  lock xadd cs:dword_180140410, r8d
0x18010790f  inc     r8d
0x180107912  lea     rdx, aVfsXopenUSqlit; "[vfs:xOpen] #%u sqlite3_malloc() failed"
0x180107919  mov     ecx, edi
0x18010791b  call    sqlite3_log
0x180107920  jmp     short loc_18010799F
0x180107922  mov     rcx, [r14]
0x180107925  movups  xmm0, xmmword ptr [rcx]
0x180107928  movups  xmmword ptr [rax], xmm0
0x18010792b  movups  xmm1, xmmword ptr [rcx+10h]
0x18010792f  movups  xmmword ptr [rax+10h], xmm1
0x180107933  movups  xmm0, xmmword ptr [rcx+20h]
0x180107937  movups  xmmword ptr [rax+20h], xmm0
0x18010793b  movups  xmm1, xmmword ptr [rcx+30h]
0x18010793f  movups  xmmword ptr [rax+30h], xmm1
0x180107943  movups  xmm0, xmmword ptr [rcx+40h]
0x180107947  movups  xmmword ptr [rax+40h], xmm0
0x18010794b  movups  xmm1, xmmword ptr [rcx+50h]
0x18010794f  movups  xmmword ptr [rax+50h], xmm1
0x180107953  movups  xmm0, xmmword ptr [rcx+60h]
0x180107957  movups  xmmword ptr [rax+60h], xmm0
0x18010795b  movups  xmm1, xmmword ptr [rcx+70h]
0x18010795f  movups  xmmword ptr [rax+70h], xmm1
0x180107963  movups  xmm0, xmmword ptr [rcx+80h]
0x18010796a  movups  xmmword ptr [rax+80h], xmm0
0x180107971  mov     rax, [rcx+90h]
0x180107978  mov     [rdx+90h], rax
0x18010797f  lea     rax, ?xClose@VfsNoImpersonation@StateRepository@@CAHPEAUsqlite3_file@@@Z; StateRepository::VfsNoImpersonation::xClose(sqlite3_file *)
0x180107986  mov     [rdx+8], rax
0x18010798a  lea     rax, ?xShmMap@VfsNoImpersonation@StateRepository@@CAHPEAUsqlite3_file@@HHHPEAPECX@Z; StateRepository::VfsNoImpersonation::xShmMap(sqlite3_file *,int,int,int,void volatile * *)
0x180107991  mov     [rdx+68h], rax
0x180107995  mov     [rdx+98h], rcx
0x18010799c  mov     [r14], rdx
0x18010799f  mov     rbx, [rsp+58h+Token]
0x1801079a4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801079a8  jz      short loc_1801079C7
0x1801079aa  mov     rdx, rbx; Token
0x1801079ad  xor     ecx, ecx; Thread
0x1801079af  call    cs:__imp_SetThreadToken
0x1801079b5  test    eax, eax
0x1801079b7  jz      short loc_1801079D3
0x1801079b9  test    rbx, rbx
0x1801079bc  jz      short loc_1801079C7
0x1801079be  mov     rcx, rbx; hObject
0x1801079c1  call    cs:__imp_CloseHandle
0x1801079c7  mov     eax, edi
0x1801079c9  add     rsp, 38h
0x1801079cd  pop     r14
0x1801079cf  pop     rdi
0x1801079d0  pop     rsi
0x1801079d1  pop     rbx
0x1801079d2  retn
0x1801079d3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
