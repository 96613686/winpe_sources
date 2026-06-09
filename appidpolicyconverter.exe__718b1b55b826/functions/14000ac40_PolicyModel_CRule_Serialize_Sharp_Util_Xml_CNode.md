# PolicyModel::CRule::Serialize(Sharp::Util::Xml::CNode &)

- ea: `0x14000ac40`
- end: `0x14000af4f`
- name: `?Serialize@CRule@PolicyModel@@MEBAXAEAVCNode@Xml@Util@Sharp@@@Z`
- size: `783`
- prototype: `void __fastcall(const OLECHAR *this, struct Sharp::Util::Xml::CNode *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callees

- `0x1400080b0`
- `0x140008368`
- `0x1400099b4`
- `0x14000ac40`
- `0x140012138`
- `0x140012604`
- `0x1400126cc`
- `0x140012764`
- `0x140013b10`
- `0x140016010`

## string_xrefs

- `0x14000acfe`: `UserOrGroupSid`

## pseudocode

```c
void __fastcall PolicyModel::CRule::Serialize(const OLECHAR *this, struct Sharp::Util::Xml::CNode *a2)
{
  _QWORD *v4; // rbx
  unsigned __int16 *v5; // rax
  _QWORD *v6; // rbx
  unsigned __int16 *v7; // rax
  __int64 v8; // [rsp+20h] [rbp-89h]
  __int64 v9; // [rsp+20h] [rbp-89h]
  OLECHAR v10[8]; // [rsp+28h] [rbp-81h] BYREF
  OLECHAR v11[8]; // [rsp+38h] [rbp-71h] BYREF
  OLECHAR v12[16]; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v13[4]; // [rsp+68h] [rbp-41h] BYREF
  unsigned __int16 v14[16]; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int16 v15[16]; // [rsp+A8h] [rbp-1h] BYREF
  OLECHAR v16[16]; // [rsp+C8h] [rbp+1Fh] BYREF

  std::wstring::wstring((__int64)v12);
  Sharp::Util::Xml::CNode::CreateAttribute((__int64)a2, v12, (__int64)(this + 8));
  std::wstring::_Tidy(v12, 1, 0);
  std::wstring::wstring((__int64)v12);
  Sharp::Util::Xml::CNode::CreateAttribute((__int64)a2, v12, this + 16);
  std::wstring::_Tidy(v12, 1, 0);
  std::wstring::wstring((__int64)v12);
  Sharp::Util::Xml::CNode::CreateAttribute((__int64)a2, v12, this + 32);
  std::wstring::_Tidy(v12, 1, 0);
  std::wstring::wstring((__int64)v12);
  Sharp::Util::Xml::CNode::CreateAttribute((__int64)a2, v12, this + 48);
  std::wstring::_Tidy(v12, 1, 0);
  std::wstring::wstring((__int64)v16);
  std::wstring::wstring((__int64)v12);
  Sharp::Util::Xml::CNode::CreateAttribute((__int64)a2, v12, v16);
  std::wstring::_Tidy(v12, 1, 0);
  if ( *((_QWORD *)this + 18) )
  {
    std::wstring::wstring((__int64)v14);
    Sharp::Util::Xml::CNode::CreateChild(a2, v10, v14);
    std::wstring::_Tidy(v14, 1, 0);
    v4 = (_QWORD *)*((_QWORD *)this + 17);
    while ( 1 )
    {
      v4 = (_QWORD *)*v4;
      if ( v4 == *((_QWORD **)this + 17) )
        break;
      v8 = v4[2];
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
      v5 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)(*(_QWORD *)(v8 + 16) + 8LL)
                                                                            + 24LL))(
                                 *(_QWORD *)(v8 + 16) + 8LL,
                                 v13);
      Sharp::Util::Xml::CNode::CreateChild((Sharp::Util::Xml::CNode *)v10, v12, v5);
      std::wstring::_Tidy(v13, 1, 0);
      (*(void (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)(*(_QWORD *)(v8 + 16) + 8LL) + 8LL))(
        *(_QWORD *)(v8 + 16) + 8LL,
        v12);
      Sharp::Util::Xml::CNode::~CNode((Sharp::Util::Xml::CNode *)v12);
      Sharp::Util::CRefCount::ReleaseReference((Sharp::Util::CRefCount *)v8);
    }
    Sharp::Util::Xml::CNode::~CNode((Sharp::Util::Xml::CNode *)v10);
  }
  if ( *((_QWORD *)this + 20) )
  {
    std::wstring::wstring((__int64)v15);
    Sharp::Util::Xml::CNode::CreateChild(a2, v11, v15);
    std::wstring::_Tidy(v15, 1, 0);
    v6 = (_QWORD *)*((_QWORD *)this + 19);
    while ( 1 )
    {
      v6 = (_QWORD *)*v6;
      if ( v6 == *((_QWORD **)this + 19) )
        break;
      v9 = v6[2];
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
      v7 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)(*(_QWORD *)(v9 + 16) + 8LL)
                                                                            + 24LL))(
                                 *(_QWORD *)(v9 + 16) + 8LL,
                                 v13);
      Sharp::Util::Xml::CNode::CreateChild((Sharp::Util::Xml::CNode *)v11, v12, v7);
      std::wstring::_Tidy(v13, 1, 0);
      (*(void (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)(*(_QWORD *)(v9 + 16) + 8LL) + 8LL))(
        *(_QWORD *)(v9 + 16) + 8LL,
        v12);
      Sharp::Util::Xml::CNode::~CNode((Sharp::Util::Xml::CNode *)v12);
      Sharp::Util::CRefCount::ReleaseReference((Sharp::Util::CRefCount *)v9);
    }
    Sharp::Util::Xml::CNode::~CNode((Sharp::Util::Xml::CNode *)v11);
  }
  std::wstring::_Tidy(v16, 1, 0);
}

