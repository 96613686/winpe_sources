# Windows::Networking::UX::CProvisioningAgentHelper::GetInfo(HSTRING__ * *,HSTRING__ * *,HSTRING__ * *,uchar *,Windows::Foundation::Collections::IVector<Windows::Networking::UX::IWifiProfileInfo *> * *)

- ea: `0x18002a740`
- end: `0x18002aa3e`
- name: `?GetInfo@CProvisioningAgentHelper@UX@Networking@Windows@@UEAAJPEAPEAUHSTRING__@@00PEAEPEAPEAU?$IVector@PEAUIWifiProfileInfo@UX@Networking@Windows@@@Collections@Foundation@4@@Z`
- size: `766`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008e30`
- `0x1800097b4`
- `0x1800121e8`
- `0x1800141a0`
- `0x18002a40c`
- `0x18002a4dc`
- `0x18002a740`
- `0x18002abac`
- `0x18002bb4c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002a9d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002a9d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a8f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a94a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a9fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a8f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a94a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a9fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002a886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002a8d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002a914`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002a886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002a8d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002a914`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a920`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a920`

## string_xrefs

- `0x18002a797`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002a7f8`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002a897`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002a935`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002a991`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::CProvisioningAgentHelper::GetInfo(
        __int64 a1,
        HSTRING *a2,
        HSTRING *a3,
        HSTRING *a4,
        bool *a5,
        _QWORD *a6)
{
  __int64 v10; // rdx
  __int64 v11; // r8
  struct IProvisioningDocument **v12; // r8
  int ProvisioningDocumentFromXml; // eax
  HRESULT v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, PCNZWCH *); // rbx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, PCNZWCH *); // rbx
  __int64 v23; // rbx
  __int64 v24; // rdx
  HRESULT v25; // edi
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // r8
  bool v30; // cl
  int WifiProfileInfo; // eax
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // r8
  PCNZWCH sourceString; // [rsp+20h] [rbp-48h] BYREF
  HSTRING string; // [rsp+28h] [rbp-40h] BYREF
  __int64 v41; // [rsp+30h] [rbp-38h] BYREF
  HSTRING__ v42[2]; // [rsp+38h] [rbp-30h] BYREF
  _BYTE v43[8]; // [rsp+40h] [rbp-28h] BYREF
  __int128 v44; // [rsp+48h] [rbp-20h] BYREF
  PCNZWCH v45; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  PCNZWCH v47; // [rsp+B0h] [rbp+48h] BYREF

  wil::EnterCriticalSection(v43, a1 + 48);
  *(_QWORD *)&v42[0].unused = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42, v10, v11);
  ProvisioningDocumentFromXml = Windows::Networking::UX::CreateProvisioningDocumentFromXml(
                                  *(Windows::Networking::UX **)(a1 + 32),
                                  v42,
                                  v12);
  v14 = ProvisioningDocumentFromXml;
  if ( ProvisioningDocumentFromXml >= 0 )
  {
    sourceString = 0;
    v47 = 0;
    v44 = 0;
    v45 = 0;
    v17 = *(_QWORD *)&v42[0].unused;
    v18 = *(__int64 (__fastcall **)(__int64, PCNZWCH *))(**(_QWORD **)&v42[0].unused + 32LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &sourceString,
      0);
    v19 = v18(v17, &sourceString);
    v14 = v19;
    if ( v19 >= 0 )
    {
      v21 = *(_QWORD *)&v42[0].unused;
      v22 = *(__int64 (__fastcall **)(__int64, PCNZWCH *))(**(_QWORD **)&v42[0].unused + 40LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v47,
        0);
      v19 = v22(v21, &v47);
      v14 = v19;
      if ( v19 >= 0 )
      {
        v19 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)&v42[0].unused + 48LL))(
                *(_QWORD *)&v42[0].unused,
                &v44);
        v14 = v19;
        if ( v19 >= 0 )
        {
          v23 = -1;
          v24 = -1;
          do
            ++v24;
          while ( sourceString[v24] );
          v25 = WindowsCreateString(sourceString, v24, a2);
          if ( v25 >= 0 )
          {
            v27 = -1;
            do
              ++v27;
            while ( v47[v27] );
            v25 = WindowsCreateString(v47, v27, a3);
            if ( v25 >= 0 )
            {
              string = 0;
              if ( !v45 )
                goto LABEL_26;
              WindowsDeleteString(0);
              string = 0;
              do
                ++v23;
              while ( v45[v23] );
              v14 = WindowsCreateString(v45, v23, &string);
              CoTaskMemFree((LPVOID)v45);
              v45 = 0;
              if ( v14 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x84,
                  (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
                  (const char *)(unsigned int)v14,
                  (int)sourceString);
              }
              else
              {
LABEL_26:
                v30 = (_DWORD)v44 != 0;
                *a5 = (_DWORD)v44 != 0;
                *(_BYTE *)(a1 + 40) = v30;
                v41 = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v41,
                  v28,
                  v29);
                WifiProfileInfo = Windows::Networking::UX::CProvisioningAgentHelper::GetWifiProfileInfo(
                                    a1,
                                    *(HSTRING *)(a1 + 32),
                                    (__int64)&v41);
                v14 = WifiProfileInfo;
                if ( WifiProfileInfo >= 0 )
                {
                  v35 = v41;
                  if ( v41 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 8LL))(v41);
                    v35 = v41;
                  }
                  *a6 = v35;
                  WifiProfileInfo = WindowsDuplicateString(string, a4);
                  v14 = WifiProfileInfo;
                  if ( WifiProfileInfo >= 0 )
                  {
                    *(_BYTE *)(a1 + 41) = 1;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                      &v41,
                      v36,
                      v37);
                    WindowsDeleteString(string);
                    string = 0;
                    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v47);
                    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
                    v14 = 0;
                    goto LABEL_34;
                  }
                  v32 = 144;
                }
                else
                {
                  v32 = 142;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v32,
                  (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
                  (const char *)(unsigned int)WifiProfileInfo,
                  (int)sourceString);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v41,
                  v33,
                  v34);
              }
              WindowsDeleteString(string);
              string = 0;
              goto LABEL_6;
            }
            v26 = 123;
          }
          else
          {
            v26 = 122;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v26,
            (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
            (const char *)(unsigned int)v25,
            (int)sourceString);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v47);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
          v14 = v25;
          goto LABEL_34;
        }
        v20 = 120;
      }
      else
      {
        v20 = 119;
      }
    }
    else
    {
      v20 = 118;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
      (const char *)(unsigned int)v19,
      (int)sourceString);
