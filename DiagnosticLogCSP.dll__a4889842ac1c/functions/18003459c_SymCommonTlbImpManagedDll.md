# SymCommonTlbImpManagedDll

- ea: `0x18003459c`
- end: `0x180034778`
- name: `SymCommonTlbImpManagedDll`
- size: `476`
- prototype: `__int64 __fastcall(PVOID BaseAddress, PIMAGE_NT_HEADERS NtHeader, BOOLEAN MappedAsImage)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033ad8`

## callees

- `0x18003459c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x18003466b`
- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x18003466b`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800345d0`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800345fd`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800345d0`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800345fd`
- `ntdll!RtlImageRvaToVa` at `0x180034655`
- `ntdll!RtlImageRvaToVa` at `0x1800346a9`
- `ntdll!RtlImageRvaToVa` at `0x1800346f2`
- `ntdll!RtlImageRvaToVa` at `0x180034726`
- `ntdll!RtlImageRvaToVa` at `0x180034655`
- `ntdll!RtlImageRvaToVa` at `0x1800346a9`
- `ntdll!RtlImageRvaToVa` at `0x1800346f2`
- `ntdll!RtlImageRvaToVa` at `0x180034726`

## string_xrefs

- `0x180034661`: `mscoree.dll`

## pseudocode

```c
__int64 __fastcall SymCommonTlbImpManagedDll(char *BaseAddress, PIMAGE_NT_HEADERS NtHeader, BOOLEAN MappedAsImage)
{
  unsigned int v6; // ebx
  ULONG *v7; // r14
  char *v8; // rsi
  __int64 v9; // r8
  char *v10; // rax
  char *v11; // rax
  __int64 v12; // r8
  __int64 *v13; // rax
  __int64 v14; // rcx
  ULONG Size; // [rsp+88h] [rbp+20h] BYREF

  v6 = 1;
  Size = 0;
  v7 = 0;
  v8 = 0;
  if ( RtlImageDirectoryEntryToData(BaseAddress, MappedAsImage, 0, &Size) || Size )
    goto LABEL_15;
  v7 = (ULONG *)RtlImageDirectoryEntryToData(BaseAddress, MappedAsImage, 1u, &Size);
  if ( !v7 )
    return 0;
  if ( !Size )
    return 0;
  v9 = v7[3];
  if ( !(_DWORD)v9 || !*v7 || v7[2] || Size >= 0x28 && v7[8] )
    return 0;
  v10 = MappedAsImage ? &BaseAddress[v9] : (char *)RtlImageRvaToVa(NtHeader, BaseAddress, v9, 0);
  if ( (unsigned int)_o__memicmp(v10, "mscoree.dll", 12) )
LABEL_15:
    v6 = 0;
  if ( !v6 )
    return v6;
  if ( NtHeader->OptionalHeader.Magic == 267 )
  {
    if ( MappedAsImage )
      v11 = &BaseAddress[*v7];
    else
      v11 = (char *)RtlImageRvaToVa(NtHeader, BaseAddress, *v7, 0);
    v12 = *(unsigned int *)v11;
    if ( (int)v12 < 0 || *((_DWORD *)v11 + 1) )
      return 0;
    if ( MappedAsImage )
    {
      v8 = &BaseAddress[v12];
      goto LABEL_36;
    }
LABEL_34:
    v8 = (char *)RtlImageRvaToVa(NtHeader, BaseAddress, v12, 0);
    goto LABEL_36;
  }
  if ( NtHeader->OptionalHeader.Magic == 523 )
  {
    if ( MappedAsImage )
      v13 = (__int64 *)&BaseAddress[*v7];
    else
      v13 = (__int64 *)RtlImageRvaToVa(NtHeader, BaseAddress, *v7, 0);
    if ( *v13 < 0 || v13[1] )
      return 0;
    if ( MappedAsImage )
    {
      v8 = &BaseAddress[*v13];
      goto LABEL_36;
    }
    LODWORD(v12) = *(_DWORD *)v13;
    goto LABEL_34;
  }
  v6 = 0;
LABEL_36:
  if ( v6 )
  {
    v14 = *(_QWORD *)(v8 + 2) - 0x4D6C6C44726F435FLL;
    if ( *(_QWORD *)(v8 + 2) == 0x4D6C6C44726F435FLL )
      v14 = *(unsigned int *)(v8 + 10) - 7235937LL;
    if ( v14 )
      return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18003459c  mov     rax, rsp
0x18003459f  push    rbx
0x1800345a0  push    rsi
0x1800345a1  push    rdi
0x1800345a2  push    r12
0x1800345a4  push    r14
0x1800345a6  push    r15
0x1800345a8  sub     rsp, 38h
0x1800345ac  mov     r15b, r8b
0x1800345af  mov     r12, rdx
0x1800345b2  mov     rdi, rcx
0x1800345b5  mov     ebx, 1
0x1800345ba  mov     dword ptr [rax+20h], 0
0x1800345c1  xor     r14d, r14d
0x1800345c4  xor     esi, esi
0x1800345c6  xor     r8d, r8d; Directory
0x1800345c9  lea     r9, [rax+20h]; Size
0x1800345cd  mov     dl, r15b; MappedAsImage
0x1800345d0  call    cs:__imp_RtlImageDirectoryEntryToData
0x1800345d6  test    rax, rax
0x1800345d9  jnz     loc_180034675
0x1800345df  cmp     [rsp+68h+Size], eax
0x1800345e6  jnz     loc_180034675
0x1800345ec  mov     r8d, ebx; Directory
0x1800345ef  lea     r9, [rsp+68h+Size]; Size
0x1800345f7  mov     dl, r15b; MappedAsImage
0x1800345fa  mov     rcx, rdi; BaseAddress
0x1800345fd  call    cs:__imp_RtlImageDirectoryEntryToData
0x180034603  mov     r14, rax
0x180034606  test    rax, rax
0x180034609  jz      short loc_18003463A
0x18003460b  mov     eax, [rsp+68h+Size]
0x180034612  test    eax, eax
0x180034614  jz      short loc_18003463A
0x180034616  mov     [rsp+68h+var_40], r14
0x18003461b  mov     r8d, [r14+0Ch]; Rva
0x18003461f  test    r8d, r8d
0x180034622  jz      short loc_18003463A
0x180034624  cmp     [r14], esi
0x180034627  jz      short loc_18003463A
0x180034629  cmp     [r14+8], esi
0x18003462d  jnz     short loc_18003463A
0x18003462f  cmp     eax, 28h ; '('
0x180034632  jb      short loc_180034641
0x180034634  cmp     [r14+20h], esi
0x180034638  jz      short loc_180034641
0x18003463a  xor     ebx, ebx
0x18003463c  jmp     loc_18003475C
0x180034641  test    r15b, r15b
0x180034644  jz      short loc_18003464C
0x180034646  lea     rax, [rdi+r8]
0x18003464a  jmp     short loc_18003465B
0x18003464c  xor     r9d, r9d; SectionHeader
0x18003464f  mov     rdx, rdi; BaseAddress
0x180034652  mov     rcx, r12; NtHeader
0x180034655  call    cs:__imp_RtlImageRvaToVa
0x18003465b  mov     r8d, 0Ch
0x180034661  lea     rdx, aMscoreeDll_0; "mscoree.dll"
0x180034668  mov     rcx, rax
0x18003466b  call    cs:__imp__o__memicmp
0x180034671  test    eax, eax
0x180034673  jz      short loc_18003467B
0x180034675  xor     ebx, ebx
0x180034677  mov     [rsp+68h+var_48], ebx
0x18003467b  test    ebx, ebx
0x18003467d  jz      loc_180034760
0x180034683  mov     eax, 10Bh
0x180034688  cmp     [r12+18h], ax
0x18003468e  jnz     short loc_1800346CC
0x180034690  test    r15b, r15b
0x180034693  jz      short loc_18003469D
0x180034695  mov     eax, [r14]
0x180034698  add     rax, rdi
0x18003469b  jmp     short loc_1800346AF
0x18003469d  xor     r9d, r9d; SectionHeader
0x1800346a0  mov     r8d, [r14]; Rva
0x1800346a3  mov     rdx, rdi; BaseAddress
0x1800346a6  mov     rcx, r12; NtHeader
0x1800346a9  call    cs:__imp_RtlImageRvaToVa
0x1800346af  mov     r8d, [rax]
0x1800346b2  test    r8d, r8d
0x1800346b5  js      short loc_18003463A
0x1800346b7  cmp     dword ptr [rax+4], 0
0x1800346bb  jnz     loc_18003463A
0x1800346c1  test    r15b, r15b
0x1800346c4  jz      short loc_18003471D
0x1800346c6  lea     rsi, [rdi+r8]
0x1800346ca  jmp     short loc_180034737
0x1800346cc  mov     eax, 20Bh
0x1800346d1  cmp     [r12+18h], ax
0x1800346d7  jnz     short loc_180034731
0x1800346d9  test    r15b, r15b
0x1800346dc  jz      short loc_1800346E6
0x1800346de  mov     eax, [r14]
0x1800346e1  add     rax, rdi
0x1800346e4  jmp     short loc_1800346F8
0x1800346e6  xor     r9d, r9d; SectionHeader
0x1800346e9  mov     r8d, [r14]; Rva
0x1800346ec  mov     rdx, rdi; BaseAddress
0x1800346ef  mov     rcx, r12; NtHeader
0x1800346f2  call    cs:__imp_RtlImageRvaToVa
0x1800346f8  mov     rcx, [rax]
0x1800346fb  test    rcx, rcx
0x1800346fe  js      loc_18003463A
0x180034704  cmp     qword ptr [rax+8], 0
0x180034709  jnz     loc_18003463A
0x18003470f  test    r15b, r15b
0x180034712  jz      short loc_18003471A
0x180034714  lea     rsi, [rcx+rdi]
0x180034718  jmp     short loc_180034737
0x18003471a  mov     r8d, [rax]; Rva
0x18003471d  xor     r9d, r9d; SectionHeader
0x180034720  mov     rdx, rdi; BaseAddress
0x180034723  mov     rcx, r12; NtHeader
0x180034726  call    cs:__imp_RtlImageRvaToVa
0x18003472c  mov     rsi, rax
0x18003472f  jmp     short loc_180034737
0x180034731  xor     ebx, ebx
0x180034733  mov     [rsp+68h+var_48], ebx
0x180034737  test    ebx, ebx
0x180034739  jz      short loc_180034760
0x18003473b  mov     rcx, [rsi+2]
0x18003473f  sub     rcx, cs:qword_18003DE90
0x180034746  jnz     short loc_180034754
0x180034748  mov     ecx, [rsi+0Ah]
0x18003474b  mov     eax, cs:dword_18003DE98
0x180034751  sub     rcx, rax
0x180034754  xor     eax, eax
0x180034756  test    rcx, rcx
0x180034759  cmovnz  ebx, eax
0x18003475c  mov     [rsp+68h+var_48], ebx
0x180034760  jmp     short loc_180034768
0x180034762  xor     ebx, ebx
0x180034764  mov     [rsp+68h+var_48], ebx
0x180034768  mov     eax, ebx
0x18003476a  add     rsp, 38h
0x18003476e  pop     r15
0x180034770  pop     r14
0x180034772  pop     r12
0x180034774  pop     rdi
0x180034775  pop     rsi
0x180034776  pop     rbx
0x180034777  retn
```
