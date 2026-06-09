# PropertyNode::GetMetadata(ConfigTreeBase *,ushort const *,tagVARIANT *)

- ea: `0x18000b470`
- end: `0x18000b4eb`
- name: `?GetMetadata@PropertyNode@@UEAAXPEAVConfigTreeBase@@PEBGPEAUtagVARIANT@@@Z`
- size: `123`
- prototype: `void __fastcall(PropertyNode *this, struct ConfigTreeBase *, OLECHAR *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000b470`
- `0x180012df4`
- `0x180012ea8`
- `0x180012f3c`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000b4cf`
- `OLEAUT32!__imp_VariantClear` at `0x18000b4cf`

## pseudocode

```c
void __fastcall PropertyNode::GetMetadata(
        PropertyNode *this,
        struct ConfigTreeBase *a2,
        OLECHAR *a3,
        struct tagVARIANT *a4)
{
  int v6; // eax
  int pExceptionObject; // [rsp+20h] [rbp-18h] BYREF
  _QWORD v8[2]; // [rsp+28h] [rbp-10h] BYREF

  v8[0] = 0;
  v6 = ScopedBSTR::CopyString((ScopedBSTR *)v8, a3);
  if ( v6 < 0 )
  {
    pExceptionObject = v6;
    throw (long *)&pExceptionObject;
  }
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, struct tagVARIANT *))(**((_QWORD **)this + 5) + 72LL))(
         *((_QWORD *)this + 5),
         v8[0],
         a4) < 0 )
    VariantClear(a4);
  ScopedBSTR::Reset((ScopedBSTR *)v8);
}

```

## disassembly

```asm
0x18000b470  mov     [rsp+arg_0], rbx
0x18000b475  push    rdi
0x18000b476  sub     rsp, 30h
0x18000b47a  mov     rbx, r9
0x18000b47d  mov     rdi, rcx
0x18000b480  mov     [rsp+38h+var_10], 0
0x18000b489  mov     rdx, r8; psz
0x18000b48c  lea     rcx, [rsp+38h+var_10]; this
0x18000b491  call    ?CopyString@ScopedBSTR@@QEAAJPEBG@Z; ScopedBSTR::CopyString(ushort const *)
0x18000b496  test    eax, eax
0x18000b498  jns     short loc_18000B4B0
0x18000b49a  mov     [rsp+38h+pExceptionObject], eax
0x18000b49e  lea     rdx, _TI1J; pThrowInfo
0x18000b4a5  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000b4aa  call    _CxxThrowException_0
0x18000b4b0  mov     rcx, [rdi+28h]
0x18000b4b4  mov     rax, [rcx]
0x18000b4b7  mov     r8, rbx
0x18000b4ba  mov     rdx, [rsp+38h+var_10]
0x18000b4bf  mov     rax, [rax+48h]
0x18000b4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4c8  test    eax, eax
0x18000b4ca  jns     short loc_18000B4D6
0x18000b4cc  mov     rcx, rbx; pvarg
0x18000b4cf  call    cs:__imp_VariantClear
0x18000b4d5  nop
0x18000b4d6  lea     rcx, [rsp+38h+var_10]; this
0x18000b4db  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000b4e0  mov     rbx, [rsp+38h+arg_0]
0x18000b4e5  add     rsp, 30h
0x18000b4e9  pop     rdi
0x18000b4ea  retn
```
