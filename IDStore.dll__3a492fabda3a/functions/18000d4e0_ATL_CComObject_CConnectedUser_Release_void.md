# ATL::CComObject<CConnectedUser>::Release(void)

- ea: `0x18000d4e0`
- end: `0x18000d566`
- name: `?Release@?$CComObject@VCConnectedUser@@@ATL@@UEAAKXZ`
- size: `134`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000d4e0`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CConnectedUser>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 48LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x18000d4e0  mov     [rsp+arg_0], rbx
0x18000d4e5  push    rdi
0x18000d4e6  sub     rsp, 20h
0x18000d4ea  mov     edx, [rcx+8]
0x18000d4ed  mov     rdi, rcx
0x18000d4f0  cmp     edx, 7FFFFFFFh
0x18000d4f6  jnz     short loc_18000D54B
0x18000d4f8  lea     ebx, [rdx-1]
0x18000d4fb  test    ebx, ebx
0x18000d4fd  jnz     short loc_18000D53E
0x18000d4ff  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000d506  mov     rax, [rcx]
0x18000d509  mov     rax, [rax+8]
0x18000d50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d512  test    rdi, rdi
0x18000d515  jz      short loc_18000D52B
0x18000d517  mov     rax, [rdi]
0x18000d51a  mov     edx, 1
0x18000d51f  mov     rcx, rdi
0x18000d522  mov     rax, [rax+30h]
0x18000d526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d52b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000d532  mov     rdx, [rcx]
0x18000d535  mov     rax, [rdx+10h]
0x18000d539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d53e  mov     eax, ebx
0x18000d540  mov     rbx, [rsp+28h+arg_0]
0x18000d545  add     rsp, 20h
0x18000d549  pop     rdi
0x18000d54a  retn
0x18000d54b  lea     r8d, [rdx-1]
0x18000d54f  mov     eax, edx
0x18000d551  lock cmpxchg [rcx+8], r8d
0x18000d557  jz      short loc_18000D4F8
0x18000d559  mov     edx, [rcx+8]
0x18000d55c  cmp     edx, 7FFFFFFFh
0x18000d562  jnz     short loc_18000D54B
0x18000d564  jmp     short loc_18000D4F8
```
