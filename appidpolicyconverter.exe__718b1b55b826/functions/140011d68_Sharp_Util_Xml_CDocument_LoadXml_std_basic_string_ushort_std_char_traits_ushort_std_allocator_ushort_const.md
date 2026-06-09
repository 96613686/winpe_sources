# Sharp::Util::Xml::CDocument::LoadXml(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140011d68`
- end: `0x140011e7d`
- name: `?LoadXml@CDocument@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a9ac`

## callees

- `0x140001d1c`
- `0x1400070e4`
- `0x140007428`
- `0x140007de4`
- `0x1400119d4`
- `0x140011d68`
- `0x140013b10`
- `0x140016010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140011e02`
- `OLEAUT32!__imp_SysFreeString` at `0x140011e02`

## pseudocode

```c
__int64 __fastcall Sharp::Util::Xml::CDocument::LoadXml(__int64 a1, const unsigned __int16 *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, __int16 *); // rsi
  ATL::CComBSTR *v6; // rax
  int v7; // ebx
  __int64 result; // rax
  __int16 v9; // [rsp+20h] [rbp-78h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-70h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+30h] [rbp-68h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_e137bfdab7b23ac569be7b05e5d5c80a_Traceguids);
  v9 = -1;
  v4 = *(_QWORD *)(a1 + 8);
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, __int16 *))(*(_QWORD *)v4 + 520LL);
  if ( *((_QWORD *)a2 + 3) >= 8u )
    a2 = *(const unsigned __int16 **)a2;
  v6 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a2);
  v7 = v5(v4, *(_QWORD *)v6, &v9);
  SysFreeString(bstrString);
  result = 0;
  if ( v7 < 0 || !v9 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_e137bfdab7b23ac569be7b05e5d5c80a_Traceguids,
        (unsigned int)v7);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v7);
    throw (xml_exception *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x140011d68  mov     [rsp+arg_10], rbx
0x140011d6d  push    rbp
0x140011d6e  push    rsi
0x140011d6f  push    rdi
0x140011d70  sub     rsp, 80h
0x140011d77  mov     rax, cs:__security_cookie
0x140011d7e  xor     rax, rsp
0x140011d81  mov     [rsp+98h+var_28], rax
0x140011d86  mov     rbx, rdx
0x140011d89  mov     rdi, rcx
0x140011d8c  lea     rbp, WPP_GLOBAL_Control
0x140011d93  mov     rcx, cs:WPP_GLOBAL_Control
0x140011d9a  cmp     rcx, rbp
0x140011d9d  jz      short loc_140011DBA
0x140011d9f  test    byte ptr [rcx+1Ch], 8
0x140011da3  jz      short loc_140011DBA
0x140011da5  mov     edx, 10h
0x140011daa  lea     r8, WPP_e137bfdab7b23ac569be7b05e5d5c80a_Traceguids
0x140011db1  mov     rcx, [rcx+10h]
0x140011db5  call    WPP_SF_
0x140011dba  or      eax, 0FFFFFFFFh
0x140011dbd  mov     [rsp+98h+var_78], ax
0x140011dc2  mov     rdi, [rdi+8]
0x140011dc6  mov     rax, [rdi]
0x140011dc9  mov     rsi, [rax+208h]
0x140011dd0  cmp     qword ptr [rbx+18h], 8
0x140011dd5  jb      short loc_140011DDA
0x140011dd7  mov     rbx, [rbx]
0x140011dda  mov     rdx, rbx; unsigned __int16 *
0x140011ddd  lea     rcx, [rsp+98h+bstrString]; this
0x140011de2  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x140011de7  nop
0x140011de8  lea     r8, [rsp+98h+var_78]
0x140011ded  mov     rdx, [rax]
0x140011df0  mov     rcx, rdi
0x140011df3  mov     rax, rsi
0x140011df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011dfb  mov     ebx, eax
0x140011dfd  mov     rcx, [rsp+98h+bstrString]; bstrString
0x140011e02  call    cs:__imp_SysFreeString
0x140011e08  xor     eax, eax
0x140011e0a  test    ebx, ebx
0x140011e0c  js      short loc_140011E15
0x140011e0e  cmp     [rsp+98h+var_78], ax
0x140011e13  jnz     short loc_140011E5D
0x140011e15  mov     rcx, cs:WPP_GLOBAL_Control
0x140011e1c  cmp     rcx, rbp
0x140011e1f  jz      short loc_140011E3F
0x140011e21  test    byte ptr [rcx+1Ch], 1
0x140011e25  jz      short loc_140011E3F
0x140011e27  mov     edx, 11h
0x140011e2c  mov     r9d, ebx
0x140011e2f  lea     r8, WPP_e137bfdab7b23ac569be7b05e5d5c80a_Traceguids
0x140011e36  mov     rcx, [rcx+10h]
0x140011e3a  call    WPP_SF_d
0x140011e3f  mov     edx, ebx; int
0x140011e41  lea     rcx, [rsp+98h+pExceptionObject]; this
0x140011e46  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x140011e4b  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x140011e52  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x140011e57  call    _CxxThrowException_0
0x140011e5d  mov     rcx, [rsp+98h+var_28]
0x140011e62  xor     rcx, rsp; StackCookie
0x140011e65  call    __security_check_cookie
0x140011e6a  mov     rbx, [rsp+98h+arg_10]
0x140011e72  add     rsp, 80h
0x140011e79  pop     rdi
0x140011e7a  pop     rsi
0x140011e7b  pop     rbp
0x140011e7c  retn
```
