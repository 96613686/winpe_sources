# CWorkflowAppSession::LaunchWorkflowUIWithMem(Microsoft::WRL::ComPtr<Windows::Graphics::Printing::Workflow::IPrintWorkflowForegroundSession> const &,unsigned __int64,uchar,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001ecd8`
- end: `0x18001f1f8`
- name: `?LaunchWorkflowUIWithMem@CWorkflowAppSession@@QEAAJAEBV?$ComPtr@UIPrintWorkflowForegroundSession@Workflow@Printing@Graphics@Windows@@@WRL@Microsoft@@_KEAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z`
- size: `1312`
- prototype: `__int64 __usercall@<rax>(CWorkflowAppSession *this@<rcx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001eaf8`
- `0x18001f200`

## callees

- `0x180001314`
- `0x180001614`
- `0x180003ca0`
- `0x1800074f4`
- `0x180008698`
- `0x18000dfd0`
- `0x180010b0c`
- `0x180012784`
- `0x180012820`
- `0x18001cce8`
- `0x18001ceb8`
- `0x18001cf5c`
- `0x18001d70c`
- `0x18001da30`
- `0x18001dee4`
- `0x18001e084`
- `0x18001ecd8`
- `0x180020af0`
- `0x180020d88`
- `0x180055604`
- `0x18005e010`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18001f010`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18001f010`

## string_xrefs

