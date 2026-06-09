# SystemSettings::WorkAccess::CEnrollmentHelper::SyncAndWait(void)

- ea: `0x18004cc34`
- end: `0x18004cef0`
- name: `?SyncAndWait@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJXZ`
- size: `700`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002454c`
- `0x1800317bc`

## callees

- `0x180002a60`
- `0x18000526c`
- `0x1800058fc`
- `0x1800069c4`
- `0x1800076ac`
- `0x1800096ec`
- `0x1800446c0`
- `0x1800447c8`
- `0x180044f08`
- `0x18004566c`
- `0x18004cc34`
- `0x18004d150`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004cd3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004cd3d`
- `dmEnrollEngine!GetEnrollmentLinkedEnrollmentId` at `0x18004cdc5`
- `dmEnrollEngine!GetEnrollmentLinkedEnrollmentId` at `0x18004cdc5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004cd50`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004cd50`

## string_xrefs

- `0x18004cc8b`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004cce9`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004cd69`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004ce03`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004ce6e`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentHelper::SyncAndWait(__int64 a1, const unsigned __int16 *a2)
{
  _QWORD *v2; // rax
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdi
  __int64 v6; // rsi
  __int64 (__fastcall *v7)(__int64, __int64, __int64, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rdx
  const OLECHAR *StringRawBuffer; // rax
  HRESULT v11; // eax
  wil::details *v12; // rbx
  void *v13; // rdx
  const unsigned __int16 *v14; // rdx
  _QWORD *v15; // rax
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING, __int64, _QWORD *); // rbx
  int v19; // eax
  __int64 v20; // rdx
  int v22; // [rsp+20h] [rbp-79h]
  __int64 v23; // [rsp+30h] [rbp-69h] BYREF
  wil::details *v24; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-59h] BYREF
  GUID v26; // [rsp+50h] [rbp-49h] BYREF
  __int64 v27; // [rsp+60h] [rbp-39h]
  __int64 v28; // [rsp+68h] [rbp-31h] BYREF
  GUID pclsid; // [rsp+70h] [rbp-29h] BYREF
  HSTRING string[4]; // [rsp+80h] [rbp-19h] BYREF
  HSTRING v31; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v27 = 0x800000001LL;
  v28 = 0;
  v2 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[53])a2);
  v3 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Provision::ISessionManager>>(
         *v2,
         &v28);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v23 = 0;
    v5 = *(_QWORD *)(SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton + 8);
    v6 = v28;
    v7 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v28 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    v8 = v7(v6, v5, v27, &v23);
    v4 = v8;
    if ( v8 < 0 )
    {
      v9 = 1731;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v8,
        v22);
LABEL_6:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      goto LABEL_25;
    }
    v8 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(v23);
    v4 = v8;
    if ( v8 < 0 )
    {
      v9 = 1734;
      goto LABEL_5;
    }
    v24 = 0;
    pclsid = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(
                        *(HSTRING *)(SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton + 16),
                        0);
    v11 = CLSIDFromString(StringRawBuffer, &pclsid);
    v4 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6CD,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v11,
        v22);
LABEL_11:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
      goto LABEL_6;
    }
    v12 = v24;
    if ( v24 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v26);
      wil::details::FreeProcessHeap(v12, v13);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v26);
    }
    v24 = 0;
    v26 = pclsid;
    if ( (int)GetEnrollmentLinkedEnrollmentId(&v26, &v24) >= 0 )
    {
      *(_QWORD *)&v26.Data1 = 0;
      v15 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v31, (const unsigned __int16 (*)[53])v14);
      v16 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Provision::ISessionManager>>(
              *v15,
              &v26);
      v4 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6D1,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
          (const char *)(unsigned int)v16,
          v22);
LABEL_17:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
        goto LABEL_11;
      }
      v25[0] = 0;
      Windows::Internal::StringReference::_ConstructorHelper(
        (Windows::Internal::StringReference *)string,
        (const unsigned __int16 *)v24);
      v17 = *(_QWORD *)&v26.Data1;
      v18 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _QWORD *))(**(_QWORD **)&v26.Data1 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
      v19 = v18(v17, string[0], v27, v25);
      v4 = v19;
      if ( v19 < 0 )
      {
        v20 = 1749;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
          (const char *)(unsigned int)v19,
          v22);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
        goto LABEL_17;
      }
      v19 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(v25[0]);
      v4 = v19;
      if ( v19 < 0 )
      {
        v20 = 1752;
        goto LABEL_20;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    v4 = 0;
    goto LABEL_25;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6BF,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
    (const char *)(unsigned int)v3,
    v22);
LABEL_25:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  return v4;
}

```

## disassembly

