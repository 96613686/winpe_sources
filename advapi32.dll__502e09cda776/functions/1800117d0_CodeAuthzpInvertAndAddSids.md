# CodeAuthzpInvertAndAddSids

- ea: `0x1800117d0`
- end: `0x180011dc9`
- name: `CodeAuthzpInvertAndAddSids`
- size: `1529`
- prototype: `__int64 __usercall@<rax>(HANDLE TokenHandle@<rcx>, PSID Sid1@<rdx>, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000fc88`
- `0x180010910`

## callees

- `0x1800117d0`
- `0x180072042`
- `0x18007204e`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1800119a6`
- `ntdll!RtlEqualSid` at `0x180011a69`
- `ntdll!RtlEqualSid` at `0x180011a8a`
- `ntdll!RtlEqualSid` at `0x180011aa4`
- `ntdll!RtlEqualSid` at `0x1800119a6`
- `ntdll!RtlEqualSid` at `0x180011a69`
- `ntdll!RtlEqualSid` at `0x180011a8a`
- `ntdll!RtlEqualSid` at `0x180011aa4`
- `ntdll!RtlLengthSid` at `0x180011b6e`
- `ntdll!RtlLengthSid` at `0x180011bc3`
- `ntdll!RtlLengthSid` at `0x180011cba`
- `ntdll!RtlLengthSid` at `0x180011d63`
- `ntdll!RtlLengthSid` at `0x180011b6e`
- `ntdll!RtlLengthSid` at `0x180011bc3`
- `ntdll!RtlLengthSid` at `0x180011cba`
- `ntdll!RtlLengthSid` at `0x180011d63`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800118b0`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800118b0`
- `ntdll!RtlFreeSid` at `0x180011c2d`
- `ntdll!RtlFreeSid` at `0x180011dbb`
- `ntdll!RtlFreeSid` at `0x180011c2d`
- `ntdll!RtlFreeSid` at `0x180011dbb`
- `ntdll!RtlFreeHeap` at `0x180011c17`
- `ntdll!RtlFreeHeap` at `0x180011ce6`
- `ntdll!RtlFreeHeap` at `0x180011d92`
- `ntdll!RtlFreeHeap` at `0x180011c17`
- `ntdll!RtlFreeHeap` at `0x180011ce6`
- `ntdll!RtlFreeHeap` at `0x180011d92`
- `ntdll!NtQueryInformationToken` at `0x180011921`
- `ntdll!NtQueryInformationToken` at `0x180011d39`
- `ntdll!NtQueryInformationToken` at `0x180011921`
- `ntdll!NtQueryInformationToken` at `0x180011d39`
- `ntdll!RtlAllocateHeap` at `0x1800118e5`
- `ntdll!RtlAllocateHeap` at `0x180011b2c`
- `ntdll!RtlAllocateHeap` at `0x180011d06`
- `ntdll!RtlAllocateHeap` at `0x1800118e5`
- `ntdll!RtlAllocateHeap` at `0x180011b2c`
- `ntdll!RtlAllocateHeap` at `0x180011d06`

## pseudocode

```c
char __fastcall CodeAuthzpInvertAndAddSids(
        HANDLE TokenHandle,
        unsigned __int8 *Sid1,
        unsigned int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int *a7,
        _QWORD *a8)
{
  __int64 v8; // rbp
  __int64 v9; // r12
  unsigned int *v13; // rdi
  NTSTATUS v14; // eax
  unsigned int v15; // esi
  unsigned int v16; // r13d
  _DWORD *v17; // rax
  __int64 v18; // r12
  __int64 v19; // rbx
  PSID v20; // rbp
  unsigned __int8 *v21; // rsi
  unsigned int i; // edi
  unsigned int v23; // edx
  _BYTE *v24; // r8
  unsigned int v25; // r10d
  int v26; // r11d
  __int64 j; // r9
  unsigned int v28; // r13d
  char *v29; // rax
  char *v30; // r12
  unsigned int v31; // r15d
  unsigned int v32; // r14d
  char *v33; // rsi
  __int64 v34; // rbp
  __int64 v35; // rbx
  PSID *v36; // rdi
  ULONG v37; // eax
  __int64 v38; // rbx
  unsigned int v39; // ebp
  __int64 v40; // r14
  ULONG v41; // eax
  __int64 v42; // rcx
  __int64 v43; // rbx
  PSID *v45; // r12
  unsigned int k; // ebx
  ULONG v47; // eax
  ULONG ReturnLength; // [rsp+60h] [rbp-98h] BYREF
  unsigned int v49; // [rsp+64h] [rbp-94h]
  char *Heap; // [rsp+68h] [rbp-90h]
  PSID Sid1a; // [rsp+70h] [rbp-88h] BYREF
  int v52; // [rsp+78h] [rbp-80h]
  _DWORD *v53; // [rsp+80h] [rbp-78h]
  __int64 v54; // [rsp+88h] [rbp-70h]
  __int64 v55; // [rsp+90h] [rbp-68h]
  _QWORD *v56; // [rsp+98h] [rbp-60h]
  unsigned int *v57; // [rsp+A0h] [rbp-58h]
  struct _SID_IDENTIFIER_AUTHORITY v58; // [rsp+A8h] [rbp-50h] BYREF

  v8 = a4;
  v9 = a6;
  v52 = a5;
  v57 = a7;
  v56 = a8;
  v55 = a4;
  v54 = a6;
  *(_DWORD *)v58.Value = 0;
  *(_WORD *)&v58.Value[4] = 1280;
  Sid1a = 0;
  if ( Sid1 && RtlAllocateAndInitializeSid(&v58, 1u, 0xAu, 0, 0, 0, 0, 0, 0, 0, &Sid1a) < 0 )
    goto LABEL_65;
  v13 = 0;
  Heap = 0;
  if ( TokenHandle )
  {
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x80u);
    v13 = (unsigned int *)Heap;
    if ( Heap )
    {
      ReturnLength = 0;
      v14 = NtQueryInformationToken(TokenHandle, TokenGroups, Heap, 0x80u, &ReturnLength);
      if ( v14 == -1073741789 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
        Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ReturnLength);
        v13 = (unsigned int *)Heap;
        if ( !Heap )
          goto LABEL_64;
        v14 = NtQueryInformationToken(TokenHandle, TokenGroups, Heap, ReturnLength, &ReturnLength);
      }
      if ( v14 >= 0 )
        goto LABEL_7;
LABEL_64:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
      goto LABEL_65;
    }
  }
