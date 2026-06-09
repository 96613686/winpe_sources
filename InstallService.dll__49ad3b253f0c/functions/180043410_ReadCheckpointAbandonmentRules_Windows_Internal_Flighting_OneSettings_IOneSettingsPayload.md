# _ReadCheckpointAbandonmentRules(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *)

- ea: `0x180043410`
- end: `0x180043a67`
- name: `?_ReadCheckpointAbandonmentRules@@YAJPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@@Z`
- size: `1623`
- prototype: `__int64 __fastcall(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180048108`
- `0x18004b594`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001c144`
- `0x18001c414`
- `0x18001c964`
- `0x18001cce0`
- `0x180034874`
- `0x180034b3c`
- `0x180034c2c`
- `0x180037984`
- `0x180043410`
- `0x180044a28`
- `0x1800d5bb0`
- `0x1800d5cc4`
- `0x1800d5fa8`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800435d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043643`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800436e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004376e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800437a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004382f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043861`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800438c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800438f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800439ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043a12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800435d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043643`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800436e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004376e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800437a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004382f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043861`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800438c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800438f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800439ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043a12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004352b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800437ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004352b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800437ca`

## string_xrefs

- `0x1800434ca`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180043561`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x1800435b4`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180043623`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x1800436bb`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180043757`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180043818`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x1800438ae`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x1800437f6`: `systemAttemptCountThreshold`
- `0x180043554`: `_ReadCheckpointAbandonmentRules`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall _ReadCheckpointAbandonmentRules(
        struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *a1)
{
  __int64 (__fastcall *v2)(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *, _QWORD, struct IInspectable **); // rbx
  __int64 v3; // rax
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // eax
  HSTRING v8; // rbx
  struct IInspectable *v9; // rsi
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rdi
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  __int64 v14; // rcx
  unsigned int v15; // edi
  unsigned int v16; // r15d
  __m128i si128; // xmm6
  struct IInspectable *v18; // rsi
  HRESULT (__stdcall *v19)(IInspectable *, const IID *const, void **); // rdi
  int v20; // eax
  unsigned int v21; // edi
  int NamedValue; // eax
  unsigned int v23; // edi
  PCWSTR StringRawBuffer; // rax
  __int64 v25; // r8
  int v26; // eax
  unsigned int v27; // edi
  int v28; // eax
  unsigned int v29; // edi
  __int64 v30; // rdx
  int v31; // [rsp+20h] [rbp-D8h]
  struct IInspectable *v32; // [rsp+50h] [rbp-A8h] BYREF
  HSTRING v33; // [rsp+58h] [rbp-A0h] BYREF
  struct Windows::Data::Json::IJsonObject *v34; // [rsp+60h] [rbp-98h] BYREF
  __int64 v35; // [rsp+68h] [rbp-90h] BYREF
  unsigned int v36; // [rsp+70h] [rbp-88h] BYREF
  __int128 v37; // [rsp+78h] [rbp-80h] BYREF
  __int64 v38; // [rsp+88h] [rbp-70h]
  HSTRING string; // [rsp+90h] [rbp-68h] BYREF
  __int16 v40; // [rsp+98h] [rbp-60h] BYREF
  __int64 v41; // [rsp+9Ah] [rbp-5Eh]
  int v42; // [rsp+A2h] [rbp-56h]
  __int16 v43; // [rsp+A6h] [rbp-52h]
  __m128i v44; // [rsp+A8h] [rbp-50h]
  unsigned int v45[2]; // [rsp+B8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  if ( qword_1802CAF68 != qword_1802CAF70 )
  {
    std::_Destroy_range<std::allocator<CheckpointAbandonmentRule>>();
    qword_1802CAF70 = qword_1802CAF68;
  }
  v37 = 0;
  v38 = 0;
  v32 = 0;
  v2 = *(__int64 (__fastcall **)(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *, _QWORD, struct IInspectable **))(*(_QWORD *)a1 + 64LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
  v3 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v40, off_180227DF0);
  v4 = v2(a1, *(_QWORD *)(v3 + 24), &v32);
  v5 = v4;
  if ( v4 >= 0 )
  {
    WindowsDeleteString(0);
    string = 0;
    v7 = Json_Stringify(v32, &string);
    v8 = string;
    if ( v7 >= 0 )
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
    v35 = 0;
    v9 = v32;
    QueryInterface = v32->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
    v11 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
            v9,
            &GUID_d44662bc_dce3_59a8_9272_4b210f33908b,
            &v35);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v36 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v35 + 56LL))(v35, &v36);
      v15 = v13;
      if ( v13 >= 0 )
      {
        v16 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        while ( v16 < v36 )
        {
          v34 = 0;
          v18 = v32;
          v19 = v32->lpVtbl[1].QueryInterface;
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
          v20 = ((__int64 (__fastcall *)(struct IInspectable *, _QWORD, struct Windows::Data::Json::IJsonObject **))v19)(
                  v18,
                  v16,
                  &v34);
          v21 = v20;
          if ( v20 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x10C8,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
              (const char *)(unsigned int)v20,
              v31);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
            WindowsDeleteString(v8);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
            std::vector<UpdateToDownload>::_Tidy(&v37);
            return v21;
          }
          std::wstring::wstring(&v40);
          *(_QWORD *)v45 = 0;
          v33 = 0;
          WindowsDeleteString(0);
          v33 = 0;
          NamedValue = Json_GetNamedValue(v34, L"callerApplicationIdKeyword", &v33);
          v23 = NamedValue;
          if ( NamedValue < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x10CD,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
              (const char *)(unsigned int)NamedValue,
              v31);
            WindowsDeleteString(v33);
            v33 = 0;
            std::wstring::_Tidy_deallocate(&v40);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
            WindowsDeleteString(v8);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
            std::vector<UpdateToDownload>::_Tidy(&v37);
            return v23;
          }
          StringRawBuffer = WindowsGetStringRawBuffer(v33, 0);
          v25 = -1;
          do
            ++v25;
          while ( StringRawBuffer[v25] );
          std::wstring::_Assign<unsigned short>(&v40, StringRawBuffer, v25);
          v26 = Json_GetNamedValue(v34, L"systemAttemptCountThreshold", v45);
          v27 = v26;
          if ( v26 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x10D0,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
              (const char *)(unsigned int)v26,
              v31);
            WindowsDeleteString(v33);
            v33 = 0;
            std::wstring::_Tidy_deallocate(&v40);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
            WindowsDeleteString(v8);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
            std::vector<UpdateToDownload>::_Tidy(&v37);
            return v27;
          }
          v28 = Json_GetNamedValue(v34, L"creationTimestampThresholdInDays", &v45[1]);
          v29 = v28;
          if ( v28 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x10D1,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
              (const char *)(unsigned int)v28,
              v31);
            WindowsDeleteString(v33);
            v33 = 0;
            std::wstring::_Tidy_deallocate(&v40);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
            WindowsDeleteString(v8);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
            std::vector<UpdateToDownload>::_Tidy(&v37);
            return v29;
          }
          v30 = *((_QWORD *)&v37 + 1);
          if ( *((_QWORD *)&v37 + 1) == v38 )
          {
            std::vector<CheckpointAbandonmentRule>::_Emplace_reallocate<CheckpointAbandonmentRule>(
              &v37,
              *((_QWORD *)&v37 + 1),
              &v40);
          }
          else
          {
            **((_OWORD **)&v37 + 1) = 0;
            *(_QWORD *)(v30 + 16) = 0;
            *(_QWORD *)(v30 + 24) = 0;
            *(_WORD *)v30 = v40;
            *(_QWORD *)(v30 + 2) = v41;
            *(_DWORD *)(v30 + 10) = v42;
            *(_WORD *)(v30 + 14) = v43;
            *(__m128i *)(v30 + 16) = v44;
            v44 = si128;
            v40 = 0;
            *(_DWORD *)(v30 + 32) = v45[0];
            *(_DWORD *)(v30 + 36) = v45[1];
            *((_QWORD *)&v37 + 1) += 40LL;
          }
          WindowsDeleteString(v33);
          v33 = 0;
          std::wstring::_Tidy_deallocate(&v40);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
          ++v16;
        }
        std::vector<CheckpointAbandonmentRule>::operator=(v14, &v37);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
        WindowsDeleteString(v8);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
        std::vector<UpdateToDownload>::_Tidy(&v37);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10C3,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          (const char *)(unsigned int)v13,
          v31);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
        WindowsDeleteString(v8);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
        std::vector<UpdateToDownload>::_Tidy(&v37);
        return v15;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10C0,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        (const char *)(unsigned int)v11,
        v31);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
      WindowsDeleteString(v8);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
      std::vector<UpdateToDownload>::_Tidy(&v37);
      return v12;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10B7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      (const char *)(unsigned int)v4,
      v31);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
    std::vector<UpdateToDownload>::_Tidy(&v37);
    return v5;
  }
}

