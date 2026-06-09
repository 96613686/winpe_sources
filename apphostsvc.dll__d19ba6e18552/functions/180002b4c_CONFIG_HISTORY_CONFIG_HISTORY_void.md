# CONFIG_HISTORY::~CONFIG_HISTORY(void)

- ea: `0x180002b4c`
- end: `0x180002ca6`
- name: `??1CONFIG_HISTORY@@QEAA@XZ`
- size: `346`
- prototype: `void __fastcall(CONFIG_HISTORY *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180003e30`
- `0x180005448`

## callees

- `0x180001048`
- `0x180002b4c`
- `0x180004344`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002bbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002be1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002bbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002be1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002bca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002bef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002bca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002bef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c83`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180002c9f`

## pseudocode

```c
void __fastcall CONFIG_HISTORY::~CONFIG_HISTORY(CONFIG_HISTORY *this)
{
  void *v2; // rdi
  __int64 v3; // rcx
  void *v4; // rdi
  HANDLE ProcessHeap; // rax
  void *v6; // rdi
  HANDLE v7; // rax
  void *v8; // rdi
  HANDLE v9; // rax
  void *v10; // rdi
  HANDLE v11; // rax
  void *v12; // rdi
  HANDLE v13; // rax
  void *v14; // rdi
  HANDLE v15; // rax

  *(_QWORD *)this = &CONFIG_HISTORY::`vftable'{for `INativeChangeListener'};
  *((_QWORD *)this + 1) = &CONFIG_HISTORY::`vftable'{for `MULTI_WORK_DISPATCH'};
  *((_DWORD *)this + 4) = 1483236963;
  v2 = (void *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    CONFIG_HISTORY_ENTITY::~CONFIG_HISTORY_ENTITY(*((CONFIG_HISTORY_ENTITY **)this + 5));
    operator delete(v2);
    *((_QWORD *)this + 5) = 0;
  }
  v3 = *((_QWORD *)this + 4);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 4) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 14);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *((_QWORD *)this + 14) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 13);
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
    *((_QWORD *)this + 13) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 12);
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
    *((_QWORD *)this + 12) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 11);
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
    *((_QWORD *)this + 11) = 0;
  }
  v12 = (void *)*((_QWORD *)this + 10);
  if ( v12 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v12);
    *((_QWORD *)this + 10) = 0;
  }
  v14 = (void *)*((_QWORD *)this + 9);
  if ( v14 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v14);
    *((_QWORD *)this + 9) = 0;
  }
  CReaderWriterLock3::~CReaderWriterLock3((CONFIG_HISTORY *)((char *)this + 24));
}

```

## disassembly

```asm
0x180002b4c  mov     [rsp+arg_0], rbx
0x180002b51  push    rdi
0x180002b52  sub     rsp, 20h
0x180002b56  mov     rbx, rcx
0x180002b59  lea     rax, ??_7CONFIG_HISTORY@@6BINativeChangeListener@@@; const CONFIG_HISTORY::`vftable'{for `INativeChangeListener'}
0x180002b60  mov     [rcx], rax
0x180002b63  lea     rax, ??_7CONFIG_HISTORY@@6BMULTI_WORK_DISPATCH@@@; const CONFIG_HISTORY::`vftable'{for `MULTI_WORK_DISPATCH'}
0x180002b6a  mov     [rcx+8], rax
0x180002b6e  mov     dword ptr [rcx+10h], 58686663h
0x180002b75  mov     rdi, [rcx+28h]
0x180002b79  test    rdi, rdi
0x180002b7c  jz      short loc_180002B96
0x180002b7e  mov     rcx, rdi; this
0x180002b81  call    ??1CONFIG_HISTORY_ENTITY@@QEAA@XZ; CONFIG_HISTORY_ENTITY::~CONFIG_HISTORY_ENTITY(void)
0x180002b86  mov     rcx, rdi; Block
0x180002b89  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002b8e  mov     qword ptr [rbx+28h], 0
0x180002b96  mov     rcx, [rbx+20h]
0x180002b9a  test    rcx, rcx
0x180002b9d  jz      short loc_180002BB3
0x180002b9f  mov     rax, [rcx]
0x180002ba2  mov     rax, [rax+10h]
0x180002ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bab  mov     qword ptr [rbx+20h], 0
0x180002bb3  mov     rdi, [rbx+70h]
0x180002bb7  test    rdi, rdi
0x180002bba  jz      short loc_180002BD8
0x180002bbc  call    cs:__imp_GetProcessHeap
0x180002bc2  mov     r8, rdi; lpMem
0x180002bc5  xor     edx, edx; dwFlags
0x180002bc7  mov     rcx, rax; hHeap
0x180002bca  call    cs:__imp_HeapFree
0x180002bd0  mov     qword ptr [rbx+70h], 0
0x180002bd8  mov     rdi, [rbx+68h]
0x180002bdc  test    rdi, rdi
0x180002bdf  jz      short loc_180002BFD
0x180002be1  call    cs:__imp_GetProcessHeap
0x180002be7  mov     r8, rdi; lpMem
0x180002bea  xor     edx, edx; dwFlags
0x180002bec  mov     rcx, rax; hHeap
0x180002bef  call    cs:__imp_HeapFree
0x180002bf5  mov     qword ptr [rbx+68h], 0
0x180002bfd  mov     rdi, [rbx+60h]
0x180002c01  test    rdi, rdi
0x180002c04  jz      short loc_180002C22
0x180002c06  call    cs:__imp_GetProcessHeap
0x180002c0c  mov     r8, rdi; lpMem
0x180002c0f  xor     edx, edx; dwFlags
0x180002c11  mov     rcx, rax; hHeap
0x180002c14  call    cs:__imp_HeapFree
0x180002c1a  mov     qword ptr [rbx+60h], 0
0x180002c22  mov     rdi, [rbx+58h]
0x180002c26  test    rdi, rdi
0x180002c29  jz      short loc_180002C47
0x180002c2b  call    cs:__imp_GetProcessHeap
0x180002c31  mov     r8, rdi; lpMem
0x180002c34  xor     edx, edx; dwFlags
0x180002c36  mov     rcx, rax; hHeap
0x180002c39  call    cs:__imp_HeapFree
0x180002c3f  mov     qword ptr [rbx+58h], 0
0x180002c47  mov     rdi, [rbx+50h]
0x180002c4b  test    rdi, rdi
0x180002c4e  jz      short loc_180002C6C
0x180002c50  call    cs:__imp_GetProcessHeap
0x180002c56  mov     r8, rdi; lpMem
0x180002c59  xor     edx, edx; dwFlags
0x180002c5b  mov     rcx, rax; hHeap
0x180002c5e  call    cs:__imp_HeapFree
0x180002c64  mov     qword ptr [rbx+50h], 0
0x180002c6c  mov     rdi, [rbx+48h]
0x180002c70  test    rdi, rdi
0x180002c73  jz      short loc_180002C91
0x180002c75  call    cs:__imp_GetProcessHeap
0x180002c7b  mov     r8, rdi; lpMem
0x180002c7e  xor     edx, edx; dwFlags
0x180002c80  mov     rcx, rax; hHeap
0x180002c83  call    cs:__imp_HeapFree
0x180002c89  mov     qword ptr [rbx+48h], 0
0x180002c91  lea     rcx, [rbx+18h]
0x180002c95  mov     rbx, [rsp+28h+arg_0]
0x180002c9a  add     rsp, 20h
0x180002c9e  pop     rdi
0x180002c9f  jmp     cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
```
