# CmsContainerRangeMap::InitializeMapIfRequired(void)

- ea: `0x14006a090`
- end: `0x14006a301`
- name: `?InitializeMapIfRequired@CmsContainerRangeMap@@AEAAJXZ`
- size: `625`
- prototype: `__int64 __fastcall(CmsContainerRangeMap *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14002d900`
- `0x140055570`
- `0x14006ab50`
- `0x1400c1ba0`
- `0x14012329c`
- `0x14012b35c`
- `0x14013c6d0`
- `0x140142358`
- `0x140147c6c`

## callees

- `0x14006a090`
- `0x1400ceda0`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006a2d9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006a2d9`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006a0b1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006a0b1`
- `ntoskrnl!ExAllocatePool2` at `0x14006a1b0`
- `ntoskrnl!ExAllocatePool2` at `0x14006a1b0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006a16c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006a16c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fe590`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fe590`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006a2f3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006a2f3`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006a0cd`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006a275`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006a0cd`
- `ntoskrnl!ExReleasePushLockEx` at `0x14006a275`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006a0df`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006a0df`

## string_xrefs

- `0x1401fe5a2`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsContainerRangeMap::InitializeMapIfRequired(CmsContainerRangeMap *this)
{
  unsigned int *v2; // rdi
  unsigned int v3; // ebx
  unsigned int *v4; // rbp
  unsigned int v5; // ebx
  _QWORD *v6; // r9
  unsigned int i; // eax
  unsigned int v8; // edx
  __int64 v9; // rsi
  ULONG CurrentProcessorNumber; // eax
  __int64 v11; // rdx
  __int64 Pool2; // rax
  int v13; // ecx
  unsigned int j; // r8d
  __int64 v15; // rax
  struct _NPAGED_LOOKASIDE_LIST *v17; // rcx
  _QWORD *v18; // rax

  v2 = 0;
  v3 = 0;
  ExAcquirePushLockSharedEx((char *)this + 40, 4);
  if ( *((_BYTE *)this + 54) )
    goto LABEL_31;
  ExReleasePushLockEx((char *)this + 40, 0);
  ExAcquirePushLockExclusiveEx((char *)this + 40, 0);
  if ( *((_BYTE *)this + 54) )
    goto LABEL_31;
  v4 = (unsigned int *)((char *)this + 8);
  v5 = *((_DWORD *)this + 12) >> 2;
  v6 = 0;
  if ( v5 < 3 )
    v5 = 3;
  while ( !v6 )
  {
    for ( i = 0; i < 0x48; ++i )
    {
      v8 = dword_140208F30[i];
      if ( v8 > v5 )
      {
        *((_DWORD *)this + 2) = v8;
        if ( v8 != -1 )
          goto LABEL_11;
LABEL_25:
        v5 >>= 2;
        goto LABEL_26;
      }
    }
    v8 = 7199369;
    *((_DWORD *)this + 2) = 7199369;
LABEL_11:
    v9 = 24LL * v8;
    if ( !is_mul_ok(v8, 0x18u) )
      v9 = -1;
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    if ( v9 != 7032 )
      goto LABEL_16;
    v2 = (unsigned int *)(qword_1402694C0 + 192LL * (CurrentProcessorNumber % NumProcessors));
    if ( *v2 < 0x1B78uLL )
    {
      v2 = 0;
LABEL_16:
      v11 = v9 + 16;
LABEL_17:
      Pool2 = ExAllocatePool2(66, v11, 1766871885, v6);
      v6 = (_QWORD *)Pool2;
      if ( (Pool2 & 0xF) != 0 )
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      if ( !Pool2 )
        goto LABEL_36;
      goto LABEL_35;
    }
    if ( *((_BYTE *)v2 + 8) )
    {
      v17 = (struct _NPAGED_LOOKASIDE_LIST *)(v2 + 16);
      if ( *((_BYTE *)v2 + 9) )
        v18 = ExAllocateFromNPagedLookasideList(v17);
      else
        v18 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v17);
    }
    else
    {
      if ( (int)*((_QWORD *)v2 + 11) <= (int)HIDWORD(*((_QWORD *)v2 + 11)) )
        goto LABEL_24;
      v13 = _InterlockedDecrement((volatile signed __int32 *)v2 + 22);
      if ( v13 < (int)v2[23] || v13 < 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v2 + 22);
LABEL_24:
        v11 = v2[1];
        goto LABEL_17;
      }
      v18 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v2 + 4);
    }
    v6 = v18;
    if ( !v18 )
      goto LABEL_24;
LABEL_35:
    *v6 = v2;
    v6 += 2;
LABEL_36:
    if ( !v6 )
      goto LABEL_25;
LABEL_26:
    v2 = 0;
    if ( v5 <= 1 )
      break;
  }
  *(_QWORD *)this = v6;
  if ( v6 )
  {
    memset(v6, 0, 24LL * *v4);
    for ( j = 0; j < *v4; *(_QWORD *)(*(_QWORD *)this + 24 * v15 + 16) = 0 )
      v15 = j++;
    v3 = 0;
    *((_BYTE *)this + 54) = 1;
  }
  else
  {
    v3 = -1073741670;
  }
LABEL_31:
  ExReleasePushLockEx((char *)this + 40, 0);
  return v3;
}

```

