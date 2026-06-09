# BfsFreeDirectoryBlockList

- ea: `0x140011994`
- end: `0x1400119f7`
- name: `BfsFreeDirectoryBlockList`
- size: `99`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001093c`
- `0x140011404`
- `0x1400123fc`

## callees

- `0x140011994`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400119c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400119d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400119c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400119d6`

## pseudocode

```c
void __fastcall BfsFreeDirectoryBlockList(void **a1)
{
  void *v2; // rbx
  void **v3; // rax

  while ( 1 )
  {
    v2 = *a1;
    if ( *a1 == a1 )
      break;
    if ( *((void ***)v2 + 1) != a1 || (v3 = *(void ***)v2, *(void **)(*(_QWORD *)v2 + 8LL) != v2) )
      __fastfail(3u);
    *a1 = v3;
    v3[1] = a1;
    ExFreePoolWithTag(*((PVOID *)v2 + 2), 0);
    ExFreePoolWithTag(v2, 0);
  }
}

```

## disassembly

```asm
0x140011994  mov     [rsp+arg_0], rbx
0x140011999  push    rdi
0x14001199a  sub     rsp, 20h
0x14001199e  mov     rdi, rcx
0x1400119a1  mov     rbx, [rdi]
0x1400119a4  cmp     rbx, rdi
0x1400119a7  jz      short loc_1400119EB
0x1400119a9  cmp     [rbx+8], rdi
0x1400119ad  jnz     short loc_1400119E4
0x1400119af  mov     rax, [rbx]
0x1400119b2  cmp     [rax+8], rbx
0x1400119b6  jnz     short loc_1400119E4
0x1400119b8  mov     [rdi], rax
0x1400119bb  xor     edx, edx; Tag
0x1400119bd  mov     [rax+8], rdi
0x1400119c1  mov     rcx, [rbx+10h]; P
0x1400119c5  call    cs:__imp_ExFreePoolWithTag
0x1400119cc  nop     dword ptr [rax+rax+00h]
0x1400119d1  xor     edx, edx; Tag
0x1400119d3  mov     rcx, rbx; P
0x1400119d6  call    cs:__imp_ExFreePoolWithTag
0x1400119dd  nop     dword ptr [rax+rax+00h]
0x1400119e2  jmp     short loc_1400119A1
0x1400119e4  mov     ecx, 3
0x1400119e9  int     29h; Win8: RtlFailFast(ecx)
0x1400119eb  mov     rbx, [rsp+28h+arg_0]
0x1400119f0  add     rsp, 20h
0x1400119f4  pop     rdi
0x1400119f5  retn
```
