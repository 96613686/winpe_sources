# CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>::Add(CCertChainList *)

- ea: `0x180013d78`
- end: `0x180013de1`
- name: `?Add@?$CPtrArrayTemplate@VCCertChainList@@U?$AutoPtrTraits@VCCertChainList@@@@@@QEAAHPEAVCCertChainList@@@Z`
- size: `105`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014c2c`

## callees

- `0x18000e8e2`
- `0x180013d78`
- `0x180015af8`

## pseudocode

```c
__int64 __fastcall CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>::Add(__int64 *a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v5; // rdx
  __int64 v6; // r8

  v2 = *((unsigned int *)a1 + 2);
  if ( (_DWORD)v2 == -1 )
    return 0;
  if ( !(unsigned int)CDynamicArray<CCertChainList *>::Grow() )
    return 0;
  memmove_0((void *)(*a1 + 8 * v2 + 8), (const void *)(*a1 + 8 * v2), 8LL * (unsigned int)(*((_DWORD *)a1 + 2) - v2));
  v5 = *((unsigned int *)a1 + 2);
  v6 = *a1;
  *((_DWORD *)a1 + 2) = v5 + 1;
  if ( !(v6 + 8 * v2) )
    return 0;
  *(_QWORD *)(v6 + 8 * v5) = a2;
  return 1;
}

```

## disassembly

```asm
0x180013d78  push    rbx
0x180013d7a  push    rbp
0x180013d7b  push    rsi
0x180013d7c  push    rdi
0x180013d7d  sub     rsp, 28h
0x180013d81  mov     esi, [rcx+8]
0x180013d84  mov     rbp, rdx
0x180013d87  mov     rdi, rcx
0x180013d8a  lea     edx, [rsi+1]
0x180013d8d  cmp     edx, 1
0x180013d90  jb      short loc_180013DD6
0x180013d92  call    ?Grow@?$CDynamicArray@PEAVCCertChainList@@@@QEAAHK@Z; CDynamicArray<CCertChainList *>::Grow(ulong)
0x180013d97  test    eax, eax
0x180013d99  jz      short loc_180013DD6
0x180013d9b  mov     r8d, [rdi+8]
0x180013d9f  mov     rax, [rdi]
0x180013da2  sub     r8d, esi
0x180013da5  shl     r8, 3; Size
0x180013da9  lea     rdx, [rax+rsi*8]; Src
0x180013dad  lea     rcx, [rdx+8]; void *
0x180013db1  call    memmove_0
0x180013db6  mov     edx, [rdi+8]
0x180013db9  mov     r8, [rdi]
0x180013dbc  lea     ecx, [rdx+1]
0x180013dbf  mov     [rdi+8], ecx
0x180013dc2  lea     rcx, [r8+rsi*8]
0x180013dc6  test    rcx, rcx
0x180013dc9  jz      short loc_180013DD6
0x180013dcb  mov     [r8+rdx*8], rbp
0x180013dcf  mov     eax, 1
0x180013dd4  jmp     short loc_180013DD8
0x180013dd6  xor     eax, eax
0x180013dd8  add     rsp, 28h
0x180013ddc  pop     rdi
0x180013ddd  pop     rsi
0x180013dde  pop     rbp
0x180013ddf  pop     rbx
0x180013de0  retn
```
