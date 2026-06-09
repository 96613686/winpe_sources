# RegistryT<256>::RegistryT<256>(ushort const *)

- ea: `0x180024fa4`
- end: `0x180025066`
- name: `??0?$RegistryT@$0BAA@@@QEAA@PEBG@Z`
- size: `194`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016bfc`
- `0x1800184e8`
- `0x180018d94`

## callees

- `0x180024e6c`
- `0x180026050`

## pseudocode

```c
_QWORD *__fastcall RegistryT<256>::RegistryT<256>(_QWORD *a1)
{
  HKEY v2; // rax
  __int64 v3; // rcx

  a1[4] = &ReadRegistryT<256>::`vbtable';
  a1[1] = &RegistryT<256>::`vbtable'{for `IHierarchicalStorage'};
  a1[6] = &IConstHierarchicalStorage::`vftable';
  v2 = (HKEY)anonymous_namespace_::CreateOrOpenKey(
               -2147483646,
               (unsigned int)L"Software\\Microsoft\\Windows\\CurrentVersion\\Parental Controls",
               1,
               131359);
  ReadRegistryT<256>::ReadRegistryT<256>((Private::RegistryBase *)(a1 + 2), v2, 0);
  *a1 = &IHierarchicalStorage::`vftable'{for `IHierarchicalStorage'};
  *(_QWORD *)((char *)a1 + *(int *)(a1[1] + 4LL) + 8) = &IHierarchicalStorage::`vftable'{for `IConstHierarchicalStorage'};
  *a1 = &RegistryT<256>::`vftable'{for `IHierarchicalStorage'};
  *(_QWORD *)((char *)a1 + *(int *)(a1[4] + 4LL) + 32) = &RegistryT<256>::`vftable';
  v3 = *(int *)(a1[4] + 4LL);
  *(_DWORD *)((char *)a1 + v3 + 28) = v3 - 16;
  return a1;
}

```

## disassembly

```asm
0x180024fa4  mov     [rsp+arg_10], r8d
0x180024fa9  mov     [rsp+arg_0], rcx
0x180024fae  push    rbx
0x180024faf  sub     rsp, 30h
0x180024fb3  mov     rbx, rcx
0x180024fb6  mov     [rsp+38h+arg_10], 0
0x180024fbe  lea     rax, ??_8?$ReadRegistryT@$0BAA@@@7B@; const ReadRegistryT<256>::`vbtable'
0x180024fc5  mov     [rcx+20h], rax
0x180024fc9  lea     rax, ??_8?$RegistryT@$0BAA@@@7BIHierarchicalStorage@@@; const RegistryT<256>::`vbtable'{for `IHierarchicalStorage'}
0x180024fd0  mov     [rcx+8], rax
0x180024fd4  lea     rax, ??_7IConstHierarchicalStorage@@6B@; const IConstHierarchicalStorage::`vftable'
0x180024fdb  mov     [rcx+30h], rax
0x180024fdf  mov     [rsp+38h+arg_10], 1
0x180024fe7  mov     r9d, 2011Fh
0x180024fed  mov     r8b, 1
0x180024ff0  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180024ff7  mov     rcx, 0FFFFFFFF80000002h
0x180024ffe  call    _anonymous_namespace___CreateOrOpenKey
0x180025003  mov     rdx, rax
0x180025006  lea     rcx, [rbx+10h]
0x18002500a  xor     r8d, r8d
0x18002500d  call    ??0?$ReadRegistryT@$0BAA@@@IEAA@PEAUHKEY__@@@Z; ReadRegistryT<256>::ReadRegistryT<256>(HKEY__ *)
0x180025012  lea     rax, ??_7IHierarchicalStorage@@6B0@@; const IHierarchicalStorage::`vftable'{for `IHierarchicalStorage'}
0x180025019  mov     [rbx], rax
0x18002501c  mov     rax, [rbx+8]
0x180025020  movsxd  rcx, dword ptr [rax+4]
0x180025024  lea     rax, ??_7IHierarchicalStorage@@6BIConstHierarchicalStorage@@@; const IHierarchicalStorage::`vftable'{for `IConstHierarchicalStorage'}
0x18002502b  mov     [rcx+rbx+8], rax
0x180025030  lea     rax, ??_7?$RegistryT@$0BAA@@@6BIHierarchicalStorage@@@; const RegistryT<256>::`vftable'{for `IHierarchicalStorage'}
0x180025037  mov     [rbx], rax
0x18002503a  mov     rax, [rbx+20h]
0x18002503e  movsxd  rcx, dword ptr [rax+4]
0x180025042  lea     rax, ??_7?$RegistryT@$0BAA@@@6B@; const RegistryT<256>::`vftable'
0x180025049  mov     [rcx+rbx+20h], rax
0x18002504e  mov     rax, [rbx+20h]
0x180025052  movsxd  rcx, dword ptr [rax+4]
0x180025056  lea     edx, [rcx-10h]
0x180025059  mov     [rcx+rbx+1Ch], edx
0x18002505d  mov     rax, rbx
0x180025060  add     rsp, 30h
0x180025064  pop     rbx
0x180025065  retn
```
