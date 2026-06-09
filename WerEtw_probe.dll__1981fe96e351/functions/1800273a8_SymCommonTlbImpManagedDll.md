# SymCommonTlbImpManagedDll

- ea: `0x1800273a8`
- end: `0x180027584`
- name: `SymCommonTlbImpManagedDll`
- size: `476`
- prototype: `__int64 __fastcall(PVOID BaseAddress, PIMAGE_NT_HEADERS NtHeader, BOOLEAN MappedAsImage)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026888`

## callees

- `0x1800273a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x180027477`
- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x180027477`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800273dc`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180027409`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800273dc`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180027409`
- `ntdll!RtlImageRvaToVa` at `0x180027461`
- `ntdll!RtlImageRvaToVa` at `0x1800274b5`
- `ntdll!RtlImageRvaToVa` at `0x1800274fe`
- `ntdll!RtlImageRvaToVa` at `0x180027532`
- `ntdll!RtlImageRvaToVa` at `0x180027461`
- `ntdll!RtlImageRvaToVa` at `0x1800274b5`
- `ntdll!RtlImageRvaToVa` at `0x1800274fe`
- `ntdll!RtlImageRvaToVa` at `0x180027532`

## string_xrefs

- `0x18002746d`: `mscoree.dll`

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
0x1800273a8  mov     rax, rsp
0x1800273ab  push    rbx
0x1800273ac  push    rsi
0x1800273ad  push    rdi
0x1800273ae  push    r12
0x1800273b0  push    r14
0x1800273b2  push    r15
0x1800273b4  sub     rsp, 38h
0x1800273b8  mov     r15b, r8b
0x1800273bb  mov     r12, rdx
0x1800273be  mov     rdi, rcx
0x1800273c1  mov     ebx, 1
0x1800273c6  mov     dword ptr [rax+20h], 0
0x1800273cd  xor     r14d, r14d
0x1800273d0  xor     esi, esi
0x1800273d2  xor     r8d, r8d; Directory
0x1800273d5  lea     r9, [rax+20h]; Size
0x1800273d9  mov     dl, r15b; MappedAsImage
0x1800273dc  call    cs:__imp_RtlImageDirectoryEntryToData
0x1800273e2  test    rax, rax
0x1800273e5  jnz     loc_180027481
0x1800273eb  cmp     [rsp+68h+Size], eax
0x1800273f2  jnz     loc_180027481
0x1800273f8  mov     r8d, ebx; Directory
0x1800273fb  lea     r9, [rsp+68h+Size]; Size
0x180027403  mov     dl, r15b; MappedAsImage
0x180027406  mov     rcx, rdi; BaseAddress
0x180027409  call    cs:__imp_RtlImageDirectoryEntryToData
0x18002740f  mov     r14, rax
0x180027412  test    rax, rax
0x180027415  jz      short loc_180027446
0x180027417  mov     eax, [rsp+68h+Size]
0x18002741e  test    eax, eax
0x180027420  jz      short loc_180027446
0x180027422  mov     [rsp+68h+var_40], r14
0x180027427  mov     r8d, [r14+0Ch]; Rva
0x18002742b  test    r8d, r8d
0x18002742e  jz      short loc_180027446
0x180027430  cmp     [r14], esi
0x180027433  jz      short loc_180027446
0x180027435  cmp     [r14+8], esi
0x180027439  jnz     short loc_180027446
0x18002743b  cmp     eax, 28h ; '('
0x18002743e  jb      short loc_18002744D
0x180027440  cmp     [r14+20h], esi
0x180027444  jz      short loc_18002744D
0x180027446  xor     ebx, ebx
0x180027448  jmp     loc_180027568
0x18002744d  test    r15b, r15b
0x180027450  jz      short loc_180027458
0x180027452  lea     rax, [rdi+r8]
0x180027456  jmp     short loc_180027467
0x180027458  xor     r9d, r9d; SectionHeader
0x18002745b  mov     rdx, rdi; BaseAddress
0x18002745e  mov     rcx, r12; NtHeader
0x180027461  call    cs:__imp_RtlImageRvaToVa
0x180027467  mov     r8d, 0Ch
0x18002746d  lea     rdx, aMscoreeDll_0; "mscoree.dll"
0x180027474  mov     rcx, rax
0x180027477  call    cs:__imp__o__memicmp
0x18002747d  test    eax, eax
0x18002747f  jz      short loc_180027487
0x180027481  xor     ebx, ebx
0x180027483  mov     [rsp+68h+var_48], ebx
0x180027487  test    ebx, ebx
0x180027489  jz      loc_18002756C
0x18002748f  mov     eax, 10Bh
0x180027494  cmp     [r12+18h], ax
0x18002749a  jnz     short loc_1800274D8
0x18002749c  test    r15b, r15b
0x18002749f  jz      short loc_1800274A9
0x1800274a1  mov     eax, [r14]
0x1800274a4  add     rax, rdi
0x1800274a7  jmp     short loc_1800274BB
0x1800274a9  xor     r9d, r9d; SectionHeader
0x1800274ac  mov     r8d, [r14]; Rva
0x1800274af  mov     rdx, rdi; BaseAddress
0x1800274b2  mov     rcx, r12; NtHeader
0x1800274b5  call    cs:__imp_RtlImageRvaToVa
0x1800274bb  mov     r8d, [rax]
0x1800274be  test    r8d, r8d
0x1800274c1  js      short loc_180027446
0x1800274c3  cmp     dword ptr [rax+4], 0
0x1800274c7  jnz     loc_180027446
0x1800274cd  test    r15b, r15b
0x1800274d0  jz      short loc_180027529
0x1800274d2  lea     rsi, [rdi+r8]
0x1800274d6  jmp     short loc_180027543
0x1800274d8  mov     eax, 20Bh
0x1800274dd  cmp     [r12+18h], ax
0x1800274e3  jnz     short loc_18002753D
0x1800274e5  test    r15b, r15b
0x1800274e8  jz      short loc_1800274F2
0x1800274ea  mov     eax, [r14]
0x1800274ed  add     rax, rdi
0x1800274f0  jmp     short loc_180027504
0x1800274f2  xor     r9d, r9d; SectionHeader
0x1800274f5  mov     r8d, [r14]; Rva
0x1800274f8  mov     rdx, rdi; BaseAddress
0x1800274fb  mov     rcx, r12; NtHeader
0x1800274fe  call    cs:__imp_RtlImageRvaToVa
0x180027504  mov     rcx, [rax]
0x180027507  test    rcx, rcx
0x18002750a  js      loc_180027446
0x180027510  cmp     qword ptr [rax+8], 0
0x180027515  jnz     loc_180027446
0x18002751b  test    r15b, r15b
0x18002751e  jz      short loc_180027526
0x180027520  lea     rsi, [rcx+rdi]
0x180027524  jmp     short loc_180027543
0x180027526  mov     r8d, [rax]; Rva
0x180027529  xor     r9d, r9d; SectionHeader
0x18002752c  mov     rdx, rdi; BaseAddress
0x18002752f  mov     rcx, r12; NtHeader
0x180027532  call    cs:__imp_RtlImageRvaToVa
0x180027538  mov     rsi, rax
0x18002753b  jmp     short loc_180027543
0x18002753d  xor     ebx, ebx
0x18002753f  mov     [rsp+68h+var_48], ebx
0x180027543  test    ebx, ebx
0x180027545  jz      short loc_18002756C
0x180027547  mov     rcx, [rsi+2]
0x18002754b  sub     rcx, cs:qword_18002F1B0
0x180027552  jnz     short loc_180027560
0x180027554  mov     ecx, [rsi+0Ah]
0x180027557  mov     eax, cs:dword_18002F1B8
0x18002755d  sub     rcx, rax
0x180027560  xor     eax, eax
0x180027562  test    rcx, rcx
0x180027565  cmovnz  ebx, eax
0x180027568  mov     [rsp+68h+var_48], ebx
0x18002756c  jmp     short loc_180027574
0x18002756e  xor     ebx, ebx
0x180027570  mov     [rsp+68h+var_48], ebx
0x180027574  mov     eax, ebx
0x180027576  add     rsp, 38h
0x18002757a  pop     r15
0x18002757c  pop     r14
0x18002757e  pop     r12
0x180027580  pop     rdi
0x180027581  pop     rsi
0x180027582  pop     rbx
0x180027583  retn
```
