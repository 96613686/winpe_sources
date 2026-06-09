# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::Release(void)

- ea: `0x180007b00`
- end: `0x180007b73`
- name: `?Release@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007b00`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::Release(_DWORD *a1)
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
0x180007b00  mov     [rsp+arg_0], rbx
0x180007b05  push    rdi
0x180007b06  sub     rsp, 20h
0x180007b0a  mov     ebx, [rcx+8]
0x180007b0d  mov     rdi, rcx
0x180007b10  cmp     ebx, 7FFFFFFFh
0x180007b16  jnz     short loc_180007B1F
0x180007b18  mov     ebx, 7FFFFFFEh
0x180007b1d  jmp     short loc_180007B66
0x180007b1f  sub     ebx, 1
0x180007b22  mov     [rcx+8], ebx
0x180007b25  jnz     short loc_180007B66
0x180007b27  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007b2e  mov     rax, [rcx]
0x180007b31  mov     rax, [rax+8]
0x180007b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b3a  test    rdi, rdi
0x180007b3d  jz      short loc_180007B53
0x180007b3f  mov     rax, [rdi]
0x180007b42  mov     edx, 1
0x180007b47  mov     rcx, rdi
0x180007b4a  mov     rax, [rax+18h]
0x180007b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b53  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007b5a  mov     rdx, [rcx]
0x180007b5d  mov     rax, [rdx+10h]
0x180007b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b66  mov     eax, ebx
0x180007b68  mov     rbx, [rsp+28h+arg_0]
0x180007b6d  add     rsp, 20h
0x180007b71  pop     rdi
0x180007b72  retn
```
