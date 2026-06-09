# mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x1800074f0`
- end: `0x18000755f`
- name: `?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAV42@PEAV42@@Z`
- size: `111`
- prototype: `__int64 __fastcall(int, int, int, int, BSTR bstrString)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002ce4c`
- `0x18002ceec`
- `0x18002d020`

## callees

- `0x180003060`
- `0x1800074f0`
- `0x180007850`
- `0x18000be30`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180007545`
- `OLEAUT32!__imp_SysFreeString` at `0x180007545`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall mlib::XmlDOM::GetNodeValue(__int64 a1, __int64 a2, __int64 a3, __int64 a4, BSTR bstrString)
{
  int NodeValue; // ebx
  OLECHAR *v7; // rcx
  int v9; // [rsp+20h] [rbp-28h]

  bstrString = 0;
  NodeValue = mlib::XmlDOM::GetNodeValue(a1, a2, 0, (__int64)&bstrString, v9);
  v7 = bstrString;
  if ( NodeValue >= 0 && bstrString )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
      a4,
      bstrString);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::strip_lt_ws(a4);
    v7 = bstrString;
  }
  SysFreeString(v7);
  return (unsigned int)NodeValue;
}

```

## disassembly

```asm
0x1800074f0  push    rdi
0x1800074f2  sub     rsp, 40h
0x1800074f6  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800074ff  mov     [rsp+48h+arg_0], rbx
0x180007504  mov     rdi, r9
0x180007507  mov     [rsp+48h+bstrString], 0
0x180007510  lea     r9, [rsp+48h+bstrString]
0x180007515  xor     r8d, r8d
0x180007518  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAPEAGPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ushort * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18000751d  mov     ebx, eax
0x18000751f  mov     rcx, [rsp+48h+bstrString]
0x180007524  test    eax, eax
0x180007526  js      short loc_180007545
0x180007528  test    rcx, rcx
0x18000752b  jz      short loc_180007545
0x18000752d  mov     rdx, rcx
0x180007530  mov     rcx, rdi
0x180007533  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x180007538  mov     rcx, rdi
0x18000753b  call    ?strip_lt_ws@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::strip_lt_ws(void)
0x180007540  mov     rcx, [rsp+48h+bstrString]; bstrString
0x180007545  call    cs:__imp_SysFreeString
0x18000754c  nop     dword ptr [rax+rax+00h]
0x180007551  mov     eax, ebx
0x180007553  mov     rbx, [rsp+48h+arg_0]
0x180007558  add     rsp, 40h
0x18000755c  pop     rdi
0x18000755d  retn
```
