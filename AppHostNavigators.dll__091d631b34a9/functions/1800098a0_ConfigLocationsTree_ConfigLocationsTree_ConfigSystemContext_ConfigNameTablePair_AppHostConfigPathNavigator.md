# ConfigLocationsTree::ConfigLocationsTree(ConfigSystemContext *,ConfigNameTablePair *,AppHostConfigPathNavigator *)

- ea: `0x1800098a0`
- end: `0x180009a1d`
- name: `??0ConfigLocationsTree@@QEAA@PEAVConfigSystemContext@@PEAVConfigNameTablePair@@PEAVAppHostConfigPathNavigator@@@Z`
- size: `381`
- prototype: `ConfigLocationsTree *__fastcall(ConfigLocationsTree *__hidden this, struct ConfigSystemContext *, struct ConfigNameTablePair *, struct AppHostConfigPathNavigator *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000280c`

## callees

- `0x1800021e0`
- `0x1800042ec`
- `0x180004840`
- `0x1800098a0`
- `0x18000a104`
- `0x18000c8a8`
- `0x180011240`
- `0x1800126b0`
- `0x180012f3c`
- `0x1800130a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
ConfigLocationsTree *__fastcall ConfigLocationsTree::ConfigLocationsTree(
        ConfigLocationsTree *this,
        struct ConfigSystemContext *a2,
        struct ConfigNameTablePair *a3,
        ConfigPathNode **a4)
{
  __int64 v6; // rcx
  __int64 v7; // r9
  NavigationNodeBase *v8; // rbx
  int v9; // eax
  int v10; // eax
  int pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  ConfigLocationsTree *v13; // [rsp+28h] [rbp-D8h]
  _BYTE v14[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+34h] [rbp-CCh]
  unsigned __int16 *v16; // [rsp+38h] [rbp-C8h]
  int v17; // [rsp+40h] [rbp-C0h]
  __int16 v18; // [rsp+50h] [rbp-B0h] BYREF

  v13 = this;
  NavigationTreeBase::NavigationTreeBase(this, a3);
  *(_QWORD *)v6 = &ConfigLocationsTree::`vftable';
  *(_QWORD *)(v6 + 24) = v7;
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
  *(_QWORD *)(v6 + 32) = 0;
  *(_QWORD *)(v6 + 40) = 0;
  v8 = (NavigationNodeBase *)(v6 + 48);
  *(_DWORD *)(v6 + 56) = -1;
  *(_DWORD *)(v6 + 60) = 0;
  *(_QWORD *)(v6 + 64) = 0;
  *(_QWORD *)(v6 + 72) = 0;
  *(_QWORD *)(v6 + 80) = 0;
  *(_QWORD *)(v6 + 96) = v6 + 88;
  *(_QWORD *)(v6 + 88) = v6 + 88;
  *(_QWORD *)(v6 + 112) = 0;
  *(_QWORD *)(v6 + 104) = 0;
  *(_QWORD *)(v6 + 120) = 0;
  *(_QWORD *)(v6 + 128) = 0;
  *(_QWORD *)(v6 + 48) = &ConfigLocationRootNode::`vftable';
  v9 = AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::Clone(
         a4,
         v6 + 32);
  if ( v9 < 0 )
  {
    pExceptionObject = v9;
    throw (long *)&pExceptionObject;
  }
  v14[2] = 0;
  v15 = 520;
  v16 = (unsigned __int16 *)&v18;
  v17 = 0;
  v18 = 0;
  ConfigPathNode::GetConfigPath(a4[6], a4[5], (struct STRU *)v14);
  v10 = String::Initialize((ConfigLocationsTree *)((char *)this + 40), v16);
  if ( v10 < 0 )
  {
    pExceptionObject = v10;
    throw (long *)&pExceptionObject;
  }
  NavigationNodeBase::Initialize(v8, this, &qword_1800181B0);
  *((_DWORD *)v8 + 2) = 0;
  ConfigLocationRootNode::InitializeDescendents(v8, this);
  BUFFER::~BUFFER((BUFFER *)v14);
  return this;
}

```

## disassembly

