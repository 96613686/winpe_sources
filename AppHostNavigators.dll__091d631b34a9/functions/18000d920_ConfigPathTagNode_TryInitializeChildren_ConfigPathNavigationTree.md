# ConfigPathTagNode::TryInitializeChildren(ConfigPathNavigationTree *)

- ea: `0x18000d920`
- end: `0x18000d9a4`
- name: `?TryInitializeChildren@ConfigPathTagNode@@EEAA_NPEAVConfigPathNavigationTree@@@Z`
- size: `132`
- prototype: `bool __fastcall(ConfigPathTagNode *__hidden this, struct ConfigPathNavigationTree *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800021a4`
- `0x18000c770`
- `0x18000cb10`
- `0x18000cc48`
- `0x18000d920`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ConfigPathTagNode::TryInitializeChildren(ConfigPathTagNode *this, struct ConfigPathNavigationTree *a2)
{
  void (__fastcall ***v5)(_QWORD, struct ConfigPathNavigationTree *, ConfigPathTagNode *); // rcx
  struct AppHostFileSystemNavigator *v6; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_BYTE *)this + 96) )
    return 0;
  *((_BYTE *)this + 96) = 1;
  v5 = (void (__fastcall ***)(_QWORD, struct ConfigPathNavigationTree *, ConfigPathTagNode *))*((_QWORD *)this + 16);
  if ( v5 )
    (**v5)(v5, a2, this);
  ConfigPathTagNode::InitializeConfigLocationsDescendents(this, a2);
  v6 = 0;
  ConfigPathNode::CreateFileSystemNavigator(this, (struct ConfigNameTablePair **)a2, &v6);
  ConfigPathTagNode::InitializeFileSystemChildren(this, a2, v6);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v6);
  return 1;
}

```

## disassembly

```asm
0x18000d920  mov     [rsp+arg_8], rbx
0x18000d925  push    rdi
0x18000d926  sub     rsp, 20h
0x18000d92a  mov     rdi, rdx
0x18000d92d  mov     rbx, rcx
0x18000d930  cmp     byte ptr [rcx+60h], 0
0x18000d934  jz      short loc_18000D93A
0x18000d936  xor     al, al
0x18000d938  jmp     short loc_18000D999
0x18000d93a  mov     byte ptr [rcx+60h], 1
0x18000d93e  mov     rcx, [rcx+80h]
0x18000d945  test    rcx, rcx
0x18000d948  jz      short loc_18000D958
0x18000d94a  mov     rax, [rcx]
0x18000d94d  mov     r8, rbx
0x18000d950  mov     rax, [rax]
0x18000d953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d958  mov     rdx, rdi; struct ConfigPathNavigationTree *
0x18000d95b  mov     rcx, rbx; this
0x18000d95e  call    ?InitializeConfigLocationsDescendents@ConfigPathTagNode@@AEAAXPEAVConfigPathNavigationTree@@@Z; ConfigPathTagNode::InitializeConfigLocationsDescendents(ConfigPathNavigationTree *)
0x18000d963  mov     [rsp+28h+arg_0], 0
0x18000d96c  lea     r8, [rsp+28h+arg_0]; struct AppHostFileSystemNavigator **
0x18000d971  mov     rdx, rdi; struct ConfigPathNavigationTree *
0x18000d974  mov     rcx, rbx; this
0x18000d977  call    ?CreateFileSystemNavigator@ConfigPathNode@@QEAAXPEAVConfigPathNavigationTree@@PEAPEAVAppHostFileSystemNavigator@@@Z; ConfigPathNode::CreateFileSystemNavigator(ConfigPathNavigationTree *,AppHostFileSystemNavigator * *)
0x18000d97c  mov     r8, [rsp+28h+arg_0]; struct AppHostFileSystemNavigator *
0x18000d981  mov     rdx, rdi; struct ConfigPathNavigationTree *
0x18000d984  mov     rcx, rbx; this
0x18000d987  call    ?InitializeFileSystemChildren@ConfigPathTagNode@@AEAAXPEAVConfigPathNavigationTree@@PEAVAppHostFileSystemNavigator@@@Z; ConfigPathTagNode::InitializeFileSystemChildren(ConfigPathNavigationTree *,AppHostFileSystemNavigator *)
0x18000d98c  nop
0x18000d98d  lea     rcx, [rsp+28h+arg_0]
0x18000d992  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d997  mov     al, 1
0x18000d999  mov     rbx, [rsp+28h+arg_8]
0x18000d99e  add     rsp, 20h
0x18000d9a2  pop     rdi
0x18000d9a3  retn
```
