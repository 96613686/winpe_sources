# VfsNormalizeNameComponentEx

- ea: `0x14000a5a0`
- end: `0x14000a77c`
- name: `VfsNormalizeNameComponentEx`
- size: `476`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, __int64, __int64, ULONG, int, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140009368`
- `0x140009f94`
- `0x14000a22c`
- `0x14000a5a0`
- `0x14000f124`
- `0x1400107c8`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000a757`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140014f13`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000a757`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140014f13`

## pseudocode

```c
__int64 __fastcall VfsNormalizeNameComponentEx(
        PFLT_INSTANCE Instance,
        __int64 a2,
        __m128i *a3,
        unsigned __int16 a4,
        __m128i *a5,
        __int64 a6,
        ULONG Length,
        int a8,
        PVOID *a9)
{
  __int64 v9; // rbx
  char v12; // si
  unsigned __int16 v14; // dx
  _WORD *v15; // rax
  __int16 v16; // dx
  int DirectoryFileName; // ebx
  PVOID v18; // rdi
  PVOID Entry; // [rsp+38h] [rbp-70h] BYREF
  __int64 v20; // [rsp+40h] [rbp-68h] BYREF
  _WORD v21[4]; // [rsp+48h] [rbp-60h] BYREF
  __int64 v22; // [rsp+50h] [rbp-58h]
  __m128i v23[5]; // [rsp+58h] [rbp-50h] BYREF

  v9 = a4;
  v20 = 0;
  Entry = 0;
  v12 = 0;
  if ( Length < 0x10 )
    return 3221225485LL;
  v23[0] = *a3;
  v23[1] = *a5;
  v14 = _mm_cvtsi128_si32(v23[0]);
  if ( (unsigned __int16)v9 < v14 )
  {
    v15 = (_WORD *)(v9 + v23[0].m128i_i64[1]);
    v22 = v9 + v23[0].m128i_i64[1];
    v16 = v14 - v9;
    v21[0] = v16;
    v21[1] = v16;
  }
  else
  {
    v22 = 0;
    v15 = 0;
    v16 = 0;
  }
  if ( v16 == 2 && *v15 == 92 || !(unsigned __int8)VfsDecodeFileObject(a2, &v20, v21) )
    goto LABEL_14;
  if ( *a9 )
  {
    Entry = *a9;
  }
  else
  {
    DirectoryFileName = VfsCreateNameNormalizationContext(v23, (unsigned __int16)v9, v20 + 152, v20 + 220, &Entry);
    if ( DirectoryFileName < 0 )
      goto LABEL_15;
    v12 = 1;
  }
  DirectoryFileName = VfsExpandTargetComponent(Instance, a6, Length);
  if ( DirectoryFileName == -1073741275 )
LABEL_14:
    DirectoryFileName = VfsQueryDirectoryFileName(Instance, Length);
LABEL_15:
  v18 = Entry;
  if ( Entry && v12 )
  {
    if ( (int)(DirectoryFileName + 0x80000000) < 0 || DirectoryFileName == -1073741809 )
    {
      *a9 = Entry;
    }
    else
    {
      if ( *(_QWORD *)Entry )
        VfsReleaseMappingEntry(*(PVOID *)Entry);
      ExFreeToPagedLookasideList(&stru_14001F900, v18);
    }
  }
  return (unsigned int)DirectoryFileName;
}

