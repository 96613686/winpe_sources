# ViewActivator::CreateCoreWindowFactory(unsigned __int64,ushort const *,_GUID,unsigned __int64,ushort const *,unsigned __int64,unsigned __int64,ACTIVATEOPTIONSINTERNAL,Navigation::ViewActivationFlags,ulong,ICoreWindowFactoryPrivCallbackSink *,Windows::UI::Core::ICoreWindowFactory * *)

- ea: `0x1800210bc`
- end: `0x180021630`
- name: `?CreateCoreWindowFactory@ViewActivator@@SAJ_KPEBGU_GUID@@0100W4ACTIVATEOPTIONSINTERNAL@@W4ViewActivationFlags@Navigation@@KPEAUICoreWindowFactoryPrivCallbackSink@@PEAPEAUICoreWindowFactory@Core@UI@Windows@@@Z`
- size: `1396`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020060`
- `0x18006bcf8`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x18001e484`
- `0x1800210bc`
- `0x18003cb08`
- `0x180082320`
- `0x1800a0010`

## import_xrefs

- `CoreMessaging!MsgStringCreateShared` at `0x1800211c3`
- `CoreMessaging!MsgStringCreateShared` at `0x180021207`
- `CoreMessaging!MsgStringCreateShared` at `0x1800212e8`
- `CoreMessaging!MsgStringCreateShared` at `0x1800211c3`
- `CoreMessaging!MsgStringCreateShared` at `0x180021207`
- `CoreMessaging!MsgStringCreateShared` at `0x1800212e8`
- `CoreMessaging!MsgRelease` at `0x180021298`
- `CoreMessaging!MsgRelease` at `0x1800212a8`
- `CoreMessaging!MsgRelease` at `0x180021379`
- `CoreMessaging!MsgRelease` at `0x1800214da`
- `CoreMessaging!MsgRelease` at `0x1800214ea`
- `CoreMessaging!MsgRelease` at `0x1800215d2`
- `CoreMessaging!MsgRelease` at `0x1800215e2`
- `CoreMessaging!MsgRelease` at `0x180021298`
- `CoreMessaging!MsgRelease` at `0x1800212a8`
- `CoreMessaging!MsgRelease` at `0x180021379`
- `CoreMessaging!MsgRelease` at `0x1800214da`
- `CoreMessaging!MsgRelease` at `0x1800214ea`
- `CoreMessaging!MsgRelease` at `0x1800215d2`
- `CoreMessaging!MsgRelease` at `0x1800215e2`
- `CoreUIComponents!CoreUICreateICoreWindowFactory` at `0x180021266`
- `CoreUIComponents!CoreUICreateICoreWindowFactory` at `0x180021266`
- `CoreUIComponents!CoreUICreateICoreWindowFactoryEx` at `0x18002135d`
- `CoreUIComponents!CoreUICreateICoreWindowFactoryEx` at `0x18002135d`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall ViewActivator::CreateCoreWindowFactory(
        unsigned int a1,
        __int64 a2,
        _OWORD *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        signed __int32 a8,
        unsigned int a9,
        unsigned int a10,
        __int64 a11,
        _QWORD *a12)
{
  _QWORD *v15; // r15
  unsigned int v16; // ebx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, GUID *, _QWORD **); // rbx
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // eax
  int Shared; // edi
  int v23; // eax
  Windows::Internal::ApplicationModel::WindowManagement *v24; // rcx
  int v25; // eax
  unsigned int v26; // edi
  _QWORD *v27; // rcx
  __int64 v29; // rdx
  _QWORD *v30; // rbx
  int (__fastcall *v31)(_QWORD *, GUID *, __int64 *); // rdi
  int v32; // eax
  __int64 v33; // rdx
  _QWORD *v34; // rbx
  int (__fastcall *v35)(_QWORD *, GUID *, __int64 *); // rdi
  int v36; // eax
  __int64 v37; // rcx
  _QWORD *v38; // rcx
  __int64 v39; // rsi
  _QWORD *v40; // rbx
  int (__fastcall *v41)(_QWORD *, GUID *, _OWORD *); // rdi
  int v42; // eax
  __int64 v43; // rcx
  _QWORD *v44; // rcx
  int v45; // [rsp+20h] [rbp-71h]
  __int64 v46; // [rsp+50h] [rbp-41h] BYREF
  __int64 v47; // [rsp+58h] [rbp-39h] BYREF
  __int64 v48; // [rsp+60h] [rbp-31h] BYREF
  __int64 v49; // [rsp+68h] [rbp-29h] BYREF
  int v50[4]; // [rsp+70h] [rbp-21h] BYREF
  _OWORD v51[5]; // [rsp+80h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+47h]

  v15 = a12;
  *a12 = 0;
  a12 = 0;
  v16 = a9;
  if ( (a9 & 8) != 0 )
  {
    Microsoft::WRL::Details::Make<CImmersiveWindowFactory,>(v51);
    v17 = *(_QWORD *)&v51[0];
    if ( (v16 & 0x400) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)&v51[0] + 156LL) = 1;
      *(_BYTE *)(v17 + 152) = 1;
      *(_DWORD *)(v17 + 132) = 4;
      *(_BYTE *)(v17 + 105) = 1;
    }
    v18 = **(__int64 (__fastcall ***)(__int64, GUID *, _QWORD **))v17;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&a12);
    v19 = v18(v17, &GUID_cd292360_2763_4085_8a9f_74b224a29175, &a12);
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F3,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
        (const char *)(unsigned int)v19,
        v45);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      goto LABEL_67;
    }
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
LABEL_64:
    v44 = a12;
    if ( a12 )
    {
      (*(void (__fastcall **)(_QWORD *))(*a12 + 8LL))(a12);
      v44 = a12;
    }
    *v15 = v44;
    v20 = 0;
    goto LABEL_67;
  }
  v46 = 0;
  v21 = MsgStringCreateShared(a2, 0xFFFFFFFFLL, &v46);
  Shared = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F8,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
      (const char *)(unsigned int)v21,
      v45);
