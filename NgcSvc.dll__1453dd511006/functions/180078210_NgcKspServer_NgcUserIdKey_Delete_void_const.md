# NgcKspServer::NgcUserIdKey::Delete(void * const)

- ea: `0x180078210`
- end: `0x180078507`
- name: `?Delete@NgcUserIdKey@NgcKspServer@@UEAAJQEAX@Z`
- size: `759`
- prototype: `__int64 __fastcall(NgcKspServer::NgcUserIdKey *__hidden this, void *const)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000782c`
- `0x180021690`
- `0x1800281e0`
- `0x1800288a0`
- `0x180028d18`
- `0x180029f0c`
- `0x180031c3c`
- `0x180038764`
- `0x180046d90`
- `0x18005cee0`
- `0x18005dd2c`
- `0x18005dd44`
- `0x180078210`
- `0x18007c9fc`
- `0x1800c4090`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180078256`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180078256`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800782c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180078344`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800783a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800784d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800782c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180078344`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800783a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800784d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078498`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078498`
- `ntdll!RtlPublishWnfStateData` at `0x18007844c`
- `ntdll!RtlPublishWnfStateData` at `0x18007844c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800783cb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800783cb`

## string_xrefs

- `0x18007832a`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcKspServer::NgcUserIdKey::Delete(RTL_SRWLOCK *this, void *const a2)
{
  unsigned int v4; // esi
  WCHAR *v5; // rbx
  char IsEnabled; // al
  RTL_SRWLOCK *v8; // r9
  RTL_SRWLOCK *v9; // r8
  RTL_SRWLOCK *v10; // rdx
  __int64 (__fastcall *v11)(PVOID, RTL_SRWLOCK *, RTL_SRWLOCK *, RTL_SRWLOCK *); // r14
  PVOID Ptr; // rcx
  int v13; // eax
  unsigned int v14; // r14d
  int v15; // eax
  unsigned int v16; // edi
  int v17; // r10d
  int v18; // eax
  char *v19; // rdx
  RTL_SRWLOCK *v20; // [rsp+20h] [rbp-E0h]
  DWORD LastError; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE Src[2160]; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+8B0h] [rbp+7B0h] BYREF
  unsigned __int16 v25[1076]; // [rsp+8B4h] [rbp+7B4h] BYREF
  char v26; // [rsp+111Ch] [rbp+101Ch]
  wil::details::in1diag3 *retaddr; // [rsp+1148h] [rbp+1048h]

  v4 = 0;
  v5 = (WCHAR *)&this[34];
  AcquireSRWLockExclusive(this + 34);
  StringSid = v5;
  if ( !LOBYTE(this[37].Ptr) )
    goto LABEL_20;
  if ( NgcKspServer::NgcUserIdKey::IsRegisteredAadKeyForCaller((NgcKspServer::NgcUserIdKey *)this, a2) )
  {
    if ( (unsigned int)dword_180122070 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180122070, 0x400000000000LL) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)&byte_18010416F,
        0);
    if ( v5 )
      ReleaseSRWLockExclusive((PSRWLOCK)v5);
    return 2148073488LL;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
  v8 = this + 9;
  v9 = this + 17;
  v10 = this + 7;
  v11 = *(__int64 (__fastcall **)(PVOID, RTL_SRWLOCK *, RTL_SRWLOCK *, RTL_SRWLOCK *))(*(_QWORD *)this[44].Ptr + 184LL);
  v20 = this + 13;
  Ptr = this[44].Ptr;
  if ( IsEnabled )
  {
    v13 = v11(Ptr, v10, v9, v8);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6A2,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
        (const char *)(unsigned int)v13,
        (int)v20);
      if ( v5 )
        ReleaseSRWLockExclusive((PSRWLOCK)v5);
      return v14;
    }
LABEL_20:
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    if ( ConvertSidToStringSidW(this[4].Ptr, &StringSid) )
    {
      v24 = 9;
      memset_0(Src, 0, 0x868u);
      memcpy_0(v25, Src, sizeof(v25));
      v26 = 0;
      v17 = StringCchCopyW(v25, 0x433u, StringSid);
      if ( v17 >= 0 )
      {
        v18 = RtlPublishWnfStateData(WNF_NGC_CREDENTIAL_REFRESH_REQUIRED, 0, &v24, 2160, 0);
        if ( v18 >= 0 || (unsigned int)dword_180122070 <= 3 )
          goto LABEL_30;
        LastError = v18 | 0x10000000;
        v19 = byte_1801040A9;
        goto LABEL_29;
      }
      if ( (unsigned int)dword_180122070 > 3 )
      {
        LastError = v17;
        v19 = (char *)word_1801040D2;
LABEL_29:
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)v19,
          0,
          0,
          (__int64)&LastError);
      }
    }
    else if ( (unsigned int)dword_180122070 > 3 )
    {
      LastError = GetLastError();
      v19 = byte_18010410B;
      goto LABEL_29;
    }
