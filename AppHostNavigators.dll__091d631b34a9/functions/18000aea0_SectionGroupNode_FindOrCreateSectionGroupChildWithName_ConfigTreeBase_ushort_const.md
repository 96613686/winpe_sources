# SectionGroupNode::FindOrCreateSectionGroupChildWithName(ConfigTreeBase *,ushort const *)

- ea: `0x18000aea0`
- end: `0x18000b020`
- name: `?FindOrCreateSectionGroupChildWithName@SectionGroupNode@@QEAAPEAV1@PEAVConfigTreeBase@@PEBG@Z`
- size: `384`
- prototype: `struct SectionGroupNode *(SectionGroupNode *__hidden this, struct ConfigTreeBase *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000acd0`
- `0x1800109c0`

## callees

- `0x180001194`
- `0x180006360`
- `0x180006500`
- `0x1800072d0`
- `0x180007300`
- `0x180009cb8`
- `0x18000a9b8`
- `0x18000aea0`
- `0x180011240`
- `0x180012f3c`
- `0x18001306e`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct SectionGroupNode *__fastcall SectionGroupNode::FindOrCreateSectionGroupChildWithName(
        SectionGroupNode *this,
        struct ConfigTreeBase *a2,
        const unsigned __int16 *a3)
{
  AppHostNameTable *v6; // rbx
  unsigned __int16 *v7; // rsi
  __int64 i; // rax
  _DWORD *v9; // rbx
  _DWORD *v10; // rax
  unsigned __int16 *v12[2]; // [rsp+20h] [rbp-38h] BYREF
  int v13; // [rsp+30h] [rbp-28h]
  void *pExceptionObject; // [rsp+68h] [rbp+10h] BYREF
  _DWORD *v15; // [rsp+78h] [rbp+20h]

  v6 = (AppHostNameTable *)(*(__int64 (__fastcall **)(struct ConfigTreeBase *))(*(_QWORD *)a2 + 16LL))(a2);
  v12[0] = 0;
  v13 = 2;
  v12[1] = (unsigned __int16 *)AppHostNameTable::AddUnaltered(v6, a3);
  AppHostNameTable::AddQualifiedName(v6, a3, 0, (const unsigned __int16 **)v12);
  v7 = v12[0];
  for ( i = TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::QueryFirstKnownChildWithLocalName(
              this,
              v12[0]);
        ;
        i = TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>::QueryNextKnownWithLocalName(v9, v7) )
  {
    v9 = (_DWORD *)i;
    if ( !i )
      break;
    if ( (unsigned __int8)ConfigNodePredicateFunctor::operator()(v12, i) )
      return (struct SectionGroupNode *)v9;
  }
  v10 = operator new(0x60u);
  v9 = v10;
  pExceptionObject = v10;
  if ( v10 )
  {
    memset_0(v10, 0, 0x60u);
    v9[2] = -1;
    v9[3] = 0;
    *((_QWORD *)v9 + 2) = 0;
    *((_QWORD *)v9 + 3) = 0;
    *((_QWORD *)v9 + 4) = 0;
    *((_QWORD *)v9 + 6) = v9 + 10;
    *((_QWORD *)v9 + 5) = v9 + 10;
    *((_QWORD *)v9 + 8) = 0;
    *((_QWORD *)v9 + 7) = 0;
    *((_QWORD *)v9 + 9) = 0;
    *((_QWORD *)v9 + 10) = 0;
    *(_QWORD *)v9 = &SectionGroupNode::`vftable';
    *((_QWORD *)v9 + 11) = 0;
  }
  else
  {
    v9 = 0;
  }
  v15 = v9;
  if ( !v9 )
  {
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  NavigationNodeBase::Initialize((NavigationNodeBase *)v9, a2, a3);
  *((_QWORD *)v9 + 10) = this;
  TagNavigationNode<FileSystemTagNode,FileSystemNode,FileSystemTree>::AddChild(this, v9);
  return (struct SectionGroupNode *)v9;
}

```

## disassembly

```asm
0x18000aea0  mov     [rsp+arg_0], rbx
0x18000aea5  mov     [rsp+arg_10], rbp
0x18000aeaa  push    rsi
0x18000aeab  push    rdi
0x18000aeac  push    r14
0x18000aeae  sub     rsp, 40h
0x18000aeb2  mov     rbp, r8
0x18000aeb5  mov     r14, rdx
0x18000aeb8  mov     rdi, rcx
0x18000aebb  mov     rax, [rdx]
0x18000aebe  mov     rcx, rdx
0x18000aec1  mov     rax, [rax+10h]
0x18000aec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeca  mov     rbx, rax
0x18000aecd  xorps   xmm0, xmm0
0x18000aed0  movdqu  xmmword ptr [rsp+58h+var_38], xmm0
0x18000aed6  mov     [rsp+58h+var_28], 2
0x18000aede  mov     rdx, rbp; unsigned __int16 *
0x18000aee1  mov     rcx, rax; this
0x18000aee4  call    ?AddUnaltered@AppHostNameTable@@QEAAPEBGPEBG@Z; AppHostNameTable::AddUnaltered(ushort const *)
0x18000aee9  mov     [rsp+58h+var_38+8], rax
0x18000aeee  lea     r9, [rsp+58h+var_38]; unsigned __int16 **
0x18000aef3  xor     r8d, r8d; unsigned __int16 **
0x18000aef6  mov     rdx, rbp; unsigned __int16 *
0x18000aef9  mov     rcx, rbx; this
0x18000aefc  call    ?AddQualifiedName@AppHostNameTable@@QEAAXPEBGPEAPEBG1@Z; AppHostNameTable::AddQualifiedName(ushort const *,ushort const * *,ushort const * *)
0x18000af01  mov     rsi, [rsp+58h+var_38]
0x18000af06  mov     rdx, rsi
0x18000af09  mov     rcx, rdi
0x18000af0c  call    ?QueryFirstKnownChildWithLocalName@?$TagNavigationNode@VConfigLocationTagNode@@VConfigLocationNode@@VConfigLocationsTree@@@@AEAAPEAVConfigLocationTagNode@@PEBG@Z; TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::QueryFirstKnownChildWithLocalName(ushort const *)
0x18000af11  mov     rbx, rax
0x18000af14  test    rax, rax
0x18000af17  jz      short loc_18000AF3B
0x18000af19  mov     rdx, rax
0x18000af1c  lea     rcx, [rsp+58h+var_38]
0x18000af21  call    ??RConfigNodePredicateFunctor@@QEAA_NPEAVConfigTagNode@@@Z; ConfigNodePredicateFunctor::operator()(ConfigTagNode *)
0x18000af26  test    al, al
0x18000af28  jnz     loc_18000B00A
0x18000af2e  mov     rdx, rsi
0x18000af31  mov     rcx, rbx
0x18000af34  call    ?QueryNextKnownWithLocalName@?$TagNavigationNode@VConfigTagNode@@VConfigNavigationNode@@VConfigTreeBase@@@@AEAAPEAVConfigTagNode@@PEBG@Z; TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>::QueryNextKnownWithLocalName(ushort const *)
0x18000af39  jmp     short loc_18000AF11
0x18000af3b  mov     esi, 60h ; '`'
0x18000af40  mov     ecx, esi; Size
0x18000af42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000af47  mov     rbx, rax
0x18000af4a  mov     [rsp+58h+pExceptionObject], rax
0x18000af4f  test    rax, rax
0x18000af52  jz      short loc_18000AFC6
0x18000af54  mov     r8d, esi; Size
0x18000af57  xor     edx, edx; Val
0x18000af59  mov     rcx, rax; void *
0x18000af5c  call    memset_0
0x18000af61  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x18000af68  mov     dword ptr [rbx+0Ch], 0
0x18000af6f  mov     qword ptr [rbx+10h], 0
0x18000af77  mov     qword ptr [rbx+18h], 0
0x18000af7f  mov     qword ptr [rbx+20h], 0
0x18000af87  lea     rax, [rbx+28h]
0x18000af8b  mov     [rax+8], rax
0x18000af8f  mov     [rax], rax
0x18000af92  mov     qword ptr [rbx+40h], 0
0x18000af9a  mov     qword ptr [rbx+38h], 0
0x18000afa2  mov     qword ptr [rbx+48h], 0
0x18000afaa  mov     qword ptr [rbx+50h], 0
0x18000afb2  lea     rax, ??_7SectionGroupNode@@6B@; const SectionGroupNode::`vftable'
0x18000afb9  mov     [rbx], rax
0x18000afbc  mov     qword ptr [rbx+58h], 0
0x18000afc4  jmp     short loc_18000AFC8
0x18000afc6  xor     ebx, ebx
0x18000afc8  mov     [rsp+58h+arg_18], rbx
0x18000afcd  test    rbx, rbx
0x18000afd0  jnz     short loc_18000AFEC
0x18000afd2  mov     dword ptr [rsp+58h+pExceptionObject], 8007000Eh
0x18000afda  lea     rdx, _TI1J; pThrowInfo
0x18000afe1  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000afe6  call    _CxxThrowException_0
0x18000afec  mov     r8, rbp; unsigned __int16 *
0x18000afef  mov     rdx, r14; struct NavigationTreeBase *
0x18000aff2  mov     rcx, rbx; this
0x18000aff5  call    ?Initialize@NavigationNodeBase@@IEAAXPEAVNavigationTreeBase@@PEBG@Z; NavigationNodeBase::Initialize(NavigationTreeBase *,ushort const *)
0x18000affa  mov     [rbx+50h], rdi
0x18000affe  mov     rdx, rbx
0x18000b001  mov     rcx, rdi
0x18000b004  call    ?AddChild@?$TagNavigationNode@VFileSystemTagNode@@VFileSystemNode@@VFileSystemTree@@@@QEAAXPEAVFileSystemTagNode@@@Z; TagNavigationNode<FileSystemTagNode,FileSystemNode,FileSystemTree>::AddChild(FileSystemTagNode *)
0x18000b009  nop
0x18000b00a  mov     rax, rbx
0x18000b00d  mov     rbx, [rsp+58h+arg_0]
0x18000b012  mov     rbp, [rsp+58h+arg_10]
0x18000b017  add     rsp, 40h
0x18000b01b  pop     r14
0x18000b01d  pop     rdi
0x18000b01e  pop     rsi
0x18000b01f  retn
```
