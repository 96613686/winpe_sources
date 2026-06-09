# TxfCreateTxfFcb

- ea: `0x140196b20`
- end: `0x140196e77`
- name: `TxfCreateTxfFcb`
- size: `855`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1401924c0`
- `0x140193510`
- `0x140195b64`
- `0x1401968a0`
- `0x140198300`
- `0x14019dcc8`
- `0x140294b6c`

## callees

- `0x140029140`
- `0x14002b990`
- `0x140059740`
- `0x140196b20`
- `0x140196e80`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140196ccc`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140196ccc`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1402ac2ab`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1402ac2ab`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140196bf1`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140196bf1`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140196b6a`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140196b6a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac2ff`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac314`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac333`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac2ff`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac314`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac333`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140196c2c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140196d40`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140196e0c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140196c2c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140196d40`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140196e0c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140196db6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140196e4e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402ac35b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140196db6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140196e4e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402ac35b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140196bcb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140196bcb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140196dea`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140196dea`
- `ntoskrnl!ExReleaseResourceLite` at `0x140196e69`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ac25a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140196e69`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ac25a`

## pseudocode

```c
_WORD *__fastcall TxfCreateTxfFcb(__int64 a1, __int64 a2, _QWORD *a3, __int16 a4, int a5, int a6)
{
  struct _RTL_AVL_TABLE *v10; // rdi
  _WORD *v12; // r13
  char v13; // bl
  _WORD **v14; // rax
  char v15; // di
  __int64 v16; // rdx
  _WORD *v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rax
  _QWORD *v20; // rax
  PVOID v21; // rax
  unsigned __int8 NewElement[3]; // [rsp+25h] [rbp-53h] BYREF
  _WORD *v23; // [rsp+28h] [rbp-50h]
  PVOID inserted; // [rsp+30h] [rbp-48h]
  __int128 Buffer; // [rsp+38h] [rbp-40h] BYREF
  PFAST_MUTEX FastMutex; // [rsp+48h] [rbp-30h]

  Buffer = 0;
  NewElement[0] = 0;
  v10 = (struct _RTL_AVL_TABLE *)(a1 + 6072);
  if ( a6 && !RtlNumberGenericTableElementsAvl(v10) )
    return 0;
  inserted = 0;
  v12 = 0;
  v23 = 0;
  FastMutex = (PFAST_MUTEX)(a1 + 6176);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 6176));
  v13 = 1;
  *(_QWORD *)&Buffer = *a3;
  BYTE8(Buffer) = 1;
  v14 = (_WORD **)RtlLookupElementGenericTableAvl(v10, &Buffer);
  inserted = v14;
  if ( v14 )
  {
    v12 = *v14;
    v23 = v12;
    ++v12[8];
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*((_QWORD *)v12 + 5) + 16LL) + 6176LL));
    v13 = 0;
    if ( a5 && !*((_QWORD *)v12 + 6) )
    {
      ExAcquireResourceExclusiveLite(*((PERESOURCE *)v12 + 17), 1u);
      v15 = 1;
      if ( !*((_QWORD *)v12 + 6) )
      {
        v21 = ExAllocateFromLookasideListEx(&TxfFcbExtensionLookasideList);
        *((_QWORD *)v12 + 6) = v21;
        memset(v21, 0, 0x50u);
        *(CLFS_LSN *)(*((_QWORD *)v12 + 6) + 40LL) = CLFS_LSN_INVALID_EXT;
      }
      goto LABEL_21;
    }
  }
  else if ( !a6 )
  {
    if ( a5 )
    {
      v12 = ExAllocateFromLookasideListEx(&TxfLargeFcbLookasideList);
      v23 = v12;
      memset(v12, 0, 0xF0u);
      v12[1] = 240;
      *((_DWORD *)v12 + 1) |= 2u;
      v17 = v12 + 80;
      *((_QWORD *)v12 + 6) = v12 + 80;
      *((CLFS_LSN *)v12 + 25) = CLFS_LSN_INVALID_EXT;
      v20 = (_QWORD *)(*((_QWORD *)v12 + 6) + 64LL);
      v20[1] = v20;
      *v20 = v20;
    }
    else
    {
      v12 = ExAllocateFromLookasideListEx(&TxfFcbLookasideList);
      v23 = v12;
      memset(v12, 0, 0xA0u);
      v12[1] = 160;
    }
    *v12 = 1812;
    *((_QWORD *)v12 + 17) = NtfsAllocateEresourcePriv(v17, v16, v18);
    *((_QWORD *)v12 + 1) = *a3;
    v12[8] = 1;
    *((_QWORD *)v12 + 10) = v12 + 36;
    *((_QWORD *)v12 + 9) = v12 + 36;
    *((_QWORD *)v12 + 12) = v12 + 44;
    *((_QWORD *)v12 + 11) = v12 + 44;
    *((_QWORD *)v12 + 14) = v12 + 52;
    *((_QWORD *)v12 + 13) = v12 + 52;
    *((CLFS_LSN *)v12 + 15) = CLFS_LSN_INVALID_EXT;
    BYTE8(Buffer) = 0;
    *(_QWORD *)&Buffer = v12;
    inserted = RtlInsertElementGenericTableAvl(v10, &Buffer, 0x10u, NewElement);
    if ( a2 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 64));
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 32));
    }
    v19 = *((_QWORD *)v12 + 5);
    if ( v19 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v19 + 32));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)v12 + 5) + 64LL), 0xFFFFFFFF) == 1 )
        TxfDeleteTxfRmcb(*((char **)v12 + 5));
    }
    *((_QWORD *)v12 + 5) = a2;
    if ( (a4 & 0x400) != 0 )
    {
      *((_DWORD *)v12 + 1) |= 0x1000000u;
      v15 = 0;
      goto LABEL_21;
    }
  }
  v15 = 0;
LABEL_21:
  if ( v15 )
    ExReleaseResourceLite(*((PERESOURCE *)v12 + 17));
  if ( v13 )
    ExReleaseFastMutexUnsafe(FastMutex);
  return v12;
}

```

