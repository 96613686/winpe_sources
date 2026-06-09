# ATL::CComAggObject<CDsmDevice>::Release(void)

- ea: `0x18000b210`
- end: `0x18000b283`
- name: `?Release@?$CComAggObject@VCDsmDevice@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b210`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CDsmDevice>::Release(_DWORD *a1)
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
0x18000b210  mov     [rsp+arg_0], rbx
0x18000b215  push    rdi
0x18000b216  sub     rsp, 20h
0x18000b21a  mov     ebx, [rcx+8]
0x18000b21d  mov     rdi, rcx
0x18000b220  cmp     ebx, 7FFFFFFFh
0x18000b226  jnz     short loc_18000B22F
0x18000b228  mov     ebx, 7FFFFFFEh
0x18000b22d  jmp     short loc_18000B276
0x18000b22f  sub     ebx, 1
0x18000b232  mov     [rcx+8], ebx
0x18000b235  jnz     short loc_18000B276
0x18000b237  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b23e  mov     rax, [rcx]
0x18000b241  mov     rax, [rax+8]
0x18000b245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b24a  test    rdi, rdi
0x18000b24d  jz      short loc_18000B263
0x18000b24f  mov     rax, [rdi]
0x18000b252  mov     edx, 1
0x18000b257  mov     rcx, rdi
0x18000b25a  mov     rax, [rax+18h]
0x18000b25e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b263  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b26a  mov     rdx, [rcx]
0x18000b26d  mov     rax, [rdx+10h]
0x18000b271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b276  mov     eax, ebx
0x18000b278  mov     rbx, [rsp+28h+arg_0]
0x18000b27d  add     rsp, 20h
0x18000b281  pop     rdi
0x18000b282  retn
```
