# ATL::CComObject<CMidi2DiagnosticsTransport>::Release(void)

- ea: `0x180008c80`
- end: `0x180008d01`
- name: `?Release@?$CComObject@VCMidi2DiagnosticsTransport@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008c80`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMidi2DiagnosticsTransport>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180008c80  mov     [rsp+arg_0], rbx
0x180008c85  push    rdi
0x180008c86  sub     rsp, 20h
0x180008c8a  mov     r8d, [rcx+8]
0x180008c8e  mov     rbx, rcx
0x180008c91  mov     ecx, 7FFFFFFFh
0x180008c96  jmp     short loc_180008CAA
0x180008c98  lea     edx, [r8-1]
0x180008c9c  mov     eax, r8d
0x180008c9f  lock cmpxchg [rbx+8], edx
0x180008ca4  jz      short loc_180008CAF
0x180008ca6  mov     r8d, [rbx+8]
0x180008caa  cmp     r8d, ecx
0x180008cad  jnz     short loc_180008C98
0x180008caf  lea     edi, [r8-1]
0x180008cb3  test    edi, edi
0x180008cb5  jnz     short loc_180008CF4
0x180008cb7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008cbe  mov     rax, [rcx]
0x180008cc1  mov     rax, [rax+8]
0x180008cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cca  test    rbx, rbx
0x180008ccd  jz      short loc_180008CE1
0x180008ccf  mov     rax, [rbx]
0x180008cd2  lea     edx, [rdi+1]
0x180008cd5  mov     rcx, rbx
0x180008cd8  mov     rax, [rax+20h]
0x180008cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ce1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008ce8  mov     rdx, [rcx]
0x180008ceb  mov     rax, [rdx+10h]
0x180008cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cf4  mov     rbx, [rsp+28h+arg_0]
0x180008cf9  mov     eax, edi
0x180008cfb  add     rsp, 20h
0x180008cff  pop     rdi
0x180008d00  retn
```
