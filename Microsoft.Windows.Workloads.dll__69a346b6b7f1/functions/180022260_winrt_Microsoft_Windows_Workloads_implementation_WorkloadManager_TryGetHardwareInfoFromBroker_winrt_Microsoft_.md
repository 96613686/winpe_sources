# winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::TryGetHardwareInfoFromBroker(winrt::Microsoft::Windows::Workloads::NpuType *,unsigned __int64 *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> *,uint *)

- ea: `0x180022260`
- end: `0x18002264f`
- name: `?TryGetHardwareInfoFromBroker@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@AEAA_NPEAW4NpuType@3456@PEA_KPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAI@Z`
- size: `1007`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x180001b90`
- `0x180001ca0`
- `0x18000d970`
- `0x1800119b0`
- `0x1800155c0`
- `0x180022260`
- `0x180024d50`
- `0x180024e40`
- `0x180024f30`
- `0x1800268c0`
- `0x18002ac60`
- `0x18002b2e0`
- `0x180030b03`
- `0x180034ef0`
- `0x180039893`
- `0x18003bed0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x18002246c`
- `ADVAPI32!EventWriteTransfer` at `0x18002246c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002258a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800225ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18002258a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800225ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::TryGetHardwareInfoFromBroker(
        __int64 a1,
        _DWORD *a2,
        const wchar_t **a3,
        __int64 a4,
        _DWORD *a5)
{
  LPVOID v9; // rbx
  _BYTE *v10; // rax
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdx
  unsigned __int8 v13; // di
  int v14; // eax
  unsigned int v15; // r8d
  const struct _tlgProvider_t *v16; // rax
  LPVOID v17; // r14
  const WCHAR *v18; // rsi
  __int64 v19; // rdi
  int v20; // eax
  __int64 v21; // r8
  int v22; // r12d
  EVENT_DESCRIPTOR *p_EventDescriptor; // rax
  const struct _tlgProvider_t *v24; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  int v27; // eax
  unsigned int v28; // r8d
  int ppv; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+44h] [rbp-BCh] BYREF
  IID rclsid; // [rsp+48h] [rbp-B8h] BYREF
  int v34; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v35; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v36; // [rsp+68h] [rbp-98h] BYREF
  EVENT_DESCRIPTOR v37; // [rsp+70h] [rbp-90h] BYREF
  __m128i v38; // [rsp+80h] [rbp-80h]
  LPVOID v39; // [rsp+90h] [rbp-70h] BYREF
  LPCWCH lpWideCharStr; // [rsp+98h] [rbp-68h] BYREF
  int v41; // [rsp+A0h] [rbp-60h] BYREF
  int v42; // [rsp+A4h] [rbp-5Ch] BYREF
  const wchar_t *v43; // [rsp+A8h] [rbp-58h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+B0h] [rbp-50h] BYREF
  __m128i si128; // [rsp+C0h] [rbp-40h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+D0h] [rbp-30h] BYREF
  char *v47; // [rsp+E0h] [rbp-20h]
  int v48; // [rsp+E8h] [rbp-18h]
  int v49; // [rsp+ECh] [rbp-14h]
  int *v50; // [rsp+F0h] [rbp-10h]
  __int64 v51; // [rsp+F8h] [rbp-8h]
  const wchar_t **v52; // [rsp+100h] [rbp+0h]
  __int64 v53; // [rsp+108h] [rbp+8h]
  int *v54; // [rsp+110h] [rbp+10h]
  __int64 v55; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v9 = 0;
  *a2 = 0;
  *a3 = 0;
  *(_QWORD *)(a4 + 16) = 0;
  v10 = (_BYTE *)a4;
  if ( *(_QWORD *)(a4 + 24) > 0xFu )
    v10 = *(_BYTE **)a4;
  *v10 = 0;
  *a5 = 0;
  v11 = TraceLogger::Provider();
  if ( *(_DWORD *)v11 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v11,
      (unsigned __int8 *)word_18004DAAA);
  rclsid.Data1 = -455322399;
  *(_DWORD *)&rclsid.Data2 = 1148794293;
  *(_DWORD *)rclsid.Data4 = -2075124834;
  *(_DWORD *)&rclsid.Data4[4] = 1989909936;
  v39 = 0;
  CoCreateInstance_0(&rclsid, 0, *(_DWORD *)(a1 + 224), &winrt::impl::guid_v<ISessionManagerBroker3>, &v39);
  v36 = v39;
  if ( !v39 )
  {
    v31 = -2147467262;
    TraceLogger::WorkloadManagerTryGetHardwareInfoFromBrokerFallback<long>(&v31);
    v13 = 0;
    goto LABEL_29;
  }
  v41 = 0;
  v43 = 0;
  v14 = (*(__int64 (__fastcall **)(LPVOID, int *, const wchar_t **))(*(_QWORD *)v39 + 72LL))(v39, &v41, &v43);
  v31 = v14;
  _mm_lfence();
  if ( v14 >= 0 )
  {
    *a2 = v41;
    *a3 = v43;
    v16 = TraceLogger::Provider();
    if ( *(_DWORD *)v16 > 5u )
    {
      v31 = 0;
      v35 = v43;
      v34 = v41;
      v54 = &v31;
      v55 = 4;
      v52 = &v35;
      v53 = 8;
      v50 = &v34;
      v51 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 5;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = *((_QWORD *)v16 + 1);
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      v47 = byte_18004D825;
      v48 = 82;
      v49 = 1;
      v32 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*((_QWORD *)v16 + 4), &EventDescriptor, 0, 0, 5u, &UserData);
    }
    lpWideCharStr = 0;
    v17 = v39;
    v32 = (*(__int64 (__fastcall **)(LPVOID, LPCWCH *))(*(_QWORD *)v39 + 80LL))(v39, &lpWideCharStr);
    if ( v32 < 0 )
    {
      if ( lpWideCharStr )
        SysFreeString((BSTR)lpWideCharStr);
    }
    else
    {
      v18 = lpWideCharStr;
      if ( lpWideCharStr )
      {
        v19 = -1;
        do
          ++v19;
        while ( lpWideCharStr[v19] );
        v20 = WINRT_IMPL_WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, v19, 0, 0, 0, 0);
        v22 = v20;
        if ( v20 )
        {
          LOBYTE(v21) = 63;
          std::string::string(&EventDescriptor, v20, v21);
          p_EventDescriptor = &EventDescriptor;
          if ( si128.m128i_i64[1] > 0xFuLL )
            p_EventDescriptor = *(EVENT_DESCRIPTOR **)&EventDescriptor.Id;
          WINRT_IMPL_WideCharToMultiByte(0xFDE9u, 0, v18, v19, (LPSTR)p_EventDescriptor, v22, 0, 0);
          v37 = EventDescriptor;
          v38 = si128;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOBYTE(EventDescriptor.Id) = 0;
          std::string::_Tidy_deallocate((__int64)&EventDescriptor);
        }
        else
        {
          v37 = 0;
          v38 = _mm_load_si128((const __m128i *)&_xmm);
          LOBYTE(v37.Id) = 0;
        }
        std::string::operator=(a4, &v37);
        std::string::_Tidy_deallocate((__int64)&v37);
        SysFreeString((BSTR)lpWideCharStr);
        v24 = TraceLogger::Provider();
        if ( *(_DWORD *)v24 > 5u )
        {
          v35 = L"GetWorkloads succeeded";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
            (__int64)v24,
            (unsigned __int8 *)byte_18004D7D5,
            v25,
            v26,
            &v35);
        }
        goto LABEL_25;
      }
    }
    TraceLogger::WorkloadManagerBrokerResourceDllPathFailed<long &>(&v32);
