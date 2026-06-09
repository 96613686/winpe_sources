# Windows::COM::CEnumIDENTITY_ATTRIBUTE::Create(Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE const> const *,unsigned __int64,_GUID const &,IUnknown * *)

- ea: `0x18007acec`
- end: `0x18007ae80`
- name: `?Create@CEnumIDENTITY_ATTRIBUTE@COM@Windows@@KAJPEBU?$Vector@$$CBU_ATTRIBUTE@Rtl@Identity@Windows@@@3@_KAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `404`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180079ee0`
- `0x18007abc0`

## callees

- `0x1800211f0`
- `0x18002175c`
- `0x180021794`
- `0x180026dc0`
- `0x18002d2b0`
- `0x180078dc0`
- `0x18007aa4c`
- `0x18007acec`
- `0x18007b094`
- `0x18009e020`

## string_xrefs

- `0x18007ad36`: `onecore\base\wcp\identity\com\enum_idattribute.cpp`
- `0x18007ad76`: `onecore\base\wcp\identity\com\enum_idattribute.cpp`
- `0x18007add8`: `onecore\base\wcp\identity\com\enum_idattribute.cpp`
- `0x18007ad4d`: `Windows::COM::CEnumIDENTITY_ATTRIBUTE::Create`
- `0x18007ad8d`: `Windows::COM::CEnumIDENTITY_ATTRIBUTE::Create`
- `0x18007adef`: `Windows::COM::CEnumIDENTITY_ATTRIBUTE::Create`

## pseudocode

```c
__int64 __fastcall Windows::COM::CEnumIDENTITY_ATTRIBUTE::Create(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  void *v8; // rax
  __int64 v9; // rbx
  int v10; // eax
  unsigned int v11; // ebx
  const char *v12; // [rsp+20h] [rbp-40h] BYREF
  const char *v13; // [rsp+28h] [rbp-38h]
  __int64 v14; // [rsp+30h] [rbp-30h]
  const char *v15; // [rsp+38h] [rbp-28h]
  __int64 v16; // [rsp+40h] [rbp-20h] BYREF
  int v17; // [rsp+48h] [rbp-18h] BYREF

  v17 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a1 && *(_QWORD *)(a1 + 8) < a2 )
  {
    v14 = 23;
    v12 = "onecore\\base\\wcp\\identity\\com\\enum_idattribute.cpp";
    v13 = "Windows::COM::CEnumIDENTITY_ATTRIBUTE::Create";
    v15 = "(IdentityAttributeList == 0) || (IdentityAttributeList->Length >= CurrentPosition)";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(
             &v17,
             &v12,
             a3);
  }
  if ( !a4 )
  {
    v14 = 24;
    v12 = "onecore\\base\\wcp\\identity\\com\\enum_idattribute.cpp";
    v13 = "Windows::COM::CEnumIDENTITY_ATTRIBUTE::Create";
    v15 = "Not-null check failed: ppIUnknown";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v17,
             &v12);
  }
  v8 = operator new(0x30u);
  if ( v8 )
    v9 = Windows::COM::CComObject<Windows::COM::CEnumIDENTITY_ATTRIBUTE>::CComObject<Windows::COM::CEnumIDENTITY_ATTRIBUTE>(v8);
  else
    v9 = 0;
  v16 = v9;
  if ( v9 )
  {
    v10 = Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize(v9, a1, a2);
    if ( v10 >= 0 )
    {
      v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))(v9 + 16))(
              v9 + 16,
              &GUID_9cdaae75_246e_4b00_a26d_b9aec137a3eb,
              a4);
      if ( v10 >= 0 )
      {
        v16 = 0;
        v11 = 0;
        goto LABEL_17;
      }
    }
  }
  else
  {
    v14 = 27;
    v12 = "onecore\\base\\wcp\\identity\\com\\enum_idattribute.cpp";
    v13 = "Windows::COM::CEnumIDENTITY_ATTRIBUTE::Create";
    v15 = "EnumIDENTITY_ATTRIBUTE.Allocate()";
    v10 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
            &v17,
            &v12,
            2147942414LL);
  }
  v11 = v10;
LABEL_17:
  Windows::Auto<Windows::COM::CComObject<Windows::COM::CEnumIDENTITY_ATTRIBUTE> *>::~Auto<Windows::COM::CComObject<Windows::COM::CEnumIDENTITY_ATTRIBUTE> *>(&v16);
  return v11;
}

```

## disassembly

