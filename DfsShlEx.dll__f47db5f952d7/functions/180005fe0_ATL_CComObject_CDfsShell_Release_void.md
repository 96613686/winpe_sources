# ATL::CComObject<CDfsShell>::Release(void)

- ea: `0x180005fe0`
- end: `0x180006053`
- name: `?Release@?$CComObject@VCDfsShell@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006060`

## callees

- `0x180005fe0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDfsShell>::Release(_DWORD *a1)
{
  int v1; // ebx
  unsigned int v3; // ebx

  v1 = a1[4];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[4] = v3;
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
0x180005fe0  mov     [rsp+arg_0], rbx
0x180005fe5  push    rdi
0x180005fe6  sub     rsp, 20h
0x180005fea  mov     ebx, [rcx+10h]
0x180005fed  mov     rdi, rcx
0x180005ff0  cmp     ebx, 7FFFFFFFh
0x180005ff6  jnz     short loc_180005FFF
0x180005ff8  mov     ebx, 7FFFFFFEh
0x180005ffd  jmp     short loc_180006046
0x180005fff  sub     ebx, 1
0x180006002  mov     [rcx+10h], ebx
0x180006005  jnz     short loc_180006046
0x180006007  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000600e  mov     rax, [rcx]
0x180006011  mov     rax, [rax+8]
0x180006015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000601a  test    rdi, rdi
0x18000601d  jz      short loc_180006033
0x18000601f  mov     rax, [rdi]
0x180006022  mov     edx, 1
0x180006027  mov     rcx, rdi
0x18000602a  mov     rax, [rax+20h]
0x18000602e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006033  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000603a  mov     rdx, [rcx]
0x18000603d  mov     rax, [rdx+10h]
0x180006041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006046  mov     eax, ebx
0x180006048  mov     rbx, [rsp+28h+arg_0]
0x18000604d  add     rsp, 20h
0x180006051  pop     rdi
0x180006052  retn
```
