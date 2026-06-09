# PolicyModel::CFileHash::Serialize(Sharp::Util::Xml::CNode &)

- ea: `0x140011240`
- end: `0x140011466`
- name: `?Serialize@CFileHash@PolicyModel@@MEBAXAEAVCNode@Xml@Util@Sharp@@@Z`
- size: `550`
- prototype: `void __fastcall(PolicyModel::CFileHash *__hidden this, struct Sharp::Util::Xml::CNode *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x140001d1c`
- `0x1400070e4`
- `0x140008368`
- `0x140008498`
- `0x1400099b4`
- `0x140009bd4`
- `0x140010c78`
- `0x140011240`
- `0x140012278`
- `0x140012604`
- `0x140013b10`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1400113f9`
- `OLEAUT32!__imp_VariantClear` at `0x1400113f9`

## pseudocode

```c
void __fastcall PolicyModel::CFileHash::Serialize(PolicyModel::CFileHash *this, struct Sharp::Util::Xml::CNode *a2)
{
  int v4; // eax
  const wchar_t *v5; // rdx
  LONG v6; // ebx
  VARIANTARG pvarg; // [rsp+20h] [rbp-69h] BYREF
  _QWORD v8[4]; // [rsp+40h] [rbp-49h] BYREF
  OLECHAR v9[16]; // [rsp+60h] [rbp-29h] BYREF
  unsigned __int16 pExceptionObject[32]; // [rsp+80h] [rbp-9h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ea87dc071bbe3ba5fabd577fed3242f7_Traceguids);
  v8[3] = 7;
  v8[2] = 0;
  LOWORD(v8[0]) = 0;
  v4 = *((_DWORD *)this + 2);
  if ( v4 )
  {
    if ( v4 == 1 )
    {
      v5 = L"SHA256Flat";
    }
    else
    {
      if ( v4 != 2 )
      {
        invalid_policy_element_exception::invalid_policy_element_exception((invalid_policy_element_exception *)pExceptionObject);
        throw (invalid_policy_element_exception *)pExceptionObject;
      }
      v5 = L"SHA1";
    }
  }
  else
  {
    v5 = L"SHA256";
  }
  std::wstring::assign((__int64)v8, (__int64)v5);
  std::wstring::wstring((__int64)&pvarg);
  Sharp::Util::Xml::CNode::CreateAttribute((__int64)a2, &pvarg.vt, (const OLECHAR *)v8);
  std::wstring::_Tidy(&pvarg, 1, 0);
  PolicyModel::CFileHash::DataToHexadecimalString(v9, (char *)this + 16);
  std::wstring::wstring((__int64)&pvarg);
  Sharp::Util::Xml::CNode::CreateAttribute((__int64)a2, &pvarg.vt, v9);
  std::wstring::_Tidy(&pvarg, 1, 0);
  if ( *((_QWORD *)this + 7) )
  {
    std::wstring::wstring((__int64)&pvarg);
    Sharp::Util::Xml::CNode::CreateAttribute((__int64)a2, &pvarg.vt, (const OLECHAR *)this + 20);
    std::wstring::_Tidy(&pvarg, 1, 0);
    v6 = *((_DWORD *)this + 18);
    std::wstring::wstring((__int64)pExceptionObject);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
    pvarg.vt = 3;
    pvarg.lVal = v6;
    Sharp::Util::Xml::CNode::CreateAttribute((__int64)a2, pExceptionObject, &pvarg);
    VariantClear(&pvarg);
    std::wstring::_Tidy(pExceptionObject, 1, 0);
  }
  std::wstring::_Tidy(v9, 1, 0);
  std::wstring::_Tidy(v8, 1, 0);
}

