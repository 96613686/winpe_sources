# BthCopyMdlChainToBuffer

- ea: `0x140162b70`
- end: `0x140162d73`
- name: `BthCopyMdlChainToBuffer`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400306a8`

## callees

- `0x140162b70`
- `0x140165640`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140162bbb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140162c22`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140162c6c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140162cdc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140162bbb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140162c22`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140162c6c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140162cdc`

## pseudocode

```c
__int64 __fastcall BthCopyMdlChainToBuffer(
        __int64 *a1,
        unsigned int a2,
        char *a3,
        __int64 a4,
        unsigned int Size,
        int *a6)
{
  bool v6; // zf
  struct _MDL *v9; // rdi
  char *MappedSystemVa; // rsi
  unsigned int i; // ebx
  unsigned int ByteCount; // ebp
  __int64 v13; // rax
  int v15; // r15d
  __int64 result; // rax
  unsigned int v17; // ebx

  v6 = (*((_BYTE *)a1 + 10) & 5) == 0;
  v9 = (struct _MDL *)a1;
  *a6 = 0;
  if ( v6 )
    MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache((PMDL)a1, 0, MmCached, 0, 0, 0x40000010u);
  else
    MappedSystemVa = (char *)a1[3];
  if ( MappedSystemVa )
  {
    for ( i = 0; ; i += ByteCount )
    {
      ByteCount = v9->ByteCount;
      if ( i >= a2 )
      {
LABEL_22:
        while ( Size && v9 )
        {
          if ( ByteCount )
          {
            v15 = *a6;
            if ( Size == ByteCount )
            {
              v17 = 0;
              goto LABEL_37;
            }
            if ( Size < ByteCount )
            {
              v17 = -2147483643;
LABEL_37:
              memmove(a3, MappedSystemVa, Size);
              result = v17;
              *a6 = v15 + Size;
              return result;
            }
            memmove(a3, MappedSystemVa, ByteCount);
            Size -= ByteCount;
            a3 += ByteCount;
            *a6 = v15 + ByteCount;
            ByteCount = 0;
          }
          else
          {
            v9 = v9->Next;
            if ( !v9 )
              return 0;
            if ( (v9->MdlFlags & 5) != 0 )
              MappedSystemVa = (char *)v9->MappedSystemVa;
            else
              MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, 0x40000010u);
            if ( !MappedSystemVa )
              return 3221225626LL;
            ByteCount = v9->ByteCount;
          }
        }
        return v9 != 0 ? 0x80000005 : 0;
      }
      v13 = a2 - i;
      if ( ByteCount > (unsigned int)v13 )
      {
        ByteCount += i - a2;
        MappedSystemVa += v13;
        goto LABEL_22;
      }
      v9 = v9->Next;
      if ( ByteCount == (_DWORD)v13 )
        break;
      if ( !v9 )
        return 0;
      if ( (v9->MdlFlags & 5) != 0 )
        MappedSystemVa = (char *)v9->MappedSystemVa;
      else
        MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, 0x40000010u);
      if ( !MappedSystemVa )
        return 3221225626LL;
    }
    if ( !v9 )
      return 0;
    if ( (v9->MdlFlags & 5) != 0 )
      MappedSystemVa = (char *)v9->MappedSystemVa;
    else
      MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, 0x40000010u);
    if ( MappedSystemVa )
    {
      ByteCount = v9->ByteCount;
      goto LABEL_22;
    }
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140162b70  push    rbx
0x140162b72  push    rbp
0x140162b73  push    rsi
0x140162b74  push    rdi
0x140162b75  push    r12
0x140162b77  push    r13
0x140162b79  push    r14
0x140162b7b  push    r15
0x140162b7d  sub     rsp, 38h
0x140162b81  mov     r12, [rsp+78h+arg_28]
0x140162b89  xor     r15d, r15d
0x140162b8c  test    byte ptr [rcx+0Ah], 5
0x140162b90  mov     r13, r8
0x140162b93  mov     r14d, edx
0x140162b96  mov     rdi, rcx
0x140162b99  mov     [r12], r15d
0x140162b9d  jz      short loc_140162BA5
0x140162b9f  mov     rsi, [rcx+18h]
0x140162ba3  jmp     short loc_140162BCA
0x140162ba5  xor     r9d, r9d; RequestedAddress
0x140162ba8  mov     [rsp+78h+Priority], 40000010h; Priority
0x140162bb0  xor     edx, edx; AccessMode
0x140162bb2  mov     [rsp+78h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x140162bb7  lea     r8d, [r9+1]; CacheType
0x140162bbb  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140162bc2  nop     dword ptr [rax+rax+00h]
0x140162bc7  mov     rsi, rax
0x140162bca  test    rsi, rsi
0x140162bcd  jz      loc_140162D5C
0x140162bd3  mov     ebx, r15d
0x140162bd6  mov     ebp, [rdi+28h]
0x140162bd9  cmp     ebx, r14d
0x140162bdc  jnb     loc_140162C91
0x140162be2  mov     eax, r14d
0x140162be5  sub     eax, ebx
0x140162be7  cmp     ebp, eax
0x140162be9  ja      loc_140162C89
0x140162bef  mov     rdi, [rdi]
0x140162bf2  jz      short loc_140162C3E
0x140162bf4  test    rdi, rdi
0x140162bf7  jz      loc_140162D29
0x140162bfd  test    byte ptr [rdi+0Ah], 5
0x140162c01  jz      short loc_140162C09
0x140162c03  mov     rsi, [rdi+18h]
0x140162c07  jmp     short loc_140162C31
0x140162c09  xor     r9d, r9d; RequestedAddress
0x140162c0c  mov     [rsp+78h+Priority], 40000010h; Priority
0x140162c14  xor     edx, edx; AccessMode
0x140162c16  mov     [rsp+78h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x140162c1b  mov     rcx, rdi; MemoryDescriptorList
0x140162c1e  lea     r8d, [r9+1]; CacheType
0x140162c22  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140162c29  nop     dword ptr [rax+rax+00h]
0x140162c2e  mov     rsi, rax
0x140162c31  test    rsi, rsi
0x140162c34  jz      loc_140162D5C
0x140162c3a  add     ebx, ebp
0x140162c3c  jmp     short loc_140162BD6
0x140162c3e  test    rdi, rdi
0x140162c41  jz      loc_140162D29
0x140162c47  test    byte ptr [rdi+0Ah], 5
0x140162c4b  jz      short loc_140162C53
0x140162c4d  mov     rsi, [rdi+18h]
0x140162c51  jmp     short loc_140162C7B
0x140162c53  xor     r9d, r9d; RequestedAddress
0x140162c56  mov     [rsp+78h+Priority], 40000010h; Priority
0x140162c5e  xor     edx, edx; AccessMode
0x140162c60  mov     [rsp+78h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x140162c65  mov     rcx, rdi; MemoryDescriptorList
0x140162c68  lea     r8d, [r9+1]; CacheType
0x140162c6c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140162c73  nop     dword ptr [rax+rax+00h]
0x140162c78  mov     rsi, rax
0x140162c7b  test    rsi, rsi
0x140162c7e  jz      loc_140162D5C
0x140162c84  mov     ebp, [rdi+28h]
0x140162c87  jmp     short loc_140162C91
0x140162c89  sub     ebx, r14d
0x140162c8c  add     ebp, ebx
0x140162c8e  add     rsi, rax
0x140162c91  mov     r14d, dword ptr [rsp+78h+Size]
0x140162c99  test    r14d, r14d
0x140162c9c  jz      loc_140162D50
0x140162ca2  test    rdi, rdi
0x140162ca5  jz      loc_140162D50
0x140162cab  test    ebp, ebp
0x140162cad  jnz     short loc_140162CF5
0x140162caf  mov     rdi, [rdi]
0x140162cb2  test    rdi, rdi
0x140162cb5  jz      short loc_140162D29
0x140162cb7  test    byte ptr [rdi+0Ah], 5
0x140162cbb  jz      short loc_140162CC3
0x140162cbd  mov     rsi, [rdi+18h]
0x140162cc1  jmp     short loc_140162CEB
0x140162cc3  xor     r9d, r9d; RequestedAddress
0x140162cc6  mov     [rsp+78h+Priority], 40000010h; Priority
0x140162cce  xor     edx, edx; AccessMode
0x140162cd0  mov     [rsp+78h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x140162cd5  mov     rcx, rdi; MemoryDescriptorList
0x140162cd8  lea     r8d, [r9+1]; CacheType
0x140162cdc  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140162ce3  nop     dword ptr [rax+rax+00h]
0x140162ce8  mov     rsi, rax
0x140162ceb  test    rsi, rsi
0x140162cee  jz      short loc_140162D5C
0x140162cf0  mov     ebp, [rdi+28h]
0x140162cf3  jmp     short loc_140162C99
0x140162cf5  mov     r15d, [r12]
0x140162cf9  cmp     r14d, ebp
0x140162cfc  jz      short loc_140162D34
0x140162cfe  jb      short loc_140162D2D
0x140162d00  mov     r8d, ebp; Size
0x140162d03  mov     rdx, rsi; Src
0x140162d06  mov     rcx, r13; void *
0x140162d09  mov     ebx, ebp
0x140162d0b  call    memmove
0x140162d10  lea     eax, [r15+rbp]
0x140162d14  sub     r14d, ebp
0x140162d17  add     r13, rbx
0x140162d1a  mov     [r12], eax
0x140162d1e  xor     r15d, r15d
0x140162d21  mov     ebp, r15d
0x140162d24  jmp     loc_140162C99
0x140162d29  xor     eax, eax
0x140162d2b  jmp     short loc_140162D61
0x140162d2d  mov     ebx, 80000005h
0x140162d32  jmp     short loc_140162D36
0x140162d34  xor     ebx, ebx
0x140162d36  mov     r8d, r14d; Size
0x140162d39  mov     rdx, rsi; Src
0x140162d3c  mov     rcx, r13; void *
0x140162d3f  call    memmove
0x140162d44  lea     ecx, [r15+r14]
0x140162d48  mov     eax, ebx
0x140162d4a  mov     [r12], ecx
0x140162d4e  jmp     short loc_140162D61
0x140162d50  neg     rdi
0x140162d53  sbb     eax, eax
0x140162d55  and     eax, 80000005h
0x140162d5a  jmp     short loc_140162D61
0x140162d5c  mov     eax, 0C000009Ah
0x140162d61  add     rsp, 38h
0x140162d65  pop     r15
0x140162d67  pop     r14
0x140162d69  pop     r13
0x140162d6b  pop     r12
0x140162d6d  pop     rdi
0x140162d6e  pop     rsi
0x140162d6f  pop     rbp
0x140162d70  pop     rbx
0x140162d71  retn
```
