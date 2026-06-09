# ATL::CComObject<CIMRequestRA>::Release(void)

- ea: `0x140009de0`
- end: `0x140009e4a`
- name: `?Release@?$CComObject@VCIMRequestRA@@@ATL@@UEAAKXZ`
- size: `106`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140003058`
- `0x140009de0`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIMRequestRA>::Release(_DWORD *a1)
{
  int v1; // edi
  unsigned int v3; // edi
  char v5; // [rsp+30h] [rbp+8h] BYREF

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
      ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v5);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 80LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140009de0  mov     [rsp+arg_8], rbx
0x140009de5  push    rdi
0x140009de6  sub     rsp, 20h
0x140009dea  mov     edi, [rcx+8]
0x140009ded  mov     rbx, rcx
0x140009df0  cmp     edi, 7FFFFFFFh
0x140009df6  jnz     short loc_140009DFF
0x140009df8  mov     edi, 7FFFFFFEh
0x140009dfd  jmp     short loc_140009E3D
0x140009dff  sub     edi, 1
0x140009e02  mov     [rcx+8], edi
0x140009e05  jnz     short loc_140009E3D
0x140009e07  lea     rcx, [rsp+28h+arg_0]; this
0x140009e0c  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x140009e11  test    rbx, rbx
0x140009e14  jz      short loc_140009E2A
0x140009e16  mov     rax, [rbx]
0x140009e19  mov     edx, 1
0x140009e1e  mov     rcx, rbx
0x140009e21  mov     rax, [rax+50h]
0x140009e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e2a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140009e31  mov     rdx, [rcx]
0x140009e34  mov     rax, [rdx+10h]
0x140009e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e3d  mov     rbx, [rsp+28h+arg_8]
0x140009e42  mov     eax, edi
0x140009e44  add     rsp, 20h
0x140009e48  pop     rdi
0x140009e49  retn
```
