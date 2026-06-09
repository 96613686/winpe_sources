# InstallItems(TraceLoggingCorrelationVector *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ProductInstallRequest,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ProductInstallRequest>>> const &,unsigned __int64,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,long,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,long>>> &)

- ea: `0x1800322d8`
- end: `0x18003298e`
- name: `?InstallItems@@YAXPEAVTraceLoggingCorrelationVector@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@@std@@@2@@std@@_KAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@3@@Z`
- size: `1718`
- prototype: `void __fastcall(TraceLoggingCorrelationVector *this, __int64 ***, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180032ac0`
- `0x180032cfc`

## callees

- `0x1800026b0`
- `0x18000d75c`
- `0x18000dc67`
- `0x18002008c`
- `0x18002c4b8`
- `0x18002ce54`
- `0x18002f028`
- `0x18002fbb4`
- `0x180030aac`
- `0x180031798`
- `0x18003182c`
- `0x180031ac0`
- `0x1800322d8`
- `0x180032fac`
- `0x1800331dc`
- `0x18004f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x180032474`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x180032474`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003234e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003250b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180032554`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003234e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003250b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180032554`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18003239b`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18003239b`

## string_xrefs

- `0x18003264a`: `onecoreuap\enduser\winstore\pushtoinstall\lib\pushtoinstall.cpp`
- `0x180032925`: `onecoreuap\enduser\winstore\pushtoinstall\lib\pushtoinstall.cpp`
- `0x18003293a`: `onecoreuap\enduser\winstore\pushtoinstall\lib\pushtoinstall.cpp`
- `0x18003295f`: `onecoreuap\enduser\winstore\pushtoinstall\lib\pushtoinstall.cpp`
- `0x18003263d`: `InstallItems`
- `0x180032347`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`

## pseudocode

