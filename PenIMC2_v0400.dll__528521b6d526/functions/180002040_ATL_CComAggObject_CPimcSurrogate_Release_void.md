# ATL::CComAggObject<CPimcSurrogate>::Release(void)

- ea: `0x180002040`
- end: `0x1800020a7`
- name: `?Release@?$CComAggObject@VCPimcSurrogate@@@ATL@@UEAAKXZ`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002040`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CPimcSurrogate>::Release(_DWORD *a1)
{
  bool v2; // zf
  unsigned int v3; // edi

  v2 = a1[2]-- == 1;
  v3 = a1[2];
  if ( v2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 24LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180002040  mov     [rsp+arg_0], rbx
0x180002045  push    rdi
0x180002046  sub     rsp, 30h
0x18000204a  mov     rbx, rcx
0x18000204d  sub     dword ptr [rcx+8], 1
0x180002051  mov     edi, [rcx+8]
0x180002054  jnz     short loc_18000209A
0x180002056  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000205d  mov     rax, [rcx]
0x180002060  mov     rax, [rax+8]
0x180002064  call    cs:__guard_dispatch_icall_fptr
0x18000206a  nop
0x18000206b  test    rbx, rbx
0x18000206e  jz      short loc_180002086
0x180002070  mov     rax, [rbx]
0x180002073  mov     edx, 1
0x180002078  mov     rcx, rbx
0x18000207b  mov     rax, [rax+18h]
0x18000207f  call    cs:__guard_dispatch_icall_fptr
0x180002085  nop
0x180002086  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000208d  mov     rdx, [rcx]
0x180002090  mov     rax, [rdx+10h]
0x180002094  call    cs:__guard_dispatch_icall_fptr
0x18000209a  mov     eax, edi
0x18000209c  mov     rbx, [rsp+38h+arg_0]
0x1800020a1  add     rsp, 30h
0x1800020a5  pop     rdi
0x1800020a6  retn
```
