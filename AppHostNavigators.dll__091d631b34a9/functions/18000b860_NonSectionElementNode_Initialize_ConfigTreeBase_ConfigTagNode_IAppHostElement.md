# NonSectionElementNode::Initialize(ConfigTreeBase *,ConfigTagNode *,IAppHostElement *)

- ea: `0x18000b860`
- end: `0x18000b8e5`
- name: `?Initialize@NonSectionElementNode@@QEAAXPEAVConfigTreeBase@@PEAVConfigTagNode@@PEAUIAppHostElement@@@Z`
- size: `133`
- prototype: `void __fastcall(NonSectionElementNode *__hidden this, struct ConfigTreeBase *, struct ConfigTagNode *, struct IAppHostElement *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b8ec`
- `0x18000ba8c`

## callees

- `0x180007aac`
- `0x18000b860`
- `0x180011240`
- `0x180012ea8`
- `0x180012f3c`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NonSectionElementNode::Initialize(
        struct IUnknown **this,
        struct ConfigTreeBase *a2,
        struct IUnknown *a3,
        struct IUnknown *a4)
{
  int v8; // eax
  unsigned __int16 *v9[7]; // [rsp+20h] [rbp-38h] BYREF
  int pExceptionObject; // [rsp+78h] [rbp+20h] BYREF

  v9[0] = 0;
  v8 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 **))a4->lpVtbl[1].QueryInterface)(a4, v9);
  if ( v8 < 0 )
  {
    pExceptionObject = v8;
    throw (long *)&pExceptionObject;
  }
  NavigationNodeBase::Initialize((NavigationNodeBase *)this, a2, v9[0]);
  this[10] = a3;
  if ( this[12] != a4 )
    ATL::AtlComPtrAssign(this + 12, a4);
  ScopedBSTR::Reset((ScopedBSTR *)v9);
}

```

## disassembly

```asm
0x18000b860  push    rbx
0x18000b862  push    rbp
0x18000b863  push    rsi
0x18000b864  push    rdi
0x18000b865  sub     rsp, 38h
0x18000b869  mov     rdi, r9
0x18000b86c  mov     rsi, r8
0x18000b86f  mov     rbp, rdx
0x18000b872  mov     rbx, rcx
0x18000b875  mov     [rsp+58h+var_38], 0
0x18000b87e  mov     rax, [r9]
0x18000b881  lea     rdx, [rsp+58h+var_38]
0x18000b886  mov     rcx, r9
0x18000b889  mov     rax, [rax+18h]
0x18000b88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b892  test    eax, eax
0x18000b894  jns     short loc_18000B8AC
0x18000b896  mov     [rsp+58h+pExceptionObject], eax
0x18000b89a  lea     rdx, _TI1J; pThrowInfo
0x18000b8a1  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000b8a6  call    _CxxThrowException_0
0x18000b8ac  mov     r8, [rsp+58h+var_38]; unsigned __int16 *
0x18000b8b1  mov     rdx, rbp; struct NavigationTreeBase *
0x18000b8b4  mov     rcx, rbx; this
0x18000b8b7  call    ?Initialize@NavigationNodeBase@@IEAAXPEAVNavigationTreeBase@@PEBG@Z; NavigationNodeBase::Initialize(NavigationTreeBase *,ushort const *)
0x18000b8bc  mov     [rbx+50h], rsi
0x18000b8c0  lea     rcx, [rbx+60h]; struct IUnknown **
0x18000b8c4  cmp     [rcx], rdi
0x18000b8c7  jz      short loc_18000B8D2
0x18000b8c9  mov     rdx, rdi; struct IUnknown *
0x18000b8cc  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000b8d1  nop
0x18000b8d2  lea     rcx, [rsp+58h+var_38]; this
0x18000b8d7  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000b8dc  add     rsp, 38h
0x18000b8e0  pop     rdi
0x18000b8e1  pop     rsi
0x18000b8e2  pop     rbp
0x18000b8e3  pop     rbx
0x18000b8e4  retn
```
