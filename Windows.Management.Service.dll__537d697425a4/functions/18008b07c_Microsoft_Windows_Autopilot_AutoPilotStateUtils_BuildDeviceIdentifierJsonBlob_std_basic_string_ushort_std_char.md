# Microsoft::Windows::Autopilot::AutoPilotStateUtils::BuildDeviceIdentifierJsonBlob(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18008b07c`
- end: `0x18008b345`
- name: `?BuildDeviceIdentifierJsonBlob@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEAV56@@Z`
- size: `713`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c1a20`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x180080bac`
- `0x180086044`
- `0x18008a9c4`
- `0x18008aecc`
- `0x18008b07c`
- `0x18008d290`
- `0x18008f570`
- `0x18008f6c0`
- `0x1800901c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008b2eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008b2eb`
- `RPCRT4!UuidCreate` at `0x18008b0af`
- `RPCRT4!UuidCreate` at `0x18008b0af`
- `RPCRT4!UuidToStringW` at `0x18008b0ee`
- `RPCRT4!UuidToStringW` at `0x18008b0ee`
- `RPCRT4!RpcStringFreeW` at `0x18008b31c`
- `RPCRT4!RpcStringFreeW` at `0x18008b31c`

## string_xrefs

- `0x18008b12d`: `Windows.Data.Json.JsonObject`
- `0x18008b0c6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008b179`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008b1eb`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008b2c8`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStateUtils::BuildDeviceIdentifierJsonBlob(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  RPC_STATUS v7; // ebx
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  const unsigned __int16 *v11; // rbx
  const unsigned __int16 *v12; // rax
  int v13; // edi
  __int64 v14; // rdx
  int v15; // eax
  PCWSTR StringRawBuffer; // rax
  struct Windows::Data::Json::IJsonObject *v18; // [rsp+20h] [rbp-60h] BYREF
  HSTRING string; // [rsp+28h] [rbp-58h] BYREF
  RPC_WSTR StringUuid[2]; // [rsp+30h] [rbp-50h] BYREF
  char v21; // [rsp+40h] [rbp-40h]
  UUID Uuid; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v24; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  Uuid = 0;
  v7 = UuidCreate(&Uuid);
  if ( v7 >= 0 )
  {
    StringUuid[0] = 0;
    v7 = UuidToStringW(&Uuid, StringUuid);
    if ( v7 < 0 )
    {
      v8 = 341;
      goto LABEL_3;
    }
    StringUuid[1] = (RPC_WSTR)StringUuid;
    v21 = 1;
    v18 = 0;
    v24 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    v9 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v24, &v18);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v9 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v18, L"Version", L"1.0.0");
      v7 = v9;
      if ( v9 >= 0 )
      {
        v9 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v18, L"Id", StringUuid[0]);
        v7 = v9;
        if ( v9 >= 0 )
        {
          v11 = &sourceString;
          if ( *(_QWORD *)(a1 + 16) )
            v12 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
          else
            v12 = &sourceString;
          v13 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v18, L"ZtdId", v12);
          if ( v13 >= 0 )
          {
            v13 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v18, L"PKID", &sourceString);
            if ( v13 >= 0 )
            {
              if ( *(_QWORD *)(a2 + 16) )
                v11 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
              v9 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v18, L"SerialNumber", v11);
              v7 = v9;
              if ( v9 >= 0 )
              {
                v9 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v18, L"SequenceBlockNumber", 1u);
                v7 = v9;
                if ( v9 >= 0 )
                {
                  v9 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v18, L"TotalBlocks", 1u);
                  v7 = v9;
                  if ( v9 >= 0 )
                  {
                    string = 0;
                    v15 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(v18, &string);
                    v7 = v15;
                    if ( v15 >= 0 )
                    {
                      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                      std::wstring::assign(a4, StringRawBuffer);
                      Windows::Internal::String::~String((Windows::Internal::String *)&string);
                      v7 = 0;
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x167,
                        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
                        (const char *)(unsigned int)v15,
                        (int)v18);
                      Windows::Internal::String::~String((Windows::Internal::String *)&string);
                    }
                    goto LABEL_32;
                  }
                  v10 = 356;
                }
                else
                {
                  v10 = 355;
                }
              }
              else
              {
                v10 = 354;
              }
              goto LABEL_10;
            }
            v14 = 353;
          }
          else
          {
            v14 = 352;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v14,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
            (const char *)(unsigned int)v13,
            (int)v18);
          v7 = v13;
          goto LABEL_32;
        }
        v10 = 351;
      }
      else
      {
        v10 = 350;
      }
    }
    else
    {
      v10 = 348;
    }
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
      (const char *)(unsigned int)v9,
      (int)v18);