```asm
0x18007acec  mov     [rsp-18h+arg_8], rbx
0x18007acf1  mov     [rsp-18h+arg_10], rsi
0x18007acf6  push    rbp
0x18007acf7  push    rdi
0x18007acf8  push    r14
0x18007acfa  mov     rbp, rsp
0x18007acfd  sub     rsp, 60h
0x18007ad01  mov     rax, cs:__security_cookie
0x18007ad08  xor     rax, rsp
0x18007ad0b  mov     [rbp+var_10], rax
0x18007ad0f  mov     [rbp+var_18], 0
0x18007ad16  mov     rdi, r9
0x18007ad19  mov     r14, rdx
0x18007ad1c  mov     rsi, rcx
0x18007ad1f  test    r9, r9
0x18007ad22  jz      short loc_18007AD2B
0x18007ad24  mov     qword ptr [r9], 0
0x18007ad2b  test    rsi, rsi
0x18007ad2e  jz      short loc_18007AD71
0x18007ad30  cmp     [rcx+8], r14
0x18007ad34  jnb     short loc_18007AD71
0x18007ad36  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\identity\\com\\enum"...
0x18007ad3d  mov     [rbp+var_30], 17h
0x18007ad45  mov     [rbp+var_40], rax
0x18007ad49  lea     rdx, [rbp+var_40]
0x18007ad4d  lea     rax, aWindowsComCenu_5; "Windows::COM::CEnumIDENTITY_ATTRIBUTE::"...
0x18007ad54  mov     [rbp+var_38], rax
0x18007ad58  lea     rcx, [rbp+var_18]
0x18007ad5c  lea     rax, aIdentityattrib_1; "(IdentityAttributeList == 0) || (Identi"...
0x18007ad63  mov     [rbp+var_28], rax
0x18007ad67  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007ad6c  jmp     loc_18007AE5E
0x18007ad71  test    rdi, rdi
0x18007ad74  jnz     short loc_18007ADB1
0x18007ad76  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\identity\\com\\enum"...
0x18007ad7d  mov     [rbp+var_30], 18h
0x18007ad85  mov     [rbp+var_40], rax
0x18007ad89  lea     rdx, [rbp+var_40]
0x18007ad8d  lea     rax, aWindowsComCenu_5; "Windows::COM::CEnumIDENTITY_ATTRIBUTE::"...
0x18007ad94  mov     [rbp+var_38], rax
0x18007ad98  lea     rcx, [rbp+var_18]
0x18007ad9c  lea     rax, aNotNullCheckFa_132; "Not-null check failed: ppIUnknown"
0x18007ada3  mov     [rbp+var_28], rax
0x18007ada7  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007adac  jmp     loc_18007AE5E
0x18007adb1  mov     ecx, 30h ; '0'; Size
0x18007adb6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007adbb  test    rax, rax
0x18007adbe  jz      short loc_18007ADCD
0x18007adc0  mov     rcx, rax
0x18007adc3  call    ??0?$CComObject@VCEnumIDENTITY_ATTRIBUTE@COM@Windows@@@COM@Windows@@QEAA@XZ; Windows::COM::CComObject<Windows::COM::CEnumIDENTITY_ATTRIBUTE>::CComObject<Windows::COM::CEnumIDENTITY_ATTRIBUTE>(void)
0x18007adc8  mov     rbx, rax
0x18007adcb  jmp     short loc_18007ADCF
0x18007adcd  xor     ebx, ebx
0x18007adcf  mov     [rbp+var_20], rbx
0x18007add3  test    rbx, rbx
0x18007add6  jnz     short loc_18007AE16
0x18007add8  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\identity\\com\\enum"...
0x18007addf  mov     [rbp+var_30], 1Bh
0x18007ade7  mov     [rbp+var_40], rax
0x18007adeb  lea     rdx, [rbp+var_40]
0x18007adef  lea     rax, aWindowsComCenu_5; "Windows::COM::CEnumIDENTITY_ATTRIBUTE::"...
0x18007adf6  mov     r8d, 8007000Eh
0x18007adfc  mov     [rbp+var_38], rax
0x18007ae00  lea     rcx, [rbp+var_18]
0x18007ae04  lea     rax, aEnumidentityAt; "EnumIDENTITY_ATTRIBUTE.Allocate()"
0x18007ae0b  mov     [rbp+var_28], rax
0x18007ae0f  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007ae14  jmp     short loc_18007AE28
0x18007ae16  mov     r8, r14
0x18007ae19  mov     rdx, rsi
0x18007ae1c  mov     rcx, rbx
0x18007ae1f  call    ?Initialize@CEnumIDENTITY_ATTRIBUTE@COM@Windows@@IEAAJPEBU?$Vector@$$CBU_ATTRIBUTE@Rtl@Identity@Windows@@@3@_K@Z; Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize(Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE const> const *,unsigned __int64)
0x18007ae24  test    eax, eax
0x18007ae26  jns     short loc_18007AE2C
0x18007ae28  mov     ebx, eax
0x18007ae2a  jmp     short loc_18007AE53
0x18007ae2c  lea     rcx, [rbx+10h]
0x18007ae30  mov     r8, rdi
0x18007ae33  mov     rax, [rcx]
0x18007ae36  lea     rdx, _GUID_9cdaae75_246e_4b00_a26d_b9aec137a3eb
0x18007ae3d  mov     rax, [rax]
0x18007ae40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ae45  test    eax, eax
0x18007ae47  js      short loc_18007AE28
0x18007ae49  mov     [rbp+var_20], 0
0x18007ae51  xor     ebx, ebx
0x18007ae53  lea     rcx, [rbp+var_20]
0x18007ae57  call    ??1?$Auto@PEAV?$CComObject@VCEnumIDENTITY_ATTRIBUTE@COM@Windows@@@COM@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::COM::CComObject<Windows::COM::CEnumIDENTITY_ATTRIBUTE> *>::~Auto<Windows::COM::CComObject<Windows::COM::CEnumIDENTITY_ATTRIBUTE> *>(void)
0x18007ae5c  mov     eax, ebx
0x18007ae5e  mov     rcx, [rbp+var_10]
0x18007ae62  xor     rcx, rsp; StackCookie
0x18007ae65  call    __security_check_cookie
0x18007ae6a  lea     r11, [rsp+60h+var_s0]
0x18007ae6f  mov     rbx, [r11+28h]
0x18007ae73  mov     rsi, [r11+30h]
0x18007ae77  mov     rsp, r11
0x18007ae7a  pop     r14
0x18007ae7c  pop     rdi
0x18007ae7d  pop     rbp
0x18007ae7e  retn
```
