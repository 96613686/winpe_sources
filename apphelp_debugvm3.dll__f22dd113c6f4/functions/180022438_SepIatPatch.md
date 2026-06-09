# SepIatPatch

- ea: `0x180022438`
- end: `0x1800225d7`
- name: `SepIatPatch`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180020624`

## callees

- `0x18000f114`
- `0x180022438`
- `0x1800366dc`

## import_xrefs

- `ntdll!RtlImageDirectoryEntryToData` at `0x18002255e`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002255e`
- `ntdll!NtProtectVirtualMemory` at `0x180022598`
- `ntdll!NtProtectVirtualMemory` at `0x180022598`

## pseudocode

```c
__int64 __fastcall SepIatPatch(__int64 a1, _QWORD *a2, __int64 a3)
{
  PVOID *v6; // r14
  int v7; // ebx
  NTSTATUS v8; // edi
  PVOID v10; // rax
  ULONG Size; // [rsp+90h] [rbp+8h] BYREF
  _QWORD *v12; // [rsp+98h] [rbp+10h]
  __int64 v13; // [rsp+A0h] [rbp+18h]

  v13 = a3;
  v12 = a2;
  Size = 0;
  v6 = (PVOID *)(a1 + 8);
  v7 = 1;
  if ( *(_QWORD *)(a1 + 8)
    || (v10 = RtlImageDirectoryEntryToData(*(PVOID *)a1, 1u, 0xCu, &Size), (*v6 = v10) == 0)
    || (*(_QWORD *)(a1 + 16) = Size,
        v8 = NtProtectVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, v6, (SIZE_T *)(a1 + 16), 0x40u, (PULONG)(a1 + 24)),
        v8 >= 0) )
  {
    if ( a2 < *v6 || a2 >= (_QWORD *)((char *)*v6 + *(_QWORD *)(a1 + 16)) )
      v7 = LUPatch(a2, a3);
    else
      *a2 = a3;
    return v7 == 0 ? 0xC0000017 : 0;
  }
  else
  {
    *v6 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    AslLogCallPrintf(1, "SepIatPatch", 149, "Failed to make IAT r/w");
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180022438  mov     rax, rsp
0x18002243b  mov     [rax+18h], r8
0x18002243f  mov     [rax+10h], rdx
0x180022443  push    rbx
0x180022444  push    rsi
0x180022445  push    rdi
0x180022446  push    r12
0x180022448  push    r13
0x18002244a  push    r14
0x18002244c  push    r15
0x18002244e  sub     rsp, 50h
0x180022452  mov     r12, r8
0x180022455  mov     rsi, rdx
0x180022458  mov     r15, rcx
0x18002245b  mov     dword ptr [rax+8], 0
0x180022462  lea     r14, [rcx+8]
0x180022466  mov     ebx, 1
0x18002246b  cmp     qword ptr [r14], 0
0x18002246f  jz      loc_18002254B
0x180022475  mov     [rsp+88h+var_48], 0
0x18002247d  mov     rcx, [r14]
0x180022480  cmp     rsi, rcx
0x180022483  jb      short loc_180022497
0x180022485  add     rcx, [r15+10h]
0x180022489  cmp     rsi, rcx
0x18002248c  jnb     short loc_180022497
0x18002248e  mov     [rsi], r12
0x180022491  mov     [rsp+88h+var_48], ebx
0x180022495  jmp     short loc_1800224A8
0x180022497  mov     rdx, r12
0x18002249a  mov     rcx, rsi
0x18002249d  call    LUPatch
0x1800224a2  mov     ebx, eax
0x1800224a4  mov     [rsp+88h+var_48], eax
0x1800224a8  jmp     loc_18002252D
0x1800224ad  mov     dword ptr [rsp+88h+OldAccessProtection], eax
0x1800224b1  lea     r9, aException08lxP_1; "Exception %08lx patching IAT: retrying"
0x1800224b8  mov     r8d, 0C0h
0x1800224be  lea     rdx, aSepiatpatch; "SepIatPatch"
0x1800224c5  mov     ecx, 2
0x1800224ca  call    AslLogCallPrintf
0x1800224cf  nop
0x1800224d0  mov     rdx, [rsp+88h+arg_10]
0x1800224d8  mov     rcx, [rsp+88h+arg_8]
0x1800224e0  call    LUPatch
0x1800224e5  mov     ebx, eax
0x1800224e7  mov     [rsp+88h+var_48], eax
0x1800224eb  jmp     short loc_18002252D
0x1800224ed  mov     [rsp+88h+var_58], eax
0x1800224f1  mov     rax, [rsp+88h+arg_10]
0x1800224f9  mov     [rsp+88h+var_60], rax
0x1800224fe  mov     rax, [rsp+88h+arg_8]
0x180022506  mov     [rsp+88h+OldAccessProtection], rax
0x18002250b  lea     r9, aLupatchPPFaile; "LUPatch(%p, %p) failed %08lx"
0x180022512  mov     r8d, 0C5h
0x180022518  lea     rdx, aSepiatpatch; "SepIatPatch"
0x18002251f  mov     ecx, 1
0x180022524  call    AslLogCallPrintf
0x180022529  mov     ebx, [rsp+88h+var_48]
0x18002252d  neg     ebx
0x18002252f  sbb     edi, edi
0x180022531  not     edi
0x180022533  and     edi, 0C0000017h
0x180022539  mov     eax, edi
0x18002253b  add     rsp, 50h
0x18002253f  pop     r15
0x180022541  pop     r14
0x180022543  pop     r13
0x180022545  pop     r12
0x180022547  pop     rdi
0x180022548  pop     rsi
0x180022549  pop     rbx
0x18002254a  retn
0x18002254b  mov     r8d, 0Ch; Directory
0x180022551  lea     r9, [rsp+88h+Size]; Size
0x180022559  mov     dl, bl; MappedAsImage
0x18002255b  mov     rcx, [rcx]; BaseAddress
0x18002255e  call    cs:__imp_RtlImageDirectoryEntryToData
0x180022564  mov     [r14], rax
0x180022567  test    rax, rax
0x18002256a  jz      loc_180022475
0x180022570  lea     r13, [r15+10h]
0x180022574  mov     eax, [rsp+88h+Size]
0x18002257b  mov     [r13+0], rax
0x18002257f  lea     rax, [r15+18h]
0x180022583  mov     [rsp+88h+OldAccessProtection], rax; OldAccessProtection
0x180022588  mov     r9d, 40h ; '@'; NewAccessProtection
0x18002258e  mov     r8, r13; NumberOfBytesToProtect
0x180022591  mov     rdx, r14; BaseAddress
0x180022594  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180022598  call    cs:__imp_NtProtectVirtualMemory
0x18002259e  mov     edi, eax
0x1800225a0  test    eax, eax
0x1800225a2  jns     loc_180022475
0x1800225a8  mov     qword ptr [r14], 0
0x1800225af  mov     qword ptr [r13+0], 0
0x1800225b7  lea     r9, aFailedToMakeIa; "Failed to make IAT r/w"
0x1800225be  mov     r8d, 95h
0x1800225c4  lea     rdx, aSepiatpatch; "SepIatPatch"
0x1800225cb  mov     ecx, ebx
0x1800225cd  call    AslLogCallPrintf
0x1800225d2  jmp     loc_180022539
```
