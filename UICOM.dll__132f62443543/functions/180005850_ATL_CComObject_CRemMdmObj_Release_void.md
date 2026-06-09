# ATL::CComObject<CRemMdmObj>::Release(void)

- ea: `0x180005850`
- end: `0x1800058c3`
- name: `?Release@?$CComObject@VCRemMdmObj@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005850`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRemMdmObj>::Release(_DWORD *a1)
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
0x180005850  mov     [rsp+arg_0], rbx
0x180005855  push    rdi
0x180005856  sub     rsp, 20h
0x18000585a  mov     ebx, [rcx+8]
0x18000585d  mov     rdi, rcx
0x180005860  cmp     ebx, 7FFFFFFFh
0x180005866  jnz     short loc_18000586F
0x180005868  mov     ebx, 7FFFFFFEh
0x18000586d  jmp     short loc_1800058B6
0x18000586f  sub     ebx, 1
0x180005872  mov     [rcx+8], ebx
0x180005875  jnz     short loc_1800058B6
0x180005877  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000587e  mov     rax, [rcx]
0x180005881  mov     rax, [rax+8]
0x180005885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000588a  test    rdi, rdi
0x18000588d  jz      short loc_1800058A3
0x18000588f  mov     rax, [rdi]
0x180005892  mov     edx, 1
0x180005897  mov     rcx, rdi
0x18000589a  mov     rax, [rax+20h]
0x18000589e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058a3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800058aa  mov     rdx, [rcx]
0x1800058ad  mov     rax, [rdx+10h]
0x1800058b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058b6  mov     eax, ebx
0x1800058b8  mov     rbx, [rsp+28h+arg_0]
0x1800058bd  add     rsp, 20h
0x1800058c1  pop     rdi
0x1800058c2  retn
```
