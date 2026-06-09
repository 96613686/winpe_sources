# CodeAuthzpExpandWildcardList

- ea: `0x180011dd0`
- end: `0x1800122f9`
- name: `CodeAuthzpExpandWildcardList`
- size: `1321`
- prototype: `__int64 __usercall@<rax>(HANDLE TokenHandle@<rcx>, PSID Sid1@<rdx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000fc88`
- `0x180010910`

## callees

- `0x180011dd0`
- `0x180072042`
- `0x18007204e`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180011f86`
- `ntdll!RtlEqualSid` at `0x180012047`
- `ntdll!RtlEqualSid` at `0x180012068`
- `ntdll!RtlEqualSid` at `0x180012082`
- `ntdll!RtlEqualSid` at `0x180011f86`
- `ntdll!RtlEqualSid` at `0x180012047`
- `ntdll!RtlEqualSid` at `0x180012068`
- `ntdll!RtlEqualSid` at `0x180012082`
- `ntdll!RtlLengthSid` at `0x18001209d`
- `ntdll!RtlLengthSid` at `0x18001212b`
- `ntdll!RtlLengthSid` at `0x18001209d`
- `ntdll!RtlLengthSid` at `0x18001212b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180011e8e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180011e8e`
- `ntdll!RtlFreeSid` at `0x18001218f`
- `ntdll!RtlFreeSid` at `0x1800122eb`
- `ntdll!RtlFreeSid` at `0x18001218f`
- `ntdll!RtlFreeSid` at `0x1800122eb`
- `ntdll!RtlFreeHeap` at `0x180012179`
- `ntdll!RtlFreeHeap` at `0x18001224c`
- `ntdll!RtlFreeHeap` at `0x1800122c2`
- `ntdll!RtlFreeHeap` at `0x180012179`
- `ntdll!RtlFreeHeap` at `0x18001224c`
- `ntdll!RtlFreeHeap` at `0x1800122c2`
- `ntdll!NtQueryInformationToken` at `0x180011eff`
- `ntdll!NtQueryInformationToken` at `0x18001229f`
- `ntdll!NtQueryInformationToken` at `0x180011eff`
- `ntdll!NtQueryInformationToken` at `0x18001229f`
- `ntdll!RtlAllocateHeap` at `0x180011ec3`
- `ntdll!RtlAllocateHeap` at `0x1800120e5`
- `ntdll!RtlAllocateHeap` at `0x18001226c`
- `ntdll!RtlAllocateHeap` at `0x180011ec3`
- `ntdll!RtlAllocateHeap` at `0x1800120e5`
- `ntdll!RtlAllocateHeap` at `0x18001226c`

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
0x180011dd0  mov     r11, rsp
0x180011dd3  push    rbx
0x180011dd4  push    rbp
0x180011dd5  push    rsi
0x180011dd6  push    rdi
0x180011dd7  push    r12
0x180011dd9  push    r14
0x180011ddb  push    r15
0x180011ddd  sub     rsp, 0B0h
0x180011de4  mov     rax, cs:__security_cookie
0x180011deb  xor     rax, rsp
0x180011dee  mov     [rsp+0E8h+var_48], rax
0x180011df6  mov     rax, [rsp+0E8h+arg_20]
0x180011dfe  mov     rsi, r9
0x180011e01  mov     [rsp+0E8h+var_58], rax
0x180011e09  mov     r15d, r8d
0x180011e0c  mov     rax, [rsp+0E8h+arg_28]
0x180011e14  mov     r14, rdx
0x180011e17  mov     [rsp+0E8h+var_60], rax
0x180011e1f  mov     rbx, rcx
0x180011e22  mov     [rsp+0E8h+var_68], r9
0x180011e2a  mov     dword ptr [r11-50h], 0
0x180011e32  mov     word ptr [r11-4Ch], 500h
0x180011e39  mov     qword ptr [r11-78h], 0
0x180011e41  test    rdx, rdx
0x180011e44  jz      short loc_180011EA2
0x180011e46  lea     rax, [r11-78h]
0x180011e4a  xor     r9d, r9d; SubAuthority1
0x180011e4d  mov     [rsp+0E8h+Sid], rax; Sid
0x180011e52  lea     rcx, [r11-50h]; IdentifierAuthority
0x180011e56  mov     [rsp+0E8h+SubAuthority7], 0; SubAuthority7
0x180011e5e  mov     r8d, 0Ah; SubAuthority0
0x180011e64  mov     [rsp+0E8h+SubAuthority6], 0; SubAuthority6
0x180011e6c  mov     dl, 1; SubAuthorityCount
0x180011e6e  mov     [rsp+0E8h+SubAuthority5], 0; SubAuthority5
0x180011e76  mov     [rsp+0E8h+SubAuthority4], 0; SubAuthority4
0x180011e7e  mov     [rsp+0E8h+SubAuthority3], 0; SubAuthority3
0x180011e86  mov     [rsp+0E8h+SubAuthority2], 0; SubAuthority2
0x180011e8e  call    cs:__imp_RtlAllocateAndInitializeSid
0x180011e95  nop     dword ptr [rax+rax+00h]
0x180011e9a  test    eax, eax
0x180011e9c  js      loc_1800122CE
0x180011ea2  xor     edi, edi
0x180011ea4  mov     [rsp+0E8h+var_80], rdi
0x180011ea9  test    rbx, rbx
0x180011eac  jz      short loc_180011F1E
0x180011eae  mov     rcx, gs:60h
0x180011eb7  xor     edx, edx; Flags
0x180011eb9  mov     r8d, 80h; Size
0x180011ebf  mov     rcx, [rcx+30h]; HeapHandle
0x180011ec3  call    cs:__imp_RtlAllocateHeap
0x180011eca  nop     dword ptr [rax+rax+00h]
0x180011ecf  mov     [rsp+0E8h+var_80], rax
0x180011ed4  mov     rdi, rax
0x180011ed7  test    rax, rax
0x180011eda  jz      short loc_180011F1E
0x180011edc  lea     rax, [rsp+0E8h+ReturnLength]
0x180011ee1  mov     [rsp+0E8h+ReturnLength], 0
0x180011ee9  mov     r9d, 80h; TokenInformationLength
0x180011eef  mov     qword ptr [rsp+0E8h+SubAuthority2], rax; ReturnLength
0x180011ef4  mov     r8, rdi; TokenInformation
0x180011ef7  mov     edx, 2; TokenInformationClass
0x180011efc  mov     rcx, rbx; TokenHandle
0x180011eff  call    cs:__imp_NtQueryInformationToken
0x180011f06  nop     dword ptr [rax+rax+00h]
0x180011f0b  cmp     eax, 0C0000023h
0x180011f10  jz      loc_18001223A
0x180011f16  test    eax, eax
0x180011f18  js      loc_1800122B0
0x180011f1e  test    rdi, rdi
0x180011f21  jz      loc_1800122CE
0x180011f27  xor     ebx, ebx
0x180011f29  mov     [rsp+0E8h+arg_10], r13
0x180011f31  xor     r13d, r13d
0x180011f34  mov     [rsp+0E8h+var_84], ebx
0x180011f38  cmp     [rdi], ebx
0x180011f3a  jbe     loc_1800120D3
0x180011f40  lea     rax, [rdi+8]
0x180011f44  mov     [rsp+0E8h+var_70], rax
0x180011f49  nop     dword ptr [rax+00000000h]
0x180011f50  mov     r12d, r13d
0x180011f53  test    rsi, rsi
0x180011f56  jz      loc_1800122DF
0x180011f5c  test    r15d, r15d
0x180011f5f  jz      loc_1800122DF
0x180011f65  mov     rbp, [rsp+0E8h+Sid1]
0x180011f6a  mov     rbx, rsi
0x180011f6d  shl     r12, 4
0x180011f71  mov     rsi, [r12+rdi+8]
0x180011f76  test    r14, r14
0x180011f79  jz      short loc_180011F98
0x180011f7b  test    rbp, rbp
0x180011f7e  jz      short loc_180011F98
0x180011f80  mov     rdx, rsi; Sid2
0x180011f83  mov     rcx, rbp; Sid1
0x180011f86  call    cs:__imp_RtlEqualSid
0x180011f8d  nop     dword ptr [rax+rax+00h]
0x180011f92  test    al, al
0x180011f94  cmovnz  rsi, r14
0x180011f98  xor     edi, edi
0x180011f9a  nop     word ptr [rax+rax+00h]
0x180011fa0  cmp     edi, r15d
0x180011fa3  jnb     loc_1800121FE
0x180011fa9  test    rbp, rbp
0x180011fac  jz      short loc_180011FBD
0x180011fae  test    r14, r14
0x180011fb1  jz      short loc_180011FBD
0x180011fb3  cmp     dword ptr [rbx+8], 0FFFFFFFFh
0x180011fb7  jz      loc_180012062
0x180011fbd  mov     edx, [rbx+8]
0x180011fc0  mov     r8, [rbx]
0x180011fc3  cmp     edx, 0FFFFFFFFh
0x180011fc6  jz      short loc_180012041
0x180011fc8  movzx   eax, byte ptr [rsi]
0x180011fcb  cmp     [r8], al
0x180011fce  jnz     loc_180012057
0x180011fd4  movzx   eax, byte ptr [rsi+2]
0x180011fd8  cmp     [r8+2], al
0x180011fdc  jnz     short loc_180012057
0x180011fde  movzx   eax, byte ptr [rsi+3]
0x180011fe2  cmp     [r8+3], al
0x180011fe6  jnz     short loc_180012057
0x180011fe8  movzx   eax, byte ptr [rsi+4]
0x180011fec  cmp     [r8+4], al
0x180011ff0  jnz     short loc_180012057
0x180011ff2  movzx   eax, byte ptr [rsi+5]
0x180011ff6  cmp     [r8+5], al
0x180011ffa  jnz     short loc_180012057
0x180011ffc  movzx   eax, byte ptr [rsi+6]
0x180012000  cmp     [r8+6], al
0x180012004  jnz     short loc_180012057
0x180012006  movzx   eax, byte ptr [rsi+7]
0x18001200a  cmp     [r8+7], al
0x18001200e  jnz     short loc_180012057
0x180012010  movzx   r10d, byte ptr [r8+1]
0x180012015  movzx   r11d, byte ptr [rsi+1]
0x18001201a  cmp     r11b, r10b
0x18001201d  jb      short loc_180012057
0x18001201f  xor     r9d, r9d
0x180012022  cmp     r9d, edx
0x180012025  jnb     loc_1800121D6
0x18001202b  lea     rcx, ds:8[r9*4]
0x180012033  mov     eax, [rcx+rsi]
0x180012036  cmp     [rcx+r8], eax
0x18001203a  jnz     short loc_180012057
0x18001203c  inc     r9d
0x18001203f  jmp     short loc_180012022
0x180012041  mov     rdx, rsi; Sid2
0x180012044  mov     rcx, r8; Sid1
0x180012047  call    cs:__imp_RtlEqualSid
0x18001204e  nop     dword ptr [rax+rax+00h]
0x180012053  test    al, al
0x180012055  jnz     short loc_180012092
0x180012057  inc     edi
0x180012059  add     rbx, 10h
0x18001205d  jmp     loc_180011FA0
0x180012062  mov     rdx, [rbx]; Sid2
0x180012065  mov     rcx, rbp; Sid1
0x180012068  call    cs:__imp_RtlEqualSid
0x18001206f  nop     dword ptr [rax+rax+00h]
0x180012074  test    al, al
0x180012076  jz      loc_180011FBD
0x18001207c  mov     rdx, rsi; Sid2
0x18001207f  mov     rcx, r14; Sid1
0x180012082  call    cs:__imp_RtlEqualSid
0x180012089  nop     dword ptr [rax+rax+00h]
0x18001208e  test    al, al
0x180012090  jz      short loc_180012057
0x180012092  mov     rcx, [rsp+0E8h+var_70]
0x180012097  add     rcx, r12
0x18001209a  mov     rcx, [rcx]; Sid
0x18001209d  call    cs:__imp_RtlLengthSid
0x1800120a4  nop     dword ptr [rax+rax+00h]
0x1800120a9  mov     ebx, [rsp+0E8h+var_84]
0x1800120ad  mov     rdi, [rsp+0E8h+var_80]
0x1800120b2  add     ebx, 10h
0x1800120b5  add     ebx, eax
0x1800120b7  mov     [rsp+0E8h+var_84], ebx
0x1800120bb  mov     rsi, [rsp+0E8h+var_68]
0x1800120c3  lea     rax, [rdi+8]
0x1800120c7  inc     r13d
0x1800120ca  cmp     r13d, [rdi]
0x1800120cd  jb      loc_180011F50
0x1800120d3  mov     rcx, gs:60h
0x1800120dc  xor     edx, edx; Flags
0x1800120de  mov     r8d, ebx; Size
0x1800120e1  mov     rcx, [rcx+30h]; HeapHandle
0x1800120e5  call    cs:__imp_RtlAllocateHeap
0x1800120ec  nop     dword ptr [rax+rax+00h]
0x1800120f1  mov     r13, [rsp+0E8h+arg_10]
0x1800120f9  mov     rbp, rax
0x1800120fc  test    rax, rax
0x1800120ff  jz      loc_1800122B0
0x180012105  mov     r14d, [rdi]
0x180012108  xor     r12d, r12d
0x18001210b  mov     esi, r14d
0x18001210e  shl     rsi, 4
0x180012112  add     rsi, rax
0x180012115  test    r14d, r14d
0x180012118  jz      short loc_180012167
0x18001211a  xor     r15d, r15d
0x18001211d  mov     rbx, r15
0x180012120  shl     rbx, 4
0x180012124  add     rdi, rbx
0x180012127  mov     rcx, [rdi+8]; Sid
0x18001212b  call    cs:__imp_RtlLengthSid
0x180012132  nop     dword ptr [rax+rax+00h]
0x180012137  mov     [rbx+rbp], rsi
0x18001213b  mov     rcx, rsi; void *
0x18001213e  mov     dword ptr [rbx+rbp+8], 0
0x180012146  mov     rdx, [rdi+8]; Src
0x18001214a  mov     r8d, eax; Size
0x18001214d  mov     ebx, eax
0x18001214f  call    memcpy_0
0x180012154  mov     rdi, [rsp+0E8h+var_80]
0x180012159  add     rsi, rbx
0x18001215c  inc     r12d
0x18001215f  inc     r15
0x180012162  cmp     r12d, r14d
0x180012165  jb      short loc_18001211D
0x180012167  mov     rcx, gs:60h
0x180012170  mov     r8, rdi; P
0x180012173  xor     edx, edx; Flags
0x180012175  mov     rcx, [rcx+30h]; HeapHandle
0x180012179  call    cs:__imp_RtlFreeHeap
0x180012180  nop     dword ptr [rax+rax+00h]
0x180012185  mov     rcx, [rsp+0E8h+Sid1]; Sid
0x18001218a  test    rcx, rcx
0x18001218d  jz      short loc_18001219B
0x18001218f  call    cs:__imp_RtlFreeSid
0x180012196  nop     dword ptr [rax+rax+00h]
0x18001219b  mov     rax, [rsp+0E8h+var_60]
0x1800121a3  mov     [rax], rbp
0x1800121a6  mov     rax, [rsp+0E8h+var_58]
0x1800121ae  mov     [rax], r14d
0x1800121b1  mov     al, 1
0x1800121b3  mov     rcx, [rsp+0E8h+var_48]
0x1800121bb  xor     rcx, rsp; StackCookie
0x1800121be  call    __security_check_cookie
0x1800121c3  add     rsp, 0B0h
0x1800121ca  pop     r15
0x1800121cc  pop     r14
0x1800121ce  pop     r12
0x1800121d0  pop     rdi
0x1800121d1  pop     rsi
0x1800121d2  pop     rbp
0x1800121d3  pop     rbx
0x1800121d4  retn
0x1800121d6  mov     r9d, r11d
0x1800121d9  sub     r9d, r10d
0x1800121dc  cmp     edx, r10d
0x1800121df  jnb     loc_180012092
0x1800121e5  mov     ecx, edx
0x1800121e7  lea     eax, [r9+rdx]
0x1800121eb  mov     eax, [rsi+rax*4+8]
0x1800121ef  cmp     [r8+rcx*4+8], eax
0x1800121f4  jnz     loc_180012057
0x1800121fa  inc     edx
0x1800121fc  jmp     short loc_1800121DC
0x1800121fe  add     r12, [rsp+0E8h+var_70]
0x180012203  mov     rdi, [rsp+0E8h+var_80]
0x180012208  mov     ebx, [rsp+0E8h+var_84]
0x18001220c  mov     r8d, r13d
0x18001220f  lea     edx, [r13+1]
0x180012213  not     r8d
0x180012216  shl     rdx, 4
0x18001221a  add     r8d, [rdi]
0x18001221d  add     rdx, 8
0x180012221  shl     r8, 4; Size
0x180012225  add     rdx, rdi; Src
0x180012228  mov     rcx, r12; void *
0x18001222b  call    memmove_0
0x180012230  dec     dword ptr [rdi]
0x180012232  dec     r13d
0x180012235  jmp     loc_1800120BB
0x18001223a  mov     rcx, gs:60h
0x180012243  mov     r8, rdi; P
0x180012246  xor     edx, edx; Flags
0x180012248  mov     rcx, [rcx+30h]; HeapHandle
0x18001224c  call    cs:__imp_RtlFreeHeap
0x180012253  nop     dword ptr [rax+rax+00h]
0x180012258  mov     rcx, gs:60h
0x180012261  xor     edx, edx; Flags
0x180012263  mov     r8d, [rsp+0E8h+ReturnLength]; Size
0x180012268  mov     rcx, [rcx+30h]; HeapHandle
0x18001226c  call    cs:__imp_RtlAllocateHeap
0x180012273  nop     dword ptr [rax+rax+00h]
0x180012278  mov     [rsp+0E8h+var_80], rax
0x18001227d  mov     rdi, rax
0x180012280  test    rax, rax
0x180012283  jz      short loc_1800122B0
0x180012285  mov     r9d, [rsp+0E8h+ReturnLength]; TokenInformationLength
0x18001228a  lea     rax, [rsp+0E8h+ReturnLength]
0x18001228f  mov     r8, rdi; TokenInformation
0x180012292  mov     qword ptr [rsp+0E8h+SubAuthority2], rax; ReturnLength
0x180012297  mov     edx, 2; TokenInformationClass
0x18001229c  mov     rcx, rbx; TokenHandle
0x18001229f  call    cs:__imp_NtQueryInformationToken
0x1800122a6  nop     dword ptr [rax+rax+00h]
0x1800122ab  jmp     loc_180011F16
  ... truncated ...
```
