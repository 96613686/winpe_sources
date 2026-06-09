# CThread::~CThread(void)

- ea: `0x180006a60`
- end: `0x180006ac1`
- name: `??1CThread@@AEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CThread *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006af0`
- `0x180006d18`

## callees

- `0x180006a60`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a8e`

## pseudocode

```c
void __fastcall CThread::~CThread(CThread *this)
{
  void *v2; // rcx
  __int64 v3; // rdx
  char *v4; // rcx
  char *v5; // rbx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 1) = 0;
  }
  CloseHandle(*((HANDLE *)this + 15));
  CloseHandle(*((HANDLE *)this + 14));
  v4 = (char *)*((_QWORD *)this + 10);
  v5 = (char *)this + 24;
  if ( v4 )
  {
    LOBYTE(v3) = v4 != v5;
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v4 + 32LL))(v4, v3);
    *((_QWORD *)v5 + 7) = 0;
  }
}

```

## disassembly

```asm
0x180006a60  push    rbx
0x180006a62  sub     rsp, 20h
0x180006a66  mov     rbx, rcx
0x180006a69  mov     rcx, [rcx+8]; hObject
0x180006a6d  test    rcx, rcx
0x180006a70  jz      short loc_180006A80
0x180006a72  call    cs:__imp_CloseHandle
0x180006a78  mov     qword ptr [rbx+8], 0
0x180006a80  mov     rcx, [rbx+78h]; hObject
0x180006a84  call    cs:__imp_CloseHandle
0x180006a8a  mov     rcx, [rbx+70h]; hObject
0x180006a8e  call    cs:__imp_CloseHandle
0x180006a94  mov     rcx, [rbx+50h]
0x180006a98  add     rbx, 18h
0x180006a9c  test    rcx, rcx
0x180006a9f  jz      short loc_180006ABB
0x180006aa1  mov     rax, [rcx]
0x180006aa4  cmp     rcx, rbx
0x180006aa7  setnz   dl
0x180006aaa  mov     rax, [rax+20h]
0x180006aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ab3  mov     qword ptr [rbx+38h], 0
0x180006abb  add     rsp, 20h
0x180006abf  pop     rbx
0x180006ac0  retn
```
