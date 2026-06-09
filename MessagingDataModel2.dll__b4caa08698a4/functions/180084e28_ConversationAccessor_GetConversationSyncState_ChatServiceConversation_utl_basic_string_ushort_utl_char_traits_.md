# ConversationAccessor::GetConversationSyncState(ChatServiceConversation *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,int *)

- ea: `0x180084e28`
- end: `0x18008522b`
- name: `?GetConversationSyncState@ConversationAccessor@@QEAAJPEAVChatServiceConversation@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAH@Z`
- size: `1027`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180078a14`

## callees

- `0x180005c50`
- `0x180008870`
- `0x18000a754`
- `0x18000b6d4`
- `0x18000b7d4`
- `0x1800242c4`
- `0x180030bd0`
- `0x180046b18`
- `0x18006b108`
- `0x180084738`
- `0x180084864`
- `0x180084e28`
- `0x180085260`
- `0x180085c88`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180084f5d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180084f5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180085158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180085158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800850ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085132`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800851a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800850ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085132`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800851a6`

## string_xrefs

- `0x180084f36`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall ConversationAccessor::GetConversationSyncState(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  int ConversationForParticipants; // eax
  unsigned int v8; // ebx
  __int64 v9; // rbx
  int v10; // eax
  int ActivationFactory; // eax
  char v12; // r8
  __int64 v13; // rcx
  void (*v14)(void); // rax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, PVOID, _QWORD); // rbx
  HSTRING_HEADER *v17; // rax
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  char v21; // r8
  const WCHAR *v22; // rdx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, PVOID, _BYTE *); // rbx
  HSTRING_HEADER *v25; // rax
  char v26; // r8
  const WCHAR *v27; // rdx
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v29)(_QWORD, GUID *, __int64); // rbx
  HSTRING_HEADER *v30; // rax
  int v31; // eax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, PVOID, HSTRING *); // rbx
  char v34; // r8
  HSTRING_HEADER *v35; // rax
  int v36; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v38; // rcx
  __int64 v40; // [rsp+30h] [rbp-79h] BYREF
  const WCHAR *v41; // [rsp+38h] [rbp-71h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-69h] BYREF
  __int64 v43; // [rsp+58h] [rbp-51h]
  _BYTE v44[8]; // [rsp+60h] [rbp-49h] BYREF
  __int64 v45; // [rsp+68h] [rbp-41h] BYREF
  const WCHAR *v46; // [rsp+70h] [rbp-39h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64); // [rsp+78h] [rbp-31h] BYREF
  __int64 v48; // [rsp+80h] [rbp-29h] BYREF
  __int64 v49; // [rsp+88h] [rbp-21h] BYREF
  HSTRING string; // [rsp+90h] [rbp-19h] BYREF
  __int64 v51; // [rsp+98h] [rbp-11h] BYREF
  __int64 v52; // [rsp+A0h] [rbp-9h] BYREF
  _OWORD v53[2]; // [rsp+A8h] [rbp-1h] BYREF

  *a4 = 0;
  v40 = 0;
  ConversationForParticipants = ConversationAccessor::_GetConversationForParticipants(a1, a2 + 168, &v40);
  v8 = ConversationForParticipants;
  if ( ConversationForParticipants >= 0 )
  {
    v9 = v40;
    v49 = 0;
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 88LL))(v40, &v49) >= 0 )
    {
      v48 = 0;
      *a4 = 1;
      ATL::CComQIPtr<ISmConversationPriv,&__s_GUID const _GUID_778e0f12_3c47_4b4a_92e7_975a59228204>::CComQIPtr<ISmConversationPriv,&__s_GUID const _GUID_778e0f12_3c47_4b4a_92e7_975a59228204>(
        &v48,
        v9);
      v46 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, const WCHAR **))(*(_QWORD *)v48 + 344LL))(v48, &v46);
      v8 = v10;
      if ( v10 < 0 )
      {
        Log_HREvent_62(v10);
LABEL_6:
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v46);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
        goto LABEL_35;
      }
      if ( v46 && *v46 )
      {
        v45 = 0;
        v43 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Data.Json.JsonObject",
          0x1Du,
          0x1Cu);
        ActivationFactory = RoGetActivationFactory(v43, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v45);
        v8 = ActivationFactory;
        if ( ActivationFactory < 0 )
        {
          Log_HREvent_62(ActivationFactory);
          v13 = v45;
          if ( !v45 )
            goto LABEL_6;
          v45 = 0;
          v14 = *(void (**)(void))(*(_QWORD *)v13 + 16LL);
LABEL_12:
          v14();
          goto LABEL_6;
        }
        v15 = v45;
        v47 = 0;
        v16 = *(__int64 (__fastcall **)(__int64, PVOID, _QWORD))(*(_QWORD *)v45 + 48LL);
        v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v46, v12);
        v18 = v16(v15, v17[1].Reserved.Reserved1, &v47);
        v8 = v18;
        if ( v18 < 0 )
        {
          Log_HREvent_62(v18);
LABEL_15:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
          v19 = v45;
          if ( !v45 )
            goto LABEL_6;
          v45 = 0;
          v14 = *(void (**)(void))(*(_QWORD *)v19 + 16LL);
          goto LABEL_12;
        }
        v51 = 0;
        v20 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
                &v47,
                (__int64)&v51);
        v8 = v20;
        if ( v20 < 0 )
          goto LABEL_18;
        v22 = *(const WCHAR **)(a2 + 56);
        v23 = v51;
        v44[0] = 0;
        v41 = v22;
        v24 = *(__int64 (__fastcall **)(__int64, PVOID, _BYTE *))(*(_QWORD *)v51 + 64LL);
        v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v41, v21);
        v20 = v24(v23, v25[1].Reserved.Reserved1, v44);
        v8 = v20;
        if ( v20 < 0 )
        {
LABEL_18:
          Log_HREvent_62(v20);
LABEL_19:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
          goto LABEL_15;
        }
        if ( v44[0] )
        {
          v27 = *(const WCHAR **)(a2 + 56);
          v28 = v47;
          v52 = 0;
          v41 = v27;
          v29 = (*v47)[8];
          v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v41, v26);
          v31 = v29(v28, (GUID *)v30[1].Reserved.Reserved1, (__int64)&v52);
          v8 = v31;
          if ( v31 < 0 )
          {
            Log_HREvent_62(v31);
LABEL_24:
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
            goto LABEL_19;
          }
          v32 = v52;
          string = 0;
          v33 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v52 + 80LL);
          WindowsDeleteString(0);
          string = 0;
          v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)off_1800FD678,
                  v34);
          v36 = v33(v32, v35[1].Reserved.Reserved1, &string);
          v8 = v36;
          if ( v36 < 0 )
          {
            Log_HREvent_62(v36);
LABEL_27:
            WindowsDeleteString(string);
            string = 0;
            goto LABEL_24;
          }
          memset(v53, 0, sizeof(v53));
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v53);
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                   v53,
                                   StringRawBuffer) )
          {
            v8 = -2147024882;
            Log_HREvent_62(-2147024882);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v53);
            goto LABEL_27;
          }
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
            a3,
            v53);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v53);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
        v38 = v45;
        if ( v45 )
        {
          v45 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        }
      }
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v46);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
    v8 = 0;
    goto LABEL_35;
  }
  Log_HREvent_62(ConversationForParticipants);
