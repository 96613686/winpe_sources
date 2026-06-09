# ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::Release(void)

- ea: `0x180007a80`
- end: `0x180007af3`
- name: `?Release@?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007a80`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::Release(_DWORD *a1)
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
0x180007a80  mov     [rsp+arg_0], rbx
0x180007a85  push    rdi
0x180007a86  sub     rsp, 20h
0x180007a8a  mov     ebx, [rcx+8]
0x180007a8d  mov     rdi, rcx
0x180007a90  cmp     ebx, 7FFFFFFFh
0x180007a96  jnz     short loc_180007A9F
0x180007a98  mov     ebx, 7FFFFFFEh
0x180007a9d  jmp     short loc_180007AE6
0x180007a9f  sub     ebx, 1
0x180007aa2  mov     [rcx+8], ebx
0x180007aa5  jnz     short loc_180007AE6
0x180007aa7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007aae  mov     rax, [rcx]
0x180007ab1  mov     rax, [rax+8]
0x180007ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aba  test    rdi, rdi
0x180007abd  jz      short loc_180007AD3
0x180007abf  mov     rax, [rdi]
0x180007ac2  mov     edx, 1
0x180007ac7  mov     rcx, rdi
0x180007aca  mov     rax, [rax+20h]
0x180007ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ad3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007ada  mov     rdx, [rcx]
0x180007add  mov     rax, [rdx+10h]
0x180007ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ae6  mov     eax, ebx
0x180007ae8  mov     rbx, [rsp+28h+arg_0]
0x180007aed  add     rsp, 20h
0x180007af1  pop     rdi
0x180007af2  retn
```
