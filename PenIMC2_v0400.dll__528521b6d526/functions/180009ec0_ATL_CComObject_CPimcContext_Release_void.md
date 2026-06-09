# ATL::CComObject<CPimcContext>::Release(void)

- ea: `0x180009ec0`
- end: `0x180009f27`
- name: `?Release@?$CComObject@VCPimcContext@@@ATL@@UEAAKXZ`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009ec0`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPimcContext>::Release(_DWORD *a1)
{
  bool v2; // zf
  unsigned int v3; // edi

  v2 = a1[2]-- == 1;
  v3 = a1[2];
  if ( v2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 72LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180009ec0  mov     [rsp+arg_0], rbx
0x180009ec5  push    rdi
0x180009ec6  sub     rsp, 30h
0x180009eca  mov     rbx, rcx
0x180009ecd  sub     dword ptr [rcx+8], 1
0x180009ed1  mov     edi, [rcx+8]
0x180009ed4  jnz     short loc_180009F1A
0x180009ed6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009edd  mov     rax, [rcx]
0x180009ee0  mov     rax, [rax+8]
0x180009ee4  call    cs:__guard_dispatch_icall_fptr
0x180009eea  nop
0x180009eeb  test    rbx, rbx
0x180009eee  jz      short loc_180009F06
0x180009ef0  mov     rax, [rbx]
0x180009ef3  mov     edx, 1
0x180009ef8  mov     rcx, rbx
0x180009efb  mov     rax, [rax+48h]
0x180009eff  call    cs:__guard_dispatch_icall_fptr
0x180009f05  nop
0x180009f06  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009f0d  mov     rdx, [rcx]
0x180009f10  mov     rax, [rdx+10h]
0x180009f14  call    cs:__guard_dispatch_icall_fptr
0x180009f1a  mov     eax, edi
0x180009f1c  mov     rbx, [rsp+38h+arg_0]
0x180009f21  add     rsp, 30h
0x180009f25  pop     rdi
0x180009f26  retn
```
