# NtfsDeleteCcb

- ea: `0x140187a00`
- end: `0x140187de1`
- name: `NtfsDeleteCcb`
- size: `993`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14013a250`
- `0x14013b8c0`
- `0x1401e7934`

## callees

- `0x140187a00`
- `0x140188078`
- `0x140188d34`
- `0x140188f30`
- `0x14018999c`

## import_xrefs

- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140187c55`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140187c55`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187af0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187b36`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187bce`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187be6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187af0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187b36`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187bce`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187be6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187a36`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187ada`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187b83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187bb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187c0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187a36`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187ada`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187b83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187bb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187c0f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140187c95`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140187d25`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140187c95`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140187d25`
- `ntoskrnl!ExReleaseResourceLite` at `0x140187d74`
- `ntoskrnl!ExReleaseResourceLite` at `0x140187da8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140187d74`
- `ntoskrnl!ExReleaseResourceLite` at `0x140187da8`
- `ntoskrnl!ExAcquireFastMutex` at `0x140187a4a`
- `ntoskrnl!ExAcquireFastMutex` at `0x140187a4a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140187aa1`
- `ntoskrnl!ExReleaseFastMutex` at `0x140187aa1`

## pseudocode

```c
void __fastcall NtfsDeleteCcb(__int64 a1, __int16 **a2)
{
  __int16 *v2; // rax
  __int64 v5; // rax
  __int64 v6; // rdx
  _QWORD *v7; // rcx
  __int64 v8; // rdi
  int v9; // eax
  __int16 *v10; // rdx
  __int16 v11; // cx
  __int16 *v12; // rdx
  void *v13; // rcx
  void *v14; // rcx
  __int64 v15; // rax
  void *v16; // rcx
  __int64 v17; // rbp
  bool v18; // r12
  __int64 v19; // rax
  __int64 v20; // r15
  char v21; // cl
  __int64 v22; // r14
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // [rsp+60h] [rbp+8h] BYREF

  v2 = *a2;
  if ( **a2 == 1800 )
  {
    v13 = (void *)*((_QWORD *)v2 + 19);
    if ( v13 )
    {
      if ( (*((_DWORD *)v2 + 1) & 0x1000000) != 0 )
        NtOfsFreeReadContext(v13);
      else
        ExFreePoolWithTag(v13, 0);
      *((_QWORD *)*a2 + 19) = 0;
      if ( (*((_DWORD *)*a2 + 1) & 0x1000000) != 0 )
        _InterlockedAnd((volatile signed __int32 *)*a2 + 1, 0xFEFFFFFF);
    }
    v14 = (void *)*((_QWORD *)*a2 + 21);
    if ( v14 )
      ExFreePoolWithTag(v14, 0);
    v15 = *((_QWORD *)*a2 + 17);
    if ( v15 )
    {
      v16 = *(void **)(v15 + 96);
      if ( v16 != (void *)(v15 + 112) )
        ExFreePoolWithTag(v16, 0);
      ExFreeToLookasideListEx(&NtfsIndexContextLookasideList, *((PVOID *)*a2 + 17));
    }
  }
  if ( (*((_DWORD *)*a2 + 1) & 0x4000) != 0 )
    ExFreePoolWithTag(*((PVOID *)*a2 + 3), 0);
  ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a1 + 104) + 8LL));
  v5 = (__int64)(*a2 + 20);
  v6 = *(_QWORD *)v5;
  if ( *(_QWORD *)(*(_QWORD *)v5 + 8LL) != v5 || (v7 = (_QWORD *)*((_QWORD *)*a2 + 6), *v7 != v5) )
    __fastfail(3u);
  *v7 = v6;
  *(_QWORD *)(v6 + 8) = v7;
  *((_QWORD *)*a2 + 6) = 2989;
  *((_QWORD *)*a2 + 5) = 2989;
  ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a1 + 104) + 8LL));
  v8 = *((_QWORD *)*a2 + 10);
  if ( v8 )
  {
    v9 = *(_DWORD *)(v8 + 4);
    v25 = 0;
    if ( (v9 & 0x20) != 0 )
    {
      TxfTransMgrSearchAddTrans(*(_QWORD *)(a1 + 320), 0, *(_QWORD *)(v8 + 56), 84, 0, &v25);
      if ( v25 )
      {
        ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v25 + 24) + 80LL), 1u);
        v23 = v25;
        if ( *(_QWORD *)(v8 + 64) == *(_QWORD *)(v25 + 304) && *(_DWORD *)(v25 + 12) >= 2u )
        {
          --*(_DWORD *)(v25 + 4);
          *(_DWORD *)(v25 + 12) = *(_DWORD *)(v25 + 12) & 1 | (2 * (*(_DWORD *)(v25 + 12) >> 1) - 2);
          v23 = v25;
        }
        ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v23 + 24) + 80LL));
        LOBYTE(v24) = 1;
        TxfDereferenceTransaction(&v25, v24);
      }
    }
    if ( (*(_DWORD *)(v8 + 4) & 2) == 0 )
    {
      ObDereferenceObjectDeferDelete(*(PVOID *)(v8 + 56));
      v17 = *(_QWORD *)(v8 + 8);
      v18 = *(_DWORD *)(v8 + 36) != 0;
      v19 = *(_QWORD *)(v17 + 16);
      if ( v19 )
        v20 = *(_QWORD *)(v19 + 64);
      else
        v20 = 0;
      v21 = 0;
      do
      {
        v22 = 0;
        if ( v20 && !v21 )
        {
          ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v20 + 136), 1u);
          v21 = 1;
        }
        _InterlockedDecrement((volatile signed __int32 *)(v17 + 4));
        if ( v18 )
          --*(_DWORD *)(*(_QWORD *)(v17 + 16) + 32LL);
        if ( !*(_DWORD *)(v17 + 4) )
        {
          v22 = *(_QWORD *)(v17 + 40);
          TxfDeleteTxfVscb((PVOID)v17);
          v21 = 0;
          v18 = 0;
        }
        v17 = v22;
      }
      while ( v22 );
      if ( v21 && v20 )
        ExReleaseResourceLite(*(PERESOURCE *)(v20 + 136));
    }
    ExFreePoolWithTag(*(PVOID *)(v8 + 40), 0);
    ExFreeToLookasideListEx(&TxfFoLookasideList, (PVOID)v8);
  }
  v10 = *a2;
  if ( *a2 == (__int16 *)(a1 + 1008) || v10 == (__int16 *)(a1 + 1144) )
  {
    *v10 = 0;
    *a2 = 0;
  }
  else
  {
    v11 = *v10;
    *v10 = 0;
    v12 = *a2;
    if ( v11 == 1800 )
      ExFreeToLookasideListEx(&NtfsCcbLookasideList, v12);
    else
      ExFreeToLookasideListEx(&NtfsCcbDataLookasideList, v12);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x140187a00  push    rbx
0x140187a02  push    rbp
0x140187a03  push    rsi
0x140187a04  push    r13
0x140187a06  sub     rsp, 38h
0x140187a0a  mov     rax, [rdx]
0x140187a0d  mov     ebp, 708h
0x140187a12  xor     r13d, r13d
0x140187a15  mov     rbx, rdx
0x140187a18  mov     rsi, rcx
0x140187a1b  cmp     [rax], bp
0x140187a1e  jz      loc_140187B62
0x140187a24  mov     rcx, [rbx]
0x140187a27  test    dword ptr [rcx+4], 4000h
0x140187a2e  jz      short loc_140187A42
0x140187a30  mov     rcx, [rcx+18h]; P
0x140187a34  xor     edx, edx; Tag
0x140187a36  call    cs:__imp_ExFreePoolWithTag
0x140187a3d  nop     dword ptr [rax+rax+00h]
0x140187a42  mov     rcx, [rsi+68h]
0x140187a46  add     rcx, 8; FastMutex
0x140187a4a  call    cs:__imp_ExAcquireFastMutex
0x140187a51  nop     dword ptr [rax+rax+00h]
0x140187a56  mov     rax, [rbx]
0x140187a59  add     rax, 28h ; '('
0x140187a5d  mov     rdx, [rax]
0x140187a60  cmp     [rdx+8], rax
0x140187a64  jnz     loc_140187D91
0x140187a6a  mov     rcx, [rax+8]
0x140187a6e  cmp     [rcx], rax
0x140187a71  jnz     loc_140187D91
0x140187a77  mov     [rcx], rdx
0x140187a7a  mov     [rdx+8], rcx
0x140187a7e  mov     rax, [rbx]
0x140187a81  mov     [rsp+58h+arg_8], rdi
0x140187a86  mov     qword ptr [rax+30h], 0BADh
0x140187a8e  mov     rax, [rbx]
0x140187a91  mov     qword ptr [rax+28h], 0BADh
0x140187a99  mov     rcx, [rsi+68h]
0x140187a9d  add     rcx, 8; FastMutex
0x140187aa1  call    cs:__imp_ExReleaseFastMutex
0x140187aa8  nop     dword ptr [rax+rax+00h]
0x140187aad  mov     rax, [rbx]
0x140187ab0  mov     rdi, [rax+50h]
0x140187ab4  test    rdi, rdi
0x140187ab7  jz      short loc_140187AFC
0x140187ab9  mov     eax, [rdi+4]
0x140187abc  mov     [rsp+58h+arg_0], r13
0x140187ac1  test    al, 20h
0x140187ac3  jnz     loc_140187CE6
0x140187ac9  mov     eax, [rdi+4]
0x140187acc  test    al, 2
0x140187ace  jz      loc_140187C42
0x140187ad4  mov     rcx, [rdi+28h]; P
0x140187ad8  xor     edx, edx; Tag
0x140187ada  call    cs:__imp_ExFreePoolWithTag
0x140187ae1  nop     dword ptr [rax+rax+00h]
0x140187ae6  mov     rdx, rdi; Entry
0x140187ae9  lea     rcx, TxfFoLookasideList; Lookaside
0x140187af0  call    cs:__imp_ExFreeToLookasideListEx
0x140187af7  nop     dword ptr [rax+rax+00h]
0x140187afc  mov     rdx, [rbx]
0x140187aff  lea     rax, [rsi+3F0h]
0x140187b06  mov     rdi, [rsp+58h+arg_8]
0x140187b0b  cmp     rdx, rax
0x140187b0e  jz      short loc_140187B50
0x140187b10  lea     rax, [rsi+478h]
0x140187b17  cmp     rdx, rax
0x140187b1a  jz      short loc_140187B50
0x140187b1c  movzx   ecx, word ptr [rdx]
0x140187b1f  mov     [rdx], r13w
0x140187b23  mov     rdx, [rbx]; Entry
0x140187b26  cmp     cx, bp
0x140187b29  jz      loc_140187BDF
0x140187b2f  lea     rcx, NtfsCcbDataLookasideList; Lookaside
0x140187b36  call    cs:__imp_ExFreeToLookasideListEx
0x140187b3d  nop     dword ptr [rax+rax+00h]
0x140187b42  mov     [rbx], r13
0x140187b45  add     rsp, 38h
0x140187b49  pop     r13
0x140187b4b  pop     rsi
0x140187b4c  pop     rbp
0x140187b4d  pop     rbx
0x140187b4e  retn
0x140187b50  mov     [rdx], r13w
0x140187b54  mov     [rbx], r13
0x140187b57  add     rsp, 38h
0x140187b5b  pop     r13
0x140187b5d  pop     rsi
0x140187b5e  pop     rbp
0x140187b5f  pop     rbx
0x140187b60  retn
0x140187b62  mov     rcx, [rax+98h]; P
0x140187b69  test    rcx, rcx
0x140187b6c  jnz     loc_140187C00
0x140187b72  mov     rax, [rbx]
0x140187b75  mov     rcx, [rax+0A8h]; P
0x140187b7c  test    rcx, rcx
0x140187b7f  jz      short loc_140187B8F
0x140187b81  xor     edx, edx; Tag
0x140187b83  call    cs:__imp_ExFreePoolWithTag
0x140187b8a  nop     dword ptr [rax+rax+00h]
0x140187b8f  mov     rax, [rbx]
0x140187b92  mov     rax, [rax+88h]
0x140187b99  test    rax, rax
0x140187b9c  jz      loc_140187A24
0x140187ba2  mov     rcx, [rax+60h]; P
0x140187ba6  add     rax, 70h ; 'p'
0x140187baa  cmp     rcx, rax
0x140187bad  jz      short loc_140187BBD
0x140187baf  xor     edx, edx; Tag
0x140187bb1  call    cs:__imp_ExFreePoolWithTag
0x140187bb8  nop     dword ptr [rax+rax+00h]
0x140187bbd  mov     rdx, [rbx]
0x140187bc0  lea     rcx, NtfsIndexContextLookasideList; Lookaside
0x140187bc7  mov     rdx, [rdx+88h]; Entry
0x140187bce  call    cs:__imp_ExFreeToLookasideListEx
0x140187bd5  nop     dword ptr [rax+rax+00h]
0x140187bda  jmp     loc_140187A24
0x140187bdf  lea     rcx, NtfsCcbLookasideList; Lookaside
0x140187be6  call    cs:__imp_ExFreeToLookasideListEx
0x140187bed  nop     dword ptr [rax+rax+00h]
0x140187bf2  mov     [rbx], r13
0x140187bf5  add     rsp, 38h
0x140187bf9  pop     r13
0x140187bfb  pop     rsi
0x140187bfc  pop     rbp
0x140187bfd  pop     rbx
0x140187bfe  retn
0x140187c00  test    dword ptr [rax+4], 1000000h
0x140187c07  jnz     loc_140187DD7
0x140187c0d  xor     edx, edx; Tag
0x140187c0f  call    cs:__imp_ExFreePoolWithTag
0x140187c16  nop     dword ptr [rax+rax+00h]
0x140187c1b  mov     rax, [rbx]
0x140187c1e  mov     [rax+98h], r13
0x140187c25  mov     rcx, [rbx]
0x140187c28  mov     eax, [rcx+4]
0x140187c2b  bt      eax, 18h
0x140187c2f  jnb     loc_140187B72
0x140187c35  lock and dword ptr [rcx+4], 0FEFFFFFFh
0x140187c3d  jmp     loc_140187B72
0x140187c42  mov     rcx, [rdi+38h]; Object
0x140187c46  mov     [rsp+58h+arg_10], r12
0x140187c4b  mov     [rsp+58h+arg_18], r14
0x140187c50  mov     [rsp+58h+var_28], r15
0x140187c55  call    cs:__imp_ObDereferenceObjectDeferDelete
0x140187c5c  nop     dword ptr [rax+rax+00h]
0x140187c61  cmp     [rdi+24h], r13d
0x140187c65  mov     rbp, [rdi+8]
0x140187c69  setnz   r12b
0x140187c6d  mov     rax, [rbp+10h]
0x140187c71  test    rax, rax
0x140187c74  jz      loc_140187DCF
0x140187c7a  mov     r15, [rax+40h]
0x140187c7e  xor     cl, cl
0x140187c80  mov     r14, r13
0x140187c83  test    r15, r15
0x140187c86  jz      short loc_140187CA3
0x140187c88  test    cl, cl
0x140187c8a  jnz     short loc_140187CA3
0x140187c8c  mov     rcx, [r15+88h]; Resource
0x140187c93  mov     dl, 1; Wait
0x140187c95  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140187c9c  nop     dword ptr [rax+rax+00h]
0x140187ca1  mov     cl, 1
0x140187ca3  lock dec dword ptr [rbp+4]
0x140187ca7  test    r12b, r12b
0x140187caa  jz      short loc_140187CB3
0x140187cac  mov     rax, [rbp+10h]
0x140187cb0  dec     dword ptr [rax+20h]
0x140187cb3  cmp     [rbp+4], r13d
0x140187cb7  jz      loc_140187DB9
0x140187cbd  mov     rbp, r14
0x140187cc0  test    r14, r14
0x140187cc3  jnz     short loc_140187C80
0x140187cc5  mov     r14, [rsp+58h+arg_18]
0x140187cca  mov     r12, [rsp+58h+arg_10]
0x140187ccf  test    cl, cl
0x140187cd1  jnz     loc_140187D98
0x140187cd7  mov     r15, [rsp+58h+var_28]
0x140187cdc  mov     ebp, 708h
0x140187ce1  jmp     loc_140187AD4
0x140187ce6  mov     r8, [rdi+38h]
0x140187cea  lea     rax, [rsp+58h+arg_0]
0x140187cef  mov     rcx, [rsi+140h]
0x140187cf6  mov     r9d, 54h ; 'T'
0x140187cfc  mov     [rsp+58h+var_30], rax
0x140187d01  xor     edx, edx
0x140187d03  mov     [rsp+58h+var_38], r13
0x140187d08  call    TxfTransMgrSearchAddTrans
0x140187d0d  mov     rcx, [rsp+58h+arg_0]
0x140187d12  test    rcx, rcx
0x140187d15  jz      loc_140187AC9
0x140187d1b  mov     rcx, [rcx+18h]
0x140187d1f  mov     dl, 1; Wait
0x140187d21  add     rcx, 50h ; 'P'; Resource
0x140187d25  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140187d2c  nop     dword ptr [rax+rax+00h]
0x140187d31  mov     rcx, [rsp+58h+arg_0]
0x140187d36  mov     rax, [rcx+130h]
0x140187d3d  cmp     [rdi+40h], rax
0x140187d41  jnz     short loc_140187D6C
0x140187d43  cmp     dword ptr [rcx+0Ch], 2
0x140187d47  jb      short loc_140187D6C
0x140187d49  dec     dword ptr [rcx+4]
0x140187d4c  mov     rdx, [rsp+58h+arg_0]
0x140187d51  mov     ecx, [rdx+0Ch]
0x140187d54  mov     eax, ecx
0x140187d56  shr     eax, 1
0x140187d58  and     ecx, 1
0x140187d5b  lea     eax, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x140187d62  or      eax, ecx
0x140187d64  mov     [rdx+0Ch], eax
0x140187d67  mov     rcx, [rsp+58h+arg_0]
0x140187d6c  mov     rcx, [rcx+18h]
0x140187d70  add     rcx, 50h ; 'P'; Resource
0x140187d74  call    cs:__imp_ExReleaseResourceLite
0x140187d7b  nop     dword ptr [rax+rax+00h]
0x140187d80  mov     dl, 1
0x140187d82  lea     rcx, [rsp+58h+arg_0]
0x140187d87  call    TxfDereferenceTransaction
0x140187d8c  jmp     loc_140187AC9
0x140187d91  mov     ecx, 3
0x140187d96  int     29h; Win8: RtlFailFast(ecx)
0x140187d98  test    r15, r15
0x140187d9b  jz      loc_140187CD7
0x140187da1  mov     rcx, [r15+88h]; Resource
0x140187da8  call    cs:__imp_ExReleaseResourceLite
0x140187daf  nop     dword ptr [rax+rax+00h]
0x140187db4  jmp     loc_140187CD7
0x140187db9  mov     r14, [rbp+28h]
0x140187dbd  mov     rcx, rbp; Entry
0x140187dc0  call    TxfDeleteTxfVscb
0x140187dc5  xor     cl, cl
0x140187dc7  xor     r12b, r12b
0x140187dca  jmp     loc_140187CBD
0x140187dcf  mov     r15, r13
0x140187dd2  jmp     loc_140187C7E
0x140187dd7  call    NtOfsFreeReadContext
0x140187ddc  jmp     loc_140187C1B
```
