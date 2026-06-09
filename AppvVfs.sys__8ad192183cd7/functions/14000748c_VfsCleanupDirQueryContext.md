# VfsCleanupDirQueryContext

- ea: `0x14000748c`
- end: `0x1400074eb`
- name: `VfsCleanupDirQueryContext`
- size: `95`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140006a60`
- `0x1400076d0`
- `0x140007a14`

## callees

- `0x14000748c`
- `0x140007a48`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400074a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400074a0`

## pseudocode

```c
void __fastcall VfsCleanupDirQueryContext(__int64 a1)
{
  void *v2; // rcx
  _QWORD **v3; // rbx
  _QWORD *v4; // rcx
  _QWORD *v5; // rax

  v2 = *(void **)(a1 + 48);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    *(_QWORD *)(a1 + 48) = 0;
  }
  v3 = (_QWORD **)(a1 + 8);
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == v3 )
      break;
    if ( (_QWORD **)v4[1] != v3 || (v5 = (_QWORD *)*v4, *(_QWORD **)(*v4 + 8LL) != v4) )
      __fastfail(3u);
    *v3 = v5;
    v5[1] = v3;
    VfsDeleteDirQuerySubContext(v4);
  }
}

```

## disassembly

```asm
0x14000748c  push    rbx
0x14000748e  sub     rsp, 20h
0x140007492  mov     rbx, rcx
0x140007495  mov     rcx, [rcx+30h]; P
0x140007499  test    rcx, rcx
0x14000749c  jz      short loc_1400074B4
0x14000749e  xor     edx, edx; Tag
0x1400074a0  call    cs:__imp_ExFreePoolWithTag
0x1400074a7  nop     dword ptr [rax+rax+00h]
0x1400074ac  mov     qword ptr [rbx+30h], 0
0x1400074b4  add     rbx, 8
0x1400074b8  mov     rcx, [rbx]; Entry
0x1400074bb  cmp     rcx, rbx
0x1400074be  jz      short loc_1400074E4
0x1400074c0  cmp     [rcx+8], rbx
0x1400074c4  jnz     short loc_1400074DD
0x1400074c6  mov     rax, [rcx]
0x1400074c9  cmp     [rax+8], rcx
0x1400074cd  jnz     short loc_1400074DD
0x1400074cf  mov     [rbx], rax
0x1400074d2  mov     [rax+8], rbx
0x1400074d6  call    VfsDeleteDirQuerySubContext
0x1400074db  jmp     short loc_1400074B8
0x1400074dd  mov     ecx, 3
0x1400074e2  int     29h; Win8: RtlFailFast(ecx)
0x1400074e4  add     rsp, 20h
0x1400074e8  pop     rbx
0x1400074e9  retn
```