## disassembly

```asm
0x140196b20  mov     [rsp+arg_8], rbx
0x140196b25  mov     [rsp+arg_10], rsi
0x140196b2a  mov     [rsp+arg_0], rcx
0x140196b2f  push    rdi
0x140196b30  push    r12
0x140196b32  push    r13
0x140196b34  push    r14
0x140196b36  push    r15
0x140196b38  sub     rsp, 50h
0x140196b3c  mov     r12d, r9d
0x140196b3f  mov     r14, r8
0x140196b42  mov     r15, rdx
0x140196b45  mov     rbx, rcx
0x140196b48  xorps   xmm0, xmm0
0x140196b4b  movups  [rsp+78h+Buffer], xmm0
0x140196b50  mov     [rsp+78h+NewElement], 0
0x140196b55  lea     rdi, [rcx+17B8h]
0x140196b5c  mov     esi, [rsp+78h+arg_28]
0x140196b63  test    esi, esi
0x140196b65  jz      short loc_140196B97
0x140196b67  mov     rcx, rdi; Table
0x140196b6a  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x140196b71  nop     dword ptr [rax+rax+00h]
0x140196b76  test    eax, eax
0x140196b78  jnz     short loc_140196B97
0x140196b7a  xor     eax, eax
0x140196b7c  lea     r11, [rsp+78h+var_28]
0x140196b81  mov     rbx, [r11+38h]
0x140196b85  mov     rsi, [r11+40h]
0x140196b89  mov     rsp, r11
0x140196b8c  pop     r15
0x140196b8e  pop     r14
0x140196b90  pop     r13
0x140196b92  pop     r12
0x140196b94  pop     rdi
0x140196b95  retn
0x140196b97  mov     [rsp+78h+var_58], 0
0x140196b9c  mov     [rsp+78h+var_57], 0
0x140196ba1  mov     [rsp+78h+var_55], 0
0x140196ba6  mov     [rsp+78h+var_56], 0
0x140196bab  mov     [rsp+78h+var_48], 0
0x140196bb4  xor     r13d, r13d
0x140196bb7  mov     [rsp+78h+var_50], r13
0x140196bbc  lea     rax, [rbx+1820h]
0x140196bc3  mov     [rsp+78h+FastMutex], rax
0x140196bc8  mov     rcx, rax; FastMutex
0x140196bcb  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140196bd2  nop     dword ptr [rax+rax+00h]
0x140196bd7  mov     bl, 1
0x140196bd9  mov     [rsp+78h+var_54], bl
0x140196bdd  mov     rax, [r14]
0x140196be0  mov     qword ptr [rsp+78h+Buffer], rax
0x140196be5  mov     byte ptr [rsp+78h+Buffer+8], bl
0x140196be9  lea     rdx, [rsp+78h+Buffer]; Buffer
0x140196bee  mov     rcx, rdi; Table
0x140196bf1  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140196bf8  nop     dword ptr [rax+rax+00h]
0x140196bfd  mov     [rsp+78h+var_48], rax
0x140196c02  test    rax, rax
0x140196c05  jnz     loc_140196D9A
0x140196c0b  test    esi, esi
0x140196c0d  jz      short loc_140196C17
0x140196c0f  xor     dil, dil
0x140196c12  jmp     loc_140196E40
0x140196c17  cmp     [rsp+78h+arg_20], 0
0x140196c1f  jnz     loc_140196D39
0x140196c25  lea     rcx, TxfFcbLookasideList; Lookaside
0x140196c2c  call    cs:__imp_ExAllocateFromLookasideListEx
0x140196c33  nop     dword ptr [rax+rax+00h]
0x140196c38  mov     r13, rax
0x140196c3b  mov     [rsp+78h+var_50], rax
0x140196c40  mov     esi, 0A0h
0x140196c45  mov     r8d, esi; Size
0x140196c48  xor     edx, edx; Val
0x140196c4a  mov     rcx, rax; void *
0x140196c4d  call    memset
0x140196c52  mov     [r13+2], si
0x140196c57  mov     [rsp+78h+var_57], 1
0x140196c5c  mov     eax, 714h
0x140196c61  mov     [r13+0], ax
0x140196c66  call    NtfsAllocateEresourcePriv
0x140196c6b  mov     [r13+88h], rax
0x140196c72  mov     rax, [r14]
0x140196c75  mov     [r13+8], rax
0x140196c79  mov     eax, 1
0x140196c7e  mov     [r13+10h], ax
0x140196c83  lea     rax, [r13+48h]
0x140196c87  mov     [rax+8], rax
0x140196c8b  mov     [rax], rax
0x140196c8e  lea     rax, [r13+58h]
0x140196c92  mov     [rax+8], rax
0x140196c96  mov     [rax], rax
0x140196c99  lea     rax, [r13+68h]
0x140196c9d  mov     [rax+8], rax
0x140196ca1  mov     [rax], rax
0x140196ca4  mov     rax, qword ptr cs:CLFS_LSN_INVALID_EXT
0x140196cab  mov     [r13+78h], rax
0x140196caf  mov     byte ptr [rsp+78h+Buffer+8], 0
0x140196cb4  mov     qword ptr [rsp+78h+Buffer], r13
0x140196cb9  lea     r9, [rsp+78h+NewElement]; NewElement
0x140196cbe  mov     r8d, 10h; BufferSize
0x140196cc4  lea     rdx, [rsp+78h+Buffer]; Buffer
0x140196cc9  mov     rcx, rdi; Table
0x140196ccc  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140196cd3  nop     dword ptr [rax+rax+00h]
0x140196cd8  mov     [rsp+78h+var_48], rax
0x140196cdd  mov     [rsp+78h+var_56], 1
0x140196ce2  test    r15, r15
0x140196ce5  jz      short loc_140196CF1
0x140196ce7  lock inc dword ptr [r15+40h]
0x140196cec  lock inc dword ptr [r15+20h]
0x140196cf1  mov     rax, [r13+28h]
0x140196cf5  test    rax, rax
0x140196cf8  jz      short loc_140196D1A
0x140196cfa  lock dec dword ptr [rax+20h]
0x140196cfe  mov     rcx, [r13+28h]
0x140196d02  mov     eax, 0FFFFFFFFh
0x140196d07  lock xadd [rcx+40h], eax
0x140196d0c  cmp     eax, 1
0x140196d0f  jnz     short loc_140196D1A
0x140196d11  mov     rcx, [r13+28h]; P
0x140196d15  call    TxfDeleteTxfRmcb
0x140196d1a  mov     [r13+28h], r15
0x140196d1e  bt      r12d, 0Ah
0x140196d23  jnb     loc_140196C0F
0x140196d29  or      dword ptr [r13+4], 1000000h
0x140196d31  xor     dil, dil
0x140196d34  jmp     loc_140196E40
0x140196d39  lea     rcx, TxfLargeFcbLookasideList; Lookaside
0x140196d40  call    cs:__imp_ExAllocateFromLookasideListEx
0x140196d47  nop     dword ptr [rax+rax+00h]
0x140196d4c  mov     r13, rax
0x140196d4f  mov     [rsp+78h+var_50], rax
0x140196d54  mov     esi, 0F0h
0x140196d59  mov     r8d, esi; Size
0x140196d5c  xor     edx, edx; Val
0x140196d5e  mov     rcx, rax; void *
0x140196d61  call    memset
0x140196d66  mov     [r13+2], si
0x140196d6b  or      dword ptr [r13+4], 2
0x140196d70  lea     rcx, [r13+0A0h]
0x140196d77  mov     [r13+30h], rcx
0x140196d7b  mov     rax, qword ptr cs:CLFS_LSN_INVALID_EXT
0x140196d82  mov     [rcx+28h], rax
0x140196d86  mov     rax, [r13+30h]
0x140196d8a  add     rax, 40h ; '@'
0x140196d8e  mov     [rax+8], rax
0x140196d92  mov     [rax], rax
0x140196d95  jmp     loc_140196C57
0x140196d9a  mov     r13, [rax]
0x140196d9d  mov     [rsp+78h+var_50], r13
0x140196da2  inc     word ptr [r13+10h]
0x140196da7  mov     rax, [r13+28h]
0x140196dab  mov     rcx, [rax+10h]
0x140196daf  add     rcx, 1820h; FastMutex
0x140196db6  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140196dbd  nop     dword ptr [rax+rax+00h]
0x140196dc2  xor     bl, bl
0x140196dc4  mov     [rsp+78h+var_54], bl
0x140196dc8  cmp     [rsp+78h+arg_20], 0
0x140196dd0  jz      loc_140196C0F
0x140196dd6  cmp     qword ptr [r13+30h], 0
0x140196ddb  jnz     loc_140196C0F
0x140196de1  mov     dl, 1; Wait
0x140196de3  mov     rcx, [r13+88h]; Resource
0x140196dea  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140196df1  nop     dword ptr [rax+rax+00h]
0x140196df6  mov     dil, 1
0x140196df9  mov     [rsp+78h+var_58], dil
0x140196dfe  cmp     qword ptr [r13+30h], 0
0x140196e03  jnz     short loc_140196E40
0x140196e05  lea     rcx, TxfFcbExtensionLookasideList; Lookaside
0x140196e0c  call    cs:__imp_ExAllocateFromLookasideListEx
0x140196e13  nop     dword ptr [rax+rax+00h]
0x140196e18  mov     [r13+30h], rax
0x140196e1c  mov     [rsp+78h+var_55], dil
0x140196e21  xor     edx, edx; Val
0x140196e23  mov     r8d, 50h ; 'P'; Size
0x140196e29  mov     rcx, rax; void *
0x140196e2c  call    memset
0x140196e31  mov     rcx, [r13+30h]
0x140196e35  mov     rax, qword ptr cs:CLFS_LSN_INVALID_EXT
0x140196e3c  mov     [rcx+28h], rax
0x140196e40  test    dil, dil
0x140196e43  jnz     short loc_140196E62
0x140196e45  test    bl, bl
0x140196e47  jz      short loc_140196E5A
0x140196e49  mov     rcx, [rsp+78h+FastMutex]; FastMutex
0x140196e4e  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140196e55  nop     dword ptr [rax+rax+00h]
0x140196e5a  mov     rax, r13
0x140196e5d  jmp     loc_140196B7C
0x140196e62  mov     rcx, [r13+88h]; Resource
0x140196e69  call    cs:__imp_ExReleaseResourceLite
0x140196e70  nop     dword ptr [rax+rax+00h]
0x140196e75  jmp     short loc_140196E45
0x1402ac230  push    rbx
0x1402ac232  push    rbp
0x1402ac233  push    rdi
0x1402ac234  sub     rsp, 20h
0x1402ac238  mov     rbp, rdx
0x1402ac23b  movzx   edi, cl
0x1402ac23e  test    cl, cl
0x1402ac240  jz      short loc_1402AC249
0x1402ac242  movzx   eax, cs:NtfsStatusDebugFlags
0x1402ac249  mov     rbx, [rbp+28h]
0x1402ac24d  cmp     byte ptr [rbp+20h], 0
0x1402ac251  jz      short loc_1402AC267
0x1402ac253  mov     rcx, [rbx+88h]; Resource
0x1402ac25a  call    cs:__imp_ExReleaseResourceLite
0x1402ac261  nop     dword ptr [rax+rax+00h]
0x1402ac266  nop
0x1402ac267  mov     eax, edi
0x1402ac269  test    dil, dil
0x1402ac26c  jz      loc_1402AC347
0x1402ac272  cmp     byte ptr [rbp+21h], 0
0x1402ac276  jz      loc_1402AC322
0x1402ac27c  cmp     qword ptr [rbx+88h], 0
0x1402ac284  jz      short loc_1402AC293
0x1402ac286  mov     rcx, [rbx+88h]; P
0x1402ac28d  call    NtfsFreeEresource
0x1402ac292  nop
0x1402ac293  cmp     byte ptr [rbp+22h], 0
0x1402ac297  jz      short loc_1402AC2B8
0x1402ac299  mov     rcx, [rbp+80h]
0x1402ac2a0  add     rcx, 17B8h; Table
0x1402ac2a7  mov     rdx, [rbp+30h]; Buffer
0x1402ac2ab  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1402ac2b2  nop     dword ptr [rax+rax+00h]
0x1402ac2b7  nop
0x1402ac2b8  cmp     qword ptr [rbx+28h], 0
0x1402ac2bd  jz      short loc_1402AC2E4
0x1402ac2bf  mov     rax, [rbx+28h]
0x1402ac2c3  lock dec dword ptr [rax+20h]
0x1402ac2c7  mov     rcx, [rbx+28h]
0x1402ac2cb  mov     eax, 0FFFFFFFFh
0x1402ac2d0  lock xadd [rcx+40h], eax
0x1402ac2d5  sub     eax, 1
0x1402ac2d8  jnz     short loc_1402AC2E4
0x1402ac2da  mov     rcx, [rbx+28h]; P
0x1402ac2de  call    TxfDeleteTxfRmcb
0x1402ac2e3  nop
0x1402ac2e4  mov     qword ptr [rbx+28h], 0
0x1402ac2ec  mov     rdx, rbx; Entry
0x1402ac2ef  cmp     dword ptr [rbp+0A0h], 0
0x1402ac2f6  jz      short loc_1402AC30D
0x1402ac2f8  lea     rcx, TxfLargeFcbLookasideList; Lookaside
0x1402ac2ff  call    cs:__imp_ExFreeToLookasideListEx
0x1402ac306  nop     dword ptr [rax+rax+00h]
0x1402ac30b  jmp     short loc_1402AC347
0x1402ac30d  lea     rcx, TxfFcbLookasideList; Lookaside
0x1402ac314  call    cs:__imp_ExFreeToLookasideListEx
0x1402ac31b  nop     dword ptr [rax+rax+00h]
0x1402ac320  jmp     short loc_1402AC347
0x1402ac322  cmp     byte ptr [rbp+23h], 0
0x1402ac326  jz      short loc_1402AC347
0x1402ac328  mov     rdx, [rbx+30h]; Entry
0x1402ac32c  lea     rcx, TxfFcbExtensionLookasideList; Lookaside
0x1402ac333  call    cs:__imp_ExFreeToLookasideListEx
0x1402ac33a  nop     dword ptr [rax+rax+00h]
0x1402ac33f  mov     qword ptr [rbx+30h], 0
0x1402ac347  cmp     byte ptr [rbp+24h], 0
0x1402ac34b  jz      short loc_1402AC368
0x1402ac34d  mov     rcx, [rbp+80h]
0x1402ac354  add     rcx, 1820h; FastMutex
0x1402ac35b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1402ac362  nop     dword ptr [rax+rax+00h]
0x1402ac367  nop
0x1402ac368  add     rsp, 20h
0x1402ac36c  pop     rdi
0x1402ac36d  pop     rbp
0x1402ac36e  pop     rbx
0x1402ac36f  retn
```
