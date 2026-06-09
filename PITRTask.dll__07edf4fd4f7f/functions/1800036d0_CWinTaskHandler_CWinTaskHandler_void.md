# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x1800036d0`
- end: `0x180003731`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180003e00`

## callees

- `0x1800036d0`
- `0x180012010`

## import_xrefs

- `msvcrt!free` at `0x180003716`
- `msvcrt!free` at `0x180003716`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036e7`

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
0x1800036d0  push    rbx
0x1800036d2  sub     rsp, 20h
0x1800036d6  mov     rbx, rcx
0x1800036d9  mov     rcx, [rcx+28h]; hObject
0x1800036dd  lea     rax, [rcx-1]
0x1800036e1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800036e5  ja      short loc_1800036F5
0x1800036e7  call    cs:__imp_CloseHandle
0x1800036ed  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x1800036f5  mov     rcx, [rbx+30h]
0x1800036f9  test    rcx, rcx
0x1800036fc  jz      short loc_180003712
0x1800036fe  mov     rax, [rcx]
0x180003701  mov     rax, [rax+10h]
0x180003705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000370a  mov     qword ptr [rbx+30h], 0
0x180003712  mov     rcx, [rbx+8]; Block
0x180003716  call    cs:__imp_free
0x18000371c  mov     qword ptr [rbx+8], 0
0x180003724  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000372b  add     rsp, 20h
0x18000372f  pop     rbx
0x180003730  retn
```
