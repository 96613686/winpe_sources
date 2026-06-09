# ATL::CComAggObject<CMidi2MidiSrvTransport>::Release(void)

- ea: `0x180007a80`
- end: `0x180007b01`
- name: `?Release@?$CComAggObject@VCMidi2MidiSrvTransport@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007a80`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMidi2MidiSrvTransport>::Release(volatile signed __int32 *a1)
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
0x180007a80  mov     [rsp+arg_0], rbx
0x180007a85  push    rdi
0x180007a86  sub     rsp, 20h
0x180007a8a  mov     r8d, [rcx+8]
0x180007a8e  mov     rbx, rcx
0x180007a91  mov     ecx, 7FFFFFFFh
0x180007a96  jmp     short loc_180007AAA
0x180007a98  lea     edx, [r8-1]
0x180007a9c  mov     eax, r8d
0x180007a9f  lock cmpxchg [rbx+8], edx
0x180007aa4  jz      short loc_180007AAF
0x180007aa6  mov     r8d, [rbx+8]
0x180007aaa  cmp     r8d, ecx
0x180007aad  jnz     short loc_180007A98
0x180007aaf  lea     edi, [r8-1]
0x180007ab3  test    edi, edi
0x180007ab5  jnz     short loc_180007AF4
0x180007ab7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007abe  mov     rax, [rcx]
0x180007ac1  mov     rax, [rax+8]
0x180007ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aca  test    rbx, rbx
0x180007acd  jz      short loc_180007AE1
0x180007acf  mov     rax, [rbx]
0x180007ad2  lea     edx, [rdi+1]
0x180007ad5  mov     rcx, rbx
0x180007ad8  mov     rax, [rax+18h]
0x180007adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ae1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007ae8  mov     rdx, [rcx]
0x180007aeb  mov     rax, [rdx+10h]
0x180007aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007af4  mov     rbx, [rsp+28h+arg_0]
0x180007af9  mov     eax, edi
0x180007afb  add     rsp, 20h
0x180007aff  pop     rdi
0x180007b00  retn
```
