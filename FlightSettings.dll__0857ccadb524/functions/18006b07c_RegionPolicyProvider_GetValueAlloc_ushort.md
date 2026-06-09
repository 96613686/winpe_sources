# RegionPolicyProvider::GetValueAlloc(ushort * *)

- ea: `0x18006b07c`
- end: `0x18006b24e`
- name: `?GetValueAlloc@RegionPolicyProvider@@QEAAJPEAPEAG@Z`
- size: `466`
- prototype: `__int64 __fastcall(RegionPolicyProvider *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180049920`

## callees

- `0x180004b80`
- `0x180005744`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x18001ec78`
- `0x180041c44`
- `0x18006a288`
- `0x18006a324`
- `0x18006b07c`
- `0x18006b510`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18006b173`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18006b173`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18006b0e1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18006b0e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006b0d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006b0d3`

## string_xrefs

- `0x18006b0f8`: `onecore\base\flighting\flightsettings\broker\libs\ctac\regionpolicyprovider.cpp`
- `0x18006b1b8`: `onecore\base\flighting\flightsettings\broker\libs\ctac\regionpolicyprovider.cpp`
- `0x18006b213`: `onecore\base\flighting\flightsettings\broker\libs\ctac\regionpolicyprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
int __fastcall RegionPolicyProvider::GetValueAlloc(HSTRING *this, unsigned __int16 **a2)
{
  const OLECHAR *StringRawBuffer; // rax
  HRESULT v5; // eax
  HRESULT v6; // ebx
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // ebx
  unsigned __int16 *v10; // rax
  unsigned int v12[4]; // [rsp+20h] [rbp-E8h] BYREF
  int v13[4]; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C8h]
  GUID pclsid; // [rsp+50h] [rbp-B8h] BYREF
  GUID v16; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v17[128]; // [rsp+70h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47988461>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47988461>::GetImpl'::`2'::impl) )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x3C,
             (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\regionpolicyprovider.cpp",
             (const char *)0x32,
             v12[0]);
  pclsid = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(this[2], 0);
  v5 = CLSIDFromString(StringRawBuffer, &pclsid);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( *((_BYTE *)this + 24) )
    {
      v16 = pclsid;
      *(_QWORD *)v12 = &v16;
      v7 = winrt::impl::call_factory<winrt::Windows::Internal::System::Profile::RegionPolicyEvaluator,winrt::Windows::Internal::System::Profile::IRegionPolicyEvaluatorStatics,_lambda_e2c2817e144d514ec6be4410d5bbf5ff_>(v12);
    }
    else
    {
      *(GUID *)v13 = pclsid;
      *(_QWORD *)v12 = v13;
      v7 = winrt::impl::call_factory<winrt::Windows::Internal::System::Profile::RegionPolicyEvaluator,winrt::Windows::Internal::System::Profile::IRegionPolicyEvaluatorStatics,_lambda_619f5862083d42432f26fb2b85cca6a3_>(v12);
    }
    memset_0(v17, 0, sizeof(v17));
    _o__itow_s(v7, v17, 64);
    memset(v13, 0, sizeof(v13));
    v14 = 0;
    v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(v13, v17, -1);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v10 = *(unsigned __int16 **)v13;
      memset(v13, 0, sizeof(v13));
      v14 = 0;
      *a2 = v10;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v13);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\regionpolicyprovider.cpp",
        (const char *)(unsigned int)v8,
        v12[0]);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v13);
      return v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\regionpolicyprovider.cpp",
      (const char *)(unsigned int)v5,
      v12[0]);
    return v6;
  }
}