```

## disassembly

```asm
0x180043410  mov     rax, rsp
0x180043413  mov     [rax+10h], rbx
0x180043417  mov     [rax+18h], rsi
0x18004341b  push    rdi
0x18004341c  push    r12
0x18004341e  push    r15
0x180043420  sub     rsp, 0E0h
0x180043427  movaps  xmmword ptr [rax-28h], xmm6
0x18004342b  mov     rax, cs:__security_cookie
0x180043432  xor     rax, rsp
0x180043435  mov     [rsp+0F8h+var_38], rax
0x18004343d  mov     rdi, rcx
0x180043440  mov     rdx, cs:qword_1802CAF70
0x180043447  mov     rcx, cs:qword_1802CAF68
0x18004344e  cmp     rcx, rdx
0x180043451  jz      short loc_180043466
0x180043453  call    ??$_Destroy_range@V?$allocator@UCheckpointAbandonmentRule@@@std@@@std@@YAXPEAUCheckpointAbandonmentRule@@QEAU1@AEAV?$allocator@UCheckpointAbandonmentRule@@@0@@Z; std::_Destroy_range<std::allocator<CheckpointAbandonmentRule>>(CheckpointAbandonmentRule *,CheckpointAbandonmentRule * const,std::allocator<CheckpointAbandonmentRule> &)
0x180043458  mov     rax, cs:qword_1802CAF68
0x18004345f  mov     cs:qword_1802CAF70, rax
0x180043466  xorps   xmm0, xmm0
0x180043469  movdqu  [rsp+0F8h+var_80], xmm0
0x18004346f  xor     r12d, r12d
0x180043472  mov     [rsp+0F8h+var_70], r12
0x18004347a  mov     [rsp+0F8h+var_A8], r12
0x18004347f  mov     rax, [rdi]
0x180043482  mov     rbx, [rax+40h]
0x180043486  lea     rcx, [rsp+0F8h+var_A8]
0x18004348b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180043490  lea     rdx, off_180227DF0; "CHECKPOINTABANDONMENTRULES"
0x180043497  lea     rcx, [rsp+0F8h+var_60]
0x18004349f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800434a4  nop
0x1800434a5  lea     r8, [rsp+0F8h+var_A8]
0x1800434aa  mov     rdx, [rax+18h]
0x1800434ae  mov     rcx, rdi
0x1800434b1  mov     rax, rbx
0x1800434b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434b9  mov     ebx, eax
0x1800434bb  test    eax, eax
0x1800434bd  jns     short loc_1800434F8
0x1800434bf  mov     rcx, [rsp+0F8h]; this
0x1800434c7  mov     r9d, eax; char *
0x1800434ca  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x1800434d1  mov     edx, 10B7h; void *
0x1800434d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800434db  nop
0x1800434dc  lea     rcx, [rsp+0F8h+var_A8]
0x1800434e1  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800434e6  nop
0x1800434e7  lea     rcx, [rsp+0F8h+var_80]
0x1800434ec  call    ?_Tidy@?$vector@UUpdateToDownload@@V?$allocator@UUpdateToDownload@@@std@@@std@@AEAAXXZ; std::vector<UpdateToDownload>::_Tidy(void)
0x1800434f1  mov     eax, ebx
0x1800434f3  jmp     loc_180043A38
0x1800434f8  xor     ecx, ecx; string
0x1800434fa  call    cs:__imp_WindowsDeleteString
0x180043500  mov     [rsp+0F8h+string], r12
0x180043508  lea     rdx, [rsp+0F8h+string]; HSTRING *
0x180043510  mov     rcx, [rsp+0F8h+var_A8]; struct IInspectable *
0x180043515  call    ?Json_Stringify@@YAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z; Json_Stringify(IInspectable *,HSTRING__ * *)
0x18004351a  mov     rbx, [rsp+0F8h+string]
0x180043522  test    eax, eax
0x180043524  js      short loc_180043572
0x180043526  xor     edx, edx; length
0x180043528  mov     rcx, rbx; string
0x18004352b  call    cs:__imp_WindowsGetStringRawBuffer
0x180043531  mov     [rsp+0F8h+var_B8], rax
0x180043536  mov     [rsp+0F8h+var_C0], r12; unsigned __int16 *
0x18004353b  mov     [rsp+0F8h+var_C8], r12; char *
0x180043540  lea     rax, aCheckpointaban; "CheckpointAbandonmentRules fetched from"...
0x180043547  mov     [rsp+0F8h+var_D0], rax; unsigned __int16 *
0x18004354c  mov     [rsp+0F8h+var_D8], 0FFFFFFFFh; int
0x180043554  lea     r9, aReadcheckpoint; "_ReadCheckpointAbandonmentRules"
0x18004355b  mov     r8d, 10BCh; unsigned int
0x180043561  lea     rdx, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x180043568  mov     ecx, 4; unsigned int
0x18004356d  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180043572  mov     [rsp+0F8h+var_90], r12
0x180043577  mov     rsi, [rsp+0F8h+var_A8]
0x18004357c  mov     rax, [rsi]
0x18004357f  mov     rdi, [rax]
0x180043582  lea     rcx, [rsp+0F8h+var_90]
0x180043587  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18004358c  lea     r8, [rsp+0F8h+var_90]
0x180043591  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x180043598  mov     rcx, rsi
0x18004359b  mov     rax, rdi
0x18004359e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435a3  mov     edi, eax
0x1800435a5  test    eax, eax
0x1800435a7  jns     short loc_1800435F7
0x1800435a9  mov     rcx, [rsp+0F8h]; this
0x1800435b1  mov     r9d, eax; char *
0x1800435b4  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x1800435bb  mov     edx, 10C0h; void *
0x1800435c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800435c5  nop
0x1800435c6  lea     rcx, [rsp+0F8h+var_90]
0x1800435cb  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800435d0  nop
0x1800435d1  mov     rcx, rbx; string
0x1800435d4  call    cs:__imp_WindowsDeleteString
0x1800435da  nop
0x1800435db  lea     rcx, [rsp+0F8h+var_A8]
0x1800435e0  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800435e5  nop
0x1800435e6  lea     rcx, [rsp+0F8h+var_80]
0x1800435eb  call    ?_Tidy@?$vector@UUpdateToDownload@@V?$allocator@UUpdateToDownload@@@std@@@std@@AEAAXXZ; std::vector<UpdateToDownload>::_Tidy(void)
0x1800435f0  mov     eax, edi
0x1800435f2  jmp     loc_180043A38
0x1800435f7  mov     [rsp+0F8h+var_88], r12d
0x1800435fc  mov     rcx, [rsp+0F8h+var_90]
0x180043601  mov     rax, [rcx]
0x180043604  lea     rdx, [rsp+0F8h+var_88]
0x180043609  mov     rax, [rax+38h]
0x18004360d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043612  mov     edi, eax
0x180043614  test    eax, eax
0x180043616  jns     short loc_180043666
0x180043618  mov     rcx, [rsp+0F8h]; this
0x180043620  mov     r9d, eax; char *
0x180043623  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18004362a  mov     edx, 10C3h; void *
0x18004362f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043634  nop
0x180043635  lea     rcx, [rsp+0F8h+var_90]
0x18004363a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18004363f  nop
0x180043640  mov     rcx, rbx; string
0x180043643  call    cs:__imp_WindowsDeleteString
0x180043649  nop
0x18004364a  lea     rcx, [rsp+0F8h+var_A8]
0x18004364f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180043654  nop
0x180043655  lea     rcx, [rsp+0F8h+var_80]
0x18004365a  call    ?_Tidy@?$vector@UUpdateToDownload@@V?$allocator@UUpdateToDownload@@@std@@@std@@AEAAXXZ; std::vector<UpdateToDownload>::_Tidy(void)
0x18004365f  mov     eax, edi
0x180043661  jmp     loc_180043A38
0x180043666  mov     r15d, r12d
0x180043669  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180043671  cmp     r15d, [rsp+0F8h+var_88]
0x180043676  jnb     loc_1800439F9
0x18004367c  mov     [rsp+0F8h+var_98], r12
0x180043681  mov     rsi, [rsp+0F8h+var_A8]
0x180043686  mov     rax, [rsi]
0x180043689  mov     rdi, [rax+30h]
0x18004368d  lea     rcx, [rsp+0F8h+var_98]
0x180043692  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180043697  lea     r8, [rsp+0F8h+var_98]
0x18004369c  mov     edx, r15d
0x18004369f  mov     rcx, rsi
0x1800436a2  mov     rax, rdi
0x1800436a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436aa  mov     edi, eax
0x1800436ac  test    eax, eax
0x1800436ae  jns     short loc_180043709
0x1800436b0  mov     rcx, [rsp+0F8h]; this
0x1800436b8  mov     r9d, eax; char *
0x1800436bb  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x1800436c2  mov     edx, 10C8h; void *
0x1800436c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800436cc  nop
0x1800436cd  lea     rcx, [rsp+0F8h+var_98]
0x1800436d2  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800436d7  nop
0x1800436d8  lea     rcx, [rsp+0F8h+var_90]
0x1800436dd  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800436e2  nop
0x1800436e3  mov     rcx, rbx; string
0x1800436e6  call    cs:__imp_WindowsDeleteString
0x1800436ec  nop
0x1800436ed  lea     rcx, [rsp+0F8h+var_A8]
0x1800436f2  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800436f7  nop
0x1800436f8  lea     rcx, [rsp+0F8h+var_80]
0x1800436fd  call    ?_Tidy@?$vector@UUpdateToDownload@@V?$allocator@UUpdateToDownload@@@std@@@std@@AEAAXXZ; std::vector<UpdateToDownload>::_Tidy(void)
0x180043702  mov     eax, edi
0x180043704  jmp     loc_180043A38
0x180043709  lea     rcx, [rsp+0F8h+var_60]
0x180043711  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180043716  mov     qword ptr [rsp+0F8h+var_40], r12
0x18004371e  mov     [rsp+0F8h+var_A0], r12
0x180043723  xor     ecx, ecx; string
0x180043725  call    cs:__imp_WindowsDeleteString
0x18004372b  mov     [rsp+0F8h+var_A0], r12
0x180043730  lea     r8, [rsp+0F8h+var_A0]; HSTRING *
0x180043735  lea     rdx, aCallerapplicat; "callerApplicationIdKeyword"
0x18004373c  mov     rcx, [rsp+0F8h+var_98]; struct Windows::Data::Json::IJsonObject *
0x180043741  call    ?Json_GetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAPEAUHSTRING__@@@Z; Json_GetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,HSTRING__ * *)
0x180043746  mov     edi, eax
0x180043748  test    eax, eax
0x18004374a  jns     short loc_1800437C3
0x18004374c  mov     rcx, [rsp+0F8h]; this
0x180043754  mov     r9d, eax; char *
0x180043757  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18004375e  mov     edx, 10CDh; void *
0x180043763  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043768  nop
0x180043769  mov     rcx, [rsp+0F8h+var_A0]; string
0x18004376e  call    cs:__imp_WindowsDeleteString
0x180043774  mov     [rsp+0F8h+var_A0], r12
0x180043779  lea     rcx, [rsp+0F8h+var_60]
0x180043781  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043786  nop
0x180043787  lea     rcx, [rsp+0F8h+var_98]
0x18004378c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180043791  nop
0x180043792  lea     rcx, [rsp+0F8h+var_90]
0x180043797  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18004379c  nop
0x18004379d  mov     rcx, rbx; string
0x1800437a0  call    cs:__imp_WindowsDeleteString
0x1800437a6  nop
0x1800437a7  lea     rcx, [rsp+0F8h+var_A8]
0x1800437ac  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800437b1  nop
0x1800437b2  lea     rcx, [rsp+0F8h+var_80]
0x1800437b7  call    ?_Tidy@?$vector@UUpdateToDownload@@V?$allocator@UUpdateToDownload@@@std@@@std@@AEAAXXZ; std::vector<UpdateToDownload>::_Tidy(void)
0x1800437bc  mov     eax, edi
0x1800437be  jmp     loc_180043A38
0x1800437c3  xor     edx, edx; length
0x1800437c5  mov     rcx, [rsp+0F8h+var_A0]; string
0x1800437ca  call    cs:__imp_WindowsGetStringRawBuffer
0x1800437d0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800437d4  inc     r8
0x1800437d7  cmp     [rax+r8*2], r12w
0x1800437dc  jnz     short loc_1800437D4
0x1800437de  mov     rdx, rax
0x1800437e1  lea     rcx, [rsp+0F8h+var_60]
0x1800437e9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800437ee  lea     r8, [rsp+0F8h+var_40]; unsigned int *
0x1800437f6  lea     rdx, aSystemattemptc_2; "systemAttemptCountThreshold"
0x1800437fd  mov     rcx, [rsp+0F8h+var_98]; struct Windows::Data::Json::IJsonObject *
0x180043802  call    ?Json_GetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAI@Z; Json_GetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,uint *)
0x180043807  mov     edi, eax
0x180043809  test    eax, eax
0x18004380b  jns     short loc_180043884
0x18004380d  mov     rcx, [rsp+0F8h]; this
0x180043815  mov     r9d, eax; char *
0x180043818  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18004381f  mov     edx, 10D0h; void *
0x180043824  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043829  nop
0x18004382a  mov     rcx, [rsp+0F8h+var_A0]; string
0x18004382f  call    cs:__imp_WindowsDeleteString
0x180043835  mov     [rsp+0F8h+var_A0], r12
0x18004383a  lea     rcx, [rsp+0F8h+var_60]
0x180043842  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043847  nop
0x180043848  lea     rcx, [rsp+0F8h+var_98]
0x18004384d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180043852  nop
0x180043853  lea     rcx, [rsp+0F8h+var_90]
0x180043858  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18004385d  nop
0x18004385e  mov     rcx, rbx; string
0x180043861  call    cs:__imp_WindowsDeleteString
0x180043867  nop
0x180043868  lea     rcx, [rsp+0F8h+var_A8]
0x18004386d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180043872  nop
0x180043873  lea     rcx, [rsp+0F8h+var_80]
0x180043878  call    ?_Tidy@?$vector@UUpdateToDownload@@V?$allocator@UUpdateToDownload@@@std@@@std@@AEAAXXZ; std::vector<UpdateToDownload>::_Tidy(void)
0x18004387d  mov     eax, edi
0x18004387f  jmp     loc_180043A38
0x180043884  lea     r8, [rsp+0F8h+var_40+4]; unsigned int *
0x18004388c  lea     rdx, aCreationtimest; "creationTimestampThresholdInDays"
0x180043893  mov     rcx, [rsp+0F8h+var_98]; struct Windows::Data::Json::IJsonObject *
0x180043898  call    ?Json_GetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAI@Z; Json_GetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,uint *)
0x18004389d  mov     edi, eax
0x18004389f  test    eax, eax
0x1800438a1  jns     short loc_18004391A
0x1800438a3  mov     rcx, [rsp+0F8h]; this
0x1800438ab  mov     r9d, eax; char *
0x1800438ae  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x1800438b5  mov     edx, 10D1h; void *
0x1800438ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800438bf  nop
0x1800438c0  mov     rcx, [rsp+0F8h+var_A0]; string
0x1800438c5  call    cs:__imp_WindowsDeleteString
0x1800438cb  mov     [rsp+0F8h+var_A0], r12
0x1800438d0  lea     rcx, [rsp+0F8h+var_60]
0x1800438d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800438dd  nop
0x1800438de  lea     rcx, [rsp+0F8h+var_98]
0x1800438e3  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800438e8  nop
0x1800438e9  lea     rcx, [rsp+0F8h+var_90]
0x1800438ee  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800438f3  nop
0x1800438f4  mov     rcx, rbx; string
0x1800438f7  call    cs:__imp_WindowsDeleteString
0x1800438fd  nop
0x1800438fe  lea     rcx, [rsp+0F8h+var_A8]
0x180043903  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180043908  nop
0x180043909  lea     rcx, [rsp+0F8h+var_80]
0x18004390e  call    ?_Tidy@?$vector@UUpdateToDownload@@V?$allocator@UUpdateToDownload@@@std@@@std@@AEAAXXZ; std::vector<UpdateToDownload>::_Tidy(void)
0x180043913  mov     eax, edi
0x180043915  jmp     loc_180043A38
0x18004391a  mov     rdx, qword ptr [rsp+0F8h+var_80+8]
  ... truncated ...
```
