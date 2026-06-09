# ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::Release(void)

- ea: `0x1400107a0`
- end: `0x140010821`
- name: `?Release@?$CComObject@VCHostProviderFactory@Spelling@Globalization@Windows@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400107a0`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::Release(
        volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1400107a0  mov     [rsp+arg_0], rbx
0x1400107a5  push    rdi
0x1400107a6  sub     rsp, 20h
0x1400107aa  mov     r8d, [rcx+8]
0x1400107ae  mov     rbx, rcx
0x1400107b1  mov     ecx, 7FFFFFFFh
0x1400107b6  jmp     short loc_1400107CA
0x1400107b8  lea     edx, [r8-1]
0x1400107bc  mov     eax, r8d
0x1400107bf  lock cmpxchg [rbx+8], edx
0x1400107c4  jz      short loc_1400107CF
0x1400107c6  mov     r8d, [rbx+8]
0x1400107ca  cmp     r8d, ecx
0x1400107cd  jnz     short loc_1400107B8
0x1400107cf  lea     edi, [r8-1]
0x1400107d3  test    edi, edi
0x1400107d5  jnz     short loc_140010814
0x1400107d7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400107de  mov     rax, [rcx]
0x1400107e1  mov     rax, [rax+8]
0x1400107e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400107ea  test    rbx, rbx
0x1400107ed  jz      short loc_140010801
0x1400107ef  mov     rax, [rbx]
0x1400107f2  lea     edx, [rdi+1]
0x1400107f5  mov     rcx, rbx
0x1400107f8  mov     rax, [rax+38h]
0x1400107fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010801  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140010808  mov     rdx, [rcx]
0x14001080b  mov     rax, [rdx+10h]
0x14001080f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010814  mov     rbx, [rsp+28h+arg_0]
0x140010819  mov     eax, edi
0x14001081b  add     rsp, 20h
0x14001081f  pop     rdi
0x140010820  retn
```
