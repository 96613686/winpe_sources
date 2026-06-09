# RtlCopyMdlToBufferToMode

- ea: `0x140055570`
- end: `0x140055708`
- name: `RtlCopyMdlToBufferToMode`
- size: `408`
- prototype: `__int64 __fastcall(PMDL SourceMdl, unsigned __int64, char *, char, unsigned __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14003c940`
- `0x140047930`
- `0x140055800`

## callees

- `0x14004798c`
- `0x140055570`
- `0x140055710`
- `0x140077fd0`
- `0x1400a90a8`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140055640`
- `ntoskrnl!KeGetCurrentIrql` at `0x140055640`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14005561f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14005561f`

## pseudocode

```c
__int64 __fastcall RtlCopyMdlToBufferToMode(
        PMDL SourceMdl,
        unsigned __int64 a2,
        char *a3,
        char a4,
        unsigned __int64 a5,
        _QWORD *a6)
{
  char v6; // r10
  char *v7; // r9
  PMDL v9; // rdi
  unsigned int v10; // r15d
  unsigned __int64 ByteCount; // rax
  unsigned __int64 v12; // rsi
  size_t v13; // r12
  char *MappedSystemVa; // rax
  __int64 result; // rax
  char *v16; // [rsp+80h] [rbp+18h]

  v16 = a3;
  v6 = a4;
  v7 = a3;
  v9 = SourceMdl;
  v10 = 0;
  for ( *a6 = 0; v9; v9 = v9->Next )
  {
    ByteCount = v9->ByteCount;
    if ( a2 < ByteCount )
      break;
    a2 -= ByteCount;
  }
  v12 = a5;
  while ( v9 && v12 )
  {
    if ( v9->ByteCount )
    {
      v13 = v12;
      if ( v12 >= v9->ByteCount - a2 )
        v13 = v9->ByteCount - a2;
      if ( (v9->MdlFlags & 5) != 0 )
      {
        MappedSystemVa = (char *)v9->MappedSystemVa;
      }
      else
      {
        MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, 0x40000000u);
        v7 = v16;
        v6 = a4;
      }
      if ( MappedSystemVa )
      {
        if ( v6 )
          RtlCopyToUser(v7, &MappedSystemVa[a2], v13);
        else
          RtlCopyVolatileMemory(v7, &MappedSystemVa[a2], v13);
      }
      else
      {
        if ( KeGetCurrentIrql() >= 2u )
          result = RtlCopyMdlToBufferWithReservedMappingAtDpcLevel(v9, v13);
        else
          result = RtlCopyMdlToBufferWithReservedMappingAtLowIrql(v9, v13);
        v10 = result;
        if ( (_DWORD)result )
          goto LABEL_25;
      }
      a2 = 0;
      v7 = &v16[v13];
      v16 += v13;
      v12 -= v13;
      v6 = a4;
    }
    v9 = v9->Next;
  }
  result = v10;
LABEL_25:
  *a6 = a5 - v12;
  return result;
}

```

## disassembly

