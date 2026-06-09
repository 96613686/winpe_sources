# ATL::CComObject<CGenericEnum>::Release(void)

- ea: `0x18000c210`
- end: `0x18000c298`
- name: `?Release@?$CComObject@VCGenericEnum@@@ATL@@UEAAKXZ`
- size: `136`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000c210`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CGenericEnum>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // edx
  unsigned __int32 v3; // ebx

  for ( i = *((_DWORD *)a1 + 2); i != 0x7FFFFFFF; i = *((_DWORD *)a1 + 2) )
  {
    if ( i == _InterlockedCompareExchange(a1 + 2, i - 1, i) )
      break;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 56LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x18000c210  mov     [rsp+arg_0], rbx
0x18000c215  push    rdi
0x18000c216  sub     rsp, 20h
0x18000c21a  mov     edx, [rcx+8]
0x18000c21d  mov     rdi, rcx
0x18000c220  cmp     edx, 7FFFFFFFh
0x18000c226  jnz     short loc_18000C27D
0x18000c228  lea     ebx, [rdx-1]
0x18000c22b  test    ebx, ebx
0x18000c22d  jnz     short loc_18000C25A
0x18000c22f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c236  mov     rax, [rcx]
0x18000c239  mov     rax, [rax+8]
0x18000c23d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c242  test    rdi, rdi
0x18000c245  jnz     short loc_18000C267
0x18000c247  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c24e  mov     rdx, [rcx]
0x18000c251  mov     rax, [rdx+10h]
0x18000c255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c25a  mov     eax, ebx
0x18000c25c  mov     rbx, [rsp+28h+arg_0]
0x18000c261  add     rsp, 20h
0x18000c265  pop     rdi
0x18000c266  retn
0x18000c267  mov     rax, [rdi]
0x18000c26a  mov     edx, 1
0x18000c26f  mov     rcx, rdi
0x18000c272  mov     rax, [rax+38h]
0x18000c276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c27b  jmp     short loc_18000C247
0x18000c27d  lea     r8d, [rdx-1]
0x18000c281  mov     eax, edx
0x18000c283  lock cmpxchg [rcx+8], r8d
0x18000c289  jz      short loc_18000C228
0x18000c28b  mov     edx, [rcx+8]
0x18000c28e  cmp     edx, 7FFFFFFFh
0x18000c294  jnz     short loc_18000C27D
0x18000c296  jmp     short loc_18000C228
```
