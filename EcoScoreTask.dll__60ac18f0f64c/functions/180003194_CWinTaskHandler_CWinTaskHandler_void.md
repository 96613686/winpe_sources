# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180003194`
- end: `0x1800031f5`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800035b0`

## callees

- `0x180003194`
- `0x180009010`

## import_xrefs

- `msvcrt!free` at `0x1800031da`
- `msvcrt!free` at `0x1800031da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031ab`

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
0x180003194  push    rbx
0x180003196  sub     rsp, 20h
0x18000319a  mov     rbx, rcx
0x18000319d  mov     rcx, [rcx+28h]; hObject
0x1800031a1  lea     rax, [rcx-1]
0x1800031a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800031a9  ja      short loc_1800031B9
0x1800031ab  call    cs:__imp_CloseHandle
0x1800031b1  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x1800031b9  mov     rcx, [rbx+30h]
0x1800031bd  test    rcx, rcx
0x1800031c0  jz      short loc_1800031D6
0x1800031c2  mov     rax, [rcx]
0x1800031c5  mov     rax, [rax+10h]
0x1800031c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ce  mov     qword ptr [rbx+30h], 0
0x1800031d6  mov     rcx, [rbx+8]; Block
0x1800031da  call    cs:__imp_free
0x1800031e0  mov     qword ptr [rbx+8], 0
0x1800031e8  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800031ef  add     rsp, 20h
0x1800031f3  pop     rbx
0x1800031f4  retn
```
