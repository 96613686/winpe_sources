# PolicyModel::CFileHash::Deserialize(Sharp::Util::Xml::CNode const &)

- ea: `0x140010d90`
- end: `0x14001100e`
- name: `?Deserialize@CFileHash@PolicyModel@@MEAAXAEBVCNode@Xml@Util@Sharp@@@Z`
- size: `638`
- prototype: `void __fastcall(PolicyModel::CFileHash *__hidden this, const struct Sharp::Util::Xml::CNode *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config`

## callees

- `0x140001d1c`
- `0x1400070e4`
- `0x140008368`
- `0x1400091c0`
- `0x1400099b4`
- `0x140009bd4`
- `0x14000a0d4`
- `0x14001065c`
- `0x140010d90`
- `0x14001108c`
- `0x14001146c`
- `0x140012e1c`
- `0x140013044`
- `0x1400130ec`
- `0x140013b10`

## pseudocode

```c
void __fastcall PolicyModel::CFileHash::Deserialize(
        PolicyModel::CFileHash *this,
        const struct Sharp::Util::Xml::CNode *a2)
{
  unsigned int v4; // ebx
  char HasAttribute; // bl
  __int64 v6; // rax
  char v7; // bl
  __int128 v8; // [rsp+20h] [rbp-89h] BYREF
  __int64 v9; // [rsp+30h] [rbp-79h]
  _QWORD v10[4]; // [rsp+38h] [rbp-71h] BYREF
  _QWORD v11[4]; // [rsp+58h] [rbp-51h] BYREF
  _QWORD v12[5]; // [rsp+78h] [rbp-31h] BYREF
  _QWORD pExceptionObject[8]; // [rsp+A0h] [rbp-9h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_ea87dc071bbe3ba5fabd577fed3242f7_Traceguids);
  std::wstring::wstring((__int64)v10);
  Sharp::Util::Xml::CNode::ParseStringAttribute(a2, v11, v10);
  std::wstring::_Tidy(v10, 1, 0);
  if ( (unsigned __int8)std::operator==<unsigned short>(v11, L"SHA256") )
  {
    v4 = 0;
  }
  else if ( (unsigned __int8)std::operator==<unsigned short>(v11, L"SHA256Flat") )
  {
    v4 = 1;
  }
  else
  {
    if ( !(unsigned __int8)std::operator==<unsigned short>(v11, L"SHA1") )
    {
      invalid_policy_element_exception::invalid_policy_element_exception((invalid_policy_element_exception *)pExceptionObject);
      throw (invalid_policy_element_exception *)pExceptionObject;
    }
    v4 = 2;
  }
  std::wstring::wstring((__int64)v10);
  Sharp::Util::Xml::CNode::ParseStringAttribute(a2, v12, v10);
  std::wstring::_Tidy(v10, 1, 0);
  v8 = 0;
  v9 = 0;
  PolicyModel::CFileHash::HexadecimalStringToData(v12, &v8);
  PolicyModel::CFileHash::SetHash((char *)this - 8, v4, &v8);
  std::wstring::wstring((__int64)v10);
  HasAttribute = Sharp::Util::Xml::CNode::HasAttribute(a2, v10);
  std::wstring::_Tidy(v10, 1, 0);
  if ( HasAttribute )
  {
    std::wstring::wstring((__int64)v10);
    v6 = Sharp::Util::Xml::CNode::ParseStringAttribute(a2, pExceptionObject, v10);
    std::wstring::operator=((__int64)this + 40, v6);
    std::wstring::_Tidy(pExceptionObject, 1, 0);
    std::wstring::_Tidy(v10, 1, 0);
  }
  std::wstring::wstring((__int64)v10);
  v7 = Sharp::Util::Xml::CNode::HasAttribute(a2, v10);
  std::wstring::_Tidy(v10, 1, 0);
  if ( v7 )
  {
    std::wstring::wstring((__int64)v10);
    *((_DWORD *)this + 18) = Sharp::Util::Xml::CNode::ParseNumberAttribute(a2, v10);
    std::wstring::_Tidy(v10, 1, 0);
  }
  std::vector<unsigned char>::_Tidy((std::_Container_base0 *)&v8);
  std::wstring::_Tidy(v12, 1, 0);
  std::wstring::_Tidy(v11, 1, 0);
}

```

## disassembly