```asm
0x18004cc34  push    rbp
0x18004cc36  push    rbx
0x18004cc37  push    rsi
0x18004cc38  push    rdi
0x18004cc39  lea     rbp, [rsp-3Fh]
0x18004cc3e  sub     rsp, 0D8h
0x18004cc45  mov     rax, cs:__security_cookie
0x18004cc4c  xor     rax, rsp
0x18004cc4f  mov     [rbp+57h+var_30], rax
0x18004cc53  mov     dword ptr [rbp+57h+var_90+4], 8
0x18004cc5a  mov     dword ptr [rbp+57h+var_90], 1
0x18004cc61  mov     [rbp+57h+var_88], 0
0x18004cc69  lea     rcx, [rbp+57h+string]; string
0x18004cc6d  call    ??$?0$0DF@@StringReference@Internal@Windows@@QEAA@AEAY0DF@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[53])
0x18004cc72  lea     rdx, [rbp+57h+var_88]
0x18004cc76  mov     rcx, [rax]
0x18004cc79  call    ??$ActivateInstance@V?$ComPtr@UISessionManager@Provision@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UISessionManager@Provision@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Provision::ISessionManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Provision::ISessionManager>>)
0x18004cc7e  mov     ebx, eax
0x18004cc80  test    eax, eax
0x18004cc82  jns     short loc_18004CCA1
0x18004cc84  mov     rcx, [rbp+5Fh]; this
0x18004cc88  mov     r9d, eax; char *
0x18004cc8b  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004cc92  mov     edx, 6BFh; void *
0x18004cc97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cc9c  jmp     loc_18004CECC
0x18004cca1  mov     [rbp+57h+var_C0], 0
0x18004cca9  mov     rax, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x18004ccb0  mov     rdi, [rax+8]
0x18004ccb4  mov     rsi, [rbp+57h+var_88]
0x18004ccb8  mov     rax, [rsi]
0x18004ccbb  mov     rbx, [rax+30h]
0x18004ccbf  lea     rcx, [rbp+57h+var_C0]
0x18004ccc3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ccc8  lea     r9, [rbp+57h+var_C0]
0x18004cccc  mov     r8, [rbp+57h+var_90]
0x18004ccd0  mov     rdx, rdi
0x18004ccd3  mov     rcx, rsi
0x18004ccd6  mov     rax, rbx
0x18004ccd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ccde  mov     ebx, eax
0x18004cce0  test    eax, eax
0x18004cce2  jns     short loc_18004CD0B
0x18004cce4  mov     edx, 6C3h; void *
0x18004cce9  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004ccf0  mov     r9d, eax; char *
0x18004ccf3  mov     rcx, [rbp+5Fh]; this
0x18004ccf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ccfc  nop
0x18004ccfd  lea     rcx, [rbp+57h+var_C0]
0x18004cd01  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cd06  jmp     loc_18004CECC
0x18004cd0b  mov     rcx, [rbp+57h+var_C0]
0x18004cd0f  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> *,tagCOWAIT_FLAGS,void *)
0x18004cd14  mov     ebx, eax
0x18004cd16  test    eax, eax
0x18004cd18  jns     short loc_18004CD21
0x18004cd1a  mov     edx, 6C6h
0x18004cd1f  jmp     short loc_18004CCE9
0x18004cd21  mov     [rbp+57h+var_B8], 0
0x18004cd29  xorps   xmm0, xmm0
0x18004cd2c  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18004cd30  mov     rcx, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x18004cd37  xor     edx, edx; length
0x18004cd39  mov     rcx, [rcx+10h]; string
0x18004cd3d  call    cs:__imp_WindowsGetStringRawBuffer
0x18004cd44  nop     dword ptr [rax+rax+00h]
0x18004cd49  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18004cd4d  mov     rcx, rax; lpsz
0x18004cd50  call    cs:__imp_CLSIDFromString
0x18004cd57  nop     dword ptr [rax+rax+00h]
0x18004cd5c  mov     ebx, eax
0x18004cd5e  test    eax, eax
0x18004cd60  jns     short loc_18004CD89
0x18004cd62  mov     rcx, [rbp+5Fh]; this
0x18004cd66  mov     r9d, eax; char *
0x18004cd69  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004cd70  mov     edx, 6CDh; void *
0x18004cd75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cd7a  nop
0x18004cd7b  lea     rcx, [rbp+57h+var_B8]
0x18004cd7f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004cd84  jmp     loc_18004CCFD
0x18004cd89  mov     rbx, [rbp+57h+var_B8]
0x18004cd8d  test    rbx, rbx
0x18004cd90  jz      short loc_18004CDAC
0x18004cd92  lea     rcx, [rbp+57h+var_A0]; this
0x18004cd96  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004cd9b  mov     rcx, rbx; this
0x18004cd9e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18004cda3  lea     rcx, [rbp+57h+var_A0]; this
0x18004cda7  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004cdac  mov     [rbp+57h+var_B8], 0
0x18004cdb4  movaps  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x18004cdb8  movdqa  [rbp+57h+var_A0], xmm0
0x18004cdbd  lea     rdx, [rbp+57h+var_B8]
0x18004cdc1  lea     rcx, [rbp+57h+var_A0]
0x18004cdc5  call    cs:__imp_GetEnrollmentLinkedEnrollmentId
0x18004cdcc  nop     dword ptr [rax+rax+00h]
0x18004cdd1  test    eax, eax
0x18004cdd3  js      loc_18004CEB7
0x18004cdd9  mov     qword ptr [rbp+57h+var_A0], 0
0x18004cde1  lea     rcx, [rbp+57h+var_50]; string
0x18004cde5  call    ??$?0$0DF@@StringReference@Internal@Windows@@QEAA@AEAY0DF@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[53])
0x18004cdea  lea     rdx, [rbp+57h+var_A0]
0x18004cdee  mov     rcx, [rax]
0x18004cdf1  call    ??$ActivateInstance@V?$ComPtr@UISessionManager@Provision@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UISessionManager@Provision@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Provision::ISessionManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Provision::ISessionManager>>)
0x18004cdf6  mov     ebx, eax
0x18004cdf8  test    eax, eax
0x18004cdfa  jns     short loc_18004CE23
0x18004cdfc  mov     rcx, [rbp+5Fh]; this
0x18004ce00  mov     r9d, eax; char *
0x18004ce03  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004ce0a  mov     edx, 6D1h; void *
0x18004ce0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ce14  nop
0x18004ce15  lea     rcx, [rbp+57h+var_A0]
0x18004ce19  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ce1e  jmp     loc_18004CD7B
0x18004ce23  mov     [rbp+57h+var_B0], 0
0x18004ce2b  mov     rdx, [rbp+57h+var_B8]; unsigned __int16 *
0x18004ce2f  lea     rcx, [rbp+57h+string]; this
0x18004ce33  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18004ce38  mov     rdi, qword ptr [rbp+57h+var_A0]
0x18004ce3c  mov     rax, [rdi]
0x18004ce3f  mov     rbx, [rax+30h]
0x18004ce43  lea     rcx, [rbp+57h+var_B0]
0x18004ce47  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ce4c  lea     r9, [rbp+57h+var_B0]
0x18004ce50  mov     r8, [rbp+57h+var_90]
0x18004ce54  mov     rdx, [rbp+57h+string]
0x18004ce58  mov     rcx, rdi
0x18004ce5b  mov     rax, rbx
0x18004ce5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce63  mov     ebx, eax
0x18004ce65  test    eax, eax
0x18004ce67  jns     short loc_18004CE8D
0x18004ce69  mov     edx, 6D5h; void *
0x18004ce6e  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004ce75  mov     r9d, eax; char *
0x18004ce78  mov     rcx, [rbp+5Fh]; this
0x18004ce7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ce81  nop
0x18004ce82  lea     rcx, [rbp+57h+var_B0]
0x18004ce86  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ce8b  jmp     short loc_18004CE15
0x18004ce8d  mov     rcx, [rbp+57h+var_B0]
0x18004ce91  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> *,tagCOWAIT_FLAGS,void *)
0x18004ce96  mov     ebx, eax
0x18004ce98  test    eax, eax
0x18004ce9a  jns     short loc_18004CEA3
0x18004ce9c  mov     edx, 6D8h
0x18004cea1  jmp     short loc_18004CE6E
0x18004cea3  lea     rcx, [rbp+57h+var_B0]
0x18004cea7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ceac  nop
0x18004cead  lea     rcx, [rbp+57h+var_A0]
0x18004ceb1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ceb6  nop
0x18004ceb7  lea     rcx, [rbp+57h+var_B8]
0x18004cebb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004cec0  nop
0x18004cec1  lea     rcx, [rbp+57h+var_C0]
0x18004cec5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ceca  xor     ebx, ebx
0x18004cecc  lea     rcx, [rbp+57h+var_88]
0x18004ced0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ced5  mov     eax, ebx
0x18004ced7  mov     rcx, [rbp+57h+var_30]
0x18004cedb  xor     rcx, rsp; StackCookie
0x18004cede  call    __security_check_cookie
0x18004cee3  add     rsp, 0D8h
0x18004ceea  pop     rdi
0x18004ceeb  pop     rsi
0x18004ceec  pop     rbx
0x18004ceed  pop     rbp
0x18004ceee  retn
```
