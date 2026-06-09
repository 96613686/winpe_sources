# ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::Release(void)

- ea: `0x180005d20`
- end: `0x180005d85`
- name: `?Release@?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@UEAAKXZ`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005d20`
- `0x180027910`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::Release(_DWORD *a1)
{
  bool v1; // zf
  unsigned int v3; // edi

  v1 = a1[2]-- == 1;
  v3 = a1[2];
  if ( v1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 32LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180005d20  mov     [rsp+arg_0], rbx
0x180005d25  push    rdi
0x180005d26  sub     rsp, 20h
0x180005d2a  sub     dword ptr [rcx+8], 1
0x180005d2e  mov     rbx, rcx
0x180005d31  mov     edi, [rcx+8]
0x180005d34  jnz     short loc_180005D78
0x180005d36  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005d3d  mov     rax, [rcx]
0x180005d40  mov     rax, [rax+8]
0x180005d44  call    cs:__guard_dispatch_icall_fptr
0x180005d4a  test    rbx, rbx
0x180005d4d  jz      short loc_180005D64
0x180005d4f  mov     rax, [rbx]
0x180005d52  mov     edx, 1
0x180005d57  mov     rcx, rbx
0x180005d5a  mov     rax, [rax+20h]
0x180005d5e  call    cs:__guard_dispatch_icall_fptr
0x180005d64  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005d6b  mov     rdx, [rcx]
0x180005d6e  mov     rax, [rdx+10h]
0x180005d72  call    cs:__guard_dispatch_icall_fptr
0x180005d78  mov     eax, edi
0x180005d7a  mov     rbx, [rsp+28h+arg_0]
0x180005d7f  add     rsp, 20h
0x180005d83  pop     rdi
0x180005d84  retn
```
