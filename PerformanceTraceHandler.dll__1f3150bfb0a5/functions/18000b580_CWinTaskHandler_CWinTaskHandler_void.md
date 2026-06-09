# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x18000b580`
- end: `0x18000b5e1`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000b5e8`
- `0x18000b8e0`

## callees

- `0x18000b580`
- `0x18001c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b5c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b5c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b597`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b597`

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
0x18000b580  push    rbx
0x18000b582  sub     rsp, 20h
0x18000b586  mov     rbx, rcx
0x18000b589  mov     rcx, [rcx+28h]; hObject
0x18000b58d  lea     rax, [rcx-1]
0x18000b591  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b595  ja      short loc_18000B5A5
0x18000b597  call    cs:__imp_CloseHandle
0x18000b59d  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x18000b5a5  mov     rcx, [rbx+30h]
0x18000b5a9  test    rcx, rcx
0x18000b5ac  jz      short loc_18000B5C2
0x18000b5ae  mov     rax, [rcx]
0x18000b5b1  mov     rax, [rax+10h]
0x18000b5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5ba  mov     qword ptr [rbx+30h], 0
0x18000b5c2  mov     rcx, [rbx+8]; Block
0x18000b5c6  call    cs:__imp_free
0x18000b5cc  mov     qword ptr [rbx+8], 0
0x18000b5d4  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000b5db  add     rsp, 20h
0x18000b5df  pop     rbx
0x18000b5e0  retn
```
