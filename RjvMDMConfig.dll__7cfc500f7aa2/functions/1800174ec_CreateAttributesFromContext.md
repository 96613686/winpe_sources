# CreateAttributesFromContext

- ea: `0x1800174ec`
- end: `0x180017758`
- name: `CreateAttributesFromContext`
- size: `620`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180017bcc`

## callees

- `0x1800174ec`
- `0x180017760`
- `0x180017784`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001760f`
- `ntdll!RtlInitUnicodeString` at `0x180017643`
- `ntdll!RtlInitUnicodeString` at `0x180017681`
- `ntdll!RtlInitUnicodeString` at `0x1800176be`
- `ntdll!RtlInitUnicodeString` at `0x18001760f`
- `ntdll!RtlInitUnicodeString` at `0x180017643`
- `ntdll!RtlInitUnicodeString` at `0x180017681`
- `ntdll!RtlInitUnicodeString` at `0x1800176be`

## pseudocode

```c
__int64 __fastcall CreateAttributesFromContext(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  __int64 v6; // r12
  unsigned __int64 *v7; // r15
  unsigned int v8; // ebx
  WCHAR *v9; // r14
  __int64 v10; // rsi
  unsigned int v11; // r8d
  __int64 v12; // rdx
  __int64 v13; // rcx
  WCHAR *v14; // rax
  struct _UNICODE_STRING *v15; // rax
  struct _UNICODE_STRING *v16; // rdi
  __int64 v17; // rax
  int v18; // ecx
  __int64 v19; // rax
  __int64 v20; // rax

  v6 = *(unsigned int *)(a1 + 4);
  *a5 = 0;
  if ( (*(_QWORD *)(a1 + 8) & 0xFFFFFFFFFFFFFF5FuLL) != 0 )
  {
    v7 = (unsigned __int64 *)EnterpriseContextLibMemAllocPaged(8);
    if ( !v7 )
      return (unsigned int)-1073741801;
    *v7 = *(_QWORD *)(a1 + 8) & 0xFFFFFFFFFFFFFF5FuLL;
  }
  else
  {
    v7 = 0;
  }
  if ( !(_DWORD)v6 )
  {
    v8 = 0;
    v10 = 0;
    goto LABEL_15;
  }
  v9 = 0;
  if ( (unsigned __int64)(16 * v6) <= 0xFFFFFFFF )
  {
    v10 = EnterpriseContextLibMemAllocPaged((unsigned int)(16 * v6));
    if ( !v10 )
    {
LABEL_28:
      v8 = -1073741801;
      goto LABEL_29;
    }
    v8 = 0;
    v11 = 0;
    v12 = 0;
    do
    {
      ++v11;
      v13 = 2 * v12++;
      *(_WORD *)(v10 + 8 * v13 + 2) = *(_WORD *)(a1 + 8 * v13 + 18);
      *(_WORD *)(v10 + 8 * v13) = *(_WORD *)(a1 + 8 * v13 + 16);
      *(_QWORD *)(v10 + 8 * v13 + 8) = *(_QWORD *)(a1 + 8 * v13 + 24);
    }
    while ( v11 < (unsigned int)v6 );
LABEL_15:
    v14 = (WCHAR *)EnterpriseContextLibMemAllocPaged(8);
    v9 = v14;
    if ( v14 )
    {
      *(_QWORD *)v14 = 1;
      if ( *(char *)(a1 + 8) < 0 )
        *(_QWORD *)v14 = 3;
      v15 = (struct _UNICODE_STRING *)EnterpriseContextLibMemAllocPaged(160);
      v16 = v15;
      if ( v15 )
      {
        RtlInitUnicodeString(v15, L"EDP://PolicyFlags");
        *(_DWORD *)&v16[1].Length = 2;
        *(_DWORD *)(&v16[1].MaximumLength + 1) = 65;
        *(_QWORD *)&v16[2].Length = v7;
        LODWORD(v16[1].Buffer) = v7 != 0;
        RtlInitUnicodeString((struct _UNICODE_STRING *)((char *)v16 + 40), L"EDP://EnterpriseIds");
        LODWORD(v16[3].Buffer) = 3;
        HIDWORD(v16[3].Buffer) = 67;
        if ( (*(_BYTE *)(a1 + 8) & 0x20) != 0 )
        {
          v17 = 0;
          v18 = 0;
        }
        else
        {
          v17 = v10;
          v18 = v6;
        }
        *(_DWORD *)&v16[4].Length = v18;
        v16[4].Buffer = (PWSTR)v17;
        RtlInitUnicodeString(v16 + 5, L"EDP://ExemptEnterpriseIds");
        *(_DWORD *)&v16[6].Length = 3;
        *(_DWORD *)(&v16[6].MaximumLength + 1) = 67;
        if ( (*(_BYTE *)(a1 + 8) & 0x20) != 0 )
        {
          v19 = v10;
        }
        else
        {
          v19 = 0;
          LODWORD(v6) = 0;
        }
        LODWORD(v16[6].Buffer) = v6;
        *(_QWORD *)&v16[7].Length = v19;
        RtlInitUnicodeString((struct _UNICODE_STRING *)((char *)v16 + 120), L"EDP://EvaluationFlags");
        LODWORD(v16[8].Buffer) = 2;
        HIDWORD(v16[8].Buffer) = 65;
        *(_DWORD *)&v16[9].Length = 1;
        v16[9].Buffer = v9;
        v20 = EnterpriseContextLibMemAllocPaged(16);
        if ( v20 )
        {
          *(_DWORD *)v20 = 1;
          *(_DWORD *)(v20 + 4) = 4;
          *(_QWORD *)(v20 + 8) = v16;
          *a5 = v20;
          return v8;
        }
        EnterpriseContextLibMemFree(v16);
      }
    }
    goto LABEL_28;
  }
  v10 = 0;
  v8 = -1073741675;
LABEL_29:
  if ( v7 )
    EnterpriseContextLibMemFree(v7);
  if ( v9 )
    EnterpriseContextLibMemFree(v9);
  if ( v10 )
    EnterpriseContextLibMemFree(v10);
  return v8;
}

```

