# ATL::CComObject<CLayerUIPropPage>::Release(void)

- ea: `0x18000df40`
- end: `0x18000dfb3`
- name: `?Release@?$CComObject@VCLayerUIPropPage@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dfc0`
- `0x18000dfd0`

## callees

- `0x18000df40`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CLayerUIPropPage>::Release(_DWORD *a1)
{
  int v1; // ebx
  unsigned int v3; // ebx

  v1 = a1[6];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[6] = v3;
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
0x18000df40  mov     [rsp+arg_0], rbx
0x18000df45  push    rdi
0x18000df46  sub     rsp, 20h
0x18000df4a  mov     ebx, [rcx+18h]
0x18000df4d  mov     rdi, rcx
0x18000df50  cmp     ebx, 7FFFFFFFh
0x18000df56  jnz     short loc_18000DF5F
0x18000df58  mov     ebx, 7FFFFFFEh
0x18000df5d  jmp     short loc_18000DFA6
0x18000df5f  sub     ebx, 1
0x18000df62  mov     [rcx+18h], ebx
0x18000df65  jnz     short loc_18000DFA6
0x18000df67  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000df6e  mov     rax, [rcx]
0x18000df71  mov     rax, [rax+8]
0x18000df75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df7a  test    rdi, rdi
0x18000df7d  jz      short loc_18000DF93
0x18000df7f  mov     rax, [rdi]
0x18000df82  mov     edx, 1
0x18000df87  mov     rcx, rdi
0x18000df8a  mov     rax, [rax+20h]
0x18000df8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df93  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000df9a  mov     rdx, [rcx]
0x18000df9d  mov     rax, [rdx+10h]
0x18000dfa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfa6  mov     eax, ebx
0x18000dfa8  mov     rbx, [rsp+28h+arg_0]
0x18000dfad  add     rsp, 20h
0x18000dfb1  pop     rdi
0x18000dfb2  retn
```
