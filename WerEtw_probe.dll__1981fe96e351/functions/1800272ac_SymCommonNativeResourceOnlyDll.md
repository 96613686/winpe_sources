# SymCommonNativeResourceOnlyDll

- ea: `0x1800272ac`
- end: `0x1800273a1`
- name: `SymCommonNativeResourceOnlyDll`
- size: `245`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026888`

## callees

- `0x1800272ac`

## import_xrefs

- `ntdll!RtlImageDirectoryEntryToData` at `0x1800272e1`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800272fd`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180027315`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002736e`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800272e1`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800272fd`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180027315`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002736e`

## pseudocode

```c
__int64 __fastcall SymCommonNativeResourceOnlyDll(unsigned int *BaseAddress, BOOLEAN a2)
{
  unsigned int v4; // ebx
  PVOID v5; // r14
  PVOID v6; // rbp
  __int64 v7; // rcx
  _DWORD *v8; // rax
  ULONG v10[10]; // [rsp+20h] [rbp-28h] BYREF
  ULONG v11; // [rsp+60h] [rbp+18h] BYREF
  ULONG Size; // [rsp+68h] [rbp+20h] BYREF

  v10[0] = 0;
  Size = 0;
  v11 = 0;
  v4 = 1;
  v5 = RtlImageDirectoryEntryToData(BaseAddress, a2, 0, v10);
  v6 = RtlImageDirectoryEntryToData(BaseAddress, a2, 1u, &Size);
  if ( !RtlImageDirectoryEntryToData(BaseAddress, a2, 2u, &v11) )
    return 0;
  if ( !v11 )
    return 0;
  if ( v6 )
    return 0;
  if ( Size )
    return 0;
  if ( v5 )
    return 0;
  if ( v10[0] )
    return 0;
  v7 = BaseAddress[15];
  if ( ((*(_WORD *)((char *)BaseAddress + v7 + 24) - 267) & 0xFEFF) != 0
    || *(unsigned int *)((char *)BaseAddress + v7 + 40) )
  {
    return 0;
  }
  else
  {
    v8 = RtlImageDirectoryEntryToData(BaseAddress, a2, 0xEu, &v11);
    if ( v11 == 72 && v8 )
      return *v8 != 72;
  }
  return v4;
}

```

## disassembly

```asm
0x1800272ac  mov     rax, rsp
0x1800272af  mov     [rax+8], rbx
0x1800272b3  mov     [rax+10h], rbp
0x1800272b7  push    rsi
0x1800272b8  push    rdi
0x1800272b9  push    r14
0x1800272bb  sub     rsp, 30h
0x1800272bf  xor     r8d, r8d; Directory
0x1800272c2  mov     dword ptr [rax-28h], 0
0x1800272c9  lea     r9, [rax-28h]; Size
0x1800272cd  mov     dword ptr [rax+20h], 0
0x1800272d4  mov     sil, dl
0x1800272d7  mov     dword ptr [rax+18h], 0
0x1800272de  mov     rdi, rcx
0x1800272e1  call    cs:__imp_RtlImageDirectoryEntryToData
0x1800272e7  mov     ebx, 1
0x1800272ec  lea     r9, [rsp+48h+Size]; Size
0x1800272f1  mov     r8d, ebx; Directory
0x1800272f4  mov     dl, sil; MappedAsImage
0x1800272f7  mov     rcx, rdi; BaseAddress
0x1800272fa  mov     r14, rax
0x1800272fd  call    cs:__imp_RtlImageDirectoryEntryToData
0x180027303  lea     r8d, [rbx+1]; Directory
0x180027307  mov     dl, sil; MappedAsImage
0x18002730a  lea     r9, [rsp+48h+arg_10]; Size
0x18002730f  mov     rcx, rdi; BaseAddress
0x180027312  mov     rbp, rax
0x180027315  call    cs:__imp_RtlImageDirectoryEntryToData
0x18002731b  test    rax, rax
0x18002731e  jz      short loc_18002738A
0x180027320  cmp     [rsp+48h+arg_10], 0
0x180027325  jz      short loc_18002738A
0x180027327  test    rbp, rbp
0x18002732a  jnz     short loc_18002738A
0x18002732c  cmp     [rsp+48h+Size], ebp
0x180027330  jnz     short loc_18002738A
0x180027332  test    r14, r14
0x180027335  jnz     short loc_18002738A
0x180027337  cmp     [rsp+48h+var_28], r14d
0x18002733c  jnz     short loc_18002738A
0x18002733e  mov     ecx, [rdi+3Ch]
0x180027341  mov     edx, 10Bh
0x180027346  movzx   eax, word ptr [rcx+rdi+18h]
0x18002734b  sub     ax, dx
0x18002734e  mov     edx, 0FEFFh
0x180027353  test    dx, ax
0x180027356  jnz     short loc_18002738A
0x180027358  cmp     [rcx+rdi+28h], r14d
0x18002735d  jnz     short loc_18002738A
0x18002735f  lea     r8d, [rbx+0Dh]; Directory
0x180027363  mov     dl, sil; MappedAsImage
0x180027366  lea     r9, [rsp+48h+arg_10]; Size
0x18002736b  mov     rcx, rdi; BaseAddress
0x18002736e  call    cs:__imp_RtlImageDirectoryEntryToData
0x180027374  cmp     [rsp+48h+arg_10], 48h ; 'H'
0x180027379  jnz     short loc_18002738C
0x18002737b  test    rax, rax
0x18002737e  jz      short loc_18002738C
0x180027380  xor     ebx, ebx
0x180027382  cmp     dword ptr [rax], 48h ; 'H'
0x180027385  setnz   bl
0x180027388  jmp     short loc_18002738C
0x18002738a  xor     ebx, ebx
0x18002738c  mov     rbp, [rsp+48h+arg_8]
0x180027391  mov     eax, ebx
0x180027393  mov     rbx, [rsp+48h+arg_0]
0x180027398  add     rsp, 30h
0x18002739c  pop     r14
0x18002739e  pop     rdi
0x18002739f  pop     rsi
0x1800273a0  retn
```
