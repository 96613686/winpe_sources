# ReadRegistryT<256>::ReadRegistryT<256>(HKEY__ *)

- ea: `0x180024e6c`
- end: `0x180024ed5`
- name: `??0?$ReadRegistryT@$0BAA@@@IEAA@PEAUHKEY__@@@Z`
- size: `105`
- prototype: `Private::RegistryBase *__fastcall(Private::RegistryBase *, HKEY, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180024edc`
- `0x180024fa4`
- `0x180026734`

## callees

- `0x180024e6c`
- `0x180025374`

## pseudocode

```c
Private::RegistryBase *__fastcall ReadRegistryT<256>::ReadRegistryT<256>(Private::RegistryBase *a1, HKEY a2, int a3)
{
  __int64 v4; // rcx

  if ( a3 )
  {
    *((_QWORD *)a1 + 2) = &ReadRegistryT<256>::`vbtable';
    *((_QWORD *)a1 + 4) = &IConstHierarchicalStorage::`vftable';
  }
  Private::RegistryBase::RegistryBase(a1, a2);
  *(_QWORD *)((char *)a1 + *(int *)(*((_QWORD *)a1 + 2) + 4LL) + 16) = &ReadRegistryT<256>::`vftable';
  v4 = *(int *)(*((_QWORD *)a1 + 2) + 4LL);
  *(_DWORD *)((char *)a1 + v4 + 12) = v4 - 16;
  return a1;
}

```

## disassembly

```asm
0x180024e6c  mov     [rsp+arg_0], rcx
0x180024e71  push    rbx
0x180024e72  sub     rsp, 20h
0x180024e76  mov     rbx, rcx
0x180024e79  mov     [rsp+28h+arg_10], 0
0x180024e81  test    r8d, r8d
0x180024e84  jz      short loc_180024EA4
0x180024e86  lea     rax, ??_8?$ReadRegistryT@$0BAA@@@7B@; const ReadRegistryT<256>::`vbtable'
0x180024e8d  mov     [rcx+10h], rax
0x180024e91  lea     rax, ??_7IConstHierarchicalStorage@@6B@; const IConstHierarchicalStorage::`vftable'
0x180024e98  mov     [rcx+20h], rax
0x180024e9c  mov     [rsp+28h+arg_10], 1
0x180024ea4  call    ??0RegistryBase@Private@@IEAA@PEAUHKEY__@@@Z; Private::RegistryBase::RegistryBase(HKEY__ *)
0x180024ea9  mov     rax, [rbx+10h]
0x180024ead  movsxd  rcx, dword ptr [rax+4]
0x180024eb1  lea     rax, ??_7?$ReadRegistryT@$0BAA@@@6B@; const ReadRegistryT<256>::`vftable'
0x180024eb8  mov     [rcx+rbx+10h], rax
0x180024ebd  mov     rax, [rbx+10h]
0x180024ec1  movsxd  rcx, dword ptr [rax+4]
0x180024ec5  lea     edx, [rcx-10h]
0x180024ec8  mov     [rcx+rbx+0Ch], edx
0x180024ecc  mov     rax, rbx
0x180024ecf  add     rsp, 20h
0x180024ed3  pop     rbx
0x180024ed4  retn
```
