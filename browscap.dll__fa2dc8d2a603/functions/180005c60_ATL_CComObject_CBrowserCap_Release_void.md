# ATL::CComObject<CBrowserCap>::Release(void)

- ea: `0x180005c60`
- end: `0x180005ce1`
- name: `?Release@?$CComObject@VCBrowserCap@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005cf0`

## callees

- `0x180005c60`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CBrowserCap>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 4);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 4, i - 1, i);
        i = *((_DWORD *)a1 + 4) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180005c60  mov     [rsp+arg_0], rbx
0x180005c65  push    rdi
0x180005c66  sub     rsp, 20h
0x180005c6a  mov     r8d, [rcx+10h]
0x180005c6e  mov     rbx, rcx
0x180005c71  mov     ecx, 7FFFFFFFh
0x180005c76  jmp     short loc_180005C8A
0x180005c78  lea     edx, [r8-1]
0x180005c7c  mov     eax, r8d
0x180005c7f  lock cmpxchg [rbx+10h], edx
0x180005c84  jz      short loc_180005C8F
0x180005c86  mov     r8d, [rbx+10h]
0x180005c8a  cmp     r8d, ecx
0x180005c8d  jnz     short loc_180005C78
0x180005c8f  lea     edi, [r8-1]
0x180005c93  test    edi, edi
0x180005c95  jnz     short loc_180005CD4
0x180005c97  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005c9e  mov     rax, [rcx]
0x180005ca1  mov     rax, [rax+8]
0x180005ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005caa  test    rbx, rbx
0x180005cad  jz      short loc_180005CC1
0x180005caf  mov     rax, [rbx]
0x180005cb2  lea     edx, [rdi+1]
0x180005cb5  mov     rcx, rbx
0x180005cb8  mov     rax, [rax+28h]
0x180005cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cc1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005cc8  mov     rdx, [rcx]
0x180005ccb  mov     rax, [rdx+10h]
0x180005ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cd4  mov     rbx, [rsp+28h+arg_0]
0x180005cd9  mov     eax, edi
0x180005cdb  add     rsp, 20h
0x180005cdf  pop     rdi
0x180005ce0  retn
```
