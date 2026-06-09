# ATL::CComObject<CDsmDevice>::Release(void)

- ea: `0x18000c2b0`
- end: `0x18000c323`
- name: `?Release@?$CComObject@VCDsmDevice@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000c2b0`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDsmDevice>::Release(_DWORD *a1)
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
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 72LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000c2b0  mov     [rsp+arg_0], rbx
0x18000c2b5  push    rdi
0x18000c2b6  sub     rsp, 20h
0x18000c2ba  mov     ebx, [rcx+8]
0x18000c2bd  mov     rdi, rcx
0x18000c2c0  cmp     ebx, 7FFFFFFFh
0x18000c2c6  jnz     short loc_18000C2CF
0x18000c2c8  mov     ebx, 7FFFFFFEh
0x18000c2cd  jmp     short loc_18000C316
0x18000c2cf  sub     ebx, 1
0x18000c2d2  mov     [rcx+8], ebx
0x18000c2d5  jnz     short loc_18000C316
0x18000c2d7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c2de  mov     rax, [rcx]
0x18000c2e1  mov     rax, [rax+8]
0x18000c2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2ea  test    rdi, rdi
0x18000c2ed  jz      short loc_18000C303
0x18000c2ef  mov     rax, [rdi]
0x18000c2f2  mov     edx, 1
0x18000c2f7  mov     rcx, rdi
0x18000c2fa  mov     rax, [rax+48h]
0x18000c2fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c303  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c30a  mov     rdx, [rcx]
0x18000c30d  mov     rax, [rdx+10h]
0x18000c311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c316  mov     eax, ebx
0x18000c318  mov     rbx, [rsp+28h+arg_0]
0x18000c31d  add     rsp, 20h
0x18000c321  pop     rdi
0x18000c322  retn
```
