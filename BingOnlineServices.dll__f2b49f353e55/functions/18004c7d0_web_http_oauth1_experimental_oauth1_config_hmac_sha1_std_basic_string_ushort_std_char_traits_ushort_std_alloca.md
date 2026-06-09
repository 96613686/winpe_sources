# web::http::oauth1::experimental::oauth1_config::_hmac_sha1(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004c7d0`
- end: `0x18004c9a9`
- name: `?_hmac_sha1@oauth1_config@experimental@oauth1@http@web@@CA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@0@Z`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18004b998`

## callees

- `0x180004fa0`
- `0x180005e6c`
- `0x18000979c`
- `0x18000e588`
- `0x18000eca4`
- `0x18001f380`
- `0x18003c0b0`
- `0x18004c7d0`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18004c95b`
- `bcrypt!BCryptDestroyHash` at `0x18004c95b`
- `bcrypt!BCryptFinishHash` at `0x18004c94c`
- `bcrypt!BCryptFinishHash` at `0x18004c94c`
- `bcrypt!BCryptHashData` at `0x18004c934`
- `bcrypt!BCryptHashData` at `0x18004c934`
- `bcrypt!BCryptCreateHash` at `0x18004c913`
- `bcrypt!BCryptCreateHash` at `0x18004c913`
- `bcrypt!BCryptGetProperty` at `0x18004c88c`
- `bcrypt!BCryptGetProperty` at `0x18004c88c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004c858`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004c858`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004c96c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004c96c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall web::http::oauth1::experimental::oauth1_config::_hmac_sha1(__int64 a1)
{
  PUCHAR v2; // rdx
  __int64 v3; // rsi
  unsigned __int64 v4; // rcx
  UCHAR *v5; // rax
  size_t v6; // rbx
  UCHAR *v7; // rax
  UCHAR *v8; // rax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-29h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-21h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-19h] BYREF
  int v13; // [rsp+58h] [rbp-11h]
  ULONG pcbResult; // [rsp+5Ch] [rbp-Dh] BYREF
  __int64 v15; // [rsp+60h] [rbp-9h]
  _BYTE v16[16]; // [rsp+68h] [rbp-1h] BYREF
  ULONG cbInput; // [rsp+78h] [rbp+Fh]
  _BYTE v18[16]; // [rsp+88h] [rbp+1Fh] BYREF
  ULONG cbSecret; // [rsp+98h] [rbp+2Fh]

  v15 = a1;
  phAlgorithm = 0;
  phHash = 0;
  std::vector<std::shared_ptr<pplx::details::_Task_impl<unsigned char>>>::vector<std::shared_ptr<pplx::details::_Task_impl<unsigned char>>>();
  v13 = 1;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  utility::conversions::utf16_to_utf8(v18);
  utility::conversions::utf16_to_utf8(v16);
  if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", 0, 8u) < 0
    || BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0) < 0 )
  {
    goto LABEL_13;
  }
  v2 = *(PUCHAR *)a1;
  v3 = *(_QWORD *)(a1 + 8);
  v4 = v3 - *(_QWORD *)a1;
  if ( *(unsigned int *)pbOutput < v4 )
  {
    v5 = &v2[*(unsigned int *)pbOutput];
LABEL_9:
    *(_QWORD *)(a1 + 8) = v5;
    goto LABEL_10;
  }
  if ( *(unsigned int *)pbOutput > v4 )
  {
    if ( (unsigned __int64)*(unsigned int *)pbOutput <= *(_QWORD *)(a1 + 16) - (_QWORD)v2 )
    {
      v6 = *(unsigned int *)pbOutput - v4;
      memset_0(*(void **)(a1 + 8), 0, v6);
      v5 = (UCHAR *)(v6 + v3);
      goto LABEL_9;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a1, *(unsigned int *)pbOutput);
  }
LABEL_10:
  v7 = (UCHAR *)std::_String_val<std::_Simple_types<char>>::_Myptr(v18);
  if ( BCryptCreateHash(phAlgorithm, &phHash, 0, 0, v7, cbSecret, 0) >= 0 )
  {
    v8 = (UCHAR *)std::_String_val<std::_Simple_types<char>>::_Myptr(v16);
    if ( BCryptHashData(phHash, v8, cbInput, 0) >= 0 )
      BCryptFinishHash(phHash, *(PUCHAR *)a1, *(ULONG *)pbOutput, 0);
  }
LABEL_13:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  std::string::_Tidy_deallocate(v16);
  std::string::_Tidy_deallocate(v18);
  return a1;
}

```

## disassembly

