# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x18000d88c`
- end: `0x18000d8ed`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000d940`

## callees

- `0x18000d88c`
- `0x18000f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d8d2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d8d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d8a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d8a3`

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
0x18000d88c  push    rbx
0x18000d88e  sub     rsp, 20h
0x18000d892  mov     rbx, rcx
0x18000d895  mov     rcx, [rcx+28h]; hObject
0x18000d899  lea     rax, [rcx-1]
0x18000d89d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d8a1  ja      short loc_18000D8B1
0x18000d8a3  call    cs:__imp_CloseHandle
0x18000d8a9  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x18000d8b1  mov     rcx, [rbx+30h]
0x18000d8b5  test    rcx, rcx
0x18000d8b8  jz      short loc_18000D8CE
0x18000d8ba  mov     rax, [rcx]
0x18000d8bd  mov     rax, [rax+10h]
0x18000d8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8c6  mov     qword ptr [rbx+30h], 0
0x18000d8ce  mov     rcx, [rbx+8]; Block
0x18000d8d2  call    cs:__imp_free
0x18000d8d8  mov     qword ptr [rbx+8], 0
0x18000d8e0  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000d8e7  add     rsp, 20h
0x18000d8eb  pop     rbx
0x18000d8ec  retn
```