```asm
0x1800098a0  mov     [rsp-8+arg_8], rbx
0x1800098a5  push    rbp
0x1800098a6  push    rsi
0x1800098a7  push    rdi
0x1800098a8  push    r14
0x1800098aa  push    r15
0x1800098ac  lea     rbp, [rsp-170h]
0x1800098b4  sub     rsp, 270h
0x1800098bb  mov     rax, cs:__security_cookie
0x1800098c2  xor     rax, rsp
0x1800098c5  mov     [rbp+190h+var_30], rax
0x1800098cc  mov     rsi, r9
0x1800098cf  mov     r9, rdx
0x1800098d2  mov     rdi, rcx
0x1800098d5  mov     [rsp+290h+var_268], rcx
0x1800098da  mov     rdx, r8; struct ConfigNameTablePair *
0x1800098dd  call    ??0NavigationTreeBase@@QEAA@PEAVConfigNameTablePair@@@Z; NavigationTreeBase::NavigationTreeBase(ConfigNameTablePair *)
0x1800098e2  nop
0x1800098e3  lea     rax, ??_7ConfigLocationsTree@@6B@; const ConfigLocationsTree::`vftable'
0x1800098ea  mov     [rcx], rax
0x1800098ed  mov     [rcx+18h], r9
0x1800098f1  xor     r15d, r15d
0x1800098f4  test    r9, r9
0x1800098f7  jz      short loc_1800098FE
0x1800098f9  lock inc dword ptr [r9+8]
0x1800098fe  lea     rdx, [rcx+20h]
0x180009902  mov     [rdx], r15
0x180009905  mov     [rcx+28h], r15
0x180009909  lea     rbx, [rcx+30h]
0x18000990d  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x180009914  mov     [rbx+0Ch], r15d
0x180009918  mov     [rbx+10h], r15
0x18000991c  mov     [rbx+18h], r15
0x180009920  mov     [rbx+20h], r15
0x180009924  lea     rax, [rbx+28h]
0x180009928  mov     [rax+8], rax
0x18000992c  mov     [rax], rax
0x18000992f  mov     [rbx+40h], r15
0x180009933  mov     [rbx+38h], r15
0x180009937  mov     [rbx+48h], r15
0x18000993b  mov     [rbx+50h], r15
0x18000993f  lea     rax, ??_7ConfigLocationRootNode@@6B@; const ConfigLocationRootNode::`vftable'
0x180009946  mov     [rbx], rax
0x180009949  mov     rcx, rsi
0x18000994c  call    ?Clone@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@QEAAJPEAPEAVAppHostConfigPathNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::Clone(AppHostConfigPathNavigator * *)
0x180009951  test    eax, eax
0x180009953  jns     short loc_18000996B
0x180009955  mov     [rsp+290h+pExceptionObject], eax
0x180009959  lea     rdx, _TI1J; pThrowInfo
0x180009960  lea     rcx, [rsp+290h+pExceptionObject]; pExceptionObject
0x180009965  call    _CxxThrowException_0
0x18000996b  mov     [rsp+290h+var_25E], r15b
0x180009970  mov     [rsp+290h+var_25C], 208h
0x180009978  lea     rax, [rsp+290h+var_240]
0x18000997d  mov     [rsp+290h+var_258], rax
0x180009982  mov     [rsp+290h+var_250], r15d
0x180009987  mov     [rsp+290h+var_240], r15w
0x18000998d  lea     r8, [rsp+290h+var_260]; struct STRU *
0x180009992  mov     rdx, [rsi+28h]; struct ConfigPathNavigationTree *
0x180009996  mov     rcx, [rsi+30h]; this
0x18000999a  call    ?GetConfigPath@ConfigPathNode@@QEAAXPEAVConfigPathNavigationTree@@AEAVSTRU@@@Z; ConfigPathNode::GetConfigPath(ConfigPathNavigationTree *,STRU &)
0x18000999f  mov     rdx, [rsp+290h+var_258]; unsigned __int16 *
0x1800099a4  lea     rcx, [rdi+28h]; this
0x1800099a8  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x1800099ad  test    eax, eax
0x1800099af  jns     short loc_1800099C7
0x1800099b1  mov     [rsp+290h+pExceptionObject], eax
0x1800099b5  lea     rdx, _TI1J; pThrowInfo
0x1800099bc  lea     rcx, [rsp+290h+pExceptionObject]; pExceptionObject
0x1800099c1  call    _CxxThrowException_0
0x1800099c7  lea     r8, qword_1800181B0; unsigned __int16 *
0x1800099ce  mov     rdx, rdi; struct NavigationTreeBase *
0x1800099d1  mov     rcx, rbx; this
0x1800099d4  call    ?Initialize@NavigationNodeBase@@IEAAXPEAVNavigationTreeBase@@PEBG@Z; NavigationNodeBase::Initialize(NavigationTreeBase *,ushort const *)
0x1800099d9  mov     [rbx+8], r15d
0x1800099dd  mov     rdx, rdi; struct ConfigLocationsTree *
0x1800099e0  mov     rcx, rbx; this
0x1800099e3  call    ?InitializeDescendents@ConfigLocationRootNode@@AEAAXPEAVConfigLocationsTree@@@Z; ConfigLocationRootNode::InitializeDescendents(ConfigLocationsTree *)
0x1800099e8  nop
0x1800099e9  lea     rcx, [rsp+290h+var_260]; this
0x1800099ee  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800099f3  nop
0x1800099f4  mov     rax, rdi
0x1800099f7  mov     rcx, [rbp+190h+var_30]
0x1800099fe  xor     rcx, rsp; StackCookie
0x180009a01  call    __security_check_cookie
0x180009a06  mov     rbx, [rsp+290h+arg_8]
0x180009a0e  add     rsp, 270h
0x180009a15  pop     r15
0x180009a17  pop     r14
0x180009a19  pop     rdi
0x180009a1a  pop     rsi
0x180009a1b  pop     rbp
0x180009a1c  retn
```