LABEL_30:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
    if ( v5 )
      ReleaseSRWLockExclusive((PSRWLOCK)v5);
    return v4;
  }
  v15 = ((__int64 (__fastcall *)(PVOID, RTL_SRWLOCK *, RTL_SRWLOCK *, RTL_SRWLOCK *, RTL_SRWLOCK *))v11)(
          Ptr,
          v10,
          v9,
          v8,
          v20);
  v4 = v15;
  if ( v15 >= 0 )
    goto LABEL_20;
  if ( (unsigned int)dword_180122070 > 2 )
  {
    LastError = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)&unk_180104140,
      0,
      0,
      (__int64)&LastError);
  }
  v16 = HResultToSecurityStatus(v4);
  if ( v5 )
    ReleaseSRWLockExclusive((PSRWLOCK)v5);
  return v16;
}

```

## disassembly

```asm
0x180078210  mov     [rsp-8+arg_10], rbx
0x180078215  mov     [rsp-8+arg_18], rsi
0x18007821a  push    rbp
0x18007821b  push    rdi
0x18007821c  push    r14
0x18007821e  lea     rbp, [rsp-1030h]
0x180078226  mov     eax, 1130h
0x18007822b  call    _alloca_probe
0x180078230  sub     rsp, rax
0x180078233  mov     rax, cs:__security_cookie
0x18007823a  xor     rax, rsp
0x18007823d  mov     [rbp+1040h+var_20], rax
0x180078244  mov     r14, rdx
0x180078247  mov     rdi, rcx
0x18007824a  xor     esi, esi
0x18007824c  lea     rbx, [rcx+110h]
0x180078253  mov     rcx, rbx; SRWLock
0x180078256  call    cs:__imp_AcquireSRWLockExclusive
0x18007825c  mov     [rsp+1140h+StringSid], rbx
0x180078261  cmp     [rdi+128h], sil
0x180078268  jz      loc_1800783AD
0x18007826e  mov     rdx, r14; void *
0x180078271  mov     rcx, rdi; this
0x180078274  call    ?IsRegisteredAadKeyForCaller@NgcUserIdKey@NgcKspServer@@AEBA_NQEAX@Z; NgcKspServer::NgcUserIdKey::IsRegisteredAadKeyForCaller(void * const)
0x180078279  test    al, al
0x18007827b  jz      short loc_1800782D1
0x18007827d  mov     eax, cs:dword_180122070
0x180078283  cmp     eax, 5
0x180078286  jbe     short loc_1800782B9
0x180078288  mov     rdx, 400000000000h
0x180078292  lea     rcx, dword_180122070
0x180078299  call    _tlgKeywordOn
0x18007829e  test    al, al
0x1800782a0  jz      short loc_1800782B9
0x1800782a2  xor     r8d, r8d
0x1800782a5  lea     rdx, byte_18010416F
0x1800782ac  lea     rcx, dword_180122070
0x1800782b3  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800782b8  nop
0x1800782b9  test    rbx, rbx
0x1800782bc  jz      short loc_1800782C7
0x1800782be  mov     rcx, rbx; SRWLock
0x1800782c1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800782c7  mov     eax, 80090010h
0x1800782cc  jmp     loc_1800784E0
0x1800782d1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x1800782d8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x1800782dd  lea     r11, [rdi+68h]
0x1800782e1  lea     r9, [rdi+48h]
0x1800782e5  lea     r8, [rdi+88h]
0x1800782ec  lea     rdx, [rdi+38h]
0x1800782f0  mov     r10, [rdi+160h]
0x1800782f7  mov     rcx, [r10]
0x1800782fa  mov     r14, [rcx+0B8h]
0x180078301  mov     qword ptr [rsp+1140h+var_1120], r11; int
0x180078306  mov     rcx, r10
0x180078309  test    al, al
0x18007830b  mov     rax, r14
0x18007830e  jz      short loc_180078352
0x180078310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078315  mov     r14d, eax
0x180078318  test    eax, eax
0x18007831a  jns     loc_1800783AD
0x180078320  mov     rcx, [rbp+1048h]; this
0x180078327  mov     r9d, eax; char *
0x18007832a  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180078331  mov     edx, 6A2h; void *
0x180078336  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007833b  nop
0x18007833c  test    rbx, rbx
0x18007833f  jz      short loc_18007834A
0x180078341  mov     rcx, rbx; SRWLock
0x180078344  call    cs:__imp_ReleaseSRWLockExclusive
0x18007834a  mov     eax, r14d
0x18007834d  jmp     loc_1800784E0
0x180078352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078357  mov     esi, eax
0x180078359  test    eax, eax
0x18007835b  jns     short loc_1800783AD
0x18007835d  mov     ecx, cs:dword_180122070
0x180078363  cmp     ecx, 2
0x180078366  jbe     short loc_18007838F
0x180078368  mov     [rsp+1140h+var_1110], eax
0x18007836c  lea     rax, [rsp+1140h+var_1110]
0x180078371  mov     qword ptr [rsp+1140h+var_1120], rax
0x180078376  xor     r9d, r9d
0x180078379  xor     r8d, r8d
0x18007837c  lea     rdx, unk_180104140
0x180078383  lea     rcx, dword_180122070
0x18007838a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007838f  mov     ecx, esi; int
0x180078391  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x180078396  mov     edi, eax
0x180078398  test    rbx, rbx
0x18007839b  jz      short loc_1800783A6
0x18007839d  mov     rcx, rbx; SRWLock
0x1800783a0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800783a6  mov     eax, edi
0x1800783a8  jmp     loc_1800784E0
0x1800783ad  mov     [rsp+1140h+StringSid], 0
0x1800783b6  xor     edx, edx
0x1800783b8  lea     rcx, [rsp+1140h+StringSid]
0x1800783bd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800783c2  lea     rdx, [rsp+1140h+StringSid]; StringSid
0x1800783c7  mov     rcx, [rdi+20h]; Sid
0x1800783cb  call    cs:__imp_ConvertSidToStringSidW
0x1800783d1  test    eax, eax
0x1800783d3  jz      loc_18007848D
0x1800783d9  mov     [rbp+1040h+var_890], 9
0x1800783e3  mov     edi, 868h
0x1800783e8  mov     r8d, edi; Size
0x1800783eb  xor     edx, edx; Val
0x1800783ed  lea     rcx, [rsp+1140h+Src]; void *
0x1800783f2  call    memset_0
0x1800783f7  lea     rcx, [rbp+1040h+var_88C]; void *
0x1800783fe  lea     rdx, [rsp+1140h+Src]; Src
0x180078403  mov     r8d, edi; Size
0x180078406  call    memcpy_0
0x18007840b  mov     [rbp+1040h+var_24], 0
0x180078412  mov     r8, [rsp+1140h+StringSid]; unsigned __int16 *
0x180078417  mov     edx, 433h; unsigned __int64
0x18007841c  lea     rcx, [rbp+1040h+var_88C]; unsigned __int16 *
0x180078423  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180078428  mov     r10d, eax
0x18007842b  test    eax, eax
0x18007842d  js      short loc_180078474
0x18007842f  mov     qword ptr [rsp+1140h+var_1120], 0
0x180078438  lea     r9d, [rdi+8]
0x18007843c  lea     r8, [rbp+1040h+var_890]
0x180078443  xor     edx, edx
0x180078445  mov     rcx, cs:WNF_NGC_CREDENTIAL_REFRESH_REQUIRED
0x18007844c  call    cs:__imp_RtlPublishWnfStateData
0x180078452  mov     ecx, eax
0x180078454  or      ecx, 10000000h
0x18007845a  jge     short loc_1800784C5
0x18007845c  mov     eax, cs:dword_180122070
0x180078462  cmp     eax, 3
0x180078465  jbe     short loc_1800784C5
0x180078467  mov     [rsp+1140h+var_1110], ecx
0x18007846b  lea     rdx, byte_1801040A9
0x180078472  jmp     short loc_1800784A9
0x180078474  mov     eax, cs:dword_180122070
0x18007847a  cmp     eax, 3
0x18007847d  jbe     short loc_1800784C5
0x18007847f  mov     [rsp+1140h+var_1110], r10d
0x180078484  lea     rdx, word_1801040D2
0x18007848b  jmp     short loc_1800784A9
0x18007848d  mov     eax, cs:dword_180122070
0x180078493  cmp     eax, 3
0x180078496  jbe     short loc_1800784C5
0x180078498  call    cs:__imp_GetLastError
0x18007849e  mov     [rsp+1140h+var_1110], eax
0x1800784a2  lea     rdx, byte_18010410B
0x1800784a9  lea     rax, [rsp+1140h+var_1110]
0x1800784ae  mov     qword ptr [rsp+1140h+var_1120], rax
0x1800784b3  xor     r9d, r9d
0x1800784b6  xor     r8d, r8d
0x1800784b9  lea     rcx, dword_180122070
0x1800784c0  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800784c5  lea     rcx, [rsp+1140h+StringSid]; void *
0x1800784ca  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800784cf  nop
0x1800784d0  test    rbx, rbx
0x1800784d3  jz      short loc_1800784DE
0x1800784d5  mov     rcx, rbx; SRWLock
0x1800784d8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800784de  mov     eax, esi
0x1800784e0  mov     rcx, [rbp+1040h+var_20]
0x1800784e7  xor     rcx, rsp; StackCookie
0x1800784ea  call    __security_check_cookie
0x1800784ef  lea     r11, [rsp+1140h+var_10]
0x1800784f7  mov     rbx, [r11+30h]
0x1800784fb  mov     rsi, [r11+38h]
0x1800784ff  mov     rsp, r11
0x180078502  pop     r14
0x180078504  pop     rdi
0x180078505  pop     rbp
0x180078506  retn
```
