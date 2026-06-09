# SectionGroupNode::FindOrCreateSectionDescendantsWithName(ConfigTreeBase *,ushort const *)

- ea: `0x18000acd0`
- end: `0x18000ae99`
- name: `?FindOrCreateSectionDescendantsWithName@SectionGroupNode@@QEAAPEAVSectionNode@@PEAVConfigTreeBase@@PEBG@Z`
- size: `457`
- prototype: `struct SectionNode *__fastcall(SectionGroupNode *__hidden this, struct ConfigTreeBase *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180010b64`
- `0x180011910`

## callees

- `0x180001194`
- `0x180006360`
- `0x180006500`
- `0x1800072d0`
- `0x180007300`
- `0x180007344`
- `0x180009cb8`
- `0x18000a9b8`
- `0x18000acd0`
- `0x18000aea0`
- `0x180011240`
- `0x180012f3c`
- `0x18001306e`
- `0x180014010`

## import_xrefs

- `msvcrt!wcschr` at `0x18000ad01`
- `msvcrt!wcschr` at `0x18000ad45`
- `msvcrt!wcschr` at `0x18000ad01`
- `msvcrt!wcschr` at `0x18000ad45`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct SectionNode *__fastcall SectionGroupNode::FindOrCreateSectionDescendantsWithName(
        SectionGroupNode *this,
        struct ConfigTreeBase *a2,
        wchar_t *a3)
{
  wchar_t *v3; // rdi
  wchar_t *i; // rax
  AppHostNameTable *v7; // rax
  const unsigned __int16 **v8; // r9
  bool v9; // zf
  __int64 (__fastcall *v10)(struct ConfigTreeBase *); // rax
  AppHostNameTable *v11; // rbx
  unsigned __int16 *v12; // r15
  __int64 j; // rax
  __int64 v14; // rbx
  wchar_t *v15; // rax
  unsigned __int16 *v17[2]; // [rsp+30h] [rbp-20h] BYREF
  int v18; // [rsp+40h] [rbp-10h]
  unsigned __int16 *v19; // [rsp+80h] [rbp+30h] BYREF
  wchar_t *Str; // [rsp+90h] [rbp+40h] BYREF

  Str = a3;
  v3 = a3;
  for ( i = wcschr(a3, 0x2Fu); ; i = wcschr(Str, 0x2Fu) )
  {
    v9 = i == 0;
    v10 = *(__int64 (__fastcall **)(struct ConfigTreeBase *))(*(_QWORD *)a2 + 16LL);
    if ( v9 )
      break;
    v19 = 0;
    v7 = (AppHostNameTable *)v10(a2);
    AppHostNameTable::TryConsumeAndAtomizeSegment(
      v7,
      (const unsigned __int16 **)&Str,
      (const unsigned __int16 **)&v19,
      v8,
      0);
    this = SectionGroupNode::FindOrCreateSectionGroupChildWithName(this, a2, v19);
    v3 = Str;
  }
  v11 = (AppHostNameTable *)v10(a2);
  v17[0] = 0;
  v18 = 3;
  v17[1] = (unsigned __int16 *)AppHostNameTable::AddUnaltered(v11, v3);
  AppHostNameTable::AddQualifiedName(v11, v3, 0, (const unsigned __int16 **)v17);
  v12 = v17[0];
  for ( j = TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::QueryFirstKnownChildWithLocalName(
              this,
              v17[0]);
        ;
        j = TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>::QueryNextKnownWithLocalName(v14, v12) )
  {
    v14 = j;
    if ( !j )
      break;
    if ( (unsigned __int8)ConfigNodePredicateFunctor::operator()(v17, j) )
      return (struct SectionNode *)v14;
  }
  v15 = (wchar_t *)operator new(0x70u);
  v14 = (__int64)v15;
  Str = v15;
  if ( v15 )
  {
    memset_0(v15, 0, 0x70u);
    *(_DWORD *)(v14 + 8) = -1;
    *(_DWORD *)(v14 + 12) = 0;
    *(_QWORD *)(v14 + 16) = 0;
    *(_QWORD *)(v14 + 24) = 0;
    *(_QWORD *)(v14 + 32) = 0;
    *(_QWORD *)(v14 + 48) = v14 + 40;
    *(_QWORD *)(v14 + 40) = v14 + 40;
    *(_QWORD *)(v14 + 64) = 0;
    *(_QWORD *)(v14 + 56) = 0;
    *(_QWORD *)(v14 + 72) = 0;
    *(_QWORD *)(v14 + 80) = 0;
    *(_QWORD *)(v14 + 88) = 0;
    *(_QWORD *)v14 = &SectionNode::`vftable';
    *(_QWORD *)(v14 + 96) = 0;
    *(_QWORD *)(v14 + 104) = 0;
  }
  else
  {
    v14 = 0;
  }
  v19 = (unsigned __int16 *)v14;
  if ( !v14 )
  {
    LODWORD(Str) = -2147024882;
    throw (long *)&Str;
  }
  NavigationNodeBase::Initialize((NavigationNodeBase *)v14, a2, v3);
  *(_QWORD *)(v14 + 80) = this;
  TagNavigationNode<FileSystemTagNode,FileSystemNode,FileSystemTree>::AddChild(this, v14);
  return (struct SectionNode *)v14;
}

```

## disassembly

```asm
0x18000acd0  mov     [rsp-28h+arg_8], rbx
0x18000acd5  mov     [rsp-28h+arg_18], rsi
0x18000acda  mov     [rsp-28h+Str], r8
0x18000acdf  push    rbp
0x18000ace0  push    rdi
0x18000ace1  push    r12
0x18000ace3  push    r14
0x18000ace5  push    r15
0x18000ace7  mov     rbp, rsp
0x18000acea  sub     rsp, 50h
0x18000acee  mov     rdi, r8
0x18000acf1  mov     r14, rdx
0x18000acf4  mov     rsi, rcx
0x18000acf7  mov     ebx, 2Fh ; '/'
0x18000acfc  mov     edx, ebx; Ch
0x18000acfe  mov     rcx, r8; Str
0x18000ad01  call    cs:__imp_wcschr
0x18000ad07  xor     r12d, r12d
0x18000ad0a  jmp     short loc_18000AD4B
0x18000ad0c  mov     [rbp+arg_0], r12
0x18000ad10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad15  mov     [rsp+50h+var_30], r12; unsigned __int16 **
0x18000ad1a  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x18000ad1e  lea     rdx, [rbp+Str]; unsigned __int16 **
0x18000ad22  mov     rcx, rax; this
0x18000ad25  call    ?TryConsumeAndAtomizeSegment@AppHostNameTable@@QEAA_NPEAPEBG000@Z; AppHostNameTable::TryConsumeAndAtomizeSegment(ushort const * *,ushort const * *,ushort const * *,ushort const * *)
0x18000ad2a  mov     r8, [rbp+arg_0]; unsigned __int16 *
0x18000ad2e  mov     rdx, r14; struct ConfigTreeBase *
0x18000ad31  mov     rcx, rsi; this
0x18000ad34  call    ?FindOrCreateSectionGroupChildWithName@SectionGroupNode@@QEAAPEAV1@PEAVConfigTreeBase@@PEBG@Z; SectionGroupNode::FindOrCreateSectionGroupChildWithName(ConfigTreeBase *,ushort const *)
0x18000ad39  mov     rsi, rax
0x18000ad3c  mov     edx, ebx; Ch
0x18000ad3e  mov     rdi, [rbp+Str]
0x18000ad42  mov     rcx, rdi; Str
0x18000ad45  call    cs:__imp_wcschr
0x18000ad4b  mov     rcx, r14
0x18000ad4e  test    rax, rax
0x18000ad51  mov     rax, [r14]
0x18000ad54  mov     rax, [rax+10h]
0x18000ad58  jnz     short loc_18000AD0C
0x18000ad5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad5f  mov     rbx, rax
0x18000ad62  xorps   xmm0, xmm0
0x18000ad65  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18000ad6a  mov     [rbp+var_10], 3
0x18000ad71  mov     rdx, rdi; unsigned __int16 *
0x18000ad74  mov     rcx, rax; this
0x18000ad77  call    ?AddUnaltered@AppHostNameTable@@QEAAPEBGPEBG@Z; AppHostNameTable::AddUnaltered(ushort const *)
0x18000ad7c  mov     [rbp+var_20+8], rax
0x18000ad80  lea     r9, [rbp+var_20]; unsigned __int16 **
0x18000ad84  xor     r8d, r8d; unsigned __int16 **
0x18000ad87  mov     rdx, rdi; unsigned __int16 *
0x18000ad8a  mov     rcx, rbx; this
0x18000ad8d  call    ?AddQualifiedName@AppHostNameTable@@QEAAXPEBGPEAPEBG1@Z; AppHostNameTable::AddQualifiedName(ushort const *,ushort const * *,ushort const * *)
0x18000ad92  mov     r15, [rbp+var_20]
0x18000ad96  mov     rdx, r15
0x18000ad99  mov     rcx, rsi
0x18000ad9c  call    ?QueryFirstKnownChildWithLocalName@?$TagNavigationNode@VConfigLocationTagNode@@VConfigLocationNode@@VConfigLocationsTree@@@@AEAAPEAVConfigLocationTagNode@@PEBG@Z; TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::QueryFirstKnownChildWithLocalName(ushort const *)
0x18000ada1  mov     rbx, rax
0x18000ada4  test    rax, rax
0x18000ada7  jz      short loc_18000ADCA
0x18000ada9  mov     rdx, rax
0x18000adac  lea     rcx, [rbp+var_20]
0x18000adb0  call    ??RConfigNodePredicateFunctor@@QEAA_NPEAVConfigTagNode@@@Z; ConfigNodePredicateFunctor::operator()(ConfigTagNode *)
0x18000adb5  test    al, al
0x18000adb7  jnz     loc_18000AE7D
0x18000adbd  mov     rdx, r15
0x18000adc0  mov     rcx, rbx
0x18000adc3  call    ?QueryNextKnownWithLocalName@?$TagNavigationNode@VConfigTagNode@@VConfigNavigationNode@@VConfigTreeBase@@@@AEAAPEAVConfigTagNode@@PEBG@Z; TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>::QueryNextKnownWithLocalName(ushort const *)
0x18000adc8  jmp     short loc_18000ADA1
0x18000adca  mov     r15d, 70h ; 'p'
0x18000add0  mov     ecx, r15d; Size
0x18000add3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000add8  mov     rbx, rax
0x18000addb  mov     [rbp+Str], rax
0x18000addf  test    rax, rax
0x18000ade2  jz      short loc_18000AE3B
0x18000ade4  mov     r8d, r15d; Size
0x18000ade7  xor     edx, edx; Val
0x18000ade9  mov     rcx, rax; void *
0x18000adec  call    memset_0
0x18000adf1  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x18000adf8  mov     [rbx+0Ch], r12d
0x18000adfc  mov     [rbx+10h], r12
0x18000ae00  mov     [rbx+18h], r12
0x18000ae04  mov     [rbx+20h], r12
0x18000ae08  lea     rax, [rbx+28h]
0x18000ae0c  mov     [rax+8], rax
0x18000ae10  mov     [rax], rax
0x18000ae13  mov     [rbx+40h], r12
0x18000ae17  mov     [rbx+38h], r12
0x18000ae1b  mov     [rbx+48h], r12
0x18000ae1f  mov     [rbx+50h], r12
0x18000ae23  mov     [rbx+58h], r12
0x18000ae27  lea     rax, ??_7SectionNode@@6B@; const SectionNode::`vftable'
0x18000ae2e  mov     [rbx], rax
0x18000ae31  mov     [rbx+60h], r12
0x18000ae35  mov     [rbx+68h], r12
0x18000ae39  jmp     short loc_18000AE3E
0x18000ae3b  mov     rbx, r12
0x18000ae3e  mov     [rbp+arg_0], rbx
0x18000ae42  test    rbx, rbx
0x18000ae45  jnz     short loc_18000AE5F
0x18000ae47  mov     dword ptr [rbp+Str], 8007000Eh
0x18000ae4e  lea     rdx, _TI1J; pThrowInfo
0x18000ae55  lea     rcx, [rbp+Str]; pExceptionObject
0x18000ae59  call    _CxxThrowException_0
0x18000ae5f  mov     r8, rdi; unsigned __int16 *
0x18000ae62  mov     rdx, r14; struct NavigationTreeBase *
0x18000ae65  mov     rcx, rbx; this
0x18000ae68  call    ?Initialize@NavigationNodeBase@@IEAAXPEAVNavigationTreeBase@@PEBG@Z; NavigationNodeBase::Initialize(NavigationTreeBase *,ushort const *)
0x18000ae6d  mov     [rbx+50h], rsi
0x18000ae71  mov     rdx, rbx
0x18000ae74  mov     rcx, rsi
0x18000ae77  call    ?AddChild@?$TagNavigationNode@VFileSystemTagNode@@VFileSystemNode@@VFileSystemTree@@@@QEAAXPEAVFileSystemTagNode@@@Z; TagNavigationNode<FileSystemTagNode,FileSystemNode,FileSystemTree>::AddChild(FileSystemTagNode *)
0x18000ae7c  nop
0x18000ae7d  mov     rax, rbx
0x18000ae80  lea     r11, [rsp+50h+var_s0]
0x18000ae85  mov     rbx, [r11+38h]
0x18000ae89  mov     rsi, [r11+48h]
0x18000ae8d  mov     rsp, r11
0x18000ae90  pop     r15
0x18000ae92  pop     r14
0x18000ae94  pop     r12
0x18000ae96  pop     rdi
0x18000ae97  pop     rbp
0x18000ae98  retn
```
