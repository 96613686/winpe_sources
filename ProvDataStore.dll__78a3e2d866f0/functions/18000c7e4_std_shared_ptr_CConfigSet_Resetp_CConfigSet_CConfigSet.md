# std::shared_ptr<CConfigSet>::_Resetp<CConfigSet>(CConfigSet *)

- ea: `0x18000c7e4`
- end: `0x18000c87c`
- name: `??$_Resetp@VCConfigSet@@@?$shared_ptr@VCConfigSet@@@std@@AEAAXPEAVCConfigSet@@@Z`
- size: `152`
- prototype: `unsigned __int64 __fastcall(CConfigSet **, CConfigSet *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e184`

## callees

- `0x1800018f4`
- `0x18000c7e4`
- `0x180012010`

## pseudocode

```c
unsigned __int64 __fastcall std::shared_ptr<CConfigSet>::_Resetp<CConfigSet>(CConfigSet **a1, CConfigSet *a2)
{
  unsigned __int64 result; // rax
  CConfigSet *v5; // rbx
  volatile signed __int32 *v6; // rdi
  __int64 v7; // [rsp+0h] [rbp-38h] BYREF

  try
  {
    result = (unsigned __int64)operator new(0x18u);
    v5 = (CConfigSet *)result;
    if ( result )
    {
      *(_DWORD *)(result + 8) = 1;
      *(_DWORD *)(result + 12) = 1;
      result = (unsigned __int64)&std::_Ref_count<CConfigSet>::`vftable';
      *(_QWORD *)v5 = &std::_Ref_count<CConfigSet>::`vftable';
      *((_QWORD *)v5 + 2) = a2;
    }
    v6 = (volatile signed __int32 *)a1[1];
    if ( v6 )
    {
      result = (unsigned int)_InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        result = (unsigned int)_InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF);
        if ( (_DWORD)result == 1 )
          result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
    }
    a1[1] = v5;
    *a1 = a2;
  }
  catch ( ... )
  {
    if ( a2 )
      CConfigSet::`scalar deleting destructor'(a2, (unsigned int)&v7);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000c7e4  mov     [rsp+arg_0], rbx
0x18000c7e9  mov     [rsp+arg_8], rdx
0x18000c7ee  push    rsi
0x18000c7ef  push    rdi
0x18000c7f0  push    r14
0x18000c7f2  sub     rsp, 20h
0x18000c7f6  mov     r14, rdx
0x18000c7f9  mov     rsi, rcx
0x18000c7fc  mov     ecx, 18h; Size
0x18000c801  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c806  mov     rbx, rax
0x18000c809  test    rbx, rbx
0x18000c80c  jz      short loc_18000C827
0x18000c80e  mov     eax, 1
0x18000c813  mov     [rbx+8], eax
0x18000c816  mov     [rbx+0Ch], eax
0x18000c819  lea     rax, ??_7?$_Ref_count@VCConfigSet@@@std@@6B@; const std::_Ref_count<CConfigSet>::`vftable'
0x18000c820  mov     [rbx], rax
0x18000c823  mov     [rbx+10h], r14
0x18000c827  mov     rdi, [rsi+8]
0x18000c82b  test    rdi, rdi
0x18000c82e  jz      short loc_18000C867
0x18000c830  or      eax, 0FFFFFFFFh
0x18000c833  lock xadd [rdi+8], eax
0x18000c838  cmp     eax, 1
0x18000c83b  jnz     short loc_18000C867
0x18000c83d  mov     rax, [rdi]
0x18000c840  mov     rcx, rdi
0x18000c843  mov     rax, [rax]
0x18000c846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c84b  or      eax, 0FFFFFFFFh
0x18000c84e  lock xadd [rdi+0Ch], eax
0x18000c853  cmp     eax, 1
0x18000c856  jnz     short loc_18000C867
0x18000c858  mov     rax, [rdi]
0x18000c85b  mov     rcx, rdi
0x18000c85e  mov     rax, [rax+8]
0x18000c862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c867  mov     [rsi+8], rbx
0x18000c86b  mov     [rsi], r14
0x18000c86e  mov     rbx, [rsp+38h+arg_0]
0x18000c873  add     rsp, 20h
0x18000c877  pop     r14
0x18000c879  pop     rdi
0x18000c87a  pop     rsi
0x18000c87b  retn
```
