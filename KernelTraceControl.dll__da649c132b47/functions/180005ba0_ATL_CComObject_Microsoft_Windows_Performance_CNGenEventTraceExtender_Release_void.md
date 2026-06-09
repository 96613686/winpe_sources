# ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::Release(void)

- ea: `0x180005ba0`
- end: `0x180005c08`
- name: `?Release@?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAKXZ`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005ba0`
- `0x180027910`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::Release(_DWORD *a1)
{
  bool v1; // zf
  unsigned int v3; // edi

  v1 = a1[6]-- == 1;
  v3 = a1[6];
  if ( v1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 136LL))(a1, 1);
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
0x180005baa  sub     dword ptr [rcx+18h], 1
0x180005bae  mov     rbx, rcx
0x180005bb1  mov     edi, [rcx+18h]
0x180005bb4  jnz     short loc_180005BFB
0x180005bb6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005bbd  mov     rax, [rcx]
0x180005bc0  mov     rax, [rax+8]
0x180005bc4  call    cs:__guard_dispatch_icall_fptr
0x180005bca  test    rbx, rbx
0x180005bcd  jz      short loc_180005BE7
0x180005bcf  mov     rax, [rbx]
0x180005bd2  mov     edx, 1
0x180005bd7  mov     rcx, rbx
0x180005bda  mov     rax, [rax+88h]
0x180005be1  call    cs:__guard_dispatch_icall_fptr
0x180005be7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005bee  mov     rdx, [rcx]
0x180005bf1  mov     rax, [rdx+10h]
0x180005bf5  call    cs:__guard_dispatch_icall_fptr
0x180005bfb  mov     eax, edi
0x180005bfd  mov     rbx, [rsp+28h+arg_0]
0x180005c02  add     rsp, 20h
0x180005c06  pop     rdi
0x180005c07  retn
```