```asm
0x140010d90  mov     [rsp-8+arg_10], rbx
0x140010d95  mov     [rsp-8+arg_18], rsi
0x140010d9a  push    rbp
0x140010d9b  push    rdi
0x140010d9c  push    r14
0x140010d9e  lea     rbp, [rsp-47h]
0x140010da3  sub     rsp, 0F0h
0x140010daa  mov     rax, cs:__security_cookie
0x140010db1  xor     rax, rsp
0x140010db4  mov     [rbp+57h+var_20], rax
0x140010db8  mov     rdi, rdx
0x140010dbb  mov     rsi, rcx
0x140010dbe  lea     rax, WPP_GLOBAL_Control
0x140010dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140010dcc  cmp     rcx, rax
0x140010dcf  jz      short loc_140010DEC
0x140010dd1  test    byte ptr [rcx+1Ch], 8
0x140010dd5  jz      short loc_140010DEC
0x140010dd7  mov     edx, 14h
0x140010ddc  lea     r8, WPP_ea87dc071bbe3ba5fabd577fed3242f7_Traceguids
0x140010de3  mov     rcx, [rcx+10h]
0x140010de7  call    WPP_SF_
0x140010dec  lea     rdx, aType; "Type"
0x140010df3  lea     rcx, [rbp+57h+var_C8]
0x140010df7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140010dfc  nop
0x140010dfd  lea     r8, [rbp+57h+var_C8]
0x140010e01  lea     rdx, [rbp+57h+var_A8]
0x140010e05  mov     rcx, rdi
0x140010e08  call    ?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Sharp::Util::Xml::CNode::ParseStringAttribute(std::wstring const &)
0x140010e0d  nop
0x140010e0e  xor     r8d, r8d
0x140010e11  mov     dl, 1
0x140010e13  lea     rcx, [rbp+57h+var_C8]
0x140010e17  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140010e1c  lea     rdx, aSha256; "SHA256"
0x140010e23  lea     rcx, [rbp+57h+var_A8]
0x140010e27  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x140010e2c  test    al, al
0x140010e2e  jz      short loc_140010E34
0x140010e30  xor     ebx, ebx
0x140010e32  jmp     short loc_140010E6C
0x140010e34  lea     rdx, aSha256flat; "SHA256Flat"
0x140010e3b  lea     rcx, [rbp+57h+var_A8]
0x140010e3f  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x140010e44  test    al, al
0x140010e46  jz      short loc_140010E4F
0x140010e48  mov     ebx, 1
0x140010e4d  jmp     short loc_140010E6C
0x140010e4f  lea     rdx, aSha1; "SHA1"
0x140010e56  lea     rcx, [rbp+57h+var_A8]
0x140010e5a  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x140010e5f  test    al, al
0x140010e61  jz      loc_140010FF4
0x140010e67  mov     ebx, 2
0x140010e6c  lea     rdx, aData; "Data"
0x140010e73  lea     rcx, [rbp+57h+var_C8]
0x140010e77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140010e7c  nop
0x140010e7d  lea     r8, [rbp+57h+var_C8]
0x140010e81  lea     rdx, [rbp+57h+var_88]
0x140010e85  mov     rcx, rdi
0x140010e88  call    ?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Sharp::Util::Xml::CNode::ParseStringAttribute(std::wstring const &)
0x140010e8d  nop
0x140010e8e  xor     r8d, r8d
0x140010e91  mov     dl, 1
0x140010e93  lea     rcx, [rbp+57h+var_C8]
0x140010e97  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140010e9c  xorps   xmm0, xmm0
0x140010e9f  movdqu  [rsp+100h+var_E0], xmm0
0x140010ea5  mov     [rbp+57h+var_D0], 0
0x140010ead  lea     rdx, [rsp+100h+var_E0]
0x140010eb2  lea     rcx, [rbp+57h+var_88]
0x140010eb6  call    ?HexadecimalStringToData@CFileHash@PolicyModel@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@4@@Z; PolicyModel::CFileHash::HexadecimalStringToData(std::wstring const &,std::vector<uchar> &)
0x140010ebb  lea     r8, [rsp+100h+var_E0]
0x140010ec0  mov     edx, ebx
0x140010ec2  lea     rcx, [rsi-8]
0x140010ec6  call    ?SetHash@CFileHash@PolicyModel@@QEAAXW4HashType@12@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; PolicyModel::CFileHash::SetHash(PolicyModel::CFileHash::HashType,std::vector<uchar> const &)
0x140010ecb  lea     rdx, aSourcefilename; "SourceFileName"
0x140010ed2  lea     rcx, [rbp+57h+var_C8]
0x140010ed6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140010edb  nop
0x140010edc  lea     rdx, [rbp+57h+var_C8]
0x140010ee0  mov     rcx, rdi
0x140010ee3  call    ?HasAttribute@CNode@Xml@Util@Sharp@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::HasAttribute(std::wstring const &)
0x140010ee8  mov     bl, al
0x140010eea  xor     r8d, r8d
0x140010eed  mov     dl, 1
0x140010eef  lea     rcx, [rbp+57h+var_C8]
0x140010ef3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140010ef8  test    bl, bl
0x140010efa  jz      short loc_140010F48
0x140010efc  lea     rdx, aSourcefilename; "SourceFileName"
0x140010f03  lea     rcx, [rbp+57h+var_C8]
0x140010f07  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140010f0c  nop
0x140010f0d  lea     r8, [rbp+57h+var_C8]
0x140010f11  lea     rdx, [rbp+57h+pExceptionObject]
0x140010f15  mov     rcx, rdi
0x140010f18  call    ?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Sharp::Util::Xml::CNode::ParseStringAttribute(std::wstring const &)
0x140010f1d  nop
0x140010f1e  lea     rcx, [rsi+28h]
0x140010f22  mov     rdx, rax
0x140010f25  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140010f2a  nop
0x140010f2b  xor     r8d, r8d
0x140010f2e  mov     dl, 1
0x140010f30  lea     rcx, [rbp+57h+pExceptionObject]
0x140010f34  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140010f39  nop
0x140010f3a  xor     r8d, r8d
0x140010f3d  mov     dl, 1
0x140010f3f  lea     rcx, [rbp+57h+var_C8]
0x140010f43  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140010f48  lea     rdx, aSourcefileleng; "SourceFileLength"
0x140010f4f  lea     rcx, [rbp+57h+var_C8]
0x140010f53  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140010f58  nop
0x140010f59  lea     rdx, [rbp+57h+var_C8]
0x140010f5d  mov     rcx, rdi
0x140010f60  call    ?HasAttribute@CNode@Xml@Util@Sharp@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::HasAttribute(std::wstring const &)
0x140010f65  mov     bl, al
0x140010f67  xor     r8d, r8d
0x140010f6a  mov     dl, 1
0x140010f6c  lea     rcx, [rbp+57h+var_C8]
0x140010f70  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140010f75  test    bl, bl
0x140010f77  jz      short loc_140010FA8
0x140010f79  lea     rdx, aSourcefileleng; "SourceFileLength"
0x140010f80  lea     rcx, [rbp+57h+var_C8]
0x140010f84  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140010f89  nop
0x140010f8a  lea     rdx, [rbp+57h+var_C8]
0x140010f8e  mov     rcx, rdi
0x140010f91  call    ?ParseNumberAttribute@CNode@Xml@Util@Sharp@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::ParseNumberAttribute(std::wstring const &)
0x140010f96  mov     [rsi+48h], eax
0x140010f99  xor     r8d, r8d
0x140010f9c  mov     dl, 1
0x140010f9e  lea     rcx, [rbp+57h+var_C8]
0x140010fa2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140010fa7  nop
0x140010fa8  lea     rcx, [rsp+100h+var_E0]
0x140010fad  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140010fb2  nop
0x140010fb3  xor     r8d, r8d
0x140010fb6  mov     dl, 1
0x140010fb8  lea     rcx, [rbp+57h+var_88]
0x140010fbc  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140010fc1  nop
0x140010fc2  xor     r8d, r8d
0x140010fc5  mov     dl, 1
0x140010fc7  lea     rcx, [rbp+57h+var_A8]
0x140010fcb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140010fd0  mov     rcx, [rbp+57h+var_20]
0x140010fd4  xor     rcx, rsp; StackCookie
0x140010fd7  call    __security_check_cookie
0x140010fdc  lea     r11, [rsp+100h+var_10]
0x140010fe4  mov     rbx, [r11+30h]
0x140010fe8  mov     rsi, [r11+38h]
0x140010fec  mov     rsp, r11
0x140010fef  pop     r14
0x140010ff1  pop     rdi
0x140010ff2  pop     rbp
0x140010ff3  retn
0x140010ff4  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140010ff8  call    ??0invalid_policy_element_exception@@QEAA@XZ; invalid_policy_element_exception::invalid_policy_element_exception(void)
0x140010ffd  lea     rdx, _TI4?AVinvalid_policy_element_exception@@; pThrowInfo
0x140011004  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140011008  call    _CxxThrowException_0
```
