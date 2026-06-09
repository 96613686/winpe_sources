# RtlCopyBufferToMdlFromMode

- ea: `0x140054f60`
- end: `0x140055162`
- name: `RtlCopyBufferToMdlFromMode`
- size: `514`
- prototype: `__int64 __fastcall(char *Src, PMDL SourceMdl, unsigned __int64, char, size_t Size, size_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140047800`
- `0x140055540`

## callees

- `0x140047858`
- `0x140051fb8`
- `0x140054f60`
- `0x140055168`
- `0x140077fd0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400550a0`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400550a0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140054fca`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140055087`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140054fca`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140055087`

## pseudocode

```c
__int64 __fastcall RtlCopyBufferToMdlFromMode(
        char *Src,
        PMDL SourceMdl,
        unsigned __int64 a3,
        char a4,
        size_t Size,
        size_t *a6)
{
  unsigned __int64 v6; // r14
  PMDL v7; // rdi
  size_t v9; // rbx
  char *v10; // rax
  char *v11; // rcx
  __int64 result; // rax
  unsigned int v13; // r15d
  unsigned __int64 ByteCount; // rax
  size_t v15; // rsi
  size_t v16; // rcx
  char *MappedSystemVa; // rax
  size_t v18; // r8
  char *v19; // rcx
  __int64 v20; // [rsp+88h] [rbp+10h]
  char v21; // [rsp+98h] [rbp+20h]

  v21 = a4;
  v6 = a3;
  v7 = SourceMdl;
  *a6 = 0;
  v9 = Size;
  if ( SourceMdl->ByteCount >= a3 + Size
    && ((SourceMdl->MdlFlags & 5) == 0
      ? (char *)(v10 = (char *)MmMapLockedPagesSpecifyCache(SourceMdl, 0, MmCached, 0, 0, 0x40000000u), a4 = v21)
      : (v10 = (char *)SourceMdl->MappedSystemVa),
        v10) )
  {
    v11 = &v10[v6];
    if ( a4 )
      RtlCopyFromUser(v11, Src, Size);
    else
      RtlCopyVolatileMemory(v11, Src, Size);
    result = 0;
  }
  else
  {
    v13 = 0;
    do
    {
      ByteCount = v7->ByteCount;
      if ( v6 < ByteCount )
        break;
      v6 -= ByteCount;
      v7 = v7->Next;
    }
    while ( v7 );
    v15 = Size;
    while ( v7 && v15 )
    {
      if ( v7->ByteCount )
      {
        v16 = v15;
        if ( v15 >= v7->ByteCount - v6 )
          v16 = v7->ByteCount - v6;
        v20 = v16;
        if ( (v7->MdlFlags & 5) != 0 )
        {
          MappedSystemVa = (char *)v7->MappedSystemVa;
        }
        else
        {
          MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v7, 0, MmCached, 0, 0, 0x40000000u);
          v16 = v20;
        }
        if ( MappedSystemVa )
        {
          v18 = v16;
          v19 = &MappedSystemVa[v6];
          if ( v21 )
            RtlCopyFromUser(v19, Src, v18);
          else
            RtlCopyVolatileMemory(v19, Src, v18);
        }
        else
        {
          if ( KeGetCurrentIrql() >= 2u )
            result = RtlCopyBufferToMdlWithReservedMappingAtDpcLevel(Src, v7, v20);
          else
            result = RtlCopyBufferToMdlWithReservedMappingAtLowIrql(Src, v7, v20);
          v13 = result;
          if ( (_DWORD)result )
            goto LABEL_34;
        }
        v6 = 0;
        Src += v20;
        v15 -= v20;
      }
      v7 = v7->Next;
    }
    result = v13;
LABEL_34:
    v9 = Size - v15;
  }
  *a6 = v9;
  return result;
}

```

## disassembly

