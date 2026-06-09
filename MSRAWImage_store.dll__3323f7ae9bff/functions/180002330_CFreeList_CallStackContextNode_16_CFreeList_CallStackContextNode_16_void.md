# CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>(void)

- ea: `0x180002330`
- end: `0x18000238d`
- name: `??1?$CFreeList@VCallStackContextNode@@$0BA@@@UEAA@XZ`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800a3140`

## callees

- `0x180002330`
- `0x1800a3178`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002381`

## pseudocode

```c
void __fastcall CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>(__int64 a1, unsigned int a2)
{
  CallStackContextNode *v3; // rcx
  CallStackContextNode *v4; // rdi

  *(_QWORD *)a1 = &CFreeList<CallStackContextNode,16>::`vftable';
  v3 = *(CallStackContextNode **)(a1 + 56);
  if ( v3 )
  {
    do
    {
      v4 = (CallStackContextNode *)*((_QWORD *)v3 + 254);
      --*(_DWORD *)(a1 + 68);
      CallStackContextNode::`scalar deleting destructor'(v3, a2);
      *(_QWORD *)(a1 + 56) = v4;
      v3 = v4;
    }
    while ( v4 );
  }
  *(_DWORD *)(a1 + 64) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
}

```

## disassembly

```asm
0x180002330  push    rbx
0x180002332  sub     rsp, 20h
0x180002336  lea     rax, ??_7?$CFreeList@VCallStackContextNode@@$0BA@@@6B@; const CFreeList<CallStackContextNode,16>::`vftable'
0x18000233d  mov     rbx, rcx
0x180002340  mov     [rcx], rax
0x180002343  mov     rcx, [rcx+38h]; this
0x180002347  test    rcx, rcx
0x18000234a  jz      short loc_180002371
0x18000234c  mov     [rsp+28h+arg_0], rdi
0x180002351  mov     rdi, [rcx+7F0h]
0x180002358  dec     dword ptr [rbx+44h]
0x18000235b  call    ??_GCallStackContextNode@@QEAAPEAXI@Z; CallStackContextNode::`scalar deleting destructor'(uint)
0x180002360  mov     [rbx+38h], rdi
0x180002364  mov     rcx, rdi
0x180002367  test    rdi, rdi
0x18000236a  jnz     short loc_180002351
0x18000236c  mov     rdi, [rsp+28h+arg_0]
0x180002371  lea     rcx, [rbx+10h]
0x180002375  mov     dword ptr [rbx+40h], 0
0x18000237c  add     rsp, 20h
0x180002380  pop     rbx
0x180002381  jmp     cs:__imp_DeleteCriticalSection
```
