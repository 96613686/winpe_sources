# _ReadCheckpointAbandonmentRules(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *)

- ea: `0x1800292b0`
- end: `0x180029917`
- name: `?_ReadCheckpointAbandonmentRules@@YAJPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@@Z`
- size: `1639`
- prototype: `__int64 __fastcall(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b21c`
- `0x18002e654`

## callees

- `0x180003450`
- `0x18000760c`
- `0x18000912c`
- `0x18000b48c`
- `0x180011044`
- `0x180012f10`
- `0x18001f710`
- `0x18001f770`
- `0x18001f81c`
- `0x180020714`
- `0x1800292b0`
- `0x18002a7e8`
- `0x180031d98`
- `0x180031eac`
- `0x180031f14`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002939a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029474`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800294e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029586`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800295d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002961e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029650`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800296df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029711`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800297a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002987e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800298c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002939a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029474`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800294e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029586`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800295d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002961e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029650`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800296df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029711`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800297a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002987e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800298c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800293cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002967a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800293cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002967a`

## string_xrefs

- `0x18002936a`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180029401`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180029454`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x1800294c3`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18002955b`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180029607`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x1800296c8`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18002975e`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x1800296a6`: `systemAttemptCountThreshold`
- `0x1800293f4`: `_ReadCheckpointAbandonmentRules`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall _ReadCheckpointAbandonmentRules(
        struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 (__fastcall *v4)(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *, PVOID, struct IInspectable **); // rbx
  char v5; // r8
  HSTRING_HEADER *v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  int v10; // eax
  HSTRING v11; // rbx
  struct IInspectable *v12; // rsi
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rdi
  int v14; // eax
  unsigned int v15; // edi
  int v16; // eax
  __int64 v17; // rcx
  unsigned int v18; // edi
  unsigned int v19; // r15d
  __m128i si128; // xmm6
  struct IInspectable *v21; // rsi
  HRESULT (__stdcall *v22)(IInspectable *, const IID *const, void **); // rdi
  int v23; // eax
  unsigned int v24; // edi
  int NamedValue; // eax
  unsigned int v26; // edi
  PCWSTR StringRawBuffer; // rax
  __int64 v28; // r8
  int v29; // eax
  unsigned int v30; // edi
  int v31; // eax
  unsigned int v32; // edi
  __int64 v33; // rdx
  int v34; // [rsp+20h] [rbp-D8h]
  struct IInspectable *v35; // [rsp+50h] [rbp-A8h] BYREF
  HSTRING v36; // [rsp+58h] [rbp-A0h] BYREF
  struct Windows::Data::Json::IJsonObject *v37; // [rsp+60h] [rbp-98h] BYREF
  __int64 v38; // [rsp+68h] [rbp-90h] BYREF
  unsigned int v39; // [rsp+70h] [rbp-88h] BYREF
  __int128 v40; // [rsp+78h] [rbp-80h] BYREF
  __int64 v41; // [rsp+88h] [rbp-70h]
  HSTRING string; // [rsp+90h] [rbp-68h] BYREF
  __int128 v43; // [rsp+98h] [rbp-60h] BYREF
  __m128i v44; // [rsp+A8h] [rbp-50h]
  unsigned int v45[2]; // [rsp+B8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  if ( qword_18006A540 != qword_18006A548 )
  {
    std::_Destroy_range<std::allocator<CheckpointAbandonmentRule>>(qword_18006A540, qword_18006A548, a3);
    qword_18006A548 = qword_18006A540;
  }
  v40 = 0;
  v41 = 0;
  v35 = 0;
  v4 = *(__int64 (__fastcall **)(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *, PVOID, struct IInspectable **))(*(_QWORD *)a1 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
         (HSTRING_HEADER *)&v43,
         (const WCHAR **)off_180048588,
         v5);
  v7 = v4(a1, v6[1].Reserved.Reserved1, &v35);
  v8 = v7;
  if ( v7 >= 0 )
  {
    WindowsDeleteString(0);
    string = 0;
    v10 = Json_Stringify(v35, &string);
    v11 = string;
    if ( v10 >= 0 )
    {
      WindowsGetStringRawBuffer(string, 0);
      LogMessage(
        4u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        0x10BCu,
        "_ReadCheckpointAbandonmentRules",
        -1,
        L"CheckpointAbandonmentRules fetched from OneSettings payload: %s",
        0,
        0);
    }
    v38 = 0;
    v12 = v35;
    QueryInterface = v35->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    v14 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
            v12,
            &GUID_d44662bc_dce3_59a8_9272_4b210f33908b,
            &v38);
    v15 = v14;
    if ( v14 >= 0 )
    {
      v39 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v38 + 56LL))(v38, &v39);
      v18 = v16;
      if ( v16 >= 0 )
      {
        v19 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        while ( v19 < v39 )
        {
          v37 = 0;
          v21 = v35;
          v22 = v35->lpVtbl[1].QueryInterface;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
          v23 = ((__int64 (__fastcall *)(struct IInspectable *, _QWORD, struct Windows::Data::Json::IJsonObject **))v22)(
                  v21,
                  v19,
                  &v37);
          v24 = v23;
          if ( v23 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x10C8,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
              (const char *)(unsigned int)v23,
              v34);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
            WindowsDeleteString(v11);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
            std::vector<CheckpointAbandonmentRule>::_Tidy(&v40);
            return v24;
          }
          v43 = 0;
          v44 = si128;
          LOWORD(v43) = 0;
          *(_QWORD *)v45 = 0;
          v36 = 0;
          WindowsDeleteString(0);
          v36 = 0;
          NamedValue = Json_GetNamedValue(v37, L"callerApplicationIdKeyword", &v36);
          v26 = NamedValue;
          if ( NamedValue < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x10CD,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
              (const char *)(unsigned int)NamedValue,
              v34);
            WindowsDeleteString(v36);
            v36 = 0;
            std::wstring::_Tidy_deallocate(&v43);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
            WindowsDeleteString(v11);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
            std::vector<CheckpointAbandonmentRule>::_Tidy(&v40);
            return v26;
          }
          StringRawBuffer = WindowsGetStringRawBuffer(v36, 0);
          v28 = -1;
          do
            ++v28;
          while ( StringRawBuffer[v28] );
          std::wstring::_Assign<unsigned short>(&v43, StringRawBuffer);
          v29 = Json_GetNamedValue(v37, L"systemAttemptCountThreshold", v45);
          v30 = v29;
          if ( v29 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x10D0,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
              (const char *)(unsigned int)v29,
              v34);
            WindowsDeleteString(v36);
            v36 = 0;
            std::wstring::_Tidy_deallocate(&v43);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
            WindowsDeleteString(v11);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
            std::vector<CheckpointAbandonmentRule>::_Tidy(&v40);
            return v30;
          }
          v31 = Json_GetNamedValue(v37, L"creationTimestampThresholdInDays", &v45[1]);
          v32 = v31;
          if ( v31 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x10D1,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
              (const char *)(unsigned int)v31,
              v34);
            WindowsDeleteString(v36);
            v36 = 0;
            std::wstring::_Tidy_deallocate(&v43);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
            WindowsDeleteString(v11);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
            std::vector<CheckpointAbandonmentRule>::_Tidy(&v40);
            return v32;
          }
          v33 = *((_QWORD *)&v40 + 1);
          if ( *((_QWORD *)&v40 + 1) == v41 )
          {
            std::vector<CheckpointAbandonmentRule>::_Emplace_reallocate<CheckpointAbandonmentRule>(
              &v40,
              *((_QWORD *)&v40 + 1),
              &v43);
          }
          else
          {
            **((_OWORD **)&v40 + 1) = 0;
            *(_QWORD *)(v33 + 16) = 0;
            *(_QWORD *)(v33 + 24) = 0;
            *(_OWORD *)v33 = v43;
            *(__m128i *)(v33 + 16) = v44;
            v44 = si128;
            LOWORD(v43) = 0;
            *(_DWORD *)(v33 + 32) = v45[0];
            *(_DWORD *)(v33 + 36) = v45[1];
            *((_QWORD *)&v40 + 1) += 40LL;
          }
          WindowsDeleteString(v36);
          v36 = 0;
          std::wstring::_Tidy_deallocate(&v43);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
          ++v19;
        }
        std::vector<CheckpointAbandonmentRule>::operator=(v17, &v40);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        WindowsDeleteString(v11);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
        std::vector<CheckpointAbandonmentRule>::_Tidy(&v40);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10C3,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          (const char *)(unsigned int)v16,
          v34);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        WindowsDeleteString(v11);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
        std::vector<CheckpointAbandonmentRule>::_Tidy(&v40);
        return v18;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10C0,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        (const char *)(unsigned int)v14,
        v34);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      WindowsDeleteString(v11);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
      std::vector<CheckpointAbandonmentRule>::_Tidy(&v40);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10B7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      (const char *)(unsigned int)v7,
      v34);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    std::vector<CheckpointAbandonmentRule>::_Tidy(&v40);
    return v8;
  }
}

```

