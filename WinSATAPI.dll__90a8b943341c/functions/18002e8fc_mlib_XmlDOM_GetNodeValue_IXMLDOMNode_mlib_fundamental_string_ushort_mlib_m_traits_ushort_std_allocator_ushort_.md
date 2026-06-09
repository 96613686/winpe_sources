# mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,bool &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18002e8fc`
- end: `0x18002e993`
- name: `?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEA_NPEAV42@@Z`
- size: `151`
- prototype: `__int64 __fastcall(int, int, int, int, BSTR bstrString)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002cbd0`
- `0x18002ceec`

## callees

- `0x180007850`
- `0x180008490`
- `0x1800084f0`
- `0x18000d9c0`
- `0x18002e8fc`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002e979`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e979`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall mlib::XmlDOM::GetNodeValue(__int64 a1, __int64 a2, char a3, bool *a4, BSTR bstrString)
{
  int NodeValue; // ebx
  OLECHAR *v7; // rcx
  int v9; // [rsp+20h] [rbp-28h]
  _QWORD v10[3]; // [rsp+30h] [rbp-18h] BYREF
  int v11; // [rsp+60h] [rbp+18h] BYREF

  LOBYTE(v11) = a3;
  v10[1] = -2;
  bstrString = 0;
  NodeValue = mlib::XmlDOM::GetNodeValue(a1, a2, 0, (__int64)&bstrString, v9);
  v7 = bstrString;
  if ( NodeValue >= 0 && bstrString )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v10,
      bstrString);
    v11 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::cvt_as_type_signed<int>(
      v10[0],
      *(_QWORD *)(v10[0] + 24LL),
      *(_QWORD *)v10[0],
      &v11);
    *a4 = v11 != 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v10);
    v7 = bstrString;
  }
  SysFreeString(v7);
  return (unsigned int)NodeValue;
}

```

## disassembly

```asm
0x18002e8fc  mov     rax, rsp
0x18002e8ff  mov     [rax+18h], r8b
0x18002e903  push    rdi
0x18002e904  sub     rsp, 40h
0x18002e908  mov     qword ptr [rax-10h], 0FFFFFFFFFFFFFFFEh
0x18002e910  mov     [rax+8], rbx
0x18002e914  mov     rdi, r9
0x18002e917  and     qword ptr [rax+28h], 0
0x18002e91c  lea     r9, [rax+28h]
0x18002e920  xor     r8d, r8d
0x18002e923  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAPEAGPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ushort * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18002e928  mov     ebx, eax
0x18002e92a  mov     rcx, [rsp+48h+bstrString]
0x18002e92f  test    eax, eax
0x18002e931  js      short loc_18002E979
0x18002e933  test    rcx, rcx
0x18002e936  jz      short loc_18002E979
0x18002e938  mov     rdx, rcx
0x18002e93b  lea     rcx, [rsp+48h+var_18]
0x18002e940  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x18002e945  and     [rsp+48h+arg_10], 0
0x18002e94a  mov     rcx, [rsp+48h+var_18]
0x18002e94f  lea     r9, [rsp+48h+arg_10]
0x18002e954  mov     r8, [rcx]
0x18002e957  mov     rdx, [rcx+18h]
0x18002e95b  call    ??$cvt_as_type_signed@H@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEBA_NPEBG_KAEAH_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::cvt_as_type_signed<int>(ushort const *,unsigned __int64,int &,bool)
0x18002e960  cmp     [rsp+48h+arg_10], 0
0x18002e965  setnz   al
0x18002e968  mov     [rdi], al
0x18002e96a  lea     rcx, [rsp+48h+var_18]
0x18002e96f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18002e974  mov     rcx, [rsp+48h+bstrString]; bstrString
0x18002e979  call    cs:__imp_SysFreeString
0x18002e980  nop     dword ptr [rax+rax+00h]
0x18002e985  mov     eax, ebx
0x18002e987  mov     rbx, [rsp+48h+arg_0]
0x18002e98c  add     rsp, 40h
0x18002e990  pop     rdi
0x18002e991  retn
```
