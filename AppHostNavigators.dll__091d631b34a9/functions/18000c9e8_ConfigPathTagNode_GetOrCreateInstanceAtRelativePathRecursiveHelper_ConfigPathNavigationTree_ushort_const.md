# ConfigPathTagNode::GetOrCreateInstanceAtRelativePathRecursiveHelper(ConfigPathNavigationTree *,ushort const *)

- ea: `0x18000c9e8`
- end: `0x18000cad9`
- name: `?GetOrCreateInstanceAtRelativePathRecursiveHelper@ConfigPathTagNode@@AEAAPEAV1@PEAVConfigPathNavigationTree@@PEBG@Z`
- size: `241`
- prototype: `struct ConfigPathTagNode *__fastcall(ConfigPathTagNode *this, struct ConfigPathNavigationTree *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000c9bc`
- `0x18000c9e8`

## callees

- `0x180001194`
- `0x180004288`
- `0x180007344`
- `0x18000c3b0`
- `0x18000c470`
- `0x18000c9e8`
- `0x18000da84`
- `0x180011240`
- `0x180014010`

## string_xrefs

- `0x18000ca94`: `ConfigPathNodeType_Location`

## pseudocode

```c
struct ConfigPathTagNode *__fastcall ConfigPathTagNode::GetOrCreateInstanceAtRelativePathRecursiveHelper(
        ConfigPathTagNode *this,
        struct ConfigPathNavigationTree *a2,
        unsigned __int16 *a3)
{
  ConfigPathTagNode *v5; // rbx
  AppHostNameTable *v6; // rax
  const unsigned __int16 **v7; // r9
  ConfigPathTagNode *v9; // rax
  ConfigPathTagNode *v10; // [rsp+30h] [rbp-20h] BYREF
  int v11; // [rsp+38h] [rbp-18h] BYREF
  const wchar_t *v12; // [rsp+40h] [rbp-10h]
  unsigned __int16 *v13; // [rsp+78h] [rbp+28h] BYREF
  unsigned __int16 *v14; // [rsp+80h] [rbp+30h] BYREF
  unsigned __int16 *v15; // [rsp+88h] [rbp+38h] BYREF

  v14 = a3;
  v5 = 0;
  v15 = 0;
  v13 = 0;
  v6 = (AppHostNameTable *)(*(__int64 (__fastcall **)(struct ConfigPathNavigationTree *))(*(_QWORD *)a2 + 16LL))(a2);
  if ( !AppHostNameTable::TryConsumeAndAtomizeSegment(
          v6,
          (const unsigned __int16 **)&v14,
          (const unsigned __int16 **)&v15,
          v7,
          (const unsigned __int16 **)&v13) )
    return this;
  v10 = 0;
  if ( (unsigned __int8)TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::TryGetLastChildWithLocalName<ConfigPathTagNode>(
                          this,
                          v13,
                          &v10) )
  {
    v5 = v10;
  }
  else
  {
    v9 = (ConfigPathTagNode *)operator new(0x88u);
    v10 = v9;
    if ( v9 )
      v5 = ConfigPathTagNode::ConfigPathTagNode(v9);
    v10 = v5;
    NavigationNodeBase::Initialize(v5, a2, v15);
    *((_QWORD *)v5 + 15) = this;
    v11 = 10;
    v12 = L"ConfigPathNodeType_Location";
    ConfigPathTagNode::TrySetConfigPathNodeType(v5, &v11);
    TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::AddChild(this, v5);
  }
  return ConfigPathTagNode::GetOrCreateInstanceAtRelativePathRecursiveHelper(v5, a2, v14);
}

```

## disassembly

