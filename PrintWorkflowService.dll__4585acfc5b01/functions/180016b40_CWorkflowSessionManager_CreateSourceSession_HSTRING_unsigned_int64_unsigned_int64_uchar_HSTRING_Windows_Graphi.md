# CWorkflowSessionManager::CreateSourceSession(HSTRING__ *,unsigned __int64,unsigned __int64,uchar,HSTRING__ *,Windows::Graphics::Internal::Printing::Workflow::IWorkflowSourceSession * *)

- ea: `0x180016b40`
- end: `0x180016db7`
- name: `?CreateSourceSession@CWorkflowSessionManager@@UEAAJPEAUHSTRING__@@_K1E0PEAPEAUIWorkflowSourceSession@Workflow@Printing@Internal@Graphics@Windows@@@Z`
- size: `631`
- prototype: `int(CWorkflowSessionManager *__hidden this, HSTRING, unsigned __int64, unsigned __int64, unsigned __int8, HSTRING, struct Windows::Graphics::Internal::Printing::Workflow::IWorkflowSourceSession **)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180001314`
- `0x180001588`
- `0x180001614`
- `0x18000dfd0`
- `0x180010b0c`
- `0x180015e20`
- `0x180016070`
- `0x180016b40`
- `0x180017de0`
- `0x1800181b8`
- `0x1800182a4`
- `0x1800239c8`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016b6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016b6c`

## string_xrefs

- `0x180016c40`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsessionmanager.cpp`
- `0x180016c81`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsessionmanager.cpp`
- `0x180016d09`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsessionmanager.cpp`
- `0x180016c2c`: `Unexpected next available session id already exists in the map`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWorkflowSessionManager::CreateSourceSession(
        CWorkflowSessionManager *this,
        HSTRING a2,
        __int64 a3,
        __int64 a4,
        char a5,
        HSTRING a6,
        struct Windows::Graphics::Internal::Printing::Workflow::IWorkflowSourceSession **a7)
{
  __int64 v7; // r9
  int TemporaryFileHandles; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  SessionMapSingleton *Instance; // rax
  unsigned int v12; // edi
  __int64 v13; // rdx
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  int v23; // [rsp+20h] [rbp-30h]
  char *v24; // [rsp+28h] [rbp-28h]
  unsigned int v25[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v26; // [rsp+38h] [rbp-18h] BYREF
  __int64 v27[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HSTRING v29; // [rsp+78h] [rbp+28h] BYREF
  __int64 v30; // [rsp+80h] [rbp+30h] BYREF
  __int64 v31; // [rsp+88h] [rbp+38h] BYREF

  v31 = a4;
  v30 = a3;
  v29 = a2;
  if ( (unsigned int)dword_180083038 > 5 )
  {
    *(_QWORD *)v25 = WindowsGetStringRawBuffer(a2, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_180083038,
      (__int64)byte_18006FA23,
      0,
      v7,
      (const WCHAR **)v25);
  }
  if ( (unsigned int)dword_180083038 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180083038,
      (__int64)word_18006F9A2,
      0);
  v27[0] = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(v27);
  TemporaryFileHandles = Microsoft::WRL::Details::MakeAndInitialize<CWorkflowSession,CWorkflowSession,HSTRING__ * &,HSTRING__ * &,unsigned __int64 &,unsigned __int64 &,unsigned char &>(
                           (unsigned int)v27,
                           (unsigned int)&v29,
                           (unsigned int)&a6,
                           (unsigned int)&v30,
                           (__int64)&v31,
                           (__int64)&a5);
  v9 = TemporaryFileHandles;
  if ( TemporaryFileHandles < 0 )
  {
    v10 = 53;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsessionmanager.cpp",
      (const char *)(unsigned int)TemporaryFileHandles,
      v23);
    goto LABEL_26;
  }
  v25[0] = 0;
  Instance = SessionMapSingleton::GetInstance();
  if ( SessionMapSingleton::AddSession(
         Instance,
         (struct Windows::Graphics::Internal::Printing::Workflow::IWorkflowSession *)((v27[0] + 24)
                                                                                    & -(__int64)(v27[0] != 0)),
         v25) )
  {
    v12 = v25[0];
    TemporaryFileHandles = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v27[0] + 24) + 56LL))(
                             v27[0] + 24,
                             v25[0]);
    v9 = TemporaryFileHandles;
    if ( TemporaryFileHandles < 0 )
    {
      v10 = 58;
      goto LABEL_11;
    }
    TemporaryFileHandles = WorkflowSessionCommon::CreateTemporaryFileHandles(
                             (WorkflowSessionCommon *)(v27[0] + 280),
                             v13,
                             v14,
                             v15);
    v9 = TemporaryFileHandles;
    if ( TemporaryFileHandles < 0 )
    {
      v10 = 61;
      goto LABEL_11;
    }
    if ( (unsigned int)dword_180083038 > 5 )
    {
      v25[0] = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180083038,
        (__int64)&dword_18006F934,
        v16,
        v17,
        (__int64)v25);
    }
    v26 = 0;
    Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v26);
    v18 = Microsoft::WRL::Details::MakeAndInitialize<CWorkflowSourceSession,CWorkflowSourceSession,Microsoft::WRL::ComPtr<CWorkflowSession> &>(
            &v26,
            v27);
    v9 = v18;
    if ( v18 >= 0 )
    {
      if ( (unsigned int)dword_180083038 > 5 )
      {
        v25[0] = v12;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180083038,
          (__int64)&byte_18006F8D7,
          v19,
          v20,
          (__int64)v25);
      }
      v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v26 + 24) + 48LL))(v26 + 24);
      v9 = v18;
      if ( v18 >= 0 )
      {
        v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct Windows::Graphics::Internal::Printing::Workflow::IWorkflowSourceSession **))v26)(
                v26,
                &GUID_b5a8be57_53b6_4597_8d5d_4e05501f687f,
                a7);
        v9 = v18;
        if ( v18 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v26);
          v9 = 0;
          goto LABEL_26;
        }
        v21 = 80;
      }
      else
      {
        v21 = 78;
      }
    }
    else
    {
      v21 = 69;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsessionmanager.cpp",
      (const char *)(unsigned int)v18,
      v23);
    Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v26);
  }
  else
  {
    v9 = -2147467259;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsessionmanager.cpp",
      (const char *)0x80004005LL,
      (int)"Unexpected next available session id already exists in the map",
      v24);
  }
