# SIDKeyCopyBuffer(ulong,uchar *,ulong *,uchar * *)

- ea: `0x1800107e0`
- end: `0x180010847`
- name: `?SIDKeyCopyBuffer@@YAJKPEAEPEAKPEAPEAE@Z`
- size: `103`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int8 *Src, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1800107e0`
- `0x180010920`
- `0x180010950`
- `0x18001a6ac`

## pseudocode

```c
__int64 __fastcall SIDKeyCopyBuffer(unsigned int a1, unsigned __int8 *Src, unsigned int *a3, unsigned __int8 **a4)
{
  size_t v4; // rbp
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // rbx
  unsigned int v10; // ebx

  v4 = a1;
  *a3 = 0;
  *a4 = 0;
  v8 = (unsigned __int8 *)SIDKeyProvAlloc(a1);
  v9 = v8;
  if ( v8 )
  {
    memcpy_0(v8, Src, v4);
    *a3 = v4;
    *a4 = v9;
    v10 = 0;
  }
  else
  {
    v10 = -2147024882;
  }
  SIDKeyProvFree(0);
  return v10;
}

```

## disassembly

```asm
0x1800107e0  push    rbx
0x1800107e2  push    rbp
0x1800107e3  push    rsi
0x1800107e4  push    rdi
0x1800107e5  push    r14
0x1800107e7  push    r15
0x1800107e9  sub     rsp, 28h
0x1800107ed  mov     ebp, ecx
0x1800107ef  mov     rdi, r9
0x1800107f2  mov     dword ptr [r8], 0
0x1800107f9  mov     rsi, r8
0x1800107fc  mov     ecx, ecx; unsigned __int64
0x1800107fe  mov     r15, rdx
0x180010801  mov     qword ptr [r9], 0
0x180010808  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18001080d  mov     rbx, rax
0x180010810  test    rax, rax
0x180010813  jnz     short loc_18001081C
0x180010815  mov     ebx, 8007000Eh
0x18001081a  jmp     short loc_180010831
0x18001081c  mov     r8, rbp; Size
0x18001081f  mov     rdx, r15; Src
0x180010822  mov     rcx, rbx; void *
0x180010825  call    memcpy_0
0x18001082a  mov     [rsi], ebp
0x18001082c  mov     [rdi], rbx
0x18001082f  xor     ebx, ebx
0x180010831  xor     ecx, ecx; lpMem
0x180010833  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180010838  mov     eax, ebx
0x18001083a  add     rsp, 28h
0x18001083e  pop     r15
0x180010840  pop     r14
0x180010842  pop     rdi
0x180010843  pop     rsi
0x180010844  pop     rbp
0x180010845  pop     rbx
0x180010846  retn
```
