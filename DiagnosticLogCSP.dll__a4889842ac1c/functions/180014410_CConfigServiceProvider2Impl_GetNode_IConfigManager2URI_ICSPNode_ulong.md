# CConfigServiceProvider2Impl::GetNode(IConfigManager2URI *,ICSPNode * *,ulong *)

- ea: `0x180014410`
- end: `0x180014505`
- name: `?GetNode@CConfigServiceProvider2Impl@@UEAAJPEAUIConfigManager2URI@@PEAPEAUICSPNode@@PEAK@Z`
- size: `245`
- prototype: `int(CConfigServiceProvider2Impl *__hidden this, struct IConfigManager2URI *, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003350`

## callees

- `0x180014410`
- `0x180014aac`
- `0x180037010`

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
0x180014410  mov     rax, rsp
0x180014413  push    rbx
0x180014414  push    rbp
0x180014415  push    rsi
0x180014416  push    rdi
0x180014417  sub     rsp, 58h
0x18001441b  mov     dword ptr [rax+10h], 0
0x180014422  mov     rsi, r9
0x180014425  mov     rbx, r8
0x180014428  mov     rdi, rdx
0x18001442b  mov     rbp, rcx
0x18001442e  test    rdx, rdx
0x180014431  jnz     short loc_18001443D
0x180014433  mov     ecx, 80004003h
0x180014438  jmp     loc_1800144FA
0x18001443d  test    rbx, rbx
0x180014440  jz      short loc_180014433
0x180014442  mov     qword ptr [r8], 0
0x180014449  test    rsi, rsi
0x18001444c  jz      short loc_180014433
0x18001444e  mov     dword ptr [r9], 0
0x180014455  mov     rcx, rdi
0x180014458  mov     rax, [rdx]
0x18001445b  lea     rdx, [rsp+78h+arg_8]
0x180014463  mov     rax, [rax+88h]
0x18001446a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001446f  mov     ecx, eax
0x180014471  test    eax, eax
0x180014473  js      loc_1800144FA
0x180014479  cmp     [rsp+78h+arg_8], 0
0x180014481  jz      short loc_1800144F5
0x180014483  mov     rcx, [rbp+20h]; struct CspNodeMapBase *
0x180014487  test    rcx, rcx
0x18001448a  jz      short loc_1800144F5
0x18001448c  mov     rdx, rdi; struct IConfigManager2URI *
0x18001448f  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x180014494  test    rax, rax
0x180014497  jz      short loc_1800144F5
0x180014499  lea     rcx, [rsp+78h+var_38]
0x18001449e  mov     [rsp+78h+var_30], 0
0x1800144a7  mov     [rsp+78h+var_50], rcx
0x1800144ac  mov     r8, rax
0x1800144af  mov     rax, [rax+20h]
0x1800144b3  lea     rcx, [rsp+78h+var_30]
0x1800144b8  mov     [rsp+78h+var_58], rcx
0x1800144bd  xor     r9d, r9d
0x1800144c0  mov     rcx, rbp
0x1800144c3  mov     [rsp+78h+var_38], 0
0x1800144cb  mov     rdx, rdi
0x1800144ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144d3  mov     ecx, eax
0x1800144d5  test    eax, eax
0x1800144d7  js      short loc_1800144FA
0x1800144d9  mov     rax, [rsp+78h+var_30]
0x1800144de  test    rax, rax
0x1800144e1  jnz     short loc_1800144EA
0x1800144e3  mov     ecx, 8007000Eh
0x1800144e8  jmp     short loc_1800144FA
0x1800144ea  mov     [rbx], rax
0x1800144ed  mov     eax, [rsp+78h+var_38]
0x1800144f1  mov     [rsi], eax
0x1800144f3  jmp     short loc_1800144FA
0x1800144f5  mov     ecx, 86000002h
0x1800144fa  mov     eax, ecx
0x1800144fc  add     rsp, 58h
0x180014500  pop     rdi
0x180014501  pop     rsi
0x180014502  pop     rbp
0x180014503  pop     rbx
0x180014504  retn
```
