# Windows::COM::CEnumIDENTITY_ATTRIBUTE::Create(Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE const> const *,unsigned __int64,_GUID const &,IUnknown * *)

- ea: `0x18007b04c`
- end: `0x18007b20c`
- name: `?Create@CEnumIDENTITY_ATTRIBUTE@COM@Windows@@KAJPEBU?$Vector@$$CBU_ATTRIBUTE@Rtl@Identity@Windows@@@3@_KAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007a210`
- `0x18007af20`

## callees

- `0x18001f4e4`
- `0x18001f51c`
- `0x18001f604`
- `0x180022eb0`
- `0x1800293a0`
- `0x180079130`
- `0x18007b04c`
- `0x18007b424`
- `0x1800a0020`

## string_xrefs

- `0x18007b096`: `onecore\base\wcp\identity\com\enum_idattribute.cpp`
- `0x18007b0d6`: `onecore\base\wcp\identity\com\enum_idattribute.cpp`
- `0x18007b164`: `onecore\base\wcp\identity\com\enum_idattribute.cpp`
- `0x18007b0ad`: `Windows::COM::CEnumIDENTITY_ATTRIBUTE::Create`
- `0x18007b0ed`: `Windows::COM::CEnumIDENTITY_ATTRIBUTE::Create`
- `0x18007b17b`: `Windows::COM::CEnumIDENTITY_ATTRIBUTE::Create`

## pseudocode