```asm
0x140054f60  mov     [rsp+arg_18], r9b
0x140054f65  push    rbx
0x140054f66  push    rsi
0x140054f67  push    rdi
0x140054f68  push    r12
0x140054f6a  push    r13
0x140054f6c  push    r14
0x140054f6e  push    r15
0x140054f70  sub     rsp, 40h
0x140054f74  mov     r14, r8
0x140054f77  mov     rdi, rdx
0x140054f7a  mov     r12, rcx
0x140054f7d  mov     r13, [rsp+78h+arg_28]
0x140054f85  mov     qword ptr [r13+0], 0
0x140054f8d  mov     r10d, [rdx+28h]
0x140054f91  mov     rbx, [rsp+78h+Size]
0x140054f99  lea     rax, [r8+rbx]
0x140054f9d  cmp     r10, rax
0x140054fa0  jb      short loc_14005500B
0x140054fa2  test    byte ptr [rdx+0Ah], 5
0x140054fa6  jz      short loc_140054FAE
0x140054fa8  mov     rax, [rdx+18h]
0x140054fac  jmp     short loc_140054FDE
0x140054fae  mov     [rsp+78h+Priority], 40000000h; Priority
0x140054fb6  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140054fbe  xor     r9d, r9d; RequestedAddress
0x140054fc1  xor     edx, edx; AccessMode
0x140054fc3  lea     r8d, [r9+1]; CacheType
0x140054fc7  mov     rcx, rdi; MemoryDescriptorList
0x140054fca  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140054fd1  nop     dword ptr [rax+rax+00h]
0x140054fd6  mov     r9b, [rsp+78h+arg_18]
0x140054fde  test    rax, rax
0x140054fe1  jz      short loc_14005500B
0x140054fe3  lea     rcx, [rax+r14]; void *
0x140054fe7  mov     r8, rbx; Size
0x140054fea  mov     rdx, r12; Src
0x140054fed  test    r9b, r9b
0x140054ff0  jz      short loc_140054FF9
0x140054ff2  call    RtlCopyFromUser
0x140054ff7  jmp     short loc_140054FFF
0x140054ff9  call    RtlCopyVolatileMemory
0x140054ffe  nop
0x140054fff  xor     eax, eax
0x140055001  jmp     loc_14005514D
0x140055006  jmp     loc_140055151
0x14005500b  xor     r15d, r15d
0x14005500e  mov     eax, [rdi+28h]
0x140055011  cmp     r14, rax
0x140055014  jb      short loc_140055021
0x140055016  sub     r14, rax
0x140055019  mov     rdi, [rdi]
0x14005501c  test    rdi, rdi
0x14005501f  jnz     short loc_14005500E
0x140055021  mov     rsi, rbx
0x140055024  mov     [rsp+78h+arg_10], rbx
0x14005502c  test    rdi, rdi
0x14005502f  jz      loc_140055147
0x140055035  test    rsi, rsi
0x140055038  jz      loc_140055147
0x14005503e  mov     eax, [rdi+28h]
0x140055041  test    rax, rax
0x140055044  jz      loc_140055122
0x14005504a  sub     rax, r14
0x14005504d  mov     rcx, rsi
0x140055050  cmp     rsi, rax
0x140055053  cmovnb  rcx, rax
0x140055057  mov     [rsp+78h+arg_8], rcx
0x14005505f  test    byte ptr [rdi+0Ah], 5
0x140055063  jz      short loc_14005506B
0x140055065  mov     rax, [rdi+18h]
0x140055069  jmp     short loc_14005509B
0x14005506b  mov     [rsp+78h+Priority], 40000000h; Priority
0x140055073  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14005507b  xor     r9d, r9d; RequestedAddress
0x14005507e  xor     edx, edx; AccessMode
0x140055080  lea     r8d, [r9+1]; CacheType
0x140055084  mov     rcx, rdi; MemoryDescriptorList
0x140055087  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14005508e  nop     dword ptr [rax+rax+00h]
0x140055093  mov     rcx, [rsp+78h+arg_8]
0x14005509b  test    rax, rax
0x14005509e  jnz     short loc_1400550E3
0x1400550a0  call    cs:__imp_KeGetCurrentIrql
0x1400550a7  nop     dword ptr [rax+rax+00h]
0x1400550ac  mov     r9b, [rsp+78h+arg_18]
0x1400550b4  mov     r8, r14
0x1400550b7  mov     rdx, rdi; SourceMdl
0x1400550ba  mov     rcx, r12; Src
0x1400550bd  cmp     al, 2
0x1400550bf  mov     rax, [rsp+78h+arg_8]
0x1400550c7  mov     qword ptr [rsp+78h+BugCheckOnFailure], rax; __int64
0x1400550cc  jnb     short loc_1400550DC
0x1400550ce  call    RtlCopyBufferToMdlWithReservedMappingAtLowIrql
0x1400550d3  mov     r15d, eax
0x1400550d6  test    eax, eax
0x1400550d8  jz      short loc_140055107
0x1400550da  jmp     short loc_14005514A
0x1400550dc  call    RtlCopyBufferToMdlWithReservedMappingAtDpcLevel
0x1400550e1  jmp     short loc_1400550D3
0x1400550e3  lea     r9, [rax+r14]
0x1400550e7  mov     r8, rcx; Size
0x1400550ea  mov     rdx, r12; Src
0x1400550ed  mov     rcx, r9; void *
0x1400550f0  cmp     [rsp+78h+arg_18], 0
0x1400550f8  jz      short loc_140055101
0x1400550fa  call    RtlCopyFromUser
0x1400550ff  jmp     short loc_140055107
0x140055101  call    RtlCopyVolatileMemory
0x140055106  nop
0x140055107  xor     r14d, r14d
0x14005510a  add     r12, [rsp+78h+arg_8]
0x140055112  sub     rsi, [rsp+78h+arg_8]
0x14005511a  mov     [rsp+78h+arg_10], rsi
0x140055122  mov     rdi, [rdi]
0x140055125  jmp     loc_14005502C
0x14005512a  mov     rdx, [rsp+78h+Size]
0x140055132  sub     rdx, [rsp+78h+arg_10]
0x14005513a  mov     rcx, [rsp+78h+arg_28]
0x140055142  mov     [rcx], rdx
0x140055145  jmp     short loc_140055151
0x140055147  mov     eax, r15d
0x14005514a  sub     rbx, rsi
0x14005514d  mov     [r13+0], rbx
0x140055151  add     rsp, 40h
0x140055155  pop     r15
0x140055157  pop     r14
0x140055159  pop     r13
0x14005515b  pop     r12
0x14005515d  pop     rdi
0x14005515e  pop     rsi
0x14005515f  pop     rbx
0x140055160  retn
0x140078a65  push    rbp
0x140078a67  sub     rsp, 30h
0x140078a6b  mov     rbp, rdx
0x140078a6e  xor     eax, eax
0x140078a70  cmp     [rbp+98h], al
0x140078a76  setnz   al
0x140078a79  mov     [rbp+30h], eax
0x140078a7c  mov     eax, [rbp+30h]
0x140078a7f  add     rsp, 30h
0x140078a83  pop     rbp
0x140078a84  retn
0x140078a86  push    rbp
0x140078a88  sub     rsp, 30h
0x140078a8c  mov     rbp, rdx
0x140078a8f  xor     eax, eax
0x140078a91  cmp     [rbp+98h], al
0x140078a97  setnz   al
0x140078a9a  mov     [rbp+34h], eax
0x140078a9d  mov     eax, [rbp+34h]
0x140078aa0  add     rsp, 30h
0x140078aa4  pop     rbp
0x140078aa5  retn
```
