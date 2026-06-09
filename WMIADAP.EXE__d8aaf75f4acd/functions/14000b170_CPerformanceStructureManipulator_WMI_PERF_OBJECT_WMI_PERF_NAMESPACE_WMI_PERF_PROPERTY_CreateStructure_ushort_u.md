# CPerformanceStructureManipulator<_WMI_PERF_OBJECT,_WMI_PERF_NAMESPACE,_WMI_PERF_PROPERTY>::CreateStructure(ushort *,ulong)

- ea: `0x14000b170`
- end: `0x14000b212`
- name: `?CreateStructure@?$CPerformanceStructureManipulator@U_WMI_PERF_OBJECT@@U_WMI_PERF_NAMESPACE@@U_WMI_PERF_PROPERTY@@@@CAPEAU_WMI_PERF_OBJECT@@PEAGK@Z`
- size: `162`
- prototype: `unsigned int *__fastcall(const wchar_t *Src, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b2e4`

## callees

- `0x140001a6f`
- `0x14000b170`

## import_xrefs

- `msvcrt!wcslen` at `0x14000b189`
- `msvcrt!wcslen` at `0x14000b189`
- `msvcrt!memcpy` at `0x14000b1e6`
- `msvcrt!memcpy` at `0x14000b1e6`
- `msvcrt!malloc` at `0x14000b1bc`
- `msvcrt!malloc` at `0x14000b1bc`

## pseudocode

```c
unsigned int *__fastcall CPerformanceStructureManipulator<_WMI_PERF_OBJECT,_WMI_PERF_NAMESPACE,_WMI_PERF_PROPERTY>::CreateStructure(
        const wchar_t *Src,
        unsigned int a2)
{
  int v4; // eax
  unsigned int v5; // esi
  unsigned int v6; // r14d
  unsigned int *v7; // rax
  unsigned int *v8; // rbx

  if ( Src )
    v4 = wcslen(Src);
  else
    v4 = 0;
  v5 = 2 * v4 + 2;
  v6 = v5 + (((2 * (_BYTE)v4 + 2) & 7) != 0 ? 8 - ((2 * (_BYTE)v4 + 2) & 7) + 40 : 40);
  v7 = (unsigned int *)malloc(v6);
  v8 = v7;
  if ( v7 )
  {
    memset_0(v7, 0, v6);
    memcpy(v8 + 9, Src, v5);
    v8[8] = v5;
    v8[7] = v6;
    *v8 = v6;
    v8[4] = a2;
  }
  return v8;
}

```

## disassembly

```asm
0x14000b170  push    rbx
0x14000b172  push    rsi
0x14000b173  push    rdi
0x14000b174  push    r12
0x14000b176  push    r14
0x14000b178  push    r15
0x14000b17a  sub     rsp, 28h
0x14000b17e  mov     r15d, edx
0x14000b181  mov     rdi, rcx
0x14000b184  test    rcx, rcx
0x14000b187  jz      short loc_14000B191
0x14000b189  call    cs:__imp_wcslen
0x14000b18f  jmp     short loc_14000B193
0x14000b191  xor     eax, eax
0x14000b193  lea     esi, ds:2[rax*2]
0x14000b19a  mov     eax, esi
0x14000b19c  and     eax, 7
0x14000b19f  mov     r14d, 8
0x14000b1a5  sub     r14d, eax
0x14000b1a8  neg     eax
0x14000b1aa  sbb     eax, eax
0x14000b1ac  and     r14d, eax
0x14000b1af  add     r14d, 28h ; '('
0x14000b1b3  add     r14d, esi
0x14000b1b6  mov     r12d, r14d
0x14000b1b9  mov     ecx, r14d; Size
0x14000b1bc  call    cs:__imp_malloc
0x14000b1c2  mov     rbx, rax
0x14000b1c5  mov     [rsp+58h+arg_0], rax
0x14000b1ca  test    rax, rax
0x14000b1cd  jz      short loc_14000B1FA
0x14000b1cf  mov     r8d, r12d; Size
0x14000b1d2  xor     edx, edx; Val
0x14000b1d4  mov     rcx, rax; void *
0x14000b1d7  call    memset_0
0x14000b1dc  mov     r8d, esi; Size
0x14000b1df  lea     rcx, [rbx+24h]; void *
0x14000b1e3  mov     rdx, rdi; Src
0x14000b1e6  call    cs:__imp_memcpy
0x14000b1ec  mov     [rbx+20h], esi
0x14000b1ef  mov     [rbx+1Ch], r14d
0x14000b1f3  mov     [rbx], r14d
0x14000b1f6  mov     [rbx+10h], r15d
0x14000b1fa  jmp     short loc_14000B201
0x14000b1fc  mov     rbx, [rsp+58h+arg_0]
0x14000b201  mov     rax, rbx
0x14000b204  add     rsp, 28h
0x14000b208  pop     r15
0x14000b20a  pop     r14
0x14000b20c  pop     r12
0x14000b20e  pop     rdi
0x14000b20f  pop     rsi
0x14000b210  pop     rbx
0x14000b211  retn
```
