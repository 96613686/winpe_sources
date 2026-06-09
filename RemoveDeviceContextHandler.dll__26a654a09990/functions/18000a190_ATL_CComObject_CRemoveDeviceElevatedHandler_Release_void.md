# ATL::CComObject<CRemoveDeviceElevatedHandler>::Release(void)

- ea: `0x18000a190`
- end: `0x18000a203`
- name: `?Release@?$CComObject@VCRemoveDeviceElevatedHandler@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a190`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRemoveDeviceElevatedHandler>::Release(_DWORD *a1)
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
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 32LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000a190  mov     [rsp+arg_0], rbx
0x18000a195  push    rdi
0x18000a196  sub     rsp, 20h
0x18000a19a  mov     ebx, [rcx+8]
0x18000a19d  mov     rdi, rcx
0x18000a1a0  cmp     ebx, 7FFFFFFFh
0x18000a1a6  jnz     short loc_18000A1AF
0x18000a1a8  mov     ebx, 7FFFFFFEh
0x18000a1ad  jmp     short loc_18000A1F6
0x18000a1af  sub     ebx, 1
0x18000a1b2  mov     [rcx+8], ebx
0x18000a1b5  jnz     short loc_18000A1F6
0x18000a1b7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a1be  mov     rax, [rcx]
0x18000a1c1  mov     rax, [rax+8]
0x18000a1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1ca  test    rdi, rdi
0x18000a1cd  jz      short loc_18000A1E3
0x18000a1cf  mov     rax, [rdi]
0x18000a1d2  mov     edx, 1
0x18000a1d7  mov     rcx, rdi
0x18000a1da  mov     rax, [rax+20h]
0x18000a1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1e3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a1ea  mov     rdx, [rcx]
0x18000a1ed  mov     rax, [rdx+10h]
0x18000a1f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1f6  mov     eax, ebx
0x18000a1f8  mov     rbx, [rsp+28h+arg_0]
0x18000a1fd  add     rsp, 20h
0x18000a201  pop     rdi
0x18000a202  retn
```
