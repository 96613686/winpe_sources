# ATL::CComObject<FwIcmpSettings>::CComObject<FwIcmpSettings>(void *)

- ea: `0x180020b40`
- end: `0x180020bbb`
- name: `??0?$CComObject@VFwIcmpSettings@@@ATL@@QEAA@PEAX@Z`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026578`

## callees

- `0x180062010`

## import_xrefs

- `FWPolicyIOMgr!CopyIcmpSettings` at `0x180020b5b`
- `FWPolicyIOMgr!CopyIcmpSettings` at `0x180020b5b`
- `FWPolicyIOMgr!CopyIcmpV4Rules` at `0x180020b6e`
- `FWPolicyIOMgr!CopyIcmpV4Rules` at `0x180020b6e`
- `FWPolicyIOMgr!CopyIcmpV6Rules` at `0x180020b81`
- `FWPolicyIOMgr!CopyIcmpV6Rules` at `0x180020b81`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<FwIcmpSettings>::CComObject<FwIcmpSettings>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 24) = 0;
  CopyIcmpSettings((struct FW_ICMP_SETTING_ *)(a1 + 28));
  CopyIcmpV4Rules((struct FW_ICMP_RULE_ *)(a1 + 472));
  CopyIcmpV6Rules((struct FW_ICMP_RULE_ *)(a1 + 760));
  _InterlockedIncrement((_DWORD *)&qword_18009BF88 + 1);
  *(_QWORD *)a1 = &ATL::CComObject<FwIcmpSettings>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return a1;
}

```

## disassembly

```asm
0x180020b40  push    rbx
0x180020b42  sub     rsp, 20h
0x180020b46  mov     rbx, rcx
0x180020b49  mov     dword ptr [rcx+8], 0
0x180020b50  mov     dword ptr [rcx+18h], 0
0x180020b57  add     rcx, 1Ch
0x180020b5b  call    cs:__imp_?CopyIcmpSettings@@YAXPEAUFW_ICMP_SETTING_@@@Z; CopyIcmpSettings(FW_ICMP_SETTING_ *)
0x180020b62  nop     dword ptr [rax+rax+00h]
0x180020b67  lea     rcx, [rbx+1D8h]
0x180020b6e  call    cs:__imp_?CopyIcmpV4Rules@@YAXPEAUFW_ICMP_RULE_@@@Z; CopyIcmpV4Rules(FW_ICMP_RULE_ *)
0x180020b75  nop     dword ptr [rax+rax+00h]
0x180020b7a  lea     rcx, [rbx+2F8h]
0x180020b81  call    cs:__imp_?CopyIcmpV6Rules@@YAXPEAUFW_ICMP_RULE_@@@Z; CopyIcmpV6Rules(FW_ICMP_RULE_ *)
0x180020b88  nop     dword ptr [rax+rax+00h]
0x180020b8d  lock inc dword ptr cs:qword_18009BF88+4
0x180020b94  lea     rax, ??_7?$CComObject@VFwIcmpSettings@@@ATL@@6B@; const ATL::CComObject<FwIcmpSettings>::`vftable'
0x180020b9b  mov     [rbx], rax
0x180020b9e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180020ba5  mov     rax, [rcx]
0x180020ba8  mov     rax, [rax+8]
0x180020bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bb1  mov     rax, rbx
0x180020bb4  add     rsp, 20h
0x180020bb8  pop     rbx
0x180020bb9  retn
```
