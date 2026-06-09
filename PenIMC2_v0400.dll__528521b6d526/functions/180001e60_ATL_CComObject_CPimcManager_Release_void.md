# ATL::CComObject<CPimcManager>::Release(void)

- ea: `0x180001e60`
- end: `0x180001ec7`
- name: `?Release@?$CComObject@VCPimcManager@@@ATL@@UEAAKXZ`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001e60`
- `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CPimcManager>::Release(_DWORD *a1)
{
  bool v2; // zf
  unsigned int v3; // edi

  v2 = a1[2]-- == 1;
  v3 = a1[2];
  if ( v2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 48LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180001e60  mov     [rsp+arg_0], rbx
0x180001e65  push    rdi
0x180001e66  sub     rsp, 30h
0x180001e6a  mov     rbx, rcx
0x180001e6d  sub     dword ptr [rcx+8], 1
0x180001e71  mov     edi, [rcx+8]
0x180001e74  jnz     short loc_180001EBA
0x180001e76  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001e7d  mov     rax, [rcx]
0x180001e80  mov     rax, [rax+8]
0x180001e84  call    cs:__guard_dispatch_icall_fptr
0x180001e8a  nop
0x180001e8b  test    rbx, rbx
0x180001e8e  jz      short loc_180001EA6
0x180001e90  mov     rax, [rbx]
0x180001e93  mov     edx, 1
0x180001e98  mov     rcx, rbx
0x180001e9b  mov     rax, [rax+30h]
0x180001e9f  call    cs:__guard_dispatch_icall_fptr
0x180001ea5  nop
0x180001ea6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001ead  mov     rdx, [rcx]
0x180001eb0  mov     rax, [rdx+10h]
0x180001eb4  call    cs:__guard_dispatch_icall_fptr
0x180001eba  mov     eax, edi
0x180001ebc  mov     rbx, [rsp+38h+arg_0]
0x180001ec1  add     rsp, 30h
0x180001ec5  pop     rdi
0x180001ec6  retn
```
