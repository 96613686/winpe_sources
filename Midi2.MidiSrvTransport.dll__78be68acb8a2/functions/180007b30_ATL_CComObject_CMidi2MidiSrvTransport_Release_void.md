# ATL::CComObject<CMidi2MidiSrvTransport>::Release(void)

- ea: `0x180007b30`
- end: `0x180007bb1`
- name: `?Release@?$CComObject@VCMidi2MidiSrvTransport@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007b30`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMidi2MidiSrvTransport>::Release(volatile signed __int32 *a1)
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
0x180007b30  mov     [rsp+arg_0], rbx
0x180007b35  push    rdi
0x180007b36  sub     rsp, 20h
0x180007b3a  mov     r8d, [rcx+8]
0x180007b3e  mov     rbx, rcx
0x180007b41  mov     ecx, 7FFFFFFFh
0x180007b46  jmp     short loc_180007B5A
0x180007b48  lea     edx, [r8-1]
0x180007b4c  mov     eax, r8d
0x180007b4f  lock cmpxchg [rbx+8], edx
0x180007b54  jz      short loc_180007B5F
0x180007b56  mov     r8d, [rbx+8]
0x180007b5a  cmp     r8d, ecx
0x180007b5d  jnz     short loc_180007B48
0x180007b5f  lea     edi, [r8-1]
0x180007b63  test    edi, edi
0x180007b65  jnz     short loc_180007BA4
0x180007b67  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007b6e  mov     rax, [rcx]
0x180007b71  mov     rax, [rax+8]
0x180007b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b7a  test    rbx, rbx
0x180007b7d  jz      short loc_180007B91
0x180007b7f  mov     rax, [rbx]
0x180007b82  lea     edx, [rdi+1]
0x180007b85  mov     rcx, rbx
0x180007b88  mov     rax, [rax+20h]
0x180007b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b91  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007b98  mov     rdx, [rcx]
0x180007b9b  mov     rax, [rdx+10h]
0x180007b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ba4  mov     rbx, [rsp+28h+arg_0]
0x180007ba9  mov     eax, edi
0x180007bab  add     rsp, 20h
0x180007baf  pop     rdi
0x180007bb0  retn
```
