# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180027fd4`
- end: `0x180028035`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180028950`

## callees

- `0x180027fd4`
- `0x180037010`

## import_xrefs

- `msvcrt!free` at `0x18002801a`
- `msvcrt!free` at `0x18002801a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027feb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027feb`

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
0x180027fd4  push    rbx
0x180027fd6  sub     rsp, 20h
0x180027fda  mov     rbx, rcx
0x180027fdd  mov     rcx, [rcx+28h]; hObject
0x180027fe1  lea     rax, [rcx-1]
0x180027fe5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180027fe9  ja      short loc_180027FF9
0x180027feb  call    cs:__imp_CloseHandle
0x180027ff1  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180027ff9  mov     rcx, [rbx+30h]
0x180027ffd  test    rcx, rcx
0x180028000  jz      short loc_180028016
0x180028002  mov     rax, [rcx]
0x180028005  mov     rax, [rax+10h]
0x180028009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002800e  mov     qword ptr [rbx+30h], 0
0x180028016  mov     rcx, [rbx+8]; Block
0x18002801a  call    cs:__imp_free
0x180028020  mov     qword ptr [rbx+8], 0
0x180028028  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18002802f  add     rsp, 20h
0x180028033  pop     rbx
0x180028034  retn
```
