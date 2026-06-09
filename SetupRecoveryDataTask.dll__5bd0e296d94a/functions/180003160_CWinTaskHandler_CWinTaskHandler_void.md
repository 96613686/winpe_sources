# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180003160`
- end: `0x1800031c1`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800038d0`

## callees

- `0x180003160`
- `0x18000d010`

## import_xrefs

- `msvcrt!free` at `0x1800031a6`
- `msvcrt!free` at `0x1800031a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003177`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003177`

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
0x180003160  push    rbx
0x180003162  sub     rsp, 20h
0x180003166  mov     rbx, rcx
0x180003169  mov     rcx, [rcx+28h]; hObject
0x18000316d  lea     rax, [rcx-1]
0x180003171  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003175  ja      short loc_180003185
0x180003177  call    cs:__imp_CloseHandle
0x18000317d  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180003185  mov     rcx, [rbx+30h]
0x180003189  test    rcx, rcx
0x18000318c  jz      short loc_1800031A2
0x18000318e  mov     rax, [rcx]
0x180003191  mov     rax, [rax+10h]
0x180003195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000319a  mov     qword ptr [rbx+30h], 0
0x1800031a2  mov     rcx, [rbx+8]; Block
0x1800031a6  call    cs:__imp_free
0x1800031ac  mov     qword ptr [rbx+8], 0
0x1800031b4  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800031bb  add     rsp, 20h
0x1800031bf  pop     rbx
0x1800031c0  retn
```
