# ApphelpCreateAppcompatData

- ea: `0x180001ea0`
- end: `0x18000210f`
- name: `ApphelpCreateAppcompatData`
- size: `623`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001730`
- `0x180001ce4`
- `0x180001ea0`
- `0x180002be0`
- `0x180008a04`
- `0x18000f114`
- `0x180015fb0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180001f20`
- `ntdll!RtlAllocateHeap` at `0x180001f20`

## string_xrefs

- `0x180001f3f`: `ApphelpCreateAppcompatData`
- `0x180001fe1`: `ApphelpCreateAppcompatData`
- `0x18000208e`: `ApphelpCreateAppcompatData`
- `0x1800020ea`: `ApphelpCreateAppcompatData`

## pseudocode

```c
__int64 __fastcall ApphelpCreateAppcompatData(
        unsigned __int16 a1,
        int a2,
        _QWORD *a3,
        _DWORD *a4,
        PVOID *a5,
        unsigned int *a6)
{
  _DWORD *v10; // rbx
  _DWORD *Heap; // rax
  void *inited; // rdi
  unsigned int v13; // r15d
  unsigned __int64 i; // rsi
  int v15; // ecx

  if ( !a4 || !a3 || *a4 && !*a3 )
  {
    AslLogCallPrintf(1, "ApphelpCreateAppcompatData", 840, "Called with invalid parameters");
    return 1;
  }
  if ( a2 && (a2 & 0xF) == 0 )
  {
    AslLogCallPrintf(1, "ApphelpCreateAppcompatData", 846, "Called with invalid flags");
    return 1;
  }
  v10 = (_DWORD *)*a3;
  if ( !*a3 && !*a4 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x1C8u);
    v10 = Heap;
    if ( !Heap )
    {
      AslLogCallPrintf(1, "ApphelpCreateAppcompatData", 863, "Failed to allocate %d bytes", 456);
      return 1;
    }
    *a4 = 456;
    *a3 = Heap;
  }
  if ( *a4 != 456 )
    return 1;
  inited = 0;
  v13 = (v10[48] >> 10) & 8 | 0x10;
  if ( (v10[48] & 0x4000) == 0 )
    v13 = (v10[48] >> 10) & 8;
  for ( i = 0; i < 4; ++i )
  {
    if ( (a2 & qword_180080420[2 * i]) != 0 )
    {
      if ( !inited )
      {
        inited = (void *)SdbInitDatabaseEx(v13, 0, a1);
        if ( !inited )
        {
          AslLogCallPrintf(1, "ApphelpCreateAppcompatData", 898, "Failed to initialize database.");
          return 1;
        }
      }
      if ( !(unsigned int)SdbAddExeTagRefToQuery(inited, v10, qword_180080420[2 * i + 1]) )
        AslLogCallPrintf(1, "ApphelpCreateAppcompatData", 904, "Failed to add exe ref");
    }
  }
  if ( *v10 || v10[32] || v10[41] || (v10[48] & 0x40) != 0 )
  {
    if ( !inited )
    {
      inited = (void *)SdbInitDatabaseEx(v13, 0, a1);
      if ( !inited )
      {
        AslLogCallPrintf(1, "ApphelpCreateAppcompatData", 917, "Failed to initialize database.");
        return 1;
      }
    }
    if ( !(unsigned int)SdbPackAppCompatData((__int64)inited, (__int64)v10, a5, a6) )
    {
      AslLogCallPrintf(1, "ApphelpCreateAppcompatData", 928, "Failed to pack data.");
      goto LABEL_40;
    }
    v15 = v10[48] & 2;
    if ( (v10[48] & 1) != 0 )
    {
      if ( !v15 )
        goto LABEL_40;
      goto LABEL_39;
    }
    if ( v15 || (unsigned int)IsEventFilteringEnabled() )
LABEL_39:
      *((_DWORD *)*a5 + 132) = 0;
  }
LABEL_40:
  if ( inited )
    SdbReleaseDatabase(inited);
  return 1;
}

