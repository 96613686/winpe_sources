# CONFIG_HISTORY_ENTITY::~CONFIG_HISTORY_ENTITY(void)

- ea: `0x180004344`
- end: `0x1800043e6`
- name: `??1CONFIG_HISTORY_ENTITY@@QEAA@XZ`
- size: `162`
- prototype: `void __fastcall(CONFIG_HISTORY_ENTITY *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002b4c`

## callees

- `0x180004344`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004370`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000439b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004370`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000439b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000437e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000437e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043a9`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x18000435e`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x1800043c1`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x1800043cb`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x18000435e`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x1800043c1`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x1800043cb`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x1800043df`

## pseudocode

```c
void __fastcall CONFIG_HISTORY_ENTITY::~CONFIG_HISTORY_ENTITY(CONFIG_HISTORY_ENTITY *this)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax

  *(_DWORD *)this = 1483040867;
  STRU_PATH::~STRU_PATH((CONFIG_HISTORY_ENTITY *)((char *)this + 216));
  v2 = (void *)*((_QWORD *)this + 26);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    *((_QWORD *)this + 26) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 25);
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
    *((_QWORD *)this + 25) = 0;
  }
  STRU_PATH::~STRU_PATH((CONFIG_HISTORY_ENTITY *)((char *)this + 136));
  STRU_PATH::~STRU_PATH((CONFIG_HISTORY_ENTITY *)((char *)this + 72));
  STRU_PATH::~STRU_PATH((CONFIG_HISTORY_ENTITY *)((char *)this + 8));
}

```

## disassembly

```asm
0x180004344  mov     [rsp+arg_0], rbx
0x180004349  push    rdi
0x18000434a  sub     rsp, 20h
0x18000434e  mov     rbx, rcx
0x180004351  mov     dword ptr [rcx], 58656863h
0x180004357  add     rcx, 0D8h
0x18000435e  call    cs:__imp_??1STRU_PATH@@QEAA@XZ; STRU_PATH::~STRU_PATH(void)
0x180004364  mov     rdi, [rbx+0D0h]
0x18000436b  test    rdi, rdi
0x18000436e  jz      short loc_18000438F
0x180004370  call    cs:__imp_GetProcessHeap
0x180004376  mov     r8, rdi; lpMem
0x180004379  xor     edx, edx; dwFlags
0x18000437b  mov     rcx, rax; hHeap
0x18000437e  call    cs:__imp_HeapFree
0x180004384  mov     qword ptr [rbx+0D0h], 0
0x18000438f  mov     rdi, [rbx+0C8h]
0x180004396  test    rdi, rdi
0x180004399  jz      short loc_1800043BA
0x18000439b  call    cs:__imp_GetProcessHeap
0x1800043a1  mov     r8, rdi; lpMem
0x1800043a4  xor     edx, edx; dwFlags
0x1800043a6  mov     rcx, rax; hHeap
0x1800043a9  call    cs:__imp_HeapFree
0x1800043af  mov     qword ptr [rbx+0C8h], 0
0x1800043ba  lea     rcx, [rbx+88h]
0x1800043c1  call    cs:__imp_??1STRU_PATH@@QEAA@XZ; STRU_PATH::~STRU_PATH(void)
0x1800043c7  lea     rcx, [rbx+48h]
0x1800043cb  call    cs:__imp_??1STRU_PATH@@QEAA@XZ; STRU_PATH::~STRU_PATH(void)
0x1800043d1  lea     rcx, [rbx+8]
0x1800043d5  mov     rbx, [rsp+28h+arg_0]
0x1800043da  add     rsp, 20h
0x1800043de  pop     rdi
0x1800043df  jmp     cs:__imp_??1STRU_PATH@@QEAA@XZ; STRU_PATH::~STRU_PATH(void)
```
