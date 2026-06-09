# ConversationAccessor::SetConversationSyncState(ChatServiceConversation *,ushort const *,int *)

- ea: `0x1800852d8`
- end: `0x1800859a1`
- name: `?SetConversationSyncState@ConversationAccessor@@QEAAJPEAVChatServiceConversation@@PEBGPEAH@Z`
- size: `1737`
- prototype: `__int64 __fastcall(ConversationAccessor *__hidden this, struct ChatServiceConversation *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180078a14`

## callees

- `0x180005c50`
- `0x18000b6d4`
- `0x180030bd0`
- `0x180046b18`
- `0x18006b108`
- `0x180084738`
- `0x1800847b8`
- `0x180084864`
- `0x1800848b4`
- `0x180085260`
- `0x1800852d8`
- `0x180085c88`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180085420`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180085604`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180085420`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180085604`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800858e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800858e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008588f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800858c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085908`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008588f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800858c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085908`

## string_xrefs

- `0x1800855e3`: `Windows.Data.Json.JsonValue`
- `0x1800853fb`: `Windows.Data.Json.JsonObject`
- `0x180085584`: `Windows.Data.Json.JsonObject`
- `0x18008563c`: `Windows.Data.Json.JsonObject`
- `0x18008569a`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall ConversationAccessor::SetConversationSyncState(
        ConversationAccessor *this,
        struct ChatServiceConversation *a2,
        const unsigned __int16 *a3,
        int *a4)
{
  int ConversationForParticipants; // eax
  unsigned int v7; // ebx
  __int64 v8; // rbx
  int v9; // eax
  int ActivationFactory; // eax
  char v11; // r8
  __int64 v12; // rcx
  void (*v13)(void); // rax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, PVOID, _QWORD); // rbx
  HSTRING_HEADER *v16; // rax
  int v17; // eax
  char v18; // r8
  __int64 v19; // rcx
  const WCHAR *v20; // rdx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, PVOID, char *); // rbx
  HSTRING_HEADER *v23; // rax
  char v24; // r8
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v26)(_QWORD, GUID *, __int64); // rbx
  HSTRING_HEADER *v27; // rax
  __int64 v28; // rcx
  int v29; // eax
  char v30; // r8
  int v31; // eax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v34; // rax
  int v35; // eax
  int v36; // eax
  char v37; // r8
  __int64 v38; // rsi
  __int64 v39; // rbx
  __int64 (__fastcall *v40)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v41; // rax
  int v42; // eax
  int v43; // eax
  char v44; // r8
  __int64 v45; // rsi
  __int64 v46; // rbx
  __int64 (__fastcall *v47)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v48; // rax
  int v49; // eax
  __int64 v50; // rdi
  __int64 (__fastcall *v51)(__int64, HSTRING *); // rbx
  int v52; // eax
  __int64 v53; // rdi
  __int64 (__fastcall *v54)(__int64, PCWSTR); // rbx
  PCWSTR StringRawBuffer; // rax
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-99h] BYREF
  __int64 v58; // [rsp+48h] [rbp-81h]
  __int64 v59; // [rsp+50h] [rbp-79h] BYREF
  const WCHAR *v60; // [rsp+58h] [rbp-71h] BYREF
  const WCHAR *v61; // [rsp+60h] [rbp-69h] BYREF
  __int64 (__fastcall ***v62)(_QWORD, GUID *, __int64); // [rsp+68h] [rbp-61h] BYREF
  __int64 (__fastcall ***v63)(_QWORD, GUID *, __int64); // [rsp+70h] [rbp-59h] BYREF
  char v64; // [rsp+78h] [rbp-51h] BYREF
  _BYTE v65[7]; // [rsp+79h] [rbp-50h] BYREF
  const WCHAR *v66; // [rsp+80h] [rbp-49h] BYREF
  __int64 v67; // [rsp+88h] [rbp-41h] BYREF
  __int64 v68; // [rsp+90h] [rbp-39h] BYREF
  __int64 v69; // [rsp+98h] [rbp-31h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v71; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v72; // [rsp+B0h] [rbp-19h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v74; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v75; // [rsp+C8h] [rbp-1h] BYREF
  __int64 v76; // [rsp+D0h] [rbp+7h] BYREF
  __int64 v77; // [rsp+D8h] [rbp+Fh] BYREF

  v61 = a3;
  *a4 = 0;
  v59 = 0;
  ConversationForParticipants = ConversationAccessor::_GetConversationForParticipants(this, (char *)a2 + 168, &v59);
  v7 = ConversationForParticipants;
  if ( ConversationForParticipants >= 0 )
  {
    v8 = v59;
    v68 = 0;
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 88LL))(v59, &v68) < 0 )
      goto LABEL_53;
    v67 = 0;
    *a4 = 1;
    ATL::CComQIPtr<ISmConversationPriv,&__s_GUID const _GUID_778e0f12_3c47_4b4a_92e7_975a59228204>::CComQIPtr<ISmConversationPriv,&__s_GUID const _GUID_778e0f12_3c47_4b4a_92e7_975a59228204>(
      &v67,
      v8);
    v66 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, const WCHAR **))(*(_QWORD *)v67 + 344LL))(v67, &v66);
    v7 = v9;
    if ( v9 < 0 )
    {
      Log_HREvent_62(v9);
LABEL_6:
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v66);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v67);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v68);
      goto LABEL_54;
    }
    v62 = 0;
    v63 = 0;
    if ( !v66 || !*v66 )
    {
      v58 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonObject",
        0x1Du,
        0x1Cu);
      v31 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v58, &v63);
      v7 = v31;
      if ( v31 < 0
        || (v58 = 0,
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"Windows.Data.Json.JsonObject",
              0x1Du,
              0x1Cu),
            v31 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v58, &v62),
            v7 = v31,
            v31 < 0) )
      {
        Log_HREvent_62(v31);
        goto LABEL_29;
      }
      goto LABEL_24;
    }
    v69 = 0;
    v58 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    ActivationFactory = RoGetActivationFactory(v58, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v69);
    v7 = ActivationFactory;
    if ( ActivationFactory < 0
      || (v14 = v69,
          v15 = *(__int64 (__fastcall **)(__int64, PVOID, _QWORD))(*(_QWORD *)v69 + 48LL),
          v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v66, v11),
          ActivationFactory = v15(v14, v16[1].Reserved.Reserved1, &v62),
          v7 = ActivationFactory,
          ActivationFactory < 0) )
    {
      Log_HREvent_62(ActivationFactory);
      v12 = v69;
      if ( !v69 )
      {
LABEL_29:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
        goto LABEL_6;
      }
      v69 = 0;
      v13 = *(void (**)(void))(*(_QWORD *)v12 + 16LL);
LABEL_12:
      v13();
      goto LABEL_29;
    }
    v76 = 0;
    v17 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
            &v62,
            (__int64)&v76);
    v7 = v17;
    if ( v17 >= 0 )
    {
      v20 = (const WCHAR *)*((_QWORD *)a2 + 7);
      v21 = v76;
      v64 = 0;
      v60 = v20;
      v22 = *(__int64 (__fastcall **)(__int64, PVOID, char *))(*(_QWORD *)v76 + 64LL);
      v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v60, v18);
      v17 = v22(v21, v23[1].Reserved.Reserved1, &v64);
      v7 = v17;
      if ( v17 >= 0 )
      {
        if ( v64 )
        {
          v25 = v62;
          v60 = (const WCHAR *)*((_QWORD *)a2 + 7);
          v26 = (*v62)[8];
          v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v60, v24);
          v17 = v26(v25, (GUID *)v27[1].Reserved.Reserved1, (__int64)&v63);
          v7 = v17;
          if ( v17 < 0 )
            goto LABEL_15;
          goto LABEL_22;
        }
        v58 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Data.Json.JsonObject",
          0x1Du,
          0x1Cu);
        v17 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v58, &v63);
        v7 = v17;
        if ( v17 >= 0 )
        {
LABEL_22:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
          v28 = v69;
          if ( v69 )
          {
            v69 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          }
LABEL_24:
          v70 = 0;
          v58 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"Windows.Data.Json.JsonValue",
            0x1Cu,
            0x1Bu);
          v29 = RoGetActivationFactory(v58, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v70);
          v7 = v29;
          if ( v29 < 0 )
          {
            Log_HREvent_62(v29);
LABEL_26:
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
            goto LABEL_29;
          }
          v32 = v70;
          v71 = 0;
          v33 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v70 + 80LL);
          v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v61, v30);
          v35 = v33(v32, v34[1].Reserved.Reserved1, &v71);
          v7 = v35;
          if ( v35 < 0 )
          {
            Log_HREvent_62(v35);
LABEL_34:
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
            goto LABEL_26;
          }
          v72 = 0;
          v36 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
                  &v63,
                  (__int64)&v72);
          v7 = v36;
          if ( v36 < 0
            || (v38 = v72,
                v39 = v71,
                v65[0] = 0,
                v40 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v72 + 80LL),
                v41 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                        &hstringHeader,
                        (const WCHAR **)off_1800FD678,
                        v37),
                v36 = v40(v38, v41[1].Reserved.Reserved1, v39, v65),
                v7 = v36,
                v36 < 0) )
          {
            Log_HREvent_62(v36);
LABEL_37:
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
            goto LABEL_34;
          }
          v74 = 0;
          v42 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                  &v63,
                  (__int64)&v74);
          v7 = v42;
          if ( v42 < 0 )
          {
            Log_HREvent_62(v42);
LABEL_41:
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
            goto LABEL_37;
          }
          v75 = 0;
          v43 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
                  &v62,
                  (__int64)&v75);
          v7 = v43;
          if ( v43 < 0
            || (v45 = v75,
                v46 = v74,
                v61 = (const WCHAR *)*((_QWORD *)a2 + 7),
                v47 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v75 + 80LL),
                v48 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v61, v44),
                v43 = v47(v45, v48[1].Reserved.Reserved1, v46, v65),
                v7 = v43,
                v43 < 0) )
          {
            Log_HREvent_62(v43);
LABEL_44:
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
            goto LABEL_41;
          }
          v77 = 0;
          v49 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                  &v62,
                  (__int64)&v77);
          v7 = v49;
          if ( v49 < 0 )
          {
            Log_HREvent_62(v49);
LABEL_48:
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
            goto LABEL_44;
          }
          v50 = v77;
          string = 0;
          v51 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v77 + 56LL);
          WindowsDeleteString(0);
          string = 0;
          v52 = v51(v50, &string);
          v7 = v52;
          if ( v52 < 0
            || (v53 = v67,
                v54 = *(__int64 (__fastcall **)(__int64, PCWSTR))(*(_QWORD *)v67 + 352LL),
                StringRawBuffer = WindowsGetStringRawBuffer(string, 0),
                v52 = v54(v53, StringRawBuffer),
                v7 = v52,
                v52 < 0) )
          {
            Log_HREvent_62(v52);
            WindowsDeleteString(string);
            string = 0;
            goto LABEL_48;
          }
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
          tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v66);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v67);