## disassembly

```asm
0x14006a090  push    rbx
0x14006a092  push    rbp
0x14006a093  push    rsi
0x14006a094  push    rdi
0x14006a095  push    r12
0x14006a097  push    r13
0x14006a099  push    r14
0x14006a09b  push    r15
0x14006a09d  sub     rsp, 28h
0x14006a0a1  mov     r14, rcx
0x14006a0a4  xor     edi, edi
0x14006a0a6  add     rcx, 28h ; '('
0x14006a0aa  mov     edx, 4
0x14006a0af  mov     ebx, edi
0x14006a0b1  call    cs:__imp_ExAcquirePushLockSharedEx
0x14006a0b8  nop     dword ptr [rax+rax+00h]
0x14006a0bd  cmp     [r14+36h], dil
0x14006a0c1  jnz     loc_14006A26F
0x14006a0c7  xor     edx, edx
0x14006a0c9  lea     rcx, [r14+28h]
0x14006a0cd  call    cs:__imp_ExReleasePushLockEx
0x14006a0d4  nop     dword ptr [rax+rax+00h]
0x14006a0d9  xor     edx, edx
0x14006a0db  lea     rcx, [r14+28h]
0x14006a0df  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006a0e6  nop     dword ptr [rax+rax+00h]
0x14006a0eb  cmp     [r14+36h], bl
0x14006a0ef  jnz     loc_14006A26F
0x14006a0f5  mov     ebx, [r14+30h]
0x14006a0f9  lea     rbp, [r14+8]
0x14006a0fd  shr     ebx, 2
0x14006a100  lea     r15, [r14+8]
0x14006a104  mov     r9d, edi
0x14006a107  cmp     ebx, 3
0x14006a10a  jnb     short loc_14006A111
0x14006a10c  mov     ebx, 3
0x14006a111  lea     rdx, dword_140208F30
0x14006a118  mov     r8, 0FFFFFFFFFFFFFFFFh
0x14006a11f  test    r9, r9
0x14006a122  jnz     loc_14006A220
0x14006a128  mov     eax, edi
0x14006a12a  nop     word ptr [rax+rax+00h]
0x14006a130  cmp     eax, 48h ; 'H'
0x14006a133  jnb     loc_14006A29C
0x14006a139  mov     ecx, eax
0x14006a13b  mov     edx, [rdx+rcx*4]
0x14006a13e  cmp     edx, ebx
0x14006a140  ja      short loc_14006A14D
0x14006a142  inc     eax
0x14006a144  lea     rdx, dword_140208F30
0x14006a14b  jmp     short loc_14006A130
0x14006a14d  mov     [r15], edx
0x14006a150  cmp     edx, 0FFFFFFFFh
0x14006a153  jnb     loc_14006A212
0x14006a159  mov     ecx, edx
0x14006a15b  mov     eax, 18h
0x14006a160  mul     rcx
0x14006a163  mov     rsi, rax
0x14006a166  cmovb   rsi, r8
0x14006a16a  xor     ecx, ecx; ProcNumber
0x14006a16c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14006a173  nop     dword ptr [rax+rax+00h]
0x14006a178  cmp     rsi, 1B78h
0x14006a17f  jnz     short loc_14006A1A1
0x14006a181  xor     edx, edx
0x14006a183  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14006a189  lea     rdi, [rdx+rdx*2]
0x14006a18d  shl     rdi, 6
0x14006a191  add     rdi, cs:qword_1402694C0
0x14006a198  mov     eax, [rdi]
0x14006a19a  cmp     rsi, rax
0x14006a19d  jbe     short loc_14006A1D5
0x14006a19f  xor     edi, edi
0x14006a1a1  lea     rdx, [rsi+10h]
0x14006a1a5  mov     ecx, 42h ; 'B'
0x14006a1aa  mov     r8d, 6950534Dh
0x14006a1b0  call    cs:__imp_ExAllocatePool2
0x14006a1b7  nop     dword ptr [rax+rax+00h]
0x14006a1bc  mov     r9, rax
0x14006a1bf  test    al, 0Fh
0x14006a1c1  jnz     loc_1401FE5A2
0x14006a1c7  test    rax, rax
0x14006a1ca  jz      loc_14006A2BD
0x14006a1d0  jmp     loc_14006A2B6
0x14006a1d5  cmp     byte ptr [rdi+8], 0
0x14006a1d9  jnz     loc_14006A2CB
0x14006a1df  mov     rcx, [rdi+58h]
0x14006a1e3  mov     rax, rcx
0x14006a1e6  shr     rax, 20h
0x14006a1ea  cmp     ecx, eax
0x14006a1ec  jle     short loc_14006A20D
0x14006a1ee  nop
0x14006a1ef  mov     ecx, 0FFFFFFFFh
0x14006a1f4  lock xadd [rdi+58h], ecx
0x14006a1f9  nop
0x14006a1fa  dec     ecx
0x14006a1fc  mov     eax, [rdi+5Ch]
0x14006a1ff  cmp     ecx, eax
0x14006a201  jge     loc_14006A2E7
0x14006a207  nop
0x14006a208  lock inc dword ptr [rdi+58h]
0x14006a20c  nop
0x14006a20d  mov     edx, [rdi+4]
0x14006a210  jmp     short loc_14006A1A5
0x14006a212  shr     ebx, 2
0x14006a215  xor     edi, edi
0x14006a217  cmp     ebx, 1
0x14006a21a  ja      loc_14006A111
0x14006a220  mov     [r14], r9
0x14006a223  test    r9, r9
0x14006a226  jz      short loc_14006A295
0x14006a228  mov     eax, [rbp+0]
0x14006a22b  xor     edx, edx; Val
0x14006a22d  mov     rcx, r9; void *
0x14006a230  lea     r8, [rax+rax*2]
0x14006a234  shl     r8, 3; Size
0x14006a238  call    memset
0x14006a23d  cmp     dword ptr [rbp+0], 0
0x14006a241  mov     r8d, edi
0x14006a244  jbe     short loc_14006A268
0x14006a246  nop     word ptr [rax+rax+00000000h]
0x14006a250  mov     eax, r8d
0x14006a253  inc     r8d
0x14006a256  lea     rdx, [rax+rax*2]
0x14006a25a  mov     rax, [r14]
0x14006a25d  mov     [rax+rdx*8+10h], rdi
0x14006a262  cmp     r8d, [rbp+0]
0x14006a266  jb      short loc_14006A250
0x14006a268  mov     ebx, edi
0x14006a26a  mov     byte ptr [r14+36h], 1
0x14006a26f  xor     edx, edx
0x14006a271  lea     rcx, [r14+28h]
0x14006a275  call    cs:__imp_ExReleasePushLockEx
0x14006a27c  nop     dword ptr [rax+rax+00h]
0x14006a281  mov     eax, ebx
0x14006a283  add     rsp, 28h
0x14006a287  pop     r15
0x14006a289  pop     r14
0x14006a28b  pop     r13
0x14006a28d  pop     r12
0x14006a28f  pop     rdi
0x14006a290  pop     rsi
0x14006a291  pop     rbp
0x14006a292  pop     rbx
0x14006a293  retn
0x14006a295  mov     ebx, 0C000009Ah
0x14006a29a  jmp     short loc_14006A26F
0x14006a29c  mov     edx, 6DDA89h
0x14006a2a1  mov     [r14+8], edx
0x14006a2a5  jmp     loc_14006A159
0x14006a2aa  mov     r9, rax
0x14006a2ad  test    rax, rax
0x14006a2b0  jz      loc_14006A20D
0x14006a2b6  mov     [r9], rdi
0x14006a2b9  add     r9, 10h
0x14006a2bd  test    r9, r9
0x14006a2c0  jnz     loc_14006A215
0x14006a2c6  jmp     loc_14006A212
0x14006a2cb  cmp     byte ptr [rdi+9], 0
0x14006a2cf  lea     rcx, [rdi+40h]; Lookaside
0x14006a2d3  jz      loc_1401FE590
0x14006a2d9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006a2e0  nop     dword ptr [rax+rax+00h]
0x14006a2e5  jmp     short loc_14006A2AA
0x14006a2e7  test    ecx, ecx
0x14006a2e9  js      loc_14006A207
0x14006a2ef  lea     rcx, [rdi+40h]; ListHead
0x14006a2f3  call    cs:__imp_ExpInterlockedPopEntrySList
0x14006a2fa  nop     dword ptr [rax+rax+00h]
0x14006a2ff  jmp     short loc_14006A2AA
0x1401fe590  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401fe597  nop     dword ptr [rax+rax+00h]
0x1401fe59c  nop
0x1401fe59d  jmp     loc_14006A2AA
0x1401fe5a2  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1401fe5a9  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
```
