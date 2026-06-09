# CodeAuthzpInvertAndAddSids

- ea: `0x18000c0d0`
- end: `0x18000c646`
- name: `CodeAuthzpInvertAndAddSids`
- size: `1398`
- prototype: `__int64 __usercall@<rax>(HANDLE TokenHandle@<rcx>, PSID Sid1@<rdx>, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a78c`
- `0x18000b340`

## callees

- `0x18000c0d0`
- `0x180065042`
- `0x18006504e`
- `0x180065090`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18000c28a`
- `ntdll!RtlEqualSid` at `0x18000c345`
- `ntdll!RtlEqualSid` at `0x18000c360`
- `ntdll!RtlEqualSid` at `0x18000c374`
- `ntdll!RtlEqualSid` at `0x18000c28a`
- `ntdll!RtlEqualSid` at `0x18000c345`
- `ntdll!RtlEqualSid` at `0x18000c360`
- `ntdll!RtlEqualSid` at `0x18000c374`
- `ntdll!RtlLengthSid` at `0x18000c42e`
- `ntdll!RtlLengthSid` at `0x18000c47d`
- `ntdll!RtlLengthSid` at `0x18000c561`
- `ntdll!RtlLengthSid` at `0x18000c5f2`
- `ntdll!RtlLengthSid` at `0x18000c42e`
- `ntdll!RtlLengthSid` at `0x18000c47d`
- `ntdll!RtlLengthSid` at `0x18000c561`
- `ntdll!RtlLengthSid` at `0x18000c5f2`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000c1b0`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000c1b0`
- `ntdll!RtlFreeSid` at `0x18000c4db`
- `ntdll!RtlFreeSid` at `0x18000c63e`
- `ntdll!RtlFreeSid` at `0x18000c4db`
- `ntdll!RtlFreeSid` at `0x18000c63e`
- `ntdll!RtlFreeHeap` at `0x18000c4cb`
- `ntdll!RtlFreeHeap` at `0x18000c587`
- `ntdll!RtlFreeHeap` at `0x18000c61b`
- `ntdll!RtlFreeHeap` at `0x18000c4cb`
- `ntdll!RtlFreeHeap` at `0x18000c587`
- `ntdll!RtlFreeHeap` at `0x18000c61b`
- `ntdll!NtQueryInformationToken` at `0x18000c215`
- `ntdll!NtQueryInformationToken` at `0x18000c5ce`
- `ntdll!NtQueryInformationToken` at `0x18000c215`
- `ntdll!NtQueryInformationToken` at `0x18000c5ce`
- `ntdll!RtlAllocateHeap` at `0x18000c1df`
- `ntdll!RtlAllocateHeap` at `0x18000c3f6`
- `ntdll!RtlAllocateHeap` at `0x18000c5a1`
- `ntdll!RtlAllocateHeap` at `0x18000c1df`
- `ntdll!RtlAllocateHeap` at `0x18000c3f6`
- `ntdll!RtlAllocateHeap` at `0x18000c5a1`

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
0x18000c0d0  mov     r11, rsp
0x18000c0d3  mov     [r11+18h], rbx
0x18000c0d7  push    rbp
0x18000c0d8  push    rsi
0x18000c0d9  push    rdi
0x18000c0da  push    r12
0x18000c0dc  push    r13
0x18000c0de  push    r14
0x18000c0e0  push    r15
0x18000c0e2  sub     rsp, 0C0h
0x18000c0e9  mov     rax, cs:__security_cookie
0x18000c0f0  xor     rax, rsp
0x18000c0f3  mov     [rsp+0F8h+var_48], rax
0x18000c0fb  mov     eax, [rsp+0F8h+arg_20]
0x18000c102  mov     rbp, r9
0x18000c105  mov     r12, [rsp+0F8h+arg_28]
0x18000c10d  mov     r15d, r8d
0x18000c110  mov     [rsp+0F8h+var_80], eax
0x18000c114  mov     r14, rdx
0x18000c117  mov     rax, [rsp+0F8h+arg_30]
0x18000c11f  mov     rbx, rcx
0x18000c122  mov     [rsp+0F8h+var_58], rax
0x18000c12a  mov     rax, [rsp+0F8h+arg_38]
0x18000c132  mov     [rsp+0F8h+var_60], rax
0x18000c13a  mov     [rsp+0F8h+var_68], r9
0x18000c142  mov     [rsp+0F8h+var_70], r12
0x18000c14a  mov     dword ptr [r11-50h], 0
0x18000c152  mov     word ptr [r11-4Ch], 500h
0x18000c159  mov     [rsp+0F8h+Sid1], 0
0x18000c162  test    rdx, rdx
0x18000c165  jz      short loc_18000C1BE
0x18000c167  lea     rax, [rsp+0F8h+Sid1]
0x18000c16c  xor     r9d, r9d; SubAuthority1
0x18000c16f  mov     [rsp+0F8h+Sid], rax; Sid
0x18000c174  lea     rcx, [r11-50h]; IdentifierAuthority
0x18000c178  mov     [rsp+0F8h+SubAuthority7], 0; SubAuthority7
0x18000c180  mov     r8d, 0Ah; SubAuthority0
0x18000c186  mov     [rsp+0F8h+SubAuthority6], 0; SubAuthority6
0x18000c18e  mov     dl, 1; SubAuthorityCount
0x18000c190  mov     [rsp+0F8h+SubAuthority5], 0; SubAuthority5
0x18000c198  mov     [rsp+0F8h+SubAuthority4], 0; SubAuthority4
0x18000c1a0  mov     [rsp+0F8h+SubAuthority3], 0; SubAuthority3
0x18000c1a8  mov     [rsp+0F8h+SubAuthority2], 0; SubAuthority2
0x18000c1b0  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000c1b6  test    eax, eax
0x18000c1b8  js      loc_18000C621
0x18000c1be  xor     edi, edi
0x18000c1c0  mov     [rsp+0F8h+var_90], rdi
0x18000c1c5  test    rbx, rbx
0x18000c1c8  jz      short loc_18000C22E
0x18000c1ca  mov     rcx, gs:60h
0x18000c1d3  xor     edx, edx; Flags
0x18000c1d5  mov     r8d, 80h; Size
0x18000c1db  mov     rcx, [rcx+30h]; HeapHandle
0x18000c1df  call    cs:__imp_RtlAllocateHeap
0x18000c1e5  mov     [rsp+0F8h+var_90], rax
0x18000c1ea  mov     rdi, rax
0x18000c1ed  test    rax, rax
0x18000c1f0  jz      short loc_18000C22E
0x18000c1f2  lea     rax, [rsp+0F8h+ReturnLength]
0x18000c1f7  mov     [rsp+0F8h+ReturnLength], 0
0x18000c1ff  mov     r9d, 80h; TokenInformationLength
0x18000c205  mov     qword ptr [rsp+0F8h+SubAuthority2], rax; ReturnLength
0x18000c20a  mov     r8, rdi; TokenInformation
0x18000c20d  mov     edx, 2; TokenInformationClass
0x18000c212  mov     rcx, rbx; TokenHandle
0x18000c215  call    cs:__imp_NtQueryInformationToken
0x18000c21b  cmp     eax, 0C0000023h
0x18000c220  jz      loc_18000C575
0x18000c226  test    eax, eax
0x18000c228  js      loc_18000C609
0x18000c22e  test    rdi, rdi
0x18000c231  jz      loc_18000C621
0x18000c237  xor     esi, esi
0x18000c239  xor     r13d, r13d
0x18000c23c  mov     [rsp+0F8h+var_94], esi
0x18000c240  cmp     [rdi], esi
0x18000c242  jbe     loc_18000C3D8
0x18000c248  lea     rax, [rdi+8]
0x18000c24c  mov     [rsp+0F8h+var_78], rax
0x18000c254  mov     r12d, r13d
0x18000c257  test    rbp, rbp
0x18000c25a  jz      loc_18000C632
0x18000c260  test    r15d, r15d
0x18000c263  jz      loc_18000C632
0x18000c269  shl     r12, 4
0x18000c26d  mov     rbx, rbp
0x18000c270  mov     rbp, [rsp+0F8h+Sid1]
0x18000c275  mov     rsi, [r12+rdi+8]
0x18000c27a  test    r14, r14
0x18000c27d  jz      short loc_18000C296
0x18000c27f  test    rbp, rbp
0x18000c282  jz      short loc_18000C296
0x18000c284  mov     rdx, rsi; Sid2
0x18000c287  mov     rcx, rbp; Sid1
0x18000c28a  call    cs:__imp_RtlEqualSid
0x18000c290  test    al, al
0x18000c292  cmovnz  rsi, r14
0x18000c296  xor     edi, edi
0x18000c298  nop     dword ptr [rax+rax+00000000h]
0x18000c2a0  cmp     edi, r15d
0x18000c2a3  jnb     loc_18000C54C
0x18000c2a9  test    rbp, rbp
0x18000c2ac  jz      short loc_18000C2BD
0x18000c2ae  test    r14, r14
0x18000c2b1  jz      short loc_18000C2BD
0x18000c2b3  cmp     dword ptr [rbx+8], 0FFFFFFFFh
0x18000c2b7  jz      loc_18000C35A
0x18000c2bd  mov     edx, [rbx+8]
0x18000c2c0  mov     r8, [rbx]
0x18000c2c3  cmp     edx, 0FFFFFFFFh
0x18000c2c6  jz      short loc_18000C33F
0x18000c2c8  movzx   eax, byte ptr [rsi]
0x18000c2cb  cmp     [r8], al
0x18000c2ce  jnz     short loc_18000C34F
0x18000c2d0  movzx   eax, byte ptr [rsi+2]
0x18000c2d4  cmp     [r8+2], al
0x18000c2d8  jnz     short loc_18000C34F
0x18000c2da  movzx   eax, byte ptr [rsi+3]
0x18000c2de  cmp     [r8+3], al
0x18000c2e2  jnz     short loc_18000C34F
0x18000c2e4  movzx   eax, byte ptr [rsi+4]
0x18000c2e8  cmp     [r8+4], al
0x18000c2ec  jnz     short loc_18000C34F
0x18000c2ee  movzx   eax, byte ptr [rsi+5]
0x18000c2f2  cmp     [r8+5], al
0x18000c2f6  jnz     short loc_18000C34F
0x18000c2f8  movzx   eax, byte ptr [rsi+6]
0x18000c2fc  cmp     [r8+6], al
0x18000c300  jnz     short loc_18000C34F
0x18000c302  movzx   eax, byte ptr [rsi+7]
0x18000c306  cmp     [r8+7], al
0x18000c30a  jnz     short loc_18000C34F
0x18000c30c  movzx   r10d, byte ptr [r8+1]
0x18000c311  movzx   r11d, byte ptr [rsi+1]
0x18000c316  cmp     r11b, r10b
0x18000c319  jb      short loc_18000C34F
0x18000c31b  xor     r9d, r9d
0x18000c31e  cmp     r9d, edx
0x18000c321  jnb     loc_18000C524
0x18000c327  mov     eax, [rsi+r9*4+8]
0x18000c32c  lea     rcx, ds:8[r9*4]
0x18000c334  cmp     [r8+rcx], eax
0x18000c338  jnz     short loc_18000C34F
0x18000c33a  inc     r9d
0x18000c33d  jmp     short loc_18000C31E
0x18000c33f  mov     rdx, rsi; Sid2
0x18000c342  mov     rcx, r8; Sid1
0x18000c345  call    cs:__imp_RtlEqualSid
0x18000c34b  test    al, al
0x18000c34d  jnz     short loc_18000C37E
0x18000c34f  inc     edi
0x18000c351  add     rbx, 10h
0x18000c355  jmp     loc_18000C2A0
0x18000c35a  mov     rdx, [rbx]; Sid2
0x18000c35d  mov     rcx, rbp; Sid1
0x18000c360  call    cs:__imp_RtlEqualSid
0x18000c366  test    al, al
0x18000c368  jz      loc_18000C2BD
0x18000c36e  mov     rdx, rsi; Sid2
0x18000c371  mov     rcx, r14; Sid1
0x18000c374  call    cs:__imp_RtlEqualSid
0x18000c37a  test    al, al
0x18000c37c  jz      short loc_18000C34F
0x18000c37e  mov     rdi, [rsp+0F8h+var_90]
0x18000c383  lea     edx, [r13+1]
0x18000c387  mov     rcx, [rsp+0F8h+var_78]
0x18000c38f  mov     r8d, r13d
0x18000c392  not     r8d
0x18000c395  shl     rdx, 4
0x18000c399  add     rdx, 8
0x18000c39d  add     rcx, r12; void *
0x18000c3a0  add     r8d, [rdi]
0x18000c3a3  add     rdx, rdi; Src
0x18000c3a6  shl     r8, 4; Size
0x18000c3aa  call    memmove_0
0x18000c3af  dec     dword ptr [rdi]
0x18000c3b1  mov     esi, [rsp+0F8h+var_94]
0x18000c3b5  dec     r13d
0x18000c3b8  mov     rbp, [rsp+0F8h+var_68]
0x18000c3c0  lea     rax, [rdi+8]
0x18000c3c4  inc     r13d
0x18000c3c7  cmp     r13d, [rdi]
0x18000c3ca  jb      loc_18000C254
0x18000c3d0  mov     r12, [rsp+0F8h+var_70]
0x18000c3d8  test    r12, r12
0x18000c3db  jnz     loc_18000C5D9
0x18000c3e1  xor     r13d, r13d
0x18000c3e4  mov     rcx, gs:60h
0x18000c3ed  xor     edx, edx; Flags
0x18000c3ef  mov     r8d, esi; Size
0x18000c3f2  mov     rcx, [rcx+30h]; HeapHandle
0x18000c3f6  call    cs:__imp_RtlAllocateHeap
0x18000c3fc  mov     r12, rax
0x18000c3ff  test    rax, rax
0x18000c402  jz      loc_18000C609
0x18000c408  mov     r15d, [rdi]
0x18000c40b  xor     r14d, r14d
0x18000c40e  lea     esi, [r15+r13]
0x18000c412  shl     rsi, 4
0x18000c416  add     rsi, rax
0x18000c419  test    r15d, r15d
0x18000c41c  jz      short loc_18000C465
0x18000c41e  xor     ebp, ebp
0x18000c420  mov     rbx, rbp
0x18000c423  shl     rbx, 4
0x18000c427  add     rdi, rbx
0x18000c42a  mov     rcx, [rdi+8]; Sid
0x18000c42e  call    cs:__imp_RtlLengthSid
0x18000c434  mov     [rbx+r12], rsi
0x18000c438  mov     rcx, rsi; void *
0x18000c43b  mov     dword ptr [rbx+r12+8], 0
0x18000c444  mov     rdx, [rdi+8]; Src
0x18000c448  mov     r8d, eax; Size
0x18000c44b  mov     ebx, eax
0x18000c44d  call    memcpy_0
0x18000c452  mov     rdi, [rsp+0F8h+var_90]
0x18000c457  add     rsi, rbx
0x18000c45a  inc     r14d
0x18000c45d  inc     rbp
0x18000c460  cmp     r14d, r15d
0x18000c463  jb      short loc_18000C420
0x18000c465  xor     ebp, ebp
0x18000c467  test    r13d, r13d
0x18000c46a  jz      short loc_18000C4B9
0x18000c46c  mov     r14, [rsp+0F8h+var_70]
0x18000c474  mov     edi, ebp
0x18000c476  add     rdi, rdi
0x18000c479  mov     rcx, [r14+rdi*8]; Sid
0x18000c47d  call    cs:__imp_RtlLengthSid
0x18000c483  mov     ecx, r15d
0x18000c486  add     rcx, rcx
0x18000c489  mov     r8d, eax; Size
0x18000c48c  mov     ebx, eax
0x18000c48e  mov     [r12+rcx*8], rsi
0x18000c492  mov     dword ptr [r12+rcx*8+8], 0
0x18000c49b  mov     rcx, rsi; void *
0x18000c49e  mov     rdx, [r14+rdi*8]; Src
0x18000c4a2  call    memcpy_0
0x18000c4a7  inc     r15d
0x18000c4aa  add     rsi, rbx
0x18000c4ad  inc     ebp
0x18000c4af  cmp     ebp, r13d
0x18000c4b2  jb      short loc_18000C474
0x18000c4b4  mov     rdi, [rsp+0F8h+var_90]
0x18000c4b9  mov     rcx, gs:60h
0x18000c4c2  mov     r8, rdi; P
0x18000c4c5  xor     edx, edx; Flags
0x18000c4c7  mov     rcx, [rcx+30h]; HeapHandle
0x18000c4cb  call    cs:__imp_RtlFreeHeap
0x18000c4d1  mov     rcx, [rsp+0F8h+Sid1]; Sid
0x18000c4d6  test    rcx, rcx
0x18000c4d9  jz      short loc_18000C4E1
0x18000c4db  call    cs:__imp_RtlFreeSid
0x18000c4e1  mov     rax, [rsp+0F8h+var_60]
0x18000c4e9  mov     [rax], r12
0x18000c4ec  mov     rax, [rsp+0F8h+var_58]
0x18000c4f4  mov     [rax], r15d
0x18000c4f7  mov     al, 1
0x18000c4f9  mov     rcx, [rsp+0F8h+var_48]
0x18000c501  xor     rcx, rsp; StackCookie
0x18000c504  call    __security_check_cookie
0x18000c509  mov     rbx, [rsp+0F8h+arg_10]
0x18000c511  add     rsp, 0C0h
0x18000c518  pop     r15
0x18000c51a  pop     r14
0x18000c51c  pop     r13
0x18000c51e  pop     r12
0x18000c520  pop     rdi
0x18000c521  pop     rsi
0x18000c522  pop     rbp
0x18000c523  retn
0x18000c524  mov     r9d, r11d
0x18000c527  sub     r9d, r10d
0x18000c52a  cmp     edx, r10d
0x18000c52d  jnb     loc_18000C37E
0x18000c533  mov     ecx, edx
0x18000c535  lea     eax, [r9+rdx]
0x18000c539  mov     eax, [rsi+rax*4+8]
0x18000c53d  cmp     [r8+rcx*4+8], eax
0x18000c542  jnz     loc_18000C34F
0x18000c548  inc     edx
0x18000c54a  jmp     short loc_18000C52A
0x18000c54c  add     r12, [rsp+0F8h+var_78]
0x18000c554  mov     rdi, [rsp+0F8h+var_90]
0x18000c559  mov     esi, [rsp+0F8h+var_94]
0x18000c55d  mov     rcx, [r12]; Sid
0x18000c561  call    cs:__imp_RtlLengthSid
0x18000c567  add     esi, 10h
0x18000c56a  add     esi, eax
0x18000c56c  mov     [rsp+0F8h+var_94], esi
0x18000c570  jmp     loc_18000C3B8
0x18000c575  mov     rcx, gs:60h
0x18000c57e  mov     r8, rdi; P
0x18000c581  xor     edx, edx; Flags
0x18000c583  mov     rcx, [rcx+30h]; HeapHandle
0x18000c587  call    cs:__imp_RtlFreeHeap
0x18000c58d  mov     rcx, gs:60h
0x18000c596  xor     edx, edx; Flags
0x18000c598  mov     r8d, [rsp+0F8h+ReturnLength]; Size
  ... truncated ...
```
