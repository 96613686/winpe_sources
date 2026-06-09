# ATL::CComAggObject<CMidi2SchedulerTransform>::Release(void)

- ea: `0x1800074c0`
- end: `0x180007541`
- name: `?Release@?$CComAggObject@VCMidi2SchedulerTransform@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800074c0`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMidi2SchedulerTransform>::Release(volatile signed __int32 *a1)
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
0x1800074c0  mov     [rsp+arg_0], rbx
0x1800074c5  push    rdi
0x1800074c6  sub     rsp, 20h
0x1800074ca  mov     r8d, [rcx+8]
0x1800074ce  mov     rbx, rcx
0x1800074d1  mov     ecx, 7FFFFFFFh
0x1800074d6  jmp     short loc_1800074EA
0x1800074d8  lea     edx, [r8-1]
0x1800074dc  mov     eax, r8d
0x1800074df  lock cmpxchg [rbx+8], edx
0x1800074e4  jz      short loc_1800074EF
0x1800074e6  mov     r8d, [rbx+8]
0x1800074ea  cmp     r8d, ecx
0x1800074ed  jnz     short loc_1800074D8
0x1800074ef  lea     edi, [r8-1]
0x1800074f3  test    edi, edi
0x1800074f5  jnz     short loc_180007534
0x1800074f7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800074fe  mov     rax, [rcx]
0x180007501  mov     rax, [rax+8]
0x180007505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000750a  test    rbx, rbx
0x18000750d  jz      short loc_180007521
0x18000750f  mov     rax, [rbx]
0x180007512  lea     edx, [rdi+1]
0x180007515  mov     rcx, rbx
0x180007518  mov     rax, [rax+18h]
0x18000751c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007521  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007528  mov     rdx, [rcx]
0x18000752b  mov     rax, [rdx+10h]
0x18000752f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007534  mov     rbx, [rsp+28h+arg_0]
0x180007539  mov     eax, edi
0x18000753b  add     rsp, 20h
0x18000753f  pop     rdi
0x180007540  retn
```
