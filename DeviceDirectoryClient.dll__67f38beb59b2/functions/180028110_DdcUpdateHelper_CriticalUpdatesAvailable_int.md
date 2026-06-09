# DdcUpdateHelper::CriticalUpdatesAvailable(int *)

- ea: `0x180028110`
- end: `0x180028445`
- name: `?CriticalUpdatesAvailable@DdcUpdateHelper@@SAJPEAH@Z`
- size: `821`
- prototype: `__int64 __fastcall(int *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800183c4`

## callees

- `0x180004060`
- `0x1800050b8`
- `0x1800280f0`
- `0x180028110`
- `0x1800285e8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800281e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800281e7`

## string_xrefs

- `0x180028177`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcupdatehelper.cpp`
- `0x180028200`: `CHR(CoCreateInstance(__uuidof(UpdateSession), nullptr, CLSCTX_INPROC_SERVER, __uuidof(IUpdateSession), (void**)&pUpdateSession))`
- `0x180028258`: `CHR(pUpdateSession->CreateUpdateSearcher(&pUpdateSearcher))`
- `0x18002829d`: `CHR(pUpdateSearcher->put_Online(((VARIANT_BOOL)0)))`
- `0x1800282f8`: `CHR(pUpdateSearcher->Search(SelectionFilter.get(), &pSearchResult))`
- `0x18002834c`: `CHR(pSearchResult->get_Updates(&pUpdates))`
- `0x180028390`: `CHR(pUpdates->get_Count(&lCountOfUpdates))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DdcUpdateHelper::CriticalUpdatesAvailable(int *a1, int a2)
{
  __int64 v3; // rbx
  int v4; // edi
  __int64 *bstr; // rax
  HRESULT v6; // eax
  unsigned int v7; // r8d
  const char *v8; // r9
  LPVOID v9; // rsi
  __int64 (__fastcall *v10)(LPVOID, __int64 *); // rdi
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, __int64, __int64 *); // rdi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  __int64 v16; // [rsp+0h] [rbp-78h] BYREF
  LPVOID *ppv; // [rsp+20h] [rbp-58h]
  const char *v18; // [rsp+28h] [rbp-50h]
  __int64 v19; // [rsp+30h] [rbp-48h] BYREF
  LPVOID v20; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v21[7]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v23; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v24; // [rsp+88h] [rbp+10h] BYREF
  __int64 v25; // [rsp+90h] [rbp+18h] BYREF
  __int64 v26; // [rsp+98h] [rbp+20h] BYREF

  v20 = 0;
  v25 = 0;
  v19 = 0;
  v26 = 0;
  v23 = 0;
  v3 = 0;
  v21[0] = 0;
  if ( a1 )
  {
    try
    {
      bstr = (__int64 *)wil::make_bstr(&v24);
      if ( v21 != bstr )
      {
        v3 = *bstr;
        v21[0] = *bstr;
        *bstr = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      v6 = CoCreateInstance(
             &GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe,
             0,
             1u,
             &GUID_816858a4_260d_4260_933a_2585f1abc76b,
             &v20);
    }
    catch ( ... )
    {
      v24 = wil::details::in1diag3::Return_CaughtException(retaddr, &v16, v7, v8);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v21);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      return v24;
    }
    v4 = v6;
    if ( v6 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_27;
      v18 = "CHR(CoCreateInstance(__uuidof(UpdateSession), nullptr, CLSCTX_INPROC_SERVER, __uuidof(IUpdateSession), (void"
            "**)&pUpdateSession))";
      LODWORD(ppv) = 41;
      goto LABEL_4;
    }
    v9 = v20;
    v10 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v20 + 96LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    v4 = v10(v9, &v25);
    if ( v4 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_27;
      v18 = "CHR(pUpdateSession->CreateUpdateSearcher(&pUpdateSearcher))";
      LODWORD(ppv) = 42;
      goto LABEL_4;
    }
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 168LL))(v25, 0);
    if ( v4 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_27;
      v18 = "CHR(pUpdateSearcher->put_Online(((VARIANT_BOOL)0)))";
      LODWORD(ppv) = 45;
      goto LABEL_4;
    }
    v11 = v25;
    v12 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v25 + 152LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    v4 = v12(v11, v3, &v19);
    if ( v4 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_27;
      v18 = "CHR(pUpdateSearcher->Search(SelectionFilter.get(), &pSearchResult))";
      LODWORD(ppv) = 46;
      goto LABEL_4;
    }
    v13 = v19;
    v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 72LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    v4 = v14(v13, &v26);
    if ( v4 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_27;
      v18 = "CHR(pSearchResult->get_Updates(&pUpdates))";
      LODWORD(ppv) = 54;
      goto LABEL_4;
    }
    v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 80LL))(v26, &v23);
    if ( v4 >= 0 )
    {
      *a1 = v23 > 0;
      goto LABEL_27;
    }
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      v18 = "CHR(pUpdates->get_Count(&lCountOfUpdates))";
      LODWORD(ppv) = 57;
      goto LABEL_4;
    }
  }
  else
  {
    v4 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      v18 = "CPR(pfAvailable)";
      LODWORD(ppv) = 32;
LABEL_4:
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        a2,
        v4,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcupdatehelper.cpp",
        (char)ppv,
        (__int64)v18);
    }
  }
