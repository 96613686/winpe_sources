# ATL::CAtlArray<IEnhancedStorageSiloAction *,ATL::CElementTraits<IEnhancedStorageSiloAction *>>::GrowBuffer(unsigned __int64)

- ea: `0x180006260`
- end: `0x180006328`
- name: `?GrowBuffer@?$CAtlArray@PEAUIEnhancedStorageSiloAction@@V?$CElementTraits@PEAUIEnhancedStorageSiloAction@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009b6c`

## callees

- `0x180006260`
- `0x180008570`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800062f9`
- `msvcrt!memmove_s` at `0x1800062f9`
- `msvcrt!calloc` at `0x18000629b`
- `msvcrt!calloc` at `0x1800062d6`
- `msvcrt!calloc` at `0x18000629b`
- `msvcrt!calloc` at `0x1800062d6`
- `msvcrt!free` at `0x180006309`
- `msvcrt!free` at `0x180006309`

## pseudocode

```c
char __fastcall ATL::CAtlArray<IEnhancedStorageSiloAction *,ATL::CElementTraits<IEnhancedStorageSiloAction *>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  unsigned __int64 v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 > v4 )
  {
    v5 = *(int *)(a1 + 24);
    if ( *(_QWORD *)a1 )
    {
      if ( !v5 )
      {
        v5 = v4 >> 1;
        if ( a2 - v4 > v4 >> 1 )
          v5 = a2 - v4;
      }
      if ( a2 < v4 + v5 )
        a2 = v4 + v5;
      v7 = calloc(a2, 8u);
      v8 = v7;
      if ( !v7 )
        return 0;
      v10 = memmove_s(v7, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
      ATL::AtlCrtErrorCheck(v10);
      free(*(void **)a1);
      *(_QWORD *)a1 = v8;
    }
    else
    {
      if ( v5 > a2 )
        a2 = v5;
      v6 = calloc(a2, 8u);
      *(_QWORD *)a1 = v6;
      if ( !v6 )
        return 0;
    }
    *(_QWORD *)(a1 + 16) = a2;
  }
  return 1;
}

```

## disassembly

```asm
0x180006260  mov     [rsp+arg_0], rbx
0x180006265  mov     [rsp+arg_8], rsi
0x18000626a  push    rdi
0x18000626b  sub     rsp, 20h
0x18000626f  mov     rbx, rdx
0x180006272  mov     rdi, rcx
0x180006275  mov     rdx, [rcx+10h]
0x180006279  cmp     rbx, rdx
0x18000627c  jbe     loc_180006316
0x180006282  cmp     qword ptr [rdi], 0
0x180006286  movsxd  rcx, dword ptr [rcx+18h]
0x18000628a  jnz     short loc_1800062AB
0x18000628c  cmp     rcx, rbx
0x18000628f  mov     edx, 8; Size
0x180006294  cmova   rbx, rcx
0x180006298  mov     rcx, rbx; Count
0x18000629b  call    cs:__imp_calloc
0x1800062a1  mov     [rdi], rax
0x1800062a4  test    rax, rax
0x1800062a7  jnz     short loc_180006312
0x1800062a9  jmp     short loc_1800062E4
0x1800062ab  test    rcx, rcx
0x1800062ae  jnz     short loc_1800062C3
0x1800062b0  mov     rcx, rdx
0x1800062b3  mov     rax, rbx
0x1800062b6  shr     rcx, 1
0x1800062b9  sub     rax, rdx
0x1800062bc  cmp     rax, rcx
0x1800062bf  cmova   rcx, rax
0x1800062c3  lea     rax, [rdx+rcx]
0x1800062c7  mov     edx, 8; Size
0x1800062cc  cmp     rbx, rax
0x1800062cf  cmovb   rbx, rax
0x1800062d3  mov     rcx, rbx; Count
0x1800062d6  call    cs:__imp_calloc
0x1800062dc  mov     rsi, rax
0x1800062df  test    rax, rax
0x1800062e2  jnz     short loc_1800062E8
0x1800062e4  xor     al, al
0x1800062e6  jmp     short loc_180006318
0x1800062e8  mov     rdx, [rdi+8]
0x1800062ec  mov     rcx, rsi; Destination
0x1800062ef  mov     r8, [rdi]; Source
0x1800062f2  shl     rdx, 3; DestinationSize
0x1800062f6  mov     r9, rdx; SourceSize
0x1800062f9  call    cs:__imp_memmove_s
0x1800062ff  mov     ecx, eax; int
0x180006301  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006306  mov     rcx, [rdi]; Block
0x180006309  call    cs:__imp_free
0x18000630f  mov     [rdi], rsi
0x180006312  mov     [rdi+10h], rbx
0x180006316  mov     al, 1
0x180006318  mov     rbx, [rsp+28h+arg_0]
0x18000631d  mov     rsi, [rsp+28h+arg_8]
0x180006322  add     rsp, 20h
0x180006326  pop     rdi
0x180006327  retn
```
