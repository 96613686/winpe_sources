# Windows::Networking::UX::CProvisioningAgentHelper::Provision(HSTRING__ * *)

- ea: `0x18002b640`
- end: `0x18002b7df`
- name: `?Provision@CProvisioningAgentHelper@UX@Networking@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `415`
- prototype: `int(Windows::Networking::UX::CProvisioningAgentHelper *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008e30`
- `0x1800097b4`
- `0x1800121e8`
- `0x1800141a0`
- `0x18002a40c`
- `0x18002a4dc`
- `0x18002b640`
- `0x18002bb4c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002b7a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002b7a1`

## string_xrefs

- `0x18002b68a`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002b6ca`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002b76a`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::CProvisioningAgentHelper::Provision(
        Windows::Networking::UX::CProvisioningAgentHelper *this,
        HSTRING *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // ebx
  __int64 v7; // rdx
  struct IProvisioningDocument **v8; // r8
  int ProvisioningDocumentFromXml; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, PCNZWCH *); // rbx
  HRESULT String; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  int v22[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  int v24; // [rsp+60h] [rbp+30h] BYREF
  __int64 v25; // [rsp+70h] [rbp+40h] BYREF
  PCNZWCH sourceString; // [rsp+78h] [rbp+48h] BYREF

  wil::EnterCriticalSection(v22, (char *)this + 48);
  if ( *((_BYTE *)this + 41) )
  {
    if ( !*((_BYTE *)this + 40) )
    {
      v6 = -2147024891;
      v7 = 158;
      goto LABEL_5;
    }
    v25 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25, v4, v5);
    ProvisioningDocumentFromXml = Windows::Networking::UX::CreateProvisioningDocumentFromXml(
                                    *((Windows::Networking::UX **)this + 4),
                                    (HSTRING)&v25,
                                    v8);
    v6 = ProvisioningDocumentFromXml;
    if ( ProvisioningDocumentFromXml >= 0 )
    {
      if ( !v25 )
      {
        v6 = -2147467261;
        v10 = 164;
        v11 = 2147500035LL;
        goto LABEL_9;
      }
      v24 = 0;
      ProvisioningDocumentFromXml = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 24LL))(v25, &v24);
      v6 = ProvisioningDocumentFromXml;
      if ( ProvisioningDocumentFromXml >= 0 )
      {
        if ( !v24 )
        {
          v14 = v25;
          sourceString = 0;
          v15 = *(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v25 + 56LL);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &sourceString,
            0);
          String = v15(v14, &sourceString);
          v6 = String;
          if ( String >= 0 )
          {
            if ( !sourceString )
              goto LABEL_25;
            v18 = -1;
            do
              ++v18;
            while ( sourceString[v18] );
            String = WindowsCreateString(sourceString, v18, a2);
            v6 = String;
            if ( String >= 0 )
            {
LABEL_25:
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                &v25,
                v19,
                v20);
              v6 = 0;
              goto LABEL_26;
            }
            v17 = 174;
          }
          else
          {
            v17 = 171;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
            (const char *)(unsigned int)String,
            v22[0]);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
          goto LABEL_10;
        }
        v6 = -2147467259;
        v10 = 168;
        v11 = 2147500037LL;
LABEL_9:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
          (const char *)v11,
          v22[0]);
LABEL_10:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25, v12, v13);
        goto LABEL_26;
      }
      v10 = 167;
    }
    else
    {
      v10 = 161;
    }
    v11 = (unsigned int)ProvisioningDocumentFromXml;
    goto LABEL_9;
  }
  v6 = -2147483634;
  v7 = 155;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
    (const char *)v6,
    v22[0]);
LABEL_26:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v22);
  return v6;
}

```

## disassembly

```asm
0x18002b640  push    rbp
0x18002b642  push    rbx
0x18002b643  push    rsi
0x18002b644  push    rdi
0x18002b645  push    r14
0x18002b647  mov     rbp, rsp
0x18002b64a  sub     rsp, 30h
0x18002b64e  mov     rsi, rdx
0x18002b651  mov     rbx, rcx
0x18002b654  lea     rdx, [rcx+30h]
0x18002b658  lea     rcx, [rbp+var_10]
0x18002b65c  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18002b661  xor     r14d, r14d
0x18002b664  cmp     [rbx+29h], r14b
0x18002b668  jnz     short loc_18002B676
0x18002b66a  mov     ebx, 8000000Eh
0x18002b66f  mov     edx, 9Bh
0x18002b674  jmp     short loc_18002B686
0x18002b676  cmp     [rbx+28h], r14b
0x18002b67a  jnz     short loc_18002B69E
0x18002b67c  mov     ebx, 80070005h
0x18002b681  mov     edx, 9Eh; void *
0x18002b686  mov     rcx, [rbp+28h]; this
0x18002b68a  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002b691  mov     r9d, ebx; char *
0x18002b694  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b699  jmp     loc_18002B7C9
0x18002b69e  lea     rcx, [rbp+arg_10]
0x18002b6a2  mov     [rbp+arg_10], r14
0x18002b6a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b6ab  mov     rcx, [rbx+20h]; this
0x18002b6af  lea     rdx, [rbp+arg_10]; HSTRING
0x18002b6b3  call    ?CreateProvisioningDocumentFromXml@UX@Networking@Windows@@YAJPEAUHSTRING__@@PEAPEAUIProvisioningDocument@@@Z; Windows::Networking::UX::CreateProvisioningDocumentFromXml(HSTRING__ *,IProvisioningDocument * *)
0x18002b6b8  mov     ebx, eax
0x18002b6ba  test    eax, eax
0x18002b6bc  jns     short loc_18002B6E4
0x18002b6be  mov     edx, 0A1h; void *
0x18002b6c3  mov     r9d, eax; char *
0x18002b6c6  mov     rcx, [rbp+28h]; this
0x18002b6ca  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002b6d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b6d6  lea     rcx, [rbp+arg_10]
0x18002b6da  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b6df  jmp     loc_18002B7C9
0x18002b6e4  mov     rcx, [rbp+arg_10]
0x18002b6e8  test    rcx, rcx
0x18002b6eb  jnz     short loc_18002B6FC
0x18002b6ed  mov     ebx, 80004003h
0x18002b6f2  mov     edx, 0A4h
0x18002b6f7  mov     r9d, ebx
0x18002b6fa  jmp     short loc_18002B6C6
0x18002b6fc  mov     [rbp+arg_0], r14d
0x18002b700  lea     rdx, [rbp+arg_0]
0x18002b704  mov     rax, [rcx]
0x18002b707  mov     rax, [rax+18h]
0x18002b70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b710  mov     ebx, eax
0x18002b712  test    eax, eax
0x18002b714  jns     short loc_18002B71D
0x18002b716  mov     edx, 0A7h
0x18002b71b  jmp     short loc_18002B6C3
0x18002b71d  cmp     [rbp+arg_0], r14d
0x18002b721  jz      short loc_18002B732
0x18002b723  mov     ebx, 80004005h
0x18002b728  mov     edx, 0A8h
0x18002b72d  mov     r9d, ebx
0x18002b730  jmp     short loc_18002B6C6
0x18002b732  mov     rdi, [rbp+arg_10]
0x18002b736  lea     rcx, [rbp+sourceString]
0x18002b73a  mov     [rbp+sourceString], r14
0x18002b73e  xor     edx, edx
0x18002b740  mov     rax, [rdi]
0x18002b743  mov     rbx, [rax+38h]
0x18002b747  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002b74c  lea     rdx, [rbp+sourceString]
0x18002b750  mov     rcx, rdi
0x18002b753  mov     rax, rbx
0x18002b756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b75b  mov     ebx, eax
0x18002b75d  test    eax, eax
0x18002b75f  jns     short loc_18002B787
0x18002b761  mov     edx, 0ABh; void *
0x18002b766  mov     rcx, [rbp+28h]; this
0x18002b76a  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002b771  mov     r9d, eax; char *
0x18002b774  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b779  lea     rcx, [rbp+sourceString]
0x18002b77d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b782  jmp     loc_18002B6D6
0x18002b787  mov     rcx, [rbp+sourceString]; sourceString
0x18002b78b  test    rcx, rcx
0x18002b78e  jz      short loc_18002B7B4
0x18002b790  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002b794  inc     rdx; length
0x18002b797  cmp     [rcx+rdx*2], r14w
0x18002b79c  jnz     short loc_18002B794
0x18002b79e  mov     r8, rsi; string
0x18002b7a1  call    cs:__imp_WindowsCreateString
0x18002b7a7  mov     ebx, eax
0x18002b7a9  test    eax, eax
0x18002b7ab  jns     short loc_18002B7B4
0x18002b7ad  mov     edx, 0AEh
0x18002b7b2  jmp     short loc_18002B766
0x18002b7b4  lea     rcx, [rbp+sourceString]
0x18002b7b8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b7bd  lea     rcx, [rbp+arg_10]
0x18002b7c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b7c6  mov     ebx, r14d
0x18002b7c9  lea     rcx, [rbp+var_10]
0x18002b7cd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002b7d2  mov     eax, ebx
0x18002b7d4  add     rsp, 30h
0x18002b7d8  pop     r14
0x18002b7da  pop     rdi
0x18002b7db  pop     rsi
0x18002b7dc  pop     rbx
0x18002b7dd  pop     rbp
0x18002b7de  retn
```
