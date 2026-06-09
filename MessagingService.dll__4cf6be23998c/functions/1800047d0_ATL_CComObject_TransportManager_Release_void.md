# ATL::CComObject<TransportManager>::Release(void)

- ea: `0x1800047d0`
- end: `0x180004851`
- name: `?Release@?$CComObject@VTransportManager@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004860`
- `0x180004870`

## callees

- `0x1800047d0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<TransportManager>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 6);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 6, i - 1, i);
        i = *((_DWORD *)a1 + 6) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800047d0  mov     [rsp+arg_0], rbx
0x1800047d5  push    rdi
0x1800047d6  sub     rsp, 20h
0x1800047da  mov     r8d, [rcx+18h]
0x1800047de  mov     rbx, rcx
0x1800047e1  mov     ecx, 7FFFFFFFh
0x1800047e6  jmp     short loc_1800047FA
0x1800047e8  lea     edx, [r8-1]
0x1800047ec  mov     eax, r8d
0x1800047ef  lock cmpxchg [rbx+18h], edx
0x1800047f4  jz      short loc_1800047FF
0x1800047f6  mov     r8d, [rbx+18h]
0x1800047fa  cmp     r8d, ecx
0x1800047fd  jnz     short loc_1800047E8
0x1800047ff  lea     edi, [r8-1]
0x180004803  test    edi, edi
0x180004805  jnz     short loc_180004844
0x180004807  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000480e  mov     rax, [rcx]
0x180004811  mov     rax, [rax+8]
0x180004815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000481a  test    rbx, rbx
0x18000481d  jz      short loc_180004831
0x18000481f  mov     rax, [rbx]
0x180004822  lea     edx, [rdi+1]
0x180004825  mov     rcx, rbx
0x180004828  mov     rax, [rax+20h]
0x18000482c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004831  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004838  mov     rdx, [rcx]
0x18000483b  mov     rax, [rdx+10h]
0x18000483f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004844  mov     rbx, [rsp+28h+arg_0]
0x180004849  mov     eax, edi
0x18000484b  add     rsp, 20h
0x18000484f  pop     rdi
0x180004850  retn
```
