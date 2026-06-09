# CRPCServiceManager::~CRPCServiceManager(void)

- ea: `0x180012424`
- end: `0x180012469`
- name: `??1CRPCServiceManager@@UEAA@XZ`
- size: `69`
- prototype: `void __fastcall(CRPCServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180012470`

## callees

- `0x180012200`
- `0x180012424`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012440`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012440`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012462`

## pseudocode

```c
void __fastcall CRPCServiceManager::~CRPCServiceManager(CRPCServiceManager *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CRPCServiceManager::`vftable';
  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
    CloseHandle(v2);
  CRequestManager::~CRequestManager((CRPCServiceManager *)((char *)this + 72));
  v3 = (void *)*((_QWORD *)this + 5);
  *(_QWORD *)this = &CGPRPCServerBase::`vftable';
  LocalFree(v3);
}

```

## disassembly

```asm
0x180012424  push    rbx
0x180012426  sub     rsp, 20h
0x18001242a  lea     rax, ??_7CRPCServiceManager@@6B@; const CRPCServiceManager::`vftable'
0x180012431  mov     rbx, rcx
0x180012434  mov     [rcx], rax
0x180012437  mov     rcx, [rcx+40h]; hObject
0x18001243b  test    rcx, rcx
0x18001243e  jz      short loc_180012446
0x180012440  call    cs:__imp_CloseHandle
0x180012446  lea     rcx, [rbx+48h]; this
0x18001244a  call    ??1CRequestManager@@QEAA@XZ; CRequestManager::~CRequestManager(void)
0x18001244f  mov     rcx, [rbx+28h]
0x180012453  lea     rax, ??_7CGPRPCServerBase@@6B@; const CGPRPCServerBase::`vftable'
0x18001245a  mov     [rbx], rax
0x18001245d  add     rsp, 20h
0x180012461  pop     rbx
0x180012462  jmp     cs:__imp_LocalFree
```
