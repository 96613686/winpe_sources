# ATL::CComObject<CMidi2SchedulerTransform>::Release(void)

- ea: `0x180007570`
- end: `0x1800075f1`
- name: `?Release@?$CComObject@VCMidi2SchedulerTransform@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007570`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMidi2SchedulerTransform>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180007570  mov     [rsp+arg_0], rbx
0x180007575  push    rdi
0x180007576  sub     rsp, 20h
0x18000757a  mov     r8d, [rcx+8]
0x18000757e  mov     rbx, rcx
0x180007581  mov     ecx, 7FFFFFFFh
0x180007586  jmp     short loc_18000759A
0x180007588  lea     edx, [r8-1]
0x18000758c  mov     eax, r8d
0x18000758f  lock cmpxchg [rbx+8], edx
0x180007594  jz      short loc_18000759F
0x180007596  mov     r8d, [rbx+8]
0x18000759a  cmp     r8d, ecx
0x18000759d  jnz     short loc_180007588
0x18000759f  lea     edi, [r8-1]
0x1800075a3  test    edi, edi
0x1800075a5  jnz     short loc_1800075E4
0x1800075a7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800075ae  mov     rax, [rcx]
0x1800075b1  mov     rax, [rax+8]
0x1800075b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075ba  test    rbx, rbx
0x1800075bd  jz      short loc_1800075D1
0x1800075bf  mov     rax, [rbx]
0x1800075c2  lea     edx, [rdi+1]
0x1800075c5  mov     rcx, rbx
0x1800075c8  mov     rax, [rax+20h]
0x1800075cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075d1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800075d8  mov     rdx, [rcx]
0x1800075db  mov     rax, [rdx+10h]
0x1800075df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075e4  mov     rbx, [rsp+28h+arg_0]
0x1800075e9  mov     eax, edi
0x1800075eb  add     rsp, 20h
0x1800075ef  pop     rdi
0x1800075f0  retn
```
