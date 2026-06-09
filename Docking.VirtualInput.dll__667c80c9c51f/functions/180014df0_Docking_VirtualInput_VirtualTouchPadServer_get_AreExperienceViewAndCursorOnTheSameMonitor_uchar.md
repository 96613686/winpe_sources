# Docking::VirtualInput::VirtualTouchPadServer::get_AreExperienceViewAndCursorOnTheSameMonitor(uchar *)

- ea: `0x180014df0`
- end: `0x180015341`
- name: `?get_AreExperienceViewAndCursorOnTheSameMonitor@VirtualTouchPadServer@VirtualInput@Docking@@UEAAJPEAE@Z`
- size: `1361`
- prototype: `__int64 __fastcall(Docking::VirtualInput::VirtualTouchPadServer *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800036a0`
- `0x180004ba0`
- `0x1800067a4`
- `0x18000bf4c`
- `0x18000c830`
- `0x18000cd44`
- `0x18000cdc0`
- `0x18000cdf4`
- `0x180014580`
- `0x1800146a8`
- `0x180014718`
- `0x18001482c`
- `0x180014850`
- `0x180014b08`
- `0x180014df0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014e80`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014e80`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Docking::VirtualInput::VirtualTouchPadServer::get_AreExperienceViewAndCursorOnTheSameMonitor(
        Docking::VirtualInput::VirtualTouchPadServer *this,
        unsigned __int8 *a2)
{
  _QWORD *v2; // rax
  unsigned int Instance; // eax
  _QWORD *v5; // rax
  unsigned int v6; // eax
  __int64 v7; // rax
  unsigned int v8; // eax
  _QWORD *v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // eax
  int ppv; // [rsp+20h] [rbp-148h]
  char v13[8]; // [rsp+30h] [rbp-138h] BYREF
  char v14[8]; // [rsp+38h] [rbp-130h] BYREF
  char v15[8]; // [rsp+40h] [rbp-128h] BYREF
  int v16; // [rsp+48h] [rbp-120h]
  int v17; // [rsp+4Ch] [rbp-11Ch]
  int v18; // [rsp+50h] [rbp-118h]
  int v19; // [rsp+54h] [rbp-114h]
  int v20; // [rsp+58h] [rbp-110h]
  int v21; // [rsp+5Ch] [rbp-10Ch]
  int v22; // [rsp+60h] [rbp-108h]
  int v23; // [rsp+64h] [rbp-104h]
  int v24; // [rsp+68h] [rbp-100h]
  int v25; // [rsp+6Ch] [rbp-FCh]
  char *v26; // [rsp+70h] [rbp-F8h] BYREF
  DWORD dwClsContext; // [rsp+78h] [rbp-F0h]
  unsigned int v28; // [rsp+7Ch] [rbp-ECh]
  unsigned int v29; // [rsp+80h] [rbp-E8h]
  unsigned int v30; // [rsp+84h] [rbp-E4h]
  unsigned int v31; // [rsp+88h] [rbp-E0h]
  unsigned int v32; // [rsp+8Ch] [rbp-DCh]
  unsigned int v33; // [rsp+90h] [rbp-D8h]
  __int64 v34; // [rsp+98h] [rbp-D0h]
  __int64 v35; // [rsp+A0h] [rbp-C8h]
  __int64 v36; // [rsp+A8h] [rbp-C0h]
  LPVOID *v37; // [rsp+B0h] [rbp-B8h]
  __int64 (__fastcall *v38)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+B8h] [rbp-B0h]
  __int64 v39; // [rsp+C0h] [rbp-A8h]
  __int64 (__fastcall *v40)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+C8h] [rbp-A0h]
  Microsoft::WRL::Wrappers::HStringReference *v41; // [rsp+D0h] [rbp-98h]
  Microsoft::WRL::Wrappers::HStringReference *v42; // [rsp+D8h] [rbp-90h]
  __int64 (__fastcall *v43)(_QWORD, _QWORD, _QWORD); // [rsp+E0h] [rbp-88h]
  __int64 v44; // [rsp+E8h] [rbp-80h]
  HSTRING v45; // [rsp+F0h] [rbp-78h]
  __int64 (__fastcall *v46)(_QWORD, _QWORD, _QWORD); // [rsp+F8h] [rbp-70h]
  __int64 (__fastcall *v47)(_QWORD, _QWORD); // [rsp+100h] [rbp-68h]
  __int64 (__fastcall *v48)(_QWORD, _QWORD); // [rsp+108h] [rbp-60h]
  char v49[8]; // [rsp+110h] [rbp-58h] BYREF
  char v50[8]; // [rsp+118h] [rbp-50h] BYREF
  char v51[8]; // [rsp+120h] [rbp-48h] BYREF
  char v52[8]; // [rsp+128h] [rbp-40h] BYREF
  _BYTE v53[32]; // [rsp+130h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  *a2 = 0;
  Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(v13);
  v2 = (_QWORD *)Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(
                   v13,
                   v49);
  v37 = (LPVOID *)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IServiceProvider>>(*v2);
  dwClsContext = operator|(4);
  Instance = CoCreateInstance(
               &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
               0,
               dwClsContext,
               &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
               v37);
  v16 = wil::verify_BOOL<int>(Instance);
  if ( v16 >= 0 )
  {
    Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(v14);
    v34 = Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get(v13);
    v38 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v34 + 24LL);
    v5 = (_QWORD *)Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(
                     v14,
                     v50);
    v39 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IServiceProvider>>(*v5);
    v40 = v38;
    v6 = v38(v34, qword_18001F9F8, &GUID_2e8fcb18_a0ee_41ad_8ef8_77fb3a370ca5, v39);
    v18 = wil::verify_BOOL<int>(v6);
    if ( v18 >= 0 )
    {
      Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(v15);
      v35 = Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get(v14);
      v43 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v35 + 48LL);
      v7 = Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(
             v15,
             v51);
      v44 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>::operator void * *(v7);
      v41 = (Microsoft::WRL::Wrappers::HStringReference *)Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                                            (Microsoft::WRL::Wrappers::HStringReference *)v53,
                                                            (const unsigned __int16 (*)[49])L"Windows.Internal.ShellExperi"
                                                                                             "ence.VirtualTouchpad");
      v42 = v41;
      v45 = Microsoft::WRL::Wrappers::HStringReference::Get(v41);
      v46 = v43;
      v8 = v43(v35, v45, v44);
      v20 = wil::verify_BOOL<int>(v8);
      Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)v53);
      if ( v20 >= 0 )
      {
        Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(&v26);
        v9 = (_QWORD *)Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(
                         &v26,
                         v52);
        v10 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(
                v15,
                *v9);
        v22 = wil::verify_BOOL<int>(v10);
        if ( v22 >= 0 )
        {
          v36 = Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get(&v26);
          v47 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v36 + 72LL);
          v48 = v47;
          v11 = v47(v36, a2);
          v24 = wil::verify_BOOL<int>(v11);
          if ( v24 >= 0 )
          {
            v33 = 0;
            Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(&v26);
            Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v15);
            Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v14);
            Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v13);
            return v33;
          }
          else
          {
            v25 = v24;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x82,
              (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\virtualtouchpad.cpp",
              (const char *)(unsigned int)v24,
              ppv);
            v32 = v25;
            Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(&v26);
            Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v15);
            Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v14);
            Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v13);
            return v32;
          }
        }
        else
        {
          v23 = v22;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x81,
            (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\virtualtouchpad.cpp",
            (const char *)(unsigned int)v22,
            ppv);
          v31 = v23;
          Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(&v26);
          Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v15);
          Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v14);
          Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v13);
          return v31;
        }
      }
      else
      {
        v21 = v20;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7F,
          (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\virtualtouchpad.cpp",
          (const char *)(unsigned int)v20,
          ppv);
        v30 = v21;
        Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v15);
        Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v14);
        Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v13);
        return v30;
      }
    }
    else
    {
      v19 = v18;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\virtualtouchpad.cpp",
        (const char *)(unsigned int)v18,
        ppv);
      v29 = v19;
      Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v14);
      Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v13);
      return v29;
    }
  }
  else
  {
    v17 = v16;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\virtualtouchpad.cpp",
      (const char *)(unsigned int)v16,
      ppv);
    v28 = v17;
    Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v13);
    return v28;
  }
}

```