```

## disassembly

```asm
0x14000ac40  mov     [rsp-8+arg_10], rbx
0x14000ac45  mov     [rsp-8+arg_18], rsi
0x14000ac4a  push    rbp
0x14000ac4b  push    rdi
0x14000ac4c  push    r14
0x14000ac4e  lea     rbp, [rsp-47h]
0x14000ac53  sub     rsp, 0F0h
0x14000ac5a  mov     rax, cs:__security_cookie
0x14000ac61  xor     rax, rsp
0x14000ac64  mov     [rbp+57h+var_18], rax
0x14000ac68  mov     r14, rdx
0x14000ac6b  mov     rsi, rcx
0x14000ac6e  lea     rdx, aId; "Id"
0x14000ac75  lea     rcx, [rbp+57h+var_B8]
0x14000ac79  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000ac7e  nop
0x14000ac7f  lea     r8, [rsi+10h]
0x14000ac83  lea     rdx, [rbp+57h+var_B8]
0x14000ac87  mov     rcx, r14
0x14000ac8a  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,_GUID const &)
0x14000ac8f  nop
0x14000ac90  xor     r8d, r8d
0x14000ac93  mov     dl, 1
0x14000ac95  lea     rcx, [rbp+57h+var_B8]
0x14000ac99  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000ac9e  lea     rdx, aName; "Name"
0x14000aca5  lea     rcx, [rbp+57h+var_B8]
0x14000aca9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000acae  nop
0x14000acaf  lea     r8, [rsi+20h]
0x14000acb3  lea     rdx, [rbp+57h+var_B8]
0x14000acb7  mov     rcx, r14
0x14000acba  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,std::wstring const &)
0x14000acbf  nop
0x14000acc0  xor     r8d, r8d
0x14000acc3  mov     dl, 1
0x14000acc5  lea     rcx, [rbp+57h+var_B8]
0x14000acc9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000acce  lea     rdx, aDescription; "Description"
0x14000acd5  lea     rcx, [rbp+57h+var_B8]
0x14000acd9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000acde  nop
0x14000acdf  lea     r8, [rsi+40h]
0x14000ace3  lea     rdx, [rbp+57h+var_B8]
0x14000ace7  mov     rcx, r14
0x14000acea  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,std::wstring const &)
0x14000acef  nop
0x14000acf0  xor     r8d, r8d
0x14000acf3  mov     dl, 1
0x14000acf5  lea     rcx, [rbp+57h+var_B8]
0x14000acf9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000acfe  lea     rdx, aUserorgroupsid; "UserOrGroupSid"
0x14000ad05  lea     rcx, [rbp+57h+var_B8]
0x14000ad09  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000ad0e  nop
0x14000ad0f  lea     r8, [rsi+60h]
0x14000ad13  lea     rdx, [rbp+57h+var_B8]
0x14000ad17  mov     rcx, r14
0x14000ad1a  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,std::wstring const &)
0x14000ad1f  nop
0x14000ad20  xor     r8d, r8d
0x14000ad23  mov     dl, 1
0x14000ad25  lea     rcx, [rbp+57h+var_B8]
0x14000ad29  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000ad2e  lea     rax, aDeny; "Deny"
0x14000ad35  lea     rdx, aAllow; "Allow"
0x14000ad3c  cmp     dword ptr [rsi+80h], 0
0x14000ad43  cmovnz  rdx, rax
0x14000ad47  lea     rcx, [rbp+57h+var_38]
0x14000ad4b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000ad50  nop
0x14000ad51  lea     rdx, aAction; "Action"
0x14000ad58  lea     rcx, [rbp+57h+var_B8]
0x14000ad5c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000ad61  nop
0x14000ad62  lea     r8, [rbp+57h+var_38]
0x14000ad66  lea     rdx, [rbp+57h+var_B8]
0x14000ad6a  mov     rcx, r14
0x14000ad6d  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,std::wstring const &)
0x14000ad72  nop
0x14000ad73  xor     r8d, r8d
0x14000ad76  mov     dl, 1
0x14000ad78  lea     rcx, [rbp+57h+var_B8]
0x14000ad7c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000ad81  cmp     qword ptr [rsi+90h], 0
0x14000ad89  jz      loc_14000AE50
0x14000ad8f  lea     rdx, aConditions; "Conditions"
0x14000ad96  lea     rcx, [rbp+57h+var_78]
0x14000ad9a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000ad9f  nop
0x14000ada0  lea     r8, [rbp+57h+var_78]; unsigned __int16 *
0x14000ada4  lea     rdx, [rsp+100h+var_D8]; struct Sharp::Util::Xml::CNode *
0x14000ada9  mov     rcx, r14; this
0x14000adac  call    ?CreateChild@CNode@Xml@Util@Sharp@@QEAA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::CreateChild(std::wstring const &)
0x14000adb1  nop
0x14000adb2  xor     r8d, r8d
0x14000adb5  mov     dl, 1
0x14000adb7  lea     rcx, [rbp+57h+var_78]
0x14000adbb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000adc0  mov     rbx, [rsi+88h]
0x14000adc7  mov     rbx, [rbx]
0x14000adca  cmp     rbx, [rsi+88h]
0x14000add1  jz      short loc_14000AE46
0x14000add3  mov     rdi, [rbx+10h]
0x14000add7  mov     [rsp+100h+var_E0], rdi
0x14000addc  lock inc dword ptr [rdi+8]
0x14000ade0  mov     rcx, [rdi+10h]
0x14000ade4  add     rcx, 8
0x14000ade8  mov     rax, [rcx]
0x14000adeb  lea     rdx, [rbp+57h+var_98]
0x14000adef  mov     rax, [rax+18h]
0x14000adf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000adf8  nop
0x14000adf9  mov     r8, rax; unsigned __int16 *
0x14000adfc  lea     rdx, [rbp+57h+var_B8]; struct Sharp::Util::Xml::CNode *
0x14000ae00  lea     rcx, [rsp+100h+var_D8]; this
0x14000ae05  call    ?CreateChild@CNode@Xml@Util@Sharp@@QEAA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::CreateChild(std::wstring const &)
0x14000ae0a  nop
0x14000ae0b  xor     r8d, r8d
0x14000ae0e  mov     dl, 1
0x14000ae10  lea     rcx, [rbp+57h+var_98]
0x14000ae14  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000ae19  mov     rcx, [rdi+10h]
0x14000ae1d  add     rcx, 8
0x14000ae21  mov     rax, [rcx]
0x14000ae24  lea     rdx, [rbp+57h+var_B8]
0x14000ae28  mov     rax, [rax+8]
0x14000ae2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae31  nop
0x14000ae32  lea     rcx, [rbp+57h+var_B8]; this
0x14000ae36  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x14000ae3b  nop
0x14000ae3c  mov     rcx, rdi; this
0x14000ae3f  call    ?ReleaseReference@CRefCount@Util@Sharp@@QEAAJXZ; Sharp::Util::CRefCount::ReleaseReference(void)
0x14000ae44  jmp     short loc_14000ADC7
0x14000ae46  lea     rcx, [rsp+100h+var_D8]; this
0x14000ae4b  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x14000ae50  cmp     qword ptr [rsi+0A0h], 0
0x14000ae58  jz      loc_14000AF1D
0x14000ae5e  lea     rdx, aExceptions; "Exceptions"
0x14000ae65  lea     rcx, [rbp+57h+var_58]
0x14000ae69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000ae6e  nop
0x14000ae6f  lea     r8, [rbp+57h+var_58]; unsigned __int16 *
0x14000ae73  lea     rdx, [rbp+57h+var_C8]; struct Sharp::Util::Xml::CNode *
0x14000ae77  mov     rcx, r14; this
0x14000ae7a  call    ?CreateChild@CNode@Xml@Util@Sharp@@QEAA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::CreateChild(std::wstring const &)
0x14000ae7f  nop
0x14000ae80  xor     r8d, r8d
0x14000ae83  mov     dl, 1
0x14000ae85  lea     rcx, [rbp+57h+var_58]
0x14000ae89  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000ae8e  mov     rbx, [rsi+98h]
0x14000ae95  mov     rbx, [rbx]
0x14000ae98  cmp     rbx, [rsi+98h]
0x14000ae9f  jz      short loc_14000AF13
0x14000aea1  mov     rdi, [rbx+10h]
0x14000aea5  mov     [rsp+100h+var_E0], rdi
0x14000aeaa  lock inc dword ptr [rdi+8]
0x14000aeae  mov     rcx, [rdi+10h]
0x14000aeb2  add     rcx, 8
0x14000aeb6  mov     rax, [rcx]
0x14000aeb9  lea     rdx, [rbp+57h+var_98]
0x14000aebd  mov     rax, [rax+18h]
0x14000aec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aec6  nop
0x14000aec7  mov     r8, rax; unsigned __int16 *
0x14000aeca  lea     rdx, [rbp+57h+var_B8]; struct Sharp::Util::Xml::CNode *
0x14000aece  lea     rcx, [rbp+57h+var_C8]; this
0x14000aed2  call    ?CreateChild@CNode@Xml@Util@Sharp@@QEAA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::CreateChild(std::wstring const &)
0x14000aed7  nop
0x14000aed8  xor     r8d, r8d
0x14000aedb  mov     dl, 1
0x14000aedd  lea     rcx, [rbp+57h+var_98]
0x14000aee1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000aee6  mov     rcx, [rdi+10h]
0x14000aeea  add     rcx, 8
0x14000aeee  mov     rax, [rcx]
0x14000aef1  lea     rdx, [rbp+57h+var_B8]
0x14000aef5  mov     rax, [rax+8]
0x14000aef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aefe  nop
0x14000aeff  lea     rcx, [rbp+57h+var_B8]; this
0x14000af03  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x14000af08  nop
0x14000af09  mov     rcx, rdi; this
0x14000af0c  call    ?ReleaseReference@CRefCount@Util@Sharp@@QEAAJXZ; Sharp::Util::CRefCount::ReleaseReference(void)
0x14000af11  jmp     short loc_14000AE95
0x14000af13  lea     rcx, [rbp+57h+var_C8]; this
0x14000af17  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x14000af1c  nop
0x14000af1d  xor     r8d, r8d
0x14000af20  mov     dl, 1
0x14000af22  lea     rcx, [rbp+57h+var_38]
0x14000af26  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000af2b  mov     rcx, [rbp+57h+var_18]
0x14000af2f  xor     rcx, rsp; StackCookie
0x14000af32  call    __security_check_cookie
0x14000af37  lea     r11, [rsp+100h+var_10]
0x14000af3f  mov     rbx, [r11+30h]
0x14000af43  mov     rsi, [r11+38h]
0x14000af47  mov     rsp, r11
0x14000af4a  pop     r14
0x14000af4c  pop     rdi
0x14000af4d  pop     rbp
0x14000af4e  retn
```
