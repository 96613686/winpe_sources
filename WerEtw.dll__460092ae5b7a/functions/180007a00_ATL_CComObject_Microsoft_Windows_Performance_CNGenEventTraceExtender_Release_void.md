# ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::Release(void)

- ea: `0x180007a00`
- end: `0x180007a76`
- name: `?Release@?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAKXZ`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007a00`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::Release(_DWORD *a1)
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
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 136LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180007a00  mov     [rsp+arg_0], rbx
0x180007a05  push    rdi
0x180007a06  sub     rsp, 20h
0x180007a0a  mov     ebx, [rcx+18h]
0x180007a0d  mov     rdi, rcx
0x180007a10  cmp     ebx, 7FFFFFFFh
0x180007a16  jnz     short loc_180007A1F
0x180007a18  mov     ebx, 7FFFFFFEh
0x180007a1d  jmp     short loc_180007A69
0x180007a1f  sub     ebx, 1
0x180007a22  mov     [rcx+18h], ebx
0x180007a25  jnz     short loc_180007A69
0x180007a27  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007a2e  mov     rax, [rcx]
0x180007a31  mov     rax, [rax+8]
0x180007a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a3a  test    rdi, rdi
0x180007a3d  jz      short loc_180007A56
0x180007a3f  mov     rax, [rdi]
0x180007a42  mov     edx, 1
0x180007a47  mov     rcx, rdi
0x180007a4a  mov     rax, [rax+88h]
0x180007a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a56  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007a5d  mov     rdx, [rcx]
0x180007a60  mov     rax, [rdx+10h]
0x180007a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a69  mov     eax, ebx
0x180007a6b  mov     rbx, [rsp+28h+arg_0]
0x180007a70  add     rsp, 20h
0x180007a74  pop     rdi
0x180007a75  retn
```
