# AslpFileGetVersionBlockImageOnly

- ea: `0x18005844c`
- end: `0x180058721`
- name: `AslpFileGetVersionBlockImageOnly`
- size: `725`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800577cc`

## callees

- `0x1800543c0`
- `0x1800553b8`
- `0x180057380`
- `0x1800580f4`
- `0x18005844c`
- `0x180065150`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18005863c`
- `ntdll!RtlAllocateHeap` at `0x18005863c`
- `ntdll!RtlFreeHeap` at `0x180058709`
- `ntdll!RtlFreeHeap` at `0x180058709`

## string_xrefs

- `0x18005851c`: `AslpFileGetImageResourceDirectoryRoot failed to get resource directory root [%x]`
- `0x180058578`: `AslpFileGetVersionBlockFromResourceRoot failed to get version block from resource directory [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetVersionBlockImageOnly(_QWORD *a1, unsigned __int16 **a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r8
  unsigned __int16 *v8; // rcx
  unsigned int v9; // ebx
  int v10; // eax
  unsigned __int64 v11; // rdx
  int ImageResourceDirectoryRoot; // eax
  const char *v13; // r9
  __int64 v14; // r8
  int VersionBlockFromResourceRoot; // eax
  SIZE_T v16; // r14
  void *v17; // r12
  unsigned __int64 v18; // rax
  char *v19; // rcx
  SIZE_T v20; // r8
  unsigned __int64 v21; // rdx
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v23; // rsi
  unsigned __int16 *v24; // rax
  void *Src; // [rsp+40h] [rbp-48h] BYREF
  __int64 v28; // [rsp+A0h] [rbp+18h] BYREF
  SIZE_T Size; // [rsp+A8h] [rbp+20h] BYREF

  v28 = 0;
  Src = 0;
  Size = 0;
  v7 = *(_QWORD *)(a4 + 64);
  if ( v7 )
  {
    v8 = 0;
    if ( *(_WORD *)(v7 + 2) >= 0x34u )
      v8 = (unsigned __int16 *)(v7 + 40);
    *a2 = v8;
    *a1 = *(_QWORD *)(a4 + 64);
    return 0;
  }
  v10 = AslFileMappingEnsure(a4, a1, 0, a4);
  v9 = v10;
  if ( v10 < 0 )
  {
    AslLogCallPrintf(1, "AslpFileGetVersionBlockImageOnly", 2288, "AslFileMappingEnsure failed [%x]", v10);
    return v9;
  }
  if ( *(_DWORD *)(a4 + 56) != 6 )
    return (unsigned int)-1073741687;
  ImageResourceDirectoryRoot = AslpFileGetImageResourceDirectoryRoot((unsigned __int64 *)&v28, v11, a4);
  v9 = ImageResourceDirectoryRoot;
  if ( ImageResourceDirectoryRoot < 0 )
  {
    if ( (unsigned int)(ImageResourceDirectoryRoot + 1073741687) <= 2 )
      return v9;
    v13 = "AslpFileGetImageResourceDirectoryRoot failed to get resource directory root [%x]";
    v14 = 2315;
LABEL_12:
    AslLogCallPrintf(1, "AslpFileGetVersionBlockImageOnly", v14, v13, v9);
    return v9;
  }
  VersionBlockFromResourceRoot = AslpFileGetVersionBlockFromResourceRoot((unsigned __int16 **)&Src, &Size, v28, a4);
  v9 = VersionBlockFromResourceRoot;
  if ( VersionBlockFromResourceRoot < 0 )
  {
    if ( (unsigned int)(VersionBlockFromResourceRoot + 1073741687) <= 2 )
      return v9;
    v13 = "AslpFileGetVersionBlockFromResourceRoot failed to get version block from resource directory [%x]";
    v14 = 2323;
    goto LABEL_12;
  }
  v16 = Size;
  if ( !Size )
    return (unsigned int)-1073741687;
  v17 = Src;
  if ( !Src )
  {
    AslLogCallPrintf(
      1,
      "AslpFileGetVersionBlockImageOnly",
      2335,
      "AslpFileGetVersionBlockFromResourceRoot returned null version block with status [%x]",
      VersionBlockFromResourceRoot);
    return (unsigned int)-1073741687;
  }
  if ( Size > 0x7FFF )
  {
    AslLogCallPrintf(
      1,
      "AslpFileGetVersionBlockImageOnly",
      2341,
      "AslpFileGetVersionBlockFromResourceRoot returned version block size that is too large");
    return (unsigned int)-1073741687;
  }
  v18 = *(_QWORD *)(a4 + 32);
  if ( (unsigned __int64)Src < v18
    || (v19 = (char *)Src + Size, Src > (char *)Src + Size)
    || (v20 = *(_QWORD *)(a4 + 40), v21 = v20 + v18, (unsigned __int64)Src > v20 + v18)
    || (unsigned __int64)v19 < v18
    || (unsigned __int64)v19 > v21
    || v18 > v21
    || Size > v20 )
  {
    AslLogCallPrintf(1, "AslpFileGetVersionBlockImageOnly", 2350, "Version block out of range");
    return (unsigned int)-1073741687;
  }
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Size);
  v23 = Heap;
  if ( Heap )
  {
    memmove_0(Heap, v17, v16);
    if ( v16 < *v23 )
      *v23 = v16;
    v24 = v23 + 20;
    if ( v23[1] < 0x34u )
      v24 = 0;
    *a2 = v24;
    *a1 = v23;
    *(_QWORD *)(a4 + 64) = v23;
    return 0;
  }
  else
  {
    return (unsigned int)-1073741801;
  }
}

```