- `0x18001ed8c`: `onecoreuap\printscan\print\workflow\broker\lib\workflowappsession.cpp`
- `0x18001ee8d`: `onecoreuap\printscan\print\workflow\broker\lib\workflowappsession.cpp`
- `0x18001ef28`: `onecoreuap\printscan\print\workflow\broker\lib\workflowappsession.cpp`
- `0x18001ef98`: `onecoreuap\printscan\print\workflow\broker\lib\workflowappsession.cpp`
- `0x18001f122`: `onecoreuap\printscan\print\workflow\broker\lib\workflowappsession.cpp`
- `0x18001ef68`: `Windows.PrintWorkflowForegroundTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CWorkflowAppSession::LaunchWorkflowUIWithMem(
        CWorkflowAppSession *this,
        __int64 *a2,
        __int64 a3,
        char a4,
        __int64 a5,
        __int64 a6)
{
  int ModalExperienceManager; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  CWorkflowAppSession *v12; // rcx
  unsigned __int64 v13; // r8
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  unsigned int v19; // edi
  const WCHAR *v20; // rbx
  unsigned int v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  int v26; // eax
  int IsAppBeingDebugged; // eax
  __int64 v28; // rdx
  CallerIdentity::ApiPolicyChecker *v29; // rax
  int *v30; // r8
  __int64 v31; // r8
  __int64 v32; // r9
  int v33; // esi
  struct Windows::Internal::Shell::ModalExperience::IModalWindowExperienceManager *v34; // rbx
  __int64 (__fastcall *v35)(struct Windows::Internal::Shell::ModalExperience::IModalWindowExperienceManager *, GUID *, __int64 *); // rdi
  int v36; // eax
  int v37; // eax
  __int64 v38; // rdx
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  struct Windows::Internal::Shell::ModalExperience::IModalExperienceDefaultOptions *v43; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v44; // [rsp+60h] [rbp-A0h] BYREF
  struct Windows::Internal::Shell::ModalExperience::IModalWindowExperienceManager *v45; // [rsp+68h] [rbp-98h] BYREF
  __int64 v46; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+78h] [rbp-88h] BYREF
  HSTRING_HEADER v48; // [rsp+80h] [rbp-80h] BYREF
  __int64 v49; // [rsp+98h] [rbp-68h]
  _BYTE v50[16]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v51; // [rsp+B0h] [rbp-50h]
  HSTRING_HEADER hstringHeader; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v53; // [rsp+D8h] [rbp-28h]
  HSTRING_HEADER v54; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v55; // [rsp+F8h] [rbp-8h]
  _BYTE v56[24]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v57; // [rsp+118h] [rbp+18h]
  _OWORD v58[2]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  if ( (unsigned int)dword_180083038 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180083038,
      (__int64)word_1800720EA,
      0);
  v45 = 0;
  v43 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v45);
  ModalExperienceManager = CWorkflowAppSession::GetModalExperienceManager(this, &v45);
  v10 = ModalExperienceManager;
  if ( ModalExperienceManager < 0 )
  {
    v11 = 452;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowappsession.cpp",
      (const char *)(unsigned int)ModalExperienceManager,
      v40);
LABEL_37:
    Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v45);
    return v10;
  }
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v43);
  ModalExperienceManager = CWorkflowAppSession::GetModalExperienceOptions(v12, &v43);
  v10 = ModalExperienceManager;
  if ( ModalExperienceManager < 0 )
  {
    v11 = 453;
    goto LABEL_7;
  }
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &sourceString, 1u, 0);
  v13 = *(_QWORD *)(a6 + 16);
  v14 = *(_QWORD *)(a5 + 16) + 1LL;
  memset(v58, 0, sizeof(v58));
  if ( v13 < v14 )
    std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
  v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a6);
  std::wstring::_Construct<1,unsigned short const *>(v58, v15 + 2 * v16, v17);
  v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
  std::wstring::wstring((__int64)v50, v18);
  std::wstring::_Tidy_deallocate(v58);
  v19 = v51;
  v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50);
  v49 = 0;
  v21 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v19);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v48, v20, v21, v19);
  v22 = (*(__int64 (__fastcall **)(struct Windows::Internal::Shell::ModalExperience::IModalExperienceDefaultOptions *, __int64))(*(_QWORD *)v43 + 96LL))(
          v43,
          v49);
  v10 = v22;
  if ( v22 < 0 )
  {
    v24 = 463;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowappsession.cpp",
      (const char *)(unsigned int)v22,
      v40);
    v49 = 0;
    std::wstring::_Tidy_deallocate(v50);
    v53 = 0;
    goto LABEL_37;
  }
  LOBYTE(v23) = 1;
  v22 = (*(__int64 (__fastcall **)(struct Windows::Internal::Shell::ModalExperience::IModalExperienceDefaultOptions *, __int64))(*(_QWORD *)v43 + 80LL))(
          v43,
          v23);
  v10 = v22;
  if ( v22 < 0 )
  {
    v24 = 464;
    goto LABEL_11;
  }
  if ( !a4 )
  {
    LOBYTE(v25) = 1;
    v22 = (*(__int64 (__fastcall **)(struct Windows::Internal::Shell::ModalExperience::IModalExperienceDefaultOptions *, __int64))(*(_QWORD *)v43 + 144LL))(
            v43,
            v25);
    v10 = v22;
    if ( v22 < 0 )
    {
      v24 = 467;
      goto LABEL_11;
    }
  }
  v42 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v42);
  v26 = Microsoft::WRL::Details::MakeAndInitialize<WorkflowUIActivatedEventArgsImpl,Windows::Graphics::Printing::Workflow::IPrintWorkflowUIActivatedEventArgs,Microsoft::WRL::ComPtr<Windows::Graphics::Printing::Workflow::IPrintWorkflowForegroundSession> const &>(
          &v42,
          a2);
  v10 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D8,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowappsession.cpp",
      (const char *)(unsigned int)v26,
      v40);
LABEL_36:
    Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v42);
    v49 = 0;
    std::wstring::_Tidy_deallocate(v50);
    v53 = 0;
    goto LABEL_37;
  }
  v46 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a6);
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v56, &v46);
  v55 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v54,
    L"Windows.PrintWorkflowForegroundTask",
    0x24u,
    0x23u);
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease((char *)this + 96);
  IsAppBeingDebugged = Microsoft::WRL::Details::MakeAndInitialize<CWorkflowModalExperienceManagerAppListener,CWorkflowModalExperienceManagerAppListener,>((char *)this + 96);
  v10 = IsAppBeingDebugged;
  if ( IsAppBeingDebugged < 0 )
  {
    v28 = 483;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowappsession.cpp",
      (const char *)(unsigned int)IsAppBeingDebugged,
      v40);
LABEL_35:
    v55 = 0;
    v57 = 0;
    goto LABEL_36;
  }
  v29 = (CallerIdentity::ApiPolicyChecker *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a6);
  IsAppBeingDebugged = CallerIdentity::ApiPolicyChecker::IsAppBeingDebugged(
                         v29,
                         (const unsigned __int16 *)this + 38,
                         v30);
  v10 = IsAppBeingDebugged;
  if ( IsAppBeingDebugged < 0 )
  {
    v28 = 486;
    goto LABEL_21;
  }
  if ( (unsigned int)dword_180083038 > 5 )
  {
    LODWORD(v46) = *((_DWORD *)this + 19);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180083038,
      (__int64)word_180072042,
      v31,
      v32,
      (__int64)&v46);
  }
  v47 = 0;
  v33 = UMgrQueryUserContext(0, &v47);
  v44 = 0;
  v34 = v45;
  v35 = **(__int64 (__fastcall ***)(struct Windows::Internal::Shell::ModalExperience::IModalWindowExperienceManager *, GUID *, __int64 *))v45;
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v44);
  v36 = v35(v34, &GUID_50c6090b_023e_4fde_b226_57c3e26d2881, &v44);
  if ( v33 < 0 || v36 < 0 )
  {
    v41 = (int)v43;
    v37 = (*(__int64 (__fastcall **)(struct Windows::Internal::Shell::ModalExperience::IModalWindowExperienceManager *, __int64, __int64, __int64))(*(_QWORD *)v45 + 56LL))(
            v45,
            v57,
            v55,
            v42);
    v10 = v37;
    if ( v37 < 0 )
    {
      v38 = 508;
      goto LABEL_34;
    }
  }
  else
  {
    v41 = (int)v43;
    v37 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v44 + 48LL))(v44, v57, v55, v42);
    v10 = v37;
    if ( v37 < 0 )
    {
      v38 = 520;
LABEL_34:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v38,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowappsession.cpp",
        (const char *)(unsigned int)v37,
        v41);
      Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v44);
      goto LABEL_35;
    }
  }
  v37 = CWorkflowModalExperienceManagerAppListener::WaitForViewVisible(*((CWorkflowModalExperienceManagerAppListener **)this
                                                                       + 12));
  v10 = v37;
  if ( v37 < 0 )
  {
    v38 = 523;
    goto LABEL_34;
  }
  *((_BYTE *)this + 72) = 1;
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v44);
  v55 = 0;
  v57 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v42);
  v49 = 0;
  std::wstring::_Tidy_deallocate(v50);
  v53 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v45);
  return 0;
}

```