```

## disassembly

```asm
0x18006b07c  mov     [rsp+arg_10], rbx
0x18006b081  mov     [rsp+arg_18], rsi
0x18006b086  push    rdi
0x18006b087  sub     rsp, 100h
0x18006b08e  mov     rax, cs:__security_cookie
0x18006b095  xor     rax, rsp
0x18006b098  mov     [rsp+108h+var_18], rax
0x18006b0a0  mov     rsi, rdx
0x18006b0a3  mov     rdi, rcx
0x18006b0a6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47988461@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47988461@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47988461> `wil::Feature<__WilFeatureTraits_Feature_47988461>::GetImpl(void)'::`2'::impl
0x18006b0ad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47988461@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47988461>::__private_IsEnabled(void)
0x18006b0b2  test    al, al
0x18006b0b4  jnz     short loc_18006B0C5
0x18006b0b6  mov     r9d, 32h ; '2'
0x18006b0bc  lea     edx, [r9+0Ah]
0x18006b0c0  jmp     loc_18006B213
0x18006b0c5  xorps   xmm0, xmm0
0x18006b0c8  movups  xmmword ptr [rsp+108h+pclsid.Data1], xmm0
0x18006b0cd  xor     edx, edx; length
0x18006b0cf  mov     rcx, [rdi+10h]; string
0x18006b0d3  call    cs:__imp_WindowsGetStringRawBuffer
0x18006b0d9  lea     rdx, [rsp+108h+pclsid]; pclsid
0x18006b0de  mov     rcx, rax; lpsz
0x18006b0e1  call    cs:__imp_CLSIDFromString
0x18006b0e7  mov     ebx, eax
0x18006b0e9  test    eax, eax
0x18006b0eb  jns     short loc_18006B110
0x18006b0ed  mov     rcx, [rsp+108h]; this
0x18006b0f5  mov     r9d, eax; char *
0x18006b0f8  lea     r8, aOnecoreBaseFli_46; "onecore\\base\\flighting\\flightsetting"...
0x18006b0ff  mov     edx, 41h ; 'A'; void *
0x18006b104  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b109  mov     eax, ebx
0x18006b10b  jmp     loc_18006B228
0x18006b110  movaps  xmm0, xmmword ptr [rsp+108h+pclsid.Data1]
0x18006b115  lea     rcx, [rsp+108h+var_E8]
0x18006b11a  cmp     byte ptr [rdi+18h], 0
0x18006b11e  jz      short loc_18006B139
0x18006b120  movdqa  [rsp+108h+var_A8], xmm0
0x18006b126  lea     rax, [rsp+108h+var_A8]
0x18006b12b  mov     qword ptr [rsp+108h+var_E8], rax
0x18006b130  call    ??$call_factory@URegionPolicyEvaluator@Profile@System@Internal@Windows@winrt@@UIRegionPolicyEvaluatorStatics@23456@V_lambda_e2c2817e144d514ec6be4410d5bbf5ff_@@@impl@winrt@@YA?A_P$$QEAV_lambda_e2c2817e144d514ec6be4410d5bbf5ff_@@@Z
0x18006b135  mov     ebx, eax
0x18006b137  jmp     short loc_18006B150
0x18006b139  movdqa  xmmword ptr [rsp+108h+var_D8], xmm0
0x18006b13f  lea     rax, [rsp+108h+var_D8]
0x18006b144  mov     qword ptr [rsp+108h+var_E8], rax; int
0x18006b149  call    ??$call_factory@URegionPolicyEvaluator@Profile@System@Internal@Windows@winrt@@UIRegionPolicyEvaluatorStatics@23456@V_lambda_619f5862083d42432f26fb2b85cca6a3_@@@impl@winrt@@YA?A_P$$QEAV_lambda_619f5862083d42432f26fb2b85cca6a3_@@@Z
0x18006b14e  mov     ebx, eax
0x18006b150  xor     edx, edx; Val
0x18006b152  mov     r8d, 80h; Size
0x18006b158  lea     rcx, [rsp+108h+var_98]; void *
0x18006b15d  call    memset_0
0x18006b162  mov     r9d, 0Ah
0x18006b168  lea     r8d, [r9+36h]
0x18006b16c  lea     rdx, [rsp+108h+var_98]
0x18006b171  mov     ecx, ebx
0x18006b173  call    cs:__imp__o__itow_s
0x18006b179  mov     qword ptr [rsp+108h+var_D8], 0
0x18006b182  mov     qword ptr [rsp+108h+var_D8+8], 0
0x18006b18b  mov     [rsp+108h+var_C8], 0
0x18006b194  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006b198  lea     rdx, [rsp+108h+var_98]
0x18006b19d  lea     rcx, [rsp+108h+var_D8]
0x18006b1a2  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18006b1a7  mov     ebx, eax
0x18006b1a9  test    eax, eax
0x18006b1ab  jns     short loc_18006B1D7
0x18006b1ad  mov     rcx, [rsp+108h]; this
0x18006b1b5  mov     r9d, eax; char *
0x18006b1b8  lea     r8, aOnecoreBaseFli_46; "onecore\\base\\flighting\\flightsetting"...
0x18006b1bf  mov     edx, 49h ; 'I'; void *
0x18006b1c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b1c9  lea     rcx, [rsp+108h+var_D8]
0x18006b1ce  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006b1d3  mov     eax, ebx
0x18006b1d5  jmp     short loc_18006B228
0x18006b1d7  mov     rax, qword ptr [rsp+108h+var_D8]
0x18006b1dc  mov     qword ptr [rsp+108h+var_D8], 0
0x18006b1e5  mov     [rsp+108h+var_C8], 0
0x18006b1ee  mov     qword ptr [rsp+108h+var_D8+8], 0
0x18006b1f7  mov     [rsi], rax
0x18006b1fa  lea     rcx, [rsp+108h+var_D8]
0x18006b1ff  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006b204  xor     eax, eax
0x18006b206  jmp     short loc_18006B228
0x18006b208  mov     r9d, 65Bh; char *
0x18006b20e  mov     edx, 4Eh ; 'N'; void *
0x18006b213  lea     r8, aOnecoreBaseFli_46; "onecore\\base\\flighting\\flightsetting"...
0x18006b21a  mov     rcx, [rsp+108h]; this
0x18006b222  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006b227  nop
0x18006b228  mov     rcx, [rsp+108h+var_18]
0x18006b230  xor     rcx, rsp; StackCookie
0x18006b233  call    __security_check_cookie
0x18006b238  lea     r11, [rsp+108h+var_8]
0x18006b240  mov     rbx, [r11+20h]
0x18006b244  mov     rsi, [r11+28h]
0x18006b248  mov     rsp, r11
0x18006b24b  pop     rdi
0x18006b24c  retn
```
