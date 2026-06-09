# ATL::CComAggObject<CDfsShellAdmin>::Release(void)

- ea: `0x180005f10`
- end: `0x180005f83`
- name: `?Release@?$CComAggObject@VCDfsShellAdmin@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005f10`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CDfsShellAdmin>::Release(_DWORD *a1)
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
0x180005f10  mov     [rsp+arg_0], rbx
0x180005f15  push    rdi
0x180005f16  sub     rsp, 20h
0x180005f1a  mov     ebx, [rcx+8]
0x180005f1d  mov     rdi, rcx
0x180005f20  cmp     ebx, 7FFFFFFFh
0x180005f26  jnz     short loc_180005F2F
0x180005f28  mov     ebx, 7FFFFFFEh
0x180005f2d  jmp     short loc_180005F76
0x180005f2f  sub     ebx, 1
0x180005f32  mov     [rcx+8], ebx
0x180005f35  jnz     short loc_180005F76
0x180005f37  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005f3e  mov     rax, [rcx]
0x180005f41  mov     rax, [rax+8]
0x180005f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f4a  test    rdi, rdi
0x180005f4d  jz      short loc_180005F63
0x180005f4f  mov     rax, [rdi]
0x180005f52  mov     edx, 1
0x180005f57  mov     rcx, rdi
0x180005f5a  mov     rax, [rax+18h]
0x180005f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f63  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005f6a  mov     rdx, [rcx]
0x180005f6d  mov     rax, [rdx+10h]
0x180005f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f76  mov     eax, ebx
0x180005f78  mov     rbx, [rsp+28h+arg_0]
0x180005f7d  add     rsp, 20h
0x180005f81  pop     rdi
0x180005f82  retn
```
