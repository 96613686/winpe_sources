# AppV::Client::Service::AppVClientImpl::SelectPublishPackagePolicy(AppV::Client::PackageIdentity const &,short,wchar_t * const &,tagVARIANT const &,AppV::Client::PublishPackageData::PublishPolicy &,std::shared_ptr<AppV::Policy::PackageUserPolicyDocument> &,_SYSTEMTIME &,unsigned __int64 &)

- ea: `0x140036680`
- end: `0x140036cac`
- name: `?SelectPublishPackagePolicy@AppVClientImpl@Service@Client@AppV@@AEBAJAEBUPackageIdentity@34@FAEBQEA_WAEBUtagVARIANT@@AEAW4PublishPolicy@PublishPackageData@34@AEAV?$shared_ptr@VPackageUserPolicyDocument@Policy@AppV@@@std@@AEAU_SYSTEMTIME@@AEA_K@Z`
- size: `1580`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x14002b460`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140018bec`
- `0x140024fa8`
- `0x140036680`
- `0x14003a0e8`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x140036c7d`
- `KERNEL32!GetSystemTime` at `0x140036c7d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400368e2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400369cc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400368e2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400369cc`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036a6f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036a97`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036ad5`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036b0a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036b55`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036b7d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036bae`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036be3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036a6f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036a97`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036ad5`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036b0a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036b55`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036b7d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036bae`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036be3`
- `APPVPOLICY!__imp_CreatePackageUserPolicyDocument` at `0x140036939`
- `APPVPOLICY!__imp_CreatePackageUserPolicyDocument` at `0x140036939`
- `APPVPOLICY!__imp_CreatePackageUserPolicyDocumentFromFile` at `0x140036a3b`
- `APPVPOLICY!__imp_CreatePackageUserPolicyDocumentFromFile` at `0x140036a3b`
- `OLEAUT32!__imp_SysStringLen` at `0x140036736`
- `OLEAUT32!__imp_SysStringLen` at `0x140036736`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x140036c66`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x140036c66`

## string_xrefs