```asm
0x140055570  mov     [rsp+arg_18], r9b
0x140055575  mov     [rsp+arg_10], r8
0x14005557a  push    rbx
0x14005557b  push    rsi
0x14005557c  push    rdi
0x14005557d  push    r12
0x14005557f  push    r13
0x140055581  push    r14
0x140055583  push    r15
0x140055585  sub     rsp, 30h
0x140055589  mov     r10b, r9b
0x14005558c  mov     r9, r8
0x14005558f  mov     r14, rdx
0x140055592  mov     rdi, rcx
0x140055595  xor     r15d, r15d
0x140055598  mov     r13, [rsp+68h+arg_28]
0x1400555a0  mov     [r13+0], r15
0x1400555a4  test    rcx, rcx
0x1400555a7  jz      short loc_1400555BC
0x1400555a9  mov     eax, [rdi+28h]
0x1400555ac  cmp     r14, rax
0x1400555af  jb      short loc_1400555BC
0x1400555b1  sub     r14, rax
0x1400555b4  mov     rdi, [rdi]
0x1400555b7  test    rdi, rdi
0x1400555ba  jnz     short loc_1400555A9
0x1400555bc  mov     rbx, [rsp+68h+arg_20]
0x1400555c4  mov     rsi, rbx
0x1400555c7  mov     [rsp+68h+arg_0], rbx
0x1400555cc  test    rdi, rdi
0x1400555cf  jz      loc_1400556ED
0x1400555d5  test    rsi, rsi
0x1400555d8  jz      loc_1400556ED
0x1400555de  mov     eax, [rdi+28h]
0x1400555e1  test    rax, rax
0x1400555e4  jz      loc_1400556E5
0x1400555ea  sub     rax, r14
0x1400555ed  mov     r12, rsi
0x1400555f0  cmp     rsi, rax
0x1400555f3  cmovnb  r12, rax
0x1400555f7  test    byte ptr [rdi+0Ah], 5
0x1400555fb  jz      short loc_140055603
0x1400555fd  mov     rax, [rdi+18h]
0x140055601  jmp     short loc_14005563B
0x140055603  mov     [rsp+68h+Priority], 40000000h; Priority
0x14005560b  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140055613  xor     r9d, r9d; RequestedAddress
0x140055616  xor     edx, edx; AccessMode
0x140055618  lea     r8d, [r9+1]; CacheType
0x14005561c  mov     rcx, rdi; MemoryDescriptorList
0x14005561f  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140055626  nop     dword ptr [rax+rax+00h]
0x14005562b  mov     r9, [rsp+68h+arg_10]
0x140055633  mov     r10b, [rsp+68h+arg_18]
0x14005563b  test    rax, rax
0x14005563e  jnz     short loc_140055680
0x140055640  call    cs:__imp_KeGetCurrentIrql
0x140055647  nop     dword ptr [rax+rax+00h]
0x14005564c  mov     qword ptr [rsp+68h+BugCheckOnFailure], r12; __int64
0x140055651  mov     r9b, [rsp+68h+arg_18]
0x140055659  mov     r8, [rsp+68h+arg_10]
0x140055661  mov     rdx, r14
0x140055664  mov     rcx, rdi; SourceMdl
0x140055667  cmp     al, 2
0x140055669  jnb     short loc_140055679
0x14005566b  call    RtlCopyMdlToBufferWithReservedMappingAtLowIrql
0x140055670  mov     r15d, eax
0x140055673  test    eax, eax
0x140055675  jz      short loc_1400556BF
0x140055677  jmp     short loc_1400556F0
0x140055679  call    RtlCopyMdlToBufferWithReservedMappingAtDpcLevel
0x14005567e  jmp     short loc_140055670
0x140055680  test    r10b, r10b
0x140055683  jz      short loc_1400556B0
0x140055685  lea     rdx, [rax+r14]; Src
0x140055689  mov     r8, r12; Size
0x14005568c  mov     rcx, r9; void *
0x14005568f  call    RtlCopyToUser
0x140055694  jmp     short loc_1400556BF
0x140055696  mov     rdx, [rsp+68h+arg_20]
0x14005569e  sub     rdx, [rsp+68h+arg_0]
0x1400556a3  mov     rcx, [rsp+68h+arg_28]
0x1400556ab  mov     [rcx], rdx
0x1400556ae  jmp     short loc_1400556F7
0x1400556b0  lea     rdx, [rax+r14]; Src
0x1400556b4  mov     r8, r12; Size
0x1400556b7  mov     rcx, r9; void *
0x1400556ba  call    RtlCopyVolatileMemory
0x1400556bf  xor     r14d, r14d
0x1400556c2  mov     r9, [rsp+68h+arg_10]
0x1400556ca  add     r9, r12
0x1400556cd  mov     [rsp+68h+arg_10], r9
0x1400556d5  sub     rsi, r12
0x1400556d8  mov     [rsp+68h+arg_0], rsi
0x1400556dd  mov     r10b, [rsp+68h+arg_18]
0x1400556e5  mov     rdi, [rdi]
0x1400556e8  jmp     loc_1400555CC
0x1400556ed  mov     eax, r15d
0x1400556f0  sub     rbx, rsi
0x1400556f3  mov     [r13+0], rbx
0x1400556f7  add     rsp, 30h
0x1400556fb  pop     r15
0x1400556fd  pop     r14
0x1400556ff  pop     r13
0x140055701  pop     r12
0x140055703  pop     rdi
0x140055704  pop     rsi
0x140055705  pop     rbx
0x140055706  retn
```
