# ConfigLocationTagNode::CreateNodeAtRelativePath(ConfigLocationsTree *,ushort const *)

- ea: `0x180009e80`
- end: `0x180009ff2`
- name: `?CreateNodeAtRelativePath@ConfigLocationTagNode@@UEAAPEAV1@PEAVConfigLocationsTree@@PEBG@Z`
- size: `370`
- prototype: `struct ConfigLocationTagNode *(ConfigLocationTagNode *__hidden this, struct ConfigLocationsTree *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180001194`
- `0x180006360`
- `0x180006594`
- `0x180007344`
- `0x180009cb8`
- `0x180009e80`
- `0x180011240`
- `0x180012f3c`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct ConfigLocationTagNode *__fastcall ConfigLocationTagNode::CreateNodeAtRelativePath(
        ConfigLocationTagNode *this,
        struct ConfigLocationsTree *a2,
        const unsigned __int16 *a3)
{
  AppHostNameTable *v6; // rax
  const unsigned __int16 **v7; // r9
  __int64 PreviousKnownWithLocalName; // rbx
  __int64 FirstKnownChildWithLocalName; // rax
  __int64 v10; // rax
  char *v11; // rax
  _QWORD *v12; // rax
  unsigned __int16 *v13; // [rsp+30h] [rbp-10h] BYREF
  char *v14; // [rsp+38h] [rbp-8h]
  const unsigned __int16 *pExceptionObject; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int16 *v16; // [rsp+78h] [rbp+38h] BYREF

  pExceptionObject = a3;
  if ( !*a3 )
    return this;
  v13 = 0;
  v16 = 0;
  v6 = (AppHostNameTable *)(*(__int64 (__fastcall **)(struct ConfigLocationsTree *))(*(_QWORD *)a2 + 16LL))(a2);
  AppHostNameTable::TryConsumeAndAtomizeSegment(v6, &pExceptionObject, (const unsigned __int16 **)&v13, v7, &v16);
  PreviousKnownWithLocalName = 0;
  if ( *((_QWORD *)this + 9) )
  {
    FirstKnownChildWithLocalName = TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::QueryFirstKnownChildWithLocalName(
                                     this,
                                     v16);
    if ( FirstKnownChildWithLocalName )
      PreviousKnownWithLocalName = *(_QWORD *)(FirstKnownChildWithLocalName + 64) - 56LL;
  }
  else
  {
    v10 = *((_QWORD *)this + 4);
    if ( v10 )
    {
      PreviousKnownWithLocalName = *(_QWORD *)(v10 + 48) - 40LL;
      if ( *(unsigned __int16 **)(PreviousKnownWithLocalName + 16) != v16 )
        PreviousKnownWithLocalName = TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::QueryPreviousKnownWithLocalName(
                                       *(_QWORD *)(v10 + 48) - 40LL,
                                       v16);
    }
  }
  if ( !PreviousKnownWithLocalName )
  {
    v11 = (char *)operator new(0x60u);
    PreviousKnownWithLocalName = (__int64)v11;
    v14 = v11;
    if ( v11 )
    {
      *((_DWORD *)v11 + 2) = -1;
      *((_DWORD *)v11 + 3) = 0;
      *((_QWORD *)v11 + 2) = 0;
      *((_QWORD *)v11 + 3) = 0;
      *((_QWORD *)v11 + 4) = 0;
      v12 = v11 + 40;
      v12[1] = v12;
      *v12 = v12;
      *(_QWORD *)(PreviousKnownWithLocalName + 64) = 0;
      *(_QWORD *)(PreviousKnownWithLocalName + 56) = 0;
      *(_QWORD *)(PreviousKnownWithLocalName + 72) = 0;
      *(_QWORD *)(PreviousKnownWithLocalName + 80) = 0;
      *(_QWORD *)PreviousKnownWithLocalName = &ConfigLocationNonRootNode::`vftable';
      *(_QWORD *)(PreviousKnownWithLocalName + 88) = 0;
    }
    else
    {
      PreviousKnownWithLocalName = 0;
    }
    v14 = (char *)PreviousKnownWithLocalName;
    if ( !PreviousKnownWithLocalName )
    {
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
    NavigationNodeBase::Initialize((NavigationNodeBase *)PreviousKnownWithLocalName, a2, v13);
    *(_QWORD *)(PreviousKnownWithLocalName + 88) = this;
    TagNavigationNode<FileSystemTagNode,FileSystemNode,FileSystemTree>::AddChild(this, PreviousKnownWithLocalName);
  }
  return (struct ConfigLocationTagNode *)(*(__int64 (__fastcall **)(__int64, struct ConfigLocationsTree *, const unsigned __int16 *))(*(_QWORD *)PreviousKnownWithLocalName + 104LL))(
                                           PreviousKnownWithLocalName,
                                           a2,
                                           pExceptionObject);
}

```

## disassembly

```asm
0x180009e80  mov     [rsp-18h+arg_0], rbx
0x180009e85  mov     [rsp-18h+arg_8], rsi
0x180009e8a  mov     [rsp-18h+pExceptionObject], r8
0x180009e8f  push    rbp
0x180009e90  push    rdi
0x180009e91  push    r14
0x180009e93  mov     rbp, rsp
0x180009e96  sub     rsp, 40h
0x180009e9a  mov     rsi, rdx
0x180009e9d  mov     rdi, rcx
0x180009ea0  xor     r14d, r14d
0x180009ea3  cmp     [r8], r14w
0x180009ea7  jnz     short loc_180009EB1
0x180009ea9  mov     rax, rcx
0x180009eac  jmp     loc_180009FDF
0x180009eb1  mov     [rbp+var_10], r14
0x180009eb5  mov     [rbp+arg_18], r14
0x180009eb9  mov     rax, [rdx]
0x180009ebc  mov     rcx, rsi
0x180009ebf  mov     rax, [rax+10h]
0x180009ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ec8  lea     rcx, [rbp+arg_18]
0x180009ecc  mov     [rsp+40h+var_20], rcx; unsigned __int16 **
0x180009ed1  lea     r8, [rbp+var_10]; unsigned __int16 **
0x180009ed5  lea     rdx, [rbp+pExceptionObject]; unsigned __int16 **
0x180009ed9  mov     rcx, rax; this
0x180009edc  call    ?TryConsumeAndAtomizeSegment@AppHostNameTable@@QEAA_NPEAPEBG000@Z; AppHostNameTable::TryConsumeAndAtomizeSegment(ushort const * *,ushort const * *,ushort const * *,ushort const * *)
0x180009ee1  mov     rdx, [rbp+arg_18]
0x180009ee5  mov     rbx, r14
0x180009ee8  cmp     [rdi+48h], r14
0x180009eec  jz      short loc_180009F05
0x180009eee  mov     rcx, rdi
0x180009ef1  call    ?QueryFirstKnownChildWithLocalName@?$TagNavigationNode@VConfigLocationTagNode@@VConfigLocationNode@@VConfigLocationsTree@@@@AEAAPEAVConfigLocationTagNode@@PEBG@Z; TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::QueryFirstKnownChildWithLocalName(ushort const *)
0x180009ef6  test    rax, rax
0x180009ef9  jz      short loc_180009F27
0x180009efb  mov     rbx, [rax+40h]
0x180009eff  sub     rbx, 38h ; '8'
0x180009f03  jmp     short loc_180009F27
0x180009f05  mov     rax, [rdi+20h]
0x180009f09  test    rax, rax
0x180009f0c  jz      short loc_180009F27
0x180009f0e  mov     rbx, [rax+30h]
0x180009f12  add     rbx, 0FFFFFFFFFFFFFFD8h
0x180009f16  cmp     [rbx+10h], rdx
0x180009f1a  jz      short loc_180009F27
0x180009f1c  mov     rcx, rbx
0x180009f1f  call    ?QueryPreviousKnownWithLocalName@?$TagNavigationNode@VConfigLocationTagNode@@VConfigLocationNode@@VConfigLocationsTree@@@@AEAAPEAVConfigLocationTagNode@@PEBG@Z; TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::QueryPreviousKnownWithLocalName(ushort const *)
0x180009f24  mov     rbx, rax
0x180009f27  test    rbx, rbx
0x180009f2a  jnz     loc_180009FC9
0x180009f30  lea     ecx, [rbx+60h]; Size
0x180009f33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009f38  mov     rbx, rax
0x180009f3b  mov     [rbp+var_8], rax
0x180009f3f  test    rax, rax
0x180009f42  jz      short loc_180009F86
0x180009f44  mov     dword ptr [rax+8], 0FFFFFFFFh
0x180009f4b  mov     [rax+0Ch], r14d
0x180009f4f  mov     [rax+10h], r14
0x180009f53  mov     [rax+18h], r14
0x180009f57  mov     [rax+20h], r14
0x180009f5b  add     rax, 28h ; '('
0x180009f5f  mov     [rax+8], rax
0x180009f63  mov     [rax], rax
0x180009f66  mov     [rbx+40h], r14
0x180009f6a  mov     [rbx+38h], r14
0x180009f6e  mov     [rbx+48h], r14
0x180009f72  mov     [rbx+50h], r14
0x180009f76  lea     rax, ??_7ConfigLocationNonRootNode@@6B@; const ConfigLocationNonRootNode::`vftable'
0x180009f7d  mov     [rbx], rax
0x180009f80  mov     [rbx+58h], r14
0x180009f84  jmp     short loc_180009F89
0x180009f86  mov     rbx, r14
0x180009f89  mov     [rbp+var_8], rbx
0x180009f8d  test    rbx, rbx
0x180009f90  jnz     short loc_180009FAA
0x180009f92  mov     dword ptr [rbp+pExceptionObject], 8007000Eh
0x180009f99  lea     rdx, _TI1J; pThrowInfo
0x180009fa0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009fa4  call    _CxxThrowException_0
0x180009faa  mov     r8, [rbp+var_10]; unsigned __int16 *
0x180009fae  mov     rdx, rsi; struct NavigationTreeBase *
0x180009fb1  mov     rcx, rbx; this
0x180009fb4  call    ?Initialize@NavigationNodeBase@@IEAAXPEAVNavigationTreeBase@@PEBG@Z; NavigationNodeBase::Initialize(NavigationTreeBase *,ushort const *)
0x180009fb9  mov     [rbx+58h], rdi
0x180009fbd  mov     rdx, rbx
0x180009fc0  mov     rcx, rdi
0x180009fc3  call    ?AddChild@?$TagNavigationNode@VFileSystemTagNode@@VFileSystemNode@@VFileSystemTree@@@@QEAAXPEAVFileSystemTagNode@@@Z; TagNavigationNode<FileSystemTagNode,FileSystemNode,FileSystemTree>::AddChild(FileSystemTagNode *)
0x180009fc8  nop
0x180009fc9  mov     rax, [rbx]
0x180009fcc  mov     r8, [rbp+pExceptionObject]
0x180009fd0  mov     rdx, rsi
0x180009fd3  mov     rcx, rbx
0x180009fd6  mov     rax, [rax+68h]
0x180009fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fdf  mov     rbx, [rsp+40h+arg_0]
0x180009fe4  mov     rsi, [rsp+40h+arg_8]
0x180009fe9  add     rsp, 40h
0x180009fed  pop     r14
0x180009fef  pop     rdi
0x180009ff0  pop     rbp
0x180009ff1  retn
```
