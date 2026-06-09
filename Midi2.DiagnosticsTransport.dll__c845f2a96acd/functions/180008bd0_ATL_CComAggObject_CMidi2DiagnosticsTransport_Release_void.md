# ATL::CComAggObject<CMidi2DiagnosticsTransport>::Release(void)

- ea: `0x180008bd0`
- end: `0x180008c51`
- name: `?Release@?$CComAggObject@VCMidi2DiagnosticsTransport@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008bd0`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMidi2DiagnosticsTransport>::Release(volatile signed __int32 *a1)
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
0x180008bd0  mov     [rsp+arg_0], rbx
0x180008bd5  push    rdi
0x180008bd6  sub     rsp, 20h
0x180008bda  mov     r8d, [rcx+8]
0x180008bde  mov     rbx, rcx
0x180008be1  mov     ecx, 7FFFFFFFh
0x180008be6  jmp     short loc_180008BFA
0x180008be8  lea     edx, [r8-1]
0x180008bec  mov     eax, r8d
0x180008bef  lock cmpxchg [rbx+8], edx
0x180008bf4  jz      short loc_180008BFF
0x180008bf6  mov     r8d, [rbx+8]
0x180008bfa  cmp     r8d, ecx
0x180008bfd  jnz     short loc_180008BE8
0x180008bff  lea     edi, [r8-1]
0x180008c03  test    edi, edi
0x180008c05  jnz     short loc_180008C44
0x180008c07  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008c0e  mov     rax, [rcx]
0x180008c11  mov     rax, [rax+8]
0x180008c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c1a  test    rbx, rbx
0x180008c1d  jz      short loc_180008C31
0x180008c1f  mov     rax, [rbx]
0x180008c22  lea     edx, [rdi+1]
0x180008c25  mov     rcx, rbx
0x180008c28  mov     rax, [rax+18h]
0x180008c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c31  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008c38  mov     rdx, [rcx]
0x180008c3b  mov     rax, [rdx+10h]
0x180008c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c44  mov     rbx, [rsp+28h+arg_0]
0x180008c49  mov     eax, edi
0x180008c4b  add     rsp, 20h
0x180008c4f  pop     rdi
0x180008c50  retn
```