LABEL_35:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
  return v8;
}

```

## disassembly

```asm
0x180084e28  push    rbp
0x180084e2a  push    rbx
0x180084e2b  push    rsi
0x180084e2c  push    rdi
0x180084e2d  push    r12
0x180084e2f  push    r14
0x180084e31  push    r15
0x180084e33  lea     rbp, [rsp-27h]
0x180084e38  sub     rsp, 0D0h
0x180084e3f  mov     rax, cs:__security_cookie
0x180084e46  xor     rax, rsp
0x180084e49  mov     [rbp+57h+var_38], rax
0x180084e4d  mov     r15, r8
0x180084e50  mov     r14, rdx
0x180084e53  xor     r12d, r12d
0x180084e56  lea     r8, [rbp+57h+var_D0]
0x180084e5a  add     rdx, 0A8h
0x180084e61  mov     [r9], r12d
0x180084e64  mov     [rbp+57h+var_D0], r12
0x180084e68  mov     rdi, r9
0x180084e6b  call    ?_GetConversationForParticipants@ConversationAccessor@@AEAAJPEBV?$vector@V?$CComPtr@VChatServiceParticipant@@@ATL@@V?$allocator@V?$CComPtr@VChatServiceParticipant@@@ATL@@@utl@@@utl@@PEAPEAUISmConversation@@@Z; ConversationAccessor::_GetConversationForParticipants(utl::vector<ATL::CComPtr<ChatServiceParticipant>,utl::allocator<ATL::CComPtr<ChatServiceParticipant>>> const *,ISmConversation * *)
0x180084e70  mov     ebx, eax
0x180084e72  test    eax, eax
0x180084e74  jns     short loc_180084E8B
0x180084e76  lea     edx, [r12+1]
0x180084e7b  mov     ecx, eax; int
0x180084e7d  lea     r9d, [rdx+7Fh]
0x180084e81  call    Log_HREvent_62
0x180084e86  jmp     loc_180085202
0x180084e8b  mov     rbx, [rbp+57h+var_D0]
0x180084e8f  lea     rdx, [rbp+57h+var_78]
0x180084e93  mov     [rbp+57h+var_78], r12
0x180084e97  mov     rcx, rbx
0x180084e9a  mov     rax, [rbx]
0x180084e9d  mov     rax, [rax+58h]
0x180084ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084ea6  test    eax, eax
0x180084ea8  js      loc_1800851F6
0x180084eae  mov     esi, 1
0x180084eb3  mov     [rbp+57h+var_80], r12
0x180084eb7  mov     rdx, rbx
0x180084eba  mov     [rdi], esi
0x180084ebc  lea     rcx, [rbp+57h+var_80]
0x180084ec0  call    ??0?$CComQIPtr@UISmConversationPriv@@$1?_GUID_778e0f12_3c47_4b4a_92e7_975a59228204@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ISmConversationPriv,&__s_GUID const _GUID_778e0f12_3c47_4b4a_92e7_975a59228204>::CComQIPtr<ISmConversationPriv,&__s_GUID const _GUID_778e0f12_3c47_4b4a_92e7_975a59228204>(IUnknown *)
0x180084ec5  mov     rcx, [rbp+57h+var_80]
0x180084ec9  lea     rdx, [rbp+57h+var_90]
0x180084ecd  mov     [rbp+57h+var_90], r12
0x180084ed1  mov     rax, [rcx]
0x180084ed4  mov     rax, [rax+158h]
0x180084edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084ee0  mov     ebx, eax
0x180084ee2  test    eax, eax
0x180084ee4  jns     short loc_180084F15
0x180084ee6  mov     r9d, 8Eh
0x180084eec  mov     edx, esi
0x180084eee  mov     ecx, eax; int
0x180084ef0  call    Log_HREvent_62
0x180084ef5  lea     rcx, [rbp+57h+var_90]
0x180084ef9  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x180084efe  lea     rcx, [rbp+57h+var_80]
0x180084f02  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180084f07  lea     rcx, [rbp+57h+var_78]
0x180084f0b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180084f10  jmp     loc_180085202
0x180084f15  mov     rax, [rbp+57h+var_90]
0x180084f19  test    rax, rax
0x180084f1c  jz      loc_1800851E4
0x180084f22  cmp     r12w, [rax]
0x180084f26  jz      loc_1800851E4
0x180084f2c  mov     r9d, 1Ch; unsigned int
0x180084f32  mov     [rbp+57h+var_98], r12
0x180084f36  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180084f3d  mov     [rbp+57h+var_A8], r12
0x180084f41  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180084f45  lea     r8d, [r9+1]; unsigned int
0x180084f49  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180084f4e  mov     rcx, [rbp+57h+var_A8]
0x180084f52  lea     r8, [rbp+57h+var_98]
0x180084f56  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x180084f5d  call    cs:__imp_RoGetActivationFactory
0x180084f63  mov     ebx, eax
0x180084f65  test    eax, eax
0x180084f67  jns     short loc_180084F9A
0x180084f69  mov     r9d, 9Ah
0x180084f6f  mov     edx, esi
0x180084f71  mov     ecx, eax; int
0x180084f73  call    Log_HREvent_62
0x180084f78  mov     rcx, [rbp+57h+var_98]
0x180084f7c  test    rcx, rcx
0x180084f7f  jz      loc_180084EF5
0x180084f85  mov     [rbp+57h+var_98], r12
0x180084f89  mov     rdx, [rcx]
0x180084f8c  mov     rax, [rdx+10h]
0x180084f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084f95  jmp     loc_180084EF5
0x180084f9a  mov     rdi, [rbp+57h+var_98]
0x180084f9e  lea     rdx, [rbp+57h+var_90]
0x180084fa2  mov     [rbp+57h+var_88], r12
0x180084fa6  lea     rcx, [rbp+57h+hstringHeader]
0x180084faa  mov     rax, [rdi]
0x180084fad  mov     rbx, [rax+30h]
0x180084fb1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180084fb6  lea     r8, [rbp+57h+var_88]
0x180084fba  mov     rcx, rdi
0x180084fbd  mov     rdx, [rax+18h]
0x180084fc1  mov     rax, rbx
0x180084fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084fc9  mov     ebx, eax
0x180084fcb  test    eax, eax
0x180084fcd  jns     short loc_180085001
0x180084fcf  mov     r9d, 9Eh
0x180084fd5  mov     edx, esi
0x180084fd7  mov     ecx, eax; int
0x180084fd9  call    Log_HREvent_62
0x180084fde  lea     rcx, [rbp+57h+var_88]
0x180084fe2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180084fe7  mov     rcx, [rbp+57h+var_98]
0x180084feb  test    rcx, rcx
0x180084fee  jz      loc_180084EF5
0x180084ff4  mov     [rbp+57h+var_98], r12
0x180084ff8  mov     rax, [rcx]
0x180084ffb  mov     rax, [rax+10h]
0x180084fff  jmp     short loc_180084F90
0x180085001  lea     rdx, [rbp+57h+var_68]
0x180085005  mov     [rbp+57h+var_68], r12
0x180085009  lea     rcx, [rbp+57h+var_88]
0x18008500d  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x180085012  mov     ebx, eax
0x180085014  test    eax, eax
0x180085016  jns     short loc_180085032
0x180085018  mov     r9d, 0A1h
0x18008501e  mov     edx, esi
0x180085020  mov     ecx, eax; int
0x180085022  call    Log_HREvent_62
0x180085027  lea     rcx, [rbp+57h+var_68]
0x18008502b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085030  jmp     short loc_180084FDE
0x180085032  mov     rdx, [r14+38h]
0x180085036  lea     rcx, [rbp+57h+hstringHeader]
0x18008503a  mov     rdi, [rbp+57h+var_68]
0x18008503e  mov     [rbp+57h+var_A0], r12b
0x180085042  mov     [rbp+57h+var_C8], rdx
0x180085046  lea     rdx, [rbp+57h+var_C8]
0x18008504a  mov     rax, [rdi]
0x18008504d  mov     rbx, [rax+40h]
0x180085051  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180085056  lea     r8, [rbp+57h+var_A0]
0x18008505a  mov     rcx, rdi
0x18008505d  mov     rdx, [rax+18h]
0x180085061  mov     rax, rbx
0x180085064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085069  mov     ebx, eax
0x18008506b  test    eax, eax
0x18008506d  jns     short loc_180085077
0x18008506f  mov     r9d, 0A5h
0x180085075  jmp     short loc_18008501E
0x180085077  cmp     [rbp+57h+var_A0], r12b
0x18008507b  jz      loc_1800851B9
0x180085081  mov     rdx, [r14+38h]
0x180085085  lea     rcx, [rbp+57h+hstringHeader]
0x180085089  mov     rdi, [rbp+57h+var_88]
0x18008508d  mov     [rbp+57h+var_60], r12
0x180085091  mov     [rbp+57h+var_C8], rdx
0x180085095  lea     rdx, [rbp+57h+var_C8]
0x180085099  mov     rax, [rdi]
0x18008509c  mov     rbx, [rax+40h]
0x1800850a0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800850a5  lea     r8, [rbp+57h+var_60]
0x1800850a9  mov     rcx, rdi
0x1800850ac  mov     rdx, [rax+18h]
0x1800850b0  mov     rax, rbx
0x1800850b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800850b8  mov     ebx, eax
0x1800850ba  test    eax, eax
0x1800850bc  jns     short loc_1800850DB
0x1800850be  mov     r9d, 0B0h
0x1800850c4  mov     edx, esi
0x1800850c6  mov     ecx, eax; int
0x1800850c8  call    Log_HREvent_62
0x1800850cd  lea     rcx, [rbp+57h+var_60]
0x1800850d1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800850d6  jmp     loc_180085027
0x1800850db  mov     rdi, [rbp+57h+var_60]
0x1800850df  xor     ecx, ecx; string
0x1800850e1  mov     [rbp+57h+string], r12
0x1800850e5  mov     rax, [rdi]
0x1800850e8  mov     rbx, [rax+50h]
0x1800850ec  call    cs:__imp_WindowsDeleteString
0x1800850f2  lea     rdx, off_1800FD678; "syncState"
0x1800850f9  mov     [rbp+57h+string], r12
0x1800850fd  lea     rcx, [rbp+57h+hstringHeader]
0x180085101  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180085106  lea     r8, [rbp+57h+string]
0x18008510a  mov     rcx, rdi
0x18008510d  mov     rdx, [rax+18h]
0x180085111  mov     rax, rbx
0x180085114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085119  mov     ebx, eax
0x18008511b  test    eax, eax
0x18008511d  jns     short loc_18008513E
0x18008511f  mov     r9d, 0B4h
0x180085125  mov     edx, esi
0x180085127  mov     ecx, eax; int
0x180085129  call    Log_HREvent_62
0x18008512e  mov     rcx, [rbp+57h+string]; string
0x180085132  call    cs:__imp_WindowsDeleteString
0x180085138  mov     [rbp+57h+string], r12
0x18008513c  jmp     short loc_1800850CD
0x18008513e  xorps   xmm0, xmm0
0x180085141  lea     rcx, [rbp+57h+var_58]
0x180085145  movups  [rbp+57h+var_58], xmm0
0x180085149  movups  [rbp+57h+var_48], xmm0
0x18008514d  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180085152  mov     rcx, [rbp+57h+string]; string
0x180085156  xor     edx, edx; length
0x180085158  call    cs:__imp_WindowsGetStringRawBuffer
0x18008515e  mov     rdx, rax
0x180085161  lea     rcx, [rbp+57h+var_58]
0x180085165  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18008516a  test    al, al
0x18008516c  jnz     short loc_18008518D
0x18008516e  mov     ebx, 8007000Eh
0x180085173  xor     edx, edx
0x180085175  mov     ecx, ebx; int
0x180085177  mov     r9d, 0B7h
0x18008517d  call    Log_HREvent_62
0x180085182  lea     rcx, [rbp+57h+var_58]
0x180085186  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18008518b  jmp     short loc_18008512E
0x18008518d  lea     rdx, [rbp+57h+var_58]
0x180085191  mov     rcx, r15
0x180085194  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180085199  lea     rcx, [rbp+57h+var_58]
0x18008519d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800851a2  mov     rcx, [rbp+57h+string]; string
0x1800851a6  call    cs:__imp_WindowsDeleteString
0x1800851ac  lea     rcx, [rbp+57h+var_60]
0x1800851b0  mov     [rbp+57h+string], r12
0x1800851b4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800851b9  lea     rcx, [rbp+57h+var_68]
0x1800851bd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800851c2  lea     rcx, [rbp+57h+var_88]
0x1800851c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800851cb  mov     rcx, [rbp+57h+var_98]
0x1800851cf  test    rcx, rcx
0x1800851d2  jz      short loc_1800851E4
0x1800851d4  mov     [rbp+57h+var_98], r12
0x1800851d8  mov     rax, [rcx]
0x1800851db  mov     rax, [rax+10h]
0x1800851df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800851e4  lea     rcx, [rbp+57h+var_90]
0x1800851e8  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x1800851ed  lea     rcx, [rbp+57h+var_80]
0x1800851f1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800851f6  lea     rcx, [rbp+57h+var_78]
0x1800851fa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800851ff  mov     ebx, r12d
0x180085202  lea     rcx, [rbp+57h+var_D0]
0x180085206  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18008520b  mov     eax, ebx
0x18008520d  mov     rcx, [rbp+57h+var_38]
0x180085211  xor     rcx, rsp; StackCookie
0x180085214  call    __security_check_cookie
0x180085219  add     rsp, 0D0h
0x180085220  pop     r15
0x180085222  pop     r14
0x180085224  pop     r12
0x180085226  pop     rdi
0x180085227  pop     rsi
0x180085228  pop     rbx
0x180085229  pop     rbp
0x18008522a  retn
```
