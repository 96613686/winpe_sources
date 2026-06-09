# BthCopyBufferToMdlChain

- ea: `0x140162958`
- end: `0x140162b69`
- name: `BthCopyBufferToMdlChain`
- size: `529`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400ba420`

## callees

- `0x140162958`
- `0x140165640`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1401629c0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140162a31`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140162a7a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140162aea`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1401629c0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140162a31`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140162a7a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140162aea`

## pseudocode

```c
__int64 __fastcall BthCopyBufferToMdlChain(
        char *Src,
        __int64 a2,
        unsigned int a3,
        struct _MDL *a4,
        unsigned int a5,
        int *a6)
{
  struct _MDL *v6; // rdi
  unsigned int v7; // r14d
  char *MappedSystemVa; // rsi
  unsigned int i; // ebx
  unsigned int ByteCount; // ebp
  __int64 v13; // rax
  int v14; // r15d

  v6 = a4;
  v7 = a3;
  *a6 = 0;
  if ( !a3 )
    return 0;
  if ( !a4 )
    return 2147483653LL;
  if ( (a4->MdlFlags & 5) != 0 )
    MappedSystemVa = (char *)a4->MappedSystemVa;
  else
    MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(a4, 0, MmCached, 0, 0, 0x40000010u);
  if ( MappedSystemVa )
  {
    for ( i = 0; ; i += ByteCount )
    {
      ByteCount = v6->ByteCount;
      if ( i >= a5 )
      {
        while ( 1 )
        {
LABEL_25:
          if ( !v7 || !v6 )
            return v7 != 0 ? 0x80000005 : 0;
          if ( !ByteCount )
            break;
          v14 = *a6;
          if ( ByteCount >= v7 )
          {
            memmove(MappedSystemVa, Src, v7);
            *a6 = v14 + v7;
            return 0;
          }
          memmove(MappedSystemVa, Src, ByteCount);
          v7 -= ByteCount;
          Src += ByteCount;
          *a6 = v14 + ByteCount;
          ByteCount = 0;
        }
        v6 = v6->Next;
        if ( v6 )
        {
          MappedSystemVa = (char *)((v6->MdlFlags & 5) != 0
                                  ? v6->MappedSystemVa
                                  : MmMapLockedPagesSpecifyCache(v6, 0, MmCached, 0, 0, 0x40000010u));
          if ( MappedSystemVa )
          {
LABEL_33:
            ByteCount = v6->ByteCount;
            goto LABEL_25;
          }
        }
        return 2147483653LL;
      }
      v13 = a5 - i;
      if ( ByteCount > (unsigned int)v13 )
      {
        ByteCount += i - a5;
        MappedSystemVa += v13;
        goto LABEL_25;
      }
      v6 = v6->Next;
      if ( ByteCount == (_DWORD)v13 )
        break;
      if ( !v6 )
        return 2147483653LL;
      if ( (v6->MdlFlags & 5) != 0 )
        MappedSystemVa = (char *)v6->MappedSystemVa;
      else
        MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v6, 0, MmCached, 0, 0, 0x40000010u);
      if ( !MappedSystemVa )
        return 3221225626LL;
    }
    if ( !v6 )
      return 2147483653LL;
    if ( (v6->MdlFlags & 5) != 0 )
      MappedSystemVa = (char *)v6->MappedSystemVa;
    else
      MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v6, 0, MmCached, 0, 0, 0x40000010u);
    if ( MappedSystemVa )
      goto LABEL_33;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140162958  push    rbx
