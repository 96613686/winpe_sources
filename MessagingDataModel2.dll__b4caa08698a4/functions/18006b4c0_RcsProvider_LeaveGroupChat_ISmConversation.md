# RcsProvider::LeaveGroupChat(ISmConversation *)

- ea: `0x18006b4c0`
- end: `0x18006ba0b`
- name: `?LeaveGroupChat@RcsProvider@@UEAAJPEAUISmConversation@@@Z`
- size: `1355`
- prototype: `__int64 __fastcall(RcsProvider *__hidden this, struct ISmConversation *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005c50`
- `0x180008870`
- `0x18000f3ac`
- `0x18001ed38`
- `0x1800282f8`
- `0x18004cd88`
- `0x18004d830`
- `0x18004eab0`
- `0x18005f340`
- `0x18006a8c8`
- `0x18006b4c0`
- `0x18006ba44`
- `0x1800c6902`
- `0x1800c6940`
- `0x1800c6a00`
- `0x1800c8010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006b9dc`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b9dc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006b630`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006b75a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006b630`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006b75a`
- `PhoneOm!PhoneGetProviderLineInfo` at `0x18006b5f2`
- `PhoneOm!PhoneGetProviderLineInfo` at `0x18006b5f2`

## pseudocode

```c
__int64 __fastcall RcsProvider::LeaveGroupChat(RcsProvider *this, struct ISmConversation *a2)
{
  __int64 v2; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  __int64 (__fastcall *v8)(RcsProvider *, BSTR, __int64 *); // rbx
  __int64 *v9; // rax
  int ProviderLineInfo; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  HRESULT v13; // eax
  HRESULT v14; // eax
  __int64 v15; // r9
  __int64 (__fastcall *v16)(struct ISmConversation *, __int64, __int64, __int64, LPVOID, __int64 *); // rax
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  int v21; // eax
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v25; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+58h] [rbp-A8h] BYREF
  int v27; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v28; // [rsp+64h] [rbp-9Ch] BYREF
  _QWORD v29[2]; // [rsp+68h] [rbp-98h] BYREF
  __int16 v30; // [rsp+78h] [rbp-88h] BYREF
  __int64 v31; // [rsp+7Ah] [rbp-86h]
  int v32; // [rsp+82h] [rbp-7Eh]
  __int16 v33; // [rsp+86h] [rbp-7Ah]
  BSTR bstrString; // [rsp+88h] [rbp-78h] BYREF
  __int64 v35; // [rsp+90h] [rbp-70h] BYREF
  __int128 v36; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v37[1616]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v38[9968]; // [rsp+700h] [rbp+600h] BYREF
  _BYTE v39[1616]; // [rsp+2DF0h] [rbp+2CF0h] BYREF

  v2 = *(_QWORD *)a2;
  bstrString = 0;
  v5 = (*(__int64 (__fastcall **)(struct ISmConversation *, BSTR *))(v2 + 64))(a2, &bstrString);
  v6 = v5;
  if ( v5 < 0 )
  {
    Log_HREvent_47(v5);
    goto LABEL_39;
  }
  v7 = *(_QWORD *)this;
  v24 = 0;
  v8 = *(__int64 (__fastcall **)(RcsProvider *, BSTR, __int64 *))(v7 + 120);
  v9 = tlx::replace<RcsChatAdapter,&void _RcsAdapterShutdownableDeleter<RcsChatAdapter>(RcsChatAdapter *)>(&v24);
  ProviderLineInfo = v8(this, bstrString, v9);
  v6 = ProviderLineInfo;
  if ( ProviderLineInfo < 0 )
    goto LABEL_4;
  ProviderLineInfo = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 112LL))(v24);
  v6 = ProviderLineInfo;
  if ( ProviderLineInfo < 0 )
    goto LABEL_4;
  v11 = *((_QWORD *)this + 12);
  v12 = *((unsigned int *)this + 22);
  v36 = 0;
  ProviderLineInfo = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v11 + 72LL))(v11, v12, &v36);
  v6 = ProviderLineInfo;
  if ( ProviderLineInfo < 0
    || (memset_0(v37, 0, sizeof(v37)),
        ProviderLineInfo = PhoneGetProviderLineInfo(&v36, v37),
        v6 = ProviderLineInfo,
        ProviderLineInfo < 0) )
  {
LABEL_4:
    Log_HREvent_47(ProviderLineInfo);
    goto LABEL_5;
  }
  ppv = 0;
  v13 = CoCreateInstance(
          &GUID_a35c5b62_6032_4caf_bb23_f0556bff94ff,
          0,
          0x17u,
          &GUID_22f73986_0e72_4b34_be10_cea0fadde335,
          &ppv);
  v6 = v13;
  if ( v13 < 0 )
    goto LABEL_11;
  v13 = (*(__int64 (__fastcall **)(LPVOID, _BYTE *))(*(_QWORD *)ppv + 32LL))(ppv, v37);
  v6 = v13;
  if ( v13 < 0 )
    goto LABEL_11;
  v13 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 48LL))(ppv, 1);
  v6 = v13;
  if ( v13 < 0 )
    goto LABEL_11;
  v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 64LL))(ppv, *((unsigned int *)this + 22));
  v6 = v13;
  if ( v13 < 0
    || (v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 96LL))(ppv, 0), v6 = v13, v13 < 0)
    || (v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 80LL))(ppv, 0), v6 = v13, v13 < 0)
    || (v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)ppv + 112LL))(ppv, 0, 0), v6 = v13, v13 < 0) )
  {
LABEL_11:
    Log_HREvent_47(v13);
LABEL_12:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
LABEL_5:
    if ( v24 )
      _RcsAdapterShutdownableDeleter<RcsServiceStatusAdapterImpl>(v24);
    goto LABEL_39;
  }
  v25 = 0;
  v14 = CoCreateInstance(
          &GUID_630bb917_aa3b_4cf5_9d24_aad1f7d4297a,
          0,
          0x17u,
          &GUID_7fe02dbd_7d62_419f_9e37_87c89b8799e6,
          &v25);
  v6 = v14;
  if ( v14 < 0
    || (v14 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v25 + 64LL))(v25, ppv), v6 = v14, v14 < 0) )
  {
    Log_HREvent_47(v14);
LABEL_22:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    goto LABEL_12;
  }
  v15 = *((unsigned int *)this + 22);
  v16 = *(__int64 (__fastcall **)(struct ISmConversation *, __int64, __int64, __int64, LPVOID, __int64 *))(*(_QWORD *)a2 + 120LL);
  v26 = 0;
  v17 = v16(a2, 1, 10003, v15, v25, &v26);
  v6 = v17;
  if ( v17 < 0 )
  {
    Log_HREvent_47(v17);
LABEL_26:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
    goto LABEL_22;
  }
  v18 = *((_QWORD *)this + 12);
  v19 = *((unsigned int *)this + 22);
  v31 = 0;
  v33 = 0;
  v29[0] = &v30;
  v29[1] = &v30;
  v30 = 0;
  v27 = 0;
  v32 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, __int64, int *, _QWORD *))(*(_QWORD *)v18 + 40LL))(v18, v19, &v27, v29);
  v6 = v20;
  if ( v20 < 0 )
  {
    Log_HREvent_47(v20);
LABEL_29:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v29);
    goto LABEL_26;
  }
  memset_0(v38, 0, 0x2D40u);
  MessagingSettings::MessagingSettings((MessagingSettings *)v38);
  v21 = MessagingSettings::Initialize(
          (MessagingSettings *)v38,
          *((_DWORD *)this + 22),
          (const unsigned __int16 *)(v29[0] & -(__int64)(v27 != 0)));
  v6 = v21;
  if ( v21 < 0 )
    goto LABEL_31;
  v28 = 0;
  v21 = BaseConfigValue<unsigned long>::Get(v39, &v28);
  v6 = v21;
  if ( v21 < 0 )
    goto LABEL_31;
  FileTime64::Now(&v35);
  FileTime64::Advance((FileTime64 *)&v35, 10000LL * v28);
  v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 160LL))(v26, v35);
  v6 = v21;
  if ( v21 < 0
    || (v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 352LL))(v26, 1), v6 = v21, v21 < 0)
    || (v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 232LL))(v26), v6 = v21, v21 < 0) )
  {
LABEL_31:
    Log_HREvent_47(v21);
    MessagingSettings::~MessagingSettings((MessagingSettings *)v38);
    goto LABEL_29;
  }
  MessagingSettings::~MessagingSettings((MessagingSettings *)v38);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v29);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  if ( v24 )
    _RcsAdapterShutdownableDeleter<RcsServiceStatusAdapterImpl>(v24);
  v6 = 0;
