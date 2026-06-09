# ATL::CComObject<CTieringEngineApiServer>::Release(void)

- ea: `0x140003ca0`
- end: `0x140003d24`
- name: `?Release@?$CComObject@VCTieringEngineApiServer@@@ATL@@UEAAKXZ`
- size: `132`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003ca0`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CTieringEngineApiServer>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 200LL))(a1, v3 + 1);
    (*(void (__fastcall **)(CTieringEngineService *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x140003ca0  mov     [rsp+arg_0], rbx
0x140003ca5  push    rdi
0x140003ca6  sub     rsp, 20h
0x140003caa  mov     r8d, [rcx+8]
0x140003cae  mov     rbx, rcx
0x140003cb1  mov     ecx, 7FFFFFFFh
0x140003cb6  jmp     short loc_140003CCA
0x140003cb8  lea     edx, [r8-1]
0x140003cbc  mov     eax, r8d
0x140003cbf  lock cmpxchg [rbx+8], edx
0x140003cc4  jz      short loc_140003CCF
0x140003cc6  mov     r8d, [rbx+8]
0x140003cca  cmp     r8d, ecx
0x140003ccd  jnz     short loc_140003CB8
0x140003ccf  lea     edi, [r8-1]
0x140003cd3  test    edi, edi
0x140003cd5  jnz     short loc_140003D17
0x140003cd7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140003cde  mov     rax, [rcx]
0x140003ce1  mov     rax, [rax+8]
0x140003ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cea  test    rbx, rbx
0x140003ced  jz      short loc_140003D04
0x140003cef  mov     rax, [rbx]
0x140003cf2  lea     edx, [rdi+1]
0x140003cf5  mov     rcx, rbx
0x140003cf8  mov     rax, [rax+0C8h]
0x140003cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d04  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140003d0b  mov     rdx, [rcx]
0x140003d0e  mov     rax, [rdx+10h]
0x140003d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d17  mov     rbx, [rsp+28h+arg_0]
0x140003d1c  mov     eax, edi
0x140003d1e  add     rsp, 20h
0x140003d22  pop     rdi
0x140003d23  retn
```