## disassembly

```asm
0x180014df0  mov     [rsp+arg_8], rdx
0x180014df5  mov     [rsp+arg_0], rcx
0x180014dfa  sub     rsp, 168h
0x180014e01  mov     rax, cs:__security_cookie
0x180014e08  xor     rax, rsp
0x180014e0b  mov     [rsp+168h+var_18], rax
0x180014e13  mov     rax, [rsp+168h+arg_8]
0x180014e1b  mov     byte ptr [rax], 0
0x180014e1e  lea     rcx, [rsp+168h+var_138]
0x180014e23  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x180014e28  nop
0x180014e29  lea     rdx, [rsp+168h+var_58]
0x180014e31  lea     rcx, [rsp+168h+var_138]
0x180014e36  call    ??I?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA?AV?$ComPtrRef@V?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@@Details@12@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(void)
0x180014e3b  mov     rcx, [rax]
0x180014e3e  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IServiceProvider>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>)
0x180014e43  mov     [rsp+168h+var_B8], rax
0x180014e4b  mov     edx, 400h
0x180014e50  mov     ecx, 4
0x180014e55  call    ??U@YA?AW4tagCLSCTX@@W40@0@Z; operator|(tagCLSCTX,tagCLSCTX)
0x180014e5a  mov     [rsp+168h+dwClsContext], eax
0x180014e5e  mov     rax, [rsp+168h+var_B8]
0x180014e66  mov     qword ptr [rsp+168h+ppv], rax; int
0x180014e6b  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180014e72  mov     r8d, [rsp+168h+dwClsContext]; dwClsContext
0x180014e77  xor     edx, edx; pUnkOuter
0x180014e79  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x180014e80  call    cs:__imp_CoCreateInstance
0x180014e86  mov     ecx, eax
0x180014e88  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x180014e8d  mov     [rsp+168h+var_120], eax
0x180014e91  cmp     [rsp+168h+var_120], 0
0x180014e96  jge     short loc_180014EE3
0x180014e98  mov     eax, [rsp+168h+var_120]
0x180014e9c  mov     dword ptr [rsp+168h+var_11C], eax
0x180014ea0  mov     rax, [rsp+168h]
0x180014ea8  mov     r9d, dword ptr [rsp+168h+var_11C]; char *
0x180014ead  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\docking\\virtualinpu"...
0x180014eb4  mov     edx, 7Bh ; '{'; void *
0x180014eb9  mov     rcx, rax; this
0x180014ebc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014ec1  nop
0x180014ec2  mov     eax, dword ptr [rsp+168h+var_11C]
0x180014ec6  mov     [rsp+168h+var_EC], eax
0x180014eca  lea     rcx, [rsp+168h+var_138]
0x180014ecf  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180014ed4  mov     eax, [rsp+168h+var_EC]
0x180014ed8  jmp     loc_180015329
0x180014edd  xor     eax, eax
0x180014edf  test    eax, eax
0x180014ee1  jnz     short loc_180014E98
0x180014ee3  xor     eax, eax
0x180014ee5  test    eax, eax
0x180014ee7  jnz     loc_180014E29
0x180014eed  lea     rcx, [rsp+168h+var_130]
0x180014ef2  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x180014ef7  nop
0x180014ef8  lea     rcx, [rsp+168h+var_138]
0x180014efd  call    ?Get@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEBAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@XZ; Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get(void)
0x180014f02  mov     [rsp+168h+var_D0], rax
0x180014f0a  mov     rax, [rsp+168h+var_D0]
0x180014f12  mov     rax, [rax]
0x180014f15  mov     rax, [rax+18h]
0x180014f19  mov     [rsp+168h+var_B0], rax
0x180014f21  lea     rdx, [rsp+168h+var_50]
0x180014f29  lea     rcx, [rsp+168h+var_130]
0x180014f2e  call    ??I?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA?AV?$ComPtrRef@V?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@@Details@12@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(void)
0x180014f33  mov     rcx, [rax]
0x180014f36  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IServiceProvider>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>)
0x180014f3b  mov     [rsp+168h+var_A8], rax
0x180014f43  mov     rax, [rsp+168h+var_B0]
0x180014f4b  mov     [rsp+168h+var_A0], rax
0x180014f53  mov     r9, [rsp+168h+var_A8]
0x180014f5b  lea     r8, _GUID_2e8fcb18_a0ee_41ad_8ef8_77fb3a370ca5
0x180014f62  lea     rdx, qword_18001F9F8
0x180014f69  mov     rcx, [rsp+168h+var_D0]
0x180014f71  mov     rax, [rsp+168h+var_A0]
0x180014f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f7e  mov     ecx, eax
0x180014f80  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x180014f85  mov     dword ptr [rsp+168h+var_11C+4], eax
0x180014f89  cmp     dword ptr [rsp+168h+var_11C+4], 0
0x180014f8e  jge     short loc_180014FEC
0x180014f90  mov     eax, dword ptr [rsp+168h+var_11C+4]
0x180014f94  mov     dword ptr [rsp+168h+var_114], eax
0x180014f98  mov     rax, [rsp+168h]
0x180014fa0  mov     r9d, dword ptr [rsp+168h+var_114]; char *
0x180014fa5  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\docking\\virtualinpu"...
0x180014fac  mov     edx, 7Dh ; '}'; void *
0x180014fb1  mov     rcx, rax; this
0x180014fb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014fb9  nop
0x180014fba  mov     eax, dword ptr [rsp+168h+var_114]
0x180014fbe  mov     [rsp+168h+var_E8], eax
0x180014fc5  lea     rcx, [rsp+168h+var_130]
0x180014fca  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180014fcf  nop
0x180014fd0  lea     rcx, [rsp+168h+var_138]
0x180014fd5  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180014fda  mov     eax, [rsp+168h+var_E8]
0x180014fe1  jmp     loc_180015329
0x180014fe6  xor     eax, eax
0x180014fe8  test    eax, eax
0x180014fea  jnz     short loc_180014F90
0x180014fec  xor     eax, eax
0x180014fee  test    eax, eax
0x180014ff0  jnz     loc_180014EF8
0x180014ff6  lea     rcx, [rsp+168h+var_128]
0x180014ffb  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x180015000  nop
0x180015001  lea     rcx, [rsp+168h+var_130]
0x180015006  call    ?Get@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEBAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@XZ; Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get(void)
0x18001500b  mov     [rsp+168h+var_C8], rax
0x180015013  mov     rax, [rsp+168h+var_C8]
0x18001501b  mov     rax, [rax]
0x18001501e  mov     rax, [rax+30h]
0x180015022  mov     [rsp+168h+var_88], rax
0x18001502a  lea     rdx, [rsp+168h+var_48]
0x180015032  lea     rcx, [rsp+168h+var_128]
0x180015037  call    ??I?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA?AV?$ComPtrRef@V?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@@Details@12@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(void)
0x18001503c  mov     rcx, rax
0x18001503f  call    ??B?$ComPtrRef@V?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEBAPEAPEAXXZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>::operator void * *(void)
0x180015044  mov     [rsp+168h+var_80], rax
0x18001504c  lea     rdx, aWindowsInterna; "Windows.Internal.ShellExperience.Virtua"...
0x180015053  lea     rcx, [rsp+168h+var_38]; this
0x18001505b  call    ??$?0$0DB@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0DB@$$CBG@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const (&)[49])
0x180015060  mov     [rsp+168h+var_98], rax
0x180015068  mov     rax, [rsp+168h+var_98]
0x180015070  mov     [rsp+168h+var_90], rax
0x180015078  mov     rcx, [rsp+168h+var_90]; this
0x180015080  call    ?Get@HStringReference@Wrappers@WRL@Microsoft@@QEBAPEAUHSTRING__@@XZ; Microsoft::WRL::Wrappers::HStringReference::Get(void)
0x180015085  mov     [rsp+168h+var_78], rax
0x18001508d  mov     rax, [rsp+168h+var_88]
0x180015095  mov     [rsp+168h+var_70], rax
0x18001509d  mov     r8, [rsp+168h+var_80]
0x1800150a5  mov     rdx, [rsp+168h+var_78]
0x1800150ad  mov     rcx, [rsp+168h+var_C8]
0x1800150b5  mov     rax, [rsp+168h+var_70]
0x1800150bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150c2  mov     ecx, eax
0x1800150c4  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x1800150c9  mov     dword ptr [rsp+168h+var_114+4], eax
0x1800150cd  lea     rcx, [rsp+168h+var_38]; this
0x1800150d5  call    ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
0x1800150da  nop
0x1800150db  cmp     dword ptr [rsp+168h+var_114+4], 0
0x1800150e0  jge     short loc_180015149
0x1800150e2  mov     eax, dword ptr [rsp+168h+var_114+4]
0x1800150e6  mov     dword ptr [rsp+168h+var_10C], eax
0x1800150ea  mov     rax, [rsp+168h]
0x1800150f2  mov     r9d, dword ptr [rsp+168h+var_10C]; char *
0x1800150f7  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\docking\\virtualinpu"...
0x1800150fe  mov     edx, 7Fh; void *
0x180015103  mov     rcx, rax; this
0x180015106  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001510b  nop
0x18001510c  mov     eax, dword ptr [rsp+168h+var_10C]
0x180015110  mov     [rsp+168h+var_E4], eax
0x180015117  lea     rcx, [rsp+168h+var_128]
0x18001511c  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180015121  nop
0x180015122  lea     rcx, [rsp+168h+var_130]
0x180015127  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x18001512c  nop
0x18001512d  lea     rcx, [rsp+168h+var_138]
0x180015132  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180015137  mov     eax, [rsp+168h+var_E4]
0x18001513e  jmp     loc_180015329
0x180015143  xor     eax, eax
0x180015145  test    eax, eax
0x180015147  jnz     short loc_1800150E2
0x180015149  xor     eax, eax
0x18001514b  test    eax, eax
0x18001514d  jnz     loc_180015001
0x180015153  lea     rcx, [rsp+168h+var_FC+4]
0x180015158  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x18001515d  nop
0x18001515e  lea     rdx, [rsp+168h+var_40]
0x180015166  lea     rcx, [rsp+168h+var_FC+4]
0x18001516b  call    ??I?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA?AV?$ComPtrRef@V?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@@Details@12@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(void)
0x180015170  mov     rdx, [rax]
0x180015173  lea     rcx, [rsp+168h+var_128]
0x180015178  call    ??$As@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>>)
0x18001517d  mov     ecx, eax
0x18001517f  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x180015184  mov     dword ptr [rsp+168h+var_10C+4], eax
0x180015188  cmp     dword ptr [rsp+168h+var_10C+4], 0
0x18001518d  jge     short loc_180015201
0x18001518f  mov     eax, dword ptr [rsp+168h+var_10C+4]
0x180015193  mov     dword ptr [rsp+168h+var_104], eax
0x180015197  mov     rax, [rsp+168h]
0x18001519f  mov     r9d, dword ptr [rsp+168h+var_104]; char *
0x1800151a4  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\docking\\virtualinpu"...
0x1800151ab  mov     edx, 81h; void *
0x1800151b0  mov     rcx, rax; this
0x1800151b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800151b8  nop
0x1800151b9  mov     eax, dword ptr [rsp+168h+var_104]
0x1800151bd  mov     [rsp+168h+var_E0], eax
0x1800151c4  lea     rcx, [rsp+168h+var_FC+4]
0x1800151c9  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x1800151ce  nop
0x1800151cf  lea     rcx, [rsp+168h+var_128]
0x1800151d4  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x1800151d9  nop
0x1800151da  lea     rcx, [rsp+168h+var_130]
0x1800151df  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x1800151e4  nop
0x1800151e5  lea     rcx, [rsp+168h+var_138]
0x1800151ea  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x1800151ef  mov     eax, [rsp+168h+var_E0]
0x1800151f6  jmp     loc_180015329
0x1800151fb  xor     eax, eax
0x1800151fd  test    eax, eax
0x1800151ff  jnz     short loc_18001518F
0x180015201  xor     eax, eax
0x180015203  test    eax, eax
0x180015205  jnz     loc_18001515E
0x18001520b  lea     rcx, [rsp+168h+var_FC+4]
0x180015210  call    ?Get@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEBAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@XZ; Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get(void)
0x180015215  mov     [rsp+168h+var_C0], rax
0x18001521d  mov     rax, [rsp+168h+var_C0]
0x180015225  mov     rax, [rax]
0x180015228  mov     rax, [rax+48h]
0x18001522c  mov     [rsp+168h+var_68], rax
0x180015234  mov     rax, [rsp+168h+var_68]
0x18001523c  mov     [rsp+168h+var_60], rax
0x180015244  mov     rdx, [rsp+168h+arg_8]
0x18001524c  mov     rcx, [rsp+168h+var_C0]
0x180015254  mov     rax, [rsp+168h+var_60]
0x18001525c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015261  mov     ecx, eax
0x180015263  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x180015268  mov     dword ptr [rsp+168h+var_104+4], eax
0x18001526c  cmp     dword ptr [rsp+168h+var_104+4], 0
0x180015271  jge     short loc_1800152E2
0x180015273  mov     eax, dword ptr [rsp+168h+var_104+4]
0x180015277  mov     dword ptr [rsp+168h+var_FC], eax
0x18001527b  mov     rax, [rsp+168h]
0x180015283  mov     r9d, dword ptr [rsp+168h+var_FC]; char *
0x180015288  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\docking\\virtualinpu"...
0x18001528f  mov     edx, 82h; void *
0x180015294  mov     rcx, rax; this
0x180015297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001529c  nop
0x18001529d  mov     eax, dword ptr [rsp+168h+var_FC]
0x1800152a1  mov     [rsp+168h+var_DC], eax
0x1800152a8  lea     rcx, [rsp+168h+var_FC+4]
0x1800152ad  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x1800152b2  nop
0x1800152b3  lea     rcx, [rsp+168h+var_128]
0x1800152b8  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x1800152bd  nop
0x1800152be  lea     rcx, [rsp+168h+var_130]
0x1800152c3  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x1800152c8  nop
0x1800152c9  lea     rcx, [rsp+168h+var_138]
0x1800152ce  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x1800152d3  mov     eax, [rsp+168h+var_DC]
0x1800152da  jmp     short loc_180015329
0x1800152dc  xor     eax, eax
0x1800152de  test    eax, eax
0x1800152e0  jnz     short loc_180015273
0x1800152e2  xor     eax, eax
0x1800152e4  test    eax, eax
0x1800152e6  jnz     loc_18001520B
0x1800152ec  mov     [rsp+168h+var_D8], 0
0x1800152f7  lea     rcx, [rsp+168h+var_FC+4]
0x1800152fc  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180015301  nop
0x180015302  lea     rcx, [rsp+168h+var_128]
0x180015307  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x18001530c  nop
0x18001530d  lea     rcx, [rsp+168h+var_130]
0x180015312  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180015317  nop
0x180015318  lea     rcx, [rsp+168h+var_138]
0x18001531d  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180015322  mov     eax, [rsp+168h+var_D8]
0x180015329  mov     rcx, [rsp+168h+var_18]
0x180015331  xor     rcx, rsp; StackCookie
0x180015334  call    __security_check_cookie
0x180015339  add     rsp, 168h
0x180015340  retn
```
