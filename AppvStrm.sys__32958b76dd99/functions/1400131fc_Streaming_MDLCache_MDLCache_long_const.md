# Streaming::MDLCache::MDLCache(long * const)

- ea: `0x1400131fc`
- end: `0x1400132fb`
- name: `??0MDLCache@Streaming@@AEAA@QEAJ@Z`
- size: `255`
- prototype: `struct _PAGED_LOOKASIDE_LIST *__fastcall(struct _PAGED_LOOKASIDE_LIST *this, int *const)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400135b4`

## callees

- `0x1400131fc`
- `0x140013304`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x1400132b5`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400132b5`
- `ntoskrnl!ExAllocatePool2` at `0x140013293`
- `ntoskrnl!ExAllocatePool2` at `0x140013293`

## pseudocode

```c
struct _PAGED_LOOKASIDE_LIST *__fastcall Streaming::MDLCache::MDLCache(
        struct _PAGED_LOOKASIDE_LIST *this,
        int *const a2)
{
  struct _ERESOURCE *Pool2; // rax
  NTSTATUS v5; // eax
  struct _PAGED_LOOKASIDE_LIST *result; // rax

  Streaming::MDLListCache::MDLListCache(this, 0xFu, 0x316D6673u, 0x1000u, a2);
  Streaming::MDLListCache::MDLListCache(this + 2, 0xFu, 0x326D6673u, 0x20000u, a2 + 1);
  Streaming::MDLListCache::MDLListCache(this + 4, 5u, 0x336D6673u, 0x100000u, a2 + 2);
  this[6].L.ListHead.Region = 0;
  LODWORD(this[6].L.ListHead.Alignment) = 1819108979;
  Pool2 = (struct _ERESOURCE *)ExAllocatePool2(64, 104, 1819108979);
  this[6].L.ListHead.Region = (ULONGLONG)Pool2;
  if ( Pool2 )
    v5 = ExInitializeResourceLite(Pool2);
  else
    v5 = -1073741670;
  a2[3] = v5;
  *(_QWORD *)&this[6].L.AllocateMisses = 0;
  *(_QWORD *)&this[6].L.FreeMisses = 0;
  this[6].L.AllocateEx = (PALLOCATE_FUNCTION_EX)&this[6].L.AllocateMisses;
  *(_QWORD *)&this[6].L.Tag = (char *)this + 792;
  result = this;
  *(_DWORD *)&this[6].L.Depth = 0;
  return result;
}

```

## disassembly

```asm
0x1400131fc  mov     [rsp+arg_0], rbx
0x140013201  push    rdi
0x140013202  sub     rsp, 30h
0x140013206  mov     rdi, rdx
0x140013209  mov     [rsp+38h+var_18], rdx; int *
0x14001320e  mov     edx, 0Fh; unsigned int
0x140013213  mov     r9d, 1000h; unsigned int
0x140013219  mov     r8d, 316D6673h; unsigned int
0x14001321f  mov     rbx, rcx
0x140013222  call    ??0MDLListCache@Streaming@@QEAA@KKKAEAJ@Z; Streaming::MDLListCache::MDLListCache(ulong,ulong,ulong,long &)
0x140013227  lea     rax, [rdi+4]
0x14001322b  mov     edx, 0Fh; unsigned int
0x140013230  lea     rcx, [rbx+100h]; Lookaside
0x140013237  mov     [rsp+38h+var_18], rax; int *
0x14001323c  mov     r9d, 20000h; unsigned int
0x140013242  mov     r8d, 326D6673h; unsigned int
0x140013248  call    ??0MDLListCache@Streaming@@QEAA@KKKAEAJ@Z; Streaming::MDLListCache::MDLListCache(ulong,ulong,ulong,long &)
0x14001324d  lea     rax, [rdi+8]
0x140013251  mov     edx, 5; unsigned int
0x140013256  lea     rcx, [rbx+200h]; Lookaside
0x14001325d  mov     [rsp+38h+var_18], rax; int *
0x140013262  mov     r9d, 100000h; unsigned int
0x140013268  mov     r8d, 336D6673h; unsigned int
0x14001326e  call    ??0MDLListCache@Streaming@@QEAA@KKKAEAJ@Z; Streaming::MDLListCache::MDLListCache(ulong,ulong,ulong,long &)
0x140013273  mov     edx, 68h ; 'h'
0x140013278  mov     qword ptr [rbx+308h], 0
0x140013283  mov     r8d, 6C6D6673h
0x140013289  mov     [rbx+300h], r8d
0x140013290  lea     ecx, [rdx-28h]
0x140013293  call    cs:__imp_ExAllocatePool2
0x14001329a  nop     dword ptr [rax+rax+00h]
0x14001329f  mov     [rbx+308h], rax
0x1400132a6  test    rax, rax
0x1400132a9  jnz     short loc_1400132B2
0x1400132ab  mov     eax, 0C000009Ah
0x1400132b0  jmp     short loc_1400132C1
0x1400132b2  mov     rcx, rax; Resource
0x1400132b5  call    cs:__imp_ExInitializeResourceLite
0x1400132bc  nop     dword ptr [rax+rax+00h]
0x1400132c1  mov     [rdi+0Ch], eax
0x1400132c4  lea     rax, [rbx+318h]
0x1400132cb  mov     qword ptr [rax], 0
0x1400132d2  mov     qword ptr [rax+8], 0
0x1400132da  mov     [rax+18h], rax
0x1400132de  mov     [rax+10h], rax
0x1400132e2  mov     rax, rbx
0x1400132e5  mov     dword ptr [rbx+310h], 0
0x1400132ef  mov     rbx, [rsp+38h+arg_0]
0x1400132f4  add     rsp, 30h
0x1400132f8  pop     rdi
0x1400132f9  retn
```