0x14016295a  push    rbp
0x14016295b  push    rsi
0x14016295c  push    rdi
0x14016295d  push    r12
0x14016295f  push    r13
0x140162961  push    r14
0x140162963  push    r15
0x140162965  sub     rsp, 38h
0x140162969  mov     r12, [rsp+78h+arg_28]
0x140162971  mov     rdi, r9
0x140162974  mov     r14d, r8d
0x140162977  mov     r13, rcx
0x14016297a  mov     dword ptr [r12], 0
0x140162982  test    r8d, r8d
0x140162985  jnz     short loc_14016298E
0x140162987  xor     eax, eax
0x140162989  jmp     loc_140162B57
0x14016298e  test    rdi, rdi
0x140162991  jz      loc_140162B52
0x140162997  test    byte ptr [r9+0Ah], 5
0x14016299c  jz      short loc_1401629A4
0x14016299e  mov     rsi, [r9+18h]
0x1401629a2  jmp     short loc_1401629CF
0x1401629a4  xor     r9d, r9d; RequestedAddress
0x1401629a7  mov     [rsp+78h+Priority], 40000010h; Priority
0x1401629af  xor     edx, edx; AccessMode
0x1401629b1  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1401629b9  mov     rcx, rdi; MemoryDescriptorList
0x1401629bc  lea     r8d, [r9+1]; CacheType
0x1401629c0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1401629c7  nop     dword ptr [rax+rax+00h]
0x1401629cc  mov     rsi, rax
0x1401629cf  test    rsi, rsi
0x1401629d2  jz      loc_140162A8E
0x1401629d8  mov     r15d, [rsp+78h+arg_20]
0x1401629e0  xor     ebx, ebx
0x1401629e2  mov     ebp, [rdi+28h]
0x1401629e5  cmp     ebx, r15d
0x1401629e8  jnb     loc_140162AA0
0x1401629ee  mov     eax, r15d
0x1401629f1  sub     eax, ebx
0x1401629f3  cmp     ebp, eax
0x1401629f5  ja      loc_140162A98
0x1401629fb  mov     rdi, [rdi]
0x1401629fe  jz      short loc_140162A49
0x140162a00  test    rdi, rdi
0x140162a03  jz      loc_140162B52
0x140162a09  test    byte ptr [rdi+0Ah], 5
0x140162a0d  jz      short loc_140162A15
0x140162a0f  mov     rsi, [rdi+18h]
0x140162a13  jmp     short loc_140162A40
0x140162a15  xor     r9d, r9d; RequestedAddress
0x140162a18  mov     [rsp+78h+Priority], 40000010h; Priority
0x140162a20  xor     edx, edx; AccessMode
0x140162a22  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140162a2a  mov     rcx, rdi; MemoryDescriptorList
0x140162a2d  lea     r8d, [r9+1]; CacheType
0x140162a31  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140162a38  nop     dword ptr [rax+rax+00h]
0x140162a3d  mov     rsi, rax
0x140162a40  test    rsi, rsi
0x140162a43  jz      short loc_140162A8E
0x140162a45  add     ebx, ebp
0x140162a47  jmp     short loc_1401629E2
0x140162a49  test    rdi, rdi
0x140162a4c  jz      loc_140162B52
0x140162a52  test    byte ptr [rdi+0Ah], 5
0x140162a56  jz      short loc_140162A5E
0x140162a58  mov     rsi, [rdi+18h]
0x140162a5c  jmp     short loc_140162A89
0x140162a5e  xor     r9d, r9d; RequestedAddress
0x140162a61  mov     [rsp+78h+Priority], 40000010h; Priority
0x140162a69  xor     edx, edx; AccessMode
0x140162a6b  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140162a73  mov     rcx, rdi; MemoryDescriptorList
0x140162a76  lea     r8d, [r9+1]; CacheType
0x140162a7a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140162a81  nop     dword ptr [rax+rax+00h]
0x140162a86  mov     rsi, rax
0x140162a89  test    rsi, rsi
0x140162a8c  jnz     short loc_140162AFE
0x140162a8e  mov     eax, 0C000009Ah
0x140162a93  jmp     loc_140162B57
0x140162a98  sub     ebx, r15d
0x140162a9b  add     ebp, ebx
0x140162a9d  add     rsi, rax
0x140162aa0  test    r14d, r14d
0x140162aa3  jz      loc_140162B46
0x140162aa9  test    rdi, rdi
0x140162aac  jz      loc_140162B46
0x140162ab2  test    ebp, ebp
0x140162ab4  jnz     short loc_140162B03
0x140162ab6  mov     rdi, [rdi]
0x140162ab9  test    rdi, rdi
0x140162abc  jz      loc_140162B52
0x140162ac2  test    byte ptr [rdi+0Ah], 5
0x140162ac6  jz      short loc_140162ACE
0x140162ac8  mov     rsi, [rdi+18h]
0x140162acc  jmp     short loc_140162AF9
0x140162ace  xor     r9d, r9d; RequestedAddress
0x140162ad1  mov     [rsp+78h+Priority], 40000010h; Priority
0x140162ad9  xor     edx, edx; AccessMode
0x140162adb  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140162ae3  mov     rcx, rdi; MemoryDescriptorList
0x140162ae6  lea     r8d, [r9+1]; CacheType
0x140162aea  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140162af1  nop     dword ptr [rax+rax+00h]
0x140162af6  mov     rsi, rax
0x140162af9  test    rsi, rsi
0x140162afc  jz      short loc_140162B52
0x140162afe  mov     ebp, [rdi+28h]
0x140162b01  jmp     short loc_140162AA0
0x140162b03  mov     r15d, [r12]
0x140162b07  mov     rdx, r13; Src
0x140162b0a  mov     rcx, rsi; void *
0x140162b0d  cmp     ebp, r14d
0x140162b10  jnb     short loc_140162B31
0x140162b12  mov     r8d, ebp; Size
0x140162b15  mov     ebx, ebp
0x140162b17  call    memmove
0x140162b1c  lea     eax, [r15+rbp]
0x140162b20  sub     r14d, ebp
0x140162b23  add     r13, rbx
0x140162b26  mov     [r12], eax
0x140162b2a  xor     ebp, ebp
0x140162b2c  jmp     loc_140162AA0
0x140162b31  mov     r8d, r14d; Size
0x140162b34  call    memmove
0x140162b39  lea     eax, [r15+r14]
0x140162b3d  mov     [r12], eax
0x140162b41  jmp     loc_140162987
0x140162b46  neg     r14d
0x140162b49  sbb     eax, eax
0x140162b4b  and     eax, 80000005h
0x140162b50  jmp     short loc_140162B57
0x140162b52  mov     eax, 80000005h
0x140162b57  add     rsp, 38h
0x140162b5b  pop     r15
0x140162b5d  pop     r14
0x140162b5f  pop     r13
0x140162b61  pop     r12
0x140162b63  pop     rdi
0x140162b64  pop     rsi
0x140162b65  pop     rbp
0x140162b66  pop     rbx
0x140162b67  retn
```
