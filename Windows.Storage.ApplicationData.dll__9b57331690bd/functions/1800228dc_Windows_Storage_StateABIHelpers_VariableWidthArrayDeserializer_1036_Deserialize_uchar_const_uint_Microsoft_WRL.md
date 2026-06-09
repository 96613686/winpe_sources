# Windows::Storage::StateABIHelpers::VariableWidthArrayDeserializer<1036>::Deserialize(uchar const *,uint,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)

- ea: `0x1800228dc`
- end: `0x180022b28`
- name: `?Deserialize@?$VariableWidthArrayDeserializer@$0EAM@@StateABIHelpers@Storage@Windows@@SAJPEBEIAEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z`
- size: `588`
- prototype: `HRESULT __fastcall(const unsigned __int8 *valueBuffer, const unsigned int valueBufferBytes, Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> *propertyValueStaticInterface, IInspectable **propertyValue)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180009ea8`

## callees

- `0x180009778`
- `0x18000aa74`
- `0x1800228dc`
- `0x180024fc4`
- `0x180025004`
- `0x18003d448`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800229cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800229cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022a36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022aa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022ac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022a36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022aa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022ac5`

## string_xrefs

- `0x180022a6a`: `CreatePropertyValue %u recordCount %u`
- `0x1800229f5`: `WindowsCreateString %u Data %ws i %u recordCount %u`

## pseudocode

```c
HRESULT __fastcall Windows::Storage::StateABIHelpers::VariableWidthArrayDeserializer<1036>::Deserialize(
        const unsigned __int8 *valueBuffer,
        unsigned int valueBufferBytes,
        Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> *propertyValueStaticInterface,
        IInspectable **propertyValue)
{
  const unsigned __int8 *v6; // rsi
  int v7; // ebx
  const unsigned __int8 *v9; // rcx
  const unsigned __int8 *v10; // rdx
  unsigned int v11; // ebx
  HSTRING *v12; // rdi
  unsigned int i; // r15d
  __int64 v14; // rdx
  int String; // ebp
  unsigned int j; // esi
  unsigned int k; // esi
  unsigned int m; // esi
  unsigned int v19; // [rsp+28h] [rbp-60h]
  void *retaddr; // [rsp+88h] [rbp+0h]

  v6 = valueBuffer;
  if ( !propertyValue )
  {
    v7 = -2147467261;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x68u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIApiSetValueToSettingProperty.hpp",
      -2147467261,
      "Size %u",
      valueBufferBytes);
    return v7;
  }
  v9 = &valueBuffer[valueBufferBytes];
  if ( v6 >= v9 )
    goto LABEL_26;
  v10 = v6;
  v11 = 0;
  do
  {
    ++v11;
    v10 += *(unsigned int *)v10 + 4;
  }
  while ( v10 < v9 );
  if ( v11 )
  {
    v12 = (HSTRING *)operator new(saturated_mul(v11, 8u));
    if ( !v12 )
    {
      v19 = v11;
      v7 = -2147024882;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x7Au,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIApiSetValueToSettingProperty.hpp",
        -2147024882,
        "new %u",
        v19);
      return v7;
    }
    for ( i = 0; i < v11; ++i )
    {
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)&v6[2 * v14 + 4] );
      String = WindowsCreateString((PCNZWCH)v6 + 2, v14, &v12[i]);
      if ( String < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x8Cu,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIApiSetValueToSettingProperty.hpp",
          String,
          "WindowsCreateString %u Data %ws i %u recordCount %u",
          valueBufferBytes,
          v6 + 4,
          i,
          v11);
        for ( j = 0; j < v11; ++j )
          WindowsDeleteString(v12[j]);
LABEL_22:
        operator delete(v12);
        return String;
      }
      v6 += *(unsigned int *)v6 + 4;
    }
    String = Windows::Storage::StateABIHelpers::PropertyValueTraits<1036>::CreatePropertyValue(
               v12,
               v11,
               propertyValueStaticInterface,
               propertyValue);
    if ( String < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x94u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIApiSetValueToSettingProperty.hpp",
        String,
        "CreatePropertyValue %u recordCount %u",
        valueBufferBytes,
        v11);
      for ( k = 0; k < v11; ++k )
        WindowsDeleteString(v12[k]);
      goto LABEL_22;
    }
    for ( m = 0; m < v11; ++m )
      WindowsDeleteString(v12[m]);
    operator delete(v12);
    return 0;
  }
  else
  {
LABEL_26:
    *propertyValue = 0;
    return wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             0x75u,
             "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIApiSetValueToSettingProperty.hpp",
             0x54Fu,
             "Size %u",
             valueBufferBytes);
  }
}