LABEL_7:
  if ( v13 )
  {
    v15 = 0;
    v16 = 0;
    v49 = 0;
    if ( *v13 )
    {
      v17 = v13 + 2;
      v53 = v13 + 2;
      do
      {
        if ( v8 && a3 )
        {
          v18 = 4LL * v16;
          v19 = v8;
          v20 = Sid1a;
          v21 = *(unsigned __int8 **)&v13[v18 + 2];
          if ( Sid1 && Sid1a && RtlEqualSid(Sid1a, *(PSID *)&v13[v18 + 2]) )
            v21 = Sid1;
          for ( i = 0; i < a3; ++i )
          {
            if ( v20 && Sid1 && *(_DWORD *)(v19 + 8) == -1 && RtlEqualSid(v20, *(PSID *)v19) )
            {
              if ( RtlEqualSid(Sid1, v21) )
                goto LABEL_38;
            }
            else
            {
              v23 = *(_DWORD *)(v19 + 8);
              v24 = *(_BYTE **)v19;
              if ( v23 == -1 )
              {
                if ( RtlEqualSid(*(PSID *)v19, v21) )
                  goto LABEL_38;
              }
              else if ( *v24 == *v21
                     && v24[2] == v21[2]
                     && v24[3] == v21[3]
                     && v24[4] == v21[4]
                     && v24[5] == v21[5]
                     && v24[6] == v21[6]
                     && v24[7] == v21[7] )
              {
                v25 = (unsigned __int8)v24[1];
                v26 = v21[1];
                if ( (unsigned __int8)v26 >= (unsigned __int8)v25 )
                {
                  for ( j = 0; (unsigned int)j < v23; j = (unsigned int)(j + 1) )
                  {
                    if ( *(_DWORD *)&v24[4 * j + 8] != *(_DWORD *)&v21[4 * j + 8] )
                      goto LABEL_35;
                  }
                  while ( v23 < v25 )
                  {
                    if ( *(_DWORD *)&v24[4 * v23 + 8] != *(_DWORD *)&v21[4 * (v26 - v25) + 8 + 4 * v23] )
                      goto LABEL_35;
                    ++v23;
                  }
LABEL_38:
                  v13 = (unsigned int *)Heap;
                  memmove_0(&v53[v18], &Heap[16 * v16 + 24], 16LL * (*(_DWORD *)Heap + ~v16));
                  --*v13;
                  v15 = v49;
                  --v16;
                  goto LABEL_39;
                }
              }
            }
LABEL_35:
            v19 += 16;
          }
          v45 = (PSID *)&v53[v18];
          v13 = (unsigned int *)Heap;
          v15 = v49;
        }
        else
        {
          v45 = (PSID *)&v17[4 * v16];
        }
        v15 += RtlLengthSid(*v45) + 16;
        v49 = v15;
LABEL_39:
        v8 = v55;
        v17 = v13 + 2;
        ++v16;
      }
      while ( v16 < *v13 );
      v9 = v54;
    }
    if ( v9 )
    {
      v28 = v52;
      for ( k = 0; k < v28; v15 += v47 + 16 )
        v47 = RtlLengthSid(*(PSID *)(v9 + 16LL * k++));
    }
    else
    {
      v28 = 0;
    }
    v29 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
    v30 = v29;
    if ( v29 )
    {
      v31 = *v13;
      v32 = 0;
      v33 = &v29[16 * *v13 + 16 * v28];
      if ( *v13 )
      {
        v34 = 0;
        do
        {
          v35 = 16 * v34;
          v36 = (PSID *)&v13[4 * v34];
          v37 = RtlLengthSid(v36[1]);
          *(_QWORD *)&v30[v35] = v33;
          *(_DWORD *)&v30[v35 + 8] = 0;
          v38 = v37;
          memcpy_0(v33, v36[1], v37);
          v13 = (unsigned int *)Heap;
          v33 += v38;
          ++v32;
          ++v34;
        }
        while ( v32 < v31 );
      }
      v39 = 0;
      if ( v28 )
      {
        v40 = v54;
        do
        {
          v41 = RtlLengthSid(*(PSID *)(v40 + 16LL * v39));
          v42 = 2LL * v31;
          v43 = v41;
          *(_QWORD *)&v30[8 * v42] = v33;
          *(_DWORD *)&v30[8 * v42 + 8] = 0;
          memcpy_0(v33, *(const void **)(v40 + 16LL * v39), v41);
          ++v31;
          v33 += v43;
          ++v39;
        }
        while ( v39 < v28 );
        v13 = (unsigned int *)Heap;
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
      if ( Sid1a )
        RtlFreeSid(Sid1a);
      *v56 = v30;
      *v57 = v31;
      return 1;
    }
    goto LABEL_64;
  }
LABEL_65:
  if ( Sid1a )
    RtlFreeSid(Sid1a);
  return 0;
}

