# ATL::CComObject<CRemoveDeviceContextHandler>::Release(void)

- ea: `0x18000a100`
- end: `0x18000a173`
- name: `?Release@?$CComObject@VCRemoveDeviceContextHandler@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a180`

## callees

- `0x18000a100`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRemoveDeviceContextHandler>::Release(_DWORD *a1)
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
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 88LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000a100  mov     [rsp+arg_0], rbx
0x18000a105  push    rdi
0x18000a106  sub     rsp, 20h
0x18000a10a  mov     ebx, [rcx+10h]
0x18000a10d  mov     rdi, rcx
0x18000a110  cmp     ebx, 7FFFFFFFh
0x18000a116  jnz     short loc_18000A11F
0x18000a118  mov     ebx, 7FFFFFFEh
0x18000a11d  jmp     short loc_18000A166
0x18000a11f  sub     ebx, 1
0x18000a122  mov     [rcx+10h], ebx
0x18000a125  jnz     short loc_18000A166
0x18000a127  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a12e  mov     rax, [rcx]
0x18000a131  mov     rax, [rax+8]
0x18000a135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a13a  test    rdi, rdi
0x18000a13d  jz      short loc_18000A153
0x18000a13f  mov     rax, [rdi]
0x18000a142  mov     edx, 1
0x18000a147  mov     rcx, rdi
0x18000a14a  mov     rax, [rax+58h]
0x18000a14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a153  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a15a  mov     rdx, [rcx]
0x18000a15d  mov     rax, [rdx+10h]
0x18000a161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a166  mov     eax, ebx
0x18000a168  mov     rbx, [rsp+28h+arg_0]
0x18000a16d  add     rsp, 20h
0x18000a171  pop     rdi
0x18000a172  retn
```
