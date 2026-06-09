# ATL::CComAggObject<CMidi2VirtualMidiTransport>::Release(void)

- ea: `0x1800092a0`
- end: `0x180009321`
- name: `?Release@?$CComAggObject@VCMidi2VirtualMidiTransport@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800092a0`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMidi2VirtualMidiTransport>::Release(volatile signed __int32 *a1)
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
0x1800092a0  mov     [rsp+arg_0], rbx
0x1800092a5  push    rdi
0x1800092a6  sub     rsp, 20h
0x1800092aa  mov     r8d, [rcx+8]
0x1800092ae  mov     rbx, rcx
0x1800092b1  mov     ecx, 7FFFFFFFh
0x1800092b6  jmp     short loc_1800092CA
0x1800092b8  lea     edx, [r8-1]
0x1800092bc  mov     eax, r8d
0x1800092bf  lock cmpxchg [rbx+8], edx
0x1800092c4  jz      short loc_1800092CF
0x1800092c6  mov     r8d, [rbx+8]
0x1800092ca  cmp     r8d, ecx
0x1800092cd  jnz     short loc_1800092B8
0x1800092cf  lea     edi, [r8-1]
0x1800092d3  test    edi, edi
0x1800092d5  jnz     short loc_180009314
0x1800092d7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800092de  mov     rax, [rcx]
0x1800092e1  mov     rax, [rax+8]
0x1800092e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092ea  test    rbx, rbx
0x1800092ed  jz      short loc_180009301
0x1800092ef  mov     rax, [rbx]
0x1800092f2  lea     edx, [rdi+1]
0x1800092f5  mov     rcx, rbx
0x1800092f8  mov     rax, [rax+18h]
0x1800092fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009301  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009308  mov     rdx, [rcx]
0x18000930b  mov     rax, [rdx+10h]
0x18000930f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009314  mov     rbx, [rsp+28h+arg_0]
0x180009319  mov     eax, edi
0x18000931b  add     rsp, 20h
0x18000931f  pop     rdi
0x180009320  retn
```
