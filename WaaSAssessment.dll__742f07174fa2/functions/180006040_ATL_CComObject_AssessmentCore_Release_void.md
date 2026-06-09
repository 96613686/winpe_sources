# ATL::CComObject<AssessmentCore>::Release(void)

- ea: `0x180006040`
- end: `0x1800060c4`
- name: `?Release@?$CComObject@VAssessmentCore@@@ATL@@UEAAKXZ`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006040`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<AssessmentCore>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 272LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180006040  mov     [rsp+arg_0], rbx
0x180006045  push    rdi
0x180006046  sub     rsp, 20h
0x18000604a  mov     r8d, [rcx+8]
0x18000604e  mov     rbx, rcx
0x180006051  mov     ecx, 7FFFFFFFh
0x180006056  jmp     short loc_18000606A
0x180006058  lea     edx, [r8-1]
0x18000605c  mov     eax, r8d
0x18000605f  lock cmpxchg [rbx+8], edx
0x180006064  jz      short loc_18000606F
0x180006066  mov     r8d, [rbx+8]
0x18000606a  cmp     r8d, ecx
0x18000606d  jnz     short loc_180006058
0x18000606f  lea     edi, [r8-1]
0x180006073  test    edi, edi
0x180006075  jnz     short loc_1800060B7
0x180006077  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000607e  mov     rax, [rcx]
0x180006081  mov     rax, [rax+8]
0x180006085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000608a  test    rbx, rbx
0x18000608d  jz      short loc_1800060A4
0x18000608f  mov     rax, [rbx]
0x180006092  lea     edx, [rdi+1]
0x180006095  mov     rcx, rbx
0x180006098  mov     rax, [rax+110h]
0x18000609f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060a4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800060ab  mov     rdx, [rcx]
0x1800060ae  mov     rax, [rdx+10h]
0x1800060b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060b7  mov     rbx, [rsp+28h+arg_0]
0x1800060bc  mov     eax, edi
0x1800060be  add     rsp, 20h
0x1800060c2  pop     rdi
0x1800060c3  retn
```