LABEL_13:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>(&v46);
    v20 = Shared;
LABEL_67:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&a12);
    return v20;
  }
  v47 = 0;
  v23 = MsgStringCreateShared(a5, 0xFFFFFFFFLL, &v47);
  Shared = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FB,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
      (const char *)(unsigned int)v23,
      v45);
LABEL_16:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>(&v47);
    goto LABEL_13;
  }
  if ( Windows::Internal::ApplicationModel::WindowManagement::IsViewManagerPhaseoutEnabled(v24) )
  {
    *(_QWORD *)v50 = 0;
    Shared = MsgStringCreateShared(&Src, 0xFFFFFFFFLL, v50);
    if ( Shared >= 0 )
    {
      v51[0] = *a3;
      v45 = v50[0];
      Shared = CoreUICreateICoreWindowFactoryEx(v46, v51, a4, v47);
      if ( Shared >= 0 )
      {
        if ( *(_QWORD *)v50 )
          MsgRelease();
LABEL_33:
        if ( _bittest(&a8, 0x1Cu) || (v16 & 0x400) != 0 )
        {
          v49 = 0;
          v30 = a12;
          v31 = *(int (__fastcall **)(_QWORD *, GUID *, __int64 *))*a12;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
          if ( v31(v30, &GUID_dbcc81cc_d31a_4e70_9632_fc3fdd4325c0, &v49) >= 0 )
          {
            v32 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 24LL))(v49, 0);
            v20 = v32;
            if ( v32 < 0 )
            {
              v33 = 798;
LABEL_37:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v33,
                (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
                (const char *)(unsigned int)v32,
                v45);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
LABEL_38:
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>(&v47);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>(&v46);
              goto LABEL_67;
            }
            v32 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 32LL))(v49, 2);
            v20 = v32;
            if ( v32 < 0 )
            {
              v33 = 799;
              goto LABEL_37;
            }
          }
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
        }
        v48 = 0;
        v34 = a12;
        v35 = *(int (__fastcall **)(_QWORD *, GUID *, __int64 *))*a12;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
        if ( v35(v34, &GUID_118b4ce1_ee64_4f90_b4c2_45280afbf38b, &v48) >= 0 )
        {
          v36 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v48 + 24LL))(v48, a1);
          v20 = v36;
          if ( v36 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x326,
              (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
              (const char *)(unsigned int)v36,
              v45);
            v37 = v48;
            if ( v48 )
            {
              v48 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
            }
            if ( v47 )
              MsgRelease();
            if ( v46 )
              MsgRelease();
            v38 = a12;
            if ( a12 )
            {
              a12 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v38 + 16LL))(v38);
            }
            return v20;
          }
        }
        v39 = a11;
        if ( a11 )
        {
          *(_QWORD *)&v51[0] = 0;
          v40 = a12;
          v41 = *(int (__fastcall **)(_QWORD *, GUID *, _OWORD *))*a12;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v51);
          if ( v41(v40, &GUID_4208d435_b020_4346_ae40_2a4796084296, v51) >= 0 )
          {
            v42 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&v51[0] + 24LL))(*(_QWORD *)&v51[0], v39);
            v20 = v42;
            if ( v42 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x32E,
                (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
                (const char *)(unsigned int)v42,
                v45);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v51);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
              goto LABEL_38;
            }
          }
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v51);
        }
        v43 = v48;
        if ( v48 )
        {
          v48 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        }
        if ( v47 )
          MsgRelease();
        if ( v46 )
          MsgRelease();
        goto LABEL_64;
      }
      v29 = 789;
    }
    else
    {
      v29 = 778;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
      (const char *)(unsigned int)Shared,
      v45);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>(v50);
    goto LABEL_16;
  }
  LOBYTE(v45) = 0;
  v25 = CoreUICreateICoreWindowFactory(a10, v46, v47, v16);
  v26 = v25;
  if ( v25 >= 0 )
    goto LABEL_33;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x305,
    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
    (const char *)(unsigned int)v25,
    v45);
  if ( v47 )
    MsgRelease();
  if ( v46 )
    MsgRelease();
  v27 = a12;
  if ( a12 )
  {
    a12 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
  }
  return v26;
}

