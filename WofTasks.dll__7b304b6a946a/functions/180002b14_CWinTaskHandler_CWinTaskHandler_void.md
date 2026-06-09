# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180002b14`
- end: `0x180002b75`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002bc0`

## callees

- `0x180002b14`
- `0x180006010`

## import_xrefs

- `msvcrt!free` at `0x180002b5a`
- `msvcrt!free` at `0x180002b5a`
- `KERNEL32!CloseHandle` at `0x180002b2b`
- `KERNEL32!CloseHandle` at `0x180002b2b`

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
0x180002b14  push    rbx
0x180002b16  sub     rsp, 20h
0x180002b1a  mov     rbx, rcx
0x180002b1d  mov     rcx, [rcx+28h]; hObject
0x180002b21  lea     rax, [rcx-1]
0x180002b25  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002b29  ja      short loc_180002B39
0x180002b2b  call    cs:__imp_CloseHandle
0x180002b31  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180002b39  mov     rcx, [rbx+30h]
0x180002b3d  test    rcx, rcx
0x180002b40  jz      short loc_180002B56
0x180002b42  mov     rax, [rcx]
0x180002b45  mov     rax, [rax+10h]
0x180002b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b4e  mov     qword ptr [rbx+30h], 0
0x180002b56  mov     rcx, [rbx+8]; Block
0x180002b5a  call    cs:__imp_free
0x180002b60  mov     qword ptr [rbx+8], 0
0x180002b68  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180002b6f  add     rsp, 20h
0x180002b73  pop     rbx
0x180002b74  retn
```
