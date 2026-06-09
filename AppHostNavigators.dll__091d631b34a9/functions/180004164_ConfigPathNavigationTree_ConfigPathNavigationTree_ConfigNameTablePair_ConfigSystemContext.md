# ConfigPathNavigationTree::ConfigPathNavigationTree(ConfigNameTablePair *,ConfigSystemContext *)

- ea: `0x180004164`
- end: `0x180004282`
- name: `??0ConfigPathNavigationTree@@QEAA@PEAVConfigNameTablePair@@PEAVConfigSystemContext@@@Z`
- size: `286`
- prototype: `ConfigPathNavigationTree *__fastcall(ConfigPathNavigationTree *__hidden this, struct ConfigNameTablePair *, struct ConfigSystemContext *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180004c04`

## callees

- `0x180004164`
- `0x180004288`
- `0x1800042ec`
- `0x18000da84`
- `0x180011240`
- `0x180012f3c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800041e5`
- `KERNEL32!GetProcessHeap` at `0x1800041e5`
- `KERNEL32!InitializeSRWLock` at `0x1800041d4`
- `KERNEL32!InitializeSRWLock` at `0x1800041d4`
- `KERNEL32!HeapAlloc` at `0x1800041f7`
- `KERNEL32!HeapAlloc` at `0x1800041f7`

## string_xrefs

- `0x18000423d`: `ConfigPathNodeType_Root`

## pseudocode

```c
ConfigPathNavigationTree *__fastcall ConfigPathNavigationTree::ConfigPathNavigationTree(
        ConfigPathNavigationTree *this,
        struct ConfigNameTablePair *a2,
        struct ConfigSystemContext *a3)
{
  _QWORD *v4; // rcx
  NavigationNodeBase *v5; // rdi
  __int64 v6; // r8
  HANDLE ProcessHeap; // rax
  LPVOID v8; // rax
  int v10; // [rsp+20h] [rbp-28h] BYREF
  const wchar_t *v11; // [rsp+28h] [rbp-20h]
  int pExceptionObject; // [rsp+60h] [rbp+18h] BYREF
  char *v13; // [rsp+68h] [rbp+20h]

  NavigationTreeBase::NavigationTreeBase(this, a2);
  *v4 = &ConfigPathNavigationTree::`vftable';
  v5 = (NavigationNodeBase *)(v4 + 3);
  ConfigPathTagNode::ConfigPathTagNode((ConfigPathTagNode *)(v4 + 3));
  *(_QWORD *)v5 = &ConfigPathRootNode::`vftable';
  *((_QWORD *)this + 20) = v6;
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  v13 = (char *)this + 168;
  *((_QWORD *)this + 21) = &HASH_TABLE<VDirMappingOwnerDescriptor,unsigned short const *>::`vftable';
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  InitializeSRWLock((PSRWLOCK)this + 24);
  *((_QWORD *)this + 21) = &VDirMappingOwnerTable::`vftable';
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 8u, 0x80u);
  *((_QWORD *)this + 22) = v8;
  if ( !v8 )
  {
    pExceptionObject = -2147024888;
    throw (long *)&pExceptionObject;
  }
  *((_DWORD *)this + 46) = 16;
  NavigationNodeBase::Initialize(v5, this, &qword_1800181B0);
  *((_QWORD *)v5 + 15) = 0;
  *((_QWORD *)v5 + 16) = &off_18001C1F0;
  v10 = 1;
  v11 = L"ConfigPathNodeType_Root";
  ConfigPathTagNode::TrySetConfigPathNodeType(v5, &v10);
  *((_DWORD *)v5 + 2) = 0;
  return this;
}

```

## disassembly

