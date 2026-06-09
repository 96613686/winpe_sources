# ATL::CComObject<CEnhancedStorageFolder>::Release(void)

- ea: `0x1800024f0`
- end: `0x18000256e`
- name: `?Release@?$CComObject@VCEnhancedStorageFolder@@@ATL@@UEAAKXZ`
- size: `126`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009090`
- `0x1800090a0`

## callees

- `0x1800024f0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageFolder>::Release(_DWORD *a1)
{
  int v1; // ebx
  unsigned int v3; // ebx

  v1 = a1[8];
  if ( v1 == 0x7FFFFFFF )
    return 2147483646;
  v3 = v1 - 1;
  a1[8] = v3;
  if ( !v3 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 32LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800024f0  mov     [rsp+arg_0], rbx
0x1800024f5  push    rdi
0x1800024f6  sub     rsp, 20h
0x1800024fa  mov     ebx, [rcx+20h]
0x1800024fd  mov     rdi, rcx
0x180002500  cmp     ebx, 7FFFFFFFh
0x180002506  jz      short loc_18000255E
0x180002508  sub     ebx, 1
0x18000250b  mov     [rcx+20h], ebx
0x18000250e  jz      short loc_18000251D
0x180002510  mov     eax, ebx
0x180002512  mov     rbx, [rsp+28h+arg_0]
0x180002517  add     rsp, 20h
0x18000251b  pop     rdi
0x18000251c  retn
0x18000251d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002524  mov     rax, [rcx]
0x180002527  mov     rax, [rax+8]
0x18000252b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002530  test    rdi, rdi
0x180002533  jz      short loc_180002549
0x180002535  mov     rax, [rdi]
0x180002538  mov     edx, 1
0x18000253d  mov     rcx, rdi
0x180002540  mov     rax, [rax+20h]
0x180002544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002549  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002550  mov     rax, [rcx]
0x180002553  mov     rax, [rax+10h]
0x180002557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000255c  jmp     short loc_180002510
0x18000255e  mov     rbx, [rsp+28h+arg_0]
0x180002563  mov     eax, 7FFFFFFEh
0x180002568  add     rsp, 20h
0x18000256c  pop     rdi
0x18000256d  retn
```
