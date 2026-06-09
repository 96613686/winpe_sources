# Sharp::Util::Xml::CNode::GetName(void)

- ea: `0x140012a74`
- end: `0x140012b8e`
- name: `?GetName@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `282`
- prototype: `OLECHAR *__fastcall(__int64, OLECHAR *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a9ac`
- `0x140013808`
- `0x140013918`

## callees

- `0x140001d1c`
- `0x1400070e4`
- `0x140007428`
- `0x140007e8c`
- `0x1400119d4`
- `0x140012a74`
- `0x140013b10`
- `0x140016010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140012b5f`
- `OLEAUT32!__imp_SysFreeString` at `0x140012b5f`

## pseudocode

```c
OLECHAR *__fastcall Sharp::Util::Xml::CNode::GetName(__int64 a1, OLECHAR *a2)
{
  int v4; // eax
  int v5; // edi
  BSTR bstrString[3]; // [rsp+28h] [rbp-70h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+40h] [rbp-58h] BYREF

  bstrString[1] = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
  bstrString[0] = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)(a1 + 8) + 56LL))(*(_QWORD *)(a1 + 8), bstrString);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids,
        (unsigned int)v4);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v5);
    throw (xml_exception *)pExceptionObject;
  }
  Sharp::Util::ComHelper::ComBstrToString((__int64)a2, (__int64 *)bstrString);
  SysFreeString(bstrString[0]);
  return a2;
}

```

## disassembly

```asm
0x140012a74  mov     [rsp+arg_10], rbx
0x140012a79  mov     [rsp+arg_18], rsi
0x140012a7e  push    rdi
0x140012a7f  sub     rsp, 90h
0x140012a86  mov     rax, cs:__security_cookie
0x140012a8d  xor     rax, rsp
0x140012a90  mov     [rsp+98h+var_18], rax
0x140012a98  mov     rbx, rdx
0x140012a9b  mov     rdi, rcx
0x140012a9e  mov     [rsp+98h+var_68], rdx
0x140012aa3  mov     [rsp+98h+var_78], 0
0x140012aab  lea     rsi, WPP_GLOBAL_Control
0x140012ab2  mov     rcx, cs:WPP_GLOBAL_Control
0x140012ab9  cmp     rcx, rsi
0x140012abc  jz      short loc_140012AD9
0x140012abe  test    byte ptr [rcx+1Ch], 8
0x140012ac2  jz      short loc_140012AD9
0x140012ac4  mov     edx, 0Dh
0x140012ac9  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140012ad0  mov     rcx, [rcx+10h]
0x140012ad4  call    WPP_SF_
0x140012ad9  mov     [rsp+98h+bstrString], 0
0x140012ae2  mov     rcx, [rdi+8]
0x140012ae6  mov     rax, [rcx]
0x140012ae9  lea     rdx, [rsp+98h+bstrString]
0x140012aee  mov     rax, [rax+38h]
0x140012af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012af7  mov     edi, eax
0x140012af9  test    eax, eax
0x140012afb  jns     short loc_140012B45
0x140012afd  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b04  cmp     rcx, rsi
0x140012b07  jz      short loc_140012B27
0x140012b09  test    byte ptr [rcx+1Ch], 1
0x140012b0d  jz      short loc_140012B27
0x140012b0f  mov     edx, 0Eh
0x140012b14  mov     r9d, eax
0x140012b17  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140012b1e  mov     rcx, [rcx+10h]
0x140012b22  call    WPP_SF_d
0x140012b27  mov     edx, edi; int
0x140012b29  lea     rcx, [rsp+98h+pExceptionObject]; this
0x140012b2e  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x140012b33  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x140012b3a  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x140012b3f  call    _CxxThrowException_0
0x140012b45  lea     rdx, [rsp+98h+bstrString]
0x140012b4a  mov     rcx, rbx
0x140012b4d  call    ?ComBstrToString@ComHelper@Util@Sharp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVCComBSTR@ATL@@@Z; Sharp::Util::ComHelper::ComBstrToString(ATL::CComBSTR const &)
0x140012b52  mov     [rsp+98h+var_78], 1
0x140012b5a  mov     rcx, [rsp+98h+bstrString]; bstrString
0x140012b5f  call    cs:__imp_SysFreeString
0x140012b65  mov     rax, rbx
0x140012b68  mov     rcx, [rsp+98h+var_18]
0x140012b70  xor     rcx, rsp; StackCookie
0x140012b73  call    __security_check_cookie
0x140012b78  lea     r11, [rsp+98h+var_8]
0x140012b80  mov     rbx, [r11+20h]
0x140012b84  mov     rsi, [r11+28h]
0x140012b88  mov     rsp, r11
0x140012b8b  pop     rdi
0x140012b8c  retn
```