```asm
0x18000c9e8  mov     [rsp-18h+arg_0], rbx
0x18000c9ed  mov     [rsp-18h+arg_10], r8
0x18000c9f2  push    rbp
0x18000c9f3  push    rsi
0x18000c9f4  push    rdi
0x18000c9f5  mov     rbp, rsp
0x18000c9f8  sub     rsp, 50h
0x18000c9fc  mov     rsi, rdx
0x18000c9ff  mov     rdi, rcx
0x18000ca02  xor     ebx, ebx
0x18000ca04  mov     [rbp+arg_18], rbx
0x18000ca08  mov     [rbp+arg_8], rbx
0x18000ca0c  mov     rax, [rdx]
0x18000ca0f  mov     rcx, rdx
0x18000ca12  mov     rax, [rax+10h]
0x18000ca16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca1b  lea     rcx, [rbp+arg_8]
0x18000ca1f  mov     [rsp+50h+var_30], rcx; unsigned __int16 **
0x18000ca24  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x18000ca28  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x18000ca2c  mov     rcx, rax; this
0x18000ca2f  call    ?TryConsumeAndAtomizeSegment@AppHostNameTable@@QEAA_NPEAPEBG000@Z; AppHostNameTable::TryConsumeAndAtomizeSegment(ushort const * *,ushort const * *,ushort const * *,ushort const * *)
0x18000ca34  test    al, al
0x18000ca36  jnz     short loc_18000CA40
0x18000ca38  mov     rax, rdi
0x18000ca3b  jmp     loc_18000CACC
0x18000ca40  mov     [rbp+var_20], rbx
0x18000ca44  lea     r8, [rbp+var_20]
0x18000ca48  mov     rdx, [rbp+arg_8]
0x18000ca4c  mov     rcx, rdi
0x18000ca4f  call    ??$TryGetLastChildWithLocalName@VConfigPathTagNode@@@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@QEAA_NPEBGPEAPEAVConfigPathTagNode@@@Z; TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::TryGetLastChildWithLocalName<ConfigPathTagNode>(ushort const *,ConfigPathTagNode * *)
0x18000ca54  test    al, al
0x18000ca56  jnz     short loc_18000CAB9
0x18000ca58  mov     ecx, 88h; Size
0x18000ca5d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ca62  mov     [rbp+var_20], rax
0x18000ca66  test    rax, rax
0x18000ca69  jz      short loc_18000CA76
0x18000ca6b  mov     rcx, rax; this
0x18000ca6e  call    ??0ConfigPathTagNode@@IEAA@XZ; ConfigPathTagNode::ConfigPathTagNode(void)
0x18000ca73  mov     rbx, rax
0x18000ca76  mov     [rbp+var_20], rbx
0x18000ca7a  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x18000ca7e  mov     rdx, rsi; struct NavigationTreeBase *
0x18000ca81  mov     rcx, rbx; this
0x18000ca84  call    ?Initialize@NavigationNodeBase@@IEAAXPEAVNavigationTreeBase@@PEBG@Z; NavigationNodeBase::Initialize(NavigationTreeBase *,ushort const *)
0x18000ca89  mov     [rbx+78h], rdi
0x18000ca8d  mov     [rbp+var_18], 0Ah
0x18000ca94  lea     rax, aConfigpathnode_6; "ConfigPathNodeType_Location"
0x18000ca9b  mov     [rbp+var_10], rax
0x18000ca9f  lea     rdx, [rbp+var_18]
0x18000caa3  mov     rcx, rbx
0x18000caa6  call    ?TrySetConfigPathNodeType@ConfigPathTagNode@@IEAA_NAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z; ConfigPathTagNode::TrySetConfigPathNodeType(NamedEnum<ConfigPathNodeType> &)
0x18000caab  mov     rdx, rbx
0x18000caae  mov     rcx, rdi
0x18000cab1  call    ?AddChild@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@QEAAXPEAVConfigPathTagNode@@@Z; TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::AddChild(ConfigPathTagNode *)
0x18000cab6  nop
0x18000cab7  jmp     short loc_18000CABD
0x18000cab9  mov     rbx, [rbp+var_20]
0x18000cabd  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x18000cac1  mov     rdx, rsi; struct ConfigPathNavigationTree *
0x18000cac4  mov     rcx, rbx; this
0x18000cac7  call    ?GetOrCreateInstanceAtRelativePathRecursiveHelper@ConfigPathTagNode@@AEAAPEAV1@PEAVConfigPathNavigationTree@@PEBG@Z; ConfigPathTagNode::GetOrCreateInstanceAtRelativePathRecursiveHelper(ConfigPathNavigationTree *,ushort const *)
0x18000cacc  mov     rbx, [rsp+50h+arg_0]
0x18000cad1  add     rsp, 50h
0x18000cad5  pop     rdi
0x18000cad6  pop     rsi
0x18000cad7  pop     rbp
0x18000cad8  retn
```
