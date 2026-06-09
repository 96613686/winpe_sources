# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180003774`
- end: `0x1800037d5`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180003bc0`

## callees

- `0x180003774`
- `0x18000a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800037ba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800037ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000378b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000378b`

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
0x180003774  push    rbx
0x180003776  sub     rsp, 20h
0x18000377a  mov     rbx, rcx
0x18000377d  mov     rcx, [rcx+28h]; hObject
0x180003781  lea     rax, [rcx-1]
0x180003785  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003789  ja      short loc_180003799
0x18000378b  call    cs:__imp_CloseHandle
0x180003791  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180003799  mov     rcx, [rbx+30h]
0x18000379d  test    rcx, rcx
0x1800037a0  jz      short loc_1800037B6
0x1800037a2  mov     rax, [rcx]
0x1800037a5  mov     rax, [rax+10h]
0x1800037a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037ae  mov     qword ptr [rbx+30h], 0
0x1800037b6  mov     rcx, [rbx+8]; Block
0x1800037ba  call    cs:__imp_free
0x1800037c0  mov     qword ptr [rbx+8], 0
0x1800037c8  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800037cf  add     rsp, 20h
0x1800037d3  pop     rbx
0x1800037d4  retn
```
