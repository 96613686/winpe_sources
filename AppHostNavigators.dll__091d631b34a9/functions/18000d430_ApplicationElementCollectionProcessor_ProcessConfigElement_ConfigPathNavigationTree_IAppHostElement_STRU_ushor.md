# ApplicationElementCollectionProcessor::ProcessConfigElement(ConfigPathNavigationTree *,IAppHostElement *,STRU &,ushort const *)

- ea: `0x18000d430`
- end: `0x18000d4b7`
- name: `?ProcessConfigElement@ApplicationElementCollectionProcessor@@UEAAXPEAVConfigPathNavigationTree@@PEAUIAppHostElement@@AEAVSTRU@@PEBG@Z`
- size: `135`
- prototype: `void __usercall(ApplicationElementCollectionProcessor *__hidden this@<rcx>, struct ConfigPathNavigationTree *@<rdx>, struct IAppHostElement *@<r8>, struct STRU *@<r9>, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000c8cc`
- `0x18000c9bc`
- `0x18000d430`
- `0x18000d8c4`
- `0x18000d9ac`

## string_xrefs

- `0x18000d475`: `ConfigPathNodeType_VirtualDirectory`

## pseudocode

```c
void __fastcall ApplicationElementCollectionProcessor::ProcessConfigElement(
        ApplicationElementCollectionProcessor *this,
        struct ConfigPathNavigationTree *a2,
        struct IAppHostElement *a3,
        const unsigned __int16 **a4,
        const unsigned __int16 *a5)
{
  struct ConfigPathTagNode *ContextNode; // rax
  ConfigPathTagNode *v9; // rax
  int v10; // [rsp+20h] [rbp-18h] BYREF
  const wchar_t *v11; // [rsp+28h] [rbp-10h]
  struct ConfigPathTagNode *v12; // [rsp+58h] [rbp+20h] BYREF

  v12 = 0;
  if ( !ConfigPathNavigationTree::TryGetVDirMappingOwner(a2, a4[1], &v12) )
  {
    ContextNode = ApplicationElementCollectionProcessor::GetContextNode(this, a2);
    v11 = L"ConfigPathNodeType_VirtualDirectory";
    v10 = 7;
    v9 = (ConfigPathTagNode *)ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(ContextNode, a2, a5, &v10);
    ConfigPathTagNode::TrySetAssociatedVDirSetPhysicalPath(v9, a2, a3);
  }
}

```

## disassembly

```asm
0x18000d430  mov     rax, rsp
0x18000d433  mov     [rax+8], rbx
0x18000d437  mov     [rax+10h], rsi
0x18000d43b  push    rdi
0x18000d43c  sub     rsp, 30h
0x18000d440  mov     rbx, rdx
0x18000d443  mov     qword ptr [rax+20h], 0
0x18000d44b  mov     rdx, [r9+8]; unsigned __int16 *
0x18000d44f  mov     rdi, r8
0x18000d452  mov     rsi, rcx
0x18000d455  lea     r8, [rax+20h]; struct ConfigPathTagNode **
0x18000d459  mov     rcx, rbx; this
0x18000d45c  call    ?TryGetVDirMappingOwner@ConfigPathNavigationTree@@QEAA_NPEBGPEAPEAVConfigPathTagNode@@@Z; ConfigPathNavigationTree::TryGetVDirMappingOwner(ushort const *,ConfigPathTagNode * *)
0x18000d461  test    al, al
0x18000d463  jnz     short loc_18000D4A7
0x18000d465  mov     rdx, rbx; struct ConfigPathNavigationTree *
0x18000d468  mov     rcx, rsi; this
0x18000d46b  call    ?GetContextNode@ApplicationElementCollectionProcessor@@QEAAPEAVConfigPathTagNode@@PEAVConfigPathNavigationTree@@@Z; ApplicationElementCollectionProcessor::GetContextNode(ConfigPathNavigationTree *)
0x18000d470  mov     r8, [rsp+38h+arg_20]
0x18000d475  lea     rcx, aConfigpathnode_2; "ConfigPathNodeType_VirtualDirectory"
0x18000d47c  mov     [rsp+38h+var_10], rcx
0x18000d481  lea     r9, [rsp+38h+var_18]
0x18000d486  mov     rcx, rax
0x18000d489  mov     [rsp+38h+var_18], 7
0x18000d491  mov     rdx, rbx
0x18000d494  call    ?GetOrCreateInstanceAtRelativePath@ConfigPathTagNode@@QEAAPEAV1@PEAVConfigPathNavigationTree@@PEBGAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z; ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(ConfigPathNavigationTree *,ushort const *,NamedEnum<ConfigPathNodeType> &)
0x18000d499  mov     r8, rdi; struct IAppHostElement *
0x18000d49c  mov     rdx, rbx; struct ConfigPathNavigationTree *
0x18000d49f  mov     rcx, rax; this
0x18000d4a2  call    ?TrySetAssociatedVDirSetPhysicalPath@ConfigPathTagNode@@QEAA_NPEAVConfigPathNavigationTree@@PEAUIAppHostElement@@@Z; ConfigPathTagNode::TrySetAssociatedVDirSetPhysicalPath(ConfigPathNavigationTree *,IAppHostElement *)
0x18000d4a7  mov     rbx, [rsp+38h+arg_0]
0x18000d4ac  mov     rsi, [rsp+38h+arg_8]
0x18000d4b1  add     rsp, 30h
0x18000d4b5  pop     rdi
0x18000d4b6  retn
```