- `0x1400368b3`: `<DEFAULTUSERCONFIG>`
- `0x14003699d`: `<DEPLOYMENTCONFIG>`
- `0x140036a65`: `admin\appman\appv\client\host\service\publicapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AppV::Client::Service::AppVClientImpl::SelectPublishPackagePolicy(
        __int64 a1,
        __int64 a2,
        __int16 a3,
        BSTR *a4,
        __int64 a5,
        _DWORD *a6,
        _QWORD *a7,
        struct _SYSTEMTIME *a8,
        _QWORD *a9)
{
  volatile signed __int32 *v11; // rbx
  unsigned __int64 v12; // rsi
  UINT v13; // eax
  unsigned __int64 ClientCatalog; // rax
  __int64 v16; // rax
  volatile signed __int32 *v17; // rbx
  volatile signed __int32 *v18; // rbx
  BSTR v19; // rdx
  unsigned __int64 v20; // r8
  __int128 *v21; // rdx
  __int128 *v22; // rcx
  int v23; // ebx
  __int64 v24; // r8
  __int64 v25; // rbx
  BSTR v26; // rdx
  unsigned __int64 v27; // r8
  __int128 *v28; // rdx
  __int128 *v29; // rcx
  int v30; // ebx
  __int64 v31; // rcx
  BSTR v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rbx
  char *v35; // rax
  const char *v36; // rax
  char *v37; // rax
  const char *v38; // rax
  char *v39; // rax
  const char *v40; // rax
  char *v41; // rax
  const char *v42; // rax
  __int64 *v43; // rdx
  char *v44; // rax
  const char *v45; // rax
  char *v46; // rax
  const char *v47; // rax
  char *v48; // rax
  const char *v49; // rax
  char *v50; // rax
  const char *v51; // rax
  LPSYSTEMTIME lpSystemTime; // [rsp+38h] [rbp-71h] BYREF
  __int128 v54; // [rsp+40h] [rbp-69h] BYREF
  __int128 v55; // [rsp+50h] [rbp-59h] BYREF
  __int128 v56; // [rsp+60h] [rbp-49h]
  __int128 v57; // [rsp+70h] [rbp-39h] BYREF
  __int128 v58; // [rsp+80h] [rbp-29h]
  __int128 v59; // [rsp+90h] [rbp-19h] BYREF

  *(_QWORD *)&v59 = a2;
  *(_QWORD *)&v54 = a5;
  lpSystemTime = a8;
  *a6 = 4;
  *a7 = 0;
  v11 = (volatile signed __int32 *)a7[1];
  a7[1] = 0;
  v12 = -1;
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  *lpSystemTime = 0;
  v13 = SysStringLen(*a4);
  if ( a3 != -1 )
  {
    if ( !v13 )
    {
      lpSystemTime = 0;
      ClientCatalog = AppV::Client::Service::AppVClientImpl::GetClientCatalog((const struct AppV::Client::ClientCatalog **)&lpSystemTime);
      if ( (ClientCatalog & 0x8000000000LL) != 0 )
      {
        v54 = 0;
        v59 = 0;
        v16 = (*(__int64 (__fastcall **)(LPSYSTEMTIME, __int64, __int64, __int128 *, __int128 *))(*(_QWORD *)&lpSystemTime->wYear
                                                                                                + 96LL))(
                lpSystemTime,
                a2,
                2,
                &v54,
                &v59);
        if ( (v16 & 0x8000000000LL) != 0 )
        {
          if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v54 + 8LL))(v54) == 1 )
            *a6 = 3;
          v18 = (volatile signed __int32 *)*((_QWORD *)&v54 + 1);
          if ( *((_QWORD *)&v54 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v54 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
              if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
            }
          }
          return 0;
        }
        *a9 = v16;
        v17 = (volatile signed __int32 *)*((_QWORD *)&v54 + 1);
        if ( *((_QWORD *)&v54 + 1)
          && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v54 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
          if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        }
      }
      else
      {
        *a9 = ClientCatalog;
      }
      return 2147500037LL;
    }
    *a6 = 2;
    v19 = *a4;
    v55 = 0;
    v56 = 0;
    v20 = -1;
    do
      ++v20;
    while ( v19[v20] );
    std::wstring::_Construct<1,wchar_t const *>((char **)&v55, v19, v20);
    v57 = 0;
    v58 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v57, L"<DEFAULTUSERCONFIG>", 0x13u);
    v21 = &v55;
    if ( *((_QWORD *)&v56 + 1) > 7u )
      v21 = (__int128 *)v55;
    v22 = &v57;
    if ( *((_QWORD *)&v58 + 1) > 7u )
      v22 = (__int128 *)v57;
    v23 = _o__wcsicmp(v22, v21);
    std::wstring::~wstring((char **)&v57);
    std::wstring::~wstring((char **)&v55);
    if ( v23 )
    {
      v26 = *a4;
      v57 = 0;
      v58 = 0;
      v27 = -1;
      do
        ++v27;
      while ( v26[v27] );
      std::wstring::_Construct<1,wchar_t const *>((char **)&v57, v26, v27);
      v55 = 0;
      v56 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v55, L"<DEPLOYMENTCONFIG>", 0x12u);
      v28 = &v57;
      if ( *((_QWORD *)&v58 + 1) > 7u )
        v28 = (__int128 *)v57;
      v29 = &v55;
      if ( *((_QWORD *)&v56 + 1) > 7u )
        v29 = (__int128 *)v55;
      v30 = _o__wcsicmp(v29, v28);
      std::wstring::~wstring((char **)&v55);
      std::wstring::~wstring((char **)&v57);
      if ( !v30 )
      {
        v31 = v54;
        if ( *(_WORD *)v54 )
          return 2147942487LL;
        *a6 = 3;
        goto LABEL_81;
      }
      v32 = *a4;
      v55 = 0;
      v56 = 0;
      do
        ++v12;
      while ( v32[v12] );
      std::wstring::_Construct<1,wchar_t const *>((char **)&v55, v32, v12);
      LOBYTE(v33) = 1;
      v34 = CreatePackageUserPolicyDocumentFromFile(&v55, v33, a7);
      std::wstring::~wstring((char **)&v55);
      if ( (v34 & 0x8000000000LL) == 0 )
      {
        *a9 = v34;
        v35 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
        if ( v35 )
          v36 = v35 + 1;
        else
          v36 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
        AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v36);
        v37 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
        if ( v37 )
          v38 = v37 + 1;
        else
          v38 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
        AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v38);
        if ( (v34 & 0x2000000000LL) == 0
          && ((v39 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92)) == 0
            ? (v40 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp")
            : (v40 = v39 + 1),
              (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v40),
               (BYTE4(v34) & 0x1F) == 9)
           && ((v41 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92)) == 0
             ? (v42 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp")
             : (v42 = v41 + 1),
               AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v42),
               (_DWORD)v34 == 1)) )
        {
          if ( (byte_1400B0B81 & 0x40) == 0 )
            return 2147942487LL;
          v43 = APPV_CLIENT_Evt_PublishPackageFailedUserConfigNotFound;
        }
        else
        {
          v44 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
          if ( v44 )
            v45 = v44 + 1;
          else
            v45 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
          AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v45);
          v46 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
          if ( v46 )
            v47 = v46 + 1;
          else
            v47 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
          AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v47);
          if ( (v34 & 0x2000000000LL) != 0 )
            return 2147942487LL;
          v48 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
          v49 = v48 ? v48 + 1 : "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
          AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v49);
          if ( (BYTE4(v34) & 0x1F) != 9 )
            return 2147942487LL;
          v50 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
          v51 = v50 ? v50 + 1 : "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
          AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v51);
          if ( (_DWORD)v34 != 7 || (byte_1400B0B81 & 0x40) == 0 )
            return 2147942487LL;
          v43 = APPV_CLIENT_Evt_PublishPackageFailedUserConfigInvalid;
        }
        McTemplateU0jjz_EventWriteTransfer(v59, (_DWORD)v43, v59, v59 + 16, (__int64)*a4);
        return 2147942487LL;
      }
    }
    else
    {
      v55 = 0;
      v56 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v55, L"(App-V Default)", 0xFu);
      LOBYTE(v24) = 1;
      v25 = CreatePackageUserPolicyDocument(v59, &v55, v24, a7);
      std::wstring::~wstring((char **)&v55);
      if ( (v25 & 0x8000000000LL) == 0 )
      {
        *a9 = v25;
        return 2147549183LL;
      }
    }
    v31 = v54;
LABEL_81:
    if ( *a6 == 3 )
      return 0;
    if ( !*(_WORD *)v31 )
    {
      GetSystemTime(lpSystemTime);
      return 0;
    }
    if ( *(_WORD *)v31 == 7 )
      return VariantTimeToSystemTime(*(DOUBLE *)(v31 + 8), lpSystemTime) != 1 ? 0x80070057 : 0;
    return 2147942487LL;
  }
  if ( v13 )
    return 2147942487LL;
  *a6 = 1;
  return 0;
}

```

