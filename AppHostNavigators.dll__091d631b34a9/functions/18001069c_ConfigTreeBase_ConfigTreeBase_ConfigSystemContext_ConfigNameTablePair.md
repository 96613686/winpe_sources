# ConfigTreeBase::ConfigTreeBase(ConfigSystemContext *,ConfigNameTablePair *)

- ea: `0x18001069c`
- end: `0x180010766`
- name: `??0ConfigTreeBase@@QEAA@PEAVConfigSystemContext@@PEAVConfigNameTablePair@@@Z`
- size: `202`
- prototype: `ConfigTreeBase *__fastcall(ConfigTreeBase *__hidden this, struct ConfigSystemContext *, struct ConfigNameTablePair *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001076c`
- `0x1800113b0`

## callees

- `0x1800042ec`
- `0x18001069c`
- `0x180011240`

## pseudocode

```c
ConfigTreeBase *__fastcall ConfigTreeBase::ConfigTreeBase(
        ConfigTreeBase *this,
        struct ConfigSystemContext *a2,
        struct ConfigNameTablePair *a3)
{
  __int64 v4; // rcx
  __int64 v5; // r9

  NavigationTreeBase::NavigationTreeBase(this, a3);
  *(_QWORD *)v4 = &ConfigTreeBase::`vftable';
  *(_QWORD *)(v4 + 24) = v5;
  if ( v5 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
  *(_DWORD *)(v4 + 40) = -1;
  *(_DWORD *)(v4 + 44) = 0;
  *(_QWORD *)(v4 + 48) = 0;
  *(_QWORD *)(v4 + 56) = 0;
  *(_QWORD *)(v4 + 64) = 0;
  *(_QWORD *)(v4 + 80) = v4 + 72;
  *(_QWORD *)(v4 + 72) = v4 + 72;
  *(_QWORD *)(v4 + 96) = 0;
  *(_QWORD *)(v4 + 88) = 0;
  *(_QWORD *)(v4 + 104) = 0;
  *(_QWORD *)(v4 + 112) = 0;
  *(_QWORD *)(v4 + 120) = 0;
  *(_QWORD *)(v4 + 32) = &ConfigRootNode::`vftable';
  NavigationNodeBase::Initialize((NavigationNodeBase *)(v4 + 32), this, &qword_1800181B0);
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 10) = 0;
  return this;
}

```

## disassembly

```asm
0x18001069c  mov     [rsp+arg_8], rbx
0x1800106a1  mov     [rsp+arg_0], rcx
0x1800106a6  push    rdi
0x1800106a7  sub     rsp, 20h
0x1800106ab  mov     r9, rdx
0x1800106ae  mov     rdi, rcx
0x1800106b1  mov     rdx, r8; struct ConfigNameTablePair *
0x1800106b4  call    ??0NavigationTreeBase@@QEAA@PEAVConfigNameTablePair@@@Z; NavigationTreeBase::NavigationTreeBase(ConfigNameTablePair *)
0x1800106b9  nop
0x1800106ba  lea     rax, ??_7ConfigTreeBase@@6B@; const ConfigTreeBase::`vftable'
0x1800106c1  mov     [rcx], rax
0x1800106c4  mov     [rcx+18h], r9
0x1800106c8  test    r9, r9
0x1800106cb  jz      short loc_1800106D2
0x1800106cd  lock inc dword ptr [r9+8]
0x1800106d2  mov     dword ptr [rcx+28h], 0FFFFFFFFh
0x1800106d9  mov     dword ptr [rcx+2Ch], 0
0x1800106e0  mov     qword ptr [rcx+30h], 0
0x1800106e8  mov     qword ptr [rcx+38h], 0
0x1800106f0  mov     qword ptr [rcx+40h], 0
0x1800106f8  lea     rax, [rcx+48h]
0x1800106fc  mov     [rax+8], rax
0x180010700  mov     [rax], rax
0x180010703  mov     qword ptr [rcx+60h], 0
0x18001070b  mov     qword ptr [rcx+58h], 0
0x180010713  mov     qword ptr [rcx+68h], 0
0x18001071b  mov     qword ptr [rcx+70h], 0
0x180010723  mov     qword ptr [rcx+78h], 0
0x18001072b  lea     rax, ??_7ConfigRootNode@@6B@; const ConfigRootNode::`vftable'
0x180010732  mov     [rcx+20h], rax
0x180010736  lea     r8, qword_1800181B0; unsigned __int16 *
0x18001073d  mov     rdx, rdi; struct NavigationTreeBase *
0x180010740  add     rcx, 20h ; ' '; this
0x180010744  call    ?Initialize@NavigationNodeBase@@IEAAXPEAVNavigationTreeBase@@PEBG@Z; NavigationNodeBase::Initialize(NavigationTreeBase *,ushort const *)
0x180010749  mov     qword ptr [rdi+70h], 0
0x180010751  mov     dword ptr [rdi+28h], 0
0x180010758  mov     rax, rdi
0x18001075b  mov     rbx, [rsp+28h+arg_8]
0x180010760  add     rsp, 20h
0x180010764  pop     rdi
0x180010765  retn
```
