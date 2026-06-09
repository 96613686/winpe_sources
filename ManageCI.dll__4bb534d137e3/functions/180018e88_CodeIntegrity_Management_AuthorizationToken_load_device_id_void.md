# CodeIntegrity::Management::AuthorizationToken::load_device_id(void)

- ea: `0x180018e88`
- end: `0x180018f2c`
- name: `?load_device_id@AuthorizationToken@Management@CodeIntegrity@@AEAAXXZ`
- size: `164`
- prototype: `void __fastcall(CodeIntegrity::Management::AuthorizationToken *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180018b50`

## callees

- `0x180002ab4`
- `0x180005308`
- `0x18000830c`
- `0x180012f70`
- `0x180016b80`
- `0x180017ec0`
- `0x180018490`
- `0x180018e88`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CodeIntegrity::Management::AuthorizationToken::load_device_id(void **this)
{
  _OWORD *v2; // rax
  const void *v3[3]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v4[32]; // [rsp+48h] [rbp-20h] BYREF
  void *v5; // [rsp+78h] [rbp+10h] BYREF

  try
  {
    CodeIntegrity::Management::detail::SbcpTokenView::get_binary(
      (__int64)this,
      (__int64)v3,
      -2130706432,
      L"Authorization",
      L"UnlockID");
    v2 = operator new(0x20u);
    *v2 = 0;
    v2[1] = 0;
    v5 = v2;
    std::unique_ptr<std::array<unsigned char,32>>::operator=<std::default_delete<std::array<unsigned char,32>>,0>(
      this + 26,
      &v5);
    std::unique_ptr<std::array<unsigned char,32>>::~unique_ptr<std::array<unsigned char,32>>(&v5);
    std::copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>,std::_Array_iterator<unsigned char,64>>(
      &v5,
      v3[0],
      (__int64)v3[1],
      (char *)this[26]);
    CodeIntegrity::Management::GetSModeUnlockID(v4);
    std::vector<unsigned char>::_Tidy((__int64)v4);
    std::vector<unsigned char>::_Tidy((__int64)v3);
  }
  catch ( std::exception )
  {
  }
}

```

## disassembly

```asm
0x180018e88  push    rbx
0x180018e8a  sub     rsp, 60h
0x180018e8e  mov     rbx, rcx
0x180018e91  lea     rax, aUnlockid; "UnlockID"
0x180018e98  mov     [rsp+68h+var_48], rax
0x180018e9d  lea     r9, aAuthorization; "Authorization"
0x180018ea4  mov     r8d, 81000000h
0x180018eaa  lea     rdx, [rsp+68h+var_38]
0x180018eaf  call    ?get_binary@SbcpTokenView@detail@Management@CodeIntegrity@@IEAA?AV?$vector@EV?$allocator@E@std@@@std@@IPEBG0@Z; CodeIntegrity::Management::detail::SbcpTokenView::get_binary(uint,ushort const *,ushort const *)
0x180018eb4  nop
0x180018eb5  mov     ecx, 20h ; ' '; Size
0x180018eba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018ebf  xorps   xmm0, xmm0
0x180018ec2  movups  xmmword ptr [rax], xmm0
0x180018ec5  movups  xmmword ptr [rax+10h], xmm0
0x180018ec9  mov     [rsp+68h+arg_8], rax
0x180018ece  lea     rdx, [rsp+68h+arg_8]
0x180018ed3  lea     rcx, [rbx+0D0h]
0x180018eda  call    ??$?4U?$default_delete@V?$array@E$0CA@@std@@@std@@$0A@@?$unique_ptr@V?$array@E$0CA@@std@@U?$default_delete@V?$array@E$0CA@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<std::array<uchar,32>>::operator=<std::default_delete<std::array<uchar,32>>,0>(std::unique_ptr<std::array<uchar,32>> &&)
0x180018edf  lea     rcx, [rsp+68h+arg_8]
0x180018ee4  call    ??1?$unique_ptr@V?$array@E$0CA@@std@@U?$default_delete@V?$array@E$0CA@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::array<uchar,32>>::~unique_ptr<std::array<uchar,32>>(void)
0x180018ee9  mov     r9, [rbx+0D0h]
0x180018ef0  mov     r8, [rsp+68h+var_30]
0x180018ef5  mov     rdx, [rsp+68h+var_38]
0x180018efa  lea     rcx, [rsp+68h+arg_8]
0x180018eff  call    ??$copy@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@V?$_Array_iterator@E$0EA@@2@@std@@YA?AV?$_Array_iterator@E$0EA@@0@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@0@0V10@@Z; std::copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Array_iterator<uchar,64>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Array_iterator<uchar,64>)
0x180018f04  lea     rcx, [rsp+68h+var_20]
0x180018f09  call    ?GetSModeUnlockID@Management@CodeIntegrity@@YA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; CodeIntegrity::Management::GetSModeUnlockID(void)
0x180018f0e  lea     rcx, [rsp+68h+var_20]
0x180018f13  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180018f18  nop
0x180018f19  lea     rcx, [rsp+68h+var_38]
0x180018f1e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180018f23  nop
0x180018f24  jmp     short $+2
0x180018f26  add     rsp, 60h
0x180018f2a  pop     rbx
0x180018f2b  retn
```
