# CPolicyCheck::DeletedMarkedEntries(HKEY__ *,int,int)

- ea: `0x18000383c`
- end: `0x1800038d6`
- name: `?DeletedMarkedEntries@CPolicyCheck@@QEAAJPEAUHKEY__@@HH@Z`
- size: `154`
- prototype: `int(CPolicyCheck *__hidden this, HKEY, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003afc`
- `0x180004364`

## callees

- `0x180002c5c`
- `0x18000383c`
- `0x180004f80`
- `0x1800054cc`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CPolicyCheck::DeletedMarkedEntries(CPolicyCheck *this, HKEY a2, int a3, int a4)
{
  _QWORD *v7; // rsi
  __int64 v8; // rbx
  __int64 v10; // rdi
  _BYTE v11[72]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+70h] [rbp+8h] BYREF

  v7 = (_QWORD *)((char *)this + 112);
  v8 = **((_QWORD **)this + 14);
LABEL_2:
  v12 = v8;
  while ( v8 != *v7 )
  {
    v10 = *(_QWORD *)(v8 + 32);
    if ( *(_DWORD *)(v10 + 44) || a4 )
    {
      v8 = *(_QWORD *)std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::erase(
                        v7,
                        v11,
                        v8);
      if ( a3 )
      {
        try
        {
          Utils::DeleteKeyRecursive(a2, *(const unsigned __int16 **)(v10 + 8));
          (**(void (__fastcall ***)(__int64, __int64))v10)(v10, 1);
        }
        catch ( std::bad_alloc )
        {
          LODWORD(v12) = -2147024882;
          return 2147942414LL;
        }
      }
      goto LABEL_2;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>,std::_Iterator_base0>::operator++(&v12);
    v8 = v12;
  }
  return 0;
}

```

## disassembly

```asm
0x18000383c  push    rbx
0x18000383e  push    rsi
0x18000383f  push    rdi
0x180003840  push    r12
0x180003842  push    r14
0x180003844  push    r15
0x180003846  sub     rsp, 38h
0x18000384a  mov     r14d, r9d
0x18000384d  mov     r12d, r8d
0x180003850  mov     r15, rdx
0x180003853  lea     rsi, [rcx+70h]
0x180003857  mov     rbx, [rsi]
0x18000385a  mov     rbx, [rbx]
0x18000385d  mov     [rsp+68h+arg_0], rbx
0x180003862  cmp     rbx, [rsi]
0x180003865  jnz     short loc_18000386B
0x180003867  xor     eax, eax
0x180003869  jmp     short loc_1800038C8
0x18000386b  mov     rdi, [rbx+20h]
0x18000386f  cmp     dword ptr [rdi+2Ch], 0
0x180003873  jnz     short loc_18000388B
0x180003875  test    r14d, r14d
0x180003878  jnz     short loc_18000388B
0x18000387a  lea     rcx, [rsp+68h+arg_0]
0x18000387f  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>,std::_Iterator_base0>::operator++(void)
0x180003884  mov     rbx, [rsp+68h+arg_0]
0x180003889  jmp     short loc_180003862
0x18000388b  mov     r8, rbx
0x18000388e  lea     rdx, [rsp+68h+var_48]
0x180003893  mov     rcx, rsi
0x180003896  call    ?erase@?$_Tree@V?$_Tset_traits@PEAVCPolicyEntry@@UCPolicyEntryCompare@@V?$allocator@PEAVCPolicyEntry@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVCPolicyEntry@@@std@@@std@@@2@V32@@Z; std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>>)
0x18000389b  mov     rbx, [rax]
0x18000389e  test    r12d, r12d
0x1800038a1  jz      short loc_18000385D
0x1800038a3  mov     rdx, [rdi+8]; unsigned __int16 *
0x1800038a7  mov     rcx, r15; HKEY
0x1800038aa  call    ?DeleteKeyRecursive@Utils@@SAJPEAUHKEY__@@PEBG@Z; Utils::DeleteKeyRecursive(HKEY__ *,ushort const *)
0x1800038af  mov     rax, [rdi]
0x1800038b2  mov     edx, 1
0x1800038b7  mov     rcx, rdi
0x1800038ba  mov     rax, [rax]
0x1800038bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038c2  jmp     short loc_18000385D
0x1800038c4  mov     eax, dword ptr [rsp+68h+arg_0]
0x1800038c8  add     rsp, 38h
0x1800038cc  pop     r15
0x1800038ce  pop     r14
0x1800038d0  pop     r12
0x1800038d2  pop     rdi
0x1800038d3  pop     rsi
0x1800038d4  pop     rbx
0x1800038d5  retn
```