## disassembly

```asm
0x18005844c  mov     rax, rsp
0x18005844f  mov     [rax+18h], r8
0x180058453  mov     [rax+8], rcx
0x180058457  push    rbx
0x180058458  push    rsi
0x180058459  push    rdi
0x18005845a  push    r12
0x18005845c  push    r13
0x18005845e  push    r14
0x180058460  push    r15
0x180058462  sub     rsp, 50h
0x180058466  mov     r15, r9
0x180058469  mov     r13, rdx
0x18005846c  mov     rdx, rcx
0x18005846f  xor     edi, edi
0x180058471  mov     [rax+18h], rdi
0x180058475  mov     [rax-48h], rdi
0x180058479  mov     esi, edi
0x18005847b  mov     [rax-50h], rdi
0x18005847f  mov     [rax+20h], rdi
0x180058483  mov     r8, [r9+40h]
0x180058487  test    r8, r8
0x18005848a  jz      short loc_1800584AE
0x18005848c  lea     rax, [r8+28h]
0x180058490  mov     ecx, edi
0x180058492  cmp     word ptr [r8+2], 34h ; '4'
0x180058498  cmovnb  rcx, rax
0x18005849c  mov     [r13+0], rcx
0x1800584a0  mov     rax, [r9+40h]
0x1800584a4  mov     [rdx], rax
0x1800584a7  mov     ebx, edi
0x1800584a9  jmp     loc_1800586F2
0x1800584ae  mov     rcx, r15
0x1800584b1  call    AslFileMappingEnsure
0x1800584b6  mov     ebx, eax
0x1800584b8  test    eax, eax
0x1800584ba  jns     short loc_1800584E3
0x1800584bc  mov     [rsp+88h+var_68], eax
0x1800584c0  lea     r9, aAslfilemapping_1; "AslFileMappingEnsure failed [%x]"
0x1800584c7  mov     r8d, 8F0h
0x1800584cd  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x1800584d4  mov     ecx, 1
0x1800584d9  call    AslLogCallPrintf
0x1800584de  jmp     loc_1800586F2
0x1800584e3  cmp     dword ptr [r15+38h], 6
0x1800584e8  jz      short loc_1800584F4
0x1800584ea  mov     ebx, 0C0000089h
0x1800584ef  jmp     loc_1800586F2
0x1800584f4  mov     r8, r15
0x1800584f7  lea     rcx, [rsp+88h+arg_10]
0x1800584ff  call    AslpFileGetImageResourceDirectoryRoot
0x180058504  mov     ebx, eax
0x180058506  mov     [rsp+88h+var_58], eax
0x18005850a  test    eax, eax
0x18005850c  jns     short loc_180058543
0x18005850e  add     eax, 3FFFFF77h
0x180058513  cmp     eax, 2
0x180058516  jbe     loc_1800586C3
0x18005851c  lea     r9, aAslpfilegetima; "AslpFileGetImageResourceDirectoryRoot f"...
0x180058523  mov     r8d, 90Bh
0x180058529  mov     [rsp+88h+var_68], ebx
0x18005852d  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x180058534  mov     ecx, 1
0x180058539  call    AslLogCallPrintf
0x18005853e  jmp     loc_1800586C3
0x180058543  mov     r9, r15
0x180058546  mov     r8, [rsp+88h+arg_10]
0x18005854e  lea     rdx, [rsp+88h+Size]
0x180058556  lea     rcx, [rsp+88h+Src]
0x18005855b  call    AslpFileGetVersionBlockFromResourceRoot
0x180058560  mov     ebx, eax
0x180058562  mov     [rsp+88h+var_58], eax
0x180058566  test    eax, eax
0x180058568  jns     short loc_180058587
0x18005856a  add     eax, 3FFFFF77h
0x18005856f  cmp     eax, 2
0x180058572  jbe     loc_1800586C3
0x180058578  lea     r9, aAslpfilegetver_6; "AslpFileGetVersionBlockFromResourceRoot"...
0x18005857f  mov     r8d, 913h
0x180058585  jmp     short loc_180058529
0x180058587  mov     r14, [rsp+88h+Size]
0x18005858f  test    r14, r14
0x180058592  jz      loc_1800586BA
0x180058598  mov     r12, [rsp+88h+Src]
0x18005859d  test    r12, r12
0x1800585a0  jnz     short loc_1800585C9
0x1800585a2  mov     [rsp+88h+var_68], ebx
0x1800585a6  lea     r9, aAslpfilegetver; "AslpFileGetVersionBlockFromResourceRoot"...
0x1800585ad  mov     r8d, 91Fh
0x1800585b3  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x1800585ba  lea     ecx, [r12+1]
0x1800585bf  call    AslLogCallPrintf
0x1800585c4  jmp     loc_1800586BA
0x1800585c9  cmp     r14, 7FFFh
0x1800585d0  jbe     short loc_1800585E4
0x1800585d2  lea     r9, aAslpfilegetver_2; "AslpFileGetVersionBlockFromResourceRoot"...
0x1800585d9  mov     r8d, 925h
0x1800585df  jmp     loc_1800586A9
0x1800585e4  mov     rax, [r15+20h]
0x1800585e8  cmp     r12, rax
0x1800585eb  jb      loc_18005869C
0x1800585f1  lea     rcx, [r14+r12]
0x1800585f5  cmp     r12, rcx
0x1800585f8  ja      loc_18005869C
0x1800585fe  mov     r8, [r15+28h]
0x180058602  lea     rdx, [r8+rax]
0x180058606  cmp     r12, rdx
0x180058609  ja      loc_18005869C
0x18005860f  cmp     rcx, rax
0x180058612  jb      loc_18005869C
0x180058618  cmp     rcx, rdx
0x18005861b  ja      short loc_18005869C
0x18005861d  cmp     rax, rdx
0x180058620  ja      short loc_18005869C
0x180058622  cmp     r14, r8
0x180058625  ja      short loc_18005869C
0x180058627  mov     rcx, gs:60h
0x180058630  mov     r8, r14; Size
0x180058633  mov     edx, 8; Flags
0x180058638  mov     rcx, [rcx+30h]; HeapHandle
0x18005863c  call    cs:__imp_RtlAllocateHeap
0x180058642  mov     rsi, rax
0x180058645  mov     [rsp+88h+var_50], rax
0x18005864a  test    rax, rax
0x18005864d  jnz     short loc_180058656
0x18005864f  mov     ebx, 0C0000017h
0x180058654  jmp     short loc_1800586BF
0x180058656  mov     r8, r14; Size
0x180058659  mov     rdx, r12; Src
0x18005865c  mov     rcx, rsi; void *
0x18005865f  call    memmove_0
0x180058664  movzx   eax, word ptr [rsi]
0x180058667  cmp     r14, rax
0x18005866a  jnb     short loc_180058670
0x18005866c  mov     [rsi], r14w
0x180058670  lea     rax, [rsi+28h]
0x180058674  cmp     word ptr [rsi+2], 34h ; '4'
0x180058679  cmovb   rax, rdi
0x18005867d  mov     [r13+0], rax
0x180058681  mov     rax, [rsp+88h+arg_0]
0x180058689  mov     [rax], rsi
0x18005868c  mov     [r15+40h], rsi
0x180058690  mov     rsi, rdi
0x180058693  mov     [rsp+88h+var_50], rdi
0x180058698  mov     ebx, edi
0x18005869a  jmp     short loc_1800586BF
0x18005869c  lea     r9, aVersionBlockOu; "Version block out of range"
0x1800586a3  mov     r8d, 92Eh
0x1800586a9  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x1800586b0  mov     ecx, 1
0x1800586b5  call    AslLogCallPrintf
0x1800586ba  mov     ebx, 0C0000089h
0x1800586bf  mov     [rsp+88h+var_58], ebx
0x1800586c3  jmp     short loc_1800586F2
0x1800586c5  mov     ebx, eax
0x1800586c7  mov     [rsp+88h+var_58], eax
0x1800586cb  mov     [rsp+88h+var_68], eax
0x1800586cf  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x1800586d6  mov     r8d, 966h
0x1800586dc  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x1800586e3  mov     ecx, 1
0x1800586e8  call    AslLogCallPrintf
0x1800586ed  mov     rsi, [rsp+88h+var_50]
0x1800586f2  test    rsi, rsi
0x1800586f5  jz      short loc_18005870F
0x1800586f7  mov     rcx, gs:60h
0x180058700  mov     r8, rsi; P
0x180058703  xor     edx, edx; Flags
0x180058705  mov     rcx, [rcx+30h]; HeapHandle
0x180058709  call    cs:__imp_RtlFreeHeap
0x18005870f  mov     eax, ebx
0x180058711  add     rsp, 50h
0x180058715  pop     r15
0x180058717  pop     r14
0x180058719  pop     r13
0x18005871b  pop     r12
0x18005871d  pop     rdi
0x18005871e  pop     rsi
0x18005871f  pop     rbx
0x180058720  retn
0x180068e9d  push    rbp
0x180068e9f  sub     rsp, 30h
0x180068ea3  mov     rbp, rdx
0x180068ea6  mov     rax, [rcx]
0x180068ea9  xor     ecx, ecx
0x180068eab  cmp     dword ptr [rax], 0C00000FDh
0x180068eb1  setnz   cl
0x180068eb4  mov     [rbp+34h], ecx
0x180068eb7  mov     eax, [rbp+34h]
0x180068eba  add     rsp, 30h
0x180068ebe  pop     rbp
0x180068ebf  retn
```
