# CLinkedList::~CLinkedList(void)

- ea: `0x18000c3b0`
- end: `0x18000c406`
- name: `??1CLinkedList@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(CLinkedList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009fe0`
- `0x18000beb0`

## callees

- `0x18000c3b0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c3ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c3ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c3ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c3ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c3f5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c3f5`

## pseudocode

```c
void __fastcall CLinkedList::~CLinkedList(void (**this)(void))
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi

  if ( *((_DWORD *)this + 2) )
  {
    v2 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
    EnterCriticalSection((LPCRITICAL_SECTION)(this + 2));
    while ( *this )
    {
      *this = *(void (**)(void))*this;
      this[8]();
    }
    LeaveCriticalSection(v2);
    DeleteCriticalSection(v2);
  }
}

```

## disassembly

```asm
0x18000c3b0  mov     [rsp+arg_0], rbx
0x18000c3b5  push    rdi
0x18000c3b6  sub     rsp, 20h
0x18000c3ba  cmp     dword ptr [rcx+8], 0
0x18000c3be  mov     rbx, rcx
0x18000c3c1  jz      short loc_18000C3FB
0x18000c3c3  lea     rdi, [rcx+10h]
0x18000c3c7  mov     rcx, rdi; lpCriticalSection
0x18000c3ca  call    cs:__imp_EnterCriticalSection
0x18000c3d0  jmp     short loc_18000C3E1
0x18000c3d2  mov     rax, [rcx]
0x18000c3d5  mov     [rbx], rax
0x18000c3d8  mov     rax, [rbx+40h]
0x18000c3dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3e1  mov     rcx, [rbx]
0x18000c3e4  test    rcx, rcx
0x18000c3e7  jnz     short loc_18000C3D2
0x18000c3e9  mov     rcx, rdi; lpCriticalSection
0x18000c3ec  call    cs:__imp_LeaveCriticalSection
0x18000c3f2  mov     rcx, rdi; lpCriticalSection
0x18000c3f5  call    cs:__imp_DeleteCriticalSection
0x18000c3fb  mov     rbx, [rsp+28h+arg_0]
0x18000c400  add     rsp, 20h
0x18000c404  pop     rdi
0x18000c405  retn
```
