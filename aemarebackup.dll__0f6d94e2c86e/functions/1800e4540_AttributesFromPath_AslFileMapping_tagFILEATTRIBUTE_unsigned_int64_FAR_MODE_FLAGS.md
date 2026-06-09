# _AttributesFromPath(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x1800e4540`
- end: `0x1800e49b5`
- name: `?_AttributesFromPath@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `1141`
- prototype: `__int64 __fastcall(LPCWSTR **, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180004ea0`
- `0x1800058fc`
- `0x180005914`
- `0x18004c020`
- `0x1800e4540`
- `0x1800e591c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800e4897`
- `ntdll!RtlAllocateHeap` at `0x1800e4897`
- `ntdll!RtlFreeHeap` at `0x1800e4932`
- `ntdll!RtlFreeHeap` at `0x1800e4932`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800e483d`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800e483d`

## string_xrefs

- `0x1800e4810`: `StringCchCopyW failed to copy full path [%x]`
- `0x1800e4821`: `_AttributesFromPath`
- `0x1800e465c`: `_SetFileAttributeValue`
- `0x1800e4767`: `_SetFileAttributeValue`
- `0x1800e48bb`: `_SetFileAttributeValue`
- `0x1800e4908`: `_SetFileAttributeValue`
- `0x1800e4663`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x1800e4752`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x1800e48f6`: `Failed to copy attribute value (index %d) [%x]`

## pseudocode

```c
__int64 __fastcall _AttributesFromPath(LPCWSTR **a1, __int64 a2, int a3)
{
  unsigned int v6; // edi
  __int64 v7; // rdi
  int IsOsComponent; // eax
  int v9; // r10d
  __int64 v10; // rax
  __int64 *v11; // rcx
  __int64 v12; // rdx
  _WORD *v13; // r8
  _WORD *v14; // rcx
  int v15; // r11d
  unsigned __int64 *v16; // rax
  __int64 v17; // rdx
  _WORD *v18; // r9
  _WORD *v19; // rcx
  WCHAR *v20; // r9
  __int64 v21; // rcx
  __int64 v22; // r8
  _WORD *v23; // rdx
  WCHAR *v24; // rdx
  int v25; // edi
  wchar_t *Heap; // rax
  int v27; // eax
  void *v28; // r8
  __int64 v30; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v31; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF

  LODWORD(v30) = 0;
  memset_0(pszPath, 0, 0x208u);
  if ( a2 )
  {
    v7 = 4;
    if ( (a3 & 4) == 0 )
      goto LABEL_18;
    IsOsComponent = _IsOsComponent(**a1);
    v9 = dword_1801197D4;
    LODWORD(v30) = IsOsComponent;
    if ( (unsigned int)dword_1801197D4 <= 2 )
    {
      *(_DWORD *)(a2 + 1088) = IsOsComponent;
    }
    else if ( dword_1801197D4 == 3 )
    {
      *(_QWORD *)(a2 + 1088) = v30;
    }
    else
    {
      if ( dword_1801197D4 != 4 )
        goto LABEL_18;
      v10 = 2;
      v11 = &v30;
      v12 = 260;
      v13 = (_WORD *)(a2 + 1088);
      do
      {
        if ( !v10 )
          break;
        if ( !*(_WORD *)v11 )
          break;
        *v13 = *(_WORD *)v11;
        v11 = (__int64 *)((char *)v11 + 2);
        ++v13;
        --v10;
        --v12;
      }
      while ( v12 );
      v14 = v13 - 1;
      if ( v12 )
        v14 = v13;
      *v14 = 0;
      if ( !v12 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          2,
          -2147024774);
        goto LABEL_18;
      }
    }
    *(_DWORD *)(a2 + 1608) = 2;
    *(_DWORD *)(a2 + 1612) = v9;
    *(_DWORD *)(a2 + 1616) = 1;
LABEL_18:
    if ( (*(_QWORD *)&a3 & 0x40000LL) != 0 )
    {
      v15 = dword_180119954;
      v31 = 0xBAD0BAD0BAD0BAD0uLL;
      switch ( dword_180119954 )
      {
        case 0:
          *(_DWORD *)(a2 + 9792) = -1160725808;
          goto LABEL_35;
        case 1:
        case 2:
          *(_DWORD *)(a2 + 9792) = -1160725808;
          goto LABEL_35;
        case 3:
          *(_QWORD *)(a2 + 9792) = 0xBAD0BAD0BAD0BAD0uLL;
          goto LABEL_35;
        case 4:
          v16 = &v31;
          v17 = 260;
          v18 = (_WORD *)(a2 + 9792);
          do
          {
            if ( !v7 )
              break;
            if ( !*(_WORD *)v16 )
              break;
            *v18 = *(_WORD *)v16;
            v16 = (unsigned __int64 *)((char *)v16 + 2);
            ++v18;
            --v7;
            --v17;
          }
          while ( v17 );
          v19 = v18 - 1;
          if ( v17 )
            v19 = v18;
          *v19 = 0;
          if ( !v17 )
          {
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3178,
              "StringCbCopy failed to copy string attribute (index %d) [%x]",
              18,
              -2147024774);
            break;
          }
LABEL_35:
          *(_DWORD *)(a2 + 10312) = 18;
          *(_DWORD *)(a2 + 10316) = v15;
          *(_DWORD *)(a2 + 10320) = 1;
          break;
      }
    }
    if ( (a3 & 2) != 0 )
    {
      v20 = pszPath;
      v21 = 2147483646;
      v22 = 260;
      v23 = **a1;
      do
      {
        if ( !v21 )
          break;
        if ( !*v23 )
          break;
        *v20++ = *v23++;
        --v21;
        --v22;
      }
      while ( v22 );
      v24 = v20 - 1;
      v6 = v22 == 0 ? 0x8007007A : 0;
      if ( v22 )
        v24 = v20;
      *v24 = 0;
      if ( !v22 )
      {
        AslLogCallPrintf(1, "_AttributesFromPath", 1415, "StringCchCopyW failed to copy full path [%x]", -2147024774);
        return v6;
      }
      if ( PathCchRemoveFileSpec(pszPath, 0x104u) >= 0 )
      {
        v25 = dword_1801197BC;
        if ( (unsigned int)dword_1801197BC <= 2 )
        {
          *(_DWORD *)(a2 + 544) = *(_DWORD *)pszPath;
          goto LABEL_59;
        }
        if ( dword_1801197BC == 3 )
        {
          *(_QWORD *)(a2 + 544) = *(_QWORD *)pszPath;
          goto LABEL_59;
        }
        if ( dword_1801197BC == 4 )
        {
          Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x20Au);
          *(_QWORD *)(a2 + 1080) = Heap;
          if ( !Heap )
          {
            AslLogCallPrintf(1, "_SetFileAttributeValue", 3144, "Failed to alloc memory for string value (index %d)", 1);
            return 0;
          }
          v27 = o_wmemcpy_s_0(Heap, 0x105u, pszPath, 0x104u);
          if ( v27 )
          {
            if ( v27 > 0 )
              v27 = (unsigned __int16)v27 | 0x80070000;
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3156,
              "Failed to copy attribute value (index %d) [%x]",
              1,
              v27);
            v28 = *(void **)(a2 + 1080);
            if ( v28 )
            {
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v28);
              *(_QWORD *)(a2 + 1080) = 0;
            }
            return 0;
          }
          *(_WORD *)(*(_QWORD *)(a2 + 1080) + 520LL) = 0;
          *(_WORD *)(a2 + 544) = 0;
LABEL_59:
          *(_DWORD *)(a2 + 1064) = 1;
          *(_DWORD *)(a2 + 1068) = v25;
          *(_DWORD *)(a2 + 1072) = 1;
        }
      }
    }
    return 0;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x1800e4540  mov     [rsp-8+arg_10], rbx
