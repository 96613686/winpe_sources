# ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>::Release(void)

- ea: `0x180008590`
- end: `0x180008611`
- name: `?Release@?$CComAggObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008590`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>::Release(volatile signed __int32 *a1)
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
0x180008590  mov     [rsp+arg_0], rbx
0x180008595  push    rdi
0x180008596  sub     rsp, 20h
0x18000859a  mov     r8d, [rcx+8]
0x18000859e  mov     rbx, rcx
0x1800085a1  mov     ecx, 7FFFFFFFh
0x1800085a6  jmp     short loc_1800085BA
0x1800085a8  lea     edx, [r8-1]
0x1800085ac  mov     eax, r8d
0x1800085af  lock cmpxchg [rbx+8], edx
0x1800085b4  jz      short loc_1800085BF
0x1800085b6  mov     r8d, [rbx+8]
0x1800085ba  cmp     r8d, ecx
0x1800085bd  jnz     short loc_1800085A8
0x1800085bf  lea     edi, [r8-1]
0x1800085c3  test    edi, edi
0x1800085c5  jnz     short loc_180008604
0x1800085c7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800085ce  mov     rax, [rcx]
0x1800085d1  mov     rax, [rax+8]
0x1800085d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085da  test    rbx, rbx
0x1800085dd  jz      short loc_1800085F1
0x1800085df  mov     rax, [rbx]
0x1800085e2  lea     edx, [rdi+1]
0x1800085e5  mov     rcx, rbx
0x1800085e8  mov     rax, [rax+18h]
0x1800085ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085f1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800085f8  mov     rdx, [rcx]
0x1800085fb  mov     rax, [rdx+10h]
0x1800085ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008604  mov     rbx, [rsp+28h+arg_0]
0x180008609  mov     eax, edi
0x18000860b  add     rsp, 20h
0x18000860f  pop     rdi
0x180008610  retn
```
