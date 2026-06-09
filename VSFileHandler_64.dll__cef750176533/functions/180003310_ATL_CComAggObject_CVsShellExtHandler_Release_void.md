# ATL::CComAggObject<CVsShellExtHandler>::Release(void)

- ea: `0x180003310`
- end: `0x180003363`
- name: `?Release@?$CComAggObject@VCVsShellExtHandler@@@ATL@@UEAAKXZ`
- size: `83`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003310`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CVsShellExtHandler>::Release(_DWORD *a1)
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
0x180003310  mov     [rsp+arg_0], rbx
0x180003315  push    rdi
0x180003316  sub     rsp, 20h
0x18000331a  mov     rbx, rcx
0x18000331d  sub     dword ptr [rcx+8], 1
0x180003321  mov     edi, [rcx+8]
0x180003324  jnz     short loc_180003356
0x180003326  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000332d  mov     rax, [rcx]
0x180003330  call    qword ptr [rax+8]
0x180003333  test    rbx, rbx
0x180003336  jz      short loc_180003348
0x180003338  mov     r8, [rbx]
0x18000333b  mov     edx, 1
0x180003340  mov     rcx, rbx
0x180003343  call    qword ptr [r8+18h]
0x180003347  nop
0x180003348  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000334f  mov     rdx, [rcx]
0x180003352  call    qword ptr [rdx+10h]
0x180003355  nop
0x180003356  mov     eax, edi
0x180003358  mov     rbx, [rsp+28h+arg_0]
0x18000335d  add     rsp, 20h
0x180003361  pop     rdi
0x180003362  retn
```
