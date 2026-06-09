# CIISTree::CreateServerObject(ushort const *,ushort const *,ushort const *,CCredentials &,ulong,_GUID const &,void * *)

- ea: `0x180002d98`
- end: `0x180002e6b`
- name: `?CreateServerObject@CIISTree@@SAJPEBG00AEAVCCredentials@@KAEBU_GUID@@PEAPEAX@Z`
- size: `211`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct CCredentials *, unsigned int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800027d4`

## callees

- `0x180002a90`
- `0x180002b00`
- `0x180002d98`
- `0x180003260`
- `0x1800148a0`
- `0x18001e010`

## string_xrefs

- `0x180002de2`: `IIsComputer`

## pseudocode

```c
__int64 __fastcall CIISTree::CreateServerObject(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct CCredentials *a4,
        unsigned int a5,
        const struct _GUID *a6,
        void **a7)
{
  int v9; // eax
  unsigned int v10; // edx
  CCoreADsObject *v11; // rdi
  int v12; // ebx
  const unsigned __int16 *v14; // [rsp+20h] [rbp-48h]
  CCoreADsObject *v15; // [rsp+80h] [rbp+18h] BYREF

  v15 = 0;
  v9 = CIISTree::AllocateTree(a4, &v15);
  v11 = v15;
  v12 = v9;
  if ( v9 < 0
    || (v12 = CCoreADsObject::InitializeCoreObject(v15, L"IIS:", a2, L"IIsComputer", v14, &CLSID_IISTree, 1u), v12 < 0)
    || (v12 = CPropertyCache::InitializePropertyCache(*((CPropertyCache **)v11 + 14), a2, a4), v12 < 0)
    || (v12 = (**((__int64 (__fastcall ***)(__int64, GUID *, void **))v11 + 8))((__int64)v11 + 64, &IID_IDispatch, a7),
        v12 < 0) )
  {
    if ( v11 )
      CIISTree::`scalar deleting destructor'(v11, v10);
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v11 + 8) + 16LL))((__int64)v11 + 64);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180002d98  mov     rax, rsp
0x180002d9b  mov     [rax+18h], r8
0x180002d9f  push    rbx
0x180002da0  push    rbp
0x180002da1  push    rsi
0x180002da2  push    rdi
0x180002da3  sub     rsp, 48h
0x180002da7  mov     rsi, rdx
0x180002daa  mov     qword ptr [rax+18h], 0
0x180002db2  lea     rdx, [rax+18h]; struct CIISTree **
0x180002db6  mov     rcx, r9; struct CCredentials *
0x180002db9  mov     rbp, r9
0x180002dbc  call    ?AllocateTree@CIISTree@@SAJAEAVCCredentials@@PEAPEAV1@@Z; CIISTree::AllocateTree(CCredentials &,CIISTree * *)
0x180002dc1  mov     rdi, [rsp+68h+arg_10]
0x180002dc9  mov     ebx, eax
0x180002dcb  test    eax, eax
0x180002dcd  js      loc_180002E53
0x180002dd3  lea     rax, CLSID_IISTree
0x180002dda  mov     [rsp+68h+var_38], 1; unsigned int
0x180002de2  lea     r9, aIiscomputer; "IIsComputer"
0x180002de9  mov     [rsp+68h+var_40], rax; struct _GUID *
0x180002dee  mov     r8, rsi; unsigned __int16 *
0x180002df1  lea     rdx, aIis_0; "IIS:"
0x180002df8  mov     rcx, rdi; this
0x180002dfb  call    ?InitializeCoreObject@CCoreADsObject@@QEAAJPEBG000AEBU_GUID@@K@Z; CCoreADsObject::InitializeCoreObject(ushort const *,ushort const *,ushort const *,ushort const *,_GUID const &,ulong)
0x180002e00  mov     ebx, eax
0x180002e02  test    eax, eax
0x180002e04  js      short loc_180002E53
0x180002e06  mov     rcx, [rdi+70h]; this
0x180002e0a  mov     r8, rbp; struct CCredentials *
0x180002e0d  mov     rdx, rsi; unsigned __int16 *
0x180002e10  call    ?InitializePropertyCache@CPropertyCache@@QEAAJPEBGAEAVCCredentials@@@Z; CPropertyCache::InitializePropertyCache(ushort const *,CCredentials &)
0x180002e15  mov     ebx, eax
0x180002e17  test    eax, eax
0x180002e19  js      short loc_180002E53
0x180002e1b  mov     r8, [rsp+68h+arg_30]
0x180002e23  lea     rsi, [rdi+40h]
0x180002e27  mov     rax, [rsi]
0x180002e2a  lea     rdx, IID_IDispatch
0x180002e31  mov     rcx, rsi
0x180002e34  mov     rax, [rax]
0x180002e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e3c  mov     ebx, eax
0x180002e3e  test    eax, eax
0x180002e40  js      short loc_180002E53
0x180002e42  mov     rax, [rsi]
0x180002e45  mov     rcx, rsi
0x180002e48  mov     rax, [rax+10h]
0x180002e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e51  jmp     short loc_180002E60
0x180002e53  test    rdi, rdi
0x180002e56  jz      short loc_180002E60
0x180002e58  mov     rcx, rdi; this
0x180002e5b  call    ??_GCIISTree@@QEAAPEAXI@Z; CIISTree::`scalar deleting destructor'(uint)
0x180002e60  mov     eax, ebx
0x180002e62  add     rsp, 48h
0x180002e66  pop     rdi
0x180002e67  pop     rsi
0x180002e68  pop     rbp
0x180002e69  pop     rbx
0x180002e6a  retn
```
