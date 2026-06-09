# ATL::CComObject<HtmlDocForParsingSiteUnmarshaller>::Release(void)

- ea: `0x1800046a0`
- end: `0x180004721`
- name: `?Release@?$CComObject@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800046a0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<HtmlDocForParsingSiteUnmarshaller>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800046a0  mov     [rsp+arg_0], rbx
0x1800046a5  push    rdi
0x1800046a6  sub     rsp, 20h
0x1800046aa  mov     r8d, [rcx+8]
0x1800046ae  mov     rbx, rcx
0x1800046b1  mov     ecx, 7FFFFFFFh
0x1800046b6  jmp     short loc_1800046CA
0x1800046b8  lea     edx, [r8-1]
0x1800046bc  mov     eax, r8d
0x1800046bf  lock cmpxchg [rbx+8], edx
0x1800046c4  jz      short loc_1800046CF
0x1800046c6  mov     r8d, [rbx+8]
0x1800046ca  cmp     r8d, ecx
0x1800046cd  jnz     short loc_1800046B8
0x1800046cf  lea     edi, [r8-1]
0x1800046d3  test    edi, edi
0x1800046d5  jnz     short loc_180004714
0x1800046d7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800046de  mov     rax, [rcx]
0x1800046e1  mov     rax, [rax+8]
0x1800046e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ea  test    rbx, rbx
0x1800046ed  jz      short loc_180004701
0x1800046ef  mov     rax, [rbx]
0x1800046f2  lea     edx, [rdi+1]
0x1800046f5  mov     rcx, rbx
0x1800046f8  mov     rax, [rax+48h]
0x1800046fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004701  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004708  mov     rdx, [rcx]
0x18000470b  mov     rax, [rdx+10h]
0x18000470f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004714  mov     rbx, [rsp+28h+arg_0]
0x180004719  mov     eax, edi
0x18000471b  add     rsp, 20h
0x18000471f  pop     rdi
0x180004720  retn
```
