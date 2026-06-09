# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x18000385c`
- end: `0x1800038bd`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800039d0`

## callees

- `0x18000385c`
- `0x180018010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800038a2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800038a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003873`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003873`

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
0x18000385c  push    rbx
0x18000385e  sub     rsp, 20h
0x180003862  mov     rbx, rcx
0x180003865  mov     rcx, [rcx+28h]; hObject
0x180003869  lea     rax, [rcx-1]
0x18000386d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003871  ja      short loc_180003881
0x180003873  call    cs:__imp_CloseHandle
0x180003879  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180003881  mov     rcx, [rbx+30h]
0x180003885  test    rcx, rcx
0x180003888  jz      short loc_18000389E
0x18000388a  mov     rax, [rcx]
0x18000388d  mov     rax, [rax+10h]
0x180003891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003896  mov     qword ptr [rbx+30h], 0
0x18000389e  mov     rcx, [rbx+8]; Block
0x1800038a2  call    cs:__imp_free
0x1800038a8  mov     qword ptr [rbx+8], 0
0x1800038b0  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800038b7  add     rsp, 20h
0x1800038bb  pop     rbx
0x1800038bc  retn
```
