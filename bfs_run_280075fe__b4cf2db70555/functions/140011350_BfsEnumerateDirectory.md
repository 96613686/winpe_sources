# BfsEnumerateDirectory

- ea: `0x140011350`
- end: `0x140011450`
- name: `BfsEnumerateDirectory`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400061a0`

## callees

- `0x140011350`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140011380`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140011380`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140011426`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140011426`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400113c3`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400113c3`
- `ntoskrnl!RtlFindSetBits` at `0x1400113fc`
- `ntoskrnl!RtlFindSetBits` at `0x1400113fc`
- `ntoskrnl!RtlNumberOfSetBits` at `0x1400113d4`
- `ntoskrnl!RtlNumberOfSetBits` at `0x1400113d4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001136f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001136f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011432`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011432`

## pseudocode

```c
__int64 __fastcall BfsEnumerateDirectory(__int64 a1, int a2, _QWORD *a3)
{
  ULONG v6; // ebp
  unsigned int v7; // esi
  _QWORD *v8; // rdi
  _QWORD *v9; // rax
  __int64 v10; // r14
  ULONG v11; // eax
  struct _RTL_BITMAP BitMapHeader; // [rsp+20h] [rbp-48h] BYREF

  v6 = 0;
  v7 = -2147483622;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a1, 0);
  v8 = **(_QWORD ***)(a1 + 16);
  while ( 1 )
  {
    v9 = *(_QWORD **)(a1 + 16);
    if ( v8 == v9 )
      break;
    LODWORD(BitMapHeader.Buffer) = 0;
    *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
    v10 = *v9;
    RtlInitializeBitMap(&BitMapHeader, (PULONG)(*(_QWORD *)(*v9 + 16LL) + 15968LL), 0x1Eu);
    v11 = RtlNumberOfSetBits(&BitMapHeader);
    if ( a2 - v6 < v11 )
    {
      *a3 = 532LL * RtlFindSetBits(&BitMapHeader, 1u, a2 - v6) + *(_QWORD *)(v10 + 16) + 8LL;
      v7 = 0;
      break;
    }
    v8 = (_QWORD *)*v8;
    v6 = v11;
  }
  ExReleasePushLockSharedEx(a1, 0);
  KeLeaveCriticalRegion();
  return v7;
}

```

## disassembly

```asm
0x140011350  push    rbx
0x140011352  push    rbp
0x140011353  push    rsi
0x140011354  push    rdi
0x140011355  push    r12
0x140011357  push    r14
0x140011359  push    r15
0x14001135b  sub     rsp, 30h
0x14001135f  mov     r15, r8
0x140011362  mov     r12d, edx
0x140011365  mov     rbx, rcx
0x140011368  xor     ebp, ebp
0x14001136a  mov     esi, 8000001Ah
0x14001136f  call    cs:__imp_KeEnterCriticalRegion
0x140011376  nop     dword ptr [rax+rax+00h]
0x14001137b  xor     edx, edx
0x14001137d  mov     rcx, rbx
0x140011380  call    cs:__imp_ExAcquirePushLockSharedEx
0x140011387  nop     dword ptr [rax+rax+00h]
0x14001138c  mov     rax, [rbx+10h]
0x140011390  mov     rdi, [rax]
0x140011393  mov     rax, [rbx+10h]
0x140011397  cmp     rdi, rax
0x14001139a  jz      loc_140011421
0x1400113a0  xor     ecx, ecx
0x1400113a2  mov     qword ptr [rsp+68h+BitMapHeader+4], rcx
0x1400113a7  mov     [rsp+20h], rcx
0x1400113ac  mov     r14, [rax]
0x1400113af  lea     r8d, [rcx+1Eh]; SizeOfBitMap
0x1400113b3  lea     rcx, [rsp+68h+BitMapHeader]; BitMapHeader
0x1400113b8  mov     rdx, [r14+10h]
0x1400113bc  add     rdx, 3E60h; BitMapBuffer
0x1400113c3  call    cs:__imp_RtlInitializeBitMap
0x1400113ca  nop     dword ptr [rax+rax+00h]
0x1400113cf  lea     rcx, [rsp+68h+BitMapHeader]; BitMapHeader
0x1400113d4  call    cs:__imp_RtlNumberOfSetBits
0x1400113db  nop     dword ptr [rax+rax+00h]
0x1400113e0  mov     r8d, r12d
0x1400113e3  sub     r8d, ebp; HintIndex
0x1400113e6  cmp     r8d, eax
0x1400113e9  jb      short loc_1400113F2
0x1400113eb  mov     rdi, [rdi]
0x1400113ee  mov     ebp, eax
0x1400113f0  jmp     short loc_140011393
0x1400113f2  mov     edx, 1; NumberToFind
0x1400113f7  lea     rcx, [rsp+68h+BitMapHeader]; BitMapHeader
0x1400113fc  call    cs:__imp_RtlFindSetBits
0x140011403  nop     dword ptr [rax+rax+00h]
0x140011408  mov     ecx, eax
0x14001140a  imul    rdx, rcx, 214h
0x140011411  mov     rcx, [r14+10h]
0x140011415  add     rcx, 8
0x140011419  add     rcx, rdx
0x14001141c  mov     [r15], rcx
0x14001141f  xor     esi, esi
0x140011421  xor     edx, edx
0x140011423  mov     rcx, rbx
0x140011426  call    cs:__imp_ExReleasePushLockSharedEx
0x14001142d  nop     dword ptr [rax+rax+00h]
0x140011432  call    cs:__imp_KeLeaveCriticalRegion
0x140011439  nop     dword ptr [rax+rax+00h]
0x14001143e  mov     eax, esi
0x140011440  add     rsp, 30h
0x140011444  pop     r15
0x140011446  pop     r14
0x140011448  pop     r12
0x14001144a  pop     rdi
0x14001144b  pop     rsi
0x14001144c  pop     rbp
0x14001144d  pop     rbx
0x14001144e  retn
```
