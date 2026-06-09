# CodeAuthzpExpandWildcardList

- ea: `0x18000c650`
- end: `0x18000cb0a`
- name: `CodeAuthzpExpandWildcardList`
- size: `1210`
- prototype: `__int64 __usercall@<rax>(HANDLE TokenHandle@<rcx>, PSID Sid1@<rdx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a78c`
- `0x18000b340`

## callees

- `0x18000c650`
- `0x180065042`
- `0x18006504e`
- `0x180065090`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18000c7f6`
- `ntdll!RtlEqualSid` at `0x18000c8a7`
- `ntdll!RtlEqualSid` at `0x18000c8c2`
- `ntdll!RtlEqualSid` at `0x18000c8d6`
- `ntdll!RtlEqualSid` at `0x18000c7f6`
- `ntdll!RtlEqualSid` at `0x18000c8a7`
- `ntdll!RtlEqualSid` at `0x18000c8c2`
- `ntdll!RtlEqualSid` at `0x18000c8d6`
- `ntdll!RtlLengthSid` at `0x18000c8eb`
- `ntdll!RtlLengthSid` at `0x18000c96d`
- `ntdll!RtlLengthSid` at `0x18000c8eb`
- `ntdll!RtlLengthSid` at `0x18000c96d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000c70e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000c70e`
- `ntdll!RtlFreeSid` at `0x18000c9c5`
- `ntdll!RtlFreeSid` at `0x18000cb02`
- `ntdll!RtlFreeSid` at `0x18000c9c5`
- `ntdll!RtlFreeSid` at `0x18000cb02`
- `ntdll!RtlFreeHeap` at `0x18000c9b5`
- `ntdll!RtlFreeHeap` at `0x18000ca7b`
- `ntdll!RtlFreeHeap` at `0x18000cadf`
- `ntdll!RtlFreeHeap` at `0x18000c9b5`
- `ntdll!RtlFreeHeap` at `0x18000ca7b`
- `ntdll!RtlFreeHeap` at `0x18000cadf`
- `ntdll!NtQueryInformationToken` at `0x18000c773`
- `ntdll!NtQueryInformationToken` at `0x18000cac2`
- `ntdll!NtQueryInformationToken` at `0x18000c773`
- `ntdll!NtQueryInformationToken` at `0x18000cac2`
- `ntdll!RtlAllocateHeap` at `0x18000c73d`
- `ntdll!RtlAllocateHeap` at `0x18000c92d`
- `ntdll!RtlAllocateHeap` at `0x18000ca95`
- `ntdll!RtlAllocateHeap` at `0x18000c73d`
- `ntdll!RtlAllocateHeap` at `0x18000c92d`
- `ntdll!RtlAllocateHeap` at `0x18000ca95`

## pseudocode

```c
char __fastcall CodeAuthzpExpandWildcardList(
        HANDLE TokenHandle,
        unsigned __int8 *Sid1,
        unsigned int a3,
        __int64 a4,
        unsigned int *a5,
        _QWORD *a6)
{
  __int64 v6; // rsi
  unsigned int *v10; // rdi
  NTSTATUS v11; // eax
  ULONG v12; // ebx
  unsigned int v13; // r13d
  _DWORD *v14; // rax
  PSID v15; // rbp
  __int64 v16; // rbx
  __int64 v17; // r12
  unsigned __int8 *v18; // rsi
  unsigned int i; // edi
  unsigned int v20; // edx
  _BYTE *v21; // r8
  unsigned int v22; // r10d
  int v23; // r11d
  __int64 j; // r9
  ULONG v25; // eax
  char *v26; // rax
  char *v27; // rbp
  unsigned int v28; // r14d
  unsigned int v29; // r12d
  char *v30; // rsi
  __int64 v31; // r15
  __int64 v32; // rbx
  PSID *v33; // rdi
  ULONG v34; // eax
  __int64 v35; // rbx
  _DWORD *v37; // r12
  ULONG ReturnLength; // [rsp+60h] [rbp-88h] BYREF
  ULONG v39; // [rsp+64h] [rbp-84h]
  unsigned int *Heap; // [rsp+68h] [rbp-80h]
  PSID Sid1a; // [rsp+70h] [rbp-78h] BYREF
  _DWORD *v42; // [rsp+78h] [rbp-70h]
  __int64 v43; // [rsp+80h] [rbp-68h]
  _QWORD *v44; // [rsp+88h] [rbp-60h]
  unsigned int *v45; // [rsp+90h] [rbp-58h]
  struct _SID_IDENTIFIER_AUTHORITY v46; // [rsp+98h] [rbp-50h] BYREF

  v6 = a4;
  v45 = a5;
  v44 = a6;
  v43 = a4;
  *(_DWORD *)v46.Value = 0;
  *(_WORD *)&v46.Value[4] = 1280;
  Sid1a = 0;
  if ( Sid1 && RtlAllocateAndInitializeSid(&v46, 1u, 0xAu, 0, 0, 0, 0, 0, 0, 0, &Sid1a) < 0 )
    goto LABEL_55;
  v10 = 0;
  Heap = 0;
  if ( TokenHandle )
  {
    Heap = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x80u);
    v10 = Heap;
    if ( Heap )
    {
      ReturnLength = 0;
      v11 = NtQueryInformationToken(TokenHandle, TokenGroups, Heap, 0x80u, &ReturnLength);
      if ( v11 == -1073741789 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
        Heap = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ReturnLength);
        v10 = Heap;
        if ( !Heap )
          goto LABEL_54;
        v11 = NtQueryInformationToken(TokenHandle, TokenGroups, Heap, ReturnLength, &ReturnLength);
      }
      if ( v11 >= 0 )
        goto LABEL_7;
LABEL_54:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
      goto LABEL_55;
    }
  }
