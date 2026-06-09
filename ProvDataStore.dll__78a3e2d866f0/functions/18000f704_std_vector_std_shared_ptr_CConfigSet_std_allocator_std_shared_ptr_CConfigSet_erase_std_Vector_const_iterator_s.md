# std::vector<std::shared_ptr<CConfigSet>,std::allocator<std::shared_ptr<CConfigSet>>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::shared_ptr<CConfigSet>>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::shared_ptr<CConfigSet>>>>)

- ea: `0x18000f704`
- end: `0x18000f788`
- name: `?erase@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VCConfigSet@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VCConfigSet@@@std@@@std@@@std@@@2@0@Z`
- size: `132`
- prototype: `__int64 **__fastcall(__int64 *, __int64 **, __int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000d424`
- `0x18000e184`

## callees

- `0x180009068`
- `0x18000a148`
- `0x18000f704`

## pseudocode

```c
__int64 **__fastcall std::vector<std::shared_ptr<CConfigSet>>::erase(
        __int64 *a1,
        __int64 **a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 *v4; // rdi
  __int64 v8; // r8
  __int64 *v9; // r15
  __int64 *v10; // rbp

  v4 = a4;
  if ( a3 == (__int64 *)*a1 && (v8 = a1[1], a4 == (__int64 *)v8) )
  {
    std::vector<std::shared_ptr<CConfigSet>>::_Destroy((__int64)a1, *a1, v8);
    a1[1] = *a1;
  }
  else if ( a3 != a4 )
  {
    v9 = (__int64 *)a1[1];
    v10 = a3;
    if ( a4 != v9 )
    {
      do
      {
        std::shared_ptr<CConfigSet>::operator=(v10, v4);
        v10 += 2;
        v4 += 2;
      }
      while ( v4 != v9 );
    }
    std::vector<std::shared_ptr<CConfigSet>>::_Destroy((__int64)a1, (__int64)v10, a1[1]);
    a1[1] = (__int64)v10;
  }
  *a2 = a3;
  return a2;
}

```

## disassembly

```asm
0x18000f704  push    rbx
0x18000f706  push    rbp
0x18000f707  push    rsi
0x18000f708  push    rdi
0x18000f709  push    r14
0x18000f70b  push    r15
0x18000f70d  sub     rsp, 28h
0x18000f711  mov     rdi, r9
0x18000f714  mov     rbx, r8
0x18000f717  mov     r14, rdx
0x18000f71a  mov     rsi, rcx
0x18000f71d  cmp     r8, [rcx]
0x18000f720  jnz     short loc_18000F72B
0x18000f722  mov     r8, [rcx+8]
0x18000f726  cmp     r9, r8
0x18000f729  jz      short loc_18000F766
0x18000f72b  cmp     rbx, r9
0x18000f72e  jz      short loc_18000F775
0x18000f730  mov     r15, [rcx+8]
0x18000f734  mov     rbp, rbx
0x18000f737  cmp     r9, r15
0x18000f73a  jz      short loc_18000F754
0x18000f73c  mov     rdx, rdi
0x18000f73f  mov     rcx, rbp
0x18000f742  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000f747  add     rbp, 10h
0x18000f74b  add     rdi, 10h
0x18000f74f  cmp     rdi, r15
0x18000f752  jnz     short loc_18000F73C
0x18000f754  mov     r8, [rsi+8]
0x18000f758  mov     rdx, rbp
0x18000f75b  call    ?_Destroy@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@IEAAXPEAV?$shared_ptr@VCConfigSet@@@2@0@Z; std::vector<std::shared_ptr<CConfigSet>>::_Destroy(std::shared_ptr<CConfigSet> *,std::shared_ptr<CConfigSet> *)
0x18000f760  mov     [rsi+8], rbp
0x18000f764  jmp     short loc_18000F775
0x18000f766  mov     rdx, [rcx]
0x18000f769  call    ?_Destroy@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@IEAAXPEAV?$shared_ptr@VCConfigSet@@@2@0@Z; std::vector<std::shared_ptr<CConfigSet>>::_Destroy(std::shared_ptr<CConfigSet> *,std::shared_ptr<CConfigSet> *)
0x18000f76e  mov     rax, [rsi]
0x18000f771  mov     [rsi+8], rax
0x18000f775  mov     [r14], rbx
0x18000f778  mov     rax, r14
0x18000f77b  add     rsp, 28h
0x18000f77f  pop     r15
0x18000f781  pop     r14
0x18000f783  pop     rdi
0x18000f784  pop     rsi
0x18000f785  pop     rbp
0x18000f786  pop     rbx
0x18000f787  retn
```
