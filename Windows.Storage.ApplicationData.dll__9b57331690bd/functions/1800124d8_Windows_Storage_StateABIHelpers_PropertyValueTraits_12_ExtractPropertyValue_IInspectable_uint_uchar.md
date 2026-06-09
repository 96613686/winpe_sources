# Windows::Storage::StateABIHelpers::PropertyValueTraits<12>::ExtractPropertyValue(IInspectable *,uint *,uchar * *)

- ea: `0x1800124d8`
- end: `0x180012760`
- name: `?ExtractPropertyValue@?$PropertyValueTraits@$0M@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAE@Z`
- size: `648`
- prototype: `HRESULT __fastcall(IInspectable *_property, unsigned int *valueBytes, unsigned __int8 **value)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000af34`

## callees

- `0x180009778`
- `0x1800124d8`
- `0x180012768`
- `0x180012790`
- `0x1800127c0`
- `0x180021fc4`
- `0x180024fc4`
- `0x1800415e2`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800125d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800125d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001260c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001260c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180012583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180012583`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::PropertyValueTraits<12>::ExtractPropertyValue(
        IInspectable *_property,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  IInspectable *v5; // rbx
  IInspectable_vtbl *v6; // rax
  HRESULT v7; // eax
  HRESULT v8; // edi
  HRESULT v9; // esi
  UINT32 StringLen; // eax
  HRESULT v11; // eax
  int v12; // r11d
  unsigned int v13; // edx
  unsigned int v14; // eax
  unsigned __int8 *v15; // rax
  PCWSTR StringRawBuffer; // rax
  RoVariant property; // [rsp+40h] [rbp-20h] BYREF
  RoVariant::Accessor v19; // [rsp+50h] [rbp-10h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]
  Windows::Internal::String stringValue; // [rsp+90h] [rbp+30h] BYREF
  IInspectable *v22; // [rsp+A8h] [rbp+48h] BYREF

  stringValue._hstring = 0;
  v5 = _property;
  if ( _property )
  {
    v6 = _property->__vftable;
    v22 = 0;
    v7 = v6->QueryInterface(_property, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, (void **)&v22);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( v7 != -2147467262 )
      {
        v5 = 0;
        property._hrState = v7;
        goto LABEL_5;
      }
      v8 = 1;
    }
    else
    {
      v5 = v22;
      v8 = 7;
    }
  }
  else
  {
    v5 = 0;
    v8 = 0;
  }
  property._hrState = v8;
LABEL_5:
  property._pI = v5;
  v19._pI = v5;
  v19._hrState = v8;
  stringValue._hstring = 0;
  v9 = RoVariant::Accessor::VerifyPV(&v19);
  if ( v9 < 0
    || (v9 = ((__int64 (__fastcall *)(IInspectable *, Windows::Internal::String *))v5->__vftable[3].AddRef)(
               v5,
               &stringValue),
        v9 < 0) )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x16Du,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABISettingPropertyToApiSetValue.hpp",
      v9,
      "GetString");
LABEL_17:
    if ( v5 && ((v8 - 3) & 0xFFFFFFFB) == 0 )
      v5->Release(v5);
    goto LABEL_18;
  }
  StringLen = WindowsGetStringLen(stringValue._hstring);
  v11 = ULongLongToUInt(2LL * StringLen, valueBytes);
  v13 = *valueBytes;
  v9 = v11;
  if ( v11 >= 0 )
  {
    v14 = v13 + 2;
    if ( v13 + 2 < v13 )
    {
      v9 = -2147024362;
      *valueBytes = -1;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x172u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABISettingPropertyToApiSetValue.hpp",
        -2147024362,
        "UIntAdd %u",
        -1);
    }
    else
    {
      *valueBytes = v14;
      v15 = (unsigned __int8 *)operator new(v14);
      *value = v15;
      if ( v15 )
      {
        if ( *valueBytes < 2 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        StringRawBuffer = WindowsGetStringRawBuffer(stringValue._hstring, 0);
        memcpy_0(*value, StringRawBuffer, *valueBytes - 2LL);
        *(_WORD *)&(*value)[*valueBytes - 2] = 0;
        if ( v5 && ((v8 - 3) & 0xFFFFFFFB) == 0 )
          v5->Release(v5);
        if ( stringValue._hstring )
          WindowsDeleteString(stringValue._hstring);
        return 0;
      }
      v9 = -2147024882;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x175u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABISettingPropertyToApiSetValue.hpp",
        -2147024882,
        "new %u",
        *valueBytes);
    }
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    0x171u,
    "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABISettingPropertyToApiSetValue.hpp",
    v11,
    "UIntMult %u butes %u",
    v12,
    v13);
  RoVariant::~RoVariant(&property);
LABEL_18:
  if ( stringValue._hstring )
    WindowsDeleteString(stringValue._hstring);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800124d8  mov     [rsp-28h+arg_8], rbx
0x1800124dd  push    rbp
0x1800124de  push    rsi
0x1800124df  push    rdi
0x1800124e0  push    r14
0x1800124e2  push    r15
0x1800124e4  mov     rbp, rsp
0x1800124e7  sub     rsp, 60h
0x1800124eb  mov     [rbp+stringValue._hstring], 0
0x1800124f3  mov     r15, value
0x1800124f6  mov     r14, valueBytes
0x1800124f9  mov     rbx, _property
0x1800124fc  test    _property, _property
0x1800124ff  jz      loc_180012712
0x180012505  mov     rax, [_property]
0x180012508  lea     value, [rbp+arg_18]
0x18001250c  lea     valueBytes, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180012513  mov     [rbp+arg_18], 0
0x18001251b  mov     rax, [rax]
0x18001251e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012523  mov     edi, eax
0x180012525  test    eax, eax
0x180012527  js      loc_180012673
0x18001252d  mov     rbx, [rbp+arg_18]
0x180012531  mov     edi, 7
0x180012536  mov     [rbp+property._hrState], edi
0x180012539  lea     _property, [rbp+var_10]; this
0x18001253d  mov     [rbp+property._pI], rbx
0x180012541  mov     [rbp+var_10._pI], rbx
0x180012545  mov     [rbp+var_10._hrState], edi
0x180012548  mov     [rbp+stringValue._hstring], 0
0x180012550  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x180012555  mov     esi, eax
0x180012557  test    eax, eax
0x180012559  js      loc_1800126C5
0x18001255f  mov     rax, [rbx]
0x180012562  lea     valueBytes, [rbp+stringValue]
0x180012566  mov     _property, rbx
0x180012569  mov     rax, [rax+98h]
0x180012570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012575  mov     esi, eax
0x180012577  test    eax, eax
0x180012579  js      loc_1800126C5
0x18001257f  mov     _property, [rbp+stringValue._hstring]; string
0x180012583  call    cs:__imp_WindowsGetStringLen
0x180012589  mov     ecx, eax
0x18001258b  mov     valueBytes, r14; puResult
0x18001258e  add     _property, _property; ullOperand
0x180012591  mov     r11d, eax
0x180012594  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180012599  mov     edx, [r14]
0x18001259c  mov     esi, eax
0x18001259e  test    eax, eax
0x1800125a0  js      loc_18001271B
0x1800125a6  lea     eax, [valueBytes+2]
0x1800125a9  cmp     eax, edx
0x1800125ab  jb      short loc_180012628
0x1800125ad  mov     ecx, eax; cb
0x1800125af  mov     [r14], eax
0x1800125b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800125b7  mov     [r15], rax
0x1800125ba  mov     edx, [r14]
0x1800125bd  test    rax, rax
0x1800125c0  jz      loc_1800126EE
0x1800125c6  cmp     edx, 2
0x1800125c9  jb      loc_180012756
0x1800125cf  mov     _property, [rbp+stringValue._hstring]; string
0x1800125d3  xor     edx, edx; length
0x1800125d5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800125db  mov     r8d, [r14]
0x1800125de  mov     valueBytes, rax; Src
0x1800125e1  mov     _property, [r15]; void *
0x1800125e4  sub     value, 2; Size
0x1800125e8  call    memcpy_0
0x1800125ed  mov     edx, [r14]
0x1800125f0  xor     eax, eax
0x1800125f2  mov     _property, [r15]
0x1800125f5  mov     [valueBytes+_property-2], ax
0x1800125fa  test    rbx, rbx
0x1800125fd  jnz     loc_180012688
0x180012603  mov     _property, [rbp+stringValue._hstring]; string
0x180012607  test    _property, _property
0x18001260a  jz      short loc_180012612
0x18001260c  call    cs:__imp_WindowsDeleteString
0x180012612  xor     eax, eax
0x180012614  mov     rbx, [rsp+60h+arg_8]
0x18001261c  add     rsp, 60h
0x180012620  pop     r15
0x180012622  pop     r14
0x180012624  pop     rdi
0x180012625  pop     rsi
0x180012626  pop     rbp
0x180012627  retn
0x180012628  or      eax, 0FFFFFFFFh
0x18001262b  mov     esi, 80070216h
0x180012630  mov     [r14], eax
0x180012633  mov     edx, 172h; lineNumber
0x180012638  mov     [rsp+60h+var_38], eax
0x18001263c  lea     rax, aUintaddU; "UIntAdd %u"
0x180012643  mov     _property, [rbp+28h]; callerReturnAddress
0x180012647  lea     value, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001264e  mov     r9d, esi; hr
0x180012651  mov     [rsp+60h+formatString], rax; formatString
0x180012656  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001265b  test    rbx, rbx
0x18001265e  jnz     short loc_1800126AA
0x180012660  mov     _property, [rbp+stringValue._hstring]; string
0x180012664  test    _property, _property
0x180012667  jz      short loc_18001266F
0x180012669  call    cs:__imp_WindowsDeleteString
0x18001266f  mov     eax, esi
0x180012671  jmp     short loc_180012614
0x180012673  cmp     eax, 80004002h
0x180012678  jnz     loc_180012708
0x18001267e  mov     edi, 1
0x180012683  jmp     loc_180012536
0x180012688  lea     eax, [rdi-3]
0x18001268b  test    eax, 0FFFFFFFBh
0x180012690  jnz     loc_180012603
0x180012696  mov     rax, [rbx]
0x180012699  mov     _property, rbx
0x18001269c  mov     rax, [rax+10h]
0x1800126a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126a5  jmp     loc_180012603
0x1800126aa  lea     eax, [rdi-3]
0x1800126ad  test    eax, 0FFFFFFFBh
0x1800126b2  jnz     short loc_180012660
0x1800126b4  mov     rax, [rbx]
0x1800126b7  mov     _property, rbx
0x1800126ba  mov     rax, [rax+10h]
0x1800126be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126c3  jmp     short loc_180012660
0x1800126c5  mov     _property, [rbp+28h]; callerReturnAddress
0x1800126c9  lea     rax, aGetstring; "GetString"
0x1800126d0  mov     r9d, esi; hr
0x1800126d3  mov     [rsp+60h+formatString], rax; formatString
0x1800126d8  lea     value, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800126df  mov     edx, 16Dh; lineNumber
0x1800126e4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800126e9  jmp     loc_18001265B
0x1800126ee  mov     [rsp+60h+var_38], edx
0x1800126f2  lea     rax, aNewU; "new %u"
0x1800126f9  mov     edx, 175h
0x1800126fe  mov     esi, 8007000Eh
0x180012703  jmp     loc_180012643
0x180012708  xor     ebx, ebx
0x18001270a  mov     [rbp+property._hrState], eax
0x18001270d  jmp     loc_180012539
0x180012712  xor     ebx, ebx
0x180012714  xor     edi, edi
0x180012716  jmp     loc_180012536
0x18001271b  mov     _property, [rbp+28h]; callerReturnAddress
0x18001271f  lea     rax, aUintmultUButes; "UIntMult %u butes %u"
0x180012726  mov     [rsp+60h+var_30], edx
0x18001272a  lea     value, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x180012731  mov     [rsp+60h+var_38], r11d
0x180012736  mov     edx, 171h; lineNumber
0x18001273b  mov     r9d, esi; hr
0x18001273e  mov     [rsp+60h+formatString], rax; formatString
0x180012743  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180012748  lea     _property, [rbp+property]; this
0x18001274c  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180012751  jmp     loc_180012660
0x180012756  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "*valueBytes >= sizeof(WCHAR)", "Unexpected size")
0x18001275b  jmp     loc_1800125CF
```
