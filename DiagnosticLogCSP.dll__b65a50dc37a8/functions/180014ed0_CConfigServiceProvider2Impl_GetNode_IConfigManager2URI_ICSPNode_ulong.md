# CConfigServiceProvider2Impl::GetNode(IConfigManager2URI *,ICSPNode * *,ulong *)

- ea: `0x180014ed0`
- end: `0x180014fc6`
- name: `?GetNode@CConfigServiceProvider2Impl@@UEAAJPEAUIConfigManager2URI@@PEAPEAUICSPNode@@PEAK@Z`
- size: `246`
- prototype: `int(CConfigServiceProvider2Impl *__hidden this, struct IConfigManager2URI *, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800033b0`

## callees

- `0x180014ed0`
- `0x180015590`
- `0x180039010`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::GetNode(
        const struct CspNodeMapBase **this,
        struct IConfigManager2URI *a2,
        struct ICSPNode **a3,
        unsigned int *a4)
{
  int v8; // ecx
  const struct CspNodeMapBase *v9; // rcx
  const struct CSP_NODEMAP_ENTRY *NodeMapEntryForURI; // rax
  const struct CSP_NODEMAP_ENTRY *v11; // r8
  __int64 (__fastcall *v12)(CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODEMAP_ENTRY *, _QWORD, struct ICSPNode **, unsigned int *); // rax
  unsigned int v14; // [rsp+40h] [rbp-38h] BYREF
  struct ICSPNode *v15; // [rsp+48h] [rbp-30h] BYREF
  int v16; // [rsp+88h] [rbp+10h] BYREF

  v16 = 0;
  if ( a2 && a3 && (*a3 = 0, a4) )
  {
    *a4 = 0;
    v8 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v16);
    if ( v8 >= 0 )
    {
      if ( v16 && (v9 = this[4]) != 0 && (NodeMapEntryForURI = CspGetNodeMapEntryForURI(v9, a2)) != 0 )
      {
        v15 = 0;
        v11 = NodeMapEntryForURI;
        v12 = (__int64 (__fastcall *)(CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODEMAP_ENTRY *, _QWORD, struct ICSPNode **, unsigned int *))*((_QWORD *)NodeMapEntryForURI + 4);
        v14 = 0;
        v8 = v12((CConfigServiceProvider2Impl *)this, a2, v11, 0, &v15, &v14);
        if ( v8 >= 0 )
        {
          if ( v15 )
          {
            *a3 = v15;
            *a4 = v14;
          }
          else
          {
            return (unsigned int)-2147024882;
          }
        }
      }
      else
      {
        return (unsigned int)-2046820350;
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180014ed0  mov     rax, rsp
0x180014ed3  push    rbx
0x180014ed4  push    rbp
0x180014ed5  push    rsi
0x180014ed6  push    rdi
0x180014ed7  sub     rsp, 58h
0x180014edb  mov     dword ptr [rax+10h], 0
0x180014ee2  mov     rsi, r9
0x180014ee5  mov     rbx, r8
0x180014ee8  mov     rdi, rdx
0x180014eeb  mov     rbp, rcx
0x180014eee  test    rdx, rdx
0x180014ef1  jnz     short loc_180014EFD
0x180014ef3  mov     ecx, 80004003h
0x180014ef8  jmp     loc_180014FBA
0x180014efd  test    rbx, rbx
0x180014f00  jz      short loc_180014EF3
0x180014f02  mov     qword ptr [r8], 0
0x180014f09  test    rsi, rsi
0x180014f0c  jz      short loc_180014EF3
0x180014f0e  mov     dword ptr [r9], 0
0x180014f15  mov     rcx, rdi
0x180014f18  mov     rax, [rdx]
0x180014f1b  lea     rdx, [rsp+78h+arg_8]
0x180014f23  mov     rax, [rax+88h]
0x180014f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f2f  mov     ecx, eax
0x180014f31  test    eax, eax
0x180014f33  js      loc_180014FBA
0x180014f39  cmp     [rsp+78h+arg_8], 0
0x180014f41  jz      short loc_180014FB5
0x180014f43  mov     rcx, [rbp+20h]; struct CspNodeMapBase *
0x180014f47  test    rcx, rcx
0x180014f4a  jz      short loc_180014FB5
0x180014f4c  mov     rdx, rdi; struct IConfigManager2URI *
0x180014f4f  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x180014f54  test    rax, rax
0x180014f57  jz      short loc_180014FB5
0x180014f59  lea     rcx, [rsp+78h+var_38]
0x180014f5e  mov     [rsp+78h+var_30], 0
0x180014f67  mov     [rsp+78h+var_50], rcx
0x180014f6c  mov     r8, rax
0x180014f6f  mov     rax, [rax+20h]
0x180014f73  lea     rcx, [rsp+78h+var_30]
0x180014f78  mov     [rsp+78h+var_58], rcx
0x180014f7d  xor     r9d, r9d
0x180014f80  mov     rcx, rbp
0x180014f83  mov     [rsp+78h+var_38], 0
0x180014f8b  mov     rdx, rdi
0x180014f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f93  mov     ecx, eax
0x180014f95  test    eax, eax
0x180014f97  js      short loc_180014FBA
0x180014f99  mov     rax, [rsp+78h+var_30]
0x180014f9e  test    rax, rax
0x180014fa1  jnz     short loc_180014FAA
0x180014fa3  mov     ecx, 8007000Eh
0x180014fa8  jmp     short loc_180014FBA
0x180014faa  mov     [rbx], rax
0x180014fad  mov     eax, [rsp+78h+var_38]
0x180014fb1  mov     [rsi], eax
0x180014fb3  jmp     short loc_180014FBA
0x180014fb5  mov     ecx, 86000002h
0x180014fba  mov     eax, ecx
0x180014fbc  add     rsp, 58h
0x180014fc0  pop     rdi
0x180014fc1  pop     rsi
0x180014fc2  pop     rbp
0x180014fc3  pop     rbx
0x180014fc4  retn
```