```

## disassembly

```asm
0x1800228dc  mov     [rsp+arg_0], rbx
0x1800228e1  mov     [rsp+arg_10], propertyValueStaticInterface
0x1800228e6  push    rbp
0x1800228e7  push    rsi
0x1800228e8  push    rdi
0x1800228e9  push    r12
0x1800228eb  push    r13
0x1800228ed  push    r14
0x1800228ef  push    r15
0x1800228f1  sub     rsp, 50h
0x1800228f5  xor     r13d, r13d
0x1800228f8  mov     r14d, valueBufferBytes
0x1800228fb  mov     r12, propertyValue
0x1800228fe  mov     rsi, valueBuffer
0x180022901  test    propertyValue, propertyValue
0x180022904  jnz     short loc_18002293E
0x180022906  mov     [rsp+88h+var_60], r14d
0x18002290b  lea     rax, aSizeU; "Size %u"
0x180022912  mov     ebx, 80004003h
0x180022917  lea     valueBufferBytes, [propertyValue+68h]; lineNumber
0x18002291b  mov     valueBuffer, [rsp+88h]; callerReturnAddress
0x180022923  lea     propertyValueStaticInterface, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\statemanage"...
0x18002292a  mov     r9d, ebx; hr
0x18002292d  mov     [rsp+88h+formatString], rax; formatString
0x180022932  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180022937  mov     eax, ebx
0x180022939  jmp     loc_180022B10
0x18002293e  add     valueBuffer, r14
0x180022941  cmp     rsi, valueBuffer
0x180022944  jnb     loc_180022ADD
0x18002294a  mov     rdx, rsi
0x18002294d  mov     ebx, r13d
0x180022950  mov     eax, [rdx]
0x180022952  inc     ebx
0x180022954  add     rdx, 4
0x180022958  add     rdx, rax
0x18002295b  cmp     rdx, valueBuffer
0x18002295e  jb      short loc_180022950
0x180022960  test    ebx, ebx
0x180022962  jz      loc_180022ADD
0x180022968  mov     ecx, ebx
0x18002296a  mov     eax, 8
0x18002296f  mul     valueBuffer
0x180022972  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180022979  cmovb   rax, rbp
0x18002297d  mov     valueBuffer, rax; cb
0x180022980  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022985  mov     rdi, rax
0x180022988  test    rax, rax
0x18002298b  jnz     short loc_1800229A5
0x18002298d  mov     [rsp+88h+var_60], ebx
0x180022991  lea     rax, aNewU; "new %u"
0x180022998  mov     ebx, 8007000Eh
0x18002299d  lea     valueBufferBytes, [rbp+7Bh]
0x1800229a0  jmp     loc_18002291B
0x1800229a5  mov     r15d, r13d
0x1800229a8  cmp     r15d, ebx
0x1800229ab  jnb     loc_180022A44
0x1800229b1  lea     r13, [rsi+4]
0x1800229b5  mov     rdx, rbp
0x1800229b8  xor     eax, eax
0x1800229ba  inc     rdx; length
0x1800229bd  cmp     [r13+rdx*2+0], ax
0x1800229c3  jnz     short loc_1800229BA
0x1800229c5  mov     eax, r15d
0x1800229c8  mov     valueBuffer, r13; sourceString
0x1800229cb  lea     propertyValueStaticInterface, [rdi+rax*8]; string
0x1800229cf  call    cs:__imp_WindowsCreateString
0x1800229d5  mov     ebp, eax
0x1800229d7  test    eax, eax
0x1800229d9  js      short loc_1800229ED
0x1800229db  mov     eax, [rsi]
0x1800229dd  inc     r15d
0x1800229e0  add     rsi, 4
0x1800229e4  add     rsi, rax
0x1800229e7  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800229eb  jmp     short loc_1800229A8
0x1800229ed  mov     valueBuffer, [rsp+88h]; callerReturnAddress
0x1800229f5  lea     rax, aWindowscreates_3; "WindowsCreateString %u Data %ws i %u re"...
0x1800229fc  mov     [rsp+88h+var_48], ebx
0x180022a00  lea     propertyValueStaticInterface, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\statemanage"...
0x180022a07  mov     [rsp+88h+var_50], r15d
0x180022a0c  mov     r9d, ebp; hr
0x180022a0f  mov     [rsp+88h+var_58], r13
0x180022a14  mov     valueBufferBytes, 8Ch; lineNumber
0x180022a19  mov     [rsp+88h+var_60], r14d
0x180022a1e  mov     [rsp+88h+formatString], rax; formatString
0x180022a23  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180022a28  xor     eax, eax
0x180022a2a  mov     esi, eax
0x180022a2c  test    ebx, ebx
0x180022a2e  jz      short loc_180022AAC
0x180022a30  mov     ecx, esi
0x180022a32  mov     valueBuffer, [rdi+valueBuffer*8]; string
0x180022a36  call    cs:__imp_WindowsDeleteString
0x180022a3c  inc     esi
0x180022a3e  cmp     esi, ebx
0x180022a40  jb      short loc_180022A30
0x180022a42  jmp     short loc_180022AAC
0x180022a44  mov     propertyValueStaticInterface, [rsp+88h+arg_10]; propertyValueStaticInterface
0x180022a4c  mov     propertyValue, r12; propertyValue
0x180022a4f  mov     valueBufferBytes, ebx; elements
0x180022a51  mov     valueBuffer, rdi; value
0x180022a54  call    ?CreatePropertyValue@?$PropertyValueTraits@$0EAM@@StateABIHelpers@Storage@Windows@@SAJPEBQEAUHSTRING__@@IAEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1036>::CreatePropertyValue(HSTRING__ * const *,uint,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)
0x180022a59  xor     r13d, r13d
0x180022a5c  mov     ebp, eax
0x180022a5e  test    eax, eax
0x180022a60  jns     short loc_180022AB8
0x180022a62  mov     valueBuffer, [rsp+88h]; callerReturnAddress
0x180022a6a  lea     rax, aCreateproperty; "CreatePropertyValue %u recordCount %u"
0x180022a71  mov     dword ptr [rsp+88h+var_58], ebx
0x180022a75  lea     propertyValueStaticInterface, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\statemanage"...
0x180022a7c  mov     [rsp+88h+var_60], r14d
0x180022a81  mov     r9d, ebp; hr
0x180022a84  mov     valueBufferBytes, 94h; lineNumber
0x180022a89  mov     [rsp+88h+formatString], rax; formatString
0x180022a8e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180022a93  mov     esi, r13d
0x180022a96  test    ebx, ebx
0x180022a98  jz      short loc_180022AAC
0x180022a9a  mov     ecx, esi
0x180022a9c  mov     valueBuffer, [rdi+valueBuffer*8]; string
0x180022aa0  call    cs:__imp_WindowsDeleteString
0x180022aa6  inc     esi
0x180022aa8  cmp     esi, ebx
0x180022aaa  jb      short loc_180022A9A
0x180022aac  mov     valueBuffer, rdi; p
0x180022aaf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022ab4  mov     eax, ebp
0x180022ab6  jmp     short loc_180022B10
0x180022ab8  mov     esi, r13d
0x180022abb  test    ebx, ebx
0x180022abd  jz      short loc_180022AD1
0x180022abf  mov     ecx, esi
0x180022ac1  mov     valueBuffer, [rdi+valueBuffer*8]; string
0x180022ac5  call    cs:__imp_WindowsDeleteString
0x180022acb  inc     esi
0x180022acd  cmp     esi, ebx
0x180022acf  jb      short loc_180022ABF
0x180022ad1  mov     valueBuffer, rdi; p
0x180022ad4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022ad9  xor     eax, eax
0x180022adb  jmp     short loc_180022B10
0x180022add  mov     valueBuffer, [rsp+88h]; callerReturnAddress
0x180022ae5  lea     rax, aSizeU; "Size %u"
0x180022aec  mov     [propertyValue], r13
0x180022aef  lea     propertyValueStaticInterface, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\statemanage"...
0x180022af6  mov     r9d, 54Fh; err
0x180022afc  mov     [rsp+88h+var_60], r14d
0x180022b01  mov     valueBufferBytes, 75h ; 'u'; lineNumber
0x180022b06  mov     [rsp+88h+formatString], rax; formatString
0x180022b0b  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180022b10  mov     rbx, [rsp+88h+arg_0]
0x180022b18  add     rsp, 50h
0x180022b1c  pop     r15
0x180022b1e  pop     r14
0x180022b20  pop     r13
0x180022b22  pop     r12
0x180022b24  pop     rdi
0x180022b25  pop     rsi
0x180022b26  pop     rbp
0x180022b27  retn
```
