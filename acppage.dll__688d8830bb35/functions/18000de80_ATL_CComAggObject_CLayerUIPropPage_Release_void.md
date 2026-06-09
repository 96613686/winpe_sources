# ATL::CComAggObject<CLayerUIPropPage>::Release(void)

- ea: `0x18000de80`
- end: `0x18000def3`
- name: `?Release@?$CComAggObject@VCLayerUIPropPage@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000de80`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CLayerUIPropPage>::Release(_DWORD *a1)
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
0x18000de80  mov     [rsp+arg_0], rbx
0x18000de85  push    rdi
0x18000de86  sub     rsp, 20h
0x18000de8a  mov     ebx, [rcx+8]
0x18000de8d  mov     rdi, rcx
0x18000de90  cmp     ebx, 7FFFFFFFh
0x18000de96  jnz     short loc_18000DE9F
0x18000de98  mov     ebx, 7FFFFFFEh
0x18000de9d  jmp     short loc_18000DEE6
0x18000de9f  sub     ebx, 1
0x18000dea2  mov     [rcx+8], ebx
0x18000dea5  jnz     short loc_18000DEE6
0x18000dea7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000deae  mov     rax, [rcx]
0x18000deb1  mov     rax, [rax+8]
0x18000deb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deba  test    rdi, rdi
0x18000debd  jz      short loc_18000DED3
0x18000debf  mov     rax, [rdi]
0x18000dec2  mov     edx, 1
0x18000dec7  mov     rcx, rdi
0x18000deca  mov     rax, [rax+18h]
0x18000dece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ded3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000deda  mov     rdx, [rcx]
0x18000dedd  mov     rax, [rdx+10h]
0x18000dee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dee6  mov     eax, ebx
0x18000dee8  mov     rbx, [rsp+28h+arg_0]
0x18000deed  add     rsp, 20h
0x18000def1  pop     rdi
0x18000def2  retn
```
