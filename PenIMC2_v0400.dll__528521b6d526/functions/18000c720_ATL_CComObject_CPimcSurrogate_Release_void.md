# ATL::CComObject<CPimcSurrogate>::Release(void)

- ea: `0x18000c720`
- end: `0x18000c787`
- name: `?Release@?$CComObject@VCPimcSurrogate@@@ATL@@UEAAKXZ`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000c720`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPimcSurrogate>::Release(_DWORD *a1)
{
  bool v2; // zf
  unsigned int v3; // edi

  v2 = a1[2]-- == 1;
  v3 = a1[2];
  if ( v2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 32LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x18000c720  mov     [rsp+arg_0], rbx
0x18000c725  push    rdi
0x18000c726  sub     rsp, 30h
0x18000c72a  mov     rbx, rcx
0x18000c72d  sub     dword ptr [rcx+8], 1
0x18000c731  mov     edi, [rcx+8]
0x18000c734  jnz     short loc_18000C77A
0x18000c736  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c73d  mov     rax, [rcx]
0x18000c740  mov     rax, [rax+8]
0x18000c744  call    cs:__guard_dispatch_icall_fptr
0x18000c74a  nop
0x18000c74b  test    rbx, rbx
0x18000c74e  jz      short loc_18000C766
0x18000c750  mov     rax, [rbx]
0x18000c753  mov     edx, 1
0x18000c758  mov     rcx, rbx
0x18000c75b  mov     rax, [rax+20h]
0x18000c75f  call    cs:__guard_dispatch_icall_fptr
0x18000c765  nop
0x18000c766  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c76d  mov     rdx, [rcx]
0x18000c770  mov     rax, [rdx+10h]
0x18000c774  call    cs:__guard_dispatch_icall_fptr
0x18000c77a  mov     eax, edi
0x18000c77c  mov     rbx, [rsp+38h+arg_0]
0x18000c781  add     rsp, 30h
0x18000c785  pop     rdi
0x18000c786  retn
```