```asm
0x18004c7d0  mov     [rsp-8+arg_18], rbx
0x18004c7d5  push    rbp
0x18004c7d6  push    rsi
0x18004c7d7  push    rdi
0x18004c7d8  lea     rbp, [rsp-47h]
0x18004c7dd  sub     rsp, 0B0h
0x18004c7e4  mov     rax, cs:__security_cookie
0x18004c7eb  xor     rax, rsp
0x18004c7ee  mov     [rbp+57h+var_18], rax
0x18004c7f2  mov     rbx, r8
0x18004c7f5  mov     rdi, rcx
0x18004c7f8  mov     [rbp+57h+var_60], rcx
0x18004c7fc  mov     [rbp+57h+var_68], 0
0x18004c803  mov     [rbp+57h+phAlgorithm], 0
0x18004c80b  mov     [rbp+57h+phHash], 0
0x18004c813  call    ??0?$vector@V?$shared_ptr@U?$_Task_impl@E@details@pplx@@@std@@V?$allocator@V?$shared_ptr@U?$_Task_impl@E@details@pplx@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<pplx::details::_Task_impl<uchar>>>::vector<std::shared_ptr<pplx::details::_Task_impl<uchar>>>(void)
0x18004c818  mov     [rbp+57h+var_68], 1
0x18004c81f  mov     dword ptr [rbp+57h+pbOutput], 0
0x18004c826  mov     [rbp+57h+var_64], 0
0x18004c82d  lea     rcx, [rbp+57h+var_38]
0x18004c831  call    ?utf16_to_utf8@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::utf16_to_utf8(std::wstring const &)
0x18004c836  nop
0x18004c837  mov     rdx, rbx
0x18004c83a  lea     rcx, [rbp+57h+var_58]
0x18004c83e  call    ?utf16_to_utf8@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::utf16_to_utf8(std::wstring const &)
0x18004c843  nop
0x18004c844  mov     r9d, 8; dwFlags
0x18004c84a  xor     r8d, r8d; pszImplementation
0x18004c84d  lea     rdx, pszAlgId; "SHA1"
0x18004c854  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x18004c858  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004c85e  test    eax, eax
0x18004c860  js      loc_18004C952
0x18004c866  mov     [rsp+0C0h+dwFlags], 0; dwFlags
0x18004c86e  lea     rax, [rbp+57h+var_64]
0x18004c872  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x18004c877  mov     r9d, 4; cbOutput
0x18004c87d  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x18004c881  lea     rdx, pszProperty; "HashDigestLength"
0x18004c888  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x18004c88c  call    cs:__imp_BCryptGetProperty
0x18004c892  test    eax, eax
0x18004c894  js      loc_18004C952
0x18004c89a  mov     ebx, dword ptr [rbp+57h+pbOutput]
0x18004c89d  mov     rdx, [rdi]
0x18004c8a0  mov     rsi, [rdi+8]
0x18004c8a4  mov     rcx, rsi
0x18004c8a7  sub     rcx, rdx
0x18004c8aa  cmp     rbx, rcx
0x18004c8ad  jnb     short loc_18004C8B5
0x18004c8af  lea     rax, [rdx+rbx]
0x18004c8b3  jmp     short loc_18004C8E4
0x18004c8b5  jbe     short loc_18004C8E8
0x18004c8b7  mov     rax, [rdi+10h]
0x18004c8bb  sub     rax, rdx
0x18004c8be  cmp     rbx, rax
0x18004c8c1  jbe     short loc_18004C8D0
0x18004c8c3  mov     rdx, rbx
0x18004c8c6  mov     rcx, rdi
0x18004c8c9  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18004c8ce  jmp     short loc_18004C8E8
0x18004c8d0  sub     rbx, rcx
0x18004c8d3  mov     r8, rbx; Size
0x18004c8d6  xor     edx, edx; Val
0x18004c8d8  mov     rcx, rsi; void *
0x18004c8db  call    memset_0
0x18004c8e0  lea     rax, [rbx+rsi]
0x18004c8e4  mov     [rdi+8], rax
0x18004c8e8  lea     rcx, [rbp+57h+var_38]
0x18004c8ec  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004c8f1  mov     [rsp+0C0h+var_90], 0; dwFlags
0x18004c8f9  mov     edx, [rbp+57h+cbSecret]
0x18004c8fc  mov     [rsp+0C0h+dwFlags], edx; cbSecret
0x18004c900  mov     [rsp+0C0h+pcbResult], rax; pbSecret
0x18004c905  xor     r9d, r9d; cbHashObject
0x18004c908  xor     r8d, r8d; pbHashObject
0x18004c90b  lea     rdx, [rbp+57h+phHash]; phHash
0x18004c90f  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18004c913  call    cs:__imp_BCryptCreateHash
0x18004c919  test    eax, eax
0x18004c91b  js      short loc_18004C952
0x18004c91d  lea     rcx, [rbp+57h+var_58]
0x18004c921  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004c926  mov     rdx, rax; pbInput
0x18004c929  xor     r9d, r9d; dwFlags
0x18004c92c  mov     r8d, [rbp+57h+cbInput]; cbInput
0x18004c930  mov     rcx, [rbp+57h+phHash]; hHash
0x18004c934  call    cs:__imp_BCryptHashData
0x18004c93a  test    eax, eax
0x18004c93c  js      short loc_18004C952
0x18004c93e  xor     r9d, r9d; dwFlags
0x18004c941  mov     r8d, dword ptr [rbp+57h+pbOutput]; cbOutput
0x18004c945  mov     rdx, [rdi]; pbOutput
0x18004c948  mov     rcx, [rbp+57h+phHash]; hHash
0x18004c94c  call    cs:__imp_BCryptFinishHash
0x18004c952  mov     rcx, [rbp+57h+phHash]; hHash
0x18004c956  test    rcx, rcx
0x18004c959  jz      short loc_18004C961
0x18004c95b  call    cs:__imp_BCryptDestroyHash
0x18004c961  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18004c965  test    rcx, rcx
0x18004c968  jz      short loc_18004C973
0x18004c96a  xor     edx, edx; dwFlags
0x18004c96c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18004c972  nop
0x18004c973  lea     rcx, [rbp+57h+var_58]
0x18004c977  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004c97c  nop
0x18004c97d  lea     rcx, [rbp+57h+var_38]
0x18004c981  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004c986  mov     rax, rdi
0x18004c989  mov     rcx, [rbp+57h+var_18]
0x18004c98d  xor     rcx, rsp; StackCookie
0x18004c990  call    __security_check_cookie
0x18004c995  mov     rbx, [rsp+0C0h+arg_18]
0x18004c99d  add     rsp, 0B0h
0x18004c9a4  pop     rdi
0x18004c9a5  pop     rsi
0x18004c9a6  pop     rbp
0x18004c9a7  retn
```
