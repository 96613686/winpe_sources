# ATL::CComObject<CTieringEngineTaskHandler>::Release(void)

- ea: `0x140003d30`
- end: `0x140003db1`
- name: `?Release@?$CComObject@VCTieringEngineTaskHandler@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140003d30`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CTieringEngineTaskHandler>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(CTieringEngineService *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, v3 + 1);
    (*(void (__fastcall **)(CTieringEngineService *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x140003d30  mov     [rsp+arg_0], rbx
0x140003d35  push    rdi
0x140003d36  sub     rsp, 20h
0x140003d3a  mov     r8d, [rcx+8]
0x140003d3e  mov     rbx, rcx
0x140003d41  mov     ecx, 7FFFFFFFh
0x140003d46  jmp     short loc_140003D5A
0x140003d48  lea     edx, [r8-1]
0x140003d4c  mov     eax, r8d
0x140003d4f  lock cmpxchg [rbx+8], edx
0x140003d54  jz      short loc_140003D5F
0x140003d56  mov     r8d, [rbx+8]
0x140003d5a  cmp     r8d, ecx
0x140003d5d  jnz     short loc_140003D48
0x140003d5f  lea     edi, [r8-1]
0x140003d63  test    edi, edi
0x140003d65  jnz     short loc_140003DA4
0x140003d67  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140003d6e  mov     rax, [rcx]
0x140003d71  mov     rax, [rax+8]
0x140003d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d7a  test    rbx, rbx
0x140003d7d  jz      short loc_140003D91
0x140003d7f  mov     rax, [rbx]
0x140003d82  lea     edx, [rdi+1]
0x140003d85  mov     rcx, rbx
0x140003d88  mov     rax, [rax+38h]
0x140003d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d91  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140003d98  mov     rdx, [rcx]
0x140003d9b  mov     rax, [rdx+10h]
0x140003d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003da4  mov     rbx, [rsp+28h+arg_0]
0x140003da9  mov     eax, edi
0x140003dab  add     rsp, 20h
0x140003daf  pop     rdi
0x140003db0  retn
```
