# appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(ulong)

- ea: `0x140003770`
- end: `0x1400037f4`
- name: `?resize@?$buffer@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z`
- size: `132`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140003408`
- `0x1400034fc`
- `0x140003650`
- `0x1400065d0`
- `0x14000ae30`
- `0x140014934`
- `0x140014c40`

## callees

- `0x140003770`
- `0x140015c00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400037dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400037dc`
- `ntoskrnl!ExAllocatePool2` at `0x14000379f`
- `ntoskrnl!ExAllocatePool2` at `0x14000379f`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(
        unsigned int *a1,
        unsigned int a2)
{
  unsigned int v2; // esi
  size_t v4; // rbp
  void *v5; // rdi
  void *Pool2; // rax
  __int64 result; // rax

  v2 = a1[1];
  if ( a2 > v2 )
  {
    v4 = *a1;
    v5 = (void *)*((_QWORD *)a1 + 1);
    *a1 = a2;
    a1[1] = a2;
    Pool2 = (void *)ExAllocatePool2(256, a2, 1937073779);
    *((_QWORD *)a1 + 1) = Pool2;
    if ( !Pool2 )
    {
      *a1 = v4;
      result = 3221225626LL;
      a1[1] = v2;
      *((_QWORD *)a1 + 1) = v5;
      return result;
    }
    if ( v5 )
    {
      memmove(Pool2, v5, v4);
      ExFreePoolWithTag(v5, 0);
    }
  }
  else
  {
    *a1 = a2;
  }
  return 0;
}

```

## disassembly

```asm
0x140003770  push    rbx
0x140003772  push    rbp
0x140003773  push    rsi
0x140003774  push    rdi
0x140003775  sub     rsp, 28h
0x140003779  mov     esi, [rcx+4]
0x14000377c  mov     rbx, rcx
0x14000377f  cmp     edx, esi
0x140003781  ja      short loc_140003787
0x140003783  mov     [rcx], edx
0x140003785  jmp     short loc_1400037E8
0x140003787  mov     ebp, [rcx]
0x140003789  mov     r8d, 73756673h
0x14000378f  mov     rdi, [rcx+8]
0x140003793  mov     [rcx], edx
0x140003795  mov     [rcx+4], edx
0x140003798  mov     ecx, 100h
0x14000379d  mov     edx, edx
0x14000379f  call    cs:__imp_ExAllocatePool2
0x1400037a6  nop     dword ptr [rax+rax+00h]
0x1400037ab  mov     [rbx+8], rax
0x1400037af  test    rax, rax
0x1400037b2  jnz     short loc_1400037C4
0x1400037b4  mov     [rbx], ebp
0x1400037b6  mov     eax, 0C000009Ah
0x1400037bb  mov     [rbx+4], esi
0x1400037be  mov     [rbx+8], rdi
0x1400037c2  jmp     short loc_1400037EA
0x1400037c4  test    rdi, rdi
0x1400037c7  jz      short loc_1400037E8
0x1400037c9  mov     r8, rbp; Size
0x1400037cc  mov     rdx, rdi; Src
0x1400037cf  mov     rcx, rax; void *
0x1400037d2  call    memmove
0x1400037d7  xor     edx, edx; Tag
0x1400037d9  mov     rcx, rdi; P
0x1400037dc  call    cs:__imp_ExFreePoolWithTag
0x1400037e3  nop     dword ptr [rax+rax+00h]
0x1400037e8  xor     eax, eax
0x1400037ea  add     rsp, 28h
0x1400037ee  pop     rdi
0x1400037ef  pop     rsi
0x1400037f0  pop     rbp
0x1400037f1  pop     rbx
0x1400037f2  retn
```
