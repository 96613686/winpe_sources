# ATL::CComObject<CMidi2UMP2BSTransform>::Release(void)

- ea: `0x180007460`
- end: `0x1800074e1`
- name: `?Release@?$CComObject@VCMidi2UMP2BSTransform@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007460`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMidi2UMP2BSTransform>::Release(volatile signed __int32 *a1)
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
0x180007460  mov     [rsp+arg_0], rbx
0x180007465  push    rdi
0x180007466  sub     rsp, 20h
0x18000746a  mov     r8d, [rcx+8]
0x18000746e  mov     rbx, rcx
0x180007471  mov     ecx, 7FFFFFFFh
0x180007476  jmp     short loc_18000748A
0x180007478  lea     edx, [r8-1]
0x18000747c  mov     eax, r8d
0x18000747f  lock cmpxchg [rbx+8], edx
0x180007484  jz      short loc_18000748F
0x180007486  mov     r8d, [rbx+8]
0x18000748a  cmp     r8d, ecx
0x18000748d  jnz     short loc_180007478
0x18000748f  lea     edi, [r8-1]
0x180007493  test    edi, edi
0x180007495  jnz     short loc_1800074D4
0x180007497  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000749e  mov     rax, [rcx]
0x1800074a1  mov     rax, [rax+8]
0x1800074a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074aa  test    rbx, rbx
0x1800074ad  jz      short loc_1800074C1
0x1800074af  mov     rax, [rbx]
0x1800074b2  lea     edx, [rdi+1]
0x1800074b5  mov     rcx, rbx
0x1800074b8  mov     rax, [rax+20h]
0x1800074bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074c1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800074c8  mov     rdx, [rcx]
0x1800074cb  mov     rax, [rdx+10h]
0x1800074cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074d4  mov     rbx, [rsp+28h+arg_0]
0x1800074d9  mov     eax, edi
0x1800074db  add     rsp, 20h
0x1800074df  pop     rdi
0x1800074e0  retn
```
