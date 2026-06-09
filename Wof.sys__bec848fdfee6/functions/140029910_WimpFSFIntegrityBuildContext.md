# WimpFSFIntegrityBuildContext

- ea: `0x140029910`
- end: `0x140029ad8`
- name: `WimpFSFIntegrityBuildContext`
- size: `456`
- prototype: `__int64 __fastcall(PVOID Object, unsigned __int64, __int64, __int64, __int64, __int64, char, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400284d8`

## callees

- `0x1400119c0`
- `0x14002881c`
- `0x140029910`

## import_xrefs

- `ntoskrnl!RtlInitializeBitMap` at `0x140029a23`
- `ntoskrnl!RtlInitializeBitMap` at `0x140029a23`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140029a00`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140029a00`
- `ntoskrnl!RtlClearAllBits` at `0x140029a32`
- `ntoskrnl!RtlClearAllBits` at `0x140029a32`
- `ntoskrnl!ObfReferenceObject` at `0x140029a61`
- `ntoskrnl!ObfReferenceObject` at `0x140029a61`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002998c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002998c`

## pseudocode

```c
__int64 __fastcall WimpFSFIntegrityBuildContext(
        PVOID Object,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7,
        _QWORD *a8)
{
  unsigned __int64 v9; // rsi
  unsigned __int64 v13; // rsi
  unsigned __int64 v14; // rax
  __int64 v15; // rax
  size_t v16; // rbx
  char *PoolWithTag; // rax
  char *v18; // rdi
  NTSTATUS v19; // ebx

  v9 = (a2 + 4095) & 0xFFFFFFFFFFFFF000uLL;
  if ( v9 < a2 )
    return (unsigned int)-1073741675;
  v13 = v9 >> 12;
  if ( v13 > 0xFFFFFFFF )
    return (unsigned int)-1073741675;
  v14 = (unsigned int)(v13 + 31);
  if ( (unsigned int)v14 < (unsigned int)v13 )
    return (unsigned int)-1073741675;
  v15 = (v14 >> 3) & 0x1FFFFFFC;
  v16 = v15 + 256;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, v15 + 256, 0x69637077u);
  v18 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, v16);
      goto LABEL_8;
    }
    return (unsigned int)-1073741801;
  }
  if ( !PoolWithTag )
    return (unsigned int)-1073741801;
