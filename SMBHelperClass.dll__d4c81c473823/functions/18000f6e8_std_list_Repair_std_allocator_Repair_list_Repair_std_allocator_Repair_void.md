# std::list<Repair *,std::allocator<Repair *>>::~list<Repair *,std::allocator<Repair *>>(void)

- ea: `0x18000f6e8`
- end: `0x18000f73d`
- name: `??1?$list@PEAVRepair@@V?$allocator@PEAVRepair@@@std@@@std@@QEAA@XZ`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x1800113df`

## callees

- `0x18000f6e8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f71b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f71b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f736`

## pseudocode

```c
void __fastcall std::list<Repair *>::~list<Repair *>(__int64 a1)
{
  _QWORD *v2; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  v2 = **(_QWORD ***)a1;
  **(_QWORD **)a1 = *(_QWORD *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = *(_QWORD *)a1;
  *(_QWORD *)(a1 + 8) = 0;
  v3 = *(_QWORD **)a1;
  if ( v2 != v3 )
  {
    do
    {
      v4 = (_QWORD *)*v2;
      operator delete(v2);
      v3 = *(_QWORD **)a1;
      v2 = v4;
    }
    while ( v4 != *(_QWORD **)a1 );
  }
  operator delete(v3);
}

```

## disassembly

```asm
0x18000f6e8  mov     [rsp+arg_0], rbx
0x18000f6ed  push    rdi
0x18000f6ee  sub     rsp, 20h
0x18000f6f2  mov     rax, [rcx]
0x18000f6f5  mov     rdi, rcx
0x18000f6f8  mov     rdx, [rax]
0x18000f6fb  mov     [rax], rax
0x18000f6fe  mov     rax, [rcx]
0x18000f701  mov     [rax+8], rax
0x18000f705  mov     qword ptr [rcx+8], 0
0x18000f70d  mov     rcx, [rcx]
0x18000f710  cmp     rdx, rcx
0x18000f713  jz      short loc_18000F72C
0x18000f715  mov     rbx, [rdx]
0x18000f718  mov     rcx, rdx
0x18000f71b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f721  mov     rcx, [rdi]
0x18000f724  mov     rdx, rbx
0x18000f727  cmp     rbx, rcx
0x18000f72a  jnz     short loc_18000F715
0x18000f72c  mov     rbx, [rsp+28h+arg_0]
0x18000f731  add     rsp, 20h
0x18000f735  pop     rdi
0x18000f736  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