```

## disassembly

```asm
0x1800210bc  push    rbp
0x1800210be  push    rbx
0x1800210bf  push    rsi
0x1800210c0  push    rdi
0x1800210c1  push    r12
0x1800210c3  push    r13
0x1800210c5  push    r14
0x1800210c7  push    r15
0x1800210c9  lea     rbp, [rsp-7]
0x1800210ce  sub     rsp, 98h
0x1800210d5  mov     rsi, r9
0x1800210d8  mov     r14, r8
0x1800210db  mov     rax, rdx
0x1800210de  mov     r12, rcx
0x1800210e1  xor     r13d, r13d
0x1800210e4  mov     r15, [rbp+3Fh+arg_58]
0x1800210eb  mov     [r15], r13
0x1800210ee  mov     [rbp+3Fh+arg_58], r13
0x1800210f5  mov     ebx, [rbp+3Fh+arg_40]
0x1800210fb  test    bl, 8
0x1800210fe  jz      loc_1800211B5
0x180021104  lea     rcx, [rbp+3Fh+var_50]
0x180021108  call    ??$Make@VCImmersiveWindowFactory@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCImmersiveWindowFactory@@@12@XZ; Microsoft::WRL::Details::Make<CImmersiveWindowFactory,>(void)
0x18002110d  nop
0x18002110e  mov     rdi, qword ptr [rbp+3Fh+var_50]
0x180021112  bt      ebx, 0Ah
0x180021116  jnb     short loc_180021137
0x180021118  mov     dword ptr [rdi+9Ch], 1
0x180021122  mov     byte ptr [rdi+98h], 1
0x180021129  mov     dword ptr [rdi+84h], 4
0x180021133  mov     byte ptr [rdi+69h], 1
0x180021137  mov     rax, [rdi]
0x18002113a  mov     rbx, [rax]
0x18002113d  lea     rcx, [rbp+3Fh+arg_58]
0x180021144  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021149  lea     r8, [rbp+3Fh+arg_58]
0x180021150  lea     rdx, _GUID_cd292360_2763_4085_8a9f_74b224a29175
0x180021157  mov     rcx, rdi
0x18002115a  mov     rax, rbx
0x18002115d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021162  mov     ebx, eax
0x180021164  test    eax, eax
0x180021166  jns     short loc_18002119B
0x180021168  mov     rcx, [rbp+47h]; this
0x18002116c  mov     r9d, eax; char *
0x18002116f  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180021176  mov     edx, 2F3h; void *
0x18002117b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021180  nop
0x180021181  test    rdi, rdi
0x180021184  jz      short loc_180021196
0x180021186  mov     rax, [rdi]
0x180021189  mov     rcx, rdi
0x18002118c  mov     rax, [rax+10h]
0x180021190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021195  nop
0x180021196  jmp     loc_18002160E
0x18002119b  test    rdi, rdi
0x18002119e  jz      short loc_1800211B0
0x1800211a0  mov     rax, [rdi]
0x1800211a3  mov     rcx, rdi
0x1800211a6  mov     rax, [rax+10h]
0x1800211aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211af  nop
0x1800211b0  jmp     loc_1800215E9
0x1800211b5  mov     [rbp+3Fh+var_80], r13
0x1800211b9  lea     r8, [rbp+3Fh+var_80]
0x1800211bd  or      edx, 0FFFFFFFFh
0x1800211c0  mov     rcx, rax
0x1800211c3  call    cs:__imp_MsgStringCreateShared
0x1800211c9  mov     edi, eax
0x1800211cb  test    eax, eax
0x1800211cd  jns     short loc_1800211F8
0x1800211cf  mov     rcx, [rbp+47h]; this
0x1800211d3  mov     r9d, eax; char *
0x1800211d6  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800211dd  mov     edx, 2F8h; void *
0x1800211e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800211e7  nop
0x1800211e8  lea     rcx, [rbp+3Fh+var_80]
0x1800211ec  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUMsgBlob@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>(void)
0x1800211f1  mov     ebx, edi
0x1800211f3  jmp     loc_18002160E
0x1800211f8  mov     [rbp+3Fh+var_78], r13
0x1800211fc  lea     r8, [rbp+3Fh+var_78]
0x180021200  or      edx, 0FFFFFFFFh
0x180021203  mov     rcx, [rbp+3Fh+arg_20]
0x180021207  call    cs:__imp_MsgStringCreateShared
0x18002120d  mov     edi, eax
0x18002120f  test    eax, eax
0x180021211  jns     short loc_180021237
0x180021213  mov     rcx, [rbp+47h]; this
0x180021217  mov     r9d, eax; char *
0x18002121a  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180021221  mov     edx, 2FBh; void *
0x180021226  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002122b  nop
0x18002122c  lea     rcx, [rbp+3Fh+var_78]
0x180021230  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUMsgBlob@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>(void)
0x180021235  jmp     short loc_1800211E8
0x180021237  call    ?IsViewManagerPhaseoutEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ; Windows::Internal::ApplicationModel::WindowManagement::IsViewManagerPhaseoutEnabled(void)
0x18002123c  test    al, al
0x18002123e  jnz     loc_1800212D6
0x180021244  lea     rax, [rbp+3Fh+arg_58]
0x18002124b  mov     [rsp+0D0h+var_A8], rax
0x180021250  mov     byte ptr [rsp+0D0h+var_B0], r13b; int
0x180021255  mov     r9d, ebx
0x180021258  mov     r8, [rbp+3Fh+var_78]
0x18002125c  mov     rdx, [rbp+3Fh+var_80]
0x180021260  mov     ecx, [rbp+3Fh+arg_48]
0x180021266  call    cs:__imp_CoreUICreateICoreWindowFactory
0x18002126c  mov     edi, eax
0x18002126e  test    eax, eax
0x180021270  jns     loc_18002137F
0x180021276  mov     rcx, [rbp+47h]; this
0x18002127a  mov     r9d, eax; char *
0x18002127d  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180021284  mov     edx, 305h; void *
0x180021289  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002128e  nop
0x18002128f  mov     rcx, [rbp+3Fh+var_78]
0x180021293  test    rcx, rcx
0x180021296  jz      short loc_18002129F
0x180021298  call    cs:__imp_MsgRelease
0x18002129e  nop
0x18002129f  mov     rcx, [rbp+3Fh+var_80]
0x1800212a3  test    rcx, rcx
0x1800212a6  jz      short loc_1800212AF
0x1800212a8  call    cs:__imp_MsgRelease
0x1800212ae  nop
0x1800212af  mov     rcx, [rbp+3Fh+arg_58]
0x1800212b6  test    rcx, rcx
0x1800212b9  jz      short loc_1800212CF
0x1800212bb  mov     [rbp+3Fh+arg_58], r13
0x1800212c2  mov     rax, [rcx]
0x1800212c5  mov     rax, [rax+10h]
0x1800212c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212ce  nop
0x1800212cf  mov     eax, edi
0x1800212d1  jmp     loc_18002161C
0x1800212d6  mov     qword ptr [rbp+3Fh+var_60], r13
0x1800212da  lea     r8, [rbp+3Fh+var_60]
0x1800212de  or      edx, 0FFFFFFFFh
0x1800212e1  lea     rcx, Src
0x1800212e8  call    cs:__imp_MsgStringCreateShared
0x1800212ee  mov     edi, eax
0x1800212f0  test    eax, eax
0x1800212f2  jns     short loc_18002131A
0x1800212f4  mov     edx, 30Ah; void *
0x1800212f9  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180021300  mov     r9d, edi; char *
0x180021303  mov     rcx, [rbp+47h]; this
0x180021307  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002130c  lea     rcx, [rbp+3Fh+var_60]
0x180021310  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUMsgBlob@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>(void)
0x180021315  jmp     loc_18002122C
0x18002131a  mov     rdx, qword ptr [rbp+3Fh+var_60]
0x18002131e  movaps  xmm0, xmmword ptr [r14]
0x180021322  movdqa  [rbp+3Fh+var_50], xmm0
0x180021327  lea     rax, [rbp+3Fh+arg_58]
0x18002132e  mov     [rsp+0D0h+var_90], rax
0x180021333  mov     [rsp+0D0h+var_98], ebx
0x180021337  mov     rax, [rbp+3Fh+arg_30]
0x18002133b  mov     [rsp+0D0h+var_A0], rax
0x180021340  mov     rax, [rbp+3Fh+arg_28]
0x180021344  mov     [rsp+0D0h+var_A8], rax
0x180021349  mov     qword ptr [rsp+0D0h+var_B0], rdx; int
0x18002134e  mov     r9, [rbp+3Fh+var_78]
0x180021352  mov     r8, rsi
0x180021355  lea     rdx, [rbp+3Fh+var_50]
0x180021359  mov     rcx, [rbp+3Fh+var_80]
0x18002135d  call    cs:__imp_CoreUICreateICoreWindowFactoryEx
0x180021363  mov     edi, eax
0x180021365  test    eax, eax
0x180021367  jns     short loc_180021370
0x180021369  mov     edx, 315h
0x18002136e  jmp     short loc_1800212F9
0x180021370  mov     rcx, qword ptr [rbp+3Fh+var_60]
0x180021374  test    rcx, rcx
0x180021377  jz      short loc_18002137F
0x180021379  call    cs:__imp_MsgRelease
0x18002137f  bt      [rbp+3Fh+arg_38], 1Ch
0x180021387  setnb   cl
0x18002138a  bt      ebx, 0Ah
0x18002138e  setnb   al
0x180021391  test    al, cl
0x180021393  jnz     loc_18002144C
0x180021399  mov     [rbp+3Fh+var_68], r13
0x18002139d  mov     rbx, [rbp+3Fh+arg_58]
0x1800213a4  mov     rax, [rbx]
0x1800213a7  mov     rdi, [rax]
0x1800213aa  lea     rcx, [rbp+3Fh+var_68]
0x1800213ae  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800213b3  lea     r8, [rbp+3Fh+var_68]
0x1800213b7  lea     rdx, _GUID_dbcc81cc_d31a_4e70_9632_fc3fdd4325c0
0x1800213be  mov     rcx, rbx
0x1800213c1  mov     rax, rdi
0x1800213c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213c9  nop
0x1800213ca  test    eax, eax
0x1800213cc  js      short loc_180021443
0x1800213ce  mov     rcx, [rbp+3Fh+var_68]
0x1800213d2  mov     rax, [rcx]
0x1800213d5  xor     edx, edx
0x1800213d7  mov     rax, [rax+18h]
0x1800213db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213e0  mov     ebx, eax
0x1800213e2  test    eax, eax
0x1800213e4  jns     short loc_180021421
0x1800213e6  mov     edx, 31Eh; void *
0x1800213eb  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800213f2  mov     r9d, eax; char *
0x1800213f5  mov     rcx, [rbp+47h]; this
0x1800213f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800213fe  nop
0x1800213ff  lea     rcx, [rbp+3Fh+var_68]
0x180021403  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021408  nop
0x180021409  lea     rcx, [rbp+3Fh+var_78]
0x18002140d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUMsgBlob@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>(void)
0x180021412  nop
0x180021413  lea     rcx, [rbp+3Fh+var_80]
0x180021417  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUMsgBlob@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>>(void)
0x18002141c  jmp     loc_18002160E
0x180021421  mov     rcx, [rbp+3Fh+var_68]
0x180021425  mov     rax, [rcx]
0x180021428  mov     edx, 2
0x18002142d  mov     rax, [rax+20h]
0x180021431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021436  mov     ebx, eax
0x180021438  test    eax, eax
0x18002143a  jns     short loc_180021443
0x18002143c  mov     edx, 31Fh
0x180021441  jmp     short loc_1800213EB
0x180021443  lea     rcx, [rbp+3Fh+var_68]
0x180021447  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002144c  mov     [rbp+3Fh+var_70], r13
0x180021450  mov     rbx, [rbp+3Fh+arg_58]
0x180021457  mov     rax, [rbx]
0x18002145a  mov     rdi, [rax]
0x18002145d  lea     rcx, [rbp+3Fh+var_70]
0x180021461  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021466  lea     r8, [rbp+3Fh+var_70]
0x18002146a  lea     rdx, _GUID_118b4ce1_ee64_4f90_b4c2_45280afbf38b
0x180021471  mov     rcx, rbx
0x180021474  mov     rax, rdi
0x180021477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002147c  nop
0x18002147d  test    eax, eax
0x18002147f  js      loc_180021516
0x180021485  mov     rcx, [rbp+3Fh+var_70]
0x180021489  mov     rax, [rcx]
0x18002148c  mov     edx, r12d
0x18002148f  mov     rax, [rax+18h]
0x180021493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021498  mov     ebx, eax
0x18002149a  test    eax, eax
0x18002149c  jns     short loc_180021516
0x18002149e  mov     rcx, [rbp+47h]; this
0x1800214a2  mov     r9d, eax; char *
0x1800214a5  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800214ac  mov     edx, 326h; void *
0x1800214b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800214b6  nop
0x1800214b7  mov     rcx, [rbp+3Fh+var_70]
0x1800214bb  test    rcx, rcx
0x1800214be  jz      short loc_1800214D1
0x1800214c0  mov     [rbp+3Fh+var_70], r13
0x1800214c4  mov     rax, [rcx]
0x1800214c7  mov     rax, [rax+10h]
0x1800214cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214d0  nop
0x1800214d1  mov     rcx, [rbp+3Fh+var_78]
0x1800214d5  test    rcx, rcx
0x1800214d8  jz      short loc_1800214E1
0x1800214da  call    cs:__imp_MsgRelease
0x1800214e0  nop
0x1800214e1  mov     rcx, [rbp+3Fh+var_80]
0x1800214e5  test    rcx, rcx
0x1800214e8  jz      short loc_1800214F1
0x1800214ea  call    cs:__imp_MsgRelease
0x1800214f0  nop
0x1800214f1  mov     rcx, [rbp+3Fh+arg_58]
0x1800214f8  test    rcx, rcx
0x1800214fb  jz      short loc_180021511
0x1800214fd  mov     [rbp+3Fh+arg_58], r13
0x180021504  mov     rax, [rcx]
0x180021507  mov     rax, [rax+10h]
0x18002150b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021510  nop
0x180021511  jmp     loc_18002161A
0x180021516  mov     rsi, [rbp+3Fh+arg_50]
0x18002151d  test    rsi, rsi
0x180021520  jz      loc_1800215AF
0x180021526  mov     qword ptr [rbp+3Fh+var_50], r13
0x18002152a  mov     rbx, [rbp+3Fh+arg_58]
0x180021531  mov     rax, [rbx]
0x180021534  mov     rdi, [rax]
0x180021537  lea     rcx, [rbp+3Fh+var_50]
0x18002153b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
  ... truncated ...
```
