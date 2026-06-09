# SymCommonTlbImpManagedDll

- ea: `0x180035ba8`
- end: `0x180035db3`
- name: `SymCommonTlbImpManagedDll`
- size: `523`
- prototype: `__int64 __fastcall(PVOID BaseAddress, PIMAGE_NT_HEADERS NtHeader, BOOLEAN MappedAsImage)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800350b0`

## callees

- `0x180035ba8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x180035c89`
- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x180035c89`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180035bdc`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180035c0f`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180035bdc`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180035c0f`
- `ntdll!RtlImageRvaToVa` at `0x180035c6d`
- `ntdll!RtlImageRvaToVa` at `0x180035ccd`
- `ntdll!RtlImageRvaToVa` at `0x180035d20`
- `ntdll!RtlImageRvaToVa` at `0x180035d5a`
- `ntdll!RtlImageRvaToVa` at `0x180035c6d`
- `ntdll!RtlImageRvaToVa` at `0x180035ccd`
- `ntdll!RtlImageRvaToVa` at `0x180035d20`
- `ntdll!RtlImageRvaToVa` at `0x180035d5a`

## string_xrefs

- `0x180035c7f`: `mscoree.dll`

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
0x180035ba8  mov     rax, rsp
0x180035bab  push    rbx
0x180035bac  push    rsi
0x180035bad  push    rdi
0x180035bae  push    r12
0x180035bb0  push    r14
0x180035bb2  push    r15
0x180035bb4  sub     rsp, 38h
0x180035bb8  mov     r15b, r8b
0x180035bbb  mov     r12, rdx
0x180035bbe  mov     rdi, rcx
0x180035bc1  mov     ebx, 1
0x180035bc6  mov     dword ptr [rax+20h], 0
0x180035bcd  xor     r14d, r14d
0x180035bd0  xor     esi, esi
0x180035bd2  xor     r8d, r8d; Directory
0x180035bd5  lea     r9, [rax+20h]; Size
0x180035bd9  mov     dl, r15b; MappedAsImage
0x180035bdc  call    cs:__imp_RtlImageDirectoryEntryToData
0x180035be3  nop     dword ptr [rax+rax+00h]
0x180035be8  test    rax, rax
0x180035beb  jnz     loc_180035C99
0x180035bf1  cmp     [rsp+68h+Size], eax
0x180035bf8  jnz     loc_180035C99
0x180035bfe  mov     r8d, ebx; Directory
0x180035c01  lea     r9, [rsp+68h+Size]; Size
0x180035c09  mov     dl, r15b; MappedAsImage
0x180035c0c  mov     rcx, rdi; BaseAddress
0x180035c0f  call    cs:__imp_RtlImageDirectoryEntryToData
0x180035c16  nop     dword ptr [rax+rax+00h]
0x180035c1b  mov     r14, rax
0x180035c1e  test    rax, rax
0x180035c21  jz      short loc_180035C52
0x180035c23  mov     eax, [rsp+68h+Size]
0x180035c2a  test    eax, eax
0x180035c2c  jz      short loc_180035C52
0x180035c2e  mov     [rsp+68h+var_40], r14
0x180035c33  mov     r8d, [r14+0Ch]; Rva
0x180035c37  test    r8d, r8d
0x180035c3a  jz      short loc_180035C52
0x180035c3c  cmp     [r14], esi
0x180035c3f  jz      short loc_180035C52
0x180035c41  cmp     [r14+8], esi
0x180035c45  jnz     short loc_180035C52
0x180035c47  cmp     eax, 28h ; '('
0x180035c4a  jb      short loc_180035C59
0x180035c4c  cmp     [r14+20h], esi
0x180035c50  jz      short loc_180035C59
0x180035c52  xor     ebx, ebx
0x180035c54  jmp     loc_180035D96
0x180035c59  test    r15b, r15b
0x180035c5c  jz      short loc_180035C64
0x180035c5e  lea     rax, [rdi+r8]
0x180035c62  jmp     short loc_180035C79
0x180035c64  xor     r9d, r9d; SectionHeader
0x180035c67  mov     rdx, rdi; BaseAddress
0x180035c6a  mov     rcx, r12; NtHeader
0x180035c6d  call    cs:__imp_RtlImageRvaToVa
0x180035c74  nop     dword ptr [rax+rax+00h]
0x180035c79  mov     r8d, 0Ch
0x180035c7f  lea     rdx, aMscoreeDll_0; "mscoree.dll"
0x180035c86  mov     rcx, rax
0x180035c89  call    cs:__imp__o__memicmp
0x180035c90  nop     dword ptr [rax+rax+00h]
0x180035c95  test    eax, eax
0x180035c97  jz      short loc_180035C9F
0x180035c99  xor     ebx, ebx
0x180035c9b  mov     [rsp+68h+var_48], ebx
0x180035c9f  test    ebx, ebx
0x180035ca1  jz      loc_180035D9A
0x180035ca7  mov     eax, 10Bh
0x180035cac  cmp     [r12+18h], ax
0x180035cb2  jnz     short loc_180035CFA
0x180035cb4  test    r15b, r15b
0x180035cb7  jz      short loc_180035CC1
0x180035cb9  mov     eax, [r14]
0x180035cbc  add     rax, rdi
0x180035cbf  jmp     short loc_180035CD9
0x180035cc1  xor     r9d, r9d; SectionHeader
0x180035cc4  mov     r8d, [r14]; Rva
0x180035cc7  mov     rdx, rdi; BaseAddress
0x180035cca  mov     rcx, r12; NtHeader
0x180035ccd  call    cs:__imp_RtlImageRvaToVa
0x180035cd4  nop     dword ptr [rax+rax+00h]
0x180035cd9  mov     r8d, [rax]
0x180035cdc  test    r8d, r8d
0x180035cdf  js      loc_180035C52
0x180035ce5  cmp     dword ptr [rax+4], 0
0x180035ce9  jnz     loc_180035C52
0x180035cef  test    r15b, r15b
0x180035cf2  jz      short loc_180035D51
0x180035cf4  lea     rsi, [rdi+r8]
0x180035cf8  jmp     short loc_180035D71
0x180035cfa  mov     eax, 20Bh
0x180035cff  cmp     [r12+18h], ax
0x180035d05  jnz     short loc_180035D6B
0x180035d07  test    r15b, r15b
0x180035d0a  jz      short loc_180035D14
0x180035d0c  mov     eax, [r14]
0x180035d0f  add     rax, rdi
0x180035d12  jmp     short loc_180035D2C
0x180035d14  xor     r9d, r9d; SectionHeader
0x180035d17  mov     r8d, [r14]; Rva
0x180035d1a  mov     rdx, rdi; BaseAddress
0x180035d1d  mov     rcx, r12; NtHeader
0x180035d20  call    cs:__imp_RtlImageRvaToVa
0x180035d27  nop     dword ptr [rax+rax+00h]
0x180035d2c  mov     rcx, [rax]
0x180035d2f  test    rcx, rcx
0x180035d32  js      loc_180035C52
0x180035d38  cmp     qword ptr [rax+8], 0
0x180035d3d  jnz     loc_180035C52
0x180035d43  test    r15b, r15b
0x180035d46  jz      short loc_180035D4E
0x180035d48  lea     rsi, [rcx+rdi]
0x180035d4c  jmp     short loc_180035D71
0x180035d4e  mov     r8d, [rax]; Rva
0x180035d51  xor     r9d, r9d; SectionHeader
0x180035d54  mov     rdx, rdi; BaseAddress
0x180035d57  mov     rcx, r12; NtHeader
0x180035d5a  call    cs:__imp_RtlImageRvaToVa
0x180035d61  nop     dword ptr [rax+rax+00h]
0x180035d66  mov     rsi, rax
0x180035d69  jmp     short loc_180035D71
0x180035d6b  xor     ebx, ebx
0x180035d6d  mov     [rsp+68h+var_48], ebx
0x180035d71  test    ebx, ebx
0x180035d73  jz      short loc_180035D9A
0x180035d75  mov     rcx, [rsi+2]
0x180035d79  sub     rcx, cs:qword_18003FE70
0x180035d80  jnz     short loc_180035D8E
0x180035d82  mov     ecx, [rsi+0Ah]
0x180035d85  mov     eax, cs:dword_18003FE78
0x180035d8b  sub     rcx, rax
0x180035d8e  xor     eax, eax
0x180035d90  test    rcx, rcx
0x180035d93  cmovnz  ebx, eax
0x180035d96  mov     [rsp+68h+var_48], ebx
0x180035d9a  jmp     short loc_180035DA2
0x180035d9c  xor     ebx, ebx
0x180035d9e  mov     [rsp+68h+var_48], ebx
0x180035da2  mov     eax, ebx
0x180035da4  add     rsp, 38h
0x180035da8  pop     r15
0x180035daa  pop     r14
0x180035dac  pop     r12
0x180035dae  pop     rdi
0x180035daf  pop     rsi
0x180035db0  pop     rbx
0x180035db1  retn
```