## disassembly

```asm
0x140036680  mov     [rsp-8+arg_0], rbx
0x140036685  push    rbp
0x140036686  push    rsi
0x140036687  push    rdi
0x140036688  push    r12
0x14003668a  push    r13
0x14003668c  push    r14
0x14003668e  push    r15
0x140036690  lea     rbp, [rsp-7]
0x140036695  sub     rsp, 0B0h
0x14003669c  mov     rax, cs:__security_cookie
0x1400366a3  xor     rax, rsp
0x1400366a6  mov     [rbp+37h+var_40], rax
0x1400366aa  mov     r13, r9
0x1400366ad  mov     [rbp+37h+var_B0], r8w
0x1400366b2  mov     rdi, rdx
0x1400366b5  mov     qword ptr [rbp+37h+var_50], rdx
0x1400366b9  mov     rax, [rbp+37h+arg_20]
0x1400366bd  mov     qword ptr [rbp+37h+var_A0], rax
0x1400366c1  mov     r14, [rbp+37h+arg_28]
0x1400366c5  mov     r15, [rbp+37h+arg_30]
0x1400366c9  mov     rbx, [rbp+37h+arg_38]
0x1400366cd  mov     [rbp+37h+lpSystemTime], rbx
0x1400366d1  mov     r12, [rbp+37h+arg_40]
0x1400366d8  mov     dword ptr [r14], 4
0x1400366df  xor     eax, eax
0x1400366e1  mov     [r15], rax
0x1400366e4  mov     rbx, [r15+8]
0x1400366e8  mov     [r15+8], rax
0x1400366ec  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400366f0  test    rbx, rbx
0x1400366f3  jz      short loc_140036728
0x1400366f5  mov     eax, esi
0x1400366f7  lock xadd [rbx+8], eax
0x1400366fc  add     eax, esi
0x1400366fe  jnz     short loc_140036728
0x140036700  mov     rax, [rbx]
0x140036703  mov     rcx, rbx
0x140036706  mov     rax, [rax]
0x140036709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003670e  mov     eax, esi
0x140036710  lock xadd [rbx+0Ch], eax
0x140036715  add     eax, esi
0x140036717  jnz     short loc_140036728
0x140036719  mov     rax, [rbx]
0x14003671c  mov     rcx, rbx
0x14003671f  mov     rax, [rax+8]
0x140036723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036728  xorps   xmm0, xmm0
0x14003672b  mov     rax, [rbp+37h+lpSystemTime]
0x14003672f  movups  xmmword ptr [rax], xmm0
0x140036732  mov     rcx, [r13+0]; pbstr
0x140036736  call    cs:__imp_SysStringLen
0x14003673c  cmp     si, [rbp+37h+var_B0]
0x140036740  jnz     short loc_140036756
0x140036742  test    eax, eax
0x140036744  jnz     loc_140036C39
0x14003674a  mov     dword ptr [r14], 1
0x140036751  jmp     loc_140036C83
0x140036756  xor     ecx, ecx
0x140036758  test    eax, eax
0x14003675a  jnz     loc_14003686D
0x140036760  mov     [rbp+37h+lpSystemTime], rcx
0x140036764  lea     rcx, [rbp+37h+lpSystemTime]; struct AppV::Client::ClientCatalog **
0x140036768  call    ?GetClientCatalog@AppVClientImpl@Service@Client@AppV@@CA_KAEAPEBVClientCatalog@34@@Z; AppV::Client::Service::AppVClientImpl::GetClientCatalog(AppV::Client::ClientCatalog const * &)
0x14003676d  bt      rax, 27h ; '''
0x140036772  jb      short loc_140036782
0x140036774  mov     [r12], rax
0x140036778  mov     eax, 80004005h
0x14003677d  jmp     loc_140036C85
0x140036782  xorps   xmm0, xmm0
0x140036785  movdqu  [rbp+37h+var_A0], xmm0
0x14003678a  movups  [rbp+37h+var_50], xmm0
0x14003678e  mov     rcx, [rbp+37h+lpSystemTime]
0x140036792  mov     rax, [rcx]
0x140036795  lea     rdx, [rbp+37h+var_50]
0x140036799  mov     [rsp+0E0h+var_C0], rdx
0x14003679e  lea     r9, [rbp+37h+var_A0]
0x1400367a2  mov     r8d, 2
0x1400367a8  mov     rdx, rdi
0x1400367ab  mov     rax, [rax+60h]
0x1400367af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400367b4  bt      rax, 27h ; '''
0x1400367b9  jb      short loc_140036800
0x1400367bb  mov     [r12], rax
0x1400367bf  mov     rbx, qword ptr [rbp+37h+var_A0+8]
0x1400367c3  test    rbx, rbx
0x1400367c6  jz      short loc_140036778
0x1400367c8  mov     eax, esi
0x1400367ca  lock xadd [rbx+8], eax
0x1400367cf  add     eax, esi
0x1400367d1  jnz     short loc_140036778
0x1400367d3  mov     rax, [rbx]
0x1400367d6  mov     rcx, rbx
0x1400367d9  mov     rax, [rax]
0x1400367dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400367e1  mov     eax, esi
0x1400367e3  lock xadd [rbx+0Ch], eax
0x1400367e8  add     eax, esi
0x1400367ea  jnz     short loc_140036778
0x1400367ec  mov     rax, [rbx]
0x1400367ef  mov     rcx, rbx
0x1400367f2  mov     rax, [rax+8]
0x1400367f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400367fb  jmp     loc_140036778
0x140036800  mov     rcx, qword ptr [rbp+37h+var_A0]
0x140036804  mov     rax, [rcx]
0x140036807  mov     rax, [rax+8]
0x14003680b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036810  mov     edi, 1
0x140036815  cmp     eax, edi
0x140036817  jnz     short loc_140036820
0x140036819  mov     dword ptr [r14], 3
0x140036820  mov     rbx, qword ptr [rbp+37h+var_A0+8]
0x140036824  test    rbx, rbx
0x140036827  jz      loc_140036C83
0x14003682d  mov     eax, esi
0x14003682f  lock xadd [rbx+8], eax
0x140036834  add     eax, esi
0x140036836  jnz     loc_140036C83
0x14003683c  mov     rax, [rbx]
0x14003683f  mov     rcx, rbx
0x140036842  mov     rax, [rax]
0x140036845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003684a  mov     eax, esi
0x14003684c  lock xadd [rbx+0Ch], eax
0x140036851  add     eax, esi
0x140036853  jnz     loc_140036C83
0x140036859  mov     rax, [rbx]
0x14003685c  mov     rcx, rbx
0x14003685f  mov     rax, [rax+8]
0x140036863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036868  jmp     loc_140036C83
0x14003686d  mov     dword ptr [r14], 2
0x140036874  mov     rdx, [r13+0]
0x140036878  xorps   xmm0, xmm0
0x14003687b  movups  [rbp+37h+var_90], xmm0
0x14003687f  xorps   xmm1, xmm1
0x140036882  movdqu  [rbp+37h+var_80], xmm1
0x140036887  mov     r8, rsi
0x14003688a  inc     r8
0x14003688d  cmp     [rdx+r8*2], cx
0x140036892  jnz     short loc_14003688A
0x140036894  lea     rcx, [rbp+37h+var_90]
0x140036898  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14003689d  nop
0x14003689e  xorps   xmm0, xmm0
0x1400368a1  movups  [rbp+37h+var_70], xmm0
0x1400368a5  xorps   xmm1, xmm1
0x1400368a8  movdqu  [rbp+37h+var_60], xmm1
0x1400368ad  mov     r8d, 13h
0x1400368b3  lea     rdx, aDefaultusercon; "<DEFAULTUSERCONFIG>"
0x1400368ba  lea     rcx, [rbp+37h+var_70]
0x1400368be  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400368c3  lea     rdx, [rbp+37h+var_90]
0x1400368c7  mov     eax, 7
0x1400368cc  cmp     qword ptr [rbp+37h+var_80+8], rax
0x1400368d0  cmova   rdx, qword ptr [rbp+37h+var_90]
0x1400368d5  lea     rcx, [rbp+37h+var_70]
0x1400368d9  cmp     qword ptr [rbp+37h+var_60+8], rax
0x1400368dd  cmova   rcx, qword ptr [rbp+37h+var_70]
0x1400368e2  call    cs:__imp__o__wcsicmp
0x1400368e8  mov     ebx, eax
0x1400368ea  lea     rcx, [rbp+37h+var_70]
0x1400368ee  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400368f3  nop
0x1400368f4  lea     rcx, [rbp+37h+var_90]
0x1400368f8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400368fd  mov     edi, 1
0x140036902  xor     ecx, ecx
0x140036904  xorps   xmm0, xmm0
0x140036907  xorps   xmm1, xmm1
0x14003690a  test    ebx, ebx
0x14003690c  jnz     short loc_140036964
0x14003690e  movups  [rbp+37h+var_90], xmm0
0x140036912  movdqu  [rbp+37h+var_80], xmm1
0x140036917  lea     r8d, [rdi+0Eh]
0x14003691b  lea     rdx, aAppVDefault; "(App-V Default)"
0x140036922  lea     rcx, [rbp+37h+var_90]
0x140036926  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14003692b  mov     r9, r15
0x14003692e  mov     r8b, dil
0x140036931  lea     rdx, [rbp+37h+var_90]
0x140036935  mov     rcx, qword ptr [rbp+37h+var_50]
0x140036939  call    cs:__imp_CreatePackageUserPolicyDocument
0x14003693f  mov     rbx, rax
0x140036942  lea     rcx, [rbp+37h+var_90]
0x140036946  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003694b  bt      rbx, 27h ; '''
0x140036950  jb      loc_140036C40
0x140036956  mov     [r12], rbx
0x14003695a  mov     eax, 8000FFFFh
0x14003695f  jmp     loc_140036C85
0x140036964  mov     rdx, [r13+0]
0x140036968  movups  [rbp+37h+var_70], xmm0
0x14003696c  movdqu  [rbp+37h+var_60], xmm1
0x140036971  mov     r8, rsi
0x140036974  inc     r8
0x140036977  cmp     [rdx+r8*2], cx
0x14003697c  jnz     short loc_140036974
0x14003697e  lea     rcx, [rbp+37h+var_70]
0x140036982  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140036987  nop
0x140036988  xorps   xmm0, xmm0
0x14003698b  movups  [rbp+37h+var_90], xmm0
0x14003698f  xorps   xmm1, xmm1
0x140036992  movdqu  [rbp+37h+var_80], xmm1
0x140036997  mov     r8d, 12h
0x14003699d  lea     rdx, aDeploymentconf; "<DEPLOYMENTCONFIG>"
0x1400369a4  lea     rcx, [rbp+37h+var_90]
0x1400369a8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400369ad  lea     rdx, [rbp+37h+var_70]
0x1400369b1  mov     eax, 7
0x1400369b6  cmp     qword ptr [rbp+37h+var_60+8], rax
0x1400369ba  cmova   rdx, qword ptr [rbp+37h+var_70]
0x1400369bf  lea     rcx, [rbp+37h+var_90]
0x1400369c3  cmp     qword ptr [rbp+37h+var_80+8], rax
0x1400369c7  cmova   rcx, qword ptr [rbp+37h+var_90]
0x1400369cc  call    cs:__imp__o__wcsicmp
0x1400369d2  mov     ebx, eax
0x1400369d4  lea     rcx, [rbp+37h+var_90]
0x1400369d8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400369dd  nop
0x1400369de  lea     rcx, [rbp+37h+var_70]
0x1400369e2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400369e7  xor     r8d, r8d
0x1400369ea  test    ebx, ebx
0x1400369ec  jnz     short loc_140036A08
0x1400369ee  mov     rcx, qword ptr [rbp+37h+var_A0]
0x1400369f2  cmp     r8w, [rcx]
0x1400369f6  jnz     loc_140036C39
0x1400369fc  mov     dword ptr [r14], 3
0x140036a03  jmp     loc_140036C47
0x140036a08  mov     rdx, [r13+0]
0x140036a0c  xorps   xmm0, xmm0
0x140036a0f  movups  [rbp+37h+var_90], xmm0
0x140036a13  xorps   xmm1, xmm1
0x140036a16  movdqu  [rbp+37h+var_80], xmm1
0x140036a1b  inc     rsi
0x140036a1e  cmp     [rdx+rsi*2], r8w
0x140036a23  jnz     short loc_140036A1B
0x140036a25  mov     r8, rsi
0x140036a28  lea     rcx, [rbp+37h+var_90]
0x140036a2c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140036a31  mov     r8, r15
0x140036a34  mov     dl, dil
0x140036a37  lea     rcx, [rbp+37h+var_90]
0x140036a3b  call    cs:__imp_CreatePackageUserPolicyDocumentFromFile
0x140036a41  mov     rbx, rax
0x140036a44  lea     rcx, [rbp+37h+var_90]
0x140036a48  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140036a4d  bt      rbx, 27h ; '''
0x140036a52  jb      loc_140036C40
0x140036a58  mov     [r12], rbx
0x140036a5c  mov     r12d, 5Ch ; '\'
0x140036a62  mov     edx, r12d; Ch
0x140036a65  lea     r15, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140036a6c  mov     rcx, r15; Str
0x140036a6f  call    cs:__imp_strrchr
0x140036a75  test    rax, rax
0x140036a78  jz      short loc_140036A7F
0x140036a7a  add     rax, rdi
0x140036a7d  jmp     short loc_140036A82
0x140036a7f  mov     rax, r15
0x140036a82  mov     rdx, rax; char *
0x140036a85  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140036a8c  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140036a91  mov     edx, r12d; Ch
0x140036a94  mov     rcx, r15; Str
0x140036a97  call    cs:__imp_strrchr
0x140036a9d  test    rax, rax
0x140036aa0  jz      short loc_140036AA7
0x140036aa2  add     rax, rdi
0x140036aa5  jmp     short loc_140036AAA
0x140036aa7  mov     rax, r15
0x140036aaa  mov     rdx, rax; char *
0x140036aad  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140036ab4  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140036ab9  mov     rax, 2000000000h
0x140036ac3  mov     rsi, rbx
0x140036ac6  and     rsi, rax
0x140036ac9  jnz     loc_140036B4F
0x140036acf  mov     edx, r12d; Ch
0x140036ad2  mov     rcx, r15; Str
0x140036ad5  call    cs:__imp_strrchr
0x140036adb  test    rax, rax
0x140036ade  jz      short loc_140036AE5
0x140036ae0  add     rax, rdi
0x140036ae3  jmp     short loc_140036AE8
0x140036ae5  mov     rax, r15
0x140036ae8  mov     rdx, rax; char *
0x140036aeb  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140036af2  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140036af7  mov     rax, rbx
0x140036afa  shr     rax, 20h
0x140036afe  and     al, 1Fh
0x140036b00  cmp     al, 9
0x140036b02  jnz     short loc_140036B4F
0x140036b04  mov     edx, r12d; Ch
0x140036b07  mov     rcx, r15; Str
  ... truncated ...
```
