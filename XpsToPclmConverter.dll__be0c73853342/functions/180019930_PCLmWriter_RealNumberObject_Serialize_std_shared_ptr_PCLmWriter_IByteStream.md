# PCLmWriter::RealNumberObject::Serialize(std::shared_ptr<PCLmWriter::IByteStream>)

- ea: `0x180019930`
- end: `0x1800199d2`
- name: `?Serialize@RealNumberObject@PCLmWriter@@UEBAXV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@Z`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800015f0`
- `0x1800101cc`
- `0x180010618`
- `0x180010718`
- `0x180019930`
- `0x18001a61c`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PCLmWriter::RealNumberObject::Serialize(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  _BYTE *v5; // rcx
  unsigned int v6; // r9d
  std::_Ref_count_base *v7; // rcx
  _BYTE v8[16]; // [rsp+28h] [rbp-30h] BYREF

  PCLmWriter::CharHelper::ToString((__int64)v8, COERCE_FLOAT(*(_QWORD *)(a1 + 24)), 5u);
  v3 = std::_String_val<std::_Simple_types<char>>::_Myptr(v8);
  v5 = (_BYTE *)(v3 + v4 - 1);
  if ( *v5 == 48 )
  {
    do
    {
      v6 = v4;
      --v5;
      v4 = (unsigned int)(v4 - 1);
    }
    while ( *v5 == 48 );
    if ( *v5 == 46 )
      v4 = v6;
  }
  (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*a2 + 24LL))(*a2, v3, v4);
  std::string::_Tidy_deallocate(v8);
  v7 = (std::_Ref_count_base *)a2[1];
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
}

```

## disassembly

```asm
0x180019930  push    rbx
0x180019932  sub     rsp, 50h
0x180019936  mov     rax, cs:__security_cookie
0x18001993d  xor     rax, rsp
0x180019940  mov     [rsp+58h+var_10], rax
0x180019945  mov     rbx, rdx
0x180019948  mov     [rsp+58h+var_38], rdx
0x18001994d  mov     r8d, 5
0x180019953  movsd   xmm1, qword ptr [rcx+18h]
0x180019958  lea     rcx, [rsp+58h+var_30]
0x18001995d  call    ?ToString@CharHelper@PCLmWriter@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@NI@Z; PCLmWriter::CharHelper::ToString(double,uint)
0x180019962  nop
0x180019963  mov     r8d, [rsp+58h+var_20]
0x180019968  lea     rcx, [rsp+58h+var_30]
0x18001996d  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180019972  mov     rdx, rax
0x180019975  lea     rcx, [r8-1]
0x180019979  add     rcx, rax
0x18001997c  cmp     byte ptr [rcx], 30h ; '0'
0x18001997f  jnz     short loc_180019996
0x180019981  mov     r9d, r8d
0x180019984  dec     rcx
0x180019987  dec     r8d
0x18001998a  mov     al, [rcx]
0x18001998c  cmp     al, 30h ; '0'
0x18001998e  jz      short loc_180019981
0x180019990  cmp     al, 2Eh ; '.'
0x180019992  cmovz   r8d, r9d
0x180019996  mov     rcx, [rbx]
0x180019999  mov     rax, [rcx]
0x18001999c  mov     rax, [rax+18h]
0x1800199a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199a5  nop
0x1800199a6  lea     rcx, [rsp+58h+var_30]
0x1800199ab  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800199b0  nop
0x1800199b1  mov     rcx, [rbx+8]; this
0x1800199b5  test    rcx, rcx
0x1800199b8  jz      short loc_1800199BF
0x1800199ba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800199bf  mov     rcx, [rsp+58h+var_10]
0x1800199c4  xor     rcx, rsp; StackCookie
0x1800199c7  call    __security_check_cookie
0x1800199cc  add     rsp, 50h
0x1800199d0  pop     rbx
0x1800199d1  retn
```