0x1800e4545  push    rbp
0x1800e4546  push    rsi
0x1800e4547  push    rdi
0x1800e4548  push    r12
0x1800e454a  push    r13
0x1800e454c  push    r14
0x1800e454e  push    r15
0x1800e4550  lea     rbp, [rsp-160h]
0x1800e4558  sub     rsp, 260h
0x1800e455f  mov     rax, cs:__security_cookie
0x1800e4566  xor     rax, rsp
0x1800e4569  mov     [rbp+190h+var_40], rax
0x1800e4570  mov     rsi, r8
0x1800e4573  mov     rbx, rdx
0x1800e4576  mov     r14, rcx
0x1800e4579  xor     r15d, r15d
0x1800e457c  xor     edx, edx; Val
0x1800e457e  mov     dword ptr [rsp+290h+var_260], r15d
0x1800e4583  mov     r8d, 208h; Size
0x1800e4589  lea     rcx, [rsp+290h+pszPath]; void *
0x1800e458e  call    memset_0
0x1800e4593  test    rbx, rbx
0x1800e4596  jnz     short loc_1800E45A2
0x1800e4598  mov     edi, 80070057h
0x1800e459d  jmp     loc_1800E4989
0x1800e45a2  mov     edi, 4
0x1800e45a7  lea     r13d, [rdi-2]
0x1800e45ab  lea     r12d, [rdi-3]
0x1800e45af  test    dil, sil
0x1800e45b2  jz      loc_1800E46A8
0x1800e45b8  mov     rcx, [r14]
0x1800e45bb  mov     rcx, [rcx]; lpFileName
0x1800e45be  call    ?_IsOsComponent@@YAHPEBG@Z; _IsOsComponent(ushort const *)
0x1800e45c3  mov     r10d, cs:dword_1801197D4
0x1800e45ca  mov     ecx, r10d
0x1800e45cd  mov     dword ptr [rsp+290h+var_260], eax
0x1800e45d1  test    r10d, r10d
0x1800e45d4  jz      loc_1800E468D
0x1800e45da  sub     ecx, r12d
0x1800e45dd  jz      loc_1800E468D
0x1800e45e3  sub     ecx, r12d
0x1800e45e6  jz      loc_1800E468D
0x1800e45ec  sub     ecx, r12d
0x1800e45ef  jz      loc_1800E467F
0x1800e45f5  cmp     ecx, r12d
0x1800e45f8  jnz     loc_1800E46A8
0x1800e45fe  mov     eax, r13d
0x1800e4601  lea     rcx, [rsp+290h+var_260]
0x1800e4606  mov     edx, 104h
0x1800e460b  lea     r8, [rbx+440h]
0x1800e4612  test    rax, rax
0x1800e4615  jz      short loc_1800E4633
0x1800e4617  movzx   r9d, word ptr [rcx]
0x1800e461b  test    r9w, r9w
0x1800e461f  jz      short loc_1800E4633
0x1800e4621  mov     [r8], r9w
0x1800e4625  add     rcx, r13
0x1800e4628  add     r8, r13
0x1800e462b  sub     rax, r12
0x1800e462e  sub     rdx, r12
0x1800e4631  jnz     short loc_1800E4612
0x1800e4633  mov     rax, rdx
0x1800e4636  lea     rcx, [r8-2]
0x1800e463a  neg     rax
0x1800e463d  sbb     r9d, r9d
0x1800e4640  not     r9d
0x1800e4643  and     r9d, 8007007Ah
0x1800e464a  test    rdx, rdx
0x1800e464d  cmovnz  rcx, r8
0x1800e4651  mov     [rcx], r15w
0x1800e4655  jnz     short loc_1800E4693
0x1800e4657  mov     [rsp+290h+var_268], r9d
0x1800e465c  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e4663  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x1800e466a  mov     [rsp+290h+var_270], r13d
0x1800e466f  mov     r8d, 0C6Ah
0x1800e4675  mov     ecx, r12d
0x1800e4678  call    AslLogCallPrintf
0x1800e467d  jmp     short loc_1800E46A8
0x1800e467f  mov     rax, [rsp+290h+var_260]
0x1800e4684  mov     [rbx+440h], rax
0x1800e468b  jmp     short loc_1800E4693
0x1800e468d  mov     [rbx+440h], eax
0x1800e4693  mov     [rbx+648h], r13d
0x1800e469a  mov     [rbx+64Ch], r10d
0x1800e46a1  mov     [rbx+650h], r12d
0x1800e46a8  bt      rsi, 12h
0x1800e46ad  jnb     loc_1800E47AF
0x1800e46b3  mov     r11d, cs:dword_180119954
0x1800e46ba  mov     rdx, 0BAD0BAD0BAD0BAD0h
0x1800e46c4  mov     [rsp+290h+var_258], rdx
0x1800e46c9  mov     ecx, r11d
0x1800e46cc  test    r11d, r11d
0x1800e46cf  jz      loc_1800E478D
0x1800e46d5  sub     ecx, r12d
0x1800e46d8  jz      loc_1800E4781
0x1800e46de  sub     ecx, r12d
0x1800e46e1  jz      loc_1800E4781
0x1800e46e7  sub     ecx, r12d
0x1800e46ea  jz      loc_1800E4778
0x1800e46f0  cmp     ecx, r12d
0x1800e46f3  jnz     loc_1800E47AF
0x1800e46f9  lea     rax, [rsp+290h+var_258]
0x1800e46fe  mov     edx, 104h
0x1800e4703  lea     r9, [rbx+2640h]
0x1800e470a  test    rdi, rdi
0x1800e470d  jz      short loc_1800E4729
0x1800e470f  movzx   ecx, word ptr [rax]
0x1800e4712  test    cx, cx
0x1800e4715  jz      short loc_1800E4729
0x1800e4717  mov     [r9], cx
0x1800e471b  add     rax, r13
0x1800e471e  add     r9, r13
0x1800e4721  sub     rdi, r12
0x1800e4724  sub     rdx, r12
0x1800e4727  jnz     short loc_1800E470A
0x1800e4729  mov     rax, rdx
0x1800e472c  lea     rcx, [r9-2]
0x1800e4730  neg     rax
0x1800e4733  sbb     r10d, r10d
0x1800e4736  not     r10d
0x1800e4739  and     r10d, 8007007Ah
0x1800e4740  test    rdx, rdx
0x1800e4743  cmovnz  rcx, r9
0x1800e4747  mov     [rcx], r15w
0x1800e474b  jnz     short loc_1800E4797
0x1800e474d  mov     [rsp+290h+var_268], r10d
0x1800e4752  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x1800e4759  mov     r8d, 0C6Ah
0x1800e475f  mov     [rsp+290h+var_270], 12h
0x1800e4767  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e476e  mov     ecx, r12d
0x1800e4771  call    AslLogCallPrintf
0x1800e4776  jmp     short loc_1800E47AF
0x1800e4778  mov     [rbx+2640h], rdx
0x1800e477f  jmp     short loc_1800E4797
0x1800e4781  mov     dword ptr [rbx+2640h], 0BAD0BAD0h
0x1800e478b  jmp     short loc_1800E4797
0x1800e478d  mov     dword ptr [rbx+2640h], 0BAD0BAD0h
0x1800e4797  mov     dword ptr [rbx+2848h], 12h
0x1800e47a1  mov     [rbx+284Ch], r11d
0x1800e47a8  mov     [rbx+2850h], r12d
0x1800e47af  test    r13b, sil
0x1800e47b2  jz      loc_1800E4986
0x1800e47b8  mov     rax, [r14]
0x1800e47bb  lea     r9, [rsp+290h+pszPath]
0x1800e47c0  mov     esi, 104h
0x1800e47c5  mov     ecx, 7FFFFFFEh
0x1800e47ca  mov     r8d, esi
0x1800e47cd  mov     rdx, [rax]
0x1800e47d0  test    rcx, rcx
0x1800e47d3  jz      short loc_1800E47EF
0x1800e47d5  movzx   eax, word ptr [rdx]
0x1800e47d8  test    ax, ax
0x1800e47db  jz      short loc_1800E47EF
0x1800e47dd  mov     [r9], ax
0x1800e47e1  add     rdx, r13
0x1800e47e4  add     r9, r13
0x1800e47e7  sub     rcx, r12
0x1800e47ea  sub     r8, r12
0x1800e47ed  jnz     short loc_1800E47D0
0x1800e47ef  mov     rax, r8
0x1800e47f2  lea     rdx, [r9-2]
0x1800e47f6  neg     rax
0x1800e47f9  sbb     edi, edi
0x1800e47fb  not     edi
0x1800e47fd  and     edi, 8007007Ah
0x1800e4803  test    r8, r8
0x1800e4806  cmovnz  rdx, r9
0x1800e480a  mov     [rdx], r15w
0x1800e480e  jnz     short loc_1800E4835
0x1800e4810  lea     r9, aStringcchcopyw_0; "StringCchCopyW failed to copy full path"...
0x1800e4817  mov     [rsp+290h+var_270], edi
0x1800e481b  mov     r8d, 587h
0x1800e4821  lea     rdx, aAttributesfrom; "_AttributesFromPath"
0x1800e4828  mov     ecx, r12d
0x1800e482b  call    AslLogCallPrintf
0x1800e4830  jmp     loc_1800E4989
0x1800e4835  mov     rdx, rsi; cchPath
0x1800e4838  lea     rcx, [rsp+290h+pszPath]; pszPath
0x1800e483d  call    cs:__imp_PathCchRemoveFileSpec
0x1800e4843  test    eax, eax
0x1800e4845  js      loc_1800E4986
0x1800e484b  mov     edi, cs:dword_1801197BC
0x1800e4851  mov     ecx, edi
0x1800e4853  test    edi, edi
0x1800e4855  jz      loc_1800E4968
0x1800e485b  sub     ecx, r12d
0x1800e485e  jz      loc_1800E4968
0x1800e4864  sub     ecx, r12d
0x1800e4867  jz      loc_1800E4968
0x1800e486d  sub     ecx, r12d
0x1800e4870  jz      loc_1800E495A
0x1800e4876  cmp     ecx, r12d
0x1800e4879  jnz     loc_1800E4986
0x1800e487f  mov     rcx, gs:60h
0x1800e4888  mov     edx, 8; Flags
0x1800e488d  mov     r8d, 20Ah; Size
0x1800e4893  mov     rcx, [rcx+30h]; HeapHandle
0x1800e4897  call    cs:__imp_RtlAllocateHeap
0x1800e489d  mov     [rbx+438h], rax
0x1800e48a4  test    rax, rax
0x1800e48a7  jnz     short loc_1800E48CF
0x1800e48a9  lea     r9, aFailedToAllocM_0; "Failed to alloc memory for string value"...
0x1800e48b0  mov     [rsp+290h+var_270], r12d
0x1800e48b5  mov     r8d, 0C48h
0x1800e48bb  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e48c2  mov     ecx, r12d
0x1800e48c5  call    AslLogCallPrintf
0x1800e48ca  jmp     loc_1800E4986
0x1800e48cf  mov     r9, rsi; N
0x1800e48d2  lea     r8, [rsp+290h+pszPath]; S2
0x1800e48d7  mov     edx, 105h; N1
0x1800e48dc  mov     rcx, rax; S1
0x1800e48df  call    _o_wmemcpy_s_0
0x1800e48e4  test    eax, eax
0x1800e48e6  jz      short loc_1800E4941
0x1800e48e8  jle     short loc_1800E48F2
0x1800e48ea  movzx   eax, ax
0x1800e48ed  or      eax, 80070000h
0x1800e48f2  mov     [rsp+290h+var_268], eax
0x1800e48f6  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
0x1800e48fd  mov     r8d, 0C54h
0x1800e4903  mov     [rsp+290h+var_270], r12d
0x1800e4908  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e490f  mov     ecx, r12d
0x1800e4912  call    AslLogCallPrintf
0x1800e4917  mov     r8, [rbx+438h]; P
0x1800e491e  test    r8, r8
0x1800e4921  jz      short loc_1800E4986
0x1800e4923  mov     rcx, gs:60h
0x1800e492c  xor     edx, edx; Flags
0x1800e492e  mov     rcx, [rcx+30h]; HeapHandle
0x1800e4932  call    cs:__imp_RtlFreeHeap
0x1800e4938  mov     [rbx+438h], r15
0x1800e493f  jmp     short loc_1800E4986
0x1800e4941  mov     rcx, [rbx+438h]
0x1800e4948  mov     [rcx+208h], r15w
0x1800e4950  mov     [rbx+220h], r15w
0x1800e4958  jmp     short loc_1800E4972
0x1800e495a  mov     rax, qword ptr [rsp+290h+pszPath]
0x1800e495f  mov     [rbx+220h], rax
0x1800e4966  jmp     short loc_1800E4972
0x1800e4968  mov     eax, dword ptr [rsp+290h+pszPath]
0x1800e496c  mov     [rbx+220h], eax
0x1800e4972  mov     [rbx+428h], r12d
0x1800e4979  mov     [rbx+42Ch], edi
0x1800e497f  mov     [rbx+430h], r12d
0x1800e4986  mov     edi, r15d
0x1800e4989  mov     eax, edi
0x1800e498b  mov     rcx, [rbp+190h+var_40]
0x1800e4992  xor     rcx, rsp; StackCookie
0x1800e4995  call    __security_check_cookie
0x1800e499a  mov     rbx, [rsp+290h+arg_10]
0x1800e49a2  add     rsp, 260h
0x1800e49a9  pop     r15
0x1800e49ab  pop     r14
0x1800e49ad  pop     r13
0x1800e49af  pop     r12
0x1800e49b1  pop     rdi
0x1800e49b2  pop     rsi
0x1800e49b3  pop     rbp
0x1800e49b4  retn
```
