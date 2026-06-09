# CreateAttributesFromContext

- ea: `0x140004410`
- end: `0x1400046df`
- name: `CreateAttributesFromContext`
- size: `719`
- prototype: `__int64 __fastcall(__int64, __int64, char, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140005568`
- `0x1400058c8`

## callees

- `0x140004410`
- `0x1400048e8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004678`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004693`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400046a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400046bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004678`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004693`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400046a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400046bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000455f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004593`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400045d1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000460e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000455f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004593`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400045d1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000460e`

## pseudocode

```c
__int64 __fastcall CreateAttributesFromContext(__int64 a1, __int64 a2, char a3, __int64 a4, __int64 *a5)
{
  __int64 v6; // r12
  unsigned __int64 *v9; // r15
  unsigned int v10; // ebx
  WCHAR *v11; // r14
  WCHAR *v12; // rsi
  unsigned int v13; // r8d
  __int64 v14; // rcx
  WCHAR *v15; // rax
  struct _UNICODE_STRING *v16; // rax
  struct _UNICODE_STRING *v17; // rdi
  WCHAR *v18; // rax
  int v19; // ecx
  WCHAR *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  char v24; // [rsp+78h] [rbp+10h]

  v24 = a2;
  v6 = *(unsigned int *)(a1 + 4);
  *a5 = 0;
  if ( (*(_QWORD *)(a1 + 8) & 0xFFFFFFFFFFFFFF5FuLL) != 0 )
  {
    LOBYTE(a2) = a3;
    v9 = (unsigned __int64 *)EnterpriseContextLibMemAllocPaged(8, a2);
    if ( !v9 )
      return (unsigned int)-1073741801;
    *v9 = *(_QWORD *)(a1 + 8) & 0xFFFFFFFFFFFFFF5FuLL;
  }
  else
  {
    v9 = 0;
  }
  v11 = 0;
  if ( !(_DWORD)v6 )
  {
    v10 = 0;
    v12 = 0;
    goto LABEL_15;
  }
  if ( (unsigned __int64)(16 * v6) <= 0xFFFFFFFF )
  {
    LOBYTE(a2) = a3;
    v12 = (WCHAR *)EnterpriseContextLibMemAllocPaged((unsigned int)(16 * v6), a2);
    if ( !v12 )
      goto LABEL_31;
    v10 = 0;
    v13 = 0;
    a2 = 0;
    do
    {
      ++v13;
      v14 = 2 * a2++;
      v12[4 * v14 + 1] = *(_WORD *)(a1 + 8 * v14 + 18);
      v12[4 * v14] = *(_WORD *)(a1 + 8 * v14 + 16);
      *(_QWORD *)&v12[4 * v14 + 4] = *(_QWORD *)(a1 + 8 * v14 + 24);
    }
    while ( v13 < (unsigned int)v6 );
    v11 = 0;
LABEL_15:
    if ( v24 )
      goto LABEL_21;
    LOBYTE(a2) = a3;
    v15 = (WCHAR *)EnterpriseContextLibMemAllocPaged(8, a2);
    v11 = v15;
    if ( v15 )
    {
      if ( a4 )
      {
        *(_QWORD *)v15 = a4;
      }
      else
      {
        *(_QWORD *)v15 = 1;
        if ( *(char *)(a1 + 8) < 0 )
          *(_QWORD *)v15 = 3;
      }
LABEL_21:
      LOBYTE(a2) = a3;
      v16 = (struct _UNICODE_STRING *)EnterpriseContextLibMemAllocPaged(160, a2);
      v17 = v16;
      if ( v16 )
      {
        RtlInitUnicodeString(v16, L"EDP://PolicyFlags");
        *(_DWORD *)&v17[1].Length = 2;
        *(_DWORD *)(&v17[1].MaximumLength + 1) = 65;
        *(_QWORD *)&v17[2].Length = v9;
        LODWORD(v17[1].Buffer) = v9 != 0;
        RtlInitUnicodeString((struct _UNICODE_STRING *)((char *)v17 + 40), L"EDP://EnterpriseIds");
        LODWORD(v17[3].Buffer) = 3;
        HIDWORD(v17[3].Buffer) = 67;
        if ( (*(_BYTE *)(a1 + 8) & 0x20) != 0 )
        {
          v18 = 0;
          v19 = 0;
        }
        else
        {
          v18 = v12;
          v19 = v6;
        }
        *(_DWORD *)&v17[4].Length = v19;
        v17[4].Buffer = v18;
        RtlInitUnicodeString(v17 + 5, L"EDP://ExemptEnterpriseIds");
        *(_DWORD *)&v17[6].Length = 3;
        *(_DWORD *)(&v17[6].MaximumLength + 1) = 67;
        if ( (*(_BYTE *)(a1 + 8) & 0x20) != 0 )
        {
          v20 = v12;
        }
        else
        {
          v20 = 0;
          LODWORD(v6) = 0;
        }
        LODWORD(v17[6].Buffer) = v6;
        *(_QWORD *)&v17[7].Length = v20;
        RtlInitUnicodeString((struct _UNICODE_STRING *)((char *)v17 + 120), L"EDP://EvaluationFlags");
        LODWORD(v17[8].Buffer) = 2;
        HIDWORD(v17[8].Buffer) = 65;
        LOBYTE(v21) = a3;
        v17[9].Buffer = v11;
        *(_DWORD *)&v17[9].Length = v11 != 0;
        v22 = EnterpriseContextLibMemAllocPaged(16, v21);
        if ( v22 )
        {
          *(_DWORD *)v22 = 1;
          *(_DWORD *)(v22 + 4) = 4;
          *(_QWORD *)(v22 + 8) = v17;
          *a5 = v22;
          return v10;
        }
        ExFreePoolWithTag(v17, 0);
      }
    }
LABEL_31:
    v10 = -1073741801;
    goto LABEL_32;
  }
  v12 = 0;
  v10 = -1073741675;
LABEL_32:
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  return v10;
}

```

