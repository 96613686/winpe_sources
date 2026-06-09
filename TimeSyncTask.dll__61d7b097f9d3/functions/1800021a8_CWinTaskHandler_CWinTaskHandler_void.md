# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x1800021a8`
- end: `0x180002209`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002250`

## callees

- `0x1800021a8`
- `0x180004010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800021ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800021ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021bf`

## pseudocode

```c
void __fastcall CWinTaskHandler::~CWinTaskHandler(CWinTaskHandler *this)
{
  char *v2; // rcx
  __int64 v3; // rcx

  v2 = (char *)*((_QWORD *)this + 5);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 5) = -1;
  }
  v3 = *((_QWORD *)this + 6);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 6) = 0;
  }
  free(*((void **)this + 1));
  *((_QWORD *)this + 1) = 0;
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
}

```

## disassembly

```asm
0x1800021a8  push    rbx
0x1800021aa  sub     rsp, 20h
0x1800021ae  mov     rbx, rcx
0x1800021b1  mov     rcx, [rcx+28h]; hObject
0x1800021b5  lea     rax, [rcx-1]
0x1800021b9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800021bd  ja      short loc_1800021CD
0x1800021bf  call    cs:__imp_CloseHandle
0x1800021c5  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x1800021cd  mov     rcx, [rbx+30h]
0x1800021d1  test    rcx, rcx
0x1800021d4  jz      short loc_1800021EA
0x1800021d6  mov     rax, [rcx]
0x1800021d9  mov     rax, [rax+10h]
0x1800021dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021e2  mov     qword ptr [rbx+30h], 0
0x1800021ea  mov     rcx, [rbx+8]; Block
0x1800021ee  call    cs:__imp_free
0x1800021f4  mov     qword ptr [rbx+8], 0
0x1800021fc  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180002203  add     rsp, 20h
0x180002207  pop     rbx
0x180002208  retn
```
