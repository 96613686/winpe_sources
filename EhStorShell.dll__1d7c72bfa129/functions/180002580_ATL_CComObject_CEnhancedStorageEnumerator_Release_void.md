# ATL::CComObject<CEnhancedStorageEnumerator>::Release(void)

- ea: `0x180002580`
- end: `0x1800025fe`
- name: `?Release@?$CComObject@VCEnhancedStorageEnumerator@@@ATL@@UEAAKXZ`
- size: `126`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002580`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageEnumerator>::Release(_DWORD *a1)
{
  int v1; // edi
  unsigned int v3; // edi

  v1 = a1[2];
  if ( v1 == 0x7FFFFFFF )
    return 2147483646;
  v3 = v1 - 1;
  a1[2] = v3;
  if ( !v3 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 56LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180002580  mov     [rsp+arg_0], rbx
0x180002585  push    rdi
0x180002586  sub     rsp, 20h
0x18000258a  mov     edi, [rcx+8]
0x18000258d  mov     rbx, rcx
0x180002590  cmp     edi, 7FFFFFFFh
0x180002596  jz      short loc_1800025EE
0x180002598  sub     edi, 1
0x18000259b  mov     [rcx+8], edi
0x18000259e  jz      short loc_1800025AD
0x1800025a0  mov     eax, edi
0x1800025a2  mov     rbx, [rsp+28h+arg_0]
0x1800025a7  add     rsp, 20h
0x1800025ab  pop     rdi
0x1800025ac  retn
0x1800025ad  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800025b4  mov     rax, [rcx]
0x1800025b7  mov     rax, [rax+8]
0x1800025bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025c0  test    rbx, rbx
0x1800025c3  jz      short loc_1800025D9
0x1800025c5  mov     rax, [rbx]
0x1800025c8  mov     edx, 1
0x1800025cd  mov     rcx, rbx
0x1800025d0  mov     rax, [rax+38h]
0x1800025d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025d9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800025e0  mov     rdx, [rcx]
0x1800025e3  mov     rax, [rdx+10h]
0x1800025e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ec  jmp     short loc_1800025A0
0x1800025ee  mov     rbx, [rsp+28h+arg_0]
0x1800025f3  mov     eax, 7FFFFFFEh
0x1800025f8  add     rsp, 20h
0x1800025fc  pop     rdi
0x1800025fd  retn
```
