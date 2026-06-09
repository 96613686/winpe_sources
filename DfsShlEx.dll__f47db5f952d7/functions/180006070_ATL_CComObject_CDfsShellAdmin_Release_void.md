# ATL::CComObject<CDfsShellAdmin>::Release(void)

- ea: `0x180006070`
- end: `0x1800060e3`
- name: `?Release@?$CComObject@VCDfsShellAdmin@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006070`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDfsShellAdmin>::Release(_DWORD *a1)
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
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180006070  mov     [rsp+arg_0], rbx
0x180006075  push    rdi
0x180006076  sub     rsp, 20h
0x18000607a  mov     ebx, [rcx+8]
0x18000607d  mov     rdi, rcx
0x180006080  cmp     ebx, 7FFFFFFFh
0x180006086  jnz     short loc_18000608F
0x180006088  mov     ebx, 7FFFFFFEh
0x18000608d  jmp     short loc_1800060D6
0x18000608f  sub     ebx, 1
0x180006092  mov     [rcx+8], ebx
0x180006095  jnz     short loc_1800060D6
0x180006097  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000609e  mov     rax, [rcx]
0x1800060a1  mov     rax, [rax+8]
0x1800060a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060aa  test    rdi, rdi
0x1800060ad  jz      short loc_1800060C3
0x1800060af  mov     rax, [rdi]
0x1800060b2  mov     edx, 1
0x1800060b7  mov     rcx, rdi
0x1800060ba  mov     rax, [rax+28h]
0x1800060be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800060ca  mov     rdx, [rcx]
0x1800060cd  mov     rax, [rdx+10h]
0x1800060d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060d6  mov     eax, ebx
0x1800060d8  mov     rbx, [rsp+28h+arg_0]
0x1800060dd  add     rsp, 20h
0x1800060e1  pop     rdi
0x1800060e2  retn
```