```asm
0x180004164  mov     [rsp+arg_0], rcx
0x180004169  push    rbx
0x18000416a  push    rsi
0x18000416b  push    rdi
0x18000416c  sub     rsp, 30h
0x180004170  mov     rbx, rcx
0x180004173  call    ??0NavigationTreeBase@@QEAA@PEAVConfigNameTablePair@@@Z; NavigationTreeBase::NavigationTreeBase(ConfigNameTablePair *)
0x180004178  nop
0x180004179  lea     rax, ??_7ConfigPathNavigationTree@@6B@; const ConfigPathNavigationTree::`vftable'
0x180004180  mov     [rcx], rax
0x180004183  lea     rdi, [rcx+18h]
0x180004187  mov     rcx, rdi; this
0x18000418a  call    ??0ConfigPathTagNode@@IEAA@XZ; ConfigPathTagNode::ConfigPathTagNode(void)
0x18000418f  lea     rcx, ??_7ConfigPathRootNode@@6B@; const ConfigPathRootNode::`vftable'
0x180004196  mov     [rdi], rcx
0x180004199  mov     [rbx+0A0h], r8
0x1800041a0  test    r8, r8
0x1800041a3  jz      short loc_1800041AA
0x1800041a5  lock inc dword ptr [r8+8]
0x1800041aa  lea     rsi, [rbx+0A8h]
0x1800041b1  mov     [rsp+48h+arg_18], rsi
0x1800041b6  lea     rax, ??_7?$HASH_TABLE@VVDirMappingOwnerDescriptor@@PEBG@@6B@; const HASH_TABLE<VDirMappingOwnerDescriptor,ushort const *>::`vftable'
0x1800041bd  mov     [rsi], rax
0x1800041c0  mov     qword ptr [rsi+8], 0
0x1800041c8  mov     qword ptr [rsi+10h], 0
0x1800041d0  lea     rcx, [rsi+18h]; SRWLock
0x1800041d4  call    cs:__imp_InitializeSRWLock
0x1800041da  nop
0x1800041db  lea     rax, ??_7VDirMappingOwnerTable@@6B@; const VDirMappingOwnerTable::`vftable'
0x1800041e2  mov     [rsi], rax
0x1800041e5  call    cs:__imp_GetProcessHeap
0x1800041eb  mov     rcx, rax; hHeap
0x1800041ee  mov     edx, 8; dwFlags
0x1800041f3  lea     r8d, [rdx+78h]; dwBytes
0x1800041f7  call    cs:__imp_HeapAlloc
0x1800041fd  mov     [rsi+8], rax
0x180004201  test    rax, rax
0x180004204  jz      short loc_180004268
0x180004206  mov     dword ptr [rsi+10h], 10h
0x18000420d  lea     r8, qword_1800181B0; unsigned __int16 *
0x180004214  mov     rdx, rbx; struct NavigationTreeBase *
0x180004217  mov     rcx, rdi; this
0x18000421a  call    ?Initialize@NavigationNodeBase@@IEAAXPEAVNavigationTreeBase@@PEBG@Z; NavigationNodeBase::Initialize(NavigationTreeBase *,ushort const *)
0x18000421f  mov     qword ptr [rdi+78h], 0
0x180004227  lea     rax, off_18001C1F0
0x18000422e  mov     [rdi+80h], rax
0x180004235  mov     [rsp+48h+var_28], 1
0x18000423d  lea     rax, aConfigpathnode_8; "ConfigPathNodeType_Root"
0x180004244  mov     [rsp+48h+var_20], rax
0x180004249  lea     rdx, [rsp+48h+var_28]
0x18000424e  mov     rcx, rdi
0x180004251  call    ?TrySetConfigPathNodeType@ConfigPathTagNode@@IEAA_NAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z; ConfigPathTagNode::TrySetConfigPathNodeType(NamedEnum<ConfigPathNodeType> &)
0x180004256  mov     dword ptr [rdi+8], 0
0x18000425d  mov     rax, rbx
0x180004260  add     rsp, 30h
0x180004264  pop     rdi
0x180004265  pop     rsi
0x180004266  pop     rbx
0x180004267  retn
0x180004268  mov     [rsp+48h+pExceptionObject], 80070008h
0x180004270  lea     rdx, _TI1J; pThrowInfo
0x180004277  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000427c  call    _CxxThrowException_0
```