## disassembly

```asm
0x18001ecd8  mov     [rsp-8+arg_18], rbx
0x18001ecdd  push    rbp
0x18001ecde  push    rsi
0x18001ecdf  push    rdi
0x18001ece0  push    r12
0x18001ece2  push    r13
0x18001ece4  push    r14
0x18001ece6  push    r15
0x18001ece8  lea     rbp, [rsp-50h]
0x18001eced  sub     rsp, 150h
0x18001ecf4  mov     rax, cs:__security_cookie
0x18001ecfb  xor     rax, rsp
0x18001ecfe  mov     [rbp+80h+var_40], rax
0x18001ed02  mov     r15b, r9b
0x18001ed05  mov     r12, r8
0x18001ed08  mov     r13, rdx
0x18001ed0b  mov     r14, rcx
0x18001ed0e  mov     rdi, [rbp+80h+arg_20]
0x18001ed15  mov     rsi, [rbp+80h+arg_28]
0x18001ed1c  xor     ebx, ebx
0x18001ed1e  mov     eax, cs:dword_180083038
0x18001ed24  cmp     eax, 5
0x18001ed27  jbe     short loc_18001ED3F
0x18001ed29  xor     r8d, r8d
0x18001ed2c  lea     rdx, word_1800720EA
0x18001ed33  lea     rcx, dword_180083038
0x18001ed3a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001ed3f  mov     [rsp+180h+var_118], rbx
0x18001ed44  mov     [rsp+180h+var_128], rbx
0x18001ed49  lea     rcx, [rsp+180h+var_118]
0x18001ed4e  call    ?InternalRelease@?$ComPtr@UIModalExperienceManagerStatic@ModalExperience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(void)
0x18001ed53  lea     rdx, [rsp+180h+var_118]; struct Windows::Internal::Shell::ModalExperience::IModalWindowExperienceManager **
0x18001ed58  mov     rcx, r14; this
0x18001ed5b  call    ?GetModalExperienceManager@CWorkflowAppSession@@QEAAJPEAPEAUIModalWindowExperienceManager@ModalExperience@Shell@Internal@Windows@@@Z; CWorkflowAppSession::GetModalExperienceManager(Windows::Internal::Shell::ModalExperience::IModalWindowExperienceManager * *)
0x18001ed60  mov     ebx, eax
0x18001ed62  test    eax, eax
0x18001ed64  jns     short loc_18001ED6D
0x18001ed66  mov     edx, 1C4h
0x18001ed6b  jmp     short loc_18001ED8C
0x18001ed6d  lea     rcx, [rsp+180h+var_128]
0x18001ed72  call    ?InternalRelease@?$ComPtr@UIModalExperienceManagerStatic@ModalExperience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(void)
0x18001ed77  lea     rdx, [rsp+180h+var_128]; struct Windows::Internal::Shell::ModalExperience::IModalExperienceDefaultOptions **
0x18001ed7c  call    ?GetModalExperienceOptions@CWorkflowAppSession@@QEAAJPEAPEAUIModalExperienceDefaultOptions@ModalExperience@Shell@Internal@Windows@@@Z; CWorkflowAppSession::GetModalExperienceOptions(Windows::Internal::Shell::ModalExperience::IModalExperienceDefaultOptions * *)
0x18001ed81  mov     ebx, eax
0x18001ed83  test    eax, eax
0x18001ed85  jns     short loc_18001EDA7
0x18001ed87  mov     edx, 1C5h; void *
0x18001ed8c  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\workflow"...
0x18001ed93  mov     r9d, eax; char *
0x18001ed96  mov     rcx, [rbp+88h]; this
0x18001ed9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eda2  jmp     loc_18001F166
0x18001eda7  mov     [rbp+80h+var_A8], 0
0x18001edaf  xor     r9d, r9d; unsigned int
0x18001edb2  lea     r8d, [r9+1]; unsigned int
0x18001edb6  lea     rdx, sourceString; sourceString
0x18001edbd  lea     rcx, [rbp+80h+hstringHeader]; hstringHeader
0x18001edc1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001edc6  nop
0x18001edc7  mov     r8, [rsi+10h]
0x18001edcb  mov     rax, [rdi+10h]
0x18001edcf  lea     rdx, [rax+1]
0x18001edd3  xorps   xmm0, xmm0
0x18001edd6  movups  [rbp+80h+var_60], xmm0
0x18001edda  xorps   xmm1, xmm1
0x18001eddd  movdqu  [rbp+80h+var_50], xmm1
0x18001ede2  cmp     r8, rdx
0x18001ede5  jb      loc_18001F1F2
0x18001edeb  not     rax
0x18001edee  add     rax, r8
0x18001edf1  sub     r8, rdx
0x18001edf4  cmp     r8, rax
0x18001edf7  cmovnb  r8, rax
0x18001edfb  mov     rcx, rsi
0x18001edfe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ee03  lea     rdx, [rax+rdx*2]
0x18001ee07  lea     rcx, [rbp+80h+var_60]
0x18001ee0b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001ee10  nop
0x18001ee11  lea     rcx, [rbp+80h+var_60]
0x18001ee15  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ee1a  mov     rdx, rax
0x18001ee1d  lea     rcx, [rbp+80h+var_E0]
0x18001ee21  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001ee26  nop
0x18001ee27  lea     rcx, [rbp+80h+var_60]
0x18001ee2b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ee30  mov     edi, [rbp+80h+var_D0]
0x18001ee33  lea     rcx, [rbp+80h+var_E0]
0x18001ee37  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ee3c  mov     rbx, rax
0x18001ee3f  mov     [rbp+80h+var_E8], 0
0x18001ee47  mov     ecx, edi; unsigned int
0x18001ee49  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18001ee4e  mov     r9d, edi; unsigned int
0x18001ee51  mov     r8d, eax; unsigned int
0x18001ee54  mov     rdx, rbx; sourceString
0x18001ee57  lea     rcx, [rbp+80h+var_100]; hstringHeader
0x18001ee5b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001ee60  nop
0x18001ee61  mov     rcx, [rsp+180h+var_128]
0x18001ee66  mov     rax, [rcx]
0x18001ee69  mov     rdx, [rbp+80h+var_E8]
0x18001ee6d  mov     rax, [rax+60h]
0x18001ee71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee76  mov     ebx, eax
0x18001ee78  xor     edi, edi
0x18001ee7a  test    eax, eax
0x18001ee7c  jns     short loc_18001EEB1
0x18001ee7e  mov     edx, 1CFh; void *
0x18001ee83  mov     rcx, [rbp+88h]; this
0x18001ee8a  mov     r9d, eax; char *
0x18001ee8d  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\workflow"...
0x18001ee94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ee99  nop
0x18001ee9a  mov     [rbp+80h+var_E8], rdi
0x18001ee9e  lea     rcx, [rbp+80h+var_E0]
0x18001eea2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001eea7  nop
0x18001eea8  mov     [rbp+80h+var_A8], rdi
0x18001eeac  jmp     loc_18001F166
0x18001eeb1  mov     rcx, [rsp+180h+var_128]
0x18001eeb6  mov     rax, [rcx]
0x18001eeb9  mov     dl, 1
0x18001eebb  mov     rax, [rax+50h]
0x18001eebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eec4  mov     ebx, eax
0x18001eec6  test    eax, eax
0x18001eec8  jns     short loc_18001EED1
0x18001eeca  mov     edx, 1D0h
0x18001eecf  jmp     short loc_18001EE83
0x18001eed1  test    r15b, r15b
0x18001eed4  jnz     short loc_18001EEF9
0x18001eed6  mov     rcx, [rsp+180h+var_128]
0x18001eedb  mov     rax, [rcx]
0x18001eede  mov     dl, 1
0x18001eee0  mov     rax, [rax+90h]
0x18001eee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eeec  mov     ebx, eax
0x18001eeee  test    eax, eax
0x18001eef0  jns     short loc_18001EEF9
0x18001eef2  mov     edx, 1D3h
0x18001eef7  jmp     short loc_18001EE83
0x18001eef9  mov     [rsp+180h+var_130], rdi
0x18001eefe  lea     rcx, [rsp+180h+var_130]
0x18001ef03  call    ?InternalRelease@?$ComPtr@UIModalExperienceManagerStatic@ModalExperience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(void)
0x18001ef08  mov     rdx, r13
0x18001ef0b  lea     rcx, [rsp+180h+var_130]
0x18001ef10  call    ??$MakeAndInitialize@VWorkflowUIActivatedEventArgsImpl@@UIPrintWorkflowUIActivatedEventArgs@Workflow@Printing@Graphics@Windows@@AEBV?$ComPtr@UIPrintWorkflowForegroundSession@Workflow@Printing@Graphics@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAUIPrintWorkflowUIActivatedEventArgs@Workflow@Printing@Graphics@Windows@@AEBV?$ComPtr@UIPrintWorkflowForegroundSession@Workflow@Printing@Graphics@Windows@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<WorkflowUIActivatedEventArgsImpl,Windows::Graphics::Printing::Workflow::IPrintWorkflowUIActivatedEventArgs,Microsoft::WRL::ComPtr<Windows::Graphics::Printing::Workflow::IPrintWorkflowForegroundSession> const &>(Windows::Graphics::Printing::Workflow::IPrintWorkflowUIActivatedEventArgs * *,Microsoft::WRL::ComPtr<Windows::Graphics::Printing::Workflow::IPrintWorkflowForegroundSession> const &)
0x18001ef15  mov     ebx, eax
0x18001ef17  xor     r13d, r13d
0x18001ef1a  test    eax, eax
0x18001ef1c  jns     short loc_18001EF3E
0x18001ef1e  mov     rcx, [rbp+88h]; this
0x18001ef25  mov     r9d, eax; char *
0x18001ef28  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\workflow"...
0x18001ef2f  mov     edx, 1D8h; void *
0x18001ef34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef39  jmp     loc_18001F149
0x18001ef3e  mov     rcx, rsi
0x18001ef41  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ef46  mov     [rsp+180h+var_110], rax
0x18001ef4b  lea     rdx, [rsp+180h+var_110]
0x18001ef50  lea     rcx, [rbp+80h+var_80]
0x18001ef54  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001ef59  nop
0x18001ef5a  mov     [rbp+80h+var_88], r13
0x18001ef5e  mov     r9d, 23h ; '#'; unsigned int
0x18001ef64  lea     r8d, [r9+1]; unsigned int
0x18001ef68  lea     rdx, aWindowsPrintwo_0; "Windows.PrintWorkflowForegroundTask"
0x18001ef6f  lea     rcx, [rbp+80h+var_A0]; hstringHeader
0x18001ef73  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001ef78  nop
0x18001ef79  lea     r15, [r14+60h]
0x18001ef7d  mov     rcx, r15
0x18001ef80  call    ?InternalRelease@?$ComPtr@UIModalExperienceManagerStatic@ModalExperience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(void)
0x18001ef85  mov     rcx, r15
0x18001ef88  call    ??$MakeAndInitialize@VCWorkflowModalExperienceManagerAppListener@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCWorkflowModalExperienceManagerAppListener@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CWorkflowModalExperienceManagerAppListener,CWorkflowModalExperienceManagerAppListener,>(CWorkflowModalExperienceManagerAppListener * *)
0x18001ef8d  mov     ebx, eax
0x18001ef8f  test    eax, eax
0x18001ef91  jns     short loc_18001EFB3
0x18001ef93  mov     edx, 1E3h; void *
0x18001ef98  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\workflow"...
0x18001ef9f  mov     r9d, eax; char *
0x18001efa2  mov     rcx, [rbp+88h]; this
0x18001efa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001efae  jmp     loc_18001F141
0x18001efb3  mov     rcx, rsi
0x18001efb6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001efbb  lea     rdx, [r14+4Ch]; unsigned __int16 *
0x18001efbf  mov     rcx, rax; this
0x18001efc2  call    ?IsAppBeingDebugged@ApiPolicyChecker@CallerIdentity@@YAJPEBGPEAH@Z; CallerIdentity::ApiPolicyChecker::IsAppBeingDebugged(ushort const *,int *)
0x18001efc7  mov     ebx, eax
0x18001efc9  test    eax, eax
0x18001efcb  jns     short loc_18001EFD4
0x18001efcd  mov     edx, 1E6h
0x18001efd2  jmp     short loc_18001EF98
0x18001efd4  mov     eax, cs:dword_180083038
0x18001efda  cmp     eax, 5
0x18001efdd  jbe     short loc_18001F004
0x18001efdf  mov     eax, [r14+4Ch]
0x18001efe3  mov     dword ptr [rsp+180h+var_110], eax
0x18001efe7  lea     rax, [rsp+180h+var_110]
0x18001efec  mov     qword ptr [rsp+180h+var_160], rax
0x18001eff1  lea     rdx, word_180072042
0x18001eff8  lea     rcx, dword_180083038
0x18001efff  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001f004  mov     [rsp+180h+var_108], r13
0x18001f009  lea     rdx, [rsp+180h+var_108]
0x18001f00e  xor     ecx, ecx
0x18001f010  call    cs:__imp_UMgrQueryUserContext
0x18001f016  mov     esi, eax
0x18001f018  mov     [rsp+180h+var_120], r13
0x18001f01d  mov     rbx, [rsp+180h+var_118]
0x18001f022  mov     rcx, [rbx]
0x18001f025  mov     rdi, [rcx]
0x18001f028  lea     rcx, [rsp+180h+var_120]
0x18001f02d  call    ?InternalRelease@?$ComPtr@UIModalExperienceManagerStatic@ModalExperience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(void)
0x18001f032  lea     r8, [rsp+180h+var_120]
0x18001f037  lea     rdx, _GUID_50c6090b_023e_4fde_b226_57c3e26d2881
0x18001f03e  mov     rcx, rbx
0x18001f041  mov     rax, rdi
0x18001f044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f049  nop
0x18001f04a  test    esi, esi
0x18001f04c  js      short loc_18001F0B4
0x18001f04e  test    eax, eax
0x18001f050  js      short loc_18001F0B4
0x18001f052  mov     rcx, [rsp+180h+var_120]
0x18001f057  mov     rbx, [rsp+180h+var_108]
0x18001f05c  mov     rdx, [r15]
0x18001f05f  mov     rdi, [rsp+180h+var_128]
0x18001f064  mov     r10, [rcx]
0x18001f067  lea     r11, [r14+58h]
0x18001f06b  lea     rax, [rdx+8]
0x18001f06f  neg     rdx
0x18001f072  sbb     r8, r8
0x18001f075  and     r8, rax
0x18001f078  mov     [rsp+180h+var_140], r11
0x18001f07d  mov     [rsp+180h+var_148], rbx
0x18001f082  mov     [rsp+180h+var_150], r8
0x18001f087  mov     [rsp+180h+var_158], r12d
0x18001f08c  mov     qword ptr [rsp+180h+var_160], rdi; int
0x18001f091  mov     r9, [rsp+180h+var_130]
0x18001f096  mov     r8, [rbp+80h+var_88]
0x18001f09a  mov     rdx, [rbp+80h+var_68]
0x18001f09e  mov     rax, [r10+30h]
0x18001f0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0a7  mov     ebx, eax
0x18001f0a9  test    eax, eax
0x18001f0ab  jns     short loc_18001F10C
0x18001f0ad  mov     edx, 208h
0x18001f0b2  jmp     short loc_18001F11F
0x18001f0b4  mov     rcx, [rsp+180h+var_118]
0x18001f0b9  mov     rdx, [r15]
0x18001f0bc  mov     r11, [rsp+180h+var_128]
0x18001f0c1  mov     r8, [rcx]
0x18001f0c4  lea     r10, [r14+58h]
0x18001f0c8  lea     rax, [rdx+8]
0x18001f0cc  neg     rdx
0x18001f0cf  sbb     rdx, rdx
0x18001f0d2  and     rdx, rax
0x18001f0d5  mov     rax, [r8+38h]
0x18001f0d9  mov     [rsp+180h+var_148], r10
0x18001f0de  mov     [rsp+180h+var_150], rdx
0x18001f0e3  mov     [rsp+180h+var_158], r12d
0x18001f0e8  mov     qword ptr [rsp+180h+var_160], r11
0x18001f0ed  mov     r9, [rsp+180h+var_130]
0x18001f0f2  mov     r8, [rbp+80h+var_88]
0x18001f0f6  mov     rdx, [rbp+80h+var_68]
0x18001f0fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0ff  mov     ebx, eax
0x18001f101  test    eax, eax
0x18001f103  jns     short loc_18001F10C
0x18001f105  mov     edx, 1FCh
0x18001f10a  jmp     short loc_18001F11F
0x18001f10c  mov     rcx, [r15]; this
0x18001f10f  call    ?WaitForViewVisible@CWorkflowModalExperienceManagerAppListener@@QEAAJXZ; CWorkflowModalExperienceManagerAppListener::WaitForViewVisible(void)
0x18001f114  mov     ebx, eax
0x18001f116  test    eax, eax
0x18001f118  jns     short loc_18001F17F
0x18001f11a  mov     edx, 20Bh; void *
0x18001f11f  mov     r9d, eax; char *
0x18001f122  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\workflow"...
0x18001f129  mov     rcx, [rbp+88h]; this
0x18001f130  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f135  nop
0x18001f136  lea     rcx, [rsp+180h+var_120]
0x18001f13b  call    ?InternalRelease@?$ComPtr@UIModalExperienceManagerStatic@ModalExperience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(void)
0x18001f140  nop
0x18001f141  mov     [rbp+80h+var_88], r13
0x18001f145  mov     [rbp+80h+var_68], r13
0x18001f149  lea     rcx, [rsp+180h+var_130]
0x18001f14e  call    ?InternalRelease@?$ComPtr@UIModalExperienceManagerStatic@ModalExperience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(void)
0x18001f153  nop
0x18001f154  mov     [rbp+80h+var_E8], r13
0x18001f158  lea     rcx, [rbp+80h+var_E0]
0x18001f15c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f161  nop
0x18001f162  mov     [rbp+80h+var_A8], r13
  ... truncated ...
```
