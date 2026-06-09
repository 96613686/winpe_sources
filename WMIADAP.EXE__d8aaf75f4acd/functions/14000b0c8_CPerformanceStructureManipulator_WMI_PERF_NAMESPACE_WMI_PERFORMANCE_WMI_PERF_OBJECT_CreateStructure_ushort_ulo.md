# CPerformanceStructureManipulator<_WMI_PERF_NAMESPACE,_WMI_PERFORMANCE,_WMI_PERF_OBJECT>::CreateStructure(ushort *,ulong)

- ea: `0x14000b0c8`
- end: `0x14000b16a`
- name: `?CreateStructure@?$CPerformanceStructureManipulator@U_WMI_PERF_NAMESPACE@@U_WMI_PERFORMANCE@@U_WMI_PERF_OBJECT@@@@CAPEAU_WMI_PERF_NAMESPACE@@PEAGK@Z`
- size: `162`
- prototype: `unsigned int *__fastcall(const wchar_t *Src, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b2e4`

## callees

- `0x140001a6f`
- `0x14000b0c8`

## import_xrefs

- `msvcrt!wcslen` at `0x14000b0e1`
- `msvcrt!wcslen` at `0x14000b0e1`
- `msvcrt!memcpy` at `0x14000b13e`
- `msvcrt!memcpy` at `0x14000b13e`
- `msvcrt!malloc` at `0x14000b114`
- `msvcrt!malloc` at `0x14000b114`

## pseudocode

```c
unsigned int *__fastcall CPerformanceStructureManipulator<_WMI_PERF_NAMESPACE,_WMI_PERFORMANCE,_WMI_PERF_OBJECT>::CreateStructure(
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
  v6 = v5 + (((2 * (_BYTE)v4 + 2) & 7) != 0 ? 8 - ((2 * (_BYTE)v4 + 2) & 7) + 32 : 32);
  v7 = (unsigned int *)malloc(v6);
  v8 = v7;
  if ( v7 )
  {
    memset_0(v7, 0, v6);
    memcpy(v8 + 7, Src, v5);
    v8[6] = v5;
    v8[5] = v6;
    *v8 = v6;
    v8[4] = a2;
  }
  return v8;
}

```

## disassembly

```asm
0x14000b0c8  push    rbx
0x14000b0ca  push    rsi
0x14000b0cb  push    rdi
0x14000b0cc  push    r12
0x14000b0ce  push    r14
0x14000b0d0  push    r15
0x14000b0d2  sub     rsp, 28h
0x14000b0d6  mov     r15d, edx
0x14000b0d9  mov     rdi, rcx
0x14000b0dc  test    rcx, rcx
0x14000b0df  jz      short loc_14000B0E9
0x14000b0e1  call    cs:__imp_wcslen
0x14000b0e7  jmp     short loc_14000B0EB
0x14000b0e9  xor     eax, eax
0x14000b0eb  lea     esi, ds:2[rax*2]
0x14000b0f2  mov     eax, esi
0x14000b0f4  and     eax, 7
0x14000b0f7  mov     r14d, 8
0x14000b0fd  sub     r14d, eax
0x14000b100  neg     eax
0x14000b102  sbb     eax, eax
0x14000b104  and     r14d, eax
0x14000b107  add     r14d, 20h ; ' '
0x14000b10b  add     r14d, esi
0x14000b10e  mov     r12d, r14d
0x14000b111  mov     ecx, r14d; Size
0x14000b114  call    cs:__imp_malloc
0x14000b11a  mov     rbx, rax
0x14000b11d  mov     [rsp+58h+arg_0], rax
0x14000b122  test    rax, rax
0x14000b125  jz      short loc_14000B152
0x14000b127  mov     r8d, r12d; Size
0x14000b12a  xor     edx, edx; Val
0x14000b12c  mov     rcx, rax; void *
0x14000b12f  call    memset_0
0x14000b134  mov     r8d, esi; Size
0x14000b137  lea     rcx, [rbx+1Ch]; void *
0x14000b13b  mov     rdx, rdi; Src
0x14000b13e  call    cs:__imp_memcpy
0x14000b144  mov     [rbx+18h], esi
0x14000b147  mov     [rbx+14h], r14d
0x14000b14b  mov     [rbx], r14d
0x14000b14e  mov     [rbx+10h], r15d
0x14000b152  jmp     short loc_14000B159
0x14000b154  mov     rbx, [rsp+58h+arg_0]
0x14000b159  mov     rax, rbx
0x14000b15c  add     rsp, 28h
0x14000b160  pop     r15
0x14000b162  pop     r14
0x14000b164  pop     r12
0x14000b166  pop     rdi
0x14000b167  pop     rsi
0x14000b168  pop     rbx
0x14000b169  retn
```