LABEL_39:
  SysFreeString(bstrString);
  return v6;
}

```

## disassembly

```asm
0x18006b4c0  mov     [rsp-8+arg_10], rbx
0x18006b4c5  mov     [rsp-8+arg_18], rsi
0x18006b4ca  push    rbp
0x18006b4cb  push    rdi
0x18006b4cc  push    r14
0x18006b4ce  lea     rbp, [rsp-3350h]
0x18006b4d6  mov     eax, 3450h
0x18006b4db  call    _alloca_probe
0x18006b4e0  sub     rsp, rax
0x18006b4e3  mov     rax, cs:__security_cookie
0x18006b4ea  xor     rax, rsp
0x18006b4ed  mov     [rbp+3360h+var_20], rax
0x18006b4f4  mov     rax, [rdx]
0x18006b4f7  mov     r14, rdx
0x18006b4fa  mov     rsi, rcx
0x18006b4fd  mov     [rbp+3360h+bstrString], 0
0x18006b505  lea     rdx, [rbp+3360h+bstrString]
0x18006b509  mov     rcx, r14
0x18006b50c  mov     rax, [rax+40h]
0x18006b510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b515  mov     ebx, eax
0x18006b517  test    eax, eax
0x18006b519  jns     short loc_18006B532
0x18006b51b  mov     edx, 1
0x18006b520  mov     r9d, 194h
0x18006b526  mov     ecx, eax; int
0x18006b528  call    Log_HREvent_47
0x18006b52d  jmp     loc_18006B9D8
0x18006b532  mov     rax, [rsi]
0x18006b535  lea     rcx, [rsp+3460h+var_3418]
0x18006b53a  mov     [rsp+3460h+var_3418], 0
0x18006b543  mov     rbx, [rax+78h]
0x18006b547  call    ??$replace@VRcsChatAdapter@@$1??$_RcsAdapterShutdownableDeleter@VRcsChatAdapter@@@@YAXPEAV1@@Z@tlx@@YAPEAPEAVRcsChatAdapter@@AEAV?$auto_ptr@VRcsChatAdapter@@$1??$_RcsAdapterShutdownableDeleter@VRcsChatAdapter@@@@YAXPEAV1@@Z@0@@Z; tlx::replace<RcsChatAdapter,&_RcsAdapterShutdownableDeleter<RcsChatAdapter>(RcsChatAdapter *)>(tlx::auto_ptr<RcsChatAdapter,&_RcsAdapterShutdownableDeleter<RcsChatAdapter>(RcsChatAdapter *)> &)
0x18006b54c  mov     rdx, [rbp+3360h+bstrString]
0x18006b550  mov     r8, rax
0x18006b553  mov     rax, rbx
0x18006b556  mov     rcx, rsi
0x18006b559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b55e  mov     ebx, eax
0x18006b560  test    eax, eax
0x18006b562  jns     short loc_18006B58E
0x18006b564  mov     r9d, 197h
0x18006b56a  mov     edx, 1
0x18006b56f  mov     ecx, eax; int
0x18006b571  call    Log_HREvent_47
0x18006b576  mov     rcx, [rsp+3460h+var_3418]
0x18006b57b  test    rcx, rcx
0x18006b57e  jz      loc_18006B9D8
0x18006b584  call    ??$_RcsAdapterShutdownableDeleter@VRcsServiceStatusAdapterImpl@@@@YAXPEAVRcsServiceStatusAdapterImpl@@@Z; _RcsAdapterShutdownableDeleter<RcsServiceStatusAdapterImpl>(RcsServiceStatusAdapterImpl *)
0x18006b589  jmp     loc_18006B9D8
0x18006b58e  mov     rcx, [rsp+3460h+var_3418]
0x18006b593  mov     rax, [rcx]
0x18006b596  mov     rax, [rax+70h]
0x18006b59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b59f  mov     ebx, eax
0x18006b5a1  test    eax, eax
0x18006b5a3  jns     short loc_18006B5AD
0x18006b5a5  mov     r9d, 199h
0x18006b5ab  jmp     short loc_18006B56A
0x18006b5ad  mov     rcx, [rsi+60h]
0x18006b5b1  lea     r8, [rbp+3360h+var_33C8]
0x18006b5b5  mov     edx, [rsi+58h]
0x18006b5b8  xorps   xmm0, xmm0
0x18006b5bb  movups  [rbp+3360h+var_33C8], xmm0
0x18006b5bf  mov     rax, [rcx]
0x18006b5c2  mov     rax, [rax+48h]
0x18006b5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b5cb  mov     ebx, eax
0x18006b5cd  test    eax, eax
0x18006b5cf  jns     short loc_18006B5D9
0x18006b5d1  mov     r9d, 19Dh
0x18006b5d7  jmp     short loc_18006B56A
0x18006b5d9  xor     edx, edx; Val
0x18006b5db  lea     rcx, [rbp+3360h+var_33B0]; void *
0x18006b5df  mov     r8d, 650h; Size
0x18006b5e5  call    memset_0
0x18006b5ea  lea     rdx, [rbp+3360h+var_33B0]
0x18006b5ee  lea     rcx, [rbp+3360h+var_33C8]
0x18006b5f2  call    cs:__imp_PhoneGetProviderLineInfo
0x18006b5f8  mov     ebx, eax
0x18006b5fa  test    eax, eax
0x18006b5fc  jns     short loc_18006B609
0x18006b5fe  mov     r9d, 1A0h
0x18006b604  jmp     loc_18006B56A
0x18006b609  xor     edx, edx; pUnkOuter
0x18006b60b  mov     [rsp+3460h+var_3420], 0
0x18006b614  lea     rax, [rsp+3460h+var_3420]
0x18006b619  lea     r9, _GUID_22f73986_0e72_4b34_be10_cea0fadde335; riid
0x18006b620  mov     [rsp+3460h+ppv], rax; ppv
0x18006b625  lea     rcx, _GUID_a35c5b62_6032_4caf_bb23_f0556bff94ff; rclsid
0x18006b62c  lea     r8d, [rdx+17h]; dwClsContext
0x18006b630  call    cs:__imp_CoCreateInstance
0x18006b636  mov     ebx, eax
0x18006b638  test    eax, eax
0x18006b63a  jns     short loc_18006B65D
0x18006b63c  mov     r9d, 1A4h
0x18006b642  mov     edx, 1
0x18006b647  mov     ecx, eax; int
0x18006b649  call    Log_HREvent_47
0x18006b64e  lea     rcx, [rsp+3460h+var_3420]
0x18006b653  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006b658  jmp     loc_18006B576
0x18006b65d  mov     rcx, [rsp+3460h+var_3420]
0x18006b662  lea     rdx, [rbp+3360h+var_33B0]
0x18006b666  mov     rax, [rcx]
0x18006b669  mov     rax, [rax+20h]
0x18006b66d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b672  mov     ebx, eax
0x18006b674  test    eax, eax
0x18006b676  jns     short loc_18006B680
0x18006b678  mov     r9d, 1A5h
0x18006b67e  jmp     short loc_18006B642
0x18006b680  mov     rcx, [rsp+3460h+var_3420]
0x18006b685  mov     edi, 1
0x18006b68a  mov     edx, edi
0x18006b68c  mov     rax, [rcx]
0x18006b68f  mov     rax, [rax+30h]
0x18006b693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b698  mov     ebx, eax
0x18006b69a  test    eax, eax
0x18006b69c  jns     short loc_18006B6A8
0x18006b69e  mov     r9d, 1A6h
0x18006b6a4  mov     edx, edi
0x18006b6a6  jmp     short loc_18006B647
0x18006b6a8  mov     rcx, [rsp+3460h+var_3420]
0x18006b6ad  mov     edx, [rsi+58h]
0x18006b6b0  mov     rax, [rcx]
0x18006b6b3  mov     rax, [rax+40h]
0x18006b6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6bc  mov     ebx, eax
0x18006b6be  test    eax, eax
0x18006b6c0  jns     short loc_18006B6CA
0x18006b6c2  mov     r9d, 1A7h
0x18006b6c8  jmp     short loc_18006B6A4
0x18006b6ca  mov     rcx, [rsp+3460h+var_3420]
0x18006b6cf  xor     edx, edx
0x18006b6d1  mov     rax, [rcx]
0x18006b6d4  mov     rax, [rax+60h]
0x18006b6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6dd  mov     ebx, eax
0x18006b6df  test    eax, eax
0x18006b6e1  jns     short loc_18006B6EB
0x18006b6e3  mov     r9d, 1A8h
0x18006b6e9  jmp     short loc_18006B6A4
0x18006b6eb  mov     rcx, [rsp+3460h+var_3420]
0x18006b6f0  xor     edx, edx
0x18006b6f2  mov     rax, [rcx]
0x18006b6f5  mov     rax, [rax+50h]
0x18006b6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6fe  mov     ebx, eax
0x18006b700  test    eax, eax
0x18006b702  jns     short loc_18006B70C
0x18006b704  mov     r9d, 1A9h
0x18006b70a  jmp     short loc_18006B6A4
0x18006b70c  mov     rcx, [rsp+3460h+var_3420]
0x18006b711  xor     r8d, r8d
0x18006b714  xor     edx, edx
0x18006b716  mov     rax, [rcx]
0x18006b719  mov     rax, [rax+70h]
0x18006b71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b722  mov     ebx, eax
0x18006b724  test    eax, eax
0x18006b726  jns     short loc_18006B733
0x18006b728  mov     r9d, 1AAh
0x18006b72e  jmp     loc_18006B6A4
0x18006b733  xor     edx, edx; pUnkOuter
0x18006b735  mov     [rsp+3460h+var_3410], 0
0x18006b73e  lea     rax, [rsp+3460h+var_3410]
0x18006b743  lea     r9, _GUID_7fe02dbd_7d62_419f_9e37_87c89b8799e6; riid
0x18006b74a  mov     [rsp+3460h+ppv], rax; ppv
0x18006b74f  lea     rcx, _GUID_630bb917_aa3b_4cf5_9d24_aad1f7d4297a; rclsid
0x18006b756  lea     r8d, [rdx+17h]; dwClsContext
0x18006b75a  call    cs:__imp_CoCreateInstance
0x18006b760  mov     ebx, eax
0x18006b762  test    eax, eax
0x18006b764  jns     short loc_18006B784
0x18006b766  mov     r9d, 1ADh
0x18006b76c  mov     edx, edi
0x18006b76e  mov     ecx, eax; int
0x18006b770  call    Log_HREvent_47
0x18006b775  lea     rcx, [rsp+3460h+var_3410]
0x18006b77a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006b77f  jmp     loc_18006B64E
0x18006b784  mov     rcx, [rsp+3460h+var_3410]
0x18006b789  mov     rdx, [rsp+3460h+var_3420]
0x18006b78e  mov     rax, [rcx]
0x18006b791  mov     rax, [rax+40h]
0x18006b795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b79a  mov     ebx, eax
0x18006b79c  test    eax, eax
0x18006b79e  jns     short loc_18006B7A8
0x18006b7a0  mov     r9d, 1AEh
0x18006b7a6  jmp     short loc_18006B76C
0x18006b7a8  mov     rdx, [rsp+3460h+var_3410]
0x18006b7ad  lea     rcx, [rsp+3460h+var_3408]
0x18006b7b2  mov     rax, [r14]
0x18006b7b5  mov     r8d, 2713h
0x18006b7bb  mov     r9d, [rsi+58h]
0x18006b7bf  mov     [rsp+3460h+var_3438], rcx
0x18006b7c4  mov     rcx, r14
0x18006b7c7  mov     [rsp+3460h+ppv], rdx
0x18006b7cc  mov     edx, edi
0x18006b7ce  mov     rax, [rax+78h]
0x18006b7d2  mov     [rsp+3460h+var_3408], 0
0x18006b7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b7e0  mov     ebx, eax
0x18006b7e2  test    eax, eax
0x18006b7e4  jns     short loc_18006B804
0x18006b7e6  mov     r9d, 1B2h
0x18006b7ec  mov     edx, edi
0x18006b7ee  mov     ecx, eax; int
0x18006b7f0  call    Log_HREvent_47
0x18006b7f5  lea     rcx, [rsp+3460h+var_3408]
0x18006b7fa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006b7ff  jmp     loc_18006B775
0x18006b804  mov     rcx, [rsi+60h]
0x18006b808  lea     r9, [rsp+3460h+var_33F8]
0x18006b80d  mov     edx, [rsi+58h]
0x18006b810  lea     r8, [rsp+3460h+var_3400]
0x18006b815  xor     eax, eax
0x18006b817  mov     [rsp+3460h+var_33E6], 0
0x18006b820  mov     [rbp+3360h+var_33DA], ax
0x18006b824  lea     rax, [rsp+3460h+var_33E8]
0x18006b829  mov     [rsp+3460h+var_33F8], rax
0x18006b82e  lea     rax, [rsp+3460h+var_33E8]
0x18006b833  mov     [rsp+3460h+var_33F0], rax
0x18006b838  xor     eax, eax
0x18006b83a  mov     [rsp+3460h+var_33E8], ax
0x18006b83f  mov     [rsp+3460h+var_3400], eax
0x18006b843  mov     [rbp+3360h+var_33DE], 0
0x18006b84a  mov     rax, [rcx]
0x18006b84d  mov     rax, [rax+28h]
0x18006b851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b856  mov     ebx, eax
0x18006b858  test    eax, eax
0x18006b85a  jns     short loc_18006B87A
0x18006b85c  mov     r9d, 1B7h
0x18006b862  mov     edx, edi
0x18006b864  mov     ecx, eax; int
0x18006b866  call    Log_HREvent_47
0x18006b86b  lea     rcx, [rsp+3460h+var_33F8]
0x18006b870  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18006b875  jmp     loc_18006B7F5
0x18006b87a  xor     edx, edx; Val
0x18006b87c  lea     rcx, [rbp+3360h+var_2D60]; void *
0x18006b883  mov     r8d, 2D40h; Size
0x18006b889  call    memset_0
0x18006b88e  lea     rcx, [rbp+3360h+var_2D60]; this
0x18006b895  call    ??0MessagingSettings@@QEAA@XZ; MessagingSettings::MessagingSettings(void)
0x18006b89a  mov     eax, [rsp+3460h+var_3400]
0x18006b89e  lea     rcx, [rbp+3360h+var_2D60]; this
0x18006b8a5  mov     edx, [rsi+58h]; unsigned int
0x18006b8a8  neg     eax
0x18006b8aa  sbb     r8, r8
0x18006b8ad  and     r8, [rsp+3460h+var_33F8]; unsigned __int16 *
0x18006b8b2  call    ?Initialize@MessagingSettings@@QEAAJKPEBG@Z; MessagingSettings::Initialize(ulong,ushort const *)
0x18006b8b7  mov     ebx, eax
0x18006b8b9  test    eax, eax
0x18006b8bb  jns     short loc_18006B8DA
0x18006b8bd  mov     r9d, 1CAh
0x18006b8c3  mov     edx, edi
0x18006b8c5  mov     ecx, eax; int
0x18006b8c7  call    Log_HREvent_47
0x18006b8cc  lea     rcx, [rbp+3360h+var_2D60]; this
0x18006b8d3  call    ??1MessagingSettings@@UEAA@XZ; MessagingSettings::~MessagingSettings(void)
0x18006b8d8  jmp     short loc_18006B86B
0x18006b8da  lea     rdx, [rsp+3460h+var_33FC]
0x18006b8df  mov     [rsp+3460h+var_33FC], 0
0x18006b8e7  lea     rcx, [rbp+3360h+var_670]
0x18006b8ee  call    ?Get@?$BaseConfigValue@K@@QEAAJPEAK@Z; BaseConfigValue<ulong>::Get(ulong *)
0x18006b8f3  mov     ebx, eax
0x18006b8f5  test    eax, eax
0x18006b8f7  jns     short loc_18006B901
0x18006b8f9  mov     r9d, 1CDh
0x18006b8ff  jmp     short loc_18006B8C3
0x18006b901  lea     rcx, [rbp+3360h+var_33D0]
0x18006b905  call    ?Now@FileTime64@@SA?AT1@XZ; FileTime64::Now(void)
0x18006b90a  mov     eax, [rsp+3460h+var_33FC]
0x18006b90e  lea     rcx, [rbp+3360h+var_33D0]; this
0x18006b912  imul    rdx, rax, 2710h; unsigned __int64
0x18006b919  call    ?Advance@FileTime64@@QEAAJ_K@Z; FileTime64::Advance(unsigned __int64)
0x18006b91e  mov     rcx, [rsp+3460h+var_3408]
0x18006b923  mov     rdx, [rbp+3360h+var_33D0]
0x18006b927  mov     rax, [rcx]
0x18006b92a  mov     rax, [rax+0A0h]
0x18006b931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b936  mov     ebx, eax
0x18006b938  mov     edx, edi
0x18006b93a  test    eax, eax
0x18006b93c  jns     short loc_18006B949
0x18006b93e  mov     r9d, 1D0h
0x18006b944  jmp     loc_18006B8C5
0x18006b949  mov     rcx, [rsp+3460h+var_3408]
0x18006b94e  mov     rax, [rcx]
0x18006b951  mov     rax, [rax+160h]
0x18006b958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b95d  mov     ebx, eax
0x18006b95f  test    eax, eax
0x18006b961  jns     short loc_18006B96E
0x18006b963  mov     r9d, 1D2h
  ... truncated ...
```
