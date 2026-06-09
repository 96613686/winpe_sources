# ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::Release(void)

- ea: `0x1800243b0`
- end: `0x180024418`
- name: `?Release@?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAKXZ`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800243b0`
- `0x180027910`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::Release(_DWORD *a1)
{
  bool v1; // zf
  unsigned int v3; // edi

  v1 = a1[6]-- == 1;
  v3 = a1[6];
  if ( v1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 160LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800243b0  mov     [rsp+arg_0], rbx
0x1800243b5  push    rdi
0x1800243b6  sub     rsp, 20h
0x1800243ba  sub     dword ptr [rcx+18h], 1
0x1800243be  mov     rbx, rcx
0x1800243c1  mov     edi, [rcx+18h]
0x1800243c4  jnz     short loc_18002440B
0x1800243c6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800243cd  mov     rax, [rcx]
0x1800243d0  mov     rax, [rax+8]
0x1800243d4  call    cs:__guard_dispatch_icall_fptr
0x1800243da  test    rbx, rbx
0x1800243dd  jz      short loc_1800243F7
0x1800243df  mov     rax, [rbx]
0x1800243e2  mov     edx, 1
0x1800243e7  mov     rcx, rbx
0x1800243ea  mov     rax, [rax+0A0h]
0x1800243f1  call    cs:__guard_dispatch_icall_fptr
0x1800243f7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800243fe  mov     rdx, [rcx]
0x180024401  mov     rax, [rdx+10h]
0x180024405  call    cs:__guard_dispatch_icall_fptr
0x18002440b  mov     eax, edi
0x18002440d  mov     rbx, [rsp+28h+arg_0]
0x180024412  add     rsp, 20h
0x180024416  pop     rdi
0x180024417  retn
```
