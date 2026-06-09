# ATL::CComAggObject<HtmlDocForParsingSiteUnmarshaller>::Release(void)

- ea: `0x1800045f0`
- end: `0x180004671`
- name: `?Release@?$CComAggObject@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800045f0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<HtmlDocForParsingSiteUnmarshaller>::Release(volatile signed __int32 *a1)
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
0x1800045f0  mov     [rsp+arg_0], rbx
0x1800045f5  push    rdi
0x1800045f6  sub     rsp, 20h
0x1800045fa  mov     r8d, [rcx+8]
0x1800045fe  mov     rbx, rcx
0x180004601  mov     ecx, 7FFFFFFFh
0x180004606  jmp     short loc_18000461A
0x180004608  lea     edx, [r8-1]
0x18000460c  mov     eax, r8d
0x18000460f  lock cmpxchg [rbx+8], edx
0x180004614  jz      short loc_18000461F
0x180004616  mov     r8d, [rbx+8]
0x18000461a  cmp     r8d, ecx
0x18000461d  jnz     short loc_180004608
0x18000461f  lea     edi, [r8-1]
0x180004623  test    edi, edi
0x180004625  jnz     short loc_180004664
0x180004627  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000462e  mov     rax, [rcx]
0x180004631  mov     rax, [rax+8]
0x180004635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000463a  test    rbx, rbx
0x18000463d  jz      short loc_180004651
0x18000463f  mov     rax, [rbx]
0x180004642  lea     edx, [rdi+1]
0x180004645  mov     rcx, rbx
0x180004648  mov     rax, [rax+18h]
0x18000464c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004651  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004658  mov     rdx, [rcx]
0x18000465b  mov     rax, [rdx+10h]
0x18000465f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004664  mov     rbx, [rsp+28h+arg_0]
0x180004669  mov     eax, edi
0x18000466b  add     rsp, 20h
0x18000466f  pop     rdi
0x180004670  retn
```
