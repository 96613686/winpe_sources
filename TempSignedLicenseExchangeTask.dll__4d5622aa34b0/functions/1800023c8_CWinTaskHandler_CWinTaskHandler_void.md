# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x1800023c8`
- end: `0x180002429`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002470`

## callees

- `0x1800023c8`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000240e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000240e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800023df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800023df`

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
0x1800023c8  push    rbx
0x1800023ca  sub     rsp, 20h
0x1800023ce  mov     rbx, rcx
0x1800023d1  mov     rcx, [rcx+28h]; hObject
0x1800023d5  lea     rax, [rcx-1]
0x1800023d9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800023dd  ja      short loc_1800023ED
0x1800023df  call    cs:__imp_CloseHandle
0x1800023e5  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x1800023ed  mov     rcx, [rbx+30h]
0x1800023f1  test    rcx, rcx
0x1800023f4  jz      short loc_18000240A
0x1800023f6  mov     rax, [rcx]
0x1800023f9  mov     rax, [rax+10h]
0x1800023fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002402  mov     qword ptr [rbx+30h], 0
0x18000240a  mov     rcx, [rbx+8]; Block
0x18000240e  call    cs:__imp_free
0x180002414  mov     qword ptr [rbx+8], 0
0x18000241c  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180002423  add     rsp, 20h
0x180002427  pop     rbx
0x180002428  retn
```
