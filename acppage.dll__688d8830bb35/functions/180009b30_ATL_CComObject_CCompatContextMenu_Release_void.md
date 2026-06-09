# ATL::CComObject<CCompatContextMenu>::Release(void)

- ea: `0x180009b30`
- end: `0x180009bb1`
- name: `?Release@?$CComObject@VCCompatContextMenu@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009bc0`
- `0x180009bd0`
- `0x180009be0`

## callees

- `0x180009b30`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCompatContextMenu>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 8);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 8, i - 1, i);
        i = *((_DWORD *)a1 + 8) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180009b30  mov     [rsp+arg_0], rbx
0x180009b35  push    rdi
0x180009b36  sub     rsp, 20h
0x180009b3a  mov     r8d, [rcx+20h]
0x180009b3e  mov     rbx, rcx
0x180009b41  mov     ecx, 7FFFFFFFh
0x180009b46  jmp     short loc_180009B5A
0x180009b48  lea     edx, [r8-1]
0x180009b4c  mov     eax, r8d
0x180009b4f  lock cmpxchg [rbx+20h], edx
0x180009b54  jz      short loc_180009B5F
0x180009b56  mov     r8d, [rbx+20h]
0x180009b5a  cmp     r8d, ecx
0x180009b5d  jnz     short loc_180009B48
0x180009b5f  lea     edi, [r8-1]
0x180009b63  test    edi, edi
0x180009b65  jnz     short loc_180009BA4
0x180009b67  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009b6e  mov     rax, [rcx]
0x180009b71  mov     rax, [rax+8]
0x180009b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b7a  test    rbx, rbx
0x180009b7d  jz      short loc_180009B91
0x180009b7f  mov     rax, [rbx]
0x180009b82  lea     edx, [rdi+1]
0x180009b85  mov     rcx, rbx
0x180009b88  mov     rax, [rax+18h]
0x180009b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b91  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009b98  mov     rdx, [rcx]
0x180009b9b  mov     rax, [rdx+10h]
0x180009b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ba4  mov     rbx, [rsp+28h+arg_0]
0x180009ba9  mov     eax, edi
0x180009bab  add     rsp, 20h
0x180009baf  pop     rdi
0x180009bb0  retn
```
