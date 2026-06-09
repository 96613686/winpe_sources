# mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,unsigned __int64 &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18002e864`
- end: `0x18002e8f5`
- name: `?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEA_KPEAV42@@Z`
- size: `145`
- prototype: `__int64 __fastcall(int, int, int, int, BSTR bstrString)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180007b90`
- `0x18002ccd8`
- `0x18002ceec`

## callees

- `0x180007850`
- `0x180008490`
- `0x1800084f0`
- `0x18002e864`
- `0x18002ecc8`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002e8db`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e8db`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall mlib::XmlDOM::GetNodeValue(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, BSTR bstrString)
{
  int NodeValue; // ebx
  OLECHAR *v7; // rcx
  int v9; // [rsp+20h] [rbp-38h]
  __int64 v10; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v11[8]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v12; // [rsp+40h] [rbp-18h]

  v12 = -2;
  bstrString = 0;
  NodeValue = mlib::XmlDOM::GetNodeValue(a1, a2, 0, (__int64)&bstrString, v9);
  v7 = bstrString;
  if ( NodeValue >= 0 && bstrString )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v11,
      bstrString);
    v10 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::to_UINT64(
      v11,
      &v10);
    *a4 = v10;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v11);
    v7 = bstrString;
  }
  SysFreeString(v7);
  return (unsigned int)NodeValue;
}

```

## disassembly

```asm
0x18002e864  mov     rax, rsp
0x18002e867  push    rdi
0x18002e868  sub     rsp, 50h
0x18002e86c  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18002e874  mov     [rax+8], rbx
0x18002e878  mov     rdi, r9
0x18002e87b  and     qword ptr [rax+28h], 0
0x18002e880  lea     r9, [rax+28h]
0x18002e884  xor     r8d, r8d
0x18002e887  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAPEAGPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ushort * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18002e88c  mov     ebx, eax
0x18002e88e  mov     rcx, [rsp+58h+bstrString]
0x18002e896  test    eax, eax
0x18002e898  js      short loc_18002E8DB
0x18002e89a  test    rcx, rcx
0x18002e89d  jz      short loc_18002E8DB
0x18002e89f  mov     rdx, rcx
0x18002e8a2  lea     rcx, [rsp+58h+var_20]
0x18002e8a7  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x18002e8ac  and     [rsp+58h+var_28], 0
0x18002e8b2  lea     rdx, [rsp+58h+var_28]
0x18002e8b7  lea     rcx, [rsp+58h+var_20]
0x18002e8bc  call    ?to_UINT64@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NAEA_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::to_UINT64(unsigned __int64 &,bool)
0x18002e8c1  mov     rax, [rsp+58h+var_28]
0x18002e8c6  mov     [rdi], rax
0x18002e8c9  lea     rcx, [rsp+58h+var_20]
0x18002e8ce  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18002e8d3  mov     rcx, [rsp+58h+bstrString]; bstrString
0x18002e8db  call    cs:__imp_SysFreeString
0x18002e8e2  nop     dword ptr [rax+rax+00h]
0x18002e8e7  mov     eax, ebx
0x18002e8e9  mov     rbx, [rsp+58h+arg_0]
0x18002e8ee  add     rsp, 50h
0x18002e8f2  pop     rdi
0x18002e8f3  retn
```