LABEL_7:
  if ( v10 )
  {
    v12 = 0;
    v13 = 0;
    v39 = 0;
    if ( *v10 )
    {
      v14 = v10 + 2;
      v42 = v10 + 2;
      do
      {
        if ( v6 && a3 )
        {
          v15 = Sid1a;
          v16 = v6;
          v17 = 4LL * v13;
          v18 = *(unsigned __int8 **)&v10[v17 + 2];
          if ( Sid1 && Sid1a && RtlEqualSid(Sid1a, *(PSID *)&v10[v17 + 2]) )
            v18 = Sid1;
          for ( i = 0; i < a3; ++i )
          {
            if ( v15 && Sid1 && *(_DWORD *)(v16 + 8) == -1 && RtlEqualSid(v15, *(PSID *)v16) )
            {
              if ( RtlEqualSid(Sid1, v18) )
                goto LABEL_38;
            }
            else
            {
              v20 = *(_DWORD *)(v16 + 8);
              v21 = *(_BYTE **)v16;
              if ( v20 == -1 )
              {
                if ( RtlEqualSid(*(PSID *)v16, v18) )
                  goto LABEL_38;
              }
              else if ( *v21 == *v18
                     && v21[2] == v18[2]
                     && v21[3] == v18[3]
                     && v21[4] == v18[4]
                     && v21[5] == v18[5]
                     && v21[6] == v18[6]
                     && v21[7] == v18[7] )
              {
                v22 = (unsigned __int8)v21[1];
                v23 = v18[1];
                if ( (unsigned __int8)v23 >= (unsigned __int8)v22 )
                {
                  for ( j = 0; (unsigned int)j < v20; j = (unsigned int)(j + 1) )
                  {
                    if ( *(_DWORD *)&v21[4 * j + 8] != *(_DWORD *)&v18[4 * j + 8] )
                      goto LABEL_35;
                  }
                  while ( v20 < v22 )
                  {
                    if ( *(_DWORD *)&v21[4 * v20 + 8] != *(_DWORD *)&v18[4 * (v23 - v22) + 8 + 4 * v20] )
                      goto LABEL_35;
                    ++v20;
                  }
LABEL_38:
                  v25 = RtlLengthSid(*(PSID *)&v42[v17]);
                  v10 = Heap;
                  v12 = v25 + v39 + 16;
                  v39 = v12;
                  goto LABEL_39;
                }
              }
            }
LABEL_35:
            v16 += 16;
          }
          v37 = &v42[v17];
          v10 = Heap;
          v12 = v39;
        }
        else
        {
          v37 = &v14[4 * v13];
        }
        memmove_0(v37, &v10[4 * v13 + 6], 16LL * (*v10 + ~v13));
        --*v10;
        --v13;
LABEL_39:
        v6 = v43;
        v14 = v10 + 2;
        ++v13;
      }
      while ( v13 < *v10 );
    }
    v26 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
    v27 = v26;
    if ( v26 )
    {
      v28 = *v10;
      v29 = 0;
      v30 = &v26[16 * *v10];
      if ( *v10 )
      {
        v31 = 0;
        do
        {
          v32 = 16 * v31;
          v33 = (PSID *)&v10[4 * v31];
          v34 = RtlLengthSid(v33[1]);
          *(_QWORD *)&v27[v32] = v30;
          *(_DWORD *)&v27[v32 + 8] = 0;
          v35 = v34;
          memcpy_0(v30, v33[1], v34);
          v10 = Heap;
          v30 += v35;
          ++v29;
          ++v31;
        }
        while ( v29 < v28 );
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
      if ( Sid1a )
        RtlFreeSid(Sid1a);
      *v44 = v27;
      *v45 = v28;
      return 1;
    }
    goto LABEL_54;
  }
LABEL_55:
  if ( Sid1a )
    RtlFreeSid(Sid1a);
  return 0;
}

