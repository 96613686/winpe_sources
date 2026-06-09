# SymCommonTlbImpManagedDll

- ea: `0x18002b9a0`
- end: `0x18002bb8e`
- name: `SymCommonTlbImpManagedDll`
- size: `494`
- prototype: `__int64 __fastcall(PVOID BaseAddress, PIMAGE_NT_HEADERS NtHeader)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a840`

## callees

- `0x18002b9a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x18002baf6`
- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x18002baf6`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002b9d4`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002b9fa`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002b9d4`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002b9fa`
- `ntdll!RtlImageRvaToVa` at `0x18002bacf`
- `ntdll!RtlImageRvaToVa` at `0x18002bae0`
- `ntdll!RtlImageRvaToVa` at `0x18002bb34`
- `ntdll!RtlImageRvaToVa` at `0x18002bb68`
- `ntdll!RtlImageRvaToVa` at `0x18002bacf`
- `ntdll!RtlImageRvaToVa` at `0x18002bae0`
- `ntdll!RtlImageRvaToVa` at `0x18002bb34`
- `ntdll!RtlImageRvaToVa` at `0x18002bb68`

## string_xrefs

- `0x18002baec`: `mscoree.dll`

## pseudocode

```c
__int64 __fastcall SymCommonTlbImpManagedDll(char *BaseAddress, PIMAGE_NT_HEADERS NtHeader, BOOLEAN a3)
{
  unsigned int v6; // ebx
  ULONG *v7; // rdi
  __int64 v8; // r8
  char *v9; // rax
  WORD Magic; // ax
  char *v11; // rax
  __int64 v12; // r8
  char *v13; // r15
  __int64 v14; // rcx
  __int64 v15; // r8
  char *v16; // rax
  ULONG Size; // [rsp+88h] [rbp+20h] BYREF

  v6 = 1;
  Size = 0;
  if ( RtlImageDirectoryEntryToData(BaseAddress, a3, 0, &Size) )
    return 0;
  if ( Size )
    return 0;
  v7 = (ULONG *)RtlImageDirectoryEntryToData(BaseAddress, a3, 1u, &Size);
  if ( !v7 )
    return 0;
  if ( !Size )
    return 0;
  v8 = v7[3];
  if ( !(_DWORD)v8 || !*v7 || v7[2] || Size >= 0x28 && v7[8] )
    return 0;
  if ( a3 )
    v9 = &BaseAddress[v8];
  else
    v9 = (char *)RtlImageRvaToVa(NtHeader, BaseAddress, v8, 0);
  if ( (unsigned int)_o__memicmp(v9, "mscoree.dll", 12) )
    v6 = 0;
  if ( v6 )
  {
    Magic = NtHeader->OptionalHeader.Magic;
    if ( Magic == 267 )
    {
      if ( a3 )
        v11 = &BaseAddress[*v7];
      else
        v11 = (char *)RtlImageRvaToVa(NtHeader, BaseAddress, *v7, 0);
      v12 = *(unsigned int *)v11;
      if ( (int)v12 >= 0 && !*((_DWORD *)v11 + 1) )
      {
        if ( a3 )
        {
          v13 = &BaseAddress[v12];
LABEL_21:
          v14 = *(_QWORD *)(v13 + 2) - 0x4D6C6C44726F435FLL;
          if ( *(_QWORD *)(v13 + 2) == 0x4D6C6C44726F435FLL )
            v14 = *(unsigned int *)(v13 + 10) - 7235937LL;
          if ( v14 )
            return 0;
          return v6;
        }
        goto LABEL_38;
      }
    }
    else if ( Magic == 523 )
    {
      v15 = *v7;
      v16 = a3 ? &BaseAddress[v15] : (char *)RtlImageRvaToVa(NtHeader, BaseAddress, v15, 0);
      v12 = *(_QWORD *)v16;
      if ( *(__int64 *)v16 >= 0 && !*((_QWORD *)v16 + 1) )
      {
        if ( a3 )
        {
          v13 = &BaseAddress[v12];
          goto LABEL_21;
        }
LABEL_38:
        v13 = (char *)RtlImageRvaToVa(NtHeader, BaseAddress, v12, 0);
        goto LABEL_21;
      }
    }
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18002b9a0  mov     rax, rsp
0x18002b9a3  push    rbx
0x18002b9a4  push    rsi
0x18002b9a5  push    rdi
0x18002b9a6  push    r13
0x18002b9a8  push    r14
0x18002b9aa  push    r15
0x18002b9ac  sub     rsp, 38h
0x18002b9b0  movzx   esi, r8b
0x18002b9b4  mov     r13, rdx
0x18002b9b7  mov     r14, rcx
0x18002b9ba  mov     ebx, 1
0x18002b9bf  mov     dword ptr [rax+20h], 0
0x18002b9c6  xor     r15d, r15d
0x18002b9c9  xor     r8d, r8d; Directory
0x18002b9cc  lea     r9, [rax+20h]; Size
0x18002b9d0  movzx   edx, sil; MappedAsImage
0x18002b9d4  call    cs:__imp_RtlImageDirectoryEntryToData
0x18002b9da  test    rax, rax
0x18002b9dd  jnz     short loc_18002BA21
0x18002b9df  cmp     [rsp+68h+Size], eax
0x18002b9e6  jnz     short loc_18002BA21
0x18002b9e8  mov     r8d, ebx; Directory
0x18002b9eb  lea     r9, [rsp+68h+Size]; Size
0x18002b9f3  movzx   edx, sil; MappedAsImage
0x18002b9f7  mov     rcx, r14; BaseAddress
0x18002b9fa  call    cs:__imp_RtlImageDirectoryEntryToData
0x18002ba00  mov     rdi, rax
0x18002ba03  test    rax, rax
0x18002ba06  jz      short loc_18002BA21
0x18002ba08  mov     eax, [rsp+68h+Size]
0x18002ba0f  test    eax, eax
0x18002ba11  jz      short loc_18002BA21
0x18002ba13  mov     [rsp+68h+var_40], rdi
0x18002ba18  mov     r8d, [rdi+0Ch]; Rva
0x18002ba1c  test    r8d, r8d
0x18002ba1f  jnz     short loc_18002BA2C
0x18002ba21  xor     ebx, ebx
0x18002ba23  mov     [rsp+68h+var_48], ebx
0x18002ba27  jmp     loc_18002BB76
0x18002ba2c  cmp     dword ptr [rdi], 0
0x18002ba2f  jz      short loc_18002BA21
0x18002ba31  cmp     dword ptr [rdi+8], 0
0x18002ba35  jnz     short loc_18002BA21
0x18002ba37  cmp     eax, 28h ; '('
0x18002ba3a  jb      short loc_18002BA42
0x18002ba3c  cmp     dword ptr [rdi+20h], 0
0x18002ba40  jnz     short loc_18002BA21
0x18002ba42  test    sil, sil
0x18002ba45  jz      loc_18002BAD7
0x18002ba4b  lea     rax, [r14+r8]
0x18002ba4f  jmp     loc_18002BAE6
0x18002ba54  test    ebx, ebx
0x18002ba56  jz      loc_18002BB76
0x18002ba5c  movzx   eax, word ptr [r13+18h]
0x18002ba61  mov     ecx, 10Bh
0x18002ba66  cmp     ax, cx
0x18002ba69  jnz     loc_18002BB0F
0x18002ba6f  test    sil, sil
0x18002ba72  jz      short loc_18002BAC3
0x18002ba74  mov     eax, [rdi]
0x18002ba76  add     rax, r14
0x18002ba79  mov     r8d, [rax]; Rva
0x18002ba7c  test    r8d, r8d
0x18002ba7f  js      short loc_18002BA21
0x18002ba81  cmp     dword ptr [rax+4], 0
0x18002ba85  jnz     short loc_18002BA21
0x18002ba87  test    sil, sil
0x18002ba8a  jz      loc_18002BB5F
0x18002ba90  lea     r15, [r14+r8]
0x18002ba94  test    ebx, ebx
0x18002ba96  jz      loc_18002BB76
0x18002ba9c  mov     rcx, [r15+2]
0x18002baa0  sub     rcx, cs:qword_18009E398
0x18002baa7  jnz     short loc_18002BAB6
0x18002baa9  mov     ecx, [r15+0Ah]
0x18002baad  mov     eax, cs:dword_18009E3A0
0x18002bab3  sub     rcx, rax
0x18002bab6  xor     eax, eax
0x18002bab8  test    rcx, rcx
0x18002babb  cmovnz  ebx, eax
0x18002babe  jmp     loc_18002BA23
0x18002bac3  xor     r9d, r9d; SectionHeader
0x18002bac6  mov     r8d, [rdi]; Rva
0x18002bac9  mov     rdx, r14; BaseAddress
0x18002bacc  mov     rcx, r13; NtHeader
0x18002bacf  call    cs:__imp_RtlImageRvaToVa
0x18002bad5  jmp     short loc_18002BA79
0x18002bad7  xor     r9d, r9d; SectionHeader
0x18002bada  mov     rdx, r14; BaseAddress
0x18002badd  mov     rcx, r13; NtHeader
0x18002bae0  call    cs:__imp_RtlImageRvaToVa
0x18002bae6  mov     r8d, 0Ch
0x18002baec  lea     rdx, aMscoreeDll_0; "mscoree.dll"
0x18002baf3  mov     rcx, rax
0x18002baf6  call    cs:__imp__o__memicmp
0x18002bafc  test    eax, eax
0x18002bafe  jz      loc_18002BA54
0x18002bb04  xor     ebx, ebx
0x18002bb06  mov     [rsp+68h+var_48], ebx
0x18002bb0a  jmp     loc_18002BA54
0x18002bb0f  mov     ecx, 20Bh
0x18002bb14  cmp     ax, cx
0x18002bb17  jnz     loc_18002BA21
0x18002bb1d  mov     r8d, [rdi]; Rva
0x18002bb20  test    sil, sil
0x18002bb23  jz      short loc_18002BB2B
0x18002bb25  lea     rax, [r14+r8]
0x18002bb29  jmp     short loc_18002BB3A
0x18002bb2b  xor     r9d, r9d; SectionHeader
0x18002bb2e  mov     rdx, r14; BaseAddress
0x18002bb31  mov     rcx, r13; NtHeader
0x18002bb34  call    cs:__imp_RtlImageRvaToVa
0x18002bb3a  mov     r8, [rax]
0x18002bb3d  test    r8, r8
0x18002bb40  js      loc_18002BA21
0x18002bb46  cmp     qword ptr [rax+8], 0
0x18002bb4b  jnz     loc_18002BA21
0x18002bb51  test    sil, sil
0x18002bb54  jz      short loc_18002BB5F
0x18002bb56  lea     r15, [r8+r14]
0x18002bb5a  jmp     loc_18002BA94
0x18002bb5f  xor     r9d, r9d; SectionHeader
0x18002bb62  mov     rdx, r14; BaseAddress
0x18002bb65  mov     rcx, r13; NtHeader
0x18002bb68  call    cs:__imp_RtlImageRvaToVa
0x18002bb6e  mov     r15, rax
0x18002bb71  jmp     loc_18002BA94
0x18002bb76  jmp     short loc_18002BB7E
0x18002bb78  xor     ebx, ebx
0x18002bb7a  mov     [rsp+68h+var_48], ebx
0x18002bb7e  mov     eax, ebx
0x18002bb80  add     rsp, 38h
0x18002bb84  pop     r15
0x18002bb86  pop     r14
0x18002bb88  pop     r13
0x18002bb8a  pop     rdi
0x18002bb8b  pop     rsi
0x18002bb8c  pop     rbx
0x18002bb8d  retn
```