```

## disassembly

```asm
0x1800117d0  mov     r11, rsp
0x1800117d3  mov     [r11+18h], rbx
0x1800117d7  push    rbp
0x1800117d8  push    rsi
0x1800117d9  push    rdi
0x1800117da  push    r12
0x1800117dc  push    r13
0x1800117de  push    r14
0x1800117e0  push    r15
0x1800117e2  sub     rsp, 0C0h
0x1800117e9  mov     rax, cs:__security_cookie
0x1800117f0  xor     rax, rsp
0x1800117f3  mov     [rsp+0F8h+var_48], rax
0x1800117fb  mov     eax, [rsp+0F8h+arg_20]
0x180011802  mov     rbp, r9
0x180011805  mov     r12, [rsp+0F8h+arg_28]
0x18001180d  mov     r15d, r8d
0x180011810  mov     [rsp+0F8h+var_80], eax
0x180011814  mov     r14, rdx
0x180011817  mov     rax, [rsp+0F8h+arg_30]
0x18001181f  mov     rbx, rcx
0x180011822  mov     [rsp+0F8h+var_58], rax
0x18001182a  mov     rax, [rsp+0F8h+arg_38]
0x180011832  mov     [rsp+0F8h+var_60], rax
0x18001183a  mov     [rsp+0F8h+var_68], r9
0x180011842  mov     [rsp+0F8h+var_70], r12
0x18001184a  mov     dword ptr [r11-50h], 0
0x180011852  mov     word ptr [r11-4Ch], 500h
0x180011859  mov     [rsp+0F8h+Sid1], 0
0x180011862  test    rdx, rdx
0x180011865  jz      short loc_1800118C4
0x180011867  lea     rax, [rsp+0F8h+Sid1]
0x18001186c  xor     r9d, r9d; SubAuthority1
0x18001186f  mov     [rsp+0F8h+Sid], rax; Sid
0x180011874  lea     rcx, [r11-50h]; IdentifierAuthority
0x180011878  mov     [rsp+0F8h+SubAuthority7], 0; SubAuthority7
0x180011880  mov     r8d, 0Ah; SubAuthority0
0x180011886  mov     [rsp+0F8h+SubAuthority6], 0; SubAuthority6
0x18001188e  mov     dl, 1; SubAuthorityCount
0x180011890  mov     [rsp+0F8h+SubAuthority5], 0; SubAuthority5
0x180011898  mov     [rsp+0F8h+SubAuthority4], 0; SubAuthority4
0x1800118a0  mov     [rsp+0F8h+SubAuthority3], 0; SubAuthority3
0x1800118a8  mov     [rsp+0F8h+SubAuthority2], 0; SubAuthority2
0x1800118b0  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800118b7  nop     dword ptr [rax+rax+00h]
0x1800118bc  test    eax, eax
0x1800118be  js      loc_180011D9E
0x1800118c4  xor     edi, edi
0x1800118c6  mov     [rsp+0F8h+var_90], rdi
0x1800118cb  test    rbx, rbx
0x1800118ce  jz      short loc_180011940
0x1800118d0  mov     rcx, gs:60h
0x1800118d9  xor     edx, edx; Flags
0x1800118db  mov     r8d, 80h; Size
0x1800118e1  mov     rcx, [rcx+30h]; HeapHandle
0x1800118e5  call    cs:__imp_RtlAllocateHeap
0x1800118ec  nop     dword ptr [rax+rax+00h]
0x1800118f1  mov     [rsp+0F8h+var_90], rax
0x1800118f6  mov     rdi, rax
0x1800118f9  test    rax, rax
0x1800118fc  jz      short loc_180011940
0x1800118fe  lea     rax, [rsp+0F8h+ReturnLength]
0x180011903  mov     [rsp+0F8h+ReturnLength], 0
0x18001190b  mov     r9d, 80h; TokenInformationLength
0x180011911  mov     qword ptr [rsp+0F8h+SubAuthority2], rax; ReturnLength
0x180011916  mov     r8, rdi; TokenInformation
0x180011919  mov     edx, 2; TokenInformationClass
0x18001191e  mov     rcx, rbx; TokenHandle
0x180011921  call    cs:__imp_NtQueryInformationToken
0x180011928  nop     dword ptr [rax+rax+00h]
0x18001192d  cmp     eax, 0C0000023h
0x180011932  jz      loc_180011CD4
0x180011938  test    eax, eax
0x18001193a  js      loc_180011D80
0x180011940  test    rdi, rdi
0x180011943  jz      loc_180011D9E
0x180011949  xor     esi, esi
0x18001194b  xor     r13d, r13d
0x18001194e  mov     [rsp+0F8h+var_94], esi
0x180011952  cmp     [rdi], esi
0x180011954  jbe     loc_180011B0E
0x18001195a  lea     rax, [rdi+8]
0x18001195e  mov     [rsp+0F8h+var_78], rax
0x180011966  nop     word ptr [rax+rax+00000000h]
0x180011970  mov     r12d, r13d
0x180011973  test    rbp, rbp
0x180011976  jz      loc_180011DAF
0x18001197c  test    r15d, r15d
0x18001197f  jz      loc_180011DAF
0x180011985  shl     r12, 4
0x180011989  mov     rbx, rbp
0x18001198c  mov     rbp, [rsp+0F8h+Sid1]
0x180011991  mov     rsi, [r12+rdi+8]
0x180011996  test    r14, r14
0x180011999  jz      short loc_1800119B8
0x18001199b  test    rbp, rbp
0x18001199e  jz      short loc_1800119B8
0x1800119a0  mov     rdx, rsi; Sid2
0x1800119a3  mov     rcx, rbp; Sid1
0x1800119a6  call    cs:__imp_RtlEqualSid
0x1800119ad  nop     dword ptr [rax+rax+00h]
0x1800119b2  test    al, al
0x1800119b4  cmovnz  rsi, r14
0x1800119b8  xor     edi, edi
0x1800119ba  nop     word ptr [rax+rax+00h]
0x1800119c0  cmp     edi, r15d
0x1800119c3  jnb     loc_180011CA5
0x1800119c9  test    rbp, rbp
0x1800119cc  jz      short loc_1800119DD
0x1800119ce  test    r14, r14
0x1800119d1  jz      short loc_1800119DD
0x1800119d3  cmp     dword ptr [rbx+8], 0FFFFFFFFh
0x1800119d7  jz      loc_180011A84
0x1800119dd  mov     edx, [rbx+8]
0x1800119e0  mov     r8, [rbx]
0x1800119e3  cmp     edx, 0FFFFFFFFh
0x1800119e6  jz      short loc_180011A63
0x1800119e8  movzx   eax, byte ptr [rsi]
0x1800119eb  cmp     [r8], al
0x1800119ee  jnz     loc_180011A79
0x1800119f4  movzx   eax, byte ptr [rsi+2]
0x1800119f8  cmp     [r8+2], al
0x1800119fc  jnz     short loc_180011A79
0x1800119fe  movzx   eax, byte ptr [rsi+3]
0x180011a02  cmp     [r8+3], al
0x180011a06  jnz     short loc_180011A79
0x180011a08  movzx   eax, byte ptr [rsi+4]
0x180011a0c  cmp     [r8+4], al
0x180011a10  jnz     short loc_180011A79
0x180011a12  movzx   eax, byte ptr [rsi+5]
0x180011a16  cmp     [r8+5], al
0x180011a1a  jnz     short loc_180011A79
0x180011a1c  movzx   eax, byte ptr [rsi+6]
0x180011a20  cmp     [r8+6], al
0x180011a24  jnz     short loc_180011A79
0x180011a26  movzx   eax, byte ptr [rsi+7]
0x180011a2a  cmp     [r8+7], al
0x180011a2e  jnz     short loc_180011A79
0x180011a30  movzx   r10d, byte ptr [r8+1]
0x180011a35  movzx   r11d, byte ptr [rsi+1]
0x180011a3a  cmp     r11b, r10b
0x180011a3d  jb      short loc_180011A79
0x180011a3f  xor     r9d, r9d
0x180011a42  cmp     r9d, edx
0x180011a45  jnb     loc_180011C7D
0x180011a4b  mov     eax, [rsi+r9*4+8]
0x180011a50  lea     rcx, ds:8[r9*4]
0x180011a58  cmp     [r8+rcx], eax
0x180011a5c  jnz     short loc_180011A79
0x180011a5e  inc     r9d
0x180011a61  jmp     short loc_180011A42
0x180011a63  mov     rdx, rsi; Sid2
0x180011a66  mov     rcx, r8; Sid1
0x180011a69  call    cs:__imp_RtlEqualSid
0x180011a70  nop     dword ptr [rax+rax+00h]
0x180011a75  test    al, al
0x180011a77  jnz     short loc_180011AB4
0x180011a79  inc     edi
0x180011a7b  add     rbx, 10h
0x180011a7f  jmp     loc_1800119C0
0x180011a84  mov     rdx, [rbx]; Sid2
0x180011a87  mov     rcx, rbp; Sid1
0x180011a8a  call    cs:__imp_RtlEqualSid
0x180011a91  nop     dword ptr [rax+rax+00h]
0x180011a96  test    al, al
0x180011a98  jz      loc_1800119DD
0x180011a9e  mov     rdx, rsi; Sid2
0x180011aa1  mov     rcx, r14; Sid1
0x180011aa4  call    cs:__imp_RtlEqualSid
0x180011aab  nop     dword ptr [rax+rax+00h]
0x180011ab0  test    al, al
0x180011ab2  jz      short loc_180011A79
0x180011ab4  mov     rdi, [rsp+0F8h+var_90]
0x180011ab9  lea     edx, [r13+1]
0x180011abd  mov     rcx, [rsp+0F8h+var_78]
0x180011ac5  mov     r8d, r13d
0x180011ac8  not     r8d
0x180011acb  shl     rdx, 4
0x180011acf  add     rdx, 8
0x180011ad3  add     rcx, r12; void *
0x180011ad6  add     r8d, [rdi]
0x180011ad9  add     rdx, rdi; Src
0x180011adc  shl     r8, 4; Size
0x180011ae0  call    memmove_0
0x180011ae5  dec     dword ptr [rdi]
0x180011ae7  mov     esi, [rsp+0F8h+var_94]
0x180011aeb  dec     r13d
0x180011aee  mov     rbp, [rsp+0F8h+var_68]
0x180011af6  lea     rax, [rdi+8]
0x180011afa  inc     r13d
0x180011afd  cmp     r13d, [rdi]
0x180011b00  jb      loc_180011970
0x180011b06  mov     r12, [rsp+0F8h+var_70]
0x180011b0e  test    r12, r12
0x180011b11  jnz     loc_180011D4A
0x180011b17  xor     r13d, r13d
0x180011b1a  mov     rcx, gs:60h
0x180011b23  xor     edx, edx; Flags
0x180011b25  mov     r8d, esi; Size
0x180011b28  mov     rcx, [rcx+30h]; HeapHandle
0x180011b2c  call    cs:__imp_RtlAllocateHeap
0x180011b33  nop     dword ptr [rax+rax+00h]
0x180011b38  mov     r12, rax
0x180011b3b  test    rax, rax
0x180011b3e  jz      loc_180011D80
0x180011b44  mov     r15d, [rdi]
0x180011b47  xor     r14d, r14d
0x180011b4a  lea     esi, [r15+r13]
0x180011b4e  shl     rsi, 4
0x180011b52  add     rsi, rax
0x180011b55  test    r15d, r15d
0x180011b58  jz      short loc_180011BAB
0x180011b5a  xor     ebp, ebp
0x180011b5c  nop     dword ptr [rax+00h]
0x180011b60  mov     rbx, rbp
0x180011b63  shl     rbx, 4
0x180011b67  add     rdi, rbx
0x180011b6a  mov     rcx, [rdi+8]; Sid
0x180011b6e  call    cs:__imp_RtlLengthSid
0x180011b75  nop     dword ptr [rax+rax+00h]
0x180011b7a  mov     [rbx+r12], rsi
0x180011b7e  mov     rcx, rsi; void *
0x180011b81  mov     dword ptr [rbx+r12+8], 0
0x180011b8a  mov     rdx, [rdi+8]; Src
0x180011b8e  mov     r8d, eax; Size
0x180011b91  mov     ebx, eax
0x180011b93  call    memcpy_0
0x180011b98  mov     rdi, [rsp+0F8h+var_90]
0x180011b9d  add     rsi, rbx
0x180011ba0  inc     r14d
0x180011ba3  inc     rbp
0x180011ba6  cmp     r14d, r15d
0x180011ba9  jb      short loc_180011B60
0x180011bab  xor     ebp, ebp
0x180011bad  test    r13d, r13d
0x180011bb0  jz      short loc_180011C05
0x180011bb2  mov     r14, [rsp+0F8h+var_70]
0x180011bba  mov     edi, ebp
0x180011bbc  add     rdi, rdi
0x180011bbf  mov     rcx, [r14+rdi*8]; Sid
0x180011bc3  call    cs:__imp_RtlLengthSid
0x180011bca  nop     dword ptr [rax+rax+00h]
0x180011bcf  mov     ecx, r15d
0x180011bd2  add     rcx, rcx
0x180011bd5  mov     r8d, eax; Size
0x180011bd8  mov     ebx, eax
0x180011bda  mov     [r12+rcx*8], rsi
0x180011bde  mov     dword ptr [r12+rcx*8+8], 0
0x180011be7  mov     rcx, rsi; void *
0x180011bea  mov     rdx, [r14+rdi*8]; Src
0x180011bee  call    memcpy_0
0x180011bf3  inc     r15d
0x180011bf6  add     rsi, rbx
0x180011bf9  inc     ebp
0x180011bfb  cmp     ebp, r13d
0x180011bfe  jb      short loc_180011BBA
0x180011c00  mov     rdi, [rsp+0F8h+var_90]
0x180011c05  mov     rcx, gs:60h
0x180011c0e  mov     r8, rdi; P
0x180011c11  xor     edx, edx; Flags
0x180011c13  mov     rcx, [rcx+30h]; HeapHandle
0x180011c17  call    cs:__imp_RtlFreeHeap
0x180011c1e  nop     dword ptr [rax+rax+00h]
0x180011c23  mov     rcx, [rsp+0F8h+Sid1]; Sid
0x180011c28  test    rcx, rcx
0x180011c2b  jz      short loc_180011C39
0x180011c2d  call    cs:__imp_RtlFreeSid
0x180011c34  nop     dword ptr [rax+rax+00h]
0x180011c39  mov     rax, [rsp+0F8h+var_60]
0x180011c41  mov     [rax], r12
0x180011c44  mov     rax, [rsp+0F8h+var_58]
0x180011c4c  mov     [rax], r15d
0x180011c4f  mov     al, 1
0x180011c51  mov     rcx, [rsp+0F8h+var_48]
0x180011c59  xor     rcx, rsp; StackCookie
0x180011c5c  call    __security_check_cookie
0x180011c61  mov     rbx, [rsp+0F8h+arg_10]
0x180011c69  add     rsp, 0C0h
0x180011c70  pop     r15
0x180011c72  pop     r14
0x180011c74  pop     r13
0x180011c76  pop     r12
0x180011c78  pop     rdi
0x180011c79  pop     rsi
0x180011c7a  pop     rbp
0x180011c7b  retn
0x180011c7d  mov     r9d, r11d
0x180011c80  sub     r9d, r10d
0x180011c83  cmp     edx, r10d
0x180011c86  jnb     loc_180011AB4
0x180011c8c  mov     ecx, edx
0x180011c8e  lea     eax, [r9+rdx]
0x180011c92  mov     eax, [rsi+rax*4+8]
0x180011c96  cmp     [r8+rcx*4+8], eax
0x180011c9b  jnz     loc_180011A79
0x180011ca1  inc     edx
0x180011ca3  jmp     short loc_180011C83
0x180011ca5  add     r12, [rsp+0F8h+var_78]
0x180011cad  mov     rdi, [rsp+0F8h+var_90]
0x180011cb2  mov     esi, [rsp+0F8h+var_94]
  ... truncated ...
```
