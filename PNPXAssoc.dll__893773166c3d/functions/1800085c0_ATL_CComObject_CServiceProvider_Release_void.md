# ATL::CComObject<CServiceProvider>::Release(void)

- ea: `0x1800085c0`
- end: `0x180008641`
- name: `?Release@?$CComObject@VCServiceProvider@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008650`
- `0x180008660`
- `0x180008670`

## callees

- `0x1800085c0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CServiceProvider>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 8);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 8, i - 1, i);
        i = *((_DWORD *)a1 + 8) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 48LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800085c0  mov     [rsp+arg_0], rbx
0x1800085c5  push    rdi
0x1800085c6  sub     rsp, 20h
0x1800085ca  mov     r8d, [rcx+20h]
0x1800085ce  mov     rbx, rcx
0x1800085d1  mov     ecx, 7FFFFFFFh
0x1800085d6  jmp     short loc_1800085EA
0x1800085d8  lea     edx, [r8-1]
0x1800085dc  mov     eax, r8d
0x1800085df  lock cmpxchg [rbx+20h], edx
0x1800085e4  jz      short loc_1800085EF
0x1800085e6  mov     r8d, [rbx+20h]
0x1800085ea  cmp     r8d, ecx
0x1800085ed  jnz     short loc_1800085D8
0x1800085ef  lea     edi, [r8-1]
0x1800085f3  test    edi, edi
0x1800085f5  jnz     short loc_180008634
0x1800085f7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800085fe  mov     rax, [rcx]
0x180008601  mov     rax, [rax+8]
0x180008605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000860a  test    rbx, rbx
0x18000860d  jz      short loc_180008621
0x18000860f  mov     rax, [rbx]
0x180008612  lea     edx, [rdi+1]
0x180008615  mov     rcx, rbx
0x180008618  mov     rax, [rax+30h]
0x18000861c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008621  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008628  mov     rdx, [rcx]
0x18000862b  mov     rax, [rdx+10h]
0x18000862f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008634  mov     rbx, [rsp+28h+arg_0]
0x180008639  mov     eax, edi
0x18000863b  add     rsp, 20h
0x18000863f  pop     rdi
0x180008640  retn
```