LABEL_32:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    RpcStringFreeW(StringUuid);
    return (unsigned int)v7;
  }
  v8 = 338;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
    (const char *)(unsigned int)v7,
    (int)v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18008b07c  push    rbp
0x18008b07e  push    rbx
0x18008b07f  push    rsi
0x18008b080  push    rdi
0x18008b081  push    r14
0x18008b083  mov     rbp, rsp
0x18008b086  sub     rsp, 80h
0x18008b08d  mov     rax, cs:__security_cookie
0x18008b094  xor     rax, rsp
0x18008b097  mov     [rbp+var_8], rax
0x18008b09b  mov     r14, r9
0x18008b09e  mov     rsi, rdx
0x18008b0a1  mov     rdi, rcx
0x18008b0a4  xorps   xmm0, xmm0
0x18008b0a7  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18008b0ab  lea     rcx, [rbp+Uuid]; Uuid
0x18008b0af  call    cs:__imp_UuidCreate
0x18008b0b6  nop     dword ptr [rax+rax+00h]
0x18008b0bb  mov     ebx, eax
0x18008b0bd  test    eax, eax
0x18008b0bf  jns     short loc_18008B0DE
0x18008b0c1  mov     edx, 152h; void *
0x18008b0c6  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008b0cd  mov     r9d, ebx; char *
0x18008b0d0  mov     rcx, [rbp+28h]; this
0x18008b0d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b0d9  jmp     loc_18008B328
0x18008b0de  mov     [rbp+StringUuid], 0
0x18008b0e6  lea     rdx, [rbp+StringUuid]; StringUuid
0x18008b0ea  lea     rcx, [rbp+Uuid]; Uuid
0x18008b0ee  call    cs:__imp_UuidToStringW
0x18008b0f5  nop     dword ptr [rax+rax+00h]
0x18008b0fa  mov     ebx, eax
0x18008b0fc  test    eax, eax
0x18008b0fe  jns     short loc_18008B107
0x18008b100  mov     edx, 155h
0x18008b105  jmp     short loc_18008B0C6
0x18008b107  lea     rax, [rbp+StringUuid]
0x18008b10b  mov     [rbp+var_48], rax
0x18008b10f  mov     [rbp+var_40], 1
0x18008b113  mov     [rbp+var_60], 0
0x18008b11b  mov     [rbp+var_10], 0
0x18008b123  mov     r9d, 1Ch; unsigned int
0x18008b129  lea     r8d, [r9+1]; unsigned int
0x18008b12d  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18008b134  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18008b138  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008b13d  lea     rdx, [rbp+var_60]
0x18008b141  mov     rcx, [rbp+var_10]
0x18008b145  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18008b14a  mov     ebx, eax
0x18008b14c  test    eax, eax
0x18008b14e  jns     short loc_18008B157
0x18008b150  mov     edx, 15Ch
0x18008b155  jmp     short loc_18008B179
0x18008b157  lea     r8, a100; "1.0.0"
0x18008b15e  lea     rdx, aVersion; "Version"
0x18008b165  mov     rcx, [rbp+var_60]; struct Windows::Data::Json::IJsonObject *
0x18008b169  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18008b16e  mov     ebx, eax
0x18008b170  test    eax, eax
0x18008b172  jns     short loc_18008B191
0x18008b174  mov     edx, 15Eh; void *
0x18008b179  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008b180  mov     r9d, eax; char *
0x18008b183  mov     rcx, [rbp+28h]; this
0x18008b187  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b18c  jmp     loc_18008B30E
0x18008b191  mov     r8, [rbp+StringUuid]; unsigned __int16 *
0x18008b195  lea     rdx, aId; "Id"
0x18008b19c  mov     rcx, [rbp+var_60]; struct Windows::Data::Json::IJsonObject *
0x18008b1a0  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18008b1a5  mov     ebx, eax
0x18008b1a7  test    eax, eax
0x18008b1a9  jns     short loc_18008B1B2
0x18008b1ab  mov     edx, 15Fh
0x18008b1b0  jmp     short loc_18008B179
0x18008b1b2  lea     rbx, sourceString
0x18008b1b9  cmp     qword ptr [rdi+10h], 0
0x18008b1be  jnz     short loc_18008B1C5
0x18008b1c0  mov     rax, rbx
0x18008b1c3  jmp     short loc_18008B1CD
0x18008b1c5  mov     rcx, rdi
0x18008b1c8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008b1cd  mov     r8, rax; unsigned __int16 *
0x18008b1d0  lea     rdx, aZtdid; "ZtdId"
0x18008b1d7  mov     rcx, [rbp+var_60]; struct Windows::Data::Json::IJsonObject *
0x18008b1db  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18008b1e0  mov     edi, eax
0x18008b1e2  test    eax, eax
0x18008b1e4  jns     short loc_18008B205
0x18008b1e6  mov     edx, 160h; void *
0x18008b1eb  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008b1f2  mov     r9d, edi; char *
0x18008b1f5  mov     rcx, [rbp+28h]; this
0x18008b1f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b1fe  mov     ebx, edi
0x18008b200  jmp     loc_18008B30E
0x18008b205  mov     r8, rbx; unsigned __int16 *
0x18008b208  lea     rdx, aPkid; "PKID"
0x18008b20f  mov     rcx, [rbp+var_60]; struct Windows::Data::Json::IJsonObject *
0x18008b213  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18008b218  mov     edi, eax
0x18008b21a  test    eax, eax
0x18008b21c  jns     short loc_18008B225
0x18008b21e  mov     edx, 161h
0x18008b223  jmp     short loc_18008B1EB
0x18008b225  cmp     qword ptr [rsi+10h], 0
0x18008b22a  jz      short loc_18008B237
0x18008b22c  mov     rcx, rsi
0x18008b22f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008b234  mov     rbx, rax
0x18008b237  mov     r8, rbx; unsigned __int16 *
0x18008b23a  lea     rdx, aSerialnumber; "SerialNumber"
0x18008b241  mov     rcx, [rbp+var_60]; struct Windows::Data::Json::IJsonObject *
0x18008b245  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18008b24a  mov     ebx, eax
0x18008b24c  test    eax, eax
0x18008b24e  jns     short loc_18008B25A
0x18008b250  mov     edx, 162h
0x18008b255  jmp     loc_18008B179
0x18008b25a  mov     r8d, 1; unsigned int
0x18008b260  lea     rdx, aSequenceblockn; "SequenceBlockNumber"
0x18008b267  mov     rcx, [rbp+var_60]; struct Windows::Data::Json::IJsonObject *
0x18008b26b  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x18008b270  mov     ebx, eax
0x18008b272  test    eax, eax
0x18008b274  jns     short loc_18008B280
0x18008b276  mov     edx, 163h
0x18008b27b  jmp     loc_18008B179
0x18008b280  mov     r8d, 1; unsigned int
0x18008b286  lea     rdx, aTotalblocks; "TotalBlocks"
0x18008b28d  mov     rcx, [rbp+var_60]; struct Windows::Data::Json::IJsonObject *
0x18008b291  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x18008b296  mov     ebx, eax
0x18008b298  test    eax, eax
0x18008b29a  jns     short loc_18008B2A6
0x18008b29c  mov     edx, 164h
0x18008b2a1  jmp     loc_18008B179
0x18008b2a6  mov     [rbp+string], 0
0x18008b2ae  lea     rdx, [rbp+string]
0x18008b2b2  mov     rcx, [rbp+var_60]
0x18008b2b6  call    ?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x18008b2bb  mov     ebx, eax
0x18008b2bd  test    eax, eax
0x18008b2bf  jns     short loc_18008B2E5
0x18008b2c1  mov     rcx, [rbp+28h]; this
0x18008b2c5  mov     r9d, eax; char *
0x18008b2c8  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008b2cf  mov     edx, 167h; void *
0x18008b2d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b2d9  nop
0x18008b2da  lea     rcx, [rbp+string]; this
0x18008b2de  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18008b2e3  jmp     short loc_18008B30E
0x18008b2e5  xor     edx, edx; length
0x18008b2e7  mov     rcx, [rbp+string]; string
0x18008b2eb  call    cs:__imp_WindowsGetStringRawBuffer
0x18008b2f2  nop     dword ptr [rax+rax+00h]
0x18008b2f7  mov     rdx, rax
0x18008b2fa  mov     rcx, r14
0x18008b2fd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18008b302  nop
0x18008b303  lea     rcx, [rbp+string]; this
0x18008b307  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18008b30c  xor     ebx, ebx
0x18008b30e  lea     rcx, [rbp+var_60]
0x18008b312  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008b317  nop
0x18008b318  lea     rcx, [rbp+StringUuid]; String
0x18008b31c  call    cs:__imp_RpcStringFreeW
0x18008b323  nop     dword ptr [rax+rax+00h]
0x18008b328  mov     eax, ebx
0x18008b32a  mov     rcx, [rbp+var_8]
0x18008b32e  xor     rcx, rsp; StackCookie
0x18008b331  call    __security_check_cookie
0x18008b336  add     rsp, 80h
0x18008b33d  pop     r14
0x18008b33f  pop     rdi
0x18008b340  pop     rsi
0x18008b341  pop     rbx
0x18008b342  pop     rbp
0x18008b343  retn
```
