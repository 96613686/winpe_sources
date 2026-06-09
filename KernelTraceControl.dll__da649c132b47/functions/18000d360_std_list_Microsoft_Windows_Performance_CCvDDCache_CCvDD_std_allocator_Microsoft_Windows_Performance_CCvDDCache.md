# std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::push_back(Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)

- ea: `0x18000d360`
- end: `0x18000d420`
- name: `?push_back@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAXAEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z`
- size: `192`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800093c0`
- `0x180009704`

## callees

- `0x1800022e4`
- `0x18000d360`
- `0x18000f3b4`
- `0x180013178`
- `0x180026e30`
- `0x180026f66`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // r8
  __int64 v5; // rax
  __int64 *result; // rax
  _BYTE v7[40]; // [rsp+28h] [rbp-80h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-58h] BYREF

  v3 = *(_QWORD *)(a1 + 8);
  v4 = std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Buynode(a1, v3, *(_QWORD *)(v3 + 8), a2, -2);
  v5 = *(_QWORD *)(a1 + 16);
  if ( v5 == 0x186186186186186LL )
  {
    std::string::string(v7, "list<T> too long");
    std::length_error::length_error(pExceptionObject, v7);
    throw (std::length_error *)pExceptionObject;
  }
  *(_QWORD *)(a1 + 16) = v5 + 1;
  *(_QWORD *)(v3 + 8) = v4;
  result = *(__int64 **)(v4 + 8);
  *result = v4;
  return result;
}

```

## disassembly

```asm
0x18000d360  mov     rax, rsp
0x18000d363  push    rdi
0x18000d364  sub     rsp, 0A0h
0x18000d36b  mov     [rsp+0A8h+var_88], 0FFFFFFFFFFFFFFFEh
0x18000d374  mov     [rax+18h], rbx
0x18000d378  mov     rax, cs:__security_cookie
0x18000d37f  xor     rax, rsp
0x18000d382  mov     [rsp+0A8h+var_18], rax
0x18000d38a  mov     rbx, rcx
0x18000d38d  mov     rdi, [rcx+8]
0x18000d391  mov     r9, rdx
0x18000d394  mov     r8, [rdi+8]
0x18000d398  mov     rdx, rdi
0x18000d39b  call    ?_Buynode@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@IEAAPEAU_Node@?$_List_nod@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@2@PEAU342@0AEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Buynode(std::_List_nod<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Node *,std::_List_nod<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Node *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)
0x18000d3a0  mov     r8, rax
0x18000d3a3  mov     rax, [rbx+10h]
0x18000d3a7  mov     rdx, 186186186186186h
0x18000d3b1  sub     rdx, rax
0x18000d3b4  cmp     rdx, 1
0x18000d3b8  jnb     short loc_18000D3ED
0x18000d3ba  lea     rdx, aListTTooLong; "list<T> too long"
0x18000d3c1  lea     rcx, [rsp+0A8h+var_80]
0x18000d3c6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18000d3cb  nop
0x18000d3cc  lea     rdx, [rsp+0A8h+var_80]
0x18000d3d1  lea     rcx, [rsp+0A8h+pExceptionObject]
0x18000d3d6  call    ??0length_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::length_error::length_error(std::string const &)
0x18000d3db  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x18000d3e2  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18000d3e7  call    _CxxThrowException_0
0x18000d3ed  inc     rax
0x18000d3f0  mov     [rbx+10h], rax
0x18000d3f4  mov     [rdi+8], r8
0x18000d3f8  mov     rax, [r8+8]
0x18000d3fc  mov     [rax], r8
0x18000d3ff  mov     rcx, [rsp+0A8h+var_18]
0x18000d407  xor     rcx, rsp; StackCookie
0x18000d40a  call    __security_check_cookie
0x18000d40f  mov     rbx, [rsp+0A8h+arg_10]
0x18000d417  add     rsp, 0A0h
0x18000d41e  pop     rdi
0x18000d41f  retn
```
