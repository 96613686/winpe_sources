# ATL::CComAggObject<CRemMdmObj>::Release(void)

- ea: `0x1800057b0`
- end: `0x180005823`
- name: `?Release@?$CComAggObject@VCRemMdmObj@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800057b0`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CRemMdmObj>::Release(_DWORD *a1)
{
  int v1; // ebx
  unsigned int v3; // ebx

  v1 = a1[2];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[2] = v3;
    if ( !v3 )
    {
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 24LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800057b0  mov     [rsp+arg_0], rbx
0x1800057b5  push    rdi
0x1800057b6  sub     rsp, 20h
0x1800057ba  mov     ebx, [rcx+8]
0x1800057bd  mov     rdi, rcx
0x1800057c0  cmp     ebx, 7FFFFFFFh
0x1800057c6  jnz     short loc_1800057CF
0x1800057c8  mov     ebx, 7FFFFFFEh
0x1800057cd  jmp     short loc_180005816
0x1800057cf  sub     ebx, 1
0x1800057d2  mov     [rcx+8], ebx
0x1800057d5  jnz     short loc_180005816
0x1800057d7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800057de  mov     rax, [rcx]
0x1800057e1  mov     rax, [rax+8]
0x1800057e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ea  test    rdi, rdi
0x1800057ed  jz      short loc_180005803
0x1800057ef  mov     rax, [rdi]
0x1800057f2  mov     edx, 1
0x1800057f7  mov     rcx, rdi
0x1800057fa  mov     rax, [rax+18h]
0x1800057fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005803  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000580a  mov     rdx, [rcx]
0x18000580d  mov     rax, [rdx+10h]
0x180005811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005816  mov     eax, ebx
0x180005818  mov     rbx, [rsp+28h+arg_0]
0x18000581d  add     rsp, 20h
0x180005821  pop     rdi
0x180005822  retn
```
