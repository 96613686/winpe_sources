# Microsoft::Windows::Autopilot::AutoPilotStateUtils::BuildDeviceIdentifierJsonBlob(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18008a1ac`
- end: `0x18008a45c`
- name: `?BuildDeviceIdentifierJsonBlob@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEAV56@@Z`
- size: `688`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bfba0`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18008019c`
- `0x1800853a0`
- `0x180089b58`
- `0x18008a014`
- `0x18008a1ac`
- `0x18008c244`
- `0x18008e438`
- `0x18008e584`
- `0x18008f068`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a40f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a40f`
- `RPCRT4!UuidCreate` at `0x18008a1df`
- `RPCRT4!UuidCreate` at `0x18008a1df`
- `RPCRT4!UuidToStringW` at `0x18008a218`
- `RPCRT4!UuidToStringW` at `0x18008a218`
- `RPCRT4!RpcStringFreeW` at `0x18008a43a`
- `RPCRT4!RpcStringFreeW` at `0x18008a43a`

## string_xrefs

- `0x18008a251`: `Windows.Data.Json.JsonObject`
- `0x18008a1f0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008a29d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008a30f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008a3ec`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

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
0x18008a1ac  push    rbp
0x18008a1ae  push    rbx
0x18008a1af  push    rsi
0x18008a1b0  push    rdi
0x18008a1b1  push    r14
0x18008a1b3  mov     rbp, rsp
0x18008a1b6  sub     rsp, 80h
0x18008a1bd  mov     rax, cs:__security_cookie
0x18008a1c4  xor     rax, rsp
0x18008a1c7  mov     [rbp+var_8], rax
0x18008a1cb  mov     r14, r9
0x18008a1ce  mov     rsi, rdx
0x18008a1d1  mov     rdi, rcx
0x18008a1d4  xorps   xmm0, xmm0
0x18008a1d7  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18008a1db  lea     rcx, [rbp+Uuid]; Uuid
0x18008a1df  call    cs:__imp_UuidCreate
0x18008a1e5  mov     ebx, eax
0x18008a1e7  test    eax, eax
0x18008a1e9  jns     short loc_18008A208
0x18008a1eb  mov     edx, 152h; void *
0x18008a1f0  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008a1f7  mov     r9d, ebx; char *
0x18008a1fa  mov     rcx, [rbp+28h]; this
0x18008a1fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a203  jmp     loc_18008A440
0x18008a208  mov     [rbp+StringUuid], 0
0x18008a210  lea     rdx, [rbp+StringUuid]; StringUuid
0x18008a214  lea     rcx, [rbp+Uuid]; Uuid
0x18008a218  call    cs:__imp_UuidToStringW
0x18008a21e  mov     ebx, eax
0x18008a220  test    eax, eax
0x18008a222  jns     short loc_18008A22B
0x18008a224  mov     edx, 155h
0x18008a229  jmp     short loc_18008A1F0
0x18008a22b  lea     rax, [rbp+StringUuid]
0x18008a22f  mov     [rbp+var_48], rax
0x18008a233  mov     [rbp+var_40], 1
0x18008a237  mov     [rbp+var_60], 0
0x18008a23f  mov     [rbp+var_10], 0
0x18008a247  mov     r9d, 1Ch; unsigned int
0x18008a24d  lea     r8d, [r9+1]; unsigned int
0x18008a251  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18008a258  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18008a25c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008a261  lea     rdx, [rbp+var_60]
0x18008a265  mov     rcx, [rbp+var_10]
0x18008a269  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18008a26e  mov     ebx, eax
0x18008a270  test    eax, eax
0x18008a272  jns     short loc_18008A27B
0x18008a274  mov     edx, 15Ch
0x18008a279  jmp     short loc_18008A29D
0x18008a27b  lea     r8, a100; "1.0.0"
0x18008a282  lea     rdx, aVersion; "Version"
0x18008a289  mov     rcx, [rbp+var_60]; struct Windows::Data::Json::IJsonObject *
0x18008a28d  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18008a292  mov     ebx, eax
0x18008a294  test    eax, eax
0x18008a296  jns     short loc_18008A2B5
0x18008a298  mov     edx, 15Eh; void *
0x18008a29d  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008a2a4  mov     r9d, eax; char *
0x18008a2a7  mov     rcx, [rbp+28h]; this
0x18008a2ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a2b0  jmp     loc_18008A42C
0x18008a2b5  mov     r8, [rbp+StringUuid]; unsigned __int16 *
0x18008a2b9  lea     rdx, aId; "Id"
0x18008a2c0  mov     rcx, [rbp+var_60]; struct Windows::Data::Json::IJsonObject *
0x18008a2c4  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18008a2c9  mov     ebx, eax
0x18008a2cb  test    eax, eax
0x18008a2cd  jns     short loc_18008A2D6
0x18008a2cf  mov     edx, 15Fh
0x18008a2d4  jmp     short loc_18008A29D
0x18008a2d6  lea     rbx, sourceString
0x18008a2dd  cmp     qword ptr [rdi+10h], 0
0x18008a2e2  jnz     short loc_18008A2E9
0x18008a2e4  mov     rax, rbx
0x18008a2e7  jmp     short loc_18008A2F1
0x18008a2e9  mov     rcx, rdi
0x18008a2ec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008a2f1  mov     r8, rax; unsigned __int16 *
0x18008a2f4  lea     rdx, aZtdid; "ZtdId"
0x18008a2fb  mov     rcx, [rbp+var_60]; struct Windows::Data::Json::IJsonObject *
0x18008a2ff  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18008a304  mov     edi, eax
0x18008a306  test    eax, eax
0x18008a308  jns     short loc_18008A329
0x18008a30a  mov     edx, 160h; void *
0x18008a30f  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008a316  mov     r9d, edi; char *
0x18008a319  mov     rcx, [rbp+28h]; this
0x18008a31d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a322  mov     ebx, edi
0x18008a324  jmp     loc_18008A42C
0x18008a329  mov     r8, rbx; unsigned __int16 *
0x18008a32c  lea     rdx, aPkid; "PKID"
0x18008a333  mov     rcx, [rbp+var_60]; struct Windows::Data::Json::IJsonObject *
0x18008a337  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18008a33c  mov     edi, eax
0x18008a33e  test    eax, eax
0x18008a340  jns     short loc_18008A349
0x18008a342  mov     edx, 161h
0x18008a347  jmp     short loc_18008A30F
0x18008a349  cmp     qword ptr [rsi+10h], 0
0x18008a34e  jz      short loc_18008A35B
0x18008a350  mov     rcx, rsi
0x18008a353  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008a358  mov     rbx, rax
0x18008a35b  mov     r8, rbx; unsigned __int16 *
0x18008a35e  lea     rdx, aSerialnumber; "SerialNumber"
0x18008a365  mov     rcx, [rbp+var_60]; struct Windows::Data::Json::IJsonObject *
0x18008a369  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18008a36e  mov     ebx, eax
0x18008a370  test    eax, eax
0x18008a372  jns     short loc_18008A37E
0x18008a374  mov     edx, 162h
0x18008a379  jmp     loc_18008A29D
0x18008a37e  mov     r8d, 1; unsigned int
0x18008a384  lea     rdx, aSequenceblockn; "SequenceBlockNumber"
0x18008a38b  mov     rcx, [rbp+var_60]; struct Windows::Data::Json::IJsonObject *
0x18008a38f  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x18008a394  mov     ebx, eax
0x18008a396  test    eax, eax
0x18008a398  jns     short loc_18008A3A4
0x18008a39a  mov     edx, 163h
0x18008a39f  jmp     loc_18008A29D
0x18008a3a4  mov     r8d, 1; unsigned int
0x18008a3aa  lea     rdx, aTotalblocks; "TotalBlocks"
0x18008a3b1  mov     rcx, [rbp+var_60]; struct Windows::Data::Json::IJsonObject *
0x18008a3b5  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x18008a3ba  mov     ebx, eax
0x18008a3bc  test    eax, eax
0x18008a3be  jns     short loc_18008A3CA
0x18008a3c0  mov     edx, 164h
0x18008a3c5  jmp     loc_18008A29D
0x18008a3ca  mov     [rbp+string], 0
0x18008a3d2  lea     rdx, [rbp+string]
0x18008a3d6  mov     rcx, [rbp+var_60]
0x18008a3da  call    ?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x18008a3df  mov     ebx, eax
0x18008a3e1  test    eax, eax
0x18008a3e3  jns     short loc_18008A409
0x18008a3e5  mov     rcx, [rbp+28h]; this
0x18008a3e9  mov     r9d, eax; char *
0x18008a3ec  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008a3f3  mov     edx, 167h; void *
0x18008a3f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a3fd  nop
0x18008a3fe  lea     rcx, [rbp+string]; this
0x18008a402  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18008a407  jmp     short loc_18008A42C
0x18008a409  xor     edx, edx; length
0x18008a40b  mov     rcx, [rbp+string]; string
0x18008a40f  call    cs:__imp_WindowsGetStringRawBuffer
0x18008a415  mov     rdx, rax
0x18008a418  mov     rcx, r14
0x18008a41b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18008a420  nop
0x18008a421  lea     rcx, [rbp+string]; this
0x18008a425  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18008a42a  xor     ebx, ebx
0x18008a42c  lea     rcx, [rbp+var_60]
0x18008a430  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008a435  nop
0x18008a436  lea     rcx, [rbp+StringUuid]; String
0x18008a43a  call    cs:__imp_RpcStringFreeW
0x18008a440  mov     eax, ebx
0x18008a442  mov     rcx, [rbp+var_8]
0x18008a446  xor     rcx, rsp; StackCookie
0x18008a449  call    __security_check_cookie
0x18008a44e  add     rsp, 80h
0x18008a455  pop     r14
0x18008a457  pop     rdi
0x18008a458  pop     rsi
0x18008a459  pop     rbx
0x18008a45a  pop     rbp
0x18008a45b  retn
```
