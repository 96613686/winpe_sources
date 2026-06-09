# ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::Release(void)

- ea: `0x1800246d0`
- end: `0x180024746`
- name: `?Release@?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAKXZ`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800246d0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::Release(_DWORD *a1)
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
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 160LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800246d0  mov     [rsp+arg_0], rbx
0x1800246d5  push    rdi
0x1800246d6  sub     rsp, 20h
0x1800246da  mov     ebx, [rcx+18h]
0x1800246dd  mov     rdi, rcx
0x1800246e0  cmp     ebx, 7FFFFFFFh
0x1800246e6  jnz     short loc_1800246EF
0x1800246e8  mov     ebx, 7FFFFFFEh
0x1800246ed  jmp     short loc_180024739
0x1800246ef  sub     ebx, 1
0x1800246f2  mov     [rcx+18h], ebx
0x1800246f5  jnz     short loc_180024739
0x1800246f7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800246fe  mov     rax, [rcx]
0x180024701  mov     rax, [rax+8]
0x180024705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002470a  test    rdi, rdi
0x18002470d  jz      short loc_180024726
0x18002470f  mov     rax, [rdi]
0x180024712  mov     edx, 1
0x180024717  mov     rcx, rdi
0x18002471a  mov     rax, [rax+0A0h]
0x180024721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024726  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002472d  mov     rdx, [rcx]
0x180024730  mov     rax, [rdx+10h]
0x180024734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024739  mov     eax, ebx
0x18002473b  mov     rbx, [rsp+28h+arg_0]
0x180024740  add     rsp, 20h
0x180024744  pop     rdi
0x180024745  retn
```
