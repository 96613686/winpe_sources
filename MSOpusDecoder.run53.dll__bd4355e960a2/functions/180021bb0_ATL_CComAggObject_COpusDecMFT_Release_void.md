# ATL::CComAggObject<COpusDecMFT>::Release(void)

- ea: `0x180021bb0`
- end: `0x180021c31`
- name: `?Release@?$CComAggObject@VCOpusDecMFT@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180021bb0`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<COpusDecMFT>::Release(volatile signed __int32 *a1)
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
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v3 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180021bb0  mov     [rsp+arg_0], rbx
0x180021bb5  push    rdi
0x180021bb6  sub     rsp, 20h
0x180021bba  mov     r8d, [rcx+8]
0x180021bbe  mov     rbx, rcx
0x180021bc1  mov     ecx, 7FFFFFFFh
0x180021bc6  jmp     short loc_180021BDA
0x180021bc8  lea     edx, [r8-1]
0x180021bcc  mov     eax, r8d
0x180021bcf  lock cmpxchg [rbx+8], edx
0x180021bd4  jz      short loc_180021BDF
0x180021bd6  mov     r8d, [rbx+8]
0x180021bda  cmp     r8d, ecx
0x180021bdd  jnz     short loc_180021BC8
0x180021bdf  lea     edi, [r8-1]
0x180021be3  test    edi, edi
0x180021be5  jnz     short loc_180021C24
0x180021be7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180021bee  mov     rax, [rcx]
0x180021bf1  mov     rax, [rax+8]
0x180021bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bfa  test    rbx, rbx
0x180021bfd  jz      short loc_180021C11
0x180021bff  mov     rax, [rbx]
0x180021c02  lea     edx, [rdi+1]
0x180021c05  mov     rcx, rbx
0x180021c08  mov     rax, [rax+18h]
0x180021c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c11  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180021c18  mov     rdx, [rcx]
0x180021c1b  mov     rax, [rdx+10h]
0x180021c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c24  mov     rbx, [rsp+28h+arg_0]
0x180021c29  mov     eax, edi
0x180021c2b  add     rsp, 20h
0x180021c2f  pop     rdi
0x180021c30  retn
```
