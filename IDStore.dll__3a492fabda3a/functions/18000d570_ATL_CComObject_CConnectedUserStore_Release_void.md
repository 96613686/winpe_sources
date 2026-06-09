# ATL::CComObject<CConnectedUserStore>::Release(void)

- ea: `0x18000d570`
- end: `0x18000d5f6`
- name: `?Release@?$CComObject@VCConnectedUserStore@@@ATL@@UEAAKXZ`
- size: `134`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011b60`

## callees

- `0x18000d570`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CConnectedUserStore>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // edx
  unsigned __int32 v3; // ebx

  for ( i = *((_DWORD *)a1 + 4); i != 0x7FFFFFFF; i = *((_DWORD *)a1 + 4) )
  {
    if ( i == _InterlockedCompareExchange(a1 + 4, i - 1, i) )
      break;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 80LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x18000d570  mov     [rsp+arg_0], rbx
0x18000d575  push    rdi
0x18000d576  sub     rsp, 20h
0x18000d57a  mov     edx, [rcx+10h]
0x18000d57d  mov     rdi, rcx
0x18000d580  cmp     edx, 7FFFFFFFh
0x18000d586  jnz     short loc_18000D5DB
0x18000d588  lea     ebx, [rdx-1]
0x18000d58b  test    ebx, ebx
0x18000d58d  jnz     short loc_18000D5CE
0x18000d58f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000d596  mov     rax, [rcx]
0x18000d599  mov     rax, [rax+8]
0x18000d59d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5a2  test    rdi, rdi
0x18000d5a5  jz      short loc_18000D5BB
0x18000d5a7  mov     rax, [rdi]
0x18000d5aa  mov     edx, 1
0x18000d5af  mov     rcx, rdi
0x18000d5b2  mov     rax, [rax+50h]
0x18000d5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5bb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000d5c2  mov     rdx, [rcx]
0x18000d5c5  mov     rax, [rdx+10h]
0x18000d5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5ce  mov     eax, ebx
0x18000d5d0  mov     rbx, [rsp+28h+arg_0]
0x18000d5d5  add     rsp, 20h
0x18000d5d9  pop     rdi
0x18000d5da  retn
0x18000d5db  lea     r8d, [rdx-1]
0x18000d5df  mov     eax, edx
0x18000d5e1  lock cmpxchg [rcx+10h], r8d
0x18000d5e7  jz      short loc_18000D588
0x18000d5e9  mov     edx, [rcx+10h]
0x18000d5ec  cmp     edx, 7FFFFFFFh
0x18000d5f2  jnz     short loc_18000D5DB
0x18000d5f4  jmp     short loc_18000D588
```
