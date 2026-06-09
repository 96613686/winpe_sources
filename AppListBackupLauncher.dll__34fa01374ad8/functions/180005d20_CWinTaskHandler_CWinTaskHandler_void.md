# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180005d20`
- end: `0x180005d81`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180006770`

## callees

- `0x180005d20`
- `0x180012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005d66`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005d66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d37`

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
0x180005d20  push    rbx
0x180005d22  sub     rsp, 20h
0x180005d26  mov     rbx, rcx
0x180005d29  mov     rcx, [rcx+28h]; hObject
0x180005d2d  lea     rax, [rcx-1]
0x180005d31  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005d35  ja      short loc_180005D45
0x180005d37  call    cs:__imp_CloseHandle
0x180005d3d  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180005d45  mov     rcx, [rbx+30h]
0x180005d49  test    rcx, rcx
0x180005d4c  jz      short loc_180005D62
0x180005d4e  mov     rax, [rcx]
0x180005d51  mov     rax, [rax+10h]
0x180005d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d5a  mov     qword ptr [rbx+30h], 0
0x180005d62  mov     rcx, [rbx+8]; Block
0x180005d66  call    cs:__imp_free
0x180005d6c  mov     qword ptr [rbx+8], 0
0x180005d74  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180005d7b  add     rsp, 20h
0x180005d7f  pop     rbx
0x180005d80  retn
```
