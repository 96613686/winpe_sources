# ShieldProvider::AppAndBrowserShield::ListenForSettingChanges(void)

- ea: `0x180070f60`
- end: `0x180071478`
- name: `?ListenForSettingChanges@AppAndBrowserShield@ShieldProvider@@AEAAJXZ`
- size: `1304`
- prototype: `__int64 __fastcall(ShieldProvider::AppAndBrowserShield *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180072800`

## callees

- `0x180004b40`
- `0x1800065ac`
- `0x18000d7fc`
- `0x180017194`
- `0x18001a2a8`
- `0x180070f60`
- `0x1800716fc`
- `0x1800dc2ac`
- `0x1800dc778`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071059`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071059`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18007106e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18007106e`

## pseudocode

```c
__int64 __fastcall ShieldProvider::AppAndBrowserShield::ListenForSettingChanges(
        ShieldProvider::AppAndBrowserShield *this)
{
  _QWORD *v2; // rbx
  struct CommonUtil::IUtilRegListenerCallback *v3; // rax
  struct CommonUtil::IUtilRegListenerCallback *v4; // r12
  ShieldProvider::AppAndBrowserShield *v5; // rcx
  _QWORD *v6; // rbx
  struct CommonUtil::IUtilRegListenerCallback *v7; // rax
  struct CommonUtil::IUtilRegListenerCallback *v8; // r13
  HKEY *v9; // rsi
  HKEY v10; // rcx
  LSTATUS v11; // eax
  unsigned int v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  int v15; // ebx
  CommonUtil::CUtilRegListener *v16; // r14
  int v17; // ebx
  CommonUtil::CUtilRegListener *v18; // r13
  HKEY v19; // r14
  int v20; // ebx
  HKEY v21; // r9
  CommonUtil::CUtilRegListener *v22; // r14
  int v23; // ebx
  CommonUtil::CUtilRegListener *v24; // r14
  int v25; // ebx
  CommonUtil::CUtilRegListener *v26; // r14
  unsigned int v28; // [rsp+38h] [rbp-18h]
  struct CommonUtil::IUtilRegListenerCallback *v29; // [rsp+40h] [rbp-10h]
  HKEY v30; // [rsp+48h] [rbp-8h]
  CommonUtil::CUtilRegListener *v31; // [rsp+98h] [rbp+48h] BYREF
  struct CommonUtil::IUtilRegListenerCallback *v32; // [rsp+A0h] [rbp+50h] BYREF
  struct CommonUtil::IUtilRegListenerCallback *v33; // [rsp+A8h] [rbp+58h] BYREF

  v32 = 0;
  v2 = (_QWORD *)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                   &v31,
                   this);
  CommonUtil::AutoRef<CommonUtil::IUtilRegListenerCallback>::Release(&v32);
  v3 = (struct CommonUtil::IUtilRegListenerCallback *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 2) = 0;
    *(_QWORD *)v3 = &CommonUtil::CRegListenerFunctorAdapter<_lambda_71059ac68cae7094b9a0a55750988db9_>::`vftable';
    *((_QWORD *)v3 + 2) = *v2;
    ((void (__fastcall *)(struct CommonUtil::IUtilRegListenerCallback *))CommonUtil::CRegListenerFunctorAdapter<_lambda_71059ac68cae7094b9a0a55750988db9_>::`vftable')(v3);
    v32 = v4;
    ShieldProvider::AppAndBrowserShield::NotifyClientsOnPua(v5);
    v33 = 0;
    v6 = (_QWORD *)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                     &v31,
                     this);
    CommonUtil::AutoRef<CommonUtil::IUtilRegListenerCallback>::Release(&v33);
    v7 = (struct CommonUtil::IUtilRegListenerCallback *)operator new(
                                                          0x18u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
    v29 = v7;
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 2) = 0;
      *(_QWORD *)v7 = &CommonUtil::CRegListenerFunctorAdapter<_lambda_18155f7eae7a246170d1f10899b2a74e_>::`vftable';
      *((_QWORD *)v7 + 2) = *v6;
      ((void (__fastcall *)(struct CommonUtil::IUtilRegListenerCallback *))CommonUtil::CRegListenerFunctorAdapter<_lambda_18155f7eae7a246170d1f10899b2a74e_>::`vftable')(v7);
      v9 = (HKEY *)((char *)this + 72);
      v33 = v8;
      v10 = (HKEY)*((_QWORD *)this + 9);
      if ( v10 )
      {
        RegCloseKey(v10);
        *v9 = 0;
      }
      v11 = RegOpenCurrentUser(0x20006u, (PHKEY)this + 9);
      v12 = v11;
      if ( !v11 )
        goto LABEL_12;
      if ( v11 > 0 )
        v12 = (unsigned __int16)v11 | 0x80070000;
      if ( (v12 & 0x80000000) == 0 )
      {
LABEL_12:
        CommonUtil::AutoRef<CommonUtil::IUtilRegListenerCallback>::Release((char *)this + 80);
        v31 = 0;
        v15 = CommonUtil::CreateNewRefObject<CommonUtil::CUtilRegListener>(&v31);
        if ( v15 >= 0 )
        {
          v16 = v31;
          v15 = CommonUtil::CUtilRegListener::Initialize(
                  v31,
                  v4,
                  L"Software\\Policies\\Microsoft\\Edge",
                  HKEY_LOCAL_MACHINE,
                  5u,
                  0xFFFFFFFF,
                  0x3E8u,
                  v28);
          if ( v15 >= 0 )
          {
            v31 = 0;
            v15 = 0;
            *((_QWORD *)this + 10) = v16;
          }
        }
        CommonUtil::AutoRef<ShieldProvider::NWPServiceWaitCancel>::~AutoRef<ShieldProvider::NWPServiceWaitCancel>(&v31);
        if ( v15 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
            (unsigned int)v15);
        v30 = *v9;
        CommonUtil::AutoRef<CommonUtil::IUtilRegListenerCallback>::Release((char *)this + 88);
        v31 = 0;
        v17 = CommonUtil::CreateNewRefObject<CommonUtil::CUtilRegListener>(&v31);
        if ( v17 >= 0 )
        {
          v18 = v31;
          v17 = CommonUtil::CUtilRegListener::Initialize(
                  v31,
                  v4,
                  L"Software\\Policies\\Microsoft\\Edge",
                  v30,
                  5u,
                  0xFFFFFFFF,
                  0x3E8u,
                  v28);
          if ( v17 >= 0 )
          {
            v31 = 0;
            v17 = 0;
            *((_QWORD *)this + 11) = v18;
          }
          v8 = v29;
        }
        CommonUtil::AutoRef<ShieldProvider::NWPServiceWaitCancel>::~AutoRef<ShieldProvider::NWPServiceWaitCancel>(&v31);
        if ( v17 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
            (unsigned int)v17);
        v19 = *v9;
        CommonUtil::AutoRef<CommonUtil::IUtilRegListenerCallback>::Release((char *)this + 96);
        v31 = 0;
        v20 = CommonUtil::CreateNewRefObject<CommonUtil::CUtilRegListener>(&v31);
        if ( v20 >= 0 )
        {
          v21 = v19;
          v22 = v31;
          v20 = CommonUtil::CUtilRegListener::Initialize(
                  v31,
                  v4,
                  L"Software\\Microsoft\\Edge",
                  v21,
                  5u,
                  0xFFFFFFFF,
                  0x3E8u,
                  v28);
          if ( v20 >= 0 )
          {
            v31 = 0;
            v20 = 0;
            *((_QWORD *)this + 12) = v22;
          }
        }
        CommonUtil::AutoRef<ShieldProvider::NWPServiceWaitCancel>::~AutoRef<ShieldProvider::NWPServiceWaitCancel>(&v31);
        if ( v20 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            58,
            WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
            (unsigned int)v20);
        CommonUtil::AutoRef<CommonUtil::IUtilRegListenerCallback>::Release((char *)this + 104);
        v31 = 0;
        v23 = CommonUtil::CreateNewRefObject<CommonUtil::CUtilRegListener>(&v31);
        if ( v23 >= 0 )
        {
          v24 = v31;
          v23 = CommonUtil::CUtilRegListener::Initialize(
                  v31,
                  v8,
                  L"SOFTWARE\\Microsoft\\Windows Defender",
                  HKEY_LOCAL_MACHINE,
                  5u,
                  0xFFFFFFFF,
                  0x3E8u,
                  v28);
          if ( v23 >= 0 )
          {
            v31 = 0;
            v23 = 0;
            *((_QWORD *)this + 13) = v24;
          }
        }
        CommonUtil::AutoRef<ShieldProvider::NWPServiceWaitCancel>::~AutoRef<ShieldProvider::NWPServiceWaitCancel>(&v31);
        if ( v23 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            59,
            WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
            (unsigned int)v23);
        CommonUtil::AutoRef<CommonUtil::IUtilRegListenerCallback>::Release((char *)this + 112);
        v31 = 0;
        v25 = CommonUtil::CreateNewRefObject<CommonUtil::CUtilRegListener>(&v31);
        if ( v25 >= 0 )
        {
          v26 = v31;
          v25 = CommonUtil::CUtilRegListener::Initialize(
                  v31,
                  v8,
                  (const unsigned __int16 *)&stru_1800FCD70,
                  HKEY_LOCAL_MACHINE,
                  5u,
                  0xFFFFFFFF,
                  0x3E8u,
                  v28);
          if ( v25 >= 0 )
          {
            v31 = 0;
            v25 = 0;
            *((_QWORD *)this + 14) = v26;
          }
        }
        CommonUtil::AutoRef<ShieldProvider::NWPServiceWaitCancel>::~AutoRef<ShieldProvider::NWPServiceWaitCancel>(&v31);
        if ( v25 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
            (unsigned int)v25);
        v12 = 0;
        goto LABEL_53;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_53:
        CommonUtil::AutoRef<ShieldProvider::NWPServiceWaitCancel>::~AutoRef<ShieldProvider::NWPServiceWaitCancel>(&v33);
        goto LABEL_57;
      }
      v14 = 55;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      v12 = -2147024882;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_53;
      v14 = 54;
    }
    WPP_SF_d(v13[2], v14, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids, v12);
    goto LABEL_53;
  }
  v12 = -2147024882;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids, 2147942414LL);
