# SdbpReadMappedData

- ea: `0x14003e248`
- end: `0x14003e35d`
- name: `SdbpReadMappedData`
- size: `277`
- prototype: ``
- caller_count: `19`
- callee_count: `7`
- tags: ``

## callers

- `0x14002e118`
- `0x14002e4cc`
- `0x14003c444`
- `0x14003c62c`
- `0x14003d820`
- `0x14003da50`
- `0x14003e1f0`
- `0x14003e9b0`
- `0x14003ea80`
- `0x14003ef10`
- `0x14003f280`
- `0x14003f570`
- `0x14003f7f0`
- `0x14003f9b4`
- `0x14003fcf8`
- `0x14003fe74`
- `0x14004007c`
- `0x140042ad4`
- `0x1400544b4`

## callees

- `0x140004445`
- `0x1400045b0`
- `0x140007b40`
- `0x14002726c`
- `0x1400272d0`
- `0x14003e248`
- `0x14003e364`

## string_xrefs

- `0x14003e2e7`: `SdbpReadMappedData`
- `0x14003e31b`: `SdbpReadMappedData`
- `0x14003e34a`: `SdbpReadMappedData`
- `0x14003e33d`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x14003e2da`: `Exception encountered reading SDB file [%x]`

## pseudocode

```c
__int64 __fastcall SdbpReadMappedData(__int64 a1, unsigned int a2, void *a3, unsigned int a4)
{
  __int64 v6; // r15
  void *v7; // rsi
  size_t v8; // rdi

  if ( a2 + a4 < a4 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      855,
      "Offset and region size add up to cause an integer overflow or underflow");
    return 0;
  }
  if ( *(_DWORD *)(a1 + 20) < a2 + a4 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      860,
      "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
      a2,
      a4,
      *(_DWORD *)(a1 + 20));
    return 0;
  }
  v6 = a2;
  v7 = (void *)(a2 + *(_QWORD *)(a1 + 8));
  v8 = a4;
  if ( (unsigned __int8)MmIsUserAddress_0(v7) )
  {
    if ( (unsigned __int8)MmIsUserAddress_0(a3) )
      RtlCopyToUserFromUser(a3, v7, (unsigned int)v8);
    else
      RtlCopyFromUser(a3, v7, (unsigned int)v8);
  }
  else if ( (unsigned __int8)MmIsUserAddress_0(a3) )
  {
    RtlCopyToUser(a3, v7, v8);
  }
  else
  {
    memmove(a3, (const void *)(v6 + *(_QWORD *)(a1 + 8)), v8);
  }
  return 1;
}

