# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x180012dc8`
- end: `0x180012e29`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180014f90`
- `0x180023070`

## callees

- `0x180012dc8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012e0e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012e0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ddf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ddf`

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
0x180012dc8  push    rbx
0x180012dca  sub     rsp, 20h
0x180012dce  mov     rbx, rcx
0x180012dd1  mov     rcx, [rcx+28h]; hObject
0x180012dd5  lea     rax, [rcx-1]
0x180012dd9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012ddd  ja      short loc_180012DED
0x180012ddf  call    cs:__imp_CloseHandle
0x180012de5  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180012ded  mov     rcx, [rbx+30h]
0x180012df1  test    rcx, rcx
0x180012df4  jz      short loc_180012E0A
0x180012df6  mov     rax, [rcx]
0x180012df9  mov     rax, [rax+10h]
0x180012dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e02  mov     qword ptr [rbx+30h], 0
0x180012e0a  mov     rcx, [rbx+8]; Block
0x180012e0e  call    cs:__imp_free
0x180012e14  mov     qword ptr [rbx+8], 0
0x180012e1c  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180012e23  add     rsp, 20h
0x180012e27  pop     rbx
0x180012e28  retn
```
