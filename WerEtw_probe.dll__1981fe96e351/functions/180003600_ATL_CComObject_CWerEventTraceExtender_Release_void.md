# ATL::CComObject<CWerEventTraceExtender>::Release(void)

- ea: `0x180003600`
- end: `0x180003684`
- name: `?Release@?$CComObject@VCWerEventTraceExtender@@@ATL@@UEAAKXZ`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003600`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWerEventTraceExtender>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 6);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 6, i - 1, i);
        i = *((_DWORD *)a1 + 6) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 136LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180003600  mov     [rsp+arg_0], rbx
0x180003605  push    rdi
0x180003606  sub     rsp, 20h
0x18000360a  mov     r8d, [rcx+18h]
0x18000360e  mov     rbx, rcx
0x180003611  mov     ecx, 7FFFFFFFh
0x180003616  jmp     short loc_18000362A
0x180003618  lea     edx, [r8-1]
0x18000361c  mov     eax, r8d
0x18000361f  lock cmpxchg [rbx+18h], edx
0x180003624  jz      short loc_18000362F
0x180003626  mov     r8d, [rbx+18h]
0x18000362a  cmp     r8d, ecx
0x18000362d  jnz     short loc_180003618
0x18000362f  lea     edi, [r8-1]
0x180003633  test    edi, edi
0x180003635  jnz     short loc_180003677
0x180003637  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000363e  mov     rax, [rcx]
0x180003641  mov     rax, [rax+8]
0x180003645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000364a  test    rbx, rbx
0x18000364d  jz      short loc_180003664
0x18000364f  mov     rax, [rbx]
0x180003652  lea     edx, [rdi+1]
0x180003655  mov     rcx, rbx
0x180003658  mov     rax, [rax+88h]
0x18000365f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003664  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000366b  mov     rdx, [rcx]
0x18000366e  mov     rax, [rdx+10h]
0x180003672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003677  mov     rbx, [rsp+28h+arg_0]
0x18000367c  mov     eax, edi
0x18000367e  add     rsp, 20h
0x180003682  pop     rdi
0x180003683  retn
```