```

## disassembly

```asm
0x14003e248  push    rbx
0x14003e24a  push    rsi
0x14003e24b  push    rdi
0x14003e24c  push    r14
0x14003e24e  push    r15
0x14003e250  sub     rsp, 70h
0x14003e254  mov     rbx, r8
0x14003e257  mov     r14, rcx
0x14003e25a  lea     ecx, [rdx+r9]
0x14003e25e  cmp     ecx, r9d
0x14003e261  jb      loc_14003E30E
0x14003e267  mov     eax, [r14+14h]
0x14003e26b  cmp     eax, ecx
0x14003e26d  jb      loc_14003E330
0x14003e273  mov     r15d, edx
0x14003e276  mov     rsi, [r14+8]
0x14003e27a  add     rsi, r15
0x14003e27d  mov     edi, r9d
0x14003e280  mov     rcx, rsi
0x14003e283  call    MmIsUserAddress_0
0x14003e288  mov     rcx, rbx
0x14003e28b  test    al, al
0x14003e28d  jz      short loc_14003E2AF
0x14003e28f  call    MmIsUserAddress_0
0x14003e294  mov     r8d, edi; Size
0x14003e297  mov     rdx, rsi; Src
0x14003e29a  mov     rcx, rbx; void *
0x14003e29d  test    al, al
0x14003e29f  jnz     short loc_14003E2A8
0x14003e2a1  call    RtlCopyFromUser
0x14003e2a6  jmp     short loc_14003E2D4
0x14003e2a8  call    RtlCopyToUserFromUser
0x14003e2ad  jmp     short loc_14003E2D4
0x14003e2af  call    MmIsUserAddress_0
0x14003e2b4  mov     r8, rdi; Size
0x14003e2b7  mov     rcx, rbx; void *
0x14003e2ba  test    al, al
0x14003e2bc  jz      short loc_14003E2C8
0x14003e2be  mov     rdx, rsi; Src
0x14003e2c1  call    RtlCopyToUser
0x14003e2c6  jmp     short loc_14003E2D4
0x14003e2c8  mov     rdx, [r14+8]
0x14003e2cc  add     rdx, r15; Src
0x14003e2cf  call    memmove
0x14003e2d4  jmp     short loc_14003E2FC
0x14003e2d6  mov     [rsp+98h+var_78], eax
0x14003e2da  lea     r9, aExceptionEncou; "Exception encountered reading SDB file "...
0x14003e2e1  mov     r8d, 374h
0x14003e2e7  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x14003e2ee  mov     ecx, 1
0x14003e2f3  call    AslLogCallPrintf
0x14003e2f8  xor     eax, eax
0x14003e2fa  jmp     short loc_14003E301
0x14003e2fc  mov     eax, 1
0x14003e301  add     rsp, 70h
0x14003e305  pop     r15
0x14003e307  pop     r14
0x14003e309  pop     rdi
0x14003e30a  pop     rsi
0x14003e30b  pop     rbx
0x14003e30c  retn
0x14003e30e  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x14003e315  mov     r8d, 357h
0x14003e31b  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x14003e322  mov     ecx, 1
0x14003e327  call    AslLogCallPrintf
0x14003e32c  xor     eax, eax
0x14003e32e  jmp     short loc_14003E301
0x14003e330  mov     [rsp+98h+var_68], eax
0x14003e334  mov     [rsp+98h+var_70], r9d
0x14003e339  mov     [rsp+98h+var_78], edx
0x14003e33d  lea     r9, aAttemptToReadP; "Attempt to read past the end of the dat"...
0x14003e344  mov     r8d, 35Ch
0x14003e34a  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x14003e351  mov     ecx, 1
0x14003e356  call    AslLogCallPrintf
0x14003e35b  jmp     short loc_14003E32C
0x14005bc16  push    rbp
0x14005bc18  sub     rsp, 60h
0x14005bc1c  mov     rbp, rdx
0x14005bc1f  mov     [rbp+68h], rcx
0x14005bc23  mov     rax, [rbp+68h]
0x14005bc27  mov     r10, [rax+8]
0x14005bc2b  mov     rax, [rbp+68h]
0x14005bc2f  mov     r9, [rax]
0x14005bc32  mov     rax, [rbp+68h]
0x14005bc36  mov     rcx, [rax]
0x14005bc39  mov     r8d, [rcx+4]
0x14005bc3d  mov     rax, [rbp+68h]
0x14005bc41  mov     rcx, [rax+8]
0x14005bc45  mov     rdx, [rcx+0F8h]
0x14005bc4c  mov     rax, [rbp+68h]
0x14005bc50  mov     rax, [rax]
0x14005bc53  mov     [rsp+68h+var_18], r10
0x14005bc58  mov     [rsp+68h+var_20], r9
0x14005bc5d  mov     [rsp+68h+var_28], r8d
0x14005bc62  mov     [rsp+68h+var_30], rdx
0x14005bc67  mov     [rsp+68h+var_38], 0
0x14005bc6f  lea     rcx, byte_14000DA20
0x14005bc76  mov     [rsp+68h+var_40], rcx
0x14005bc7b  mov     eax, [rax]
0x14005bc7d  mov     [rsp+68h+var_48], eax
0x14005bc81  lea     r9, aShimExceptionX; "Shim Exception %#x in module \"%hs\", l"...
0x14005bc88  mov     r8d, 0F5h
0x14005bc8e  lea     rdx, aShimexceptionh; "ShimExceptionHandler"
0x14005bc95  mov     ecx, 1
0x14005bc9a  call    AslLogCallPrintf
0x14005bc9f  mov     dword ptr [rbp+60h], 1
0x14005bca6  mov     eax, [rbp+60h]
0x14005bca9  add     rsp, 60h
0x14005bcad  pop     rbp
0x14005bcae  retn
```
