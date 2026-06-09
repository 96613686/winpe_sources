# CWinTaskHandler::~CWinTaskHandler(void)

- ea: `0x1800035dc`
- end: `0x18000363d`
- name: `??1CWinTaskHandler@@MEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180003800`

## callees

- `0x1800035dc`
- `0x180015010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003622`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003622`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035f3`

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
0x1800035dc  push    rbx
0x1800035de  sub     rsp, 20h
0x1800035e2  mov     rbx, rcx
0x1800035e5  mov     rcx, [rcx+28h]; hObject
0x1800035e9  lea     rax, [rcx-1]
0x1800035ed  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800035f1  ja      short loc_180003601
0x1800035f3  call    cs:__imp_CloseHandle
0x1800035f9  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180003601  mov     rcx, [rbx+30h]
0x180003605  test    rcx, rcx
0x180003608  jz      short loc_18000361E
0x18000360a  mov     rax, [rcx]
0x18000360d  mov     rax, [rax+10h]
0x180003611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003616  mov     qword ptr [rbx+30h], 0
0x18000361e  mov     rcx, [rbx+8]; Block
0x180003622  call    cs:__imp_free
0x180003628  mov     qword ptr [rbx+8], 0
0x180003630  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180003637  add     rsp, 20h
0x18000363b  pop     rbx
0x18000363c  retn
```