## disassembly

```asm
0x1800292b0  mov     rax, rsp
0x1800292b3  mov     [rax+10h], rbx
0x1800292b7  mov     [rax+18h], rsi
0x1800292bb  push    rdi
0x1800292bc  push    r12
0x1800292be  push    r15
0x1800292c0  sub     rsp, 0E0h
0x1800292c7  movaps  xmmword ptr [rax-28h], xmm6
0x1800292cb  mov     rax, cs:__security_cookie
0x1800292d2  xor     rax, rsp
0x1800292d5  mov     [rsp+0F8h+var_38], rax
0x1800292dd  mov     rdi, rcx
0x1800292e0  mov     rdx, cs:qword_18006A548
0x1800292e7  mov     rcx, cs:qword_18006A540
0x1800292ee  cmp     rcx, rdx
0x1800292f1  jz      short loc_180029306
0x1800292f3  call    ??$_Destroy_range@V?$allocator@UCheckpointAbandonmentRule@@@std@@@std@@YAXPEAUCheckpointAbandonmentRule@@QEAU1@AEAV?$allocator@UCheckpointAbandonmentRule@@@0@@Z; std::_Destroy_range<std::allocator<CheckpointAbandonmentRule>>(CheckpointAbandonmentRule *,CheckpointAbandonmentRule * const,std::allocator<CheckpointAbandonmentRule> &)
0x1800292f8  mov     rax, cs:qword_18006A540
0x1800292ff  mov     cs:qword_18006A548, rax
0x180029306  xorps   xmm0, xmm0
0x180029309  movdqu  [rsp+0F8h+var_80], xmm0
0x18002930f  xor     r12d, r12d
0x180029312  mov     [rsp+0F8h+var_70], r12
0x18002931a  mov     [rsp+0F8h+var_A8], r12
0x18002931f  mov     rax, [rdi]
0x180029322  mov     rbx, [rax+40h]
0x180029326  lea     rcx, [rsp+0F8h+var_A8]
0x18002932b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029330  lea     rdx, off_180048588; "CHECKPOINTABANDONMENTRULES"
0x180029337  lea     rcx, [rsp+0F8h+var_60]
0x18002933f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180029344  nop
0x180029345  lea     r8, [rsp+0F8h+var_A8]
0x18002934a  mov     rdx, [rax+18h]
0x18002934e  mov     rcx, rdi
0x180029351  mov     rax, rbx
0x180029354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029359  mov     ebx, eax
0x18002935b  test    eax, eax
0x18002935d  jns     short loc_180029398
0x18002935f  mov     rcx, [rsp+0F8h]; this
0x180029367  mov     r9d, eax; char *
0x18002936a  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180029371  mov     edx, 10B7h; void *
0x180029376  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002937b  nop
0x18002937c  lea     rcx, [rsp+0F8h+var_A8]
0x180029381  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029386  nop
0x180029387  lea     rcx, [rsp+0F8h+var_80]
0x18002938c  call    ?_Tidy@?$vector@UCheckpointAbandonmentRule@@V?$allocator@UCheckpointAbandonmentRule@@@std@@@std@@AEAAXXZ; std::vector<CheckpointAbandonmentRule>::_Tidy(void)
0x180029391  mov     eax, ebx
0x180029393  jmp     loc_1800298E8
0x180029398  xor     ecx, ecx; string
0x18002939a  call    cs:__imp_WindowsDeleteString
0x1800293a0  mov     [rsp+0F8h+string], r12
0x1800293a8  lea     rdx, [rsp+0F8h+string]; HSTRING *
0x1800293b0  mov     rcx, [rsp+0F8h+var_A8]; struct IInspectable *
0x1800293b5  call    ?Json_Stringify@@YAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z; Json_Stringify(IInspectable *,HSTRING__ * *)
0x1800293ba  mov     rbx, [rsp+0F8h+string]
0x1800293c2  test    eax, eax
0x1800293c4  js      short loc_180029412
0x1800293c6  xor     edx, edx; length
0x1800293c8  mov     rcx, rbx; string
0x1800293cb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800293d1  mov     [rsp+0F8h+var_B8], rax
0x1800293d6  mov     [rsp+0F8h+var_C0], r12; unsigned __int16 *
0x1800293db  mov     [rsp+0F8h+var_C8], r12; char *
0x1800293e0  lea     rax, aCheckpointaban; "CheckpointAbandonmentRules fetched from"...
0x1800293e7  mov     [rsp+0F8h+var_D0], rax; unsigned __int16 *
0x1800293ec  mov     [rsp+0F8h+var_D8], 0FFFFFFFFh; int
0x1800293f4  lea     r9, aReadcheckpoint; "_ReadCheckpointAbandonmentRules"
0x1800293fb  mov     r8d, 10BCh; unsigned int
0x180029401  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180029408  mov     ecx, 4; unsigned int
0x18002940d  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180029412  mov     [rsp+0F8h+var_90], r12
0x180029417  mov     rsi, [rsp+0F8h+var_A8]
0x18002941c  mov     rax, [rsi]
0x18002941f  mov     rdi, [rax]
0x180029422  lea     rcx, [rsp+0F8h+var_90]
0x180029427  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002942c  lea     r8, [rsp+0F8h+var_90]
0x180029431  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x180029438  mov     rcx, rsi
0x18002943b  mov     rax, rdi
0x18002943e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029443  mov     edi, eax
0x180029445  test    eax, eax
0x180029447  jns     short loc_180029497
0x180029449  mov     rcx, [rsp+0F8h]; this
0x180029451  mov     r9d, eax; char *
0x180029454  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18002945b  mov     edx, 10C0h; void *
0x180029460  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029465  nop
0x180029466  lea     rcx, [rsp+0F8h+var_90]
0x18002946b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029470  nop
0x180029471  mov     rcx, rbx; string
0x180029474  call    cs:__imp_WindowsDeleteString
0x18002947a  nop
0x18002947b  lea     rcx, [rsp+0F8h+var_A8]
0x180029480  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029485  nop
0x180029486  lea     rcx, [rsp+0F8h+var_80]
0x18002948b  call    ?_Tidy@?$vector@UCheckpointAbandonmentRule@@V?$allocator@UCheckpointAbandonmentRule@@@std@@@std@@AEAAXXZ; std::vector<CheckpointAbandonmentRule>::_Tidy(void)
0x180029490  mov     eax, edi
0x180029492  jmp     loc_1800298E8
0x180029497  mov     [rsp+0F8h+var_88], r12d
0x18002949c  mov     rcx, [rsp+0F8h+var_90]
0x1800294a1  mov     rax, [rcx]
0x1800294a4  lea     rdx, [rsp+0F8h+var_88]
0x1800294a9  mov     rax, [rax+38h]
0x1800294ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294b2  mov     edi, eax
0x1800294b4  test    eax, eax
0x1800294b6  jns     short loc_180029506
0x1800294b8  mov     rcx, [rsp+0F8h]; this
0x1800294c0  mov     r9d, eax; char *
0x1800294c3  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x1800294ca  mov     edx, 10C3h; void *
0x1800294cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800294d4  nop
0x1800294d5  lea     rcx, [rsp+0F8h+var_90]
0x1800294da  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800294df  nop
0x1800294e0  mov     rcx, rbx; string
0x1800294e3  call    cs:__imp_WindowsDeleteString
0x1800294e9  nop
0x1800294ea  lea     rcx, [rsp+0F8h+var_A8]
0x1800294ef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800294f4  nop
0x1800294f5  lea     rcx, [rsp+0F8h+var_80]
0x1800294fa  call    ?_Tidy@?$vector@UCheckpointAbandonmentRule@@V?$allocator@UCheckpointAbandonmentRule@@@std@@@std@@AEAAXXZ; std::vector<CheckpointAbandonmentRule>::_Tidy(void)
0x1800294ff  mov     eax, edi
0x180029501  jmp     loc_1800298E8
0x180029506  mov     r15d, r12d
0x180029509  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180029511  cmp     r15d, [rsp+0F8h+var_88]
0x180029516  jnb     loc_1800298A9
0x18002951c  mov     [rsp+0F8h+var_98], r12
0x180029521  mov     rsi, [rsp+0F8h+var_A8]
0x180029526  mov     rax, [rsi]
0x180029529  mov     rdi, [rax+30h]
0x18002952d  lea     rcx, [rsp+0F8h+var_98]
0x180029532  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029537  lea     r8, [rsp+0F8h+var_98]
0x18002953c  mov     edx, r15d
0x18002953f  mov     rcx, rsi
0x180029542  mov     rax, rdi
0x180029545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002954a  mov     edi, eax
0x18002954c  test    eax, eax
0x18002954e  jns     short loc_1800295A9
0x180029550  mov     rcx, [rsp+0F8h]; this
0x180029558  mov     r9d, eax; char *
0x18002955b  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180029562  mov     edx, 10C8h; void *
0x180029567  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002956c  nop
0x18002956d  lea     rcx, [rsp+0F8h+var_98]
0x180029572  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029577  nop
0x180029578  lea     rcx, [rsp+0F8h+var_90]
0x18002957d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029582  nop
0x180029583  mov     rcx, rbx; string
0x180029586  call    cs:__imp_WindowsDeleteString
0x18002958c  nop
0x18002958d  lea     rcx, [rsp+0F8h+var_A8]
0x180029592  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029597  nop
0x180029598  lea     rcx, [rsp+0F8h+var_80]
0x18002959d  call    ?_Tidy@?$vector@UCheckpointAbandonmentRule@@V?$allocator@UCheckpointAbandonmentRule@@@std@@@std@@AEAAXXZ; std::vector<CheckpointAbandonmentRule>::_Tidy(void)
0x1800295a2  mov     eax, edi
0x1800295a4  jmp     loc_1800298E8
0x1800295a9  xorps   xmm0, xmm0
0x1800295ac  movups  [rsp+0F8h+var_60], xmm0
0x1800295b4  movdqu  [rsp+0F8h+var_50], xmm6
0x1800295bd  mov     word ptr [rsp+0F8h+var_60], r12w
0x1800295c6  mov     qword ptr [rsp+0F8h+var_40], r12
0x1800295ce  mov     [rsp+0F8h+var_A0], r12
0x1800295d3  xor     ecx, ecx; string
0x1800295d5  call    cs:__imp_WindowsDeleteString
0x1800295db  mov     [rsp+0F8h+var_A0], r12
0x1800295e0  lea     r8, [rsp+0F8h+var_A0]; HSTRING *
0x1800295e5  lea     rdx, aCallerapplicat; "callerApplicationIdKeyword"
0x1800295ec  mov     rcx, [rsp+0F8h+var_98]; struct Windows::Data::Json::IJsonObject *
0x1800295f1  call    ?Json_GetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAPEAUHSTRING__@@@Z; Json_GetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,HSTRING__ * *)
0x1800295f6  mov     edi, eax
0x1800295f8  test    eax, eax
0x1800295fa  jns     short loc_180029673
0x1800295fc  mov     rcx, [rsp+0F8h]; this
0x180029604  mov     r9d, eax; char *
0x180029607  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18002960e  mov     edx, 10CDh; void *
0x180029613  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029618  nop
0x180029619  mov     rcx, [rsp+0F8h+var_A0]; string
0x18002961e  call    cs:__imp_WindowsDeleteString
0x180029624  mov     [rsp+0F8h+var_A0], r12
0x180029629  lea     rcx, [rsp+0F8h+var_60]
0x180029631  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029636  nop
0x180029637  lea     rcx, [rsp+0F8h+var_98]
0x18002963c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029641  nop
0x180029642  lea     rcx, [rsp+0F8h+var_90]
0x180029647  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002964c  nop
0x18002964d  mov     rcx, rbx; string
0x180029650  call    cs:__imp_WindowsDeleteString
0x180029656  nop
0x180029657  lea     rcx, [rsp+0F8h+var_A8]
0x18002965c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029661  nop
0x180029662  lea     rcx, [rsp+0F8h+var_80]
0x180029667  call    ?_Tidy@?$vector@UCheckpointAbandonmentRule@@V?$allocator@UCheckpointAbandonmentRule@@@std@@@std@@AEAAXXZ; std::vector<CheckpointAbandonmentRule>::_Tidy(void)
0x18002966c  mov     eax, edi
0x18002966e  jmp     loc_1800298E8
0x180029673  xor     edx, edx; length
0x180029675  mov     rcx, [rsp+0F8h+var_A0]; string
0x18002967a  call    cs:__imp_WindowsGetStringRawBuffer
0x180029680  or      r8, 0FFFFFFFFFFFFFFFFh
0x180029684  inc     r8
0x180029687  cmp     [rax+r8*2], r12w
0x18002968c  jnz     short loc_180029684
0x18002968e  mov     rdx, rax
0x180029691  lea     rcx, [rsp+0F8h+var_60]
0x180029699  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002969e  lea     r8, [rsp+0F8h+var_40]; unsigned int *
0x1800296a6  lea     rdx, aSystemattemptc; "systemAttemptCountThreshold"
0x1800296ad  mov     rcx, [rsp+0F8h+var_98]; struct Windows::Data::Json::IJsonObject *
0x1800296b2  call    ?Json_GetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAI@Z; Json_GetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,uint *)
0x1800296b7  mov     edi, eax
0x1800296b9  test    eax, eax
0x1800296bb  jns     short loc_180029734
0x1800296bd  mov     rcx, [rsp+0F8h]; this
0x1800296c5  mov     r9d, eax; char *
0x1800296c8  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x1800296cf  mov     edx, 10D0h; void *
0x1800296d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800296d9  nop
0x1800296da  mov     rcx, [rsp+0F8h+var_A0]; string
0x1800296df  call    cs:__imp_WindowsDeleteString
0x1800296e5  mov     [rsp+0F8h+var_A0], r12
0x1800296ea  lea     rcx, [rsp+0F8h+var_60]
0x1800296f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800296f7  nop
0x1800296f8  lea     rcx, [rsp+0F8h+var_98]
0x1800296fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029702  nop
0x180029703  lea     rcx, [rsp+0F8h+var_90]
0x180029708  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002970d  nop
0x18002970e  mov     rcx, rbx; string
0x180029711  call    cs:__imp_WindowsDeleteString
0x180029717  nop
0x180029718  lea     rcx, [rsp+0F8h+var_A8]
0x18002971d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029722  nop
0x180029723  lea     rcx, [rsp+0F8h+var_80]
0x180029728  call    ?_Tidy@?$vector@UCheckpointAbandonmentRule@@V?$allocator@UCheckpointAbandonmentRule@@@std@@@std@@AEAAXXZ; std::vector<CheckpointAbandonmentRule>::_Tidy(void)
0x18002972d  mov     eax, edi
0x18002972f  jmp     loc_1800298E8
0x180029734  lea     r8, [rsp+0F8h+var_40+4]; unsigned int *
0x18002973c  lea     rdx, aCreationtimest; "creationTimestampThresholdInDays"
0x180029743  mov     rcx, [rsp+0F8h+var_98]; struct Windows::Data::Json::IJsonObject *
0x180029748  call    ?Json_GetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAI@Z; Json_GetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,uint *)
0x18002974d  mov     edi, eax
0x18002974f  test    eax, eax
0x180029751  jns     short loc_1800297CA
0x180029753  mov     rcx, [rsp+0F8h]; this
0x18002975b  mov     r9d, eax; char *
0x18002975e  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180029765  mov     edx, 10D1h; void *
0x18002976a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002976f  nop
0x180029770  mov     rcx, [rsp+0F8h+var_A0]; string
0x180029775  call    cs:__imp_WindowsDeleteString
0x18002977b  mov     [rsp+0F8h+var_A0], r12
0x180029780  lea     rcx, [rsp+0F8h+var_60]
0x180029788  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002978d  nop
0x18002978e  lea     rcx, [rsp+0F8h+var_98]
0x180029793  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029798  nop
0x180029799  lea     rcx, [rsp+0F8h+var_90]
0x18002979e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800297a3  nop
0x1800297a4  mov     rcx, rbx; string
0x1800297a7  call    cs:__imp_WindowsDeleteString
0x1800297ad  nop
0x1800297ae  lea     rcx, [rsp+0F8h+var_A8]
0x1800297b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800297b8  nop
0x1800297b9  lea     rcx, [rsp+0F8h+var_80]
0x1800297be  call    ?_Tidy@?$vector@UCheckpointAbandonmentRule@@V?$allocator@UCheckpointAbandonmentRule@@@std@@@std@@AEAAXXZ; std::vector<CheckpointAbandonmentRule>::_Tidy(void)
0x1800297c3  mov     eax, edi
  ... truncated ...
```
