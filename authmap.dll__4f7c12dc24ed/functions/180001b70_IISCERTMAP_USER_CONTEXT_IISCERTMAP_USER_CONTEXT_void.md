# IISCERTMAP_USER_CONTEXT::~IISCERTMAP_USER_CONTEXT(void)

- ea: `0x180001b70`
- end: `0x180001bdb`
- name: `??1IISCERTMAP_USER_CONTEXT@@EEAA@XZ`
- size: `107`
- prototype: `void __fastcall(IISCERTMAP_USER_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001cb0`

## callees

- `0x180001b70`
- `0x180006d92`
- `0x180008010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180001bc0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001bc0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001bd4`

## pseudocode

```c
void __fastcall IISCERTMAP_USER_CONTEXT::~IISCERTMAP_USER_CONTEXT(IISCERTMAP_USER_CONTEXT *this)
{
  __int64 v2; // rcx
  unsigned int v3; // eax

  *(_QWORD *)this = &IISCERTMAP_USER_CONTEXT::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v3 = 2 * *((_DWORD *)this + 32);
  if ( v3 )
    memset_0(*((void **)this + 14), 0, v3);
  STRU::~STRU((IISCERTMAP_USER_CONTEXT *)((char *)this + 80));
  STRU::~STRU((IISCERTMAP_USER_CONTEXT *)((char *)this + 24));
}

```

## disassembly

```asm
0x180001b70  mov     [rsp+arg_0], rbx
0x180001b75  push    rdi
0x180001b76  sub     rsp, 20h
0x180001b7a  lea     rax, ??_7IISCERTMAP_USER_CONTEXT@@6B@; const IISCERTMAP_USER_CONTEXT::`vftable'
0x180001b81  mov     rbx, rcx
0x180001b84  mov     [rcx], rax
0x180001b87  mov     rcx, [rcx+10h]
0x180001b8b  test    rcx, rcx
0x180001b8e  jz      short loc_180001BA4
0x180001b90  mov     rax, [rcx]
0x180001b93  mov     rax, [rax+10h]
0x180001b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b9c  mov     qword ptr [rbx+10h], 0
0x180001ba4  mov     eax, [rbx+80h]
0x180001baa  add     eax, eax
0x180001bac  jz      short loc_180001BBC
0x180001bae  mov     rcx, [rbx+70h]; void *
0x180001bb2  xor     edx, edx; Val
0x180001bb4  mov     r8d, eax; Size
0x180001bb7  call    memset_0
0x180001bbc  lea     rcx, [rbx+50h]
0x180001bc0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001bc6  lea     rcx, [rbx+18h]
0x180001bca  mov     rbx, [rsp+28h+arg_0]
0x180001bcf  add     rsp, 20h
0x180001bd3  pop     rdi
0x180001bd4  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
