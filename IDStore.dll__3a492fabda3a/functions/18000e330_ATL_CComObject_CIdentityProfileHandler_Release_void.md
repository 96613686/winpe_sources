# ATL::CComObject<CIdentityProfileHandler>::Release(void)

- ea: `0x18000e330`
- end: `0x18000e396`
- name: `?Release@?$CComObject@VCIdentityProfileHandler@@@ATL@@UEAAKXZ`
- size: `102`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e330`
- `0x18000eb08`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIdentityProfileHandler>::Release(volatile int *a1)
{
  unsigned int v2; // edi

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x18000e330  mov     [rsp+arg_0], rbx
0x18000e335  push    rdi
0x18000e336  sub     rsp, 20h
0x18000e33a  mov     rbx, rcx
0x18000e33d  add     rcx, 8; volatile int *
0x18000e341  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000e346  mov     edi, eax
0x18000e348  test    eax, eax
0x18000e34a  jnz     short loc_18000E389
0x18000e34c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000e353  mov     rdx, [rcx]
0x18000e356  mov     rax, [rdx+8]
0x18000e35a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e35f  test    rbx, rbx
0x18000e362  jz      short loc_18000E376
0x18000e364  mov     rax, [rbx]
0x18000e367  lea     edx, [rdi+1]
0x18000e36a  mov     rcx, rbx
0x18000e36d  mov     rax, [rax+48h]
0x18000e371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e376  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000e37d  mov     rax, [rcx]
0x18000e380  mov     rax, [rax+10h]
0x18000e384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e389  mov     rbx, [rsp+28h+arg_0]
0x18000e38e  mov     eax, edi
0x18000e390  add     rsp, 20h
0x18000e394  pop     rdi
0x18000e395  retn
```