## disassembly

```asm
0x1800174ec  push    rbx
0x1800174ee  push    rbp
0x1800174ef  push    rsi
0x1800174f0  push    rdi
0x1800174f1  push    r12
0x1800174f3  push    r13
0x1800174f5  push    r14
0x1800174f7  push    r15
0x1800174f9  sub     rsp, 28h
0x1800174fd  mov     r13, [rsp+68h+arg_20]
0x180017505  mov     rbx, 0FFFFFFFFFFFFFF5Fh
0x18001750c  mov     rbp, rcx
0x18001750f  mov     r12d, [rcx+4]
0x180017513  mov     qword ptr [r13+0], 0
0x18001751b  test    [rcx+8], rbx
0x18001751f  jz      short loc_180017549
0x180017521  mov     ecx, 8
0x180017526  call    EnterpriseContextLibMemAllocPaged
0x18001752b  mov     r15, rax
0x18001752e  test    rax, rax
0x180017531  jnz     short loc_18001753D
0x180017533  mov     ebx, 0C0000017h
0x180017538  jmp     loc_180017744
0x18001753d  mov     rax, [rbp+8]
0x180017541  and     rax, rbx
0x180017544  mov     [r15], rax
0x180017547  jmp     short loc_18001754C
0x180017549  xor     r15d, r15d
0x18001754c  mov     edi, 1
0x180017551  test    r12d, r12d
0x180017554  jz      short loc_1800175C5
0x180017556  mov     rax, r12
0x180017559  xor     r14d, r14d
0x18001755c  shl     rax, 4
0x180017560  mov     ecx, 0FFFFFFFFh
0x180017565  cmp     rax, rcx
0x180017568  ja      short loc_1800175B9
0x18001756a  mov     ecx, eax
0x18001756c  call    EnterpriseContextLibMemAllocPaged
0x180017571  mov     rsi, rax
0x180017574  test    rax, rax
0x180017577  jz      loc_180017718
0x18001757d  xor     ebx, ebx
0x18001757f  xor     r8d, r8d
0x180017582  test    r12d, r12d
0x180017585  jz      short loc_1800175C9
0x180017587  xor     edx, edx
0x180017589  mov     rcx, rdx
0x18001758c  add     r8d, edi
0x18001758f  add     rcx, rcx
0x180017592  add     rdx, rdi
0x180017595  movzx   eax, word ptr [rbp+rcx*8+12h]
0x18001759a  mov     [rsi+rcx*8+2], ax
0x18001759f  movzx   eax, word ptr [rbp+rcx*8+10h]
0x1800175a4  mov     [rsi+rcx*8], ax
0x1800175a8  mov     rax, [rbp+rcx*8+18h]
0x1800175ad  mov     [rsi+rcx*8+8], rax
0x1800175b2  cmp     r8d, r12d
0x1800175b5  jb      short loc_180017589
0x1800175b7  jmp     short loc_1800175C9
0x1800175b9  xor     esi, esi
0x1800175bb  mov     ebx, 0C0000095h
0x1800175c0  jmp     loc_18001771D
0x1800175c5  xor     ebx, ebx
0x1800175c7  xor     esi, esi
0x1800175c9  mov     ecx, 8
0x1800175ce  call    EnterpriseContextLibMemAllocPaged
0x1800175d3  mov     r14, rax
0x1800175d6  test    rax, rax
0x1800175d9  jz      loc_180017718
0x1800175df  mov     [rax], rdi
0x1800175e2  test    byte ptr [rbp+8], 80h
0x1800175e6  jz      short loc_1800175EF
0x1800175e8  mov     qword ptr [rax], 3
0x1800175ef  mov     ecx, 0A0h
0x1800175f4  call    EnterpriseContextLibMemAllocPaged
0x1800175f9  mov     rdi, rax
0x1800175fc  test    rax, rax
0x1800175ff  jz      loc_180017718
0x180017605  lea     rdx, SourceString; "EDP://PolicyFlags"
0x18001760c  mov     rcx, rax; DestinationString
0x18001760f  call    cs:__imp_RtlInitUnicodeString
0x180017616  nop     dword ptr [rax+rax+00h]
0x18001761b  xor     eax, eax
0x18001761d  mov     dword ptr [rdi+10h], 2
0x180017624  test    r15, r15
0x180017627  mov     dword ptr [rdi+14h], 41h ; 'A'
0x18001762e  lea     rcx, [rdi+28h]; DestinationString
0x180017632  mov     [rdi+20h], r15
0x180017636  setnz   al
0x180017639  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x180017640  mov     [rdi+18h], eax
0x180017643  call    cs:__imp_RtlInitUnicodeString
0x18001764a  nop     dword ptr [rax+rax+00h]
0x18001764f  mov     dword ptr [rdi+38h], 3
0x180017656  mov     dword ptr [rdi+3Ch], 43h ; 'C'
0x18001765d  test    byte ptr [rbp+8], 20h
0x180017661  jz      short loc_180017669
0x180017663  xor     eax, eax
0x180017665  xor     ecx, ecx
0x180017667  jmp     short loc_18001766F
0x180017669  mov     rax, rsi
0x18001766c  mov     ecx, r12d
0x18001766f  mov     [rdi+40h], ecx
0x180017672  lea     rdx, aEdpExemptenter; "EDP://ExemptEnterpriseIds"
0x180017679  lea     rcx, [rdi+50h]; DestinationString
0x18001767d  mov     [rdi+48h], rax
0x180017681  call    cs:__imp_RtlInitUnicodeString
0x180017688  nop     dword ptr [rax+rax+00h]
0x18001768d  mov     dword ptr [rdi+60h], 3
0x180017694  mov     dword ptr [rdi+64h], 43h ; 'C'
0x18001769b  test    byte ptr [rbp+8], 20h
0x18001769f  jz      short loc_1800176A6
0x1800176a1  mov     rax, rsi
0x1800176a4  jmp     short loc_1800176AB
0x1800176a6  xor     eax, eax
0x1800176a8  xor     r12d, r12d
0x1800176ab  mov     [rdi+68h], r12d
0x1800176af  lea     rcx, [rdi+78h]; DestinationString
0x1800176b3  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x1800176ba  mov     [rdi+70h], rax
0x1800176be  call    cs:__imp_RtlInitUnicodeString
0x1800176c5  nop     dword ptr [rax+rax+00h]
0x1800176ca  mov     ebp, 1
0x1800176cf  mov     dword ptr [rdi+88h], 2
0x1800176d9  mov     dword ptr [rdi+8Ch], 41h ; 'A'
0x1800176e3  mov     [rdi+90h], ebp
0x1800176e9  mov     [rdi+98h], r14
0x1800176f0  lea     ecx, [rbp+0Fh]
0x1800176f3  call    EnterpriseContextLibMemAllocPaged
0x1800176f8  test    rax, rax
0x1800176fb  jz      short loc_180017710
0x1800176fd  mov     [rax], ebp
0x1800176ff  mov     dword ptr [rax+4], 4
0x180017706  mov     [rax+8], rdi
0x18001770a  mov     [r13+0], rax
0x18001770e  jmp     short loc_180017744
0x180017710  mov     rcx, rdi
0x180017713  call    EnterpriseContextLibMemFree
0x180017718  mov     ebx, 0C0000017h
0x18001771d  test    r15, r15
0x180017720  jz      short loc_18001772A
0x180017722  mov     rcx, r15
0x180017725  call    EnterpriseContextLibMemFree
0x18001772a  test    r14, r14
0x18001772d  jz      short loc_180017737
0x18001772f  mov     rcx, r14
0x180017732  call    EnterpriseContextLibMemFree
0x180017737  test    rsi, rsi
0x18001773a  jz      short loc_180017744
0x18001773c  mov     rcx, rsi
0x18001773f  call    EnterpriseContextLibMemFree
0x180017744  mov     eax, ebx
0x180017746  add     rsp, 28h
0x18001774a  pop     r15
0x18001774c  pop     r14
0x18001774e  pop     r13
0x180017750  pop     r12
0x180017752  pop     rdi
0x180017753  pop     rsi
0x180017754  pop     rbp
0x180017755  pop     rbx
0x180017756  retn
```