LABEL_27:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v21);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180028110  mov     rax, rsp
0x180028113  push    rbx
0x180028114  push    rsi
0x180028115  push    rdi
0x180028116  push    r14
0x180028118  sub     rsp, 58h
0x18002811c  mov     r14, rcx
0x18002811f  mov     qword ptr [rax-40h], 0
0x180028127  mov     qword ptr [rax+18h], 0
0x18002812f  mov     qword ptr [rax-48h], 0
0x180028137  mov     qword ptr [rax+20h], 0
0x18002813f  mov     dword ptr [rax+8], 0
0x180028146  xor     ebx, ebx
0x180028148  mov     [rax-38h], rbx
0x18002814c  test    rcx, rcx
0x18002814f  jnz     short loc_18002818B
0x180028151  mov     edi, 80070057h
0x180028156  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002815d  jz      loc_1800283B8
0x180028163  lea     rax, aCprPfavailable; "CPR(pfAvailable)"
0x18002816a  mov     [rsp+78h+var_50], rax
0x18002816f  mov     dword ptr [rsp+78h+ppv], 20h ; ' '
0x180028177  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18002817e  mov     r8d, edi
0x180028181  call    McTemplateU0dsqs_EventWriteTransfer
0x180028186  jmp     loc_1800283B8
0x18002818b  lea     rcx, [rsp+78h+arg_8]
0x180028193  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180028198  lea     rcx, [rsp+78h+var_38]
0x18002819d  cmp     rcx, rax
0x1800281a0  jz      short loc_1800281B1
0x1800281a2  mov     rbx, [rax]
0x1800281a5  mov     [rsp+78h+var_38], rbx
0x1800281aa  mov     qword ptr [rax], 0
0x1800281b1  lea     rcx, [rsp+78h+arg_8]
0x1800281b9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800281be  nop
0x1800281bf  lea     rcx, [rsp+78h+var_40]
0x1800281c4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800281c9  lea     rax, [rsp+78h+var_40]
0x1800281ce  mov     [rsp+78h+ppv], rax; ppv
0x1800281d3  lea     r9, _GUID_816858a4_260d_4260_933a_2585f1abc76b; riid
0x1800281da  xor     edx, edx; pUnkOuter
0x1800281dc  lea     r8d, [rdx+1]; dwClsContext
0x1800281e0  lea     rcx, _GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe; rclsid
0x1800281e7  call    cs:__imp_CoCreateInstance
0x1800281ed  mov     edi, eax
0x1800281ef  test    eax, eax
0x1800281f1  jns     short loc_180028219
0x1800281f3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800281fa  jz      loc_1800283B8
0x180028200  lea     rax, aChrCocreateins_4; "CHR(CoCreateInstance(__uuidof(UpdateSes"...
0x180028207  mov     [rsp+78h+var_50], rax
0x18002820c  mov     dword ptr [rsp+78h+ppv], 29h ; ')'
0x180028214  jmp     loc_180028177
0x180028219  mov     rsi, [rsp+78h+var_40]
0x18002821e  mov     rax, [rsi]
0x180028221  mov     rdi, [rax+60h]
0x180028225  lea     rcx, [rsp+78h+arg_10]
0x18002822d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028232  lea     rdx, [rsp+78h+arg_10]
0x18002823a  mov     rcx, rsi
0x18002823d  mov     rax, rdi
0x180028240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028245  mov     edi, eax
0x180028247  test    eax, eax
0x180028249  jns     short loc_180028271
0x18002824b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180028252  jz      loc_1800283B8
0x180028258  lea     rax, aChrPupdatesess; "CHR(pUpdateSession->CreateUpdateSearche"...
0x18002825f  mov     [rsp+78h+var_50], rax
0x180028264  mov     dword ptr [rsp+78h+ppv], 2Ah ; '*'
0x18002826c  jmp     loc_180028177
0x180028271  mov     rcx, [rsp+78h+arg_10]
0x180028279  mov     rax, [rcx]
0x18002827c  xor     edx, edx
0x18002827e  mov     rax, [rax+0A8h]
0x180028285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002828a  mov     edi, eax
0x18002828c  test    eax, eax
0x18002828e  jns     short loc_1800282B6
0x180028290  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180028297  jz      loc_1800283B8
0x18002829d  lea     rax, aChrPupdatesear_0; "CHR(pUpdateSearcher->put_Online(((VARIA"...
0x1800282a4  mov     [rsp+78h+var_50], rax
0x1800282a9  mov     dword ptr [rsp+78h+ppv], 2Dh ; '-'
0x1800282b1  jmp     loc_180028177
0x1800282b6  mov     rsi, [rsp+78h+arg_10]
0x1800282be  mov     rax, [rsi]
0x1800282c1  mov     rdi, [rax+98h]
0x1800282c8  lea     rcx, [rsp+78h+var_48]
0x1800282cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800282d2  lea     r8, [rsp+78h+var_48]
0x1800282d7  mov     rdx, rbx
0x1800282da  mov     rcx, rsi
0x1800282dd  mov     rax, rdi
0x1800282e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282e5  mov     edi, eax
0x1800282e7  test    eax, eax
0x1800282e9  jns     short loc_180028311
0x1800282eb  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800282f2  jz      loc_1800283B8
0x1800282f8  lea     rax, aChrPupdatesear; "CHR(pUpdateSearcher->Search(SelectionFi"...
0x1800282ff  mov     [rsp+78h+var_50], rax
0x180028304  mov     dword ptr [rsp+78h+ppv], 2Eh ; '.'
0x18002830c  jmp     loc_180028177
0x180028311  mov     rdi, [rsp+78h+var_48]
0x180028316  mov     rax, [rdi]
0x180028319  mov     rbx, [rax+48h]
0x18002831d  lea     rcx, [rsp+78h+arg_18]
0x180028325  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002832a  lea     rdx, [rsp+78h+arg_18]
0x180028332  mov     rcx, rdi
0x180028335  mov     rax, rbx
0x180028338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002833d  mov     edi, eax
0x18002833f  test    eax, eax
0x180028341  jns     short loc_180028365
0x180028343  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002834a  jz      short loc_1800283B8
0x18002834c  lea     rax, aChrPsearchresu; "CHR(pSearchResult->get_Updates(&pUpdate"...
0x180028353  mov     [rsp+78h+var_50], rax
0x180028358  mov     dword ptr [rsp+78h+ppv], 36h ; '6'
0x180028360  jmp     loc_180028177
0x180028365  mov     rcx, [rsp+78h+arg_18]
0x18002836d  mov     rax, [rcx]
0x180028370  lea     rdx, [rsp+78h+arg_0]
0x180028378  mov     rax, [rax+50h]
0x18002837c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028381  mov     edi, eax
0x180028383  test    eax, eax
0x180028385  jns     short loc_1800283A9
0x180028387  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002838e  jz      short loc_1800283B8
0x180028390  lea     rax, aChrPupdatesGet; "CHR(pUpdates->get_Count(&lCountOfUpdate"...
0x180028397  mov     [rsp+78h+var_50], rax
0x18002839c  mov     dword ptr [rsp+78h+ppv], 39h ; '9'
0x1800283a4  jmp     loc_180028177
0x1800283a9  xor     eax, eax
0x1800283ab  cmp     [rsp+78h+arg_0], eax
0x1800283b2  setnle  al
0x1800283b5  mov     [r14], eax
0x1800283b8  lea     rcx, [rsp+78h+var_38]
0x1800283bd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800283c2  nop
0x1800283c3  lea     rcx, [rsp+78h+arg_18]
0x1800283cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800283d0  nop
0x1800283d1  lea     rcx, [rsp+78h+var_48]
0x1800283d6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800283db  nop
0x1800283dc  lea     rcx, [rsp+78h+arg_10]
0x1800283e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800283e9  nop
0x1800283ea  lea     rcx, [rsp+78h+var_40]
0x1800283ef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800283f4  mov     eax, edi
0x1800283f6  jmp     short loc_18002843B
0x1800283f8  lea     rcx, [rsp+78h+var_38]
0x1800283fd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180028402  nop
0x180028403  lea     rcx, [rsp+78h+arg_18]
0x18002840b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028410  nop
0x180028411  lea     rcx, [rsp+78h+var_48]
0x180028416  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002841b  nop
0x18002841c  lea     rcx, [rsp+78h+arg_10]
0x180028424  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028429  nop
0x18002842a  lea     rcx, [rsp+78h+var_40]
0x18002842f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028434  mov     eax, [rsp+78h+arg_8]
0x18002843b  add     rsp, 58h
0x18002843f  pop     r14
0x180028441  pop     rdi
0x180028442  pop     rsi
0x180028443  pop     rbx
0x180028444  retn
```
