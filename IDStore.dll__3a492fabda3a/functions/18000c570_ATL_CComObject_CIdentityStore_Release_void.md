# ATL::CComObject<CIdentityStore>::Release(void)

- ea: `0x18000c570`
- end: `0x18000c5f6`
- name: `?Release@?$CComObject@VCIdentityStore@@@ATL@@UEAAKXZ`
- size: `134`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011b70`
- `0x180011b80`

## callees

- `0x18000c570`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIdentityStore>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // edx
  unsigned __int32 v3; // ebx

  for ( i = *((_DWORD *)a1 + 6); i != 0x7FFFFFFF; i = *((_DWORD *)a1 + 6) )
  {
    if ( i == _InterlockedCompareExchange(a1 + 6, i - 1, i) )
      break;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 72LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x18000c570  mov     [rsp+arg_0], rbx
0x18000c575  push    rdi
0x18000c576  sub     rsp, 20h
0x18000c57a  mov     edx, [rcx+18h]
0x18000c57d  mov     rdi, rcx
0x18000c580  cmp     edx, 7FFFFFFFh
0x18000c586  jnz     short loc_18000C5DB
0x18000c588  lea     ebx, [rdx-1]
0x18000c58b  test    ebx, ebx
0x18000c58d  jnz     short loc_18000C5CE
0x18000c58f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c596  mov     rax, [rcx]
0x18000c599  mov     rax, [rax+8]
0x18000c59d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5a2  test    rdi, rdi
0x18000c5a5  jz      short loc_18000C5BB
0x18000c5a7  mov     rax, [rdi]
0x18000c5aa  mov     edx, 1
0x18000c5af  mov     rcx, rdi
0x18000c5b2  mov     rax, [rax+48h]
0x18000c5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5bb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c5c2  mov     rdx, [rcx]
0x18000c5c5  mov     rax, [rdx+10h]
0x18000c5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5ce  mov     eax, ebx
0x18000c5d0  mov     rbx, [rsp+28h+arg_0]
0x18000c5d5  add     rsp, 20h
0x18000c5d9  pop     rdi
0x18000c5da  retn
0x18000c5db  lea     r8d, [rdx-1]
0x18000c5df  mov     eax, edx
0x18000c5e1  lock cmpxchg [rcx+18h], r8d
0x18000c5e7  jz      short loc_18000C588
0x18000c5e9  mov     edx, [rcx+18h]
0x18000c5ec  cmp     edx, 7FFFFFFFh
0x18000c5f2  jnz     short loc_18000C5DB
0x18000c5f4  jmp     short loc_18000C588
```