```

## disassembly

```asm
0x18000c650  mov     r11, rsp
0x18000c653  push    rbx
0x18000c654  push    rbp
0x18000c655  push    rsi
0x18000c656  push    rdi
0x18000c657  push    r12
0x18000c659  push    r14
0x18000c65b  push    r15
0x18000c65d  sub     rsp, 0B0h
0x18000c664  mov     rax, cs:__security_cookie
0x18000c66b  xor     rax, rsp
0x18000c66e  mov     [rsp+0E8h+var_48], rax
0x18000c676  mov     rax, [rsp+0E8h+arg_20]
0x18000c67e  mov     rsi, r9
0x18000c681  mov     [rsp+0E8h+var_58], rax
0x18000c689  mov     r15d, r8d
0x18000c68c  mov     rax, [rsp+0E8h+arg_28]
0x18000c694  mov     r14, rdx
0x18000c697  mov     [rsp+0E8h+var_60], rax
0x18000c69f  mov     rbx, rcx
0x18000c6a2  mov     [rsp+0E8h+var_68], r9
0x18000c6aa  mov     dword ptr [r11-50h], 0
0x18000c6b2  mov     word ptr [r11-4Ch], 500h
0x18000c6b9  mov     qword ptr [r11-78h], 0
0x18000c6c1  test    rdx, rdx
0x18000c6c4  jz      short loc_18000C71C
0x18000c6c6  lea     rax, [r11-78h]
0x18000c6ca  xor     r9d, r9d; SubAuthority1
0x18000c6cd  mov     [rsp+0E8h+Sid], rax; Sid
0x18000c6d2  lea     rcx, [r11-50h]; IdentifierAuthority
0x18000c6d6  mov     [rsp+0E8h+SubAuthority7], 0; SubAuthority7
0x18000c6de  mov     r8d, 0Ah; SubAuthority0
0x18000c6e4  mov     [rsp+0E8h+SubAuthority6], 0; SubAuthority6
0x18000c6ec  mov     dl, 1; SubAuthorityCount
0x18000c6ee  mov     [rsp+0E8h+SubAuthority5], 0; SubAuthority5
0x18000c6f6  mov     [rsp+0E8h+SubAuthority4], 0; SubAuthority4
0x18000c6fe  mov     [rsp+0E8h+SubAuthority3], 0; SubAuthority3
0x18000c706  mov     [rsp+0E8h+SubAuthority2], 0; SubAuthority2
0x18000c70e  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000c714  test    eax, eax
0x18000c716  js      loc_18000CAE5
0x18000c71c  xor     edi, edi
0x18000c71e  mov     [rsp+0E8h+var_80], rdi
0x18000c723  test    rbx, rbx
0x18000c726  jz      short loc_18000C78C
0x18000c728  mov     rcx, gs:60h
0x18000c731  xor     edx, edx; Flags
0x18000c733  mov     r8d, 80h; Size
0x18000c739  mov     rcx, [rcx+30h]; HeapHandle
0x18000c73d  call    cs:__imp_RtlAllocateHeap
0x18000c743  mov     [rsp+0E8h+var_80], rax
0x18000c748  mov     rdi, rax
0x18000c74b  test    rax, rax
0x18000c74e  jz      short loc_18000C78C
0x18000c750  lea     rax, [rsp+0E8h+ReturnLength]
0x18000c755  mov     [rsp+0E8h+ReturnLength], 0
0x18000c75d  mov     r9d, 80h; TokenInformationLength
0x18000c763  mov     qword ptr [rsp+0E8h+SubAuthority2], rax; ReturnLength
0x18000c768  mov     r8, rdi; TokenInformation
0x18000c76b  mov     edx, 2; TokenInformationClass
0x18000c770  mov     rcx, rbx; TokenHandle
0x18000c773  call    cs:__imp_NtQueryInformationToken
0x18000c779  cmp     eax, 0C0000023h
0x18000c77e  jz      loc_18000CA69
0x18000c784  test    eax, eax
0x18000c786  js      loc_18000CACD
0x18000c78c  test    rdi, rdi
0x18000c78f  jz      loc_18000CAE5
0x18000c795  xor     ebx, ebx
0x18000c797  mov     [rsp+0E8h+arg_10], r13
0x18000c79f  xor     r13d, r13d
0x18000c7a2  mov     [rsp+0E8h+var_84], ebx
0x18000c7a6  cmp     [rdi], ebx
0x18000c7a8  jbe     loc_18000C91B
0x18000c7ae  lea     rax, [rdi+8]
0x18000c7b2  mov     [rsp+0E8h+var_70], rax
0x18000c7b7  nop     word ptr [rax+rax+00000000h]
0x18000c7c0  mov     r12d, r13d
0x18000c7c3  test    rsi, rsi
0x18000c7c6  jz      loc_18000CAF6
0x18000c7cc  test    r15d, r15d
0x18000c7cf  jz      loc_18000CAF6
0x18000c7d5  mov     rbp, [rsp+0E8h+Sid1]
0x18000c7da  mov     rbx, rsi
0x18000c7dd  shl     r12, 4
0x18000c7e1  mov     rsi, [r12+rdi+8]
0x18000c7e6  test    r14, r14
0x18000c7e9  jz      short loc_18000C802
0x18000c7eb  test    rbp, rbp
0x18000c7ee  jz      short loc_18000C802
0x18000c7f0  mov     rdx, rsi; Sid2
0x18000c7f3  mov     rcx, rbp; Sid1
0x18000c7f6  call    cs:__imp_RtlEqualSid
0x18000c7fc  test    al, al
0x18000c7fe  cmovnz  rsi, r14
0x18000c802  xor     edi, edi
0x18000c804  cmp     edi, r15d
0x18000c807  jnb     loc_18000CA2D
0x18000c80d  test    rbp, rbp
0x18000c810  jz      short loc_18000C821
0x18000c812  test    r14, r14
0x18000c815  jz      short loc_18000C821
0x18000c817  cmp     dword ptr [rbx+8], 0FFFFFFFFh
0x18000c81b  jz      loc_18000C8BC
0x18000c821  mov     edx, [rbx+8]
0x18000c824  mov     r8, [rbx]
0x18000c827  cmp     edx, 0FFFFFFFFh
0x18000c82a  jz      short loc_18000C8A1
0x18000c82c  movzx   eax, byte ptr [rsi]
0x18000c82f  cmp     [r8], al
0x18000c832  jnz     short loc_18000C8B1
0x18000c834  movzx   eax, byte ptr [rsi+2]
0x18000c838  cmp     [r8+2], al
0x18000c83c  jnz     short loc_18000C8B1
0x18000c83e  movzx   eax, byte ptr [rsi+3]
0x18000c842  cmp     [r8+3], al
0x18000c846  jnz     short loc_18000C8B1
0x18000c848  movzx   eax, byte ptr [rsi+4]
0x18000c84c  cmp     [r8+4], al
0x18000c850  jnz     short loc_18000C8B1
0x18000c852  movzx   eax, byte ptr [rsi+5]
0x18000c856  cmp     [r8+5], al
0x18000c85a  jnz     short loc_18000C8B1
0x18000c85c  movzx   eax, byte ptr [rsi+6]
0x18000c860  cmp     [r8+6], al
0x18000c864  jnz     short loc_18000C8B1
0x18000c866  movzx   eax, byte ptr [rsi+7]
0x18000c86a  cmp     [r8+7], al
0x18000c86e  jnz     short loc_18000C8B1
0x18000c870  movzx   r10d, byte ptr [r8+1]
0x18000c875  movzx   r11d, byte ptr [rsi+1]
0x18000c87a  cmp     r11b, r10b
0x18000c87d  jb      short loc_18000C8B1
0x18000c87f  xor     r9d, r9d
0x18000c882  cmp     r9d, edx
0x18000c885  jnb     loc_18000CA05
0x18000c88b  lea     rcx, ds:8[r9*4]
0x18000c893  mov     eax, [rcx+rsi]
0x18000c896  cmp     [rcx+r8], eax
0x18000c89a  jnz     short loc_18000C8B1
0x18000c89c  inc     r9d
0x18000c89f  jmp     short loc_18000C882
0x18000c8a1  mov     rdx, rsi; Sid2
0x18000c8a4  mov     rcx, r8; Sid1
0x18000c8a7  call    cs:__imp_RtlEqualSid
0x18000c8ad  test    al, al
0x18000c8af  jnz     short loc_18000C8E0
0x18000c8b1  inc     edi
0x18000c8b3  add     rbx, 10h
0x18000c8b7  jmp     loc_18000C804
0x18000c8bc  mov     rdx, [rbx]; Sid2
0x18000c8bf  mov     rcx, rbp; Sid1
0x18000c8c2  call    cs:__imp_RtlEqualSid
0x18000c8c8  test    al, al
0x18000c8ca  jz      loc_18000C821
0x18000c8d0  mov     rdx, rsi; Sid2
0x18000c8d3  mov     rcx, r14; Sid1
0x18000c8d6  call    cs:__imp_RtlEqualSid
0x18000c8dc  test    al, al
0x18000c8de  jz      short loc_18000C8B1
0x18000c8e0  mov     rcx, [rsp+0E8h+var_70]
0x18000c8e5  add     rcx, r12
0x18000c8e8  mov     rcx, [rcx]; Sid
0x18000c8eb  call    cs:__imp_RtlLengthSid
0x18000c8f1  mov     ebx, [rsp+0E8h+var_84]
0x18000c8f5  mov     rdi, [rsp+0E8h+var_80]
0x18000c8fa  add     ebx, 10h
0x18000c8fd  add     ebx, eax
0x18000c8ff  mov     [rsp+0E8h+var_84], ebx
0x18000c903  mov     rsi, [rsp+0E8h+var_68]
0x18000c90b  lea     rax, [rdi+8]
0x18000c90f  inc     r13d
0x18000c912  cmp     r13d, [rdi]
0x18000c915  jb      loc_18000C7C0
0x18000c91b  mov     rcx, gs:60h
0x18000c924  xor     edx, edx; Flags
0x18000c926  mov     r8d, ebx; Size
0x18000c929  mov     rcx, [rcx+30h]; HeapHandle
0x18000c92d  call    cs:__imp_RtlAllocateHeap
0x18000c933  mov     r13, [rsp+0E8h+arg_10]
0x18000c93b  mov     rbp, rax
0x18000c93e  test    rax, rax
0x18000c941  jz      loc_18000CACD
0x18000c947  mov     r14d, [rdi]
0x18000c94a  xor     r12d, r12d
0x18000c94d  mov     esi, r14d
0x18000c950  shl     rsi, 4
0x18000c954  add     rsi, rax
0x18000c957  test    r14d, r14d
0x18000c95a  jz      short loc_18000C9A3
0x18000c95c  xor     r15d, r15d
0x18000c95f  mov     rbx, r15
0x18000c962  shl     rbx, 4
0x18000c966  add     rdi, rbx
0x18000c969  mov     rcx, [rdi+8]; Sid
0x18000c96d  call    cs:__imp_RtlLengthSid
0x18000c973  mov     [rbx+rbp], rsi
0x18000c977  mov     rcx, rsi; void *
0x18000c97a  mov     dword ptr [rbx+rbp+8], 0
0x18000c982  mov     rdx, [rdi+8]; Src
0x18000c986  mov     r8d, eax; Size
0x18000c989  mov     ebx, eax
0x18000c98b  call    memcpy_0
0x18000c990  mov     rdi, [rsp+0E8h+var_80]
0x18000c995  add     rsi, rbx
0x18000c998  inc     r12d
0x18000c99b  inc     r15
0x18000c99e  cmp     r12d, r14d
0x18000c9a1  jb      short loc_18000C95F
0x18000c9a3  mov     rcx, gs:60h
0x18000c9ac  mov     r8, rdi; P
0x18000c9af  xor     edx, edx; Flags
0x18000c9b1  mov     rcx, [rcx+30h]; HeapHandle
0x18000c9b5  call    cs:__imp_RtlFreeHeap
0x18000c9bb  mov     rcx, [rsp+0E8h+Sid1]; Sid
0x18000c9c0  test    rcx, rcx
0x18000c9c3  jz      short loc_18000C9CB
0x18000c9c5  call    cs:__imp_RtlFreeSid
0x18000c9cb  mov     rax, [rsp+0E8h+var_60]
0x18000c9d3  mov     [rax], rbp
0x18000c9d6  mov     rax, [rsp+0E8h+var_58]
0x18000c9de  mov     [rax], r14d
0x18000c9e1  mov     al, 1
0x18000c9e3  mov     rcx, [rsp+0E8h+var_48]
0x18000c9eb  xor     rcx, rsp; StackCookie
0x18000c9ee  call    __security_check_cookie
0x18000c9f3  add     rsp, 0B0h
0x18000c9fa  pop     r15
0x18000c9fc  pop     r14
0x18000c9fe  pop     r12
0x18000ca00  pop     rdi
0x18000ca01  pop     rsi
0x18000ca02  pop     rbp
0x18000ca03  pop     rbx
0x18000ca04  retn
0x18000ca05  mov     r9d, r11d
0x18000ca08  sub     r9d, r10d
0x18000ca0b  cmp     edx, r10d
0x18000ca0e  jnb     loc_18000C8E0
0x18000ca14  mov     ecx, edx
0x18000ca16  lea     eax, [r9+rdx]
0x18000ca1a  mov     eax, [rsi+rax*4+8]
0x18000ca1e  cmp     [r8+rcx*4+8], eax
0x18000ca23  jnz     loc_18000C8B1
0x18000ca29  inc     edx
0x18000ca2b  jmp     short loc_18000CA0B
0x18000ca2d  add     r12, [rsp+0E8h+var_70]
0x18000ca32  mov     rdi, [rsp+0E8h+var_80]
0x18000ca37  mov     ebx, [rsp+0E8h+var_84]
0x18000ca3b  mov     r8d, r13d
0x18000ca3e  lea     edx, [r13+1]
0x18000ca42  not     r8d
0x18000ca45  shl     rdx, 4
0x18000ca49  add     r8d, [rdi]
0x18000ca4c  add     rdx, 8
0x18000ca50  shl     r8, 4; Size
0x18000ca54  add     rdx, rdi; Src
0x18000ca57  mov     rcx, r12; void *
0x18000ca5a  call    memmove_0
0x18000ca5f  dec     dword ptr [rdi]
0x18000ca61  dec     r13d
0x18000ca64  jmp     loc_18000C903
0x18000ca69  mov     rcx, gs:60h
0x18000ca72  mov     r8, rdi; P
0x18000ca75  xor     edx, edx; Flags
0x18000ca77  mov     rcx, [rcx+30h]; HeapHandle
0x18000ca7b  call    cs:__imp_RtlFreeHeap
0x18000ca81  mov     rcx, gs:60h
0x18000ca8a  xor     edx, edx; Flags
0x18000ca8c  mov     r8d, [rsp+0E8h+ReturnLength]; Size
0x18000ca91  mov     rcx, [rcx+30h]; HeapHandle
0x18000ca95  call    cs:__imp_RtlAllocateHeap
0x18000ca9b  mov     [rsp+0E8h+var_80], rax
0x18000caa0  mov     rdi, rax
0x18000caa3  test    rax, rax
0x18000caa6  jz      short loc_18000CACD
0x18000caa8  mov     r9d, [rsp+0E8h+ReturnLength]; TokenInformationLength
0x18000caad  lea     rax, [rsp+0E8h+ReturnLength]
0x18000cab2  mov     r8, rdi; TokenInformation
0x18000cab5  mov     qword ptr [rsp+0E8h+SubAuthority2], rax; ReturnLength
0x18000caba  mov     edx, 2; TokenInformationClass
0x18000cabf  mov     rcx, rbx; TokenHandle
0x18000cac2  call    cs:__imp_NtQueryInformationToken
0x18000cac8  jmp     loc_18000C784
0x18000cacd  mov     rcx, gs:60h
0x18000cad6  mov     r8, rdi; P
0x18000cad9  xor     edx, edx; Flags
0x18000cadb  mov     rcx, [rcx+30h]; HeapHandle
0x18000cadf  call    cs:__imp_RtlFreeHeap
0x18000cae5  mov     rcx, [rsp+0E8h+Sid1]; Sid
0x18000caea  test    rcx, rcx
0x18000caed  jnz     short loc_18000CB02
0x18000caef  xor     al, al
0x18000caf1  jmp     loc_18000C9E3
0x18000caf6  shl     r12, 4
0x18000cafa  add     r12, rax
0x18000cafd  jmp     loc_18000CA3B
0x18000cb02  call    cs:__imp_RtlFreeSid
0x18000cb08  jmp     short loc_18000CAEF
```