LABEL_25:
    v42 = 0;
    v27 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v17 + 88LL))(v17, &v42);
    if ( v27 >= 0 )
    {
      *a5 = v42;
    }
    else
    {
      _mm_lfence();
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x354, v28, (const char *)(unsigned int)v27, ppv);
      v17 = v39;
    }
    v13 = 1;
    v9 = v17;
    goto LABEL_29;
  }
  wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x331, v15, (const char *)(unsigned int)v14, ppv);
  TraceLogger::WorkloadManagerTryGetHardwareInfoFromBrokerFallback<long &>(&v31);
  v9 = v39;
  v13 = 0;
LABEL_29:
  if ( v9 )
    winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(&v36, v12);
  return v13;
}

```

## disassembly

```asm
0x180022260  push    rbp
0x180022262  push    rbx
0x180022263  push    rsi
0x180022264  push    rdi
0x180022265  push    r12
0x180022267  push    r13
0x180022269  push    r14
0x18002226b  push    r15
0x18002226d  lea     rbp, [rsp-38h]
0x180022272  sub     rsp, 138h
0x180022279  mov     rax, cs:__security_cookie
0x180022280  xor     rax, rsp
0x180022283  mov     [rbp+70h+var_50], rax
0x180022287  mov     r15, r9
0x18002228a  mov     rsi, r8
0x18002228d  mov     rdi, rdx
0x180022290  mov     r14, rcx
0x180022293  mov     r13, [rbp+70h+arg_20]
0x18002229a  xor     ebx, ebx
0x18002229c  mov     [rdx], ebx
0x18002229e  mov     [r8], rbx
0x1800222a1  mov     [r9+10h], rbx
0x1800222a5  mov     rax, r9
0x1800222a8  cmp     qword ptr [r9+18h], 0Fh
0x1800222ad  jbe     short loc_1800222B2
0x1800222af  mov     rax, [r9]
0x1800222b2  mov     [rax], bl
0x1800222b4  mov     [r13+0], ebx
0x1800222b8  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x1800222bd  cmp     dword ptr [rax], 5
0x1800222c0  jbe     short loc_1800222D1
0x1800222c2  lea     rdx, word_18004DAAA
0x1800222c9  mov     rcx, rax
0x1800222cc  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800222d1  mov     [rsp+170h+rclsid.Data1], 0E4DC54E1h
0x1800222d9  mov     dword ptr [rsp+170h+rclsid.Data2], 447935B5h
0x1800222e1  mov     dword ptr [rsp+170h+rclsid.Data4], 84501B9Eh
0x1800222e9  mov     dword ptr [rsp+170h+rclsid.Data4+4], 769B9DB0h
0x1800222f1  mov     [rbp+70h+var_E0], rbx
0x1800222f5  lea     rax, [rbp+70h+var_E0]
0x1800222f9  mov     [rsp+170h+ppv], rax; int
0x1800222fe  lea     r9, ??$guid_v@UISessionManagerBroker3@@@impl@winrt@@3Uguid@2@B; riid
0x180022305  mov     r8d, [r14+0E0h]; dwClsContext
0x18002230c  xor     edx, edx; pUnkOuter
0x18002230e  lea     rcx, [rsp+170h+rclsid]; rclsid
0x180022313  call    CoCreateInstance_0
0x180022318  mov     rcx, [rbp+70h+var_E0]
0x18002231c  mov     [rsp+170h+var_108], rcx
0x180022321  test    rcx, rcx
0x180022324  jnz     short loc_180022340
0x180022326  mov     [rsp+170h+var_130], 80004002h
0x18002232e  lea     rcx, [rsp+170h+var_130]
0x180022333  call    ??$WorkloadManagerTryGetHardwareInfoFromBrokerFallback@J@TraceLogger@@SAX$$QEAJ@Z; TraceLogger::WorkloadManagerTryGetHardwareInfoFromBrokerFallback<long>(long &&)
0x180022338  xor     dil, dil
0x18002233b  jmp     loc_18002261C
0x180022340  mov     [rbp+70h+var_D0], ebx
0x180022343  mov     [rbp+70h+var_C8], rbx
0x180022347  mov     rax, [rcx]
0x18002234a  lea     r8, [rbp+70h+var_C8]
0x18002234e  lea     rdx, [rbp+70h+var_D0]
0x180022352  mov     rax, [rax+48h]
0x180022356  call    cs:__guard_dispatch_icall_fptr
0x18002235c  mov     [rsp+170h+var_130], eax
0x180022360  mov     rcx, [rbp+78h]; this
0x180022364  lfence
0x180022367  test    eax, eax
0x180022369  jns     short loc_18002238E
0x18002236b  mov     r9d, eax; char *
0x18002236e  mov     edx, 331h; void *
0x180022373  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022378  lea     rcx, [rsp+170h+var_130]
0x18002237d  call    ??$WorkloadManagerTryGetHardwareInfoFromBrokerFallback@AEAJ@TraceLogger@@SAXAEAJ@Z; TraceLogger::WorkloadManagerTryGetHardwareInfoFromBrokerFallback<long &>(long &)
0x180022382  mov     rbx, [rbp+70h+var_E0]
0x180022386  xor     dil, dil
0x180022389  jmp     loc_18002261C
0x18002238e  mov     eax, [rbp+70h+var_D0]
0x180022391  mov     [rdi], eax
0x180022393  mov     rax, [rbp+70h+var_C8]
0x180022397  mov     [rsi], rax
0x18002239a  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18002239f  mov     r10, rax
0x1800223a2  cmp     dword ptr [rax], 5
0x1800223a5  jbe     loc_180022472
0x1800223ab  mov     [rsp+170h+var_130], ebx
0x1800223af  mov     rcx, [rbp+70h+var_C8]
0x1800223b3  mov     [rsp+170h+var_110], rcx
0x1800223b8  mov     ecx, [rbp+70h+var_D0]
0x1800223bb  mov     [rsp+170h+var_118], ecx
0x1800223bf  lea     rax, [rsp+170h+var_130]
0x1800223c4  mov     [rbp+70h+var_60], rax
0x1800223c8  mov     [rbp+70h+var_58], 4
0x1800223d0  lea     rax, [rsp+170h+var_110]
0x1800223d5  mov     [rbp+70h+var_70], rax
0x1800223d9  mov     [rbp+70h+var_68], 8
0x1800223e1  lea     rax, [rsp+170h+var_118]
0x1800223e6  mov     [rbp+70h+var_80], rax
0x1800223ea  mov     [rbp+70h+var_78], 4
0x1800223f2  mov     dword ptr [rbp+70h+EventDescriptor.Id], 0B000000h
0x1800223f9  movzx   eax, cs:word_18004D81B
0x180022400  mov     dword ptr [rbp+70h+EventDescriptor.Level], eax
0x180022403  mov     [rbp+70h+EventDescriptor.Keyword], rbx
0x180022407  mov     rax, [r10+8]
0x18002240b  mov     [rbp+70h+var_A0.Ptr], rax
0x18002240f  movzx   eax, word ptr [rax]
0x180022412  mov     [rbp+70h+var_A0.Size], eax
0x180022415  mov     dword ptr [rbp+70h+var_A0.0Ch], 2
0x18002241c  lea     rax, byte_18004D825
0x180022423  mov     [rbp+70h+var_90], rax
0x180022427  mov     [rbp+70h+var_88], 52h ; 'R'
0x18002242e  mov     [rbp+70h+var_84], 1
0x180022435  lea     rax, _TraceLoggingMetadataEnd
0x18002243c  lea     rcx, _TraceLoggingMetadata
0x180022443  sub     eax, ecx
0x180022445  mov     [rsp+170h+var_12C], eax
0x180022449  mov     eax, [rsp+170h+var_12C]
0x18002244d  lea     rax, [rbp+70h+var_A0]
0x180022451  mov     [rsp+170h+UserData], rax; UserData
0x180022456  mov     dword ptr [rsp+170h+ppv], 5; int
0x18002245e  xor     r9d, r9d; RelatedActivityId
0x180022461  xor     r8d, r8d; ActivityId
0x180022464  lea     rdx, [rbp+70h+EventDescriptor]; EventDescriptor
0x180022468  mov     rcx, [r10+20h]; RegHandle
0x18002246c  call    cs:__imp_EventWriteTransfer
0x180022472  mov     [rbp+70h+lpWideCharStr], rbx
0x180022476  mov     r14, [rbp+70h+var_E0]
0x18002247a  mov     rax, [r14]
0x18002247d  lea     rdx, [rbp+70h+lpWideCharStr]
0x180022481  mov     rcx, r14
0x180022484  mov     rax, [rax+50h]
0x180022488  call    cs:__guard_dispatch_icall_fptr
0x18002248e  mov     [rsp+170h+var_12C], eax
0x180022492  test    eax, eax
0x180022494  js      loc_1800225C1
0x18002249a  mov     rsi, [rbp+70h+lpWideCharStr]
0x18002249e  test    rsi, rsi
0x1800224a1  jz      loc_1800225D0
0x1800224a7  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800224ae  xchg    ax, ax
0x1800224b0  inc     rdi
0x1800224b3  cmp     word ptr [rsi+rdi*2], 0
0x1800224b8  jnz     short loc_1800224B0
0x1800224ba  mov     [rsp+170h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x1800224bf  mov     [rsp+170h+lpDefaultChar], rbx; lpDefaultChar
0x1800224c4  mov     dword ptr [rsp+170h+UserData], ebx; cbMultiByte
0x1800224c8  mov     [rsp+170h+ppv], rbx; lpMultiByteStr
0x1800224cd  mov     r9d, edi; cchWideChar
0x1800224d0  mov     r8, rsi; lpWideCharStr
0x1800224d3  xor     edx, edx; dwFlags
0x1800224d5  mov     ecx, 0FDE9h; CodePage
0x1800224da  call    WINRT_IMPL_WideCharToMultiByte
0x1800224df  movsxd  r12, eax
0x1800224e2  test    eax, eax
0x1800224e4  jnz     short loc_180022501
0x1800224e6  xorps   xmm0, xmm0
0x1800224e9  movups  [rsp+170h+var_100], xmm0
0x1800224ee  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800224f6  movdqu  [rbp+70h+var_F0], xmm1
0x1800224fb  mov     byte ptr [rsp+170h+var_100], al
0x1800224ff  jmp     short loc_18002256F
0x180022501  mov     rdx, r12
0x180022504  mov     r8b, 3Fh ; '?'
0x180022507  lea     rcx, [rbp+70h+EventDescriptor]
0x18002250b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@_KD@Z; std::string::string(unsigned __int64,char)
0x180022510  lea     rax, [rbp+70h+EventDescriptor]
0x180022514  cmp     [rbp+70h+var_A8], 0Fh
0x180022519  cmova   rax, qword ptr [rbp+70h+EventDescriptor.Id]
0x18002251e  mov     [rsp+170h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x180022523  mov     [rsp+170h+lpDefaultChar], rbx; lpDefaultChar
0x180022528  mov     dword ptr [rsp+170h+UserData], r12d; cbMultiByte
0x18002252d  mov     [rsp+170h+ppv], rax; lpMultiByteStr
0x180022532  mov     r9d, edi; cchWideChar
0x180022535  mov     r8, rsi; lpWideCharStr
0x180022538  xor     edx, edx; dwFlags
0x18002253a  mov     ecx, 0FDE9h; CodePage
0x18002253f  call    WINRT_IMPL_WideCharToMultiByte
0x180022544  movups  xmm0, xmmword ptr [rbp+70h+EventDescriptor.Id]
0x180022548  movups  [rsp+170h+var_100], xmm0
0x18002254d  movups  xmm1, xmmword ptr [rbp-40h]
0x180022551  movups  [rbp+70h+var_F0], xmm1
0x180022555  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18002255d  movdqu  xmmword ptr [rbp-40h], xmm0
0x180022562  mov     byte ptr [rbp+70h+EventDescriptor.Id], 0
0x180022566  lea     rcx, [rbp+70h+EventDescriptor]
0x18002256a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002256f  lea     rdx, [rsp+170h+var_100]
0x180022574  mov     rcx, r15
0x180022577  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002257c  lea     rcx, [rsp+170h+var_100]
0x180022581  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180022586  mov     rcx, [rbp+70h+lpWideCharStr]; bstrString
0x18002258a  call    cs:__imp_SysFreeString
0x180022590  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x180022595  cmp     dword ptr [rax], 5
0x180022598  jbe     short loc_1800225DA
0x18002259a  lea     rcx, aGetworkloadsSu; "GetWorkloads succeeded"
0x1800225a1  mov     [rsp+170h+var_110], rcx
0x1800225a6  lea     rcx, [rsp+170h+var_110]
0x1800225ab  mov     [rsp+170h+ppv], rcx
0x1800225b0  lea     rdx, byte_18004D7D5
0x1800225b7  mov     rcx, rax
0x1800225ba  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1800225bf  jmp     short loc_1800225DA
0x1800225c1  mov     rcx, [rbp+70h+lpWideCharStr]; bstrString
0x1800225c5  test    rcx, rcx
0x1800225c8  jz      short loc_1800225D0
0x1800225ca  call    cs:__imp_SysFreeString
0x1800225d0  lea     rcx, [rsp+170h+var_12C]
0x1800225d5  call    ??$WorkloadManagerBrokerResourceDllPathFailed@AEAJ@TraceLogger@@SAXAEAJ@Z; TraceLogger::WorkloadManagerBrokerResourceDllPathFailed<long &>(long &)
0x1800225da  mov     [rbp+70h+var_CC], ebx
0x1800225dd  mov     rax, [r14]
0x1800225e0  lea     rdx, [rbp+70h+var_CC]
0x1800225e4  mov     rcx, r14
0x1800225e7  mov     rax, [rax+58h]
0x1800225eb  call    cs:__guard_dispatch_icall_fptr
0x1800225f1  mov     rcx, [rbp+78h]; this
0x1800225f5  test    eax, eax
0x1800225f7  jns     short loc_18002260F
0x1800225f9  lfence
0x1800225fc  mov     r9d, eax; char *
0x1800225ff  mov     edx, 354h; void *
0x180022604  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022609  mov     r14, [rbp+70h+var_E0]
0x18002260d  jmp     short loc_180022616
0x18002260f  mov     eax, [rbp+70h+var_CC]
0x180022612  mov     [r13+0], eax
0x180022616  mov     dil, 1
0x180022619  mov     rbx, r14
0x18002261c  test    rbx, rbx
0x18002261f  jz      short loc_18002262B
0x180022621  lea     rcx, [rsp+170h+var_108]
0x180022626  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerBroker@@@winrt@@AEAAXXZ; winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(void)
0x18002262b  movzx   eax, dil
0x18002262f  mov     rcx, [rbp+70h+var_50]
0x180022633  xor     rcx, rsp; StackCookie
0x180022636  call    __security_check_cookie
0x18002263b  add     rsp, 138h
0x180022642  pop     r15
0x180022644  pop     r14
0x180022646  pop     r13
0x180022648  pop     r12
0x18002264a  pop     rdi
0x18002264b  pop     rsi
0x18002264c  pop     rbx
0x18002264d  pop     rbp
0x18002264e  retn
```
