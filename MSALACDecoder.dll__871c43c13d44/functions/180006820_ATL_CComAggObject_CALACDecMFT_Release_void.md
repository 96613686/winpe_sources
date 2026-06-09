# ATL::CComAggObject<CALACDecMFT>::Release(void)

- ea: `0x180006820`
- end: `0x1800068a1`
- name: `?Release@?$CComAggObject@VCALACDecMFT@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006820`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CALACDecMFT>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v3 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180006820  mov     [rsp+arg_0], rbx
0x180006825  push    rdi
0x180006826  sub     rsp, 20h
0x18000682a  mov     r8d, [rcx+8]
0x18000682e  mov     rbx, rcx
0x180006831  mov     ecx, 7FFFFFFFh
0x180006836  jmp     short loc_18000684A
0x180006838  lea     edx, [r8-1]
0x18000683c  mov     eax, r8d
0x18000683f  lock cmpxchg [rbx+8], edx
0x180006844  jz      short loc_18000684F
0x180006846  mov     r8d, [rbx+8]
0x18000684a  cmp     r8d, ecx
0x18000684d  jnz     short loc_180006838
0x18000684f  lea     edi, [r8-1]
0x180006853  test    edi, edi
0x180006855  jnz     short loc_180006894
0x180006857  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000685e  mov     rax, [rcx]
0x180006861  mov     rax, [rax+8]
0x180006865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000686a  test    rbx, rbx
0x18000686d  jz      short loc_180006881
0x18000686f  mov     rax, [rbx]
0x180006872  lea     edx, [rdi+1]
0x180006875  mov     rcx, rbx
0x180006878  mov     rax, [rax+18h]
0x18000687c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006881  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006888  mov     rdx, [rcx]
0x18000688b  mov     rax, [rdx+10h]
0x18000688f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006894  mov     rbx, [rsp+28h+arg_0]
0x180006899  mov     eax, edi
0x18000689b  add     rsp, 20h
0x18000689f  pop     rdi
0x1800068a0  retn
```
