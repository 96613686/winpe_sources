# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180001948`
- end: `0x1800019a9`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800019f0`

## callees

- `0x180001948`
- `0x180003010`

## import_xrefs

- `msvcrt!free` at `0x18000198e`
- `msvcrt!free` at `0x18000198e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000195f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000195f`

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
0x180001948  push    rbx
0x18000194a  sub     rsp, 20h
0x18000194e  mov     rbx, rcx
0x180001951  mov     rcx, [rcx+28h]; hObject
0x180001955  lea     rax, [rcx-1]
0x180001959  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000195d  ja      short loc_18000196D
0x18000195f  call    cs:__imp_CloseHandle
0x180001965  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x18000196d  mov     rcx, [rbx+30h]
0x180001971  test    rcx, rcx
0x180001974  jz      short loc_18000198A
0x180001976  mov     rax, [rcx]
0x180001979  mov     rax, [rax+10h]
0x18000197d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001982  mov     qword ptr [rbx+30h], 0
0x18000198a  mov     rcx, [rbx+8]; Block
0x18000198e  call    cs:__imp_free
0x180001994  mov     qword ptr [rbx+8], 0
0x18000199c  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800019a3  add     rsp, 20h
0x1800019a7  pop     rbx
0x1800019a8  retn
```
