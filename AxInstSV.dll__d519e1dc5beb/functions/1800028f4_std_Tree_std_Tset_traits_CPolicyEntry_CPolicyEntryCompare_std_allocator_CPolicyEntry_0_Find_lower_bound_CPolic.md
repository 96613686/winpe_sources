# std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Find_lower_bound<CPolicyEntry *>(CPolicyEntry * const &)

- ea: `0x1800028f4`
- end: `0x18000296f`
- name: `??$_Find_lower_bound@PEAVCPolicyEntry@@@?$_Tree@V?$_Tset_traits@PEAVCPolicyEntry@@UCPolicyEntryCompare@@V?$allocator@PEAVCPolicyEntry@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@std@@@1@AEBQEAVCPolicyEntry@@@Z`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800027b4`
- `0x1800038dc`

## callees

- `0x1800028f4`
- `0x180002ca8`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Find_lower_bound<CPolicyEntry *>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rbx
  int v7; // eax

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    if ( CPolicyEntryCompare::operator()(a1, (__int64)(v6 + 4), a3) )
    {
      v6 += 2;
      v7 = 0;
    }
    else
    {
      a2[2] = v6;
      v7 = 1;
    }
    *((_DWORD *)a2 + 2) = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x1800028f4  mov     [rsp+arg_0], rbx
0x1800028f9  mov     [rsp+arg_8], rsi
0x1800028fe  push    rdi
0x1800028ff  sub     rsp, 20h
0x180002903  mov     rax, [rcx]
0x180002906  mov     rsi, r8
0x180002909  mov     rdi, rdx
0x18000290c  mov     r9, [rax+8]
0x180002910  mov     [rdx], r9
0x180002913  mov     rbx, r9
0x180002916  mov     qword ptr [rdx+8], 0
0x18000291e  mov     rax, [rcx]
0x180002921  mov     [rdx+10h], rax
0x180002925  cmp     byte ptr [r9+19h], 0
0x18000292a  jnz     short loc_18000295C
0x18000292c  lea     rdx, [rbx+20h]
0x180002930  mov     [rdi], rbx
0x180002933  mov     r8, rsi
0x180002936  call    ??RCPolicyEntryCompare@@QEBA_NAEBQEAVCPolicyEntry@@0@Z; CPolicyEntryCompare::operator()(CPolicyEntry * const &,CPolicyEntry * const &)
0x18000293b  test    al, al
0x18000293d  jz      short loc_180002947
0x18000293f  add     rbx, 10h
0x180002943  xor     eax, eax
0x180002945  jmp     short loc_180002950
0x180002947  mov     [rdi+10h], rbx
0x18000294b  mov     eax, 1
0x180002950  mov     [rdi+8], eax
0x180002953  mov     rbx, [rbx]
0x180002956  cmp     byte ptr [rbx+19h], 0
0x18000295a  jz      short loc_18000292C
0x18000295c  mov     rbx, [rsp+28h+arg_0]
0x180002961  mov     rax, rdi
0x180002964  mov     rsi, [rsp+28h+arg_8]
0x180002969  add     rsp, 20h
0x18000296d  pop     rdi
0x18000296e  retn
```