```

## disassembly

```asm
0x140011240  mov     [rsp-8+arg_10], rbx
0x140011245  push    rbp
0x140011246  push    rdi
0x140011247  push    r14
0x140011249  lea     rbp, [rsp-47h]
0x14001124e  sub     rsp, 0D0h
0x140011255  mov     rax, cs:__security_cookie
0x14001125c  xor     rax, rsp
0x14001125f  mov     [rbp+57h+var_20], rax
0x140011263  mov     rdi, rdx
0x140011266  mov     rbx, rcx
0x140011269  lea     r14, WPP_GLOBAL_Control
0x140011270  mov     rcx, cs:WPP_GLOBAL_Control
0x140011277  cmp     rcx, r14
0x14001127a  jz      short loc_140011297
0x14001127c  test    byte ptr [rcx+1Ch], 8
0x140011280  jz      short loc_140011297
0x140011282  mov     edx, 13h
0x140011287  lea     r8, WPP_ea87dc071bbe3ba5fabd577fed3242f7_Traceguids
0x14001128e  mov     rcx, [rcx+10h]
0x140011292  call    WPP_SF_
0x140011297  mov     [rbp+57h+var_90], 0
0x14001129f  mov     [rbp+57h+var_88], 0
0x1400112a7  mov     [rbp+57h+var_88], 7
0x1400112af  mov     [rbp+57h+var_90], 0
0x1400112b7  xor     eax, eax
0x1400112b9  mov     [rbp+57h+var_A0], ax
0x1400112bd  mov     eax, [rbx+8]
0x1400112c0  test    eax, eax
0x1400112c2  jnz     short loc_1400112CD
0x1400112c4  lea     rdx, aSha256; "SHA256"
0x1400112cb  jmp     short loc_1400112EB
0x1400112cd  cmp     eax, 1
0x1400112d0  jnz     short loc_1400112DB
0x1400112d2  lea     rdx, aSha256flat; "SHA256Flat"
0x1400112d9  jmp     short loc_1400112EB
0x1400112db  cmp     eax, 2
0x1400112de  jnz     loc_14001144C
0x1400112e4  lea     rdx, aSha1; "SHA1"
0x1400112eb  lea     rcx, [rbp+57h+var_A0]
0x1400112ef  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1400112f4  lea     rdx, aType; "Type"
0x1400112fb  lea     rcx, [rbp+57h+pvarg]
0x1400112ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140011304  nop
0x140011305  lea     r8, [rbp+57h+var_A0]
0x140011309  lea     rdx, [rbp+57h+pvarg]
0x14001130d  mov     rcx, rdi
0x140011310  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,std::wstring const &)
0x140011315  nop
0x140011316  xor     r8d, r8d
0x140011319  mov     dl, 1
0x14001131b  lea     rcx, [rbp+57h+pvarg]
0x14001131f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140011324  lea     rdx, [rbx+10h]
0x140011328  lea     rcx, [rbp+57h+var_80]
0x14001132c  call    ?DataToHexadecimalString@CFileHash@PolicyModel@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@4@@Z; PolicyModel::CFileHash::DataToHexadecimalString(std::vector<uchar> const &)
0x140011331  nop
0x140011332  lea     rdx, aData; "Data"
0x140011339  lea     rcx, [rbp+57h+pvarg]
0x14001133d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140011342  nop
0x140011343  lea     r8, [rbp+57h+var_80]
0x140011347  lea     rdx, [rbp+57h+pvarg]
0x14001134b  mov     rcx, rdi
0x14001134e  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,std::wstring const &)
0x140011353  nop
0x140011354  xor     r8d, r8d
0x140011357  mov     dl, 1
0x140011359  lea     rcx, [rbp+57h+pvarg]
0x14001135d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140011362  cmp     qword ptr [rbx+38h], 0
0x140011367  jz      loc_14001140F
0x14001136d  lea     rdx, aSourcefilename; "SourceFileName"
0x140011374  lea     rcx, [rbp+57h+pvarg]
0x140011378  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14001137d  nop
0x14001137e  lea     r8, [rbx+28h]
0x140011382  lea     rdx, [rbp+57h+pvarg]
0x140011386  mov     rcx, rdi
0x140011389  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,std::wstring const &)
0x14001138e  nop
0x14001138f  xor     r8d, r8d
0x140011392  mov     dl, 1
0x140011394  lea     rcx, [rbp+57h+pvarg]
0x140011398  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14001139d  mov     ebx, [rbx+48h]
0x1400113a0  lea     rdx, aSourcefileleng; "SourceFileLength"
0x1400113a7  lea     rcx, [rbp+57h+pExceptionObject]
0x1400113ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1400113b0  nop
0x1400113b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400113b8  cmp     rcx, r14
0x1400113bb  jz      short loc_1400113D8
0x1400113bd  test    byte ptr [rcx+1Ch], 8
0x1400113c1  jz      short loc_1400113D8
0x1400113c3  mov     edx, 34h ; '4'
0x1400113c8  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x1400113cf  mov     rcx, [rcx+10h]
0x1400113d3  call    WPP_SF_
0x1400113d8  mov     eax, 3
0x1400113dd  mov     word ptr [rbp+57h+pvarg], ax
0x1400113e1  mov     dword ptr [rbp+57h+pvarg+8], ebx
0x1400113e4  lea     r8, [rbp+57h+pvarg]
0x1400113e8  lea     rdx, [rbp+57h+pExceptionObject]
0x1400113ec  mov     rcx, rdi
0x1400113ef  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVCComVariant@ATL@@@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,ATL::CComVariant const &)
0x1400113f4  nop
0x1400113f5  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1400113f9  call    cs:__imp_VariantClear
0x1400113ff  nop
0x140011400  xor     r8d, r8d
0x140011403  mov     dl, 1
0x140011405  lea     rcx, [rbp+57h+pExceptionObject]
0x140011409  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14001140e  nop
0x14001140f  xor     r8d, r8d
0x140011412  mov     dl, 1
0x140011414  lea     rcx, [rbp+57h+var_80]
0x140011418  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14001141d  nop
0x14001141e  xor     r8d, r8d
0x140011421  mov     dl, 1
0x140011423  lea     rcx, [rbp+57h+var_A0]
0x140011427  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14001142c  mov     rcx, [rbp+57h+var_20]
0x140011430  xor     rcx, rsp; StackCookie
0x140011433  call    __security_check_cookie
0x140011438  mov     rbx, [rsp+0E0h+arg_10]
0x140011440  add     rsp, 0D0h
0x140011447  pop     r14
0x140011449  pop     rdi
0x14001144a  pop     rbp
0x14001144b  retn
0x14001144c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140011450  call    ??0invalid_policy_element_exception@@QEAA@XZ; invalid_policy_element_exception::invalid_policy_element_exception(void)
0x140011455  lea     rdx, _TI4?AVinvalid_policy_element_exception@@; pThrowInfo
0x14001145c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140011460  call    _CxxThrowException_0
```
