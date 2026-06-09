# ATL::CComObject<CMsMpClientUtils>::Release(void)

- ea: `0x180004a30`
- end: `0x180004ab1`
- name: `?Release@?$CComObject@VCMsMpClientUtils@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004a30`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMsMpClientUtils>::Release(__int64 a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *(_DWORD *)(a1 - 56);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)(a1 - 56), i - 1, i);
        i = *(_DWORD *)(a1 - 56) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 != 64 )
      (**(void (__fastcall ***)(__int64, _QWORD))(a1 - 64))(a1 - 64, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180004a30  mov     [rsp+arg_0], rbx
0x180004a35  push    rdi
0x180004a36  sub     rsp, 20h
0x180004a3a  mov     r8d, [rcx-38h]
0x180004a3e  mov     rbx, rcx
0x180004a41  mov     ecx, 7FFFFFFFh
0x180004a46  jmp     short loc_180004A5A
0x180004a48  lea     edx, [r8-1]
0x180004a4c  mov     eax, r8d
0x180004a4f  lock cmpxchg [rbx-38h], edx
0x180004a54  jz      short loc_180004A5F
0x180004a56  mov     r8d, [rbx-38h]
0x180004a5a  cmp     r8d, ecx
0x180004a5d  jnz     short loc_180004A48
0x180004a5f  lea     edi, [r8-1]
0x180004a63  test    edi, edi
0x180004a65  jnz     short loc_180004AA4
0x180004a67  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004a6e  mov     rax, [rcx]
0x180004a71  mov     rax, [rax+8]
0x180004a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a7a  lea     rcx, [rbx-40h]
0x180004a7e  test    rcx, rcx
0x180004a81  jz      short loc_180004A91
0x180004a83  mov     rax, [rcx]
0x180004a86  lea     edx, [rdi+1]
0x180004a89  mov     rax, [rax]
0x180004a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a91  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004a98  mov     rdx, [rcx]
0x180004a9b  mov     rax, [rdx+10h]
0x180004a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aa4  mov     rbx, [rsp+28h+arg_0]
0x180004aa9  mov     eax, edi
0x180004aab  add     rsp, 20h
0x180004aaf  pop     rdi
0x180004ab0  retn
```