LABEL_8:
  v19 = ExInitializeLookasideListEx(
          (PLOOKASIDE_LIST_EX)(v18 + 64),
          WimpFSFAllocateMultiHashContext,
          WimpFSFFreeMultiHashContext,
          PagedPool,
          0,
          (unsigned int)(g_WimIntegrityMultiHashObjectLength + 1352),
          0x69637077u,
          0);
  if ( v19 < 0 )
  {
    WimFSFDestroyIntegrity(v18);
  }
  else
  {
    RtlInitializeBitMap((PRTL_BITMAP)v18, (PULONG)v18 + 64, v13);
    RtlClearAllBits((PRTL_BITMAP)v18);
    *((_QWORD *)v18 + 4) = a5;
    *((_QWORD *)v18 + 5) = a6;
    *((_QWORD *)v18 + 2) = a3;
    *((_QWORD *)v18 + 3) = a4;
    ObfReferenceObject(Object);
    *((_QWORD *)v18 + 20) = Object;
    *((_QWORD *)v18 + 21) = a2;
    *((_QWORD *)v18 + 22) = 0;
    *((_DWORD *)v18 + 46) = a7 != 0 ? 2 : 0;
    *a8 = v18;
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x140029910  push    rbx
0x140029912  push    rbp
0x140029913  push    rsi
0x140029914  push    rdi
0x140029915  push    r12
0x140029917  push    r13
0x140029919  push    r14
0x14002991b  push    r15
0x14002991d  sub     rsp, 48h
0x140029921  lea     rsi, [rdx+0FFFh]
0x140029928  mov     r12, r9
0x14002992b  and     rsi, 0FFFFFFFFFFFFF000h
0x140029932  mov     r13, r8
0x140029935  mov     r14, rdx
0x140029938  mov     r15, rcx
0x14002993b  cmp     rsi, rdx
0x14002993e  jb      loc_140029ABF
0x140029944  shr     rsi, 0Ch
0x140029948  mov     eax, 0FFFFFFFFh
0x14002994d  cmp     rsi, rax
0x140029950  ja      loc_140029ABF
0x140029956  lea     eax, [rsi+1Fh]
0x140029959  cmp     eax, esi
0x14002995b  jb      loc_140029ABF
0x140029961  shr     rax, 3
0x140029965  and     eax, 1FFFFFFCh
0x14002996a  lea     rbx, [rax+100h]
0x140029971  cmp     rbx, 100h
0x140029978  jb      loc_140029ABF
0x14002997e  mov     r8d, 69637077h; Tag
0x140029984  mov     rdx, rbx; NumberOfBytes
0x140029987  mov     ecx, 600h; PoolType
0x14002998c  call    cs:__imp_ExAllocatePoolWithTag
0x140029993  nop     dword ptr [rax+rax+00h]
0x140029998  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14002999f  mov     rdi, rax
0x1400299a2  jnz     loc_140029AA5
0x1400299a8  test    rax, rax
0x1400299ab  jz      loc_140029AAE
0x1400299b1  mov     r8, rbx; Size
0x1400299b4  xor     edx, edx; Val
0x1400299b6  mov     rcx, rax; void *
0x1400299b9  call    memset
0x1400299be  mov     edx, cs:g_WimIntegrityMultiHashObjectLength
0x1400299c4  lea     rcx, [rdi+40h]; Lookaside
0x1400299c8  xor     r9d, r9d
0x1400299cb  lea     r8, WimpFSFFreeMultiHashContext; Free
0x1400299d2  mov     [rsp+88h+Depth], r9w; Depth
0x1400299d8  add     edx, 548h
0x1400299de  mov     [rsp+88h+Tag], 69637077h; Tag
0x1400299e6  mov     rbp, rdi
0x1400299e9  mov     [rsp+88h+Size], rdx; Size
0x1400299ee  lea     rdx, WimpFSFAllocateMultiHashContext; Allocate
0x1400299f5  mov     [rsp+88h+Flags], r9d; Flags
0x1400299fa  mov     r9d, 1; PoolType
0x140029a00  call    cs:__imp_ExInitializeLookasideListEx
0x140029a07  nop     dword ptr [rax+rax+00h]
0x140029a0c  mov     ebx, eax
0x140029a0e  test    eax, eax
0x140029a10  js      loc_140029AB5
0x140029a16  lea     rdx, [rdi+100h]; BitMapBuffer
0x140029a1d  mov     r8d, esi; SizeOfBitMap
0x140029a20  mov     rcx, rdi; BitMapHeader
0x140029a23  call    cs:__imp_RtlInitializeBitMap
0x140029a2a  nop     dword ptr [rax+rax+00h]
0x140029a2f  mov     rcx, rdi; BitMapHeader
0x140029a32  call    cs:__imp_RtlClearAllBits
0x140029a39  nop     dword ptr [rax+rax+00h]
0x140029a3e  mov     rcx, [rsp+88h+arg_20]
0x140029a46  mov     [rdi+20h], rcx
0x140029a4a  mov     rcx, [rsp+88h+arg_28]
0x140029a52  mov     [rdi+28h], rcx
0x140029a56  mov     rcx, r15; Object
0x140029a59  mov     [rdi+10h], r13
0x140029a5d  mov     [rdi+18h], r12
0x140029a61  call    cs:__imp_ObfReferenceObject
0x140029a68  nop     dword ptr [rax+rax+00h]
0x140029a6d  neg     [rsp+88h+arg_30]
0x140029a74  mov     [rdi+0A0h], r15
0x140029a7b  sbb     eax, eax
0x140029a7d  mov     [rdi+0A8h], r14
0x140029a84  and     eax, 2
0x140029a87  mov     qword ptr [rdi+0B0h], 0
0x140029a92  mov     [rdi+0B8h], eax
0x140029a98  mov     rax, [rsp+88h+arg_38]
0x140029aa0  mov     [rax], rdi
0x140029aa3  jmp     short loc_140029AC4
0x140029aa5  test    rdi, rdi
0x140029aa8  jnz     loc_1400299BE
0x140029aae  mov     ebx, 0C0000017h
0x140029ab3  jmp     short loc_140029AC4
0x140029ab5  mov     rcx, rbp; P
0x140029ab8  call    WimFSFDestroyIntegrity
0x140029abd  jmp     short loc_140029AC4
0x140029abf  mov     ebx, 0C0000095h
0x140029ac4  mov     eax, ebx
0x140029ac6  add     rsp, 48h
0x140029aca  pop     r15
0x140029acc  pop     r14
0x140029ace  pop     r13
0x140029ad0  pop     r12
0x140029ad2  pop     rdi
0x140029ad3  pop     rsi
0x140029ad4  pop     rbp
0x140029ad5  pop     rbx
0x140029ad6  retn
```