```

## disassembly

```asm
0x14000a5a0  mov     rax, rsp
0x14000a5a3  push    rbx
0x14000a5a4  push    rsi
0x14000a5a5  push    rdi
0x14000a5a6  push    r14
0x14000a5a8  sub     rsp, 88h
0x14000a5af  movzx   ebx, r9w
0x14000a5b3  mov     r9, rdx
0x14000a5b6  mov     r14, rcx
0x14000a5b9  mov     dword ptr [rax-74h], 0
0x14000a5c0  mov     qword ptr [rax-68h], 0
0x14000a5c8  mov     qword ptr [rax-70h], 0
0x14000a5d0  xor     sil, sil
0x14000a5d3  mov     [rax-78h], sil
0x14000a5d7  mov     edi, [rsp+0A8h+arg_30]
0x14000a5de  cmp     edi, 10h
0x14000a5e1  jnb     short loc_14000A5F6
0x14000a5e3  mov     eax, 0C000000Dh
0x14000a5e8  add     rsp, 88h
0x14000a5ef  pop     r14
0x14000a5f1  pop     rdi
0x14000a5f2  pop     rsi
0x14000a5f3  pop     rbx
0x14000a5f4  retn
0x14000a5f6  movups  xmm1, xmmword ptr [r8]
0x14000a5fa  movups  [rsp+0A8h+var_50], xmm1
0x14000a5ff  mov     rax, [rsp+0A8h+arg_20]
0x14000a607  movups  xmm0, xmmword ptr [rax]
0x14000a60a  movdqu  [rsp+0A8h+var_40], xmm0
0x14000a610  movd    edx, xmm1
0x14000a614  cmp     bx, dx
0x14000a617  jb      short loc_14000A628
0x14000a619  mov     [rsp+0A8h+var_58], 0
0x14000a622  xor     eax, eax
0x14000a624  xor     edx, edx
0x14000a626  jmp     short loc_14000A642
0x14000a628  mov     rax, qword ptr [rsp+0A8h+var_50+8]
0x14000a62d  add     rax, rbx
0x14000a630  mov     [rsp+0A8h+var_58], rax
0x14000a635  sub     dx, bx
0x14000a638  mov     [rsp+0A8h+var_60], dx
0x14000a63d  mov     [rsp+0A8h+var_5E], dx
0x14000a642  cmp     dx, 2
0x14000a646  jnz     short loc_14000A652
0x14000a648  cmp     word ptr [rax], 5Ch ; '\'
0x14000a64c  jz      loc_14000A6F4
0x14000a652  lea     r8, [rsp+0A8h+var_60]
0x14000a657  lea     rdx, [rsp+0A8h+var_68]
0x14000a65c  mov     rcx, r9
0x14000a65f  call    VfsDecodeFileObject
0x14000a664  test    al, al
0x14000a666  jz      loc_14000A6F4
0x14000a66c  mov     rax, [rsp+0A8h+arg_40]
0x14000a674  mov     rcx, [rax]
0x14000a677  test    rcx, rcx
0x14000a67a  jnz     short loc_14000A6BA
0x14000a67c  mov     r8, [rsp+0A8h+var_68]
0x14000a681  lea     r9, [r8+0DCh]
0x14000a688  add     r8, 98h
0x14000a68f  lea     rax, [rsp+0A8h+Entry]
0x14000a694  mov     qword ptr [rsp+0A8h+Length], rax
0x14000a699  movzx   edx, bx
0x14000a69c  lea     rcx, [rsp+0A8h+var_50]
0x14000a6a1  call    VfsCreateNameNormalizationContext
0x14000a6a6  mov     ebx, eax
0x14000a6a8  mov     [rsp+0A8h+var_74], eax
0x14000a6ac  test    eax, eax
0x14000a6ae  js      short loc_14000A718
0x14000a6b0  mov     sil, 1
0x14000a6b3  mov     [rsp+0A8h+var_78], sil
0x14000a6b8  jmp     short loc_14000A6BF
0x14000a6ba  mov     [rsp+0A8h+Entry], rcx
0x14000a6bf  mov     [rsp+0A8h+var_80], edi; ULONG
0x14000a6c3  mov     rax, [rsp+0A8h+arg_28]
0x14000a6cb  mov     qword ptr [rsp+0A8h+Length], rax; __int64
0x14000a6d0  mov     r9, [rsp+0A8h+Entry]
0x14000a6d5  lea     r8, [rsp+0A8h+var_40]
0x14000a6da  lea     rdx, [rsp+0A8h+var_50]
0x14000a6df  mov     rcx, r14; Instance
0x14000a6e2  call    VfsExpandTargetComponent
0x14000a6e7  mov     ebx, eax
0x14000a6e9  mov     [rsp+0A8h+var_74], eax
0x14000a6ed  cmp     eax, 0C0000225h
0x14000a6f2  jnz     short loc_14000A718
0x14000a6f4  mov     [rsp+0A8h+Length], edi; Length
0x14000a6f8  mov     r9, [rsp+0A8h+arg_28]
0x14000a700  lea     r8, [rsp+0A8h+var_40]
0x14000a705  lea     rdx, [rsp+0A8h+var_50]
0x14000a70a  mov     rcx, r14; Instance
0x14000a70d  call    VfsQueryDirectoryFileName
0x14000a712  mov     ebx, eax
0x14000a714  mov     [rsp+0A8h+var_74], eax
0x14000a718  mov     rdi, [rsp+0A8h+Entry]
0x14000a71d  test    rdi, rdi
0x14000a720  jz      short loc_14000A775
0x14000a722  test    sil, sil
0x14000a725  jz      short loc_14000A775
0x14000a727  mov     ecx, 80000000h
0x14000a72c  lea     eax, [rbx+rcx]
0x14000a72f  test    ecx, eax
0x14000a731  jnz     short loc_14000A765
0x14000a733  cmp     ebx, 0C000000Fh
0x14000a739  jz      short loc_14000A765
0x14000a73b  test    rdi, rdi
0x14000a73e  jz      short loc_14000A775
0x14000a740  mov     rcx, [rdi]; P
0x14000a743  test    rcx, rcx
0x14000a746  jz      short loc_14000A74D
0x14000a748  call    VfsReleaseMappingEntry
0x14000a74d  mov     rdx, rdi; Entry
0x14000a750  lea     rcx, stru_14001F900; Lookaside
0x14000a757  call    cs:__imp_ExFreeToPagedLookasideList
0x14000a75e  nop     dword ptr [rax+rax+00h]
0x14000a763  jmp     short loc_14000A775
0x14000a765  mov     rcx, [rsp+0A8h+arg_40]
0x14000a76d  mov     rax, [rsp+0A8h+Entry]
0x14000a772  mov     [rcx], rax
0x14000a775  mov     eax, ebx
0x14000a777  jmp     loc_14000A5E8
0x140014ec8  push    rbx
0x140014eca  push    rbp
0x140014ecb  sub     rsp, 38h
0x140014ecf  mov     rbp, rdx
0x140014ed2  mov     rbx, [rbp+38h]
0x140014ed6  test    rbx, rbx
0x140014ed9  jz      short loc_140014F2B
0x140014edb  cmp     byte ptr [rbp+30h], 0
0x140014edf  jz      short loc_140014F2B
0x140014ee1  mov     eax, 80000000h
0x140014ee6  mov     ecx, [rbp+34h]
0x140014ee9  add     eax, ecx
0x140014eeb  js      short loc_140014F21
0x140014eed  cmp     ecx, 0C000000Fh
0x140014ef3  jz      short loc_140014F21
0x140014ef5  test    rbx, rbx
0x140014ef8  jz      short loc_140014F2B
0x140014efa  cmp     qword ptr [rbx], 0
0x140014efe  jz      short loc_140014F09
0x140014f00  mov     rcx, [rbx]; P
0x140014f03  call    VfsReleaseMappingEntry
0x140014f08  nop
0x140014f09  mov     rdx, rbx; Entry
0x140014f0c  lea     rcx, stru_14001F900; Lookaside
0x140014f13  call    cs:__imp_ExFreeToPagedLookasideList
0x140014f1a  nop     dword ptr [rax+rax+00h]
0x140014f1f  jmp     short loc_140014F2B
0x140014f21  mov     rax, [rbp+0F0h]
0x140014f28  mov     [rax], rbx
0x140014f2b  add     rsp, 38h
0x140014f2f  pop     rbp
0x140014f30  pop     rbx
0x140014f31  retn
```
