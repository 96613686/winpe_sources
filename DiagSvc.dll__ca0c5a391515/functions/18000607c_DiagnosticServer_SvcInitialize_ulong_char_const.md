# DiagnosticServer::SvcInitialize(ulong,char * * const)

- ea: `0x18000607c`
- end: `0x18000625e`
- name: `?SvcInitialize@DiagnosticServer@@IEAAJKQEAPEAD@Z`
- size: `482`
- prototype: `__int64 __fastcall(DiagnosticServer *__hidden this, unsigned int, char **const)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005a24`

## callees

- `0x180001178`
- `0x180001720`
- `0x18000517c`
- `0x1800056d8`
- `0x18000607c`
- `0x180006634`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800060cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800060cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800060d7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800060d7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800060ae`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800060ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800060b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800060b8`

## string_xrefs

- `0x1800060e3`: `onecoreuap\base\diagnosis\pdi\diagsvc\dll\diagnosticserver.cpp`
- `0x180006115`: `DSService created`
- `0x1800061b9`: `DSService Initialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DiagnosticServer::SvcInitialize(DiagnosticServer *this, int a2, char **const a3)
{
  int DSServiceNoLock; // edi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  struct IDSService *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  char *v17; // [rsp+58h] [rbp-19h] BYREF
  const char *v18; // [rsp+60h] [rbp-11h] BYREF
  char *v19; // [rsp+68h] [rbp-9h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+70h] [rbp-1h] BYREF
  struct IDSService *v21; // [rsp+D8h] [rbp+67h] BYREF
  int v22; // [rsp+E0h] [rbp+6Fh]
  char **v23; // [rsp+E8h] [rbp+77h] BYREF
  const char *v24; // [rsp+F0h] [rbp+7Fh] BYREF

  v23 = a3;
  v22 = a2;
  v21 = 0;
  InitializeCriticalSectionEx(&CriticalSection, 0, 0);
  EnterCriticalSection(&CriticalSection);
  DSServiceNoLock = DSService::GetDSServiceNoLock(&v21);
  LeaveCriticalSection(&CriticalSection);
  DeleteCriticalSection(&CriticalSection);
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v5, v4, v6) )
  {
    v22 = 184;
    v24 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\dll\\diagnosticserver.cpp";
    v17 = "DiagnosticServer::SvcInitialize";
    v18 = "DSService created";
    LODWORD(v23) = DSServiceNoLock;
    v19 = qword_180039BD8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v7,
      (__int64)byte_18002EB3D,
      v8,
      v9,
      &v19,
      (__int64)&v23,
      &v18,
      &v17,
      &v24);
  }
  if ( DSServiceNoLock >= 0 )
  {
    v10 = v21;
    DSServiceNoLock = (*(__int64 (__fastcall **)(struct IDSService *, char *, __int64, __int64))(*(_QWORD *)v21 + 24LL))(
                        v21,
                        qword_180039BD8,
                        qword_180039B98,
                        10000);
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180039000, v11, v12) )
    {
      v22 = 192;
      v24 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\dll\\diagnosticserver.cpp";
      v19 = "DiagnosticServer::SvcInitialize";
      v18 = "DSService Initialized";
      LODWORD(v23) = DSServiceNoLock;
      v17 = qword_180039BD8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v13,
        (__int64)&dword_18002EAD4,
        v14,
        v15,
        &v17,
        (__int64)&v23,
        &v18,
        &v19,
        &v24);
    }
    if ( DSServiceNoLock >= 0 && *((struct IDSService **)&xmmword_180039BA0 + 1) != v10 )
    {
      v23 = (char **)v10;
      Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v23);
      v23 = (char **)*((_QWORD *)&xmmword_180039BA0 + 1);
      *((_QWORD *)&xmmword_180039BA0 + 1) = v10;
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v23);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v21);
  return (unsigned int)DSServiceNoLock;
}

```

## disassembly