```

## disassembly

```asm
0x180001ea0  push    rbx
0x180001ea2  push    rbp
0x180001ea3  push    rsi
0x180001ea4  push    rdi
0x180001ea5  push    r12
0x180001ea7  push    r14
0x180001ea9  push    r15
0x180001eab  sub     rsp, 30h
0x180001eaf  mov     rsi, r9
0x180001eb2  mov     rdi, r8
0x180001eb5  mov     r14d, edx
0x180001eb8  movzx   r12d, cx
0x180001ebc  test    r9, r9
0x180001ebf  jz      loc_1800020DD
0x180001ec5  test    r8, r8
0x180001ec8  jz      loc_1800020DD
0x180001ece  cmp     dword ptr [r9], 0
0x180001ed2  jz      short loc_180001EDE
0x180001ed4  cmp     qword ptr [r8], 0
0x180001ed8  jz      loc_1800020DD
0x180001ede  test    r14d, r14d
0x180001ee1  jz      short loc_180001EFB
0x180001ee3  test    r14b, 0Fh
0x180001ee7  jnz     short loc_180001EFB
0x180001ee9  lea     r9, aCalledWithInva; "Called with invalid flags"
0x180001ef0  mov     r8d, 34Eh
0x180001ef6  jmp     loc_1800020EA
0x180001efb  mov     rbx, [r8]
0x180001efe  mov     ebp, 1C8h
0x180001f03  test    rbx, rbx
0x180001f06  jnz     short loc_180001F58
0x180001f08  cmp     [r9], ebx
0x180001f0b  jnz     short loc_180001F58
0x180001f0d  mov     rcx, gs:60h
0x180001f16  lea     edx, [rbx+8]; Flags
0x180001f19  mov     r8d, ebp; Size
0x180001f1c  mov     rcx, [rcx+30h]; HeapHandle
0x180001f20  call    cs:__imp_RtlAllocateHeap
0x180001f26  mov     rbx, rax
0x180001f29  test    rax, rax
0x180001f2c  jnz     short loc_180001F53
0x180001f2e  lea     r9, aFailedToAlloca_34; "Failed to allocate %d bytes"
0x180001f35  mov     [rsp+68h+var_48], ebp
0x180001f39  mov     r8d, 35Fh
0x180001f3f  lea     rdx, aApphelpcreatea_0; "ApphelpCreateAppcompatData"
0x180001f46  lea     ecx, [rax+1]
0x180001f49  call    AslLogCallPrintf
0x180001f4e  jmp     loc_1800020FB
0x180001f53  mov     [rsi], ebp
0x180001f55  mov     [rdi], rax
0x180001f58  cmp     [rsi], ebp
0x180001f5a  jnz     loc_1800020FB
0x180001f60  mov     ecx, [rbx+0C0h]
0x180001f66  lea     rax, qword_180080420
0x180001f6d  shr     ecx, 0Ah
0x180001f70  xor     edi, edi
0x180001f72  and     ecx, 8
0x180001f75  mov     r15d, ecx
0x180001f78  or      r15d, 10h
0x180001f7c  test    dword ptr [rbx+0C0h], 4000h
0x180001f86  cmovz   r15d, ecx
0x180001f8a  xor     esi, esi
0x180001f8c  cmp     rsi, 4
0x180001f90  jnb     short loc_18000200E
0x180001f92  mov     rbp, rsi
0x180001f95  add     rbp, rbp
0x180001f98  test    [rax+rbp*8], r14d
0x180001f9c  jz      short loc_180001FF7
0x180001f9e  test    rdi, rdi
0x180001fa1  jnz     short loc_180001FC0
0x180001fa3  movzx   r8d, r12w
0x180001fa7  xor     edx, edx
0x180001fa9  mov     ecx, r15d
0x180001fac  call    SdbInitDatabaseEx
0x180001fb1  mov     rdi, rax
0x180001fb4  test    rax, rax
0x180001fb7  jz      short loc_180001FFC
0x180001fb9  lea     rax, qword_180080420
0x180001fc0  mov     r8, [rax+rbp*8+8]
0x180001fc5  mov     rdx, rbx
0x180001fc8  mov     rcx, rdi
0x180001fcb  call    SdbAddExeTagRefToQuery
0x180001fd0  test    eax, eax
0x180001fd2  jnz     short loc_180001FF0
0x180001fd4  lea     r9, aFailedToAddExe; "Failed to add exe ref"
0x180001fdb  mov     r8d, 388h
0x180001fe1  lea     rdx, aApphelpcreatea_0; "ApphelpCreateAppcompatData"
0x180001fe8  lea     ecx, [rax+1]
0x180001feb  call    AslLogCallPrintf
0x180001ff0  lea     rax, qword_180080420
0x180001ff7  inc     rsi
0x180001ffa  jmp     short loc_180001F8C
0x180001ffc  lea     r9, aFailedToInitia_3; "Failed to initialize database."
0x180002003  mov     r8d, 382h
0x180002009  jmp     loc_1800020EA
0x18000200e  cmp     dword ptr [rbx], 0
0x180002011  jnz     short loc_180002032
0x180002013  cmp     dword ptr [rbx+80h], 0
0x18000201a  jnz     short loc_180002032
0x18000201c  cmp     dword ptr [rbx+0A4h], 0
0x180002023  jnz     short loc_180002032
0x180002025  test    byte ptr [rbx+0C0h], 40h
0x18000202c  jz      loc_1800020CE
0x180002032  test    rdi, rdi
0x180002035  jnz     short loc_18000205F
0x180002037  movzx   r8d, r12w
0x18000203b  xor     edx, edx
0x18000203d  mov     ecx, r15d
0x180002040  call    SdbInitDatabaseEx
0x180002045  mov     rdi, rax
0x180002048  test    rax, rax
0x18000204b  jnz     short loc_18000205F
0x18000204d  lea     r9, aFailedToInitia_3; "Failed to initialize database."
0x180002054  mov     r8d, 395h
0x18000205a  jmp     loc_1800020EA
0x18000205f  mov     rsi, [rsp+68h+arg_20]
0x180002067  mov     rdx, rbx
0x18000206a  mov     r9, [rsp+68h+arg_28]
0x180002072  mov     r8, rsi
0x180002075  mov     rcx, rdi
0x180002078  call    SdbPackAppCompatData
0x18000207d  test    eax, eax
0x18000207f  jnz     short loc_18000209F
0x180002081  lea     r9, aFailedToPackDa; "Failed to pack data."
0x180002088  mov     r8d, 3A0h
0x18000208e  lea     rdx, aApphelpcreatea_0; "ApphelpCreateAppcompatData"
0x180002095  lea     ecx, [rax+1]
0x180002098  call    AslLogCallPrintf
0x18000209d  jmp     short loc_1800020CE
0x18000209f  mov     eax, [rbx+0C0h]
0x1800020a5  mov     ecx, eax
0x1800020a7  and     ecx, 2
0x1800020aa  test    al, 1
0x1800020ac  jnz     short loc_1800020BD
0x1800020ae  test    ecx, ecx
0x1800020b0  jnz     short loc_1800020C1
0x1800020b2  call    IsEventFilteringEnabled
0x1800020b7  test    eax, eax
0x1800020b9  jz      short loc_1800020CE
0x1800020bb  jmp     short loc_1800020C1
0x1800020bd  test    ecx, ecx
0x1800020bf  jz      short loc_1800020CE
0x1800020c1  mov     rax, [rsi]
0x1800020c4  mov     dword ptr [rax+210h], 0
0x1800020ce  test    rdi, rdi
0x1800020d1  jz      short loc_1800020FB
0x1800020d3  mov     rcx, rdi; P
0x1800020d6  call    SdbReleaseDatabase
0x1800020db  jmp     short loc_1800020FB
0x1800020dd  lea     r9, aCalledWithInva_0; "Called with invalid parameters"
0x1800020e4  mov     r8d, 348h
0x1800020ea  lea     rdx, aApphelpcreatea_0; "ApphelpCreateAppcompatData"
0x1800020f1  mov     ecx, 1
0x1800020f6  call    AslLogCallPrintf
0x1800020fb  mov     eax, 1
0x180002100  add     rsp, 30h
0x180002104  pop     r15
0x180002106  pop     r14
0x180002108  pop     r12
0x18000210a  pop     rdi
0x18000210b  pop     rsi
0x18000210c  pop     rbp
0x18000210d  pop     rbx
0x18000210e  retn
```
