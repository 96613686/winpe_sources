# ATL::CComAggObject<CRemoveDeviceElevatedHandler>::Release(void)

- ea: `0x18000a030`
- end: `0x18000a0a3`
- name: `?Release@?$CComAggObject@VCRemoveDeviceElevatedHandler@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a030`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CRemoveDeviceElevatedHandler>::Release(_DWORD *a1)
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
0x18000a030  mov     [rsp+arg_0], rbx
0x18000a035  push    rdi
0x18000a036  sub     rsp, 20h
0x18000a03a  mov     ebx, [rcx+8]
0x18000a03d  mov     rdi, rcx
0x18000a040  cmp     ebx, 7FFFFFFFh
0x18000a046  jnz     short loc_18000A04F
0x18000a048  mov     ebx, 7FFFFFFEh
0x18000a04d  jmp     short loc_18000A096
0x18000a04f  sub     ebx, 1
0x18000a052  mov     [rcx+8], ebx
0x18000a055  jnz     short loc_18000A096
0x18000a057  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a05e  mov     rax, [rcx]
0x18000a061  mov     rax, [rax+8]
0x18000a065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a06a  test    rdi, rdi
0x18000a06d  jz      short loc_18000A083
0x18000a06f  mov     rax, [rdi]
0x18000a072  mov     edx, 1
0x18000a077  mov     rcx, rdi
0x18000a07a  mov     rax, [rax+18h]
0x18000a07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a083  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a08a  mov     rdx, [rcx]
0x18000a08d  mov     rax, [rdx+10h]
0x18000a091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a096  mov     eax, ebx
0x18000a098  mov     rbx, [rsp+28h+arg_0]
0x18000a09d  add     rsp, 20h
0x18000a0a1  pop     rdi
0x18000a0a2  retn
```