```c
void __fastcall InstallItems(TraceLoggingCorrelationVector *this, __int64 ***a2, __int64 a3, _QWORD *a4)
{
  int v4; // ebx
  _QWORD *v5; // r12
  TraceLoggingCorrelationVector *v7; // r14
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  wil::details::in1diag3 *v11; // rcx
  __int64 *v12; // rbx
  _QWORD *v13; // rsi
  int v14; // eax
  unsigned int v15; // r8d
  unsigned __int64 v16; // rdx
  _QWORD *v17; // r15
  __int64 v18; // r14
  HRESULT v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  HRESULT v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  int v25; // r13d
  _QWORD *v26; // r14
  _QWORD *v27; // rax
  __int64 v28; // rax
  int v29; // eax
  wil::details::in1diag3 *v30; // rcx
  int v31; // r15d
  _QWORD *v32; // r14
  _QWORD *v33; // rsi
  int v34; // r15d
  _QWORD *v35; // r13
  __int64 v36; // rsi
  _OWORD *v37; // rax
  __int64 (__fastcall ***v38)(_QWORD, GUID *, _QWORD); // rcx
  _QWORD *v39; // rcx
  __int64 **v40; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 (__fastcall ***v43)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v44; // rax
  __int64 v45; // [rsp+38h] [rbp-310h]
  int v46; // [rsp+20h] [rbp-328h]
  int v47; // [rsp+20h] [rbp-328h]
  __int64 v48; // [rsp+38h] [rbp-310h]
  __int64 v49; // [rsp+40h] [rbp-308h]
  HSTRING v50; // [rsp+48h] [rbp-300h]
  __int64 (__fastcall ***v51)(_QWORD, GUID *, _QWORD **); // [rsp+78h] [rbp-2D0h] BYREF
  __int64 (__fastcall ***v52)(_QWORD, GUID *, _QWORD **); // [rsp+80h] [rbp-2C8h] BYREF
  _QWORD *v53; // [rsp+88h] [rbp-2C0h] BYREF
  __int64 *v54; // [rsp+90h] [rbp-2B8h]
  __int64 (__fastcall *v55)(_QWORD *, _QWORD, _QWORD, _QWORD); // [rsp+98h] [rbp-2B0h]
  TraceLoggingCorrelationVector *v56; // [rsp+A0h] [rbp-2A8h]
  __int64 v57; // [rsp+A8h] [rbp-2A0h] BYREF
  _QWORD *v58; // [rsp+B0h] [rbp-298h] BYREF
  HSTRING v59; // [rsp+B8h] [rbp-290h]
  __int64 *v60; // [rsp+C0h] [rbp-288h]
  TraceLoggingCorrelationVector *v61; // [rsp+C8h] [rbp-280h]
  _QWORD *v62; // [rsp+D0h] [rbp-278h]
  _QWORD *v63; // [rsp+E0h] [rbp-268h] BYREF
  int v64; // [rsp+E8h] [rbp-260h]
  int v65; // [rsp+ECh] [rbp-25Ch]
  _QWORD *v66; // [rsp+F0h] [rbp-258h]
  __int64 v67; // [rsp+F8h] [rbp-250h]
  const wil::ResultException *v68; // [rsp+100h] [rbp-248h] BYREF
  __int128 v69; // [rsp+108h] [rbp-240h] BYREF
  __int64 v70; // [rsp+118h] [rbp-230h]
  __int64 v71; // [rsp+120h] [rbp-228h]
  int v72; // [rsp+128h] [rbp-220h]
  HSTRING_HEADER v73; // [rsp+130h] [rbp-218h] BYREF
  HSTRING v74; // [rsp+148h] [rbp-200h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+150h] [rbp-1F8h] BYREF
  HSTRING string; // [rsp+168h] [rbp-1E0h] BYREF
  char Destination[144]; // [rsp+170h] [rbp-1D8h] BYREF
  WCHAR sourceString[136]; // [rsp+200h] [rbp-148h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+0h]

  v5 = a4;
  v7 = this;
  v56 = this;
  v61 = this;
  v62 = a4;
  v52 = 0;
  v74 = 0;
  v8 = WindowsCreateStringReference(
         L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager",
         0x47u,
         &v73,
         &v74);
  if ( v8 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    goto LABEL_56;
  }
  v52 = 0;
  v51 = 0;
  v4 = RoActivateInstance(v74, &v51);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_9353e170_8441_4b45_bd72_7c2fa925beee, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v52 = v51;
    }
    else
    {
      v4 = (**v51)(v51, &GUID_9353e170_8441_4b45_bd72_7c2fa925beee, &v52);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v51)[2])(v51);
    }
  }
  v11 = retaddr;
  if ( v4 < 0 )
LABEL_56:
    wil::details::in1diag3::_Throw_Hr(
      v11,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\pushtoinstall.cpp",
      (const char *)(unsigned int)v4,
      v46);
  v12 = **a2;
  while ( 1 )
  {
    v54 = v12;
    if ( *((_BYTE *)v12 + 25) )
      break;
    v13 = v12 + 4;
    v60 = v12 + 4;
    TraceLoggingCorrelationVector::Increment(v7, Destination);
    v57 = 0;
    v47 = 129;
    _o_mbstowcs_s(&v57, sourceString, 129, Destination);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v53 = 0;
      v14 = (**v52)(v52, &GUID_e5362e53_1657_4c6c_b537_ddb132eb14de, &v53);
      if ( v14 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x2D,
          (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\pushtoinstall.cpp",
          (const char *)(unsigned int)v14,
          129);
      v51 = 0;
      v16 = -1;
      do
        ++v16;
      while ( sourceString[v16] );
      if ( v16 > 0xFFFFFFFF )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v16, v15);
        JUMPOUT(0x18003298CLL);
      }
      if ( (int)v16 + 1 < (unsigned int)v16 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v16, v15);
        __debugbreak();
      }
      v17 = v53;
      v18 = *v53;
      v19 = WindowsCreateStringReference(sourceString, v16, &hstringHeader, &string);
      if ( v19 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
LABEL_59:
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
LABEL_60:
        wil::details::in1diag3::_Throw_Hr(
          v30,
          (void *)0x3C,
          (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\pushtoinstall.cpp",
          (const char *)(unsigned int)v29,
          v47);
      }
      v59 = string;
      v74 = 0;
      v22 = WindowsCreateStringReference(L"PTIClient", 9u, &v73, &v74);
      if ( v22 < 0 )
        goto LABEL_59;
      v55 = *(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, _QWORD))(v18 + 56);
      v25 = (int)v74;
      v26 = v12 + 8;
      if ( (unsigned __int64)v12[11] <= 7 )
        v27 = v12 + 8;
      else
        v27 = (_QWORD *)*v26;
      v58 = v27;
      v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v69, &v58);
      v50 = v59;
      LOBYTE(v49) = 0;
      LOBYTE(v48) = 0;
      v47 = v25;
      v29 = v55(v17, *(_QWORD *)(v28 + 24), 0, 0);
      v30 = retaddr;
      if ( v29 < 0 )
        goto LABEL_60;
      v31 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>>(v51);
      if ( v31 >= 0 )
      {
        if ( (unsigned __int64)v12[11] > 7 )
          v26 = (_QWORD *)*v26;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\pushtoinstall.cpp",
          0x41u,
          "InstallItems",
          -1,
          L"Product (with id: %s) queued successfully.",
          v26,
          v48,
          v49,
          v50,
          0,
          &v51);
      }
      v69 = 0;
      v70 = 0;
      v71 = 0;
      if ( (unsigned __int64)v12[7] > 7 )
        v13 = (_QWORD *)*v13;
      std::wstring::_Construct<2,unsigned short const *>(&v69, v13, v12[6]);
      v72 = v31;
      v32 = (_QWORD *)*v5;
      v33 = *(_QWORD **)(*v5 + 8LL);
      v34 = 0;
      v55 = 0;
      if ( *((_BYTE *)v33 + 25) )
      {
        v35 = v33;
      }
      else
      {
        do
        {
          v35 = v33;
          v73.Reserved.Reserved1 = v33;
          if ( (unsigned __int8)std::operator<<unsigned short>(v33 + 4, &v69) )
          {
            v34 = 0;
            v33 = (_QWORD *)v33[2];
          }
          else
          {
            v34 = 1;
            v32 = v33;
            v33 = (_QWORD *)*v33;
          }
        }
        while ( !*((_BYTE *)v33 + 25) );
      }
      if ( *((_BYTE *)v32 + 25) || (unsigned __int8)std::operator<<unsigned short>(&v69, v32 + 4) )
      {
        if ( v5[1] == 0x38E38E38E38E38ELL )
          std::_Throw_tree_length_error();
        v36 = *v5;
        v66 = v5;
        v67 = 0;
        v37 = operator new(0x48u);
        v37[2] = v69;
        *((_QWORD *)v37 + 6) = v70;
        *((_QWORD *)v37 + 7) = v71;
        v70 = 0;
        v71 = 7;
        LOWORD(v69) = 0;
        *((_DWORD *)v37 + 16) = v72;
        *(_QWORD *)v37 = v36;
        *((_QWORD *)v37 + 1) = v36;
        *((_QWORD *)v37 + 2) = v36;
        *((_WORD *)v37 + 12) = 0;
        v67 = 0;
        v63 = v35;
        v64 = v34;
        v65 = (int)v55;
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,long>>>::_Insert_node(v5, &v63);
      }
      std::wstring::_Tidy_deallocate(&v69);
      v38 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD))v51;
      if ( v51 )
      {
        v51 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v38)[2])(v38);
      }
      v39 = v53;
      if ( v53 )
      {
        v53 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v39 + 16LL))(v39);
      }
      v7 = v56;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &wil::ResultException `RTTI Type Descriptor', &v68) )
      {
        v44 = v60 + 4;
        if ( (unsigned __int64)v60[7] > 7 )
          v44 = (_QWORD *)*v44;
        LODWORD(v45) = *((_BYTE *)v60 + 64) != 0;
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\pushtoinstall.cpp",
          0x4Au,
          "InstallItems",
          *((_DWORD *)v68 + 8),
          L"Installation failed for item with storeId %s, isInteractive = %u",
          v44,
          v45);
        v12 = v54;
        v7 = v61;
        v56 = v61;
        v5 = v62;
        __eh34_try_continuation(0, &wil::ResultException `RTTI Type Descriptor', &loc_18003285A);
      }
    }
    v40 = (__int64 **)v12[2];
    if ( *((_BYTE *)v40 + 25) )
    {
      for ( i = (__int64 *)v12[1]; !*((_BYTE *)i + 25) && v12 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v12 = i;
      v12 = i;
    }
    else
    {
      v12 = (__int64 *)v12[2];
      for ( j = *v40; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v12 = j;
    }
  }
  v43 = v52;
  if ( v52 )
  {
    v52 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v43)[2])(v43);
  }
}

```

## disassembly

```asm
0x1800322d8  mov     r11, rsp
0x1800322db  mov     [r11+10h], rbx
0x1800322df  mov     [r11+18h], rsi
0x1800322e3  push    rdi
0x1800322e4  push    r12
0x1800322e6  push    r13
0x1800322e8  push    r14
0x1800322ea  push    r15
0x1800322ec  sub     rsp, 320h
0x1800322f3  mov     rax, cs:__security_cookie
0x1800322fa  xor     rax, rsp
0x1800322fd  mov     [rsp+348h+var_38], rax
0x180032305  mov     r12, r9
0x180032308  mov     rsi, rdx
0x18003230b  mov     r14, rcx
0x18003230e  mov     [rsp+348h+var_2A8], rcx
0x180032316  mov     [rsp+348h+var_280], rcx
0x18003231e  mov     [rsp+348h+var_278], r9
0x180032326  xor     edi, edi
0x180032328  mov     [r11-2C8h], rdi
0x18003232f  mov     [r11-200h], rdi
0x180032336  lea     r9, [r11-200h]; string
0x18003233d  lea     r8, [r11-218h]; hstringHeader
0x180032344  lea     edx, [rdi+47h]; length
0x180032347  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallManager@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x18003234e  call    cs:__imp_WindowsCreateStringReference
0x180032354  test    eax, eax
0x180032356  js      loc_18003291A
0x18003235c  mov     rbx, [rsp+348h+var_200]
0x180032364  mov     rcx, [rsp+348h+var_2C8]
0x18003236c  test    rcx, rcx
0x18003236f  jz      short loc_180032386
0x180032371  mov     [rsp+348h+var_2C8], rdi
0x180032379  mov     rax, [rcx]
0x18003237c  mov     rax, [rax+10h]
0x180032380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032385  nop
0x180032386  mov     [rsp+348h+var_2C8], rdi
0x18003238e  mov     [rsp+348h+var_2D0], rdi
0x180032393  lea     rdx, [rsp+348h+var_2D0]
0x180032398  mov     rcx, rbx
0x18003239b  call    cs:__imp_RoActivateInstance
0x1800323a1  mov     ebx, eax
0x1800323a3  test    eax, eax
0x1800323a5  js      short loc_180032401
0x1800323a7  mov     r8d, 10h; Size
0x1800323ad  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800323b4  lea     rcx, _GUID_9353e170_8441_4b45_bd72_7c2fa925beee; Buf1
0x1800323bb  call    memcmp_0
0x1800323c0  mov     rcx, [rsp+348h+var_2D0]
0x1800323c5  test    eax, eax
0x1800323c7  jnz     short loc_1800323D3
0x1800323c9  mov     [rsp+348h+var_2C8], rcx
0x1800323d1  jmp     short loc_180032401
0x1800323d3  mov     rax, [rcx]
0x1800323d6  lea     r8, [rsp+348h+var_2C8]
0x1800323de  lea     rdx, _GUID_9353e170_8441_4b45_bd72_7c2fa925beee
0x1800323e5  mov     rax, [rax]
0x1800323e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323ed  mov     ebx, eax
0x1800323ef  mov     rcx, [rsp+348h+var_2D0]
0x1800323f4  mov     rax, [rcx]
0x1800323f7  mov     rax, [rax+10h]
0x1800323fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032400  nop
0x180032401  mov     rcx, [rsp+348h]
0x180032409  test    ebx, ebx
0x18003240b  js      loc_180032922
0x180032411  mov     rbx, [rsi]
0x180032414  mov     rbx, [rbx]
0x180032417  mov     [rsp+348h+var_2B8], rbx
0x18003241f  cmp     [rbx+19h], dil
0x180032423  jnz     loc_1800328CB
0x180032429  lea     rsi, [rbx+20h]
0x18003242d  mov     [rsp+348h+var_288], rsi
0x180032435  lea     rdx, [rsp+348h+Destination]; Destination
0x18003243d  mov     rcx, r14; this
0x180032440  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x180032445  mov     [rsp+348h+var_2A0], rdi
0x18003244d  mov     qword ptr [rsp+348h+var_328], 81h; int
0x180032456  lea     r9, [rsp+348h+Destination]
0x18003245e  mov     r8d, 81h
0x180032464  lea     rdx, [rsp+348h+sourceString]
0x18003246c  lea     rcx, [rsp+348h+var_2A0]
0x180032474  call    cs:__imp__o_mbstowcs_s
0x18003247a  mov     [rsp+348h+var_2C0], rdi
0x180032482  mov     rcx, [rsp+348h+var_2C8]
0x18003248a  mov     rax, [rcx]
0x18003248d  lea     r8, [rsp+348h+var_2C0]
0x180032495  lea     rdx, _GUID_e5362e53_1657_4c6c_b537_ddb132eb14de
0x18003249c  mov     rax, [rax]
0x18003249f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324a4  nop
0x1800324a5  mov     rcx, [rsp+348h]; this
0x1800324ad  test    eax, eax
0x1800324af  js      loc_180032937
0x1800324b5  mov     [rsp+348h+var_2D0], rdi
0x1800324ba  lea     rax, [rsp+348h+sourceString]
0x1800324c2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800324c6  inc     rdx; int
0x1800324c9  cmp     [rax+rdx*2], di
0x1800324cd  jnz     short loc_1800324C6
0x1800324cf  mov     eax, 0FFFFFFFFh
0x1800324d4  cmp     rdx, rax
0x1800324d7  ja      loc_180032982
0x1800324dd  lea     eax, [rdx+1]
0x1800324e0  cmp     eax, edx
0x1800324e2  jb      loc_180032977
0x1800324e8  mov     r15, [rsp+348h+var_2C0]
0x1800324f0  mov     r14, [r15]
0x1800324f3  lea     r9, [rsp+348h+string]; string
0x1800324fb  lea     r8, [rsp+348h+hstringHeader]; hstringHeader
0x180032503  lea     rcx, [rsp+348h+sourceString]; sourceString
0x18003250b  call    cs:__imp_WindowsCreateStringReference
0x180032511  test    eax, eax
0x180032513  js      loc_18003294C
0x180032519  mov     rax, [rsp+348h+string]
0x180032521  mov     [rsp+348h+var_290], rax
0x180032529  mov     al, [rsi+40h]
0x18003252c  mov     [rsp+348h+var_2D8], al
0x180032530  mov     [rsp+348h+var_200], rdi
0x180032538  lea     r9, [rsp+348h+var_200]; string
0x180032540  lea     r8, [rsp+348h+var_218]; hstringHeader
0x180032548  mov     edx, 9; length
0x18003254d  lea     rcx, aPticlient; "PTIClient"
0x180032554  call    cs:__imp_WindowsCreateStringReference
0x18003255a  test    eax, eax
0x18003255c  js      loc_180032954
0x180032562  mov     rax, [r14+38h]
0x180032566  mov     [rsp+348h+var_2B0], rax
0x18003256e  mov     r13, [rsp+348h+var_200]
0x180032576  lea     r14, [rsi+20h]
0x18003257a  cmp     qword ptr [r14+18h], 7
0x18003257f  jbe     short loc_180032586
0x180032581  mov     rax, [r14]
0x180032584  jmp     short loc_180032589
0x180032586  mov     rax, r14
0x180032589  mov     [rsp+348h+var_298], rax
0x180032591  lea     rdx, [rsp+348h+var_298]
0x180032599  lea     rcx, [rsp+348h+var_240]
0x1800325a1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800325a6  nop
0x1800325a7  lea     rcx, [rsp+348h+var_2D0]
0x1800325ac  mov     [rsp+348h+var_2F0], rcx
0x1800325b1  mov     [rsp+348h+var_2F8], rdi
0x1800325b6  mov     rcx, [rsp+348h+var_290]
0x1800325be  mov     [rsp+348h+var_300], rcx
0x1800325c3  mov     byte ptr [rsp+348h+var_308], dil
0x1800325c8  mov     byte ptr [rsp+348h+var_310], dil
0x1800325cd  mov     cl, [rsp+348h+var_2D8]
0x1800325d1  mov     byte ptr [rsp+348h+var_318], cl
0x1800325d5  mov     byte ptr [rsp+348h+var_320], dil
0x1800325da  mov     qword ptr [rsp+348h+var_328], r13
0x1800325df  xor     r9d, r9d
0x1800325e2  xor     r8d, r8d
0x1800325e5  mov     rdx, [rax+18h]
0x1800325e9  mov     rcx, r15
0x1800325ec  mov     rax, [rsp+348h+var_2B0]
0x1800325f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325f9  mov     rcx, [rsp+348h]
0x180032601  test    eax, eax
0x180032603  js      loc_18003295C
0x180032609  mov     rcx, [rsp+348h+var_2D0]
0x18003260e  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *,tagCOWAIT_FLAGS,void *)
0x180032613  mov     r15d, eax
0x180032616  test    eax, eax
0x180032618  js      short loc_18003265A
0x18003261a  cmp     qword ptr [r14+18h], 7
0x18003261f  jbe     short loc_180032624
0x180032621  mov     r14, [r14]
0x180032624  mov     [rsp+348h+var_318], r14
0x180032629  lea     rax, aProductWithIdS; "Product (with id: %s) queued successful"...
0x180032630  mov     [rsp+348h+var_320], rax; unsigned __int16 *
0x180032635  mov     [rsp+348h+var_328], 0FFFFFFFFh; int
0x18003263d  lea     r9, aInstallitems; "InstallItems"
0x180032644  mov     r8d, 41h ; 'A'; unsigned int
0x18003264a  lea     rdx, aOnecoreuapEndu_9; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180032651  lea     ecx, [r8-3Eh]; unsigned int
0x180032655  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x18003265a  xorps   xmm0, xmm0
0x18003265d  movups  [rsp+348h+var_240], xmm0
0x180032665  mov     [rsp+348h+var_230], rdi
0x18003266d  mov     [rsp+348h+var_228], rdi
0x180032675  mov     r8, [rsi+10h]
0x180032679  cmp     qword ptr [rsi+18h], 7
0x18003267e  jbe     short loc_180032683
0x180032680  mov     rsi, [rsi]
0x180032683  mov     rdx, rsi
0x180032686  lea     rcx, [rsp+348h+var_240]
0x18003268e  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180032693  mov     [rsp+348h+var_220], r15d
0x18003269b  mov     r14, [r12]
0x18003269f  mov     rsi, [r14+8]
0x1800326a3  mov     r15d, edi
0x1800326a6  xor     eax, eax
0x1800326a8  mov     [rsp+348h+var_2B0], rax
0x1800326b0  cmp     [rsi+19h], dil
0x1800326b4  jnz     short loc_1800326F3
0x1800326b6  mov     r13, rsi
0x1800326b9  mov     qword ptr [rsp+348h+var_218.Reserved], rsi
0x1800326c1  lea     rcx, [rsi+20h]
0x1800326c5  lea     rdx, [rsp+348h+var_240]
0x1800326cd  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x1800326d2  test    al, al
0x1800326d4  jz      short loc_1800326DF
0x1800326d6  mov     r15d, edi
0x1800326d9  mov     rsi, [rsi+10h]
0x1800326dd  jmp     short loc_1800326EB
0x1800326df  mov     r15d, 1
0x1800326e5  mov     r14, rsi
0x1800326e8  mov     rsi, [rsi]
0x1800326eb  cmp     [rsi+19h], dil
0x1800326ef  jz      short loc_1800326B6
0x1800326f1  jmp     short loc_1800326F6
0x1800326f3  mov     r13, rsi
0x1800326f6  cmp     [r14+19h], dil
0x1800326fa  jnz     short loc_180032715
0x1800326fc  lea     rdx, [r14+20h]
0x180032700  lea     rcx, [rsp+348h+var_240]
0x180032708  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18003270d  test    al, al
0x18003270f  jz      loc_180032804
0x180032715  mov     rax, 38E38E38E38E38Eh
0x18003271f  cmp     [r12+8], rax
0x180032724  jz      loc_180032971
0x18003272a  mov     rsi, [r12]
0x18003272e  mov     [rsp+348h+var_258], r12
0x180032736  mov     [rsp+348h+var_250], rdi
0x18003273e  mov     ecx, 48h ; 'H'; Size
0x180032743  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032748  mov     r8, rax
0x18003274b  movzx   ecx, word ptr [rsp+348h+var_240]
0x180032753  mov     [rax+20h], cx
0x180032757  movsd   xmm0, qword ptr [rsp+348h+var_240+2]
0x180032760  movsd   qword ptr [rax+22h], xmm0
0x180032765  mov     ecx, dword ptr [rsp+348h+var_240+0Ah]
0x18003276c  mov     [rax+2Ah], ecx
0x18003276f  movzx   ecx, word ptr [rsp+348h+var_240+0Eh]
0x180032777  mov     [rax+2Eh], cx
0x18003277b  mov     rcx, [rsp+348h+var_230]
0x180032783  mov     [rax+30h], rcx
0x180032787  mov     rax, [rsp+348h+var_228]
0x18003278f  mov     [r8+38h], rax
0x180032793  mov     [rsp+348h+var_230], rdi
0x18003279b  mov     [rsp+348h+var_228], 7
0x1800327a7  mov     word ptr [rsp+348h+var_240], di
0x1800327af  mov     eax, [rsp+348h+var_220]
0x1800327b6  mov     [r8+40h], eax
0x1800327ba  mov     [r8], rsi
0x1800327bd  mov     [r8+8], rsi
0x1800327c1  mov     [r8+10h], rsi
0x1800327c5  mov     word ptr [r8+18h], 0
0x1800327cc  mov     [rsp+348h+var_250], rdi
0x1800327d4  mov     [rsp+348h+var_268], r13
0x1800327dc  mov     [rsp+348h+var_260], r15d
0x1800327e4  mov     rax, [rsp+348h+var_2B0]
0x1800327ec  mov     [rsp+348h+var_25C], eax
0x1800327f3  lea     rdx, [rsp+348h+var_268]
0x1800327fb  mov     rcx, r12
0x1800327fe  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,long>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,long>,void *> *>,std::_Tree_node<std::pair<std::wstring const,long>,void *> * const)
0x180032803  nop
0x180032804  lea     rcx, [rsp+348h+var_240]
0x18003280c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180032811  nop
0x180032812  mov     rcx, [rsp+348h+var_2D0]
0x180032817  test    rcx, rcx
0x18003281a  jz      short loc_18003282E
0x18003281c  mov     [rsp+348h+var_2D0], rdi
0x180032821  mov     rax, [rcx]
0x180032824  mov     rax, [rax+10h]
0x180032828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003282d  nop
0x18003282e  mov     rcx, [rsp+348h+var_2C0]
0x180032836  test    rcx, rcx
0x180032839  jz      short loc_180032850
0x18003283b  mov     [rsp+348h+var_2C0], rdi
0x180032843  mov     rax, [rcx]
0x180032846  mov     rax, [rax+10h]
0x18003284a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003284f  nop
0x180032850  mov     r14, [rsp+348h+var_2A8]
0x180032858  jmp     short loc_18003287C
0x18003285a  xor     edi, edi
0x18003285c  mov     rbx, [rsp+348h+var_2B8]
0x180032864  mov     r14, [rsp+348h+var_280]
0x18003286c  mov     [rsp+348h+var_2A8], r14
0x180032874  mov     r12, [rsp+348h+var_278]
0x18003287c  mov     rcx, [rbx+10h]
0x180032880  cmp     [rcx+19h], dil
0x180032884  jz      short loc_1800328A7
0x180032886  mov     rax, [rbx+8]
0x18003288a  jmp     short loc_180032899
0x18003288c  cmp     rbx, [rax+10h]
0x180032890  jnz     short loc_18003289F
0x180032892  mov     rbx, rax
0x180032895  mov     rax, [rax+8]
0x180032899  cmp     [rax+19h], dil
0x18003289d  jz      short loc_18003288C
0x18003289f  mov     rbx, rax
0x1800328a2  jmp     loc_180032417
  ... truncated ...
```
