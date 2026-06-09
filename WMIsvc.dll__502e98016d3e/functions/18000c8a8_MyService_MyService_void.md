# MyService::~MyService(void)

- ea: `0x18000c8a8`
- end: `0x18000c8dc`
- name: `??1MyService@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(MyService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001db5b`

## callees

- `0x18000c8a8`
- `0x18000c8e4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MyService::~MyService(MyService *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &MyService::`vftable';
  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
    CloseHandle(v2);
  CNtService::~CNtService(this);
}

```

## disassembly

```asm
0x18000c8a8  mov     [rsp+arg_0], rcx
0x18000c8ad  push    rbx
0x18000c8ae  sub     rsp, 20h
0x18000c8b2  mov     rbx, rcx
0x18000c8b5  lea     rax, ??_7MyService@@6B@; const MyService::`vftable'
0x18000c8bc  mov     [rcx], rax
0x18000c8bf  mov     rcx, [rcx+40h]; hObject
0x18000c8c3  test    rcx, rcx
0x18000c8c6  jz      short loc_18000C8CF
0x18000c8c8  call    cs:__imp_CloseHandle
0x18000c8ce  nop
0x18000c8cf  mov     rcx, rbx; this
0x18000c8d2  add     rsp, 20h
0x18000c8d6  pop     rbx
0x18000c8d7  jmp     ??1CNtService@@QEAA@XZ; CNtService::~CNtService(void)
```
