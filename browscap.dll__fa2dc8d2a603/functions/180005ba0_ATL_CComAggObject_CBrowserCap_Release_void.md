# ATL::CComAggObject<CBrowserCap>::Release(void)

- ea: `0x180005ba0`
- end: `0x180005c21`
- name: `?Release@?$CComAggObject@VCBrowserCap@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005ba0`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CBrowserCap>::Release(volatile signed __int32 *a1)
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
0x180005ba0  mov     [rsp+arg_0], rbx
0x180005ba5  push    rdi
0x180005ba6  sub     rsp, 20h
0x180005baa  mov     r8d, [rcx+8]
0x180005bae  mov     rbx, rcx
0x180005bb1  mov     ecx, 7FFFFFFFh
0x180005bb6  jmp     short loc_180005BCA
0x180005bb8  lea     edx, [r8-1]
0x180005bbc  mov     eax, r8d
0x180005bbf  lock cmpxchg [rbx+8], edx
0x180005bc4  jz      short loc_180005BCF
0x180005bc6  mov     r8d, [rbx+8]
0x180005bca  cmp     r8d, ecx
0x180005bcd  jnz     short loc_180005BB8
0x180005bcf  lea     edi, [r8-1]
0x180005bd3  test    edi, edi
0x180005bd5  jnz     short loc_180005C14
0x180005bd7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005bde  mov     rax, [rcx]
0x180005be1  mov     rax, [rax+8]
0x180005be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bea  test    rbx, rbx
0x180005bed  jz      short loc_180005C01
0x180005bef  mov     rax, [rbx]
0x180005bf2  lea     edx, [rdi+1]
0x180005bf5  mov     rcx, rbx
0x180005bf8  mov     rax, [rax+18h]
0x180005bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c01  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005c08  mov     rdx, [rcx]
0x180005c0b  mov     rax, [rdx+10h]
0x180005c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c14  mov     rbx, [rsp+28h+arg_0]
0x180005c19  mov     eax, edi
0x180005c1b  add     rsp, 20h
0x180005c1f  pop     rdi
0x180005c20  retn
```
