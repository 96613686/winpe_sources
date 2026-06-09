# BfsEnumerateDirectory

- ea: `0x1400114e8`
- end: `0x1400115e8`
- name: `BfsEnumerateDirectory`
- size: `256`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140006330`

## callees

- `0x1400114e8`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140011518`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140011518`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400115be`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400115be`
- `ntoskrnl!RtlInitializeBitMap` at `0x14001155b`
- `ntoskrnl!RtlInitializeBitMap` at `0x14001155b`
- `ntoskrnl!RtlFindSetBits` at `0x140011594`
- `ntoskrnl!RtlFindSetBits` at `0x140011594`
- `ntoskrnl!RtlNumberOfSetBits` at `0x14001156c`
- `ntoskrnl!RtlNumberOfSetBits` at `0x14001156c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011507`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011507`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400115ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400115ca`

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
0x1400114e8  push    rbx
0x1400114ea  push    rbp
0x1400114eb  push    rsi
0x1400114ec  push    rdi
0x1400114ed  push    r12
0x1400114ef  push    r14
0x1400114f1  push    r15
0x1400114f3  sub     rsp, 30h
0x1400114f7  mov     r15, r8
0x1400114fa  mov     r12d, edx
0x1400114fd  mov     rbx, rcx
0x140011500  xor     ebp, ebp
0x140011502  mov     esi, 8000001Ah
0x140011507  call    cs:__imp_KeEnterCriticalRegion
0x14001150e  nop     dword ptr [rax+rax+00h]
0x140011513  xor     edx, edx
0x140011515  mov     rcx, rbx
0x140011518  call    cs:__imp_ExAcquirePushLockSharedEx
0x14001151f  nop     dword ptr [rax+rax+00h]
0x140011524  mov     rax, [rbx+10h]
0x140011528  mov     rdi, [rax]
0x14001152b  mov     rax, [rbx+10h]
0x14001152f  cmp     rdi, rax
0x140011532  jz      loc_1400115B9
0x140011538  xor     ecx, ecx
0x14001153a  mov     qword ptr [rsp+68h+BitMapHeader+4], rcx
0x14001153f  mov     [rsp+20h], rcx
0x140011544  mov     r14, [rax]
0x140011547  lea     r8d, [rcx+1Eh]; SizeOfBitMap
0x14001154b  lea     rcx, [rsp+68h+BitMapHeader]; BitMapHeader
0x140011550  mov     rdx, [r14+10h]
0x140011554  add     rdx, 3E60h; BitMapBuffer
0x14001155b  call    cs:__imp_RtlInitializeBitMap
0x140011562  nop     dword ptr [rax+rax+00h]
0x140011567  lea     rcx, [rsp+68h+BitMapHeader]; BitMapHeader
0x14001156c  call    cs:__imp_RtlNumberOfSetBits
0x140011573  nop     dword ptr [rax+rax+00h]
0x140011578  mov     r8d, r12d
0x14001157b  sub     r8d, ebp; HintIndex
0x14001157e  cmp     r8d, eax
0x140011581  jb      short loc_14001158A
0x140011583  mov     rdi, [rdi]
0x140011586  mov     ebp, eax
0x140011588  jmp     short loc_14001152B
0x14001158a  mov     edx, 1; NumberToFind
0x14001158f  lea     rcx, [rsp+68h+BitMapHeader]; BitMapHeader
0x140011594  call    cs:__imp_RtlFindSetBits
0x14001159b  nop     dword ptr [rax+rax+00h]
0x1400115a0  mov     ecx, eax
0x1400115a2  imul    rdx, rcx, 214h
0x1400115a9  mov     rcx, [r14+10h]
0x1400115ad  add     rcx, 8
0x1400115b1  add     rcx, rdx
0x1400115b4  mov     [r15], rcx
0x1400115b7  xor     esi, esi
0x1400115b9  xor     edx, edx
0x1400115bb  mov     rcx, rbx
0x1400115be  call    cs:__imp_ExReleasePushLockSharedEx
0x1400115c5  nop     dword ptr [rax+rax+00h]
0x1400115ca  call    cs:__imp_KeLeaveCriticalRegion
0x1400115d1  nop     dword ptr [rax+rax+00h]
0x1400115d6  mov     eax, esi
0x1400115d8  add     rsp, 30h
0x1400115dc  pop     r15
0x1400115de  pop     r14
0x1400115e0  pop     r12
0x1400115e2  pop     rdi
0x1400115e3  pop     rsi
0x1400115e4  pop     rbp
0x1400115e5  pop     rbx
0x1400115e6  retn
```