LABEL_26:
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(v27);
  return v9;
}

```

## disassembly

```asm
0x180016b40  mov     [rsp-18h+arg_18], r9
0x180016b45  mov     [rsp-18h+arg_10], r8
0x180016b4a  mov     [rsp-18h+arg_8], rdx
0x180016b4f  push    rbp
0x180016b50  push    rbx
0x180016b51  push    rdi
0x180016b52  mov     rbp, rsp
0x180016b55  sub     rsp, 50h
0x180016b59  mov     r8, rdx
0x180016b5c  mov     eax, cs:dword_180083038
0x180016b62  cmp     eax, 5
0x180016b65  jbe     short loc_180016B95
0x180016b67  xor     edx, edx; length
0x180016b69  mov     rcx, r8; string
0x180016b6c  call    cs:__imp_WindowsGetStringRawBuffer
0x180016b72  mov     qword ptr [rbp+var_20], rax
0x180016b76  lea     rax, [rbp+var_20]
0x180016b7a  mov     qword ptr [rsp+50h+var_30], rax
0x180016b7f  xor     r8d, r8d
0x180016b82  lea     rdx, byte_18006FA23
0x180016b89  lea     rcx, dword_180083038
0x180016b90  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180016b95  mov     eax, cs:dword_180083038
0x180016b9b  cmp     eax, 5
0x180016b9e  jbe     short loc_180016BB6
0x180016ba0  xor     r8d, r8d
0x180016ba3  lea     rdx, word_18006F9A2
0x180016baa  lea     rcx, dword_180083038
0x180016bb1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180016bb6  mov     [rbp+var_10], 0
0x180016bbe  lea     rcx, [rbp+var_10]
0x180016bc2  call    ?InternalRelease@?$ComPtr@UIModalExperienceManagerStatic@ModalExperience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(void)
0x180016bc7  lea     rax, [rbp+arg_20]
0x180016bcb  mov     [rsp+50h+var_28], rax; char *
0x180016bd0  lea     rax, [rbp+arg_18]
0x180016bd4  mov     qword ptr [rsp+50h+var_30], rax; int
0x180016bd9  lea     r9, [rbp+arg_10]
0x180016bdd  lea     r8, [rbp+arg_28]
0x180016be1  lea     rdx, [rbp+arg_8]
0x180016be5  lea     rcx, [rbp+var_10]
0x180016be9  call    ??$MakeAndInitialize@VCWorkflowSession@@V1@AEAPEAUHSTRING__@@AEAPEAU2@AEA_KAEA_KAEAE@Details@WRL@Microsoft@@YAJPEAPEAVCWorkflowSession@@AEAPEAUHSTRING__@@1AEA_K2AEAE@Z; Microsoft::WRL::Details::MakeAndInitialize<CWorkflowSession,CWorkflowSession,HSTRING__ * &,HSTRING__ * &,unsigned __int64 &,unsigned __int64 &,uchar &>(CWorkflowSession * *,HSTRING__ * &,HSTRING__ * &,unsigned __int64 &,unsigned __int64 &,uchar &)
0x180016bee  mov     ebx, eax
0x180016bf0  test    eax, eax
0x180016bf2  jns     short loc_180016BFB
0x180016bf4  mov     edx, 35h ; '5'
0x180016bf9  jmp     short loc_180016C7A
0x180016bfb  mov     [rbp+var_20], 0
0x180016c02  call    ?GetInstance@SessionMapSingleton@@SAAEAV1@XZ; SessionMapSingleton::GetInstance(void)
0x180016c07  mov     rcx, [rbp+var_10]
0x180016c0b  lea     r8, [rcx+18h]
0x180016c0f  neg     rcx
0x180016c12  sbb     rdx, rdx
0x180016c15  and     rdx, r8; struct Windows::Graphics::Internal::Printing::Workflow::IWorkflowSession *
0x180016c18  lea     r8, [rbp+var_20]; unsigned int *
0x180016c1c  mov     rcx, rax; this
0x180016c1f  call    ?AddSession@SessionMapSingleton@@QEAA_NPEAUIWorkflowSession@Workflow@Printing@Internal@Graphics@Windows@@PEAK@Z; SessionMapSingleton::AddSession(Windows::Graphics::Internal::Printing::Workflow::IWorkflowSession *,ulong *)
0x180016c24  test    al, al
0x180016c26  jnz     short loc_180016C56
0x180016c28  mov     rcx, [rbp+18h]; this
0x180016c2c  lea     rax, aUnexpectedNext; "Unexpected next available session id al"...
0x180016c33  mov     qword ptr [rsp+50h+var_30], rax; int
0x180016c38  mov     ebx, 80004005h
0x180016c3d  mov     r9d, ebx; char *
0x180016c40  lea     r8, aOnecoreuapPrin_21; "onecoreuap\\printscan\\print\\workflow"...
0x180016c47  mov     edx, 38h ; '8'; void *
0x180016c4c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180016c51  jmp     loc_180016DA4
0x180016c56  mov     rcx, [rbp+var_10]
0x180016c5a  add     rcx, 18h
0x180016c5e  mov     rax, [rcx]
0x180016c61  mov     edi, [rbp+var_20]
0x180016c64  mov     edx, edi
0x180016c66  mov     rax, [rax+38h]
0x180016c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c6f  mov     ebx, eax
0x180016c71  test    eax, eax
0x180016c73  jns     short loc_180016C92
0x180016c75  mov     edx, 3Ah ; ':'; void *
0x180016c7a  mov     rcx, [rbp+18h]; this
0x180016c7e  mov     r9d, eax; char *
0x180016c81  lea     r8, aOnecoreuapPrin_21; "onecoreuap\\printscan\\print\\workflow"...
0x180016c88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c8d  jmp     loc_180016DA4
0x180016c92  mov     rcx, [rbp+var_10]
0x180016c96  add     rcx, 118h; this
0x180016c9d  call    ?CreateTemporaryFileHandles@WorkflowSessionCommon@@QEAAJXZ; WorkflowSessionCommon::CreateTemporaryFileHandles(void)
0x180016ca2  mov     ebx, eax
0x180016ca4  test    eax, eax
0x180016ca6  jns     short loc_180016CAF
0x180016ca8  mov     edx, 3Dh ; '='
0x180016cad  jmp     short loc_180016C7A
0x180016caf  mov     eax, cs:dword_180083038
0x180016cb5  cmp     eax, 5
0x180016cb8  jbe     short loc_180016CD9
0x180016cba  mov     [rbp+var_20], edi
0x180016cbd  lea     rax, [rbp+var_20]
0x180016cc1  mov     qword ptr [rsp+50h+var_30], rax; int
0x180016cc6  lea     rdx, dword_18006F934
0x180016ccd  lea     rcx, dword_180083038
0x180016cd4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180016cd9  mov     [rbp+var_18], 0
0x180016ce1  lea     rcx, [rbp+var_18]
0x180016ce5  call    ?InternalRelease@?$ComPtr@UIModalExperienceManagerStatic@ModalExperience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(void)
0x180016cea  lea     rdx, [rbp+var_10]
0x180016cee  lea     rcx, [rbp+var_18]
0x180016cf2  call    ??$MakeAndInitialize@VCWorkflowSourceSession@@V1@AEAV?$ComPtr@VCWorkflowSession@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAVCWorkflowSourceSession@@AEAV?$ComPtr@VCWorkflowSession@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<CWorkflowSourceSession,CWorkflowSourceSession,Microsoft::WRL::ComPtr<CWorkflowSession> &>(CWorkflowSourceSession * *,Microsoft::WRL::ComPtr<CWorkflowSession> &)
0x180016cf7  mov     ebx, eax
0x180016cf9  test    eax, eax
0x180016cfb  jns     short loc_180016D24
0x180016cfd  mov     edx, 45h ; 'E'; void *
0x180016d02  mov     rcx, [rbp+18h]; this
0x180016d06  mov     r9d, eax; char *
0x180016d09  lea     r8, aOnecoreuapPrin_21; "onecoreuap\\printscan\\print\\workflow"...
0x180016d10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016d15  nop
0x180016d16  lea     rcx, [rbp+var_18]
0x180016d1a  call    ?InternalRelease@?$ComPtr@UIModalExperienceManagerStatic@ModalExperience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(void)
0x180016d1f  jmp     loc_180016DA4
0x180016d24  mov     eax, cs:dword_180083038
0x180016d2a  cmp     eax, 5
0x180016d2d  jbe     short loc_180016D4E
0x180016d2f  mov     [rbp+var_20], edi
0x180016d32  lea     rax, [rbp+var_20]
0x180016d36  mov     qword ptr [rsp+50h+var_30], rax
0x180016d3b  lea     rdx, byte_18006F8D7
0x180016d42  lea     rcx, dword_180083038
0x180016d49  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180016d4e  mov     rcx, [rbp+var_18]
0x180016d52  add     rcx, 18h
0x180016d56  mov     rax, [rcx]
0x180016d59  mov     rax, [rax+30h]
0x180016d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d62  mov     ebx, eax
0x180016d64  test    eax, eax
0x180016d66  jns     short loc_180016D6F
0x180016d68  mov     edx, 4Eh ; 'N'
0x180016d6d  jmp     short loc_180016D02
0x180016d6f  mov     rcx, [rbp+var_18]
0x180016d73  mov     rax, [rcx]
0x180016d76  mov     r8, [rbp+arg_30]
0x180016d7a  lea     rdx, _GUID_b5a8be57_53b6_4597_8d5d_4e05501f687f
0x180016d81  mov     rax, [rax]
0x180016d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d89  mov     ebx, eax
0x180016d8b  test    eax, eax
0x180016d8d  jns     short loc_180016D99
0x180016d8f  mov     edx, 50h ; 'P'
0x180016d94  jmp     loc_180016D02
0x180016d99  lea     rcx, [rbp+var_18]
0x180016d9d  call    ?InternalRelease@?$ComPtr@UIModalExperienceManagerStatic@ModalExperience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(void)
0x180016da2  xor     ebx, ebx
0x180016da4  lea     rcx, [rbp+var_10]
0x180016da8  call    ?InternalRelease@?$ComPtr@UIModalExperienceManagerStatic@ModalExperience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(void)
0x180016dad  mov     eax, ebx
0x180016daf  add     rsp, 50h
0x180016db3  pop     rdi
0x180016db4  pop     rbx
0x180016db5  pop     rbp
0x180016db6  retn
```