LABEL_57:
  CommonUtil::AutoRef<ShieldProvider::NWPServiceWaitCancel>::~AutoRef<ShieldProvider::NWPServiceWaitCancel>(&v32);
  return v12;
}

```

## disassembly

```asm
0x180070f60  mov     [rsp-38h+arg_0], rbx
0x180070f65  push    rbp
0x180070f66  push    rsi
0x180070f67  push    rdi
0x180070f68  push    r12
0x180070f6a  push    r13
0x180070f6c  push    r14
0x180070f6e  push    r15
0x180070f70  mov     rbp, rsp
0x180070f73  sub     rsp, 50h
0x180070f77  mov     rdx, rcx
0x180070f7a  mov     [rbp+arg_10], 0
0x180070f82  mov     r15, rcx
0x180070f85  lea     rcx, [rbp+arg_8]
0x180070f89  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180070f8e  lea     rcx, [rbp+arg_10]
0x180070f92  mov     rbx, rax
0x180070f95  call    ?Release@?$AutoRef@UIUtilRegListenerCallback@CommonUtil@@@CommonUtil@@QEAAXXZ; CommonUtil::AutoRef<CommonUtil::IUtilRegListenerCallback>::Release(void)
0x180070f9a  mov     edi, 18h
0x180070f9f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180070fa6  mov     ecx, edi; unsigned __int64
0x180070fa8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180070fad  mov     r12, rax
0x180070fb0  test    rax, rax
0x180070fb3  jz      loc_18007141F
0x180070fb9  mov     dword ptr [rax+8], 0
0x180070fc0  lea     rax, ??_7?$CRegListenerFunctorAdapter@V_lambda_71059ac68cae7094b9a0a55750988db9_@@@CommonUtil@@6B@; const CommonUtil::CRegListenerFunctorAdapter<_lambda_71059ac68cae7094b9a0a55750988db9_>::`vftable'
0x180070fc7  mov     [r12], rax
0x180070fcb  mov     rcx, [rbx]
0x180070fce  mov     rax, [rax]
0x180070fd1  mov     [r12+10h], rcx
0x180070fd6  mov     rcx, r12
0x180070fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070fde  mov     [rbp+arg_10], r12
0x180070fe2  call    ?NotifyClientsOnPua@AppAndBrowserShield@ShieldProvider@@AEAAJXZ; ShieldProvider::AppAndBrowserShield::NotifyClientsOnPua(void)
0x180070fe7  mov     rdx, r15
0x180070fea  mov     [rbp+arg_18], 0
0x180070ff2  lea     rcx, [rbp+arg_8]
0x180070ff6  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180070ffb  lea     rcx, [rbp+arg_18]
0x180070fff  mov     rbx, rax
0x180071002  call    ?Release@?$AutoRef@UIUtilRegListenerCallback@CommonUtil@@@CommonUtil@@QEAAXXZ; CommonUtil::AutoRef<CommonUtil::IUtilRegListenerCallback>::Release(void)
0x180071007  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007100e  mov     ecx, edi; unsigned __int64
0x180071010  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180071015  mov     [rbp+var_10], rax
0x180071019  mov     r13, rax
0x18007101c  test    rax, rax
0x18007101f  jz      loc_1800713DE
0x180071025  mov     dword ptr [rax+8], 0
0x18007102c  lea     rax, ??_7?$CRegListenerFunctorAdapter@V_lambda_18155f7eae7a246170d1f10899b2a74e_@@@CommonUtil@@6B@; const CommonUtil::CRegListenerFunctorAdapter<_lambda_18155f7eae7a246170d1f10899b2a74e_>::`vftable'
0x180071033  mov     [r13+0], rax
0x180071037  mov     rcx, [rbx]
0x18007103a  mov     rax, [rax]
0x18007103d  mov     [r13+10h], rcx
0x180071041  mov     rcx, r13
0x180071044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071049  lea     rsi, [r15+48h]
0x18007104d  mov     [rbp+arg_18], r13
0x180071051  mov     rcx, [rsi]; hKey
0x180071054  test    rcx, rcx
0x180071057  jz      short loc_180071066
0x180071059  call    cs:__imp_RegCloseKey
0x18007105f  mov     qword ptr [rsi], 0
0x180071066  mov     rdx, rsi; phkResult
0x180071069  mov     ecx, 20006h; samDesired
0x18007106e  call    cs:__imp_RegOpenCurrentUser
0x180071074  mov     ebx, eax
0x180071076  test    eax, eax
0x180071078  jz      short loc_1800710B4
0x18007107a  jle     short loc_180071085
0x18007107c  movzx   ebx, ax
0x18007107f  or      ebx, 80070000h
0x180071085  test    ebx, ebx
0x180071087  jns     short loc_1800710B4
0x180071089  mov     rcx, cs:WPP_GLOBAL_Control
0x180071090  lea     rdi, WPP_GLOBAL_Control
0x180071097  cmp     rcx, rdi
0x18007109a  jz      loc_180071414
0x1800710a0  test    byte ptr [rcx+1Ch], 1
0x1800710a4  jz      loc_180071414
0x1800710aa  mov     edx, 37h ; '7'
0x1800710af  jmp     loc_180071401
0x1800710b4  lea     rcx, [r15+50h]
0x1800710b8  call    ?Release@?$AutoRef@UIUtilRegListenerCallback@CommonUtil@@@CommonUtil@@QEAAXXZ; CommonUtil::AutoRef<CommonUtil::IUtilRegListenerCallback>::Release(void)
0x1800710bd  lea     rcx, [rbp+arg_8]
0x1800710c1  mov     [rbp+arg_8], 0
0x1800710c9  call    ??$CreateNewRefObject@VCUtilRegListener@CommonUtil@@@CommonUtil@@YAJPEAPEAVCUtilRegListener@0@@Z; CommonUtil::CreateNewRefObject<CommonUtil::CUtilRegListener>(CommonUtil::CUtilRegListener * *)
0x1800710ce  mov     ebx, eax
0x1800710d0  test    eax, eax
0x1800710d2  js      short loc_18007111D
0x1800710d4  mov     r14, [rbp+arg_8]
0x1800710d8  lea     r8, aSoftwarePolici_2; "Software\\Policies\\Microsoft\\Edge"
0x1800710df  mov     [rsp+50h+var_20], 3E8h; unsigned int
0x1800710e7  mov     rcx, r14; this
0x1800710ea  mov     [rsp+50h+var_28], 0FFFFFFFFh; unsigned int
0x1800710f2  mov     r9, 0FFFFFFFF80000002h; HKEY
0x1800710f9  mov     rdx, r12; struct CommonUtil::IUtilRegListenerCallback *
0x1800710fc  mov     [rsp+50h+var_30], 5; unsigned int
0x180071104  call    ?Initialize@CUtilRegListener@CommonUtil@@QEAAJPEAUIUtilRegListenerCallback@2@PEBGPEAUHKEY__@@KKKK@Z; CommonUtil::CUtilRegListener::Initialize(CommonUtil::IUtilRegListenerCallback *,ushort const *,HKEY__ *,ulong,ulong,ulong,ulong)
0x180071109  mov     ebx, eax
0x18007110b  test    eax, eax
0x18007110d  js      short loc_18007111D
0x18007110f  mov     [rbp+arg_8], 0
0x180071117  xor     ebx, ebx
0x180071119  mov     [r15+50h], r14
0x18007111d  lea     rcx, [rbp+arg_8]
0x180071121  call    ??1?$AutoRef@VNWPServiceWaitCancel@ShieldProvider@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<ShieldProvider::NWPServiceWaitCancel>::~AutoRef<ShieldProvider::NWPServiceWaitCancel>(void)
0x180071126  lea     rdi, WPP_GLOBAL_Control
0x18007112d  test    ebx, ebx
0x18007112f  jns     short loc_18007115B
0x180071131  mov     rcx, cs:WPP_GLOBAL_Control
0x180071138  cmp     rcx, rdi
0x18007113b  jz      short loc_18007115B
0x18007113d  test    byte ptr [rcx+1Ch], 1
0x180071141  jz      short loc_18007115B
0x180071143  mov     rcx, [rcx+10h]
0x180071147  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18007114e  mov     edx, 38h ; '8'
0x180071153  mov     r9d, ebx
0x180071156  call    WPP_SF_d
0x18007115b  mov     rax, [rsi]
0x18007115e  lea     rcx, [r15+58h]
0x180071162  mov     [rbp+var_8], rax
0x180071166  call    ?Release@?$AutoRef@UIUtilRegListenerCallback@CommonUtil@@@CommonUtil@@QEAAXXZ; CommonUtil::AutoRef<CommonUtil::IUtilRegListenerCallback>::Release(void)
0x18007116b  lea     rcx, [rbp+arg_8]
0x18007116f  mov     [rbp+arg_8], 0
0x180071177  call    ??$CreateNewRefObject@VCUtilRegListener@CommonUtil@@@CommonUtil@@YAJPEAPEAVCUtilRegListener@0@@Z; CommonUtil::CreateNewRefObject<CommonUtil::CUtilRegListener>(CommonUtil::CUtilRegListener * *)
0x18007117c  mov     ebx, eax
0x18007117e  test    eax, eax
0x180071180  js      short loc_1800711CC
0x180071182  mov     r13, [rbp+arg_8]
0x180071186  lea     r8, aSoftwarePolici_2; "Software\\Policies\\Microsoft\\Edge"
0x18007118d  mov     r9, [rbp+var_8]; HKEY
0x180071191  mov     rcx, r13; this
0x180071194  mov     [rsp+50h+var_20], 3E8h; unsigned int
0x18007119c  mov     rdx, r12; struct CommonUtil::IUtilRegListenerCallback *
0x18007119f  mov     [rsp+50h+var_28], 0FFFFFFFFh; unsigned int
0x1800711a7  mov     [rsp+50h+var_30], 5; unsigned int
0x1800711af  call    ?Initialize@CUtilRegListener@CommonUtil@@QEAAJPEAUIUtilRegListenerCallback@2@PEBGPEAUHKEY__@@KKKK@Z; CommonUtil::CUtilRegListener::Initialize(CommonUtil::IUtilRegListenerCallback *,ushort const *,HKEY__ *,ulong,ulong,ulong,ulong)
0x1800711b4  mov     ebx, eax
0x1800711b6  test    eax, eax
0x1800711b8  js      short loc_1800711C8
0x1800711ba  mov     [rbp+arg_8], 0
0x1800711c2  xor     ebx, ebx
0x1800711c4  mov     [r15+58h], r13
0x1800711c8  mov     r13, [rbp+var_10]
0x1800711cc  lea     rcx, [rbp+arg_8]
0x1800711d0  call    ??1?$AutoRef@VNWPServiceWaitCancel@ShieldProvider@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<ShieldProvider::NWPServiceWaitCancel>::~AutoRef<ShieldProvider::NWPServiceWaitCancel>(void)
0x1800711d5  test    ebx, ebx
0x1800711d7  jns     short loc_180071203
0x1800711d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800711e0  cmp     rcx, rdi
0x1800711e3  jz      short loc_180071203
0x1800711e5  test    byte ptr [rcx+1Ch], 1
0x1800711e9  jz      short loc_180071203
0x1800711eb  mov     rcx, [rcx+10h]
0x1800711ef  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x1800711f6  mov     edx, 39h ; '9'
0x1800711fb  mov     r9d, ebx
0x1800711fe  call    WPP_SF_d
0x180071203  mov     r14, [rsi]
0x180071206  lea     rcx, [r15+60h]
0x18007120a  call    ?Release@?$AutoRef@UIUtilRegListenerCallback@CommonUtil@@@CommonUtil@@QEAAXXZ; CommonUtil::AutoRef<CommonUtil::IUtilRegListenerCallback>::Release(void)
0x18007120f  lea     rcx, [rbp+arg_8]
0x180071213  mov     [rbp+arg_8], 0
0x18007121b  call    ??$CreateNewRefObject@VCUtilRegListener@CommonUtil@@@CommonUtil@@YAJPEAPEAVCUtilRegListener@0@@Z; CommonUtil::CreateNewRefObject<CommonUtil::CUtilRegListener>(CommonUtil::CUtilRegListener * *)
0x180071220  mov     ebx, eax
0x180071222  test    eax, eax
0x180071224  jns     short loc_18007122B
0x180071226  xor     r12d, r12d
0x180071229  jmp     short loc_180071270
0x18007122b  mov     r9, r14; HKEY
0x18007122e  mov     [rsp+50h+var_20], 3E8h; unsigned int
0x180071236  mov     r14, [rbp+arg_8]
0x18007123a  lea     r8, aSoftwareMicros_19; "Software\\Microsoft\\Edge"
0x180071241  mov     rcx, r14; this
0x180071244  mov     [rsp+50h+var_28], 0FFFFFFFFh; unsigned int
0x18007124c  mov     rdx, r12; struct CommonUtil::IUtilRegListenerCallback *
0x18007124f  mov     [rsp+50h+var_30], 5; unsigned int
0x180071257  call    ?Initialize@CUtilRegListener@CommonUtil@@QEAAJPEAUIUtilRegListenerCallback@2@PEBGPEAUHKEY__@@KKKK@Z; CommonUtil::CUtilRegListener::Initialize(CommonUtil::IUtilRegListenerCallback *,ushort const *,HKEY__ *,ulong,ulong,ulong,ulong)
0x18007125c  xor     r12d, r12d
0x18007125f  mov     ebx, eax
0x180071261  test    eax, eax
0x180071263  js      short loc_180071270
0x180071265  mov     [rbp+arg_8], r12
0x180071269  mov     ebx, r12d
0x18007126c  mov     [r15+60h], r14
0x180071270  lea     rcx, [rbp+arg_8]
0x180071274  call    ??1?$AutoRef@VNWPServiceWaitCancel@ShieldProvider@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<ShieldProvider::NWPServiceWaitCancel>::~AutoRef<ShieldProvider::NWPServiceWaitCancel>(void)
0x180071279  test    ebx, ebx
0x18007127b  jns     short loc_1800712A7
0x18007127d  mov     rcx, cs:WPP_GLOBAL_Control
0x180071284  cmp     rcx, rdi
0x180071287  jz      short loc_1800712A7
0x180071289  test    byte ptr [rcx+1Ch], 1
0x18007128d  jz      short loc_1800712A7
0x18007128f  mov     rcx, [rcx+10h]
0x180071293  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18007129a  mov     edx, 3Ah ; ':'
0x18007129f  mov     r9d, ebx
0x1800712a2  call    WPP_SF_d
0x1800712a7  lea     rcx, [r15+68h]
0x1800712ab  call    ?Release@?$AutoRef@UIUtilRegListenerCallback@CommonUtil@@@CommonUtil@@QEAAXXZ; CommonUtil::AutoRef<CommonUtil::IUtilRegListenerCallback>::Release(void)
0x1800712b0  lea     rcx, [rbp+arg_8]
0x1800712b4  mov     [rbp+arg_8], r12
0x1800712b8  call    ??$CreateNewRefObject@VCUtilRegListener@CommonUtil@@@CommonUtil@@YAJPEAPEAVCUtilRegListener@0@@Z; CommonUtil::CreateNewRefObject<CommonUtil::CUtilRegListener>(CommonUtil::CUtilRegListener * *)
0x1800712bd  mov     ebx, eax
0x1800712bf  test    eax, eax
0x1800712c1  js      short loc_180071309
0x1800712c3  mov     r14, [rbp+arg_8]
0x1800712c7  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows Defender"
0x1800712ce  mov     [rsp+50h+var_20], 3E8h; unsigned int
0x1800712d6  mov     rcx, r14; this
0x1800712d9  mov     [rsp+50h+var_28], 0FFFFFFFFh; unsigned int
0x1800712e1  mov     r9, 0FFFFFFFF80000002h; HKEY
0x1800712e8  mov     rdx, r13; struct CommonUtil::IUtilRegListenerCallback *
0x1800712eb  mov     [rsp+50h+var_30], 5; unsigned int
0x1800712f3  call    ?Initialize@CUtilRegListener@CommonUtil@@QEAAJPEAUIUtilRegListenerCallback@2@PEBGPEAUHKEY__@@KKKK@Z; CommonUtil::CUtilRegListener::Initialize(CommonUtil::IUtilRegListenerCallback *,ushort const *,HKEY__ *,ulong,ulong,ulong,ulong)
0x1800712f8  mov     ebx, eax
0x1800712fa  test    eax, eax
0x1800712fc  js      short loc_180071309
0x1800712fe  mov     [rbp+arg_8], r12
0x180071302  mov     ebx, r12d
0x180071305  mov     [r15+68h], r14
0x180071309  lea     rcx, [rbp+arg_8]
0x18007130d  call    ??1?$AutoRef@VNWPServiceWaitCancel@ShieldProvider@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<ShieldProvider::NWPServiceWaitCancel>::~AutoRef<ShieldProvider::NWPServiceWaitCancel>(void)
0x180071312  test    ebx, ebx
0x180071314  jns     short loc_180071340
0x180071316  mov     rcx, cs:WPP_GLOBAL_Control
0x18007131d  cmp     rcx, rdi
0x180071320  jz      short loc_180071340
0x180071322  test    byte ptr [rcx+1Ch], 1
0x180071326  jz      short loc_180071340
0x180071328  mov     rcx, [rcx+10h]
0x18007132c  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x180071333  mov     edx, 3Bh ; ';'
0x180071338  mov     r9d, ebx
0x18007133b  call    WPP_SF_d
0x180071340  lea     rcx, [r15+70h]
0x180071344  call    ?Release@?$AutoRef@UIUtilRegListenerCallback@CommonUtil@@@CommonUtil@@QEAAXXZ; CommonUtil::AutoRef<CommonUtil::IUtilRegListenerCallback>::Release(void)
0x180071349  lea     rcx, [rbp+arg_8]
0x18007134d  mov     [rbp+arg_8], r12
0x180071351  call    ??$CreateNewRefObject@VCUtilRegListener@CommonUtil@@@CommonUtil@@YAJPEAPEAVCUtilRegListener@0@@Z; CommonUtil::CreateNewRefObject<CommonUtil::CUtilRegListener>(CommonUtil::CUtilRegListener * *)
0x180071356  mov     ebx, eax
0x180071358  test    eax, eax
0x18007135a  js      short loc_1800713A2
0x18007135c  mov     r14, [rbp+arg_8]
0x180071360  lea     r8, stru_1800FCD70; unsigned __int16 *
0x180071367  mov     [rsp+50h+var_20], 3E8h; unsigned int
0x18007136f  mov     rcx, r14; this
0x180071372  mov     [rsp+50h+var_28], 0FFFFFFFFh; unsigned int
0x18007137a  mov     r9, 0FFFFFFFF80000002h; HKEY
0x180071381  mov     rdx, r13; struct CommonUtil::IUtilRegListenerCallback *
0x180071384  mov     [rsp+50h+var_30], 5; unsigned int
0x18007138c  call    ?Initialize@CUtilRegListener@CommonUtil@@QEAAJPEAUIUtilRegListenerCallback@2@PEBGPEAUHKEY__@@KKKK@Z; CommonUtil::CUtilRegListener::Initialize(CommonUtil::IUtilRegListenerCallback *,ushort const *,HKEY__ *,ulong,ulong,ulong,ulong)
0x180071391  mov     ebx, eax
0x180071393  test    eax, eax
0x180071395  js      short loc_1800713A2
0x180071397  mov     [rbp+arg_8], r12
0x18007139b  mov     ebx, r12d
0x18007139e  mov     [r15+70h], r14
0x1800713a2  lea     rcx, [rbp+arg_8]
0x1800713a6  call    ??1?$AutoRef@VNWPServiceWaitCancel@ShieldProvider@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<ShieldProvider::NWPServiceWaitCancel>::~AutoRef<ShieldProvider::NWPServiceWaitCancel>(void)
0x1800713ab  test    ebx, ebx
0x1800713ad  jns     short loc_1800713D9
0x1800713af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800713b6  cmp     rcx, rdi
0x1800713b9  jz      short loc_1800713D9
0x1800713bb  test    byte ptr [rcx+1Ch], 1
0x1800713bf  jz      short loc_1800713D9
0x1800713c1  mov     rcx, [rcx+10h]
0x1800713c5  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x1800713cc  mov     edx, 3Ch ; '<'
0x1800713d1  mov     r9d, ebx
0x1800713d4  call    WPP_SF_d
0x1800713d9  mov     ebx, r12d
0x1800713dc  jmp     short loc_180071414
0x1800713de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800713e5  lea     rdi, WPP_GLOBAL_Control
0x1800713ec  mov     ebx, 8007000Eh
0x1800713f1  cmp     rcx, rdi
0x1800713f4  jz      short loc_180071414
0x1800713f6  test    byte ptr [rcx+1Ch], 1
0x1800713fa  jz      short loc_180071414
0x1800713fc  mov     edx, 36h ; '6'
0x180071401  mov     rcx, [rcx+10h]
0x180071405  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18007140c  mov     r9d, ebx
0x18007140f  call    WPP_SF_d
0x180071414  lea     rcx, [rbp+arg_18]
0x180071418  call    ??1?$AutoRef@VNWPServiceWaitCancel@ShieldProvider@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<ShieldProvider::NWPServiceWaitCancel>::~AutoRef<ShieldProvider::NWPServiceWaitCancel>(void)
0x18007141d  jmp     short loc_180071455
0x18007141f  mov     rcx, cs:WPP_GLOBAL_Control
0x180071426  lea     rdi, WPP_GLOBAL_Control
0x18007142d  mov     ebx, 8007000Eh
0x180071432  cmp     rcx, rdi
0x180071435  jz      short loc_180071455
0x180071437  test    byte ptr [rcx+1Ch], 1
0x18007143b  jz      short loc_180071455
  ... truncated ...
```
