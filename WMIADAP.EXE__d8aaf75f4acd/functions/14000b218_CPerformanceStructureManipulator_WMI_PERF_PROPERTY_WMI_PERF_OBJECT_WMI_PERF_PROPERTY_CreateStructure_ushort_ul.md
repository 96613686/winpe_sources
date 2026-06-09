# CPerformanceStructureManipulator<_WMI_PERF_PROPERTY,_WMI_PERF_OBJECT,_WMI_PERF_PROPERTY>::CreateStructure(ushort *,ulong)

- ea: `0x14000b218`
- end: `0x14000b2ba`
- name: `?CreateStructure@?$CPerformanceStructureManipulator@U_WMI_PERF_PROPERTY@@U_WMI_PERF_OBJECT@@U1@@@CAPEAU_WMI_PERF_PROPERTY@@PEAGK@Z`
- size: `162`
- prototype: `unsigned int *__fastcall(const wchar_t *Src, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b2e4`

## callees

- `0x140001a6f`
- `0x14000b218`

## import_xrefs

- `msvcrt!wcslen` at `0x14000b231`
- `msvcrt!wcslen` at `0x14000b231`
- `msvcrt!memcpy` at `0x14000b28e`
- `msvcrt!memcpy` at `0x14000b28e`
- `msvcrt!malloc` at `0x14000b264`
- `msvcrt!malloc` at `0x14000b264`

## pseudocode

```c
unsigned int *__fastcall CPerformanceStructureManipulator<_WMI_PERF_PROPERTY,_WMI_PERF_OBJECT,_WMI_PERF_PROPERTY>::CreateStructure(
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
    v8[2] = a2;
  }
  return v8;
}

```

## disassembly

```asm
0x14000b218  push    rbx
0x14000b21a  push    rsi
0x14000b21b  push    rdi
0x14000b21c  push    r12
0x14000b21e  push    r14
0x14000b220  push    r15
0x14000b222  sub     rsp, 28h
0x14000b226  mov     r15d, edx
0x14000b229  mov     rdi, rcx
0x14000b22c  test    rcx, rcx
0x14000b22f  jz      short loc_14000B239
0x14000b231  call    cs:__imp_wcslen
0x14000b237  jmp     short loc_14000B23B
0x14000b239  xor     eax, eax
0x14000b23b  lea     esi, ds:2[rax*2]
0x14000b242  mov     eax, esi
0x14000b244  and     eax, 7
0x14000b247  mov     r14d, 8
0x14000b24d  sub     r14d, eax
0x14000b250  neg     eax
0x14000b252  sbb     eax, eax
0x14000b254  and     r14d, eax
0x14000b257  add     r14d, 28h ; '('
0x14000b25b  add     r14d, esi
0x14000b25e  mov     r12d, r14d
0x14000b261  mov     ecx, r14d; Size
0x14000b264  call    cs:__imp_malloc
0x14000b26a  mov     rbx, rax
0x14000b26d  mov     [rsp+58h+arg_0], rax
0x14000b272  test    rax, rax
0x14000b275  jz      short loc_14000B2A2
0x14000b277  mov     r8d, r12d; Size
0x14000b27a  xor     edx, edx; Val
0x14000b27c  mov     rcx, rax; void *
0x14000b27f  call    memset_0
0x14000b284  mov     r8d, esi; Size
0x14000b287  lea     rcx, [rbx+24h]; void *
0x14000b28b  mov     rdx, rdi; Src
0x14000b28e  call    cs:__imp_memcpy
0x14000b294  mov     [rbx+20h], esi
0x14000b297  mov     [rbx+1Ch], r14d
0x14000b29b  mov     [rbx], r14d
0x14000b29e  mov     [rbx+8], r15d
0x14000b2a2  jmp     short loc_14000B2A9
0x14000b2a4  mov     rbx, [rsp+58h+arg_0]
0x14000b2a9  mov     rax, rbx
0x14000b2ac  add     rsp, 28h
0x14000b2b0  pop     r15
0x14000b2b2  pop     r14
0x14000b2b4  pop     r12
0x14000b2b6  pop     rdi
0x14000b2b7  pop     rsi
0x14000b2b8  pop     rbx
0x14000b2b9  retn
```
