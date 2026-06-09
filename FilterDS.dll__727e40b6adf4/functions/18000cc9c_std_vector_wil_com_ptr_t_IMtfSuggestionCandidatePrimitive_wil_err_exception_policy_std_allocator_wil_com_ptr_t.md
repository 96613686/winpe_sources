# std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>>::_Reserve(unsigned __int64)

- ea: `0x18000cc9c`
- end: `0x18000cd11`
- name: `?_Reserve@?$vector@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@IEAAX_K@Z`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009890`

## callees

- `0x18000cbb4`
- `0x18000cc9c`
- `0x18000cd9c`

## pseudocode

```c
__int64 __fastcall std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>::_Reserve(
        _QWORD *a1)
{
  __int64 v2; // rdx
  __int64 result; // rax
  __int64 v4; // rdx
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rcx

  v2 = a1[1];
  result = (a1[2] - v2) >> 3;
  if ( !result )
  {
    v4 = (v2 - *a1) >> 3;
    if ( v4 == 0x1FFFFFFFFFFFFFFFLL )
      std::vector<std::unique_ptr<FilterAgent>>::_Xlen(a1, 0x1FFFFFFFFFFFFFFFLL, a1);
    v5 = v4 + 1;
    v6 = (__int64)(a1[2] - *a1) >> 3;
    v7 = 0;
    if ( 0x1FFFFFFFFFFFFFFFLL - (v6 >> 1) >= v6 )
      v7 = v6 + (v6 >> 1);
    if ( v7 >= v5 )
      v5 = v7;
    return (__int64)std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>::_Reallocate(
                      (__int64)a1,
                      v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000cc9c  sub     rsp, 28h
0x18000cca0  mov     r9, [rcx+10h]
0x18000cca4  mov     r8, rcx
0x18000cca7  mov     rdx, [rcx+8]
0x18000ccab  mov     rax, r9
0x18000ccae  sub     rax, rdx
0x18000ccb1  sar     rax, 3
0x18000ccb5  cmp     rax, 1
0x18000ccb9  jnb     short loc_18000CD06
0x18000ccbb  sub     rdx, [rcx]
0x18000ccbe  mov     r10, 1FFFFFFFFFFFFFFFh
0x18000ccc8  sar     rdx, 3
0x18000cccc  mov     rax, r10
0x18000cccf  sub     rax, rdx
0x18000ccd2  cmp     rax, 1
0x18000ccd6  jb      short loc_18000CD0B
0x18000ccd8  sub     r9, [rcx]
0x18000ccdb  inc     rdx
0x18000ccde  sar     r9, 3
0x18000cce2  xor     ecx, ecx
0x18000cce4  mov     rax, r9
0x18000cce7  shr     rax, 1
0x18000ccea  sub     r10, rax
0x18000cced  add     rax, r9
0x18000ccf0  cmp     r10, r9
0x18000ccf3  cmovnb  rcx, rax
0x18000ccf7  cmp     rcx, rdx
0x18000ccfa  cmovnb  rdx, rcx
0x18000ccfe  mov     rcx, r8
0x18000cd01  call    ?_Reallocate@?$vector@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@IEAAX_K@Z; std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>::_Reallocate(unsigned __int64)
0x18000cd06  add     rsp, 28h
0x18000cd0a  retn
0x18000cd0b  call    ?_Xlen@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::unique_ptr<FilterAgent>>::_Xlen(void)
```