LABEL_53:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v68);
          v7 = 0;
          goto LABEL_54;
        }
      }
    }
LABEL_15:
    Log_HREvent_62(v17);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
    v19 = v69;
    if ( !v69 )
      goto LABEL_29;
    v69 = 0;
    v13 = *(void (**)(void))(*(_QWORD *)v19 + 16LL);
    goto LABEL_12;
  }
  Log_HREvent_62(ConversationForParticipants);
LABEL_54:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v59);
  return v7;
}

```

## disassembly

```asm
0x1800852d8  push    rbp
0x1800852da  push    rbx
0x1800852db  push    rsi
0x1800852dc  push    rdi
0x1800852dd  push    r12
0x1800852df  push    r13
0x1800852e1  push    r14
0x1800852e3  lea     rbp, [rsp-27h]
0x1800852e8  sub     rsp, 0F0h
0x1800852ef  mov     rax, cs:__security_cookie
0x1800852f6  xor     rax, rsp
0x1800852f9  mov     [rbp+57h+var_40], rax
0x1800852fd  mov     r13, rdx
0x180085300  mov     [rbp+57h+var_C0], r8
0x180085304  xor     r12d, r12d
0x180085307  lea     r8, [rbp+57h+var_D0]
0x18008530b  add     rdx, 0A8h
0x180085312  mov     [r9], r12d
0x180085315  mov     [rbp+57h+var_D0], r12
0x180085319  mov     rdi, r9
0x18008531c  call    ?_GetConversationForParticipants@ConversationAccessor@@AEAAJPEBV?$vector@V?$CComPtr@VChatServiceParticipant@@@ATL@@V?$allocator@V?$CComPtr@VChatServiceParticipant@@@ATL@@@utl@@@utl@@PEAPEAUISmConversation@@@Z; ConversationAccessor::_GetConversationForParticipants(utl::vector<ATL::CComPtr<ChatServiceParticipant>,utl::allocator<ATL::CComPtr<ChatServiceParticipant>>> const *,ISmConversation * *)
0x180085321  mov     ebx, eax
0x180085323  test    eax, eax
0x180085325  jns     short loc_18008533E
0x180085327  lea     edx, [r12+1]
0x18008532c  mov     r9d, 0C4h
0x180085332  mov     ecx, eax; int
0x180085334  call    Log_HREvent_62
0x180085339  jmp     loc_180085978
0x18008533e  mov     rbx, [rbp+57h+var_D0]
0x180085342  lea     rdx, [rbp+57h+var_90]
0x180085346  mov     [rbp+57h+var_90], r12
0x18008534a  mov     rcx, rbx
0x18008534d  mov     rax, [rbx]
0x180085350  mov     rax, [rax+58h]
0x180085354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085359  test    eax, eax
0x18008535b  js      loc_18008596C
0x180085361  mov     r14d, 1
0x180085367  mov     [rbp+57h+var_98], r12
0x18008536b  mov     rdx, rbx
0x18008536e  mov     [rdi], r14d
0x180085371  lea     rcx, [rbp+57h+var_98]
0x180085375  call    ??0?$CComQIPtr@UISmConversationPriv@@$1?_GUID_778e0f12_3c47_4b4a_92e7_975a59228204@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ISmConversationPriv,&__s_GUID const _GUID_778e0f12_3c47_4b4a_92e7_975a59228204>::CComQIPtr<ISmConversationPriv,&__s_GUID const _GUID_778e0f12_3c47_4b4a_92e7_975a59228204>(IUnknown *)
0x18008537a  mov     rcx, [rbp+57h+var_98]
0x18008537e  lea     rdx, [rbp+57h+var_A0]
0x180085382  mov     [rbp+57h+var_A0], r12
0x180085386  mov     rax, [rcx]
0x180085389  mov     rax, [rax+158h]
0x180085390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085395  mov     ebx, eax
0x180085397  test    eax, eax
0x180085399  jns     short loc_1800853CB
0x18008539b  mov     r9d, 0D2h
0x1800853a1  mov     edx, r14d
0x1800853a4  mov     ecx, eax; int
0x1800853a6  call    Log_HREvent_62
0x1800853ab  lea     rcx, [rbp+57h+var_A0]
0x1800853af  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x1800853b4  lea     rcx, [rbp+57h+var_98]
0x1800853b8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800853bd  lea     rcx, [rbp+57h+var_90]
0x1800853c1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800853c6  jmp     loc_180085978
0x1800853cb  mov     rax, [rbp+57h+var_A0]
0x1800853cf  mov     [rbp+57h+var_B8], r12
0x1800853d3  mov     [rbp+57h+var_B0], r12
0x1800853d7  test    rax, rax
0x1800853da  jz      loc_18008562F
0x1800853e0  cmp     r12w, [rax]
0x1800853e4  jz      loc_18008562F
0x1800853ea  mov     esi, 1Ch
0x1800853ef  mov     [rbp+57h+var_88], r12
0x1800853f3  mov     r9d, esi; unsigned int
0x1800853f6  mov     [rsp+120h+var_D8], r12
0x1800853fb  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180085402  lea     rcx, [rsp+120h+hstringHeader]; hstringHeader
0x180085407  lea     r8d, [rsi+1]; unsigned int
0x18008540b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180085410  mov     rcx, [rsp+120h+var_D8]
0x180085415  lea     r8, [rbp+57h+var_88]
0x180085419  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x180085420  call    cs:__imp_RoGetActivationFactory
0x180085426  mov     ebx, eax
0x180085428  test    eax, eax
0x18008542a  jns     short loc_18008545E
0x18008542c  mov     r9d, 0E6h
0x180085432  mov     edx, r14d
0x180085435  mov     ecx, eax; int
0x180085437  call    Log_HREvent_62
0x18008543c  mov     rcx, [rbp+57h+var_88]
0x180085440  test    rcx, rcx
0x180085443  jz      loc_180085675
0x180085449  mov     [rbp+57h+var_88], r12
0x18008544d  mov     rdx, [rcx]
0x180085450  mov     rax, [rdx+10h]
0x180085454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085459  jmp     loc_180085675
0x18008545e  mov     rdi, [rbp+57h+var_88]
0x180085462  lea     rdx, [rbp+57h+var_A0]
0x180085466  lea     rcx, [rsp+120h+hstringHeader]
0x18008546b  mov     rax, [rdi]
0x18008546e  mov     rbx, [rax+30h]
0x180085472  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180085477  lea     r8, [rbp+57h+var_B8]
0x18008547b  mov     rcx, rdi
0x18008547e  mov     rdx, [rax+18h]
0x180085482  mov     rax, rbx
0x180085485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008548a  mov     ebx, eax
0x18008548c  test    eax, eax
0x18008548e  jns     short loc_180085498
0x180085490  mov     r9d, 0E9h
0x180085496  jmp     short loc_180085432
0x180085498  lea     rdx, [rbp+57h+var_50]
0x18008549c  mov     [rbp+57h+var_50], r12
0x1800854a0  lea     rcx, [rbp+57h+var_B8]
0x1800854a4  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x1800854a9  mov     ebx, eax
0x1800854ab  test    eax, eax
0x1800854ad  jns     short loc_1800854E5
0x1800854af  mov     r9d, 0ECh
0x1800854b5  mov     edx, r14d
0x1800854b8  mov     ecx, eax; int
0x1800854ba  call    Log_HREvent_62
0x1800854bf  lea     rcx, [rbp+57h+var_50]
0x1800854c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800854c8  mov     rcx, [rbp+57h+var_88]
0x1800854cc  test    rcx, rcx
0x1800854cf  jz      loc_180085675
0x1800854d5  mov     [rbp+57h+var_88], r12
0x1800854d9  mov     rax, [rcx]
0x1800854dc  mov     rax, [rax+10h]
0x1800854e0  jmp     loc_180085454
0x1800854e5  mov     rdx, [r13+38h]
0x1800854e9  lea     rcx, [rsp+120h+hstringHeader]
0x1800854ee  mov     rdi, [rbp+57h+var_50]
0x1800854f2  mov     [rbp+57h+var_A8], r12b
0x1800854f6  mov     [rbp+57h+var_C8], rdx
0x1800854fa  lea     rdx, [rbp+57h+var_C8]
0x1800854fe  mov     rax, [rdi]
0x180085501  mov     rbx, [rax+40h]
0x180085505  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18008550a  lea     r8, [rbp+57h+var_A8]
0x18008550e  mov     rcx, rdi
0x180085511  mov     rdx, [rax+18h]
0x180085515  mov     rax, rbx
0x180085518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008551d  mov     ebx, eax
0x18008551f  test    eax, eax
0x180085521  jns     short loc_18008552B
0x180085523  mov     r9d, 0F0h
0x180085529  jmp     short loc_1800854B5
0x18008552b  lea     rcx, [rsp+120h+hstringHeader]; hstringHeader
0x180085530  cmp     [rbp+57h+var_A8], r12b
0x180085534  jz      short loc_180085576
0x180085536  mov     rdx, [r13+38h]
0x18008553a  mov     rdi, [rbp+57h+var_B8]
0x18008553e  mov     [rbp+57h+var_C8], rdx
0x180085542  lea     rdx, [rbp+57h+var_C8]
0x180085546  mov     rax, [rdi]
0x180085549  mov     rbx, [rax+40h]
0x18008554d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180085552  lea     r8, [rbp+57h+var_B0]
0x180085556  mov     rcx, rdi
0x180085559  mov     rdx, [rax+18h]
0x18008555d  mov     rax, rbx
0x180085560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085565  mov     ebx, eax
0x180085567  test    eax, eax
0x180085569  jns     short loc_1800855AF
0x18008556b  mov     r9d, 0F5h
0x180085571  jmp     loc_1800854B5
0x180085576  mov     r9d, esi; unsigned int
0x180085579  mov     [rsp+120h+var_D8], r12
0x18008557e  mov     r8d, 1Dh; unsigned int
0x180085584  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18008558b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180085590  mov     rcx, [rsp+120h+var_D8]
0x180085595  lea     rdx, [rbp+57h+var_B0]
0x180085599  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18008559e  mov     ebx, eax
0x1800855a0  test    eax, eax
0x1800855a2  jns     short loc_1800855AF
0x1800855a4  mov     r9d, 0FCh
0x1800855aa  jmp     loc_1800854B5
0x1800855af  lea     rcx, [rbp+57h+var_50]
0x1800855b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800855b8  mov     rcx, [rbp+57h+var_88]
0x1800855bc  test    rcx, rcx
0x1800855bf  jz      short loc_1800855D1
0x1800855c1  mov     [rbp+57h+var_88], r12
0x1800855c5  mov     rax, [rcx]
0x1800855c8  mov     rax, [rax+10h]
0x1800855cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800855d1  mov     r9d, 1Bh; unsigned int
0x1800855d7  mov     [rbp+57h+var_80], r12
0x1800855db  mov     r8d, esi; unsigned int
0x1800855de  mov     [rsp+120h+var_D8], r12
0x1800855e3  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800855ea  lea     rcx, [rsp+120h+hstringHeader]; hstringHeader
0x1800855ef  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800855f4  mov     rcx, [rsp+120h+var_D8]
0x1800855f9  lea     r8, [rbp+57h+var_80]
0x1800855fd  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180085604  call    cs:__imp_RoGetActivationFactory
0x18008560a  mov     ebx, eax
0x18008560c  test    eax, eax
0x18008560e  jns     loc_1800856CB
0x180085614  mov     r9d, 103h
0x18008561a  mov     edx, r14d
0x18008561d  mov     ecx, eax; int
0x18008561f  call    Log_HREvent_62
0x180085624  lea     rcx, [rbp+57h+var_80]
0x180085628  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008562d  jmp     short loc_180085675
0x18008562f  mov     esi, 1Ch
0x180085634  mov     [rsp+120h+var_D8], r12
0x180085639  mov     r9d, esi; unsigned int
0x18008563c  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180085643  lea     rcx, [rsp+120h+hstringHeader]; hstringHeader
0x180085648  lea     r8d, [rsi+1]; unsigned int
0x18008564c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180085651  mov     rcx, [rsp+120h+var_D8]
0x180085656  lea     rdx, [rbp+57h+var_B0]
0x18008565a  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18008565f  mov     ebx, eax
0x180085661  test    eax, eax
0x180085663  jns     short loc_18008568C
0x180085665  mov     r9d, 0DCh
0x18008566b  mov     edx, r14d
0x18008566e  mov     ecx, eax; int
0x180085670  call    Log_HREvent_62
0x180085675  lea     rcx, [rbp+57h+var_B0]
0x180085679  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008567e  lea     rcx, [rbp+57h+var_B8]
0x180085682  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085687  jmp     loc_1800853AB
0x18008568c  mov     r9d, esi; unsigned int
0x18008568f  mov     [rsp+120h+var_D8], r12
0x180085694  mov     r8d, 1Dh; unsigned int
0x18008569a  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800856a1  lea     rcx, [rsp+120h+hstringHeader]; hstringHeader
0x1800856a6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800856ab  mov     rcx, [rsp+120h+var_D8]
0x1800856b0  lea     rdx, [rbp+57h+var_B8]
0x1800856b4  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x1800856b9  mov     ebx, eax
0x1800856bb  test    eax, eax
0x1800856bd  jns     loc_1800855D1
0x1800856c3  mov     r9d, 0DFh
0x1800856c9  jmp     short loc_18008566B
0x1800856cb  mov     rdi, [rbp+57h+var_80]
0x1800856cf  lea     rdx, [rbp+57h+var_C0]
0x1800856d3  mov     [rbp+57h+var_78], r12
0x1800856d7  lea     rcx, [rsp+120h+hstringHeader]
0x1800856dc  mov     rax, [rdi]
0x1800856df  mov     rbx, [rax+50h]
0x1800856e3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800856e8  lea     r8, [rbp+57h+var_78]
0x1800856ec  mov     rcx, rdi
0x1800856ef  mov     rdx, [rax+18h]
0x1800856f3  mov     rax, rbx
0x1800856f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800856fb  mov     ebx, eax
0x1800856fd  test    eax, eax
0x1800856ff  jns     short loc_18008571F
0x180085701  mov     r9d, 106h
0x180085707  mov     edx, r14d
0x18008570a  mov     ecx, eax; int
0x18008570c  call    Log_HREvent_62
0x180085711  lea     rcx, [rbp+57h+var_78]
0x180085715  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008571a  jmp     loc_180085624
0x18008571f  lea     rdx, [rbp+57h+var_70]
0x180085723  mov     [rbp+57h+var_70], r12
0x180085727  lea     rcx, [rbp+57h+var_B0]
0x18008572b  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x180085730  mov     ebx, eax
0x180085732  test    eax, eax
0x180085734  jns     short loc_180085751
0x180085736  mov     r9d, 109h
0x18008573c  mov     edx, r14d
0x18008573f  mov     ecx, eax; int
0x180085741  call    Log_HREvent_62
0x180085746  lea     rcx, [rbp+57h+var_70]
0x18008574a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008574f  jmp     short loc_180085711
0x180085751  mov     rsi, [rbp+57h+var_70]
0x180085755  lea     rdx, off_1800FD678; "syncState"
0x18008575c  mov     rbx, [rbp+57h+var_78]
0x180085760  lea     rcx, [rsp+120h+hstringHeader]
0x180085765  mov     [rbp+57h+var_A7], r12b
0x180085769  mov     rax, [rsi]
0x18008576c  mov     rdi, [rax+50h]
0x180085770  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180085775  lea     r9, [rbp+57h+var_A7]
0x180085779  mov     r8, rbx
0x18008577c  mov     rcx, rsi
0x18008577f  mov     rdx, [rax+18h]
  ... truncated ...
```
