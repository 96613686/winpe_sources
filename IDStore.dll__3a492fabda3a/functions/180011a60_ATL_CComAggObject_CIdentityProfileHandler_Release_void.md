# ATL::CComAggObject<CIdentityProfileHandler>::Release(void)

- ea: `0x180011a60`
- end: `0x180011abd`
- name: `?Release@?$CComAggObject@VCIdentityProfileHandler@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000da50`
- `0x18000eb08`
- `0x180011a60`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CIdentityProfileHandler>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180011a60  mov     [rsp+arg_8], rbx
0x180011a65  push    rdi
0x180011a66  sub     rsp, 20h
0x180011a6a  mov     rbx, rcx
0x180011a6d  add     rcx, 8; volatile int *
0x180011a71  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180011a76  mov     edi, eax
0x180011a78  test    eax, eax
0x180011a7a  jnz     short loc_180011AB0
0x180011a7c  lea     rcx, [rsp+28h+arg_0]; this
0x180011a81  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180011a86  test    rbx, rbx
0x180011a89  jz      short loc_180011A9D
0x180011a8b  mov     rdx, [rbx]
0x180011a8e  mov     rcx, rbx
0x180011a91  mov     rax, [rdx+18h]
0x180011a95  lea     edx, [rdi+1]
0x180011a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a9d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011aa4  mov     rax, [rcx]
0x180011aa7  mov     rax, [rax+10h]
0x180011aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ab0  mov     rbx, [rsp+28h+arg_8]
0x180011ab5  mov     eax, edi
0x180011ab7  add     rsp, 20h
0x180011abb  pop     rdi
0x180011abc  retn
```
