# Streaming::MDLListCache::MDLListCache(ulong,ulong,ulong,long &)

- ea: `0x140013304`
- end: `0x1400133ec`
- name: `??0MDLListCache@Streaming@@QEAA@KKKAEAJ@Z`
- size: `232`
- prototype: `PPAGED_LOOKASIDE_LIST __fastcall(PPAGED_LOOKASIDE_LIST Lookaside, int, int, unsigned int, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400131fc`

## callees

- `0x140013304`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400133cc`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400133cc`
- `ntoskrnl!ExInitializeResourceLite` at `0x140013364`
- `ntoskrnl!ExInitializeResourceLite` at `0x140013364`
- `ntoskrnl!ExAllocatePool2` at `0x140013342`
- `ntoskrnl!ExAllocatePool2` at `0x140013342`

## pseudocode

```c
PPAGED_LOOKASIDE_LIST __fastcall Streaming::MDLListCache::MDLListCache(
        PPAGED_LOOKASIDE_LIST Lookaside,
        int a2,
        int a3,
        unsigned int a4,
        int *a5)
{
  SIZE_T Size; // rdi
  struct _ERESOURCE *Pool2; // rax
  NTSTATUS v9; // eax
  ULONG Tag; // [rsp+28h] [rbp-20h]

  LODWORD(Lookaside[1].L.ListHead.Alignment) = a3;
  *(_QWORD *)&Lookaside[1].L.Depth = 0;
  Size = a4;
  *((_DWORD *)&Lookaside[1].L.SingleListHead + 2) = 1819108979;
  Pool2 = (struct _ERESOURCE *)ExAllocatePool2(64, 104, 1819108979);
  *(_QWORD *)&Lookaside[1].L.Depth = Pool2;
  if ( Pool2 )
    v9 = ExInitializeResourceLite(Pool2);
  else
    v9 = -1073741670;
  *a5 = v9;
  *(_QWORD *)&Lookaside[1].L.FreeMisses = 0;
  *(_QWORD *)&Lookaside[1].L.Tag = 0;
  Lookaside[1].L.FreeEx = (PFREE_FUNCTION_EX)&Lookaside[1].L.FreeMisses;
  Lookaside[1].L.AllocateEx = (PALLOCATE_FUNCTION_EX)&Lookaside[1].L.FreeMisses;
  Lookaside[1].L.AllocateMisses = 0;
  Tag = Lookaside[1].L.ListHead.Alignment;
  LODWORD(Lookaside[1].L.ListEntry.Flink) = a2;
  HIDWORD(Lookaside[1].L.ListEntry.Flink) = Size;
  ExInitializePagedLookasideList(Lookaside, 0, 0, 0, Size, Tag, 0);
  return Lookaside;
}

```

## disassembly

```asm
0x140013304  mov     [rsp+arg_0], rbx
0x140013309  mov     [rsp+arg_8], rsi
0x14001330e  push    rdi
0x14001330f  sub     rsp, 40h
0x140013313  mov     [rcx+80h], r8d
0x14001331a  mov     esi, edx
0x14001331c  mov     edx, 68h ; 'h'
0x140013321  mov     qword ptr [rcx+90h], 0
0x14001332c  mov     r8d, 6C6D6673h
0x140013332  mov     edi, r9d
0x140013335  mov     rbx, rcx
0x140013338  mov     [rcx+88h], r8d
0x14001333f  lea     ecx, [rdx-28h]
0x140013342  call    cs:__imp_ExAllocatePool2
0x140013349  nop     dword ptr [rax+rax+00h]
0x14001334e  mov     [rbx+90h], rax
0x140013355  test    rax, rax
0x140013358  jnz     short loc_140013361
0x14001335a  mov     eax, 0C000009Ah
0x14001335f  jmp     short loc_140013370
0x140013361  mov     rcx, rax; Resource
0x140013364  call    cs:__imp_ExInitializeResourceLite
0x14001336b  nop     dword ptr [rax+rax+00h]
0x140013370  mov     rcx, [rsp+48h+arg_20]
0x140013375  xor     r9d, r9d; Flags
0x140013378  xor     r8d, r8d; Free
0x14001337b  xor     edx, edx; Allocate
0x14001337d  mov     [rcx], eax
0x14001337f  lea     rax, [rbx+0A0h]
0x140013386  mov     qword ptr [rax], 0
0x14001338d  mov     rcx, rbx; Lookaside
0x140013390  mov     qword ptr [rax+8], 0
0x140013398  mov     [rax+18h], rax
0x14001339c  mov     [rax+10h], rax
0x1400133a0  xor     eax, eax
0x1400133a2  mov     [rsp+48h+Depth], ax; Depth
0x1400133a7  mov     dword ptr [rbx+98h], 0
0x1400133b1  mov     eax, [rbx+80h]
0x1400133b7  mov     [rsp+48h+Tag], eax; Tag
0x1400133bb  mov     [rsp+48h+Size], rdi; Size
0x1400133c0  mov     [rbx+0C0h], esi
0x1400133c6  mov     [rbx+0C4h], edi
0x1400133cc  call    cs:__imp_ExInitializePagedLookasideList
0x1400133d3  nop     dword ptr [rax+rax+00h]
0x1400133d8  mov     rsi, [rsp+48h+arg_8]
0x1400133dd  mov     rax, rbx
0x1400133e0  mov     rbx, [rsp+48h+arg_0]
0x1400133e5  add     rsp, 40h
0x1400133e9  pop     rdi
0x1400133ea  retn
```