LABEL_6:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v47);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
    goto LABEL_34;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x70,
    (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
    (const char *)(unsigned int)ProvisioningDocumentFromXml,
    (int)sourceString);
LABEL_34:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42, v15, v16);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v43);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002a740  push    rbp
0x18002a742  push    rbx
0x18002a743  push    rsi
0x18002a744  push    rdi
0x18002a745  push    r12
0x18002a747  push    r13
0x18002a749  push    r14
0x18002a74b  push    r15
0x18002a74d  mov     rbp, rsp
0x18002a750  sub     rsp, 68h
0x18002a754  mov     r12, r9
0x18002a757  mov     r15, r8
0x18002a75a  mov     r14, rdx
0x18002a75d  mov     rsi, rcx
0x18002a760  lea     rdx, [rcx+30h]
0x18002a764  lea     rcx, [rbp+var_28]
0x18002a768  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18002a76d  xor     r13d, r13d
0x18002a770  mov     qword ptr [rbp+var_30.unused], r13
0x18002a774  lea     rcx, [rbp+var_30]
0x18002a778  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a77d  lea     rdx, [rbp+var_30]; HSTRING
0x18002a781  mov     rcx, [rsi+20h]; this
0x18002a785  call    ?CreateProvisioningDocumentFromXml@UX@Networking@Windows@@YAJPEAUHSTRING__@@PEAPEAUIProvisioningDocument@@@Z; Windows::Networking::UX::CreateProvisioningDocumentFromXml(HSTRING__ *,IProvisioningDocument * *)
0x18002a78a  mov     ebx, eax
0x18002a78c  test    eax, eax
0x18002a78e  jns     short loc_18002A7AC
0x18002a790  mov     rcx, [rbp+40h]; this
0x18002a794  mov     r9d, eax; char *
0x18002a797  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002a79e  lea     edx, [r13+70h]; void *
0x18002a7a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a7a7  jmp     loc_18002AA19
0x18002a7ac  mov     [rbp+sourceString], r13
0x18002a7b0  mov     [rbp+arg_0], r13
0x18002a7b4  xorps   xmm0, xmm0
0x18002a7b7  xor     eax, eax
0x18002a7b9  movups  [rbp+var_20], xmm0
0x18002a7bd  mov     [rbp+var_10], rax
0x18002a7c1  mov     rdi, qword ptr [rbp+var_30.unused]
0x18002a7c5  mov     rax, [rdi]
0x18002a7c8  mov     rbx, [rax+20h]
0x18002a7cc  xor     edx, edx
0x18002a7ce  lea     rcx, [rbp+sourceString]
0x18002a7d2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002a7d7  lea     rdx, [rbp+sourceString]
0x18002a7db  mov     rcx, rdi
0x18002a7de  mov     rax, rbx
0x18002a7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7e6  mov     ebx, eax
0x18002a7e8  test    eax, eax
0x18002a7ea  jns     short loc_18002A81B
0x18002a7ec  mov     edx, 76h ; 'v'; void *
0x18002a7f1  mov     rcx, [rbp+40h]; this
0x18002a7f5  mov     r9d, eax; char *
0x18002a7f8  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002a7ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a804  lea     rcx, [rbp+arg_0]
0x18002a808  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002a80d  lea     rcx, [rbp+sourceString]
0x18002a811  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002a816  jmp     loc_18002AA19
0x18002a81b  mov     rdi, qword ptr [rbp+var_30.unused]
0x18002a81f  mov     rax, [rdi]
0x18002a822  mov     rbx, [rax+28h]
0x18002a826  xor     edx, edx
0x18002a828  lea     rcx, [rbp+arg_0]
0x18002a82c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002a831  lea     rdx, [rbp+arg_0]
0x18002a835  mov     rcx, rdi
0x18002a838  mov     rax, rbx
0x18002a83b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a840  mov     ebx, eax
0x18002a842  test    eax, eax
0x18002a844  jns     short loc_18002A84D
0x18002a846  mov     edx, 77h ; 'w'
0x18002a84b  jmp     short loc_18002A7F1
0x18002a84d  mov     rcx, qword ptr [rbp+var_30.unused]
0x18002a851  mov     rax, [rcx]
0x18002a854  lea     rdx, [rbp+var_20]
0x18002a858  mov     rax, [rax+30h]
0x18002a85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a861  mov     ebx, eax
0x18002a863  test    eax, eax
0x18002a865  jns     short loc_18002A86E
0x18002a867  mov     edx, 78h ; 'x'
0x18002a86c  jmp     short loc_18002A7F1
0x18002a86e  mov     rcx, [rbp+sourceString]; sourceString
0x18002a872  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002a876  mov     rdx, rbx
0x18002a879  inc     rdx; length
0x18002a87c  cmp     [rcx+rdx*2], r13w
0x18002a881  jnz     short loc_18002A879
0x18002a883  mov     r8, r14; string
0x18002a886  call    cs:__imp_WindowsCreateString
0x18002a88c  mov     edi, eax
0x18002a88e  test    eax, eax
0x18002a890  jns     short loc_18002A8C3
0x18002a892  mov     edx, 7Ah ; 'z'; void *
0x18002a897  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002a89e  mov     r9d, edi; char *
0x18002a8a1  mov     rcx, [rbp+40h]; this
0x18002a8a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a8aa  lea     rcx, [rbp+arg_0]
0x18002a8ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002a8b3  lea     rcx, [rbp+sourceString]
0x18002a8b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002a8bc  mov     ebx, edi
0x18002a8be  jmp     loc_18002AA19
0x18002a8c3  mov     rcx, [rbp+arg_0]; sourceString
0x18002a8c7  mov     rdx, rbx
0x18002a8ca  inc     rdx; length
0x18002a8cd  cmp     [rcx+rdx*2], r13w
0x18002a8d2  jnz     short loc_18002A8CA
0x18002a8d4  mov     r8, r15; string
0x18002a8d7  call    cs:__imp_WindowsCreateString
0x18002a8dd  mov     edi, eax
0x18002a8df  test    eax, eax
0x18002a8e1  jns     short loc_18002A8EA
0x18002a8e3  mov     edx, 7Bh ; '{'
0x18002a8e8  jmp     short loc_18002A897
0x18002a8ea  mov     [rbp+string], r13
0x18002a8ee  cmp     [rbp+var_10], r13
0x18002a8f2  jz      short loc_18002A959
0x18002a8f4  xor     ecx, ecx; string
0x18002a8f6  call    cs:__imp_WindowsDeleteString
0x18002a8fc  mov     [rbp+string], r13
0x18002a900  mov     rcx, [rbp+var_10]; sourceString
0x18002a904  inc     rbx
0x18002a907  cmp     [rcx+rbx*2], r13w
0x18002a90c  jnz     short loc_18002A904
0x18002a90e  lea     r8, [rbp+string]; string
0x18002a912  mov     edx, ebx; length
0x18002a914  call    cs:__imp_WindowsCreateString
0x18002a91a  mov     ebx, eax
0x18002a91c  mov     rcx, [rbp+var_10]; pv
0x18002a920  call    cs:__imp_CoTaskMemFree
0x18002a926  mov     [rbp+var_10], r13
0x18002a92a  test    ebx, ebx
0x18002a92c  jns     short loc_18002A959
0x18002a92e  mov     rcx, [rbp+40h]; this
0x18002a932  mov     r9d, ebx; char *
0x18002a935  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002a93c  mov     edx, 84h; void *
0x18002a941  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a946  mov     rcx, [rbp+string]; string
0x18002a94a  call    cs:__imp_WindowsDeleteString
0x18002a950  mov     [rbp+string], r13
0x18002a954  jmp     loc_18002A804
0x18002a959  cmp     dword ptr [rbp+var_20], r13d
0x18002a95d  setnz   cl
0x18002a960  mov     rax, [rbp+arg_20]
0x18002a964  mov     [rax], cl
0x18002a966  mov     [rsi+28h], cl
0x18002a969  mov     [rbp+var_38], r13
0x18002a96d  lea     rcx, [rbp+var_38]
0x18002a971  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a976  lea     r8, [rbp+var_38]
0x18002a97a  mov     rdx, [rsi+20h]
0x18002a97e  mov     rcx, rsi
0x18002a981  call    ?GetWifiProfileInfo@CProvisioningAgentHelper@UX@Networking@Windows@@AEAAJPEAUHSTRING__@@PEAPEAU?$IVector@PEAUIWifiProfileInfo@UX@Networking@Windows@@@Collections@Foundation@4@@Z; Windows::Networking::UX::CProvisioningAgentHelper::GetWifiProfileInfo(HSTRING__ *,Windows::Foundation::Collections::IVector<Windows::Networking::UX::IWifiProfileInfo *> * *)
0x18002a986  mov     ebx, eax
0x18002a988  test    eax, eax
0x18002a98a  jns     short loc_18002A9AF
0x18002a98c  mov     edx, 8Eh; void *
0x18002a991  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002a998  mov     r9d, eax; char *
0x18002a99b  mov     rcx, [rbp+40h]; this
0x18002a99f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a9a4  lea     rcx, [rbp+var_38]
0x18002a9a8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a9ad  jmp     short loc_18002A946
0x18002a9af  mov     rcx, [rbp+var_38]
0x18002a9b3  test    rcx, rcx
0x18002a9b6  jz      short loc_18002A9C8
0x18002a9b8  mov     rax, [rcx]
0x18002a9bb  mov     rax, [rax+8]
0x18002a9bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9c4  mov     rcx, [rbp+var_38]
0x18002a9c8  mov     rax, [rbp+arg_28]
0x18002a9cc  mov     [rax], rcx
0x18002a9cf  mov     rdx, r12; newString
0x18002a9d2  mov     rcx, [rbp+string]; string
0x18002a9d6  call    cs:__imp_WindowsDuplicateString
0x18002a9dc  mov     ebx, eax
0x18002a9de  test    eax, eax
0x18002a9e0  jns     short loc_18002A9E9
0x18002a9e2  mov     edx, 90h
0x18002a9e7  jmp     short loc_18002A991
0x18002a9e9  mov     byte ptr [rsi+29h], 1
0x18002a9ed  lea     rcx, [rbp+var_38]
0x18002a9f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a9f6  mov     rcx, [rbp+string]; string
0x18002a9fa  call    cs:__imp_WindowsDeleteString
0x18002aa00  mov     [rbp+string], r13
0x18002aa04  lea     rcx, [rbp+arg_0]
0x18002aa08  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002aa0d  lea     rcx, [rbp+sourceString]
0x18002aa11  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002aa16  mov     ebx, r13d
0x18002aa19  lea     rcx, [rbp+var_30]
0x18002aa1d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002aa22  lea     rcx, [rbp+var_28]
0x18002aa26  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002aa2b  mov     eax, ebx
0x18002aa2d  add     rsp, 68h
0x18002aa31  pop     r15
0x18002aa33  pop     r14
0x18002aa35  pop     r13
0x18002aa37  pop     r12
0x18002aa39  pop     rdi
0x18002aa3a  pop     rsi
0x18002aa3b  pop     rbx
0x18002aa3c  pop     rbp
0x18002aa3d  retn
```
