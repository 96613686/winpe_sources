# RegistryT<256>::RegistryT<256>(HKEY__ *,ushort const *,bool,_SECURITY_ATTRIBUTES *)

- ea: `0x180024edc`
- end: `0x180024f9c`
- name: `??0?$RegistryT@$0BAA@@@QEAA@PEAUHKEY__@@PEBG_NPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `192`
- prototype: `_QWORD *__fastcall(_QWORD *, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027070`

## callees

- `0x180024e6c`
- `0x180026050`

## pseudocode

```c
_QWORD *__fastcall RegistryT<256>::RegistryT<256>(_QWORD *a1, int a2, int a3)
{
  int v3; // eax
  HKEY v5; // rax
  __int64 v6; // rcx

  v3 = a3;
  a1[4] = &ReadRegistryT<256>::`vbtable';
  a1[1] = &RegistryT<256>::`vbtable'{for `IHierarchicalStorage'};
  a1[6] = &IConstHierarchicalStorage::`vftable';
  LOBYTE(a3) = 1;
  v5 = (HKEY)anonymous_namespace_::CreateOrOpenKey(a2, v3, a3, 131359);
  ReadRegistryT<256>::ReadRegistryT<256>((Private::RegistryBase *)(a1 + 2), v5, 0);
  *a1 = &IHierarchicalStorage::`vftable'{for `IHierarchicalStorage'};
  *(_QWORD *)((char *)a1 + *(int *)(a1[1] + 4LL) + 8) = &IHierarchicalStorage::`vftable'{for `IConstHierarchicalStorage'};
  *a1 = &RegistryT<256>::`vftable'{for `IHierarchicalStorage'};
  *(_QWORD *)((char *)a1 + *(int *)(a1[4] + 4LL) + 32) = &RegistryT<256>::`vftable';
  v6 = *(int *)(a1[4] + 4LL);
  *(_DWORD *)((char *)a1 + v6 + 28) = v6 - 16;
  return a1;
}

```

## disassembly

```asm
0x180024edc  mov     byte ptr [rsp+arg_18], r9b
0x180024ee1  mov     [rsp+arg_0], rcx
0x180024ee6  push    rbx
0x180024ee7  sub     rsp, 30h
0x180024eeb  mov     rax, r8
0x180024eee  mov     r10, rdx
0x180024ef1  mov     rbx, rcx
0x180024ef4  mov     [rsp+38h+arg_18], 0
0x180024efc  lea     rcx, ??_8?$ReadRegistryT@$0BAA@@@7B@; const ReadRegistryT<256>::`vbtable'
0x180024f03  mov     [rbx+20h], rcx
0x180024f07  lea     rcx, ??_8?$RegistryT@$0BAA@@@7BIHierarchicalStorage@@@; const RegistryT<256>::`vbtable'{for `IHierarchicalStorage'}
0x180024f0e  mov     [rbx+8], rcx
0x180024f12  lea     rcx, ??_7IConstHierarchicalStorage@@6B@; const IConstHierarchicalStorage::`vftable'
0x180024f19  mov     [rbx+30h], rcx
0x180024f1d  mov     [rsp+38h+arg_18], 1
0x180024f25  mov     r9d, 2011Fh
0x180024f2b  mov     r8b, 1
0x180024f2e  mov     rdx, rax
0x180024f31  mov     rcx, r10
0x180024f34  call    _anonymous_namespace___CreateOrOpenKey
0x180024f39  mov     rdx, rax
0x180024f3c  lea     rcx, [rbx+10h]
0x180024f40  xor     r8d, r8d
0x180024f43  call    ??0?$ReadRegistryT@$0BAA@@@IEAA@PEAUHKEY__@@@Z; ReadRegistryT<256>::ReadRegistryT<256>(HKEY__ *)
0x180024f48  lea     rax, ??_7IHierarchicalStorage@@6B0@@; const IHierarchicalStorage::`vftable'{for `IHierarchicalStorage'}
0x180024f4f  mov     [rbx], rax
0x180024f52  mov     rax, [rbx+8]
0x180024f56  movsxd  rcx, dword ptr [rax+4]
0x180024f5a  lea     rax, ??_7IHierarchicalStorage@@6BIConstHierarchicalStorage@@@; const IHierarchicalStorage::`vftable'{for `IConstHierarchicalStorage'}
0x180024f61  mov     [rcx+rbx+8], rax
0x180024f66  lea     rax, ??_7?$RegistryT@$0BAA@@@6BIHierarchicalStorage@@@; const RegistryT<256>::`vftable'{for `IHierarchicalStorage'}
0x180024f6d  mov     [rbx], rax
0x180024f70  mov     rax, [rbx+20h]
0x180024f74  movsxd  rcx, dword ptr [rax+4]
0x180024f78  lea     rax, ??_7?$RegistryT@$0BAA@@@6B@; const RegistryT<256>::`vftable'
0x180024f7f  mov     [rcx+rbx+20h], rax
0x180024f84  mov     rax, [rbx+20h]
0x180024f88  movsxd  rcx, dword ptr [rax+4]
0x180024f8c  lea     edx, [rcx-10h]
0x180024f8f  mov     [rcx+rbx+1Ch], edx
0x180024f93  mov     rax, rbx
0x180024f96  add     rsp, 30h
0x180024f9a  pop     rbx
0x180024f9b  retn
```