```c
__int64 __fastcall Windows::COM::CEnumIDENTITY_ATTRIBUTE::Create(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  int v10; // eax
  unsigned int v11; // ebx
  const char *v12; // [rsp+20h] [rbp-40h] BYREF
  const char *v13; // [rsp+28h] [rbp-38h]
  __int64 v14; // [rsp+30h] [rbp-30h]
  const char *v15; // [rsp+38h] [rbp-28h]
  _DWORD *v16; // [rsp+40h] [rbp-20h] BYREF
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
  v9 = v8;
  if ( v8 )
  {
    v8[2] = 0;
    *((_QWORD *)v8 + 3) = 0;
    *((_QWORD *)v8 + 4) = 0;
    *((_QWORD *)v8 + 5) = -1;
    *(_QWORD *)v8 = &Windows::COM::CComObject<Windows::COM::CEnumIDENTITY_ATTRIBUTE>::`vftable'{for `Windows::COM::CComObjectBase'};
    *((_QWORD *)v8 + 2) = &Windows::COM::CComObject<Windows::COM::CEnumIDENTITY_ATTRIBUTE>::`vftable'{for `IEnumIDENTITY_ATTRIBUTE'};
  }
  else
  {
    v9 = 0;
  }
  v16 = v9;
  if ( v9 )
  {
    v10 = Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize(v9, a1, a2);
    if ( v10 >= 0 )
    {
      v10 = (**((__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v9 + 2))(
              (__int64)(v9 + 4),
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
0x18007b04c  mov     [rsp-18h+arg_8], rbx
0x18007b051  mov     [rsp-18h+arg_10], rsi
0x18007b056  push    rbp
0x18007b057  push    rdi
0x18007b058  push    r14
0x18007b05a  mov     rbp, rsp
0x18007b05d  sub     rsp, 60h
0x18007b061  mov     rax, cs:__security_cookie
0x18007b068  xor     rax, rsp
0x18007b06b  mov     [rbp+var_10], rax
0x18007b06f  mov     [rbp+var_18], 0
0x18007b076  mov     rdi, r9
0x18007b079  mov     r14, rdx
0x18007b07c  mov     rsi, rcx
0x18007b07f  test    r9, r9
0x18007b082  jz      short loc_18007B08B
0x18007b084  mov     qword ptr [r9], 0
0x18007b08b  test    rsi, rsi
0x18007b08e  jz      short loc_18007B0D1
0x18007b090  cmp     [rcx+8], r14
0x18007b094  jnb     short loc_18007B0D1
0x18007b096  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\identity\\com\\enum"...
0x18007b09d  mov     [rbp+var_30], 17h
0x18007b0a5  mov     [rbp+var_40], rax
0x18007b0a9  lea     rdx, [rbp+var_40]
0x18007b0ad  lea     rax, aWindowsComCenu_5; "Windows::COM::CEnumIDENTITY_ATTRIBUTE::"...
0x18007b0b4  mov     [rbp+var_38], rax
0x18007b0b8  lea     rcx, [rbp+var_18]
0x18007b0bc  lea     rax, aIdentityattrib_1; "(IdentityAttributeList == 0) || (Identi"...
0x18007b0c3  mov     [rbp+var_28], rax
0x18007b0c7  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007b0cc  jmp     loc_18007B1EA
0x18007b0d1  test    rdi, rdi
0x18007b0d4  jnz     short loc_18007B111
0x18007b0d6  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\identity\\com\\enum"...
0x18007b0dd  mov     [rbp+var_30], 18h
0x18007b0e5  mov     [rbp+var_40], rax
0x18007b0e9  lea     rdx, [rbp+var_40]
0x18007b0ed  lea     rax, aWindowsComCenu_5; "Windows::COM::CEnumIDENTITY_ATTRIBUTE::"...
0x18007b0f4  mov     [rbp+var_38], rax
0x18007b0f8  lea     rcx, [rbp+var_18]
0x18007b0fc  lea     rax, aNotNullCheckFa_132; "Not-null check failed: ppIUnknown"
0x18007b103  mov     [rbp+var_28], rax
0x18007b107  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007b10c  jmp     loc_18007B1EA
0x18007b111  mov     ecx, 30h ; '0'; Size
0x18007b116  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007b11b  mov     rbx, rax
0x18007b11e  test    rax, rax
0x18007b121  jz      short loc_18007B159
0x18007b123  mov     dword ptr [rax+8], 0
0x18007b12a  mov     qword ptr [rax+18h], 0
0x18007b132  mov     qword ptr [rax+20h], 0
0x18007b13a  mov     qword ptr [rax+28h], 0FFFFFFFFFFFFFFFFh
0x18007b142  lea     rax, ??_7?$CComObject@VCEnumIDENTITY_ATTRIBUTE@COM@Windows@@@COM@Windows@@6BCComObjectBase@12@@; const Windows::COM::CComObject<Windows::COM::CEnumIDENTITY_ATTRIBUTE>::`vftable'{for `Windows::COM::CComObjectBase'}
0x18007b149  mov     [rbx], rax
0x18007b14c  lea     rax, ??_7?$CComObject@VCEnumIDENTITY_ATTRIBUTE@COM@Windows@@@COM@Windows@@6BIEnumIDENTITY_ATTRIBUTE@@@; const Windows::COM::CComObject<Windows::COM::CEnumIDENTITY_ATTRIBUTE>::`vftable'{for `IEnumIDENTITY_ATTRIBUTE'}
0x18007b153  mov     [rbx+10h], rax
0x18007b157  jmp     short loc_18007B15B
0x18007b159  xor     ebx, ebx
0x18007b15b  mov     [rbp+var_20], rbx
0x18007b15f  test    rbx, rbx
0x18007b162  jnz     short loc_18007B1A2
0x18007b164  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\identity\\com\\enum"...
0x18007b16b  mov     [rbp+var_30], 1Bh
0x18007b173  mov     [rbp+var_40], rax
0x18007b177  lea     rdx, [rbp+var_40]
0x18007b17b  lea     rax, aWindowsComCenu_5; "Windows::COM::CEnumIDENTITY_ATTRIBUTE::"...
0x18007b182  mov     r8d, 8007000Eh
0x18007b188  mov     [rbp+var_38], rax
0x18007b18c  lea     rcx, [rbp+var_18]
0x18007b190  lea     rax, aEnumidentityAt; "EnumIDENTITY_ATTRIBUTE.Allocate()"
0x18007b197  mov     [rbp+var_28], rax
0x18007b19b  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007b1a0  jmp     short loc_18007B1B4
0x18007b1a2  mov     r8, r14
0x18007b1a5  mov     rdx, rsi
0x18007b1a8  mov     rcx, rbx
0x18007b1ab  call    ?Initialize@CEnumIDENTITY_ATTRIBUTE@COM@Windows@@IEAAJPEBU?$Vector@$$CBU_ATTRIBUTE@Rtl@Identity@Windows@@@3@_K@Z; Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize(Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE const> const *,unsigned __int64)
0x18007b1b0  test    eax, eax
0x18007b1b2  jns     short loc_18007B1B8
0x18007b1b4  mov     ebx, eax
0x18007b1b6  jmp     short loc_18007B1DF
0x18007b1b8  lea     rcx, [rbx+10h]
0x18007b1bc  mov     r8, rdi
0x18007b1bf  mov     rax, [rcx]
0x18007b1c2  lea     rdx, _GUID_9cdaae75_246e_4b00_a26d_b9aec137a3eb
0x18007b1c9  mov     rax, [rax]
0x18007b1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b1d1  test    eax, eax
0x18007b1d3  js      short loc_18007B1B4
0x18007b1d5  mov     [rbp+var_20], 0
0x18007b1dd  xor     ebx, ebx
0x18007b1df  lea     rcx, [rbp+var_20]
0x18007b1e3  call    ??1?$Auto@PEAV?$CComObject@VCEnumIDENTITY_ATTRIBUTE@COM@Windows@@@COM@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::COM::CComObject<Windows::COM::CEnumIDENTITY_ATTRIBUTE> *>::~Auto<Windows::COM::CComObject<Windows::COM::CEnumIDENTITY_ATTRIBUTE> *>(void)
0x18007b1e8  mov     eax, ebx
0x18007b1ea  mov     rcx, [rbp+var_10]
0x18007b1ee  xor     rcx, rsp; StackCookie
0x18007b1f1  call    __security_check_cookie
0x18007b1f6  lea     r11, [rsp+60h+var_s0]
0x18007b1fb  mov     rbx, [r11+28h]
0x18007b1ff  mov     rsi, [r11+30h]
0x18007b203  mov     rsp, r11
0x18007b206  pop     r14
0x18007b208  pop     rdi
0x18007b209  pop     rbp
0x18007b20a  retn
```