## disassembly

```asm
0x140004410  mov     [rsp+arg_8], dl
0x140004414  push    rbx
0x140004415  push    rbp
0x140004416  push    rsi
0x140004417  push    rdi
0x140004418  push    r12
0x14000441a  push    r13
0x14000441c  push    r14
0x14000441e  push    r15
0x140004420  sub     rsp, 28h
0x140004424  mov     rax, [rsp+68h+arg_20]
0x14000442c  mov     rbx, 0FFFFFFFFFFFFFF5Fh
0x140004433  mov     rdi, r9
0x140004436  mov     r12d, [rcx+4]
0x14000443a  mov     r13b, r8b
0x14000443d  mov     rbp, rcx
0x140004440  mov     qword ptr [rax], 0
0x140004447  test    [rcx+8], rbx
0x14000444b  jz      short loc_140004478
0x14000444d  mov     dl, r8b
0x140004450  mov     ecx, 8
0x140004455  call    EnterpriseContextLibMemAllocPaged
0x14000445a  mov     r15, rax
0x14000445d  test    rax, rax
0x140004460  jnz     short loc_14000446C
0x140004462  mov     ebx, 0C0000017h
0x140004467  jmp     loc_1400046CB
0x14000446c  mov     rax, [rbp+8]
0x140004470  and     rax, rbx
0x140004473  mov     [r15], rax
0x140004476  jmp     short loc_14000447B
0x140004478  xor     r15d, r15d
0x14000447b  xor     r14d, r14d
0x14000447e  test    r12d, r12d
0x140004481  jz      short loc_1400044F9
0x140004483  mov     rax, r12
0x140004486  mov     ecx, 0FFFFFFFFh
0x14000448b  shl     rax, 4
0x14000448f  cmp     rax, rcx
0x140004492  ja      short loc_1400044ED
0x140004494  mov     ecx, eax
0x140004496  mov     dl, r13b
0x140004499  call    EnterpriseContextLibMemAllocPaged
0x14000449e  mov     rsi, rax
0x1400044a1  test    rax, rax
0x1400044a4  jz      loc_140004684
0x1400044aa  xor     ebx, ebx
0x1400044ac  xor     r8d, r8d
0x1400044af  test    r12d, r12d
0x1400044b2  jz      short loc_1400044FD
0x1400044b4  xor     edx, edx
0x1400044b6  lea     r14d, [rbx+1]
0x1400044ba  mov     rcx, rdx
0x1400044bd  add     r8d, r14d
0x1400044c0  add     rcx, rcx
0x1400044c3  add     rdx, r14
0x1400044c6  movzx   eax, word ptr [rbp+rcx*8+12h]
0x1400044cb  mov     [rsi+rcx*8+2], ax
0x1400044d0  movzx   eax, word ptr [rbp+rcx*8+10h]
0x1400044d5  mov     [rsi+rcx*8], ax
0x1400044d9  mov     rax, [rbp+rcx*8+18h]
0x1400044de  mov     [rsi+rcx*8+8], rax
0x1400044e3  cmp     r8d, r12d
0x1400044e6  jb      short loc_1400044BA
0x1400044e8  xor     r14d, r14d
0x1400044eb  jmp     short loc_1400044FD
0x1400044ed  xor     esi, esi
0x1400044ef  mov     ebx, 0C0000095h
0x1400044f4  jmp     loc_140004689
0x1400044f9  xor     ebx, ebx
0x1400044fb  xor     esi, esi
0x1400044fd  cmp     [rsp+68h+arg_8], 0
0x140004502  jnz     short loc_14000453C
0x140004504  mov     dl, r13b
0x140004507  mov     ecx, 8
0x14000450c  call    EnterpriseContextLibMemAllocPaged
0x140004511  mov     r14, rax
0x140004514  test    rax, rax
0x140004517  jz      loc_140004684
0x14000451d  test    rdi, rdi
0x140004520  jz      short loc_140004527
0x140004522  mov     [rax], rdi
0x140004525  jmp     short loc_14000453C
0x140004527  mov     qword ptr [rax], 1
0x14000452e  mov     al, [rbp+8]
0x140004531  test    al, al
0x140004533  jns     short loc_14000453C
0x140004535  mov     qword ptr [r14], 3
0x14000453c  mov     dl, r13b
0x14000453f  mov     ecx, 0A0h
0x140004544  call    EnterpriseContextLibMemAllocPaged
0x140004549  mov     rdi, rax
0x14000454c  test    rax, rax
0x14000454f  jz      loc_140004684
0x140004555  lea     rdx, SourceString; "EDP://PolicyFlags"
0x14000455c  mov     rcx, rax; DestinationString
0x14000455f  call    cs:__imp_RtlInitUnicodeString
0x140004566  nop     dword ptr [rax+rax+00h]
0x14000456b  xor     eax, eax
0x14000456d  mov     dword ptr [rdi+10h], 2
0x140004574  test    r15, r15
0x140004577  mov     dword ptr [rdi+14h], 41h ; 'A'
0x14000457e  lea     rcx, [rdi+28h]; DestinationString
0x140004582  mov     [rdi+20h], r15
0x140004586  setnz   al
0x140004589  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x140004590  mov     [rdi+18h], eax
0x140004593  call    cs:__imp_RtlInitUnicodeString
0x14000459a  nop     dword ptr [rax+rax+00h]
0x14000459f  mov     dword ptr [rdi+38h], 3
0x1400045a6  mov     dword ptr [rdi+3Ch], 43h ; 'C'
0x1400045ad  test    byte ptr [rbp+8], 20h
0x1400045b1  jz      short loc_1400045B9
0x1400045b3  xor     eax, eax
0x1400045b5  xor     ecx, ecx
0x1400045b7  jmp     short loc_1400045BF
0x1400045b9  mov     rax, rsi
0x1400045bc  mov     ecx, r12d
0x1400045bf  mov     [rdi+40h], ecx
0x1400045c2  lea     rdx, aEdpExemptenter; "EDP://ExemptEnterpriseIds"
0x1400045c9  lea     rcx, [rdi+50h]; DestinationString
0x1400045cd  mov     [rdi+48h], rax
0x1400045d1  call    cs:__imp_RtlInitUnicodeString
0x1400045d8  nop     dword ptr [rax+rax+00h]
0x1400045dd  mov     dword ptr [rdi+60h], 3
0x1400045e4  mov     dword ptr [rdi+64h], 43h ; 'C'
0x1400045eb  test    byte ptr [rbp+8], 20h
0x1400045ef  jz      short loc_1400045F6
0x1400045f1  mov     rax, rsi
0x1400045f4  jmp     short loc_1400045FB
0x1400045f6  xor     eax, eax
0x1400045f8  xor     r12d, r12d
0x1400045fb  mov     [rdi+68h], r12d
0x1400045ff  lea     rcx, [rdi+78h]; DestinationString
0x140004603  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x14000460a  mov     [rdi+70h], rax
0x14000460e  call    cs:__imp_RtlInitUnicodeString
0x140004615  nop     dword ptr [rax+rax+00h]
0x14000461a  xor     eax, eax
0x14000461c  mov     dword ptr [rdi+88h], 2
0x140004626  test    r14, r14
0x140004629  mov     dword ptr [rdi+8Ch], 41h ; 'A'
0x140004633  mov     dl, r13b
0x140004636  mov     [rdi+98h], r14
0x14000463d  setnz   al
0x140004640  mov     ecx, 10h
0x140004645  mov     [rdi+90h], eax
0x14000464b  call    EnterpriseContextLibMemAllocPaged
0x140004650  test    rax, rax
0x140004653  jz      short loc_140004673
0x140004655  mov     rcx, [rsp+68h+arg_20]
0x14000465d  mov     dword ptr [rax], 1
0x140004663  mov     dword ptr [rax+4], 4
0x14000466a  mov     [rax+8], rdi
0x14000466e  mov     [rcx], rax
0x140004671  jmp     short loc_1400046CB
0x140004673  xor     edx, edx; Tag
0x140004675  mov     rcx, rdi; P
0x140004678  call    cs:__imp_ExFreePoolWithTag
0x14000467f  nop     dword ptr [rax+rax+00h]
0x140004684  mov     ebx, 0C0000017h
0x140004689  test    r15, r15
0x14000468c  jz      short loc_14000469F
0x14000468e  xor     edx, edx; Tag
0x140004690  mov     rcx, r15; P
0x140004693  call    cs:__imp_ExFreePoolWithTag
0x14000469a  nop     dword ptr [rax+rax+00h]
0x14000469f  test    r14, r14
0x1400046a2  jz      short loc_1400046B5
0x1400046a4  xor     edx, edx; Tag
0x1400046a6  mov     rcx, r14; P
0x1400046a9  call    cs:__imp_ExFreePoolWithTag
0x1400046b0  nop     dword ptr [rax+rax+00h]
0x1400046b5  test    rsi, rsi
0x1400046b8  jz      short loc_1400046CB
0x1400046ba  xor     edx, edx; Tag
0x1400046bc  mov     rcx, rsi; P
0x1400046bf  call    cs:__imp_ExFreePoolWithTag
0x1400046c6  nop     dword ptr [rax+rax+00h]
0x1400046cb  mov     eax, ebx
0x1400046cd  add     rsp, 28h
0x1400046d1  pop     r15
0x1400046d3  pop     r14
0x1400046d5  pop     r13
0x1400046d7  pop     r12
0x1400046d9  pop     rdi
0x1400046da  pop     rsi
0x1400046db  pop     rbp
0x1400046dc  pop     rbx
0x1400046dd  retn
```
