# ATL::CComAggObject<CServiceProvider>::Release(void)

- ea: `0x1800083f0`
- end: `0x180008471`
- name: `?Release@?$CComAggObject@VCServiceProvider@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800083f0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CServiceProvider>::Release(volatile signed __int32 *a1)
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
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800083f0  mov     [rsp+arg_0], rbx
0x1800083f5  push    rdi
0x1800083f6  sub     rsp, 20h
0x1800083fa  mov     r8d, [rcx+8]
0x1800083fe  mov     rbx, rcx
0x180008401  mov     ecx, 7FFFFFFFh
0x180008406  jmp     short loc_18000841A
0x180008408  lea     edx, [r8-1]
0x18000840c  mov     eax, r8d
0x18000840f  lock cmpxchg [rbx+8], edx
0x180008414  jz      short loc_18000841F
0x180008416  mov     r8d, [rbx+8]
0x18000841a  cmp     r8d, ecx
0x18000841d  jnz     short loc_180008408
0x18000841f  lea     edi, [r8-1]
0x180008423  test    edi, edi
0x180008425  jnz     short loc_180008464
0x180008427  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000842e  mov     rax, [rcx]
0x180008431  mov     rax, [rax+8]
0x180008435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000843a  test    rbx, rbx
0x18000843d  jz      short loc_180008451
0x18000843f  mov     rax, [rbx]
0x180008442  lea     edx, [rdi+1]
0x180008445  mov     rcx, rbx
0x180008448  mov     rax, [rax+18h]
0x18000844c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008451  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008458  mov     rdx, [rcx]
0x18000845b  mov     rax, [rdx+10h]
0x18000845f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008464  mov     rbx, [rsp+28h+arg_0]
0x180008469  mov     eax, edi
0x18000846b  add     rsp, 20h
0x18000846f  pop     rdi
0x180008470  retn
```
