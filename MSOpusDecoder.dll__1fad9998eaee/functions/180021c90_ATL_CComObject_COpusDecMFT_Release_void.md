# ATL::CComObject<COpusDecMFT>::Release(void)

- ea: `0x180021c90`
- end: `0x180021d1d`
- name: `?Release@?$CComObject@VCOpusDecMFT@@@ATL@@UEAAKXZ`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021d30`

## callees

- `0x180021c90`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<COpusDecMFT>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 40);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 40, i - 1, i);
        i = *((_DWORD *)a1 + 40) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 368LL))(a1, v3 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180021c90  mov     [rsp+arg_0], rbx
0x180021c95  push    rdi
0x180021c96  sub     rsp, 20h
0x180021c9a  mov     r8d, [rcx+0A0h]
0x180021ca1  mov     rbx, rcx
0x180021ca4  mov     ecx, 7FFFFFFFh
0x180021ca9  jmp     short loc_180021CC3
0x180021cab  lea     edx, [r8-1]
0x180021caf  mov     eax, r8d
0x180021cb2  lock cmpxchg [rbx+0A0h], edx
0x180021cba  jz      short loc_180021CC8
0x180021cbc  mov     r8d, [rbx+0A0h]
0x180021cc3  cmp     r8d, ecx
0x180021cc6  jnz     short loc_180021CAB
0x180021cc8  lea     edi, [r8-1]
0x180021ccc  test    edi, edi
0x180021cce  jnz     short loc_180021D10
0x180021cd0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180021cd7  mov     rax, [rcx]
0x180021cda  mov     rax, [rax+8]
0x180021cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ce3  test    rbx, rbx
0x180021ce6  jz      short loc_180021CFD
0x180021ce8  mov     rax, [rbx]
0x180021ceb  lea     edx, [rdi+1]
0x180021cee  mov     rcx, rbx
0x180021cf1  mov     rax, [rax+170h]
0x180021cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cfd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180021d04  mov     rdx, [rcx]
0x180021d07  mov     rax, [rdx+10h]
0x180021d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d10  mov     rbx, [rsp+28h+arg_0]
0x180021d15  mov     eax, edi
0x180021d17  add     rsp, 20h
0x180021d1b  pop     rdi
0x180021d1c  retn
```
