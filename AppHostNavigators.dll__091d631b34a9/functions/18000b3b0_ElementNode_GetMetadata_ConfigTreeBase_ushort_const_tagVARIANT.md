# ElementNode::GetMetadata(ConfigTreeBase *,ushort const *,tagVARIANT *)

- ea: `0x18000b3b0`
- end: `0x18000b463`
- name: `?GetMetadata@ElementNode@@UEAAXPEAVConfigTreeBase@@PEBGPEAUtagVARIANT@@@Z`
- size: `179`
- prototype: `void __fastcall(ElementNode *this, struct ConfigTreeBase *, OLECHAR *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b5a0`

## callees

- `0x1800021a4`
- `0x18000b3b0`
- `0x180012df4`
- `0x180012ea8`
- `0x180012f3c`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000b437`
- `OLEAUT32!__imp_VariantClear` at `0x18000b437`

## pseudocode

```c
void __fastcall ElementNode::GetMetadata(
        ElementNode *this,
        struct ConfigTreeBase *a2,
        OLECHAR *a3,
        struct tagVARIANT *a4)
{
  int v7; // eax
  int pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+28h] [rbp-20h] BYREF
  _QWORD v10[3]; // [rsp+30h] [rbp-18h] BYREF

  v10[0] = 0;
  v7 = ScopedBSTR::CopyString((ScopedBSTR *)v10, a3);
  if ( v7 < 0 )
  {
    pExceptionObject = v7;
    throw (long *)&pExceptionObject;
  }
  v9 = 0;
  (*(void (__fastcall **)(ElementNode *, struct ConfigTreeBase *, __int64 *))(*(_QWORD *)this + 112LL))(this, a2, &v9);
  if ( (*(int (__fastcall **)(__int64, _QWORD, struct tagVARIANT *))(*(_QWORD *)v9 + 56LL))(v9, v10[0], a4) < 0 )
    VariantClear(a4);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  ScopedBSTR::Reset((ScopedBSTR *)v10);
}

```

## disassembly

```asm
0x18000b3b0  mov     rax, rsp
0x18000b3b3  mov     [rax+8], rbx
0x18000b3b7  mov     [rax+10h], rsi
0x18000b3bb  push    rdi
0x18000b3bc  sub     rsp, 40h
0x18000b3c0  mov     rbx, r9
0x18000b3c3  mov     rsi, rdx
0x18000b3c6  mov     rdi, rcx
0x18000b3c9  mov     qword ptr [rax-18h], 0
0x18000b3d1  mov     rdx, r8; psz
0x18000b3d4  lea     rcx, [rax-18h]; this
0x18000b3d8  call    ?CopyString@ScopedBSTR@@QEAAJPEBG@Z; ScopedBSTR::CopyString(ushort const *)
0x18000b3dd  test    eax, eax
0x18000b3df  jns     short loc_18000B3F7
0x18000b3e1  mov     [rsp+48h+pExceptionObject], eax
0x18000b3e5  lea     rdx, _TI1J; pThrowInfo
0x18000b3ec  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000b3f1  call    _CxxThrowException_0
0x18000b3f7  mov     [rsp+48h+var_20], 0
0x18000b400  mov     rax, [rdi]
0x18000b403  lea     r8, [rsp+48h+var_20]
0x18000b408  mov     rdx, rsi
0x18000b40b  mov     rcx, rdi
0x18000b40e  mov     rax, [rax+70h]
0x18000b412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b417  mov     rcx, [rsp+48h+var_20]
0x18000b41c  mov     rax, [rcx]
0x18000b41f  mov     r8, rbx
0x18000b422  mov     rdx, [rsp+48h+var_18]
0x18000b427  mov     rax, [rax+38h]
0x18000b42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b430  test    eax, eax
0x18000b432  jns     short loc_18000B43E
0x18000b434  mov     rcx, rbx; pvarg
0x18000b437  call    cs:__imp_VariantClear
0x18000b43d  nop
0x18000b43e  lea     rcx, [rsp+48h+var_20]
0x18000b443  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b448  nop
0x18000b449  lea     rcx, [rsp+48h+var_18]; this
0x18000b44e  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000b453  mov     rbx, [rsp+48h+arg_0]
0x18000b458  mov     rsi, [rsp+48h+arg_8]
0x18000b45d  add     rsp, 40h
0x18000b461  pop     rdi
0x18000b462  retn
```