```asm
0x18000607c  mov     rax, rsp
0x18000607f  mov     [rax+18h], r8
0x180006083  mov     [rax+10h], edx
0x180006086  mov     [rax+8], rcx
0x18000608a  push    rbp
0x18000608b  push    rbx
0x18000608c  push    rsi
0x18000608d  push    rdi
0x18000608e  push    r14
0x180006090  push    r15
0x180006092  lea     rbp, [rax-5Fh]
0x180006096  sub     rsp, 98h
0x18000609d  mov     [rbp+57h+arg_0], 0
0x1800060a5  xor     r8d, r8d; Flags
0x1800060a8  xor     edx, edx; dwSpinCount
0x1800060aa  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x1800060ae  call    cs:__imp_InitializeCriticalSectionEx
0x1800060b4  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x1800060b8  call    cs:__imp_EnterCriticalSection
0x1800060be  lea     rcx, [rbp+57h+arg_0]; struct IDSService **
0x1800060c2  call    ?GetDSServiceNoLock@DSService@@SAJPEAPEAUIDSService@@@Z; DSService::GetDSServiceNoLock(IDSService * *)
0x1800060c7  mov     edi, eax
0x1800060c9  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x1800060cd  call    cs:__imp_LeaveCriticalSection
0x1800060d3  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x1800060d7  call    cs:__imp_DeleteCriticalSection
0x1800060dd  mov     eax, cs:dword_180039000
0x1800060e3  lea     r14, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x1800060ea  lea     r15, aDiagnosticserv_4; "DiagnosticServer::SvcInitialize"
0x1800060f1  lea     rsi, qword_180039BD8
0x1800060f8  cmp     eax, 5
0x1800060fb  jbe     short loc_180006169
0x1800060fd  call    _tlgKeywordOn
0x180006102  test    al, al
0x180006104  jz      short loc_180006169
0x180006106  mov     [rbp+57h+arg_8], 0B8h
0x18000610d  mov     [rbp+57h+arg_18], r14
0x180006111  mov     [rbp+57h+var_70], r15
0x180006115  lea     rax, aDsserviceCreat; "DSService created"
0x18000611c  mov     [rbp+57h+var_68], rax
0x180006120  mov     dword ptr [rbp+57h+arg_10], edi
0x180006123  mov     [rbp+57h+var_60], rsi
0x180006127  lea     rax, [rbp+57h+arg_8]
0x18000612b  mov     [rsp+48h], rax
0x180006130  lea     rax, [rbp+57h+arg_18]
0x180006134  mov     [rsp+0C0h+var_80], rax
0x180006139  lea     rax, [rbp+57h+var_70]
0x18000613d  mov     [rsp+0C0h+var_88], rax
0x180006142  lea     rax, [rbp+57h+var_68]
0x180006146  mov     [rsp+0C0h+var_90], rax
0x18000614b  lea     rax, [rbp+57h+arg_10]
0x18000614f  mov     [rsp+0C0h+var_98], rax
0x180006154  lea     rax, [rbp+57h+var_60]
0x180006158  mov     [rsp+0C0h+var_A0], rax
0x18000615d  lea     rdx, byte_18002EB3D
0x180006164  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180006169  test    edi, edi
0x18000616b  js      loc_180006243
0x180006171  mov     rbx, [rbp+57h+arg_0]
0x180006175  mov     rax, [rbx]
0x180006178  mov     r9d, 2710h
0x18000617e  mov     r8, cs:qword_180039B98
0x180006185  mov     rdx, rsi
0x180006188  mov     rcx, rbx
0x18000618b  mov     rax, [rax+18h]
0x18000618f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006194  mov     edi, eax
0x180006196  mov     ecx, cs:dword_180039000
0x18000619c  cmp     ecx, 5
0x18000619f  jbe     short loc_18000620D
0x1800061a1  call    _tlgKeywordOn
0x1800061a6  test    al, al
0x1800061a8  jz      short loc_18000620D
0x1800061aa  mov     [rbp+57h+arg_8], 0C0h
0x1800061b1  mov     [rbp+57h+arg_18], r14
0x1800061b5  mov     [rbp+57h+var_60], r15
0x1800061b9  lea     rax, aDsserviceIniti_0; "DSService Initialized"
0x1800061c0  mov     [rbp+57h+var_68], rax
0x1800061c4  mov     dword ptr [rbp+57h+arg_10], edi
0x1800061c7  mov     [rbp+57h+var_70], rsi
0x1800061cb  lea     rax, [rbp+57h+arg_8]
0x1800061cf  mov     [rsp+48h], rax
0x1800061d4  lea     rax, [rbp+57h+arg_18]
0x1800061d8  mov     [rsp+0C0h+var_80], rax
0x1800061dd  lea     rax, [rbp+57h+var_60]
0x1800061e1  mov     [rsp+0C0h+var_88], rax
0x1800061e6  lea     rax, [rbp+57h+var_68]
0x1800061ea  mov     [rsp+0C0h+var_90], rax
0x1800061ef  lea     rax, [rbp+57h+arg_10]
0x1800061f3  mov     [rsp+0C0h+var_98], rax
0x1800061f8  lea     rax, [rbp+57h+var_70]
0x1800061fc  mov     [rsp+0C0h+var_A0], rax
0x180006201  lea     rdx, dword_18002EAD4
0x180006208  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000620d  test    edi, edi
0x18000620f  js      short loc_180006243
0x180006211  cmp     qword ptr cs:xmmword_180039BA0+8, rbx
0x180006218  jz      short loc_180006243
0x18000621a  mov     [rbp+57h+arg_10], rbx
0x18000621e  lea     rcx, [rbp+57h+arg_10]
0x180006222  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x180006227  mov     rax, qword ptr cs:xmmword_180039BA0+8
0x18000622e  mov     [rbp+57h+arg_10], rax
0x180006232  mov     qword ptr cs:xmmword_180039BA0+8, rbx
0x180006239  lea     rcx, [rbp+57h+arg_10]
0x18000623d  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180006242  nop
0x180006243  lea     rcx, [rbp+57h+arg_0]
0x180006247  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18000624c  mov     eax, edi
0x18000624e  add     rsp, 98h
0x180006255  pop     r15
0x180006257  pop     r14
0x180006259  pop     rdi
0x18000625a  pop     rsi
0x18000625b  pop     rbx
0x18000625c  pop     rbp
0x18000625d  retn
```
