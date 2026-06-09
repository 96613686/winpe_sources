# CertificateInfo::VerifyFileWithCatalog(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &,CertificateInfo &)

- ea: `0x18004dce0`
- end: `0x18004e108`
- name: `?VerifyFileWithCatalog@CertificateInfo@@CAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@AEAV1@@Z`
- size: `1064`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003886c`

## callees

- `0x180002520`
- `0x180002ee8`
- `0x1800030d0`
- `0x18000a444`
- `0x18000a464`
- `0x18001045c`
- `0x180014c04`
- `0x18004c820`
- `0x18004caa8`
- `0x18004cb8c`
- `0x18004d4b4`
- `0x18004dce0`
- `0x180068010`

## import_xrefs

- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18004df71`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18004df71`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x18004df07`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x18004df07`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x18004dfb5`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x18004dfb5`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18004dd9b`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18004de5c`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18004dd9b`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18004de5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dda1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dda1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ddeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004de88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004dea4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ddeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004de88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004dea4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004dd52`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004dd52`

## string_xrefs

- `0x18004dd70`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\certificateinfo.cpp`
- `0x18004ddcd`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\certificateinfo.cpp`
- `0x18004de6b`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\certificateinfo.cpp`
- `0x18004df18`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\certificateinfo.cpp`
- `0x18004df83`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\certificateinfo.cpp`
- `0x18004dfc6`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\certificateinfo.cpp`
- `0x18004e020`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\certificateinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CertificateInfo::VerifyFileWithCatalog(char *a1, __int64 a2, struct CertificateInfo *a3)
{
  char *v4; // r14
  HANDLE FileW; // rax
  const char *v6; // r9
  void *v7; // rbx
  unsigned __int64 v8; // rsi
  int LastError; // edi
  const char *v10; // r9
  __int64 v11; // rdx
  BYTE *v12; // rdi
  __int64 v13; // rdx
  char *v14; // rbx
  const char *v15; // r9
  void *v16; // rcx
  HCATINFO v17; // rax
  const char *v18; // r9
  const char *v19; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD pcbHash[2]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *pbHash[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h]
  __int128 v25; // [rsp+60h] [rbp-A0h] BYREF
  char *v26; // [rsp+70h] [rbp-90h]
  __int64 v27; // [rsp+78h] [rbp-88h]
  CATALOG_INFO psCatInfo; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v4 = a1;
  *(_OWORD *)pbHash = 0;
  v24 = 0;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(char **)a1;
  FileW = CreateFileW((LPCWSTR)a1, 0x120089u, 1u, 0, 3u, 0, 0);
  v7 = FileW;
  *(_QWORD *)&v25 = FileW;
  v8 = -1;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x100,
                  (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\certificateinfo.cpp",
                  v6);
  }
  else
  {
    pcbHash[0] = 0;
    CryptCATAdminCalcHashFromFileHandle(FileW, pcbHash, 0, 0);
    if ( GetLastError() == 122 )
    {
      if ( !pcbHash[0] )
      {
        LastError = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x108,
          (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\certificateinfo.cpp",
          (const char *)0x8000FFFFLL,
          dwCreationDisposition);
        if ( v7 )
          CloseHandle(v7);
        goto LABEL_21;
      }
      if ( (BYTE *)pcbHash[0] >= (BYTE *)(pbHash[1] - pbHash[0]) )
      {
        if ( (BYTE *)pcbHash[0] > (BYTE *)(pbHash[1] - pbHash[0]) )
        {
          if ( pcbHash[0] <= v24 - (unsigned __int64)pbHash[0] )
          {
            v12 = &pbHash[0][pcbHash[0]];
            memset_0(pbHash[1], 0, pcbHash[0] - (unsigned __int64)(pbHash[1] - pbHash[0]));
            pbHash[1] = v12;
          }
          else
          {
            std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(pbHash, pcbHash[0]);
          }
        }
      }
      else
      {
        pbHash[1] = &pbHash[0][pcbHash[0]];
      }
      if ( CryptCATAdminCalcHashFromFileHandle(v7, pcbHash, pbHash[0], 0) )
      {
        if ( v7 )
          CloseHandle(v7);
        goto LABEL_24;
      }
      v11 = 267;
    }
    else
    {
      v11 = 263;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v11,
                  (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\certificateinfo.cpp",
                  v10);
    if ( v7 )
      CloseHandle(v7);
  }
  if ( LastError < 0 )
  {
LABEL_21:
    v13 = 224;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\certificateinfo.cpp",
      (const char *)(unsigned int)LastError,
      dwCreationDisposition);
    goto LABEL_46;
  }
LABEL_24:
  memset_0(psCatInfo.wszCatalogFile, 0, sizeof(psCatInfo.wszCatalogFile));
  psCatInfo.cbStruct = 524;
  v25 = 0;
  v14 = (char *)operator new(0x18u);
  *(_QWORD *)&v25 = v14;
  *(_OWORD *)v14 = 0;
  *((_DWORD *)v14 + 2) = 1;
  *((_DWORD *)v14 + 3) = 1;
  *(_QWORD *)v14 = ___7___Ref_count_obj2_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CryptCATAdminReleaseContextNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___std__6B_;
  *((_QWORD *)v14 + 2) = 0;
  if ( !CryptCATAdminAcquireContext((HCATADMIN *)v14 + 2, 0, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11D,
                  (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\certificateinfo.cpp",
                  v15);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 + 2, 0xFFFFFFFF) != 1 )
      goto LABEL_37;
    goto LABEL_35;
  }
  *(_QWORD *)pcbHash = 0;
  if ( v14 == (char *)-16LL )
    v16 = 0;
  else
    v16 = (void *)*((_QWORD *)v14 + 2);
  v17 = CryptCATAdminEnumCatalogFromHash(
          v16,
          pbHash[0],
          LODWORD(pbHash[1]) - LODWORD(pbHash[0]),
          0,
          (HCATINFO *)pcbHash);
  if ( v17 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v14 + 2);
    *(_QWORD *)&v25 = v17;
    *((_QWORD *)&v25 + 1) = v14 + 16;
    v26 = v14;
    if ( CryptCATCatalogInfoFromContext(v17, &psCatInfo, 0) )
    {
      wistd::unique_ptr<void,wil::hcatinfo_deleter>::~unique_ptr<void,wil::hcatinfo_deleter>((__int64)&v25);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v14)(v14);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 8LL))(v14);
      }
      goto LABEL_43;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x12A,
                  (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\certificateinfo.cpp",
                  v19);
    wistd::unique_ptr<void,wil::hcatinfo_deleter>::~unique_ptr<void,wil::hcatinfo_deleter>((__int64)&v25);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x127,
                  (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\certificateinfo.cpp",
                  v18);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 + 2, 0xFFFFFFFF) == 1 )
  {
LABEL_35:
    (**(void (__fastcall ***)(void *))v14)(v14);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 8LL))(v14);
  }
LABEL_37:
  if ( LastError < 0 )
  {
    v13 = 228;
    goto LABEL_39;
  }
LABEL_43:
  v25 = 0;
  v26 = 0;
  v27 = 0;
  do
    ++v8;
  while ( psCatInfo.wszCatalogFile[v8] );
  std::wstring::_Construct<1,wchar_t const *>((char **)&v25, psCatInfo.wszCatalogFile, v8);
  LastError = CertificateInfo::PerformCatalogVerification(v4, a3);
  std::wstring::~wstring((char **)&v25);
LABEL_46:
  std::vector<unsigned char>::~vector<unsigned char>(pbHash);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18004dce0  mov     [rsp-8+arg_18], rbx
0x18004dce5  push    rbp
0x18004dce6  push    rsi
0x18004dce7  push    rdi
0x18004dce8  push    r12
0x18004dcea  push    r13
0x18004dcec  push    r14
0x18004dcee  push    r15
0x18004dcf0  lea     rbp, [rsp-1A0h]
0x18004dcf8  sub     rsp, 2A0h
0x18004dcff  mov     rax, cs:__security_cookie
0x18004dd06  xor     rax, rsp
0x18004dd09  mov     [rbp+1D0h+var_40], rax
0x18004dd10  mov     r12, r8
0x18004dd13  mov     r15, rdx
0x18004dd16  mov     r14, rcx
0x18004dd19  xor     r13d, r13d
0x18004dd1c  xorps   xmm0, xmm0
0x18004dd1f  movdqu  xmmword ptr [rsp+2D0h+pbHash], xmm0
0x18004dd25  mov     [rsp+2D0h+var_278], r13
0x18004dd2a  cmp     qword ptr [rcx+18h], 7
0x18004dd2f  jbe     short loc_18004DD34
0x18004dd31  mov     rcx, [rcx]; lpFileName
0x18004dd34  mov     [rsp+2D0h+hTemplateFile], r13; hTemplateFile
0x18004dd39  mov     [rsp+2D0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x18004dd3e  mov     [rsp+2D0h+dwCreationDisposition], 3; int
0x18004dd46  xor     r9d, r9d; lpSecurityAttributes
0x18004dd49  mov     edx, 120089h; dwDesiredAccess
0x18004dd4e  lea     r8d, [r9+1]; dwShareMode
0x18004dd52  call    cs:__imp_CreateFileW
0x18004dd58  mov     rbx, rax
0x18004dd5b  mov     qword ptr [rsp+2D0h+var_270], rax
0x18004dd60  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004dd64  cmp     rax, rsi
0x18004dd67  jnz     short loc_18004DD88
0x18004dd69  mov     rcx, [rbp+1D8h]; this
0x18004dd70  lea     r8, aOnecoreuapWind_16; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004dd77  mov     edx, 100h; void *
0x18004dd7c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004dd81  mov     edi, eax
0x18004dd83  jmp     loc_18004DE8E
0x18004dd88  mov     [rsp+2D0h+pcbHash], r13d
0x18004dd8d  xor     r9d, r9d; dwFlags
0x18004dd90  xor     r8d, r8d; pbHash
0x18004dd93  lea     rdx, [rsp+2D0h+pcbHash]; pcbHash
0x18004dd98  mov     rcx, rbx; hFile
0x18004dd9b  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x18004dda1  call    cs:__imp_GetLastError
0x18004dda7  cmp     eax, 7Ah ; 'z'
0x18004ddaa  jz      short loc_18004DDB6
0x18004ddac  mov     edx, 107h
0x18004ddb1  jmp     loc_18004DE6B
0x18004ddb6  mov     eax, [rsp+2D0h+pcbHash]
0x18004ddba  test    eax, eax
0x18004ddbc  jnz     short loc_18004DDF6
0x18004ddbe  mov     rcx, [rbp+1D8h]; this
0x18004ddc5  mov     edi, 8000FFFFh
0x18004ddca  mov     r9d, edi; char *
0x18004ddcd  lea     r8, aOnecoreuapWind_16; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004ddd4  mov     edx, 108h; void *
0x18004ddd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ddde  nop
0x18004dddf  test    rbx, rbx
0x18004dde2  jz      loc_18004DE92
0x18004dde8  mov     rcx, rbx; hObject
0x18004ddeb  call    cs:__imp_CloseHandle
0x18004ddf1  jmp     loc_18004DE92
0x18004ddf6  mov     r8, rax
0x18004ddf9  mov     r9, [rsp+2D0h+pbHash+8]
0x18004ddfe  mov     rdx, [rsp+2D0h+pbHash]
0x18004de03  mov     rcx, r9
0x18004de06  sub     rcx, rdx
0x18004de09  cmp     rax, rcx
0x18004de0c  jnb     short loc_18004DE18
0x18004de0e  add     rax, rdx
0x18004de11  mov     [rsp+2D0h+pbHash+8], rax
0x18004de16  jmp     short loc_18004DE4C
0x18004de18  jbe     short loc_18004DE4C
0x18004de1a  mov     rax, [rsp+2D0h+var_278]
0x18004de1f  sub     rax, rdx
0x18004de22  cmp     r8, rax
0x18004de25  jbe     short loc_18004DE36
0x18004de27  mov     rdx, r8
0x18004de2a  lea     rcx, [rsp+2D0h+pbHash]
0x18004de2f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18004de34  jmp     short loc_18004DE4C
0x18004de36  sub     r8, rcx; Size
0x18004de39  lea     rdi, [r8+r9]
0x18004de3d  xor     edx, edx; Val
0x18004de3f  mov     rcx, r9; void *
0x18004de42  call    memset_0
0x18004de47  mov     [rsp+2D0h+pbHash+8], rdi
0x18004de4c  xor     r9d, r9d; dwFlags
0x18004de4f  mov     r8, [rsp+2D0h+pbHash]; pbHash
0x18004de54  lea     rdx, [rsp+2D0h+pcbHash]; pcbHash
0x18004de59  mov     rcx, rbx; hFile
0x18004de5c  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x18004de62  test    eax, eax
0x18004de64  jnz     short loc_18004DE9C
0x18004de66  mov     edx, 10Bh; void *
0x18004de6b  lea     r8, aOnecoreuapWind_16; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004de72  mov     rcx, [rbp+1D8h]; this
0x18004de79  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004de7e  mov     edi, eax
0x18004de80  test    rbx, rbx
0x18004de83  jz      short loc_18004DE8E
0x18004de85  mov     rcx, rbx; hObject
0x18004de88  call    cs:__imp_CloseHandle
0x18004de8e  test    edi, edi
0x18004de90  jns     short loc_18004DEAA
0x18004de92  mov     edx, 0E0h
0x18004de97  jmp     loc_18004E020
0x18004de9c  test    rbx, rbx
0x18004de9f  jz      short loc_18004DEAA
0x18004dea1  mov     rcx, rbx; hObject
0x18004dea4  call    cs:__imp_CloseHandle
0x18004deaa  xor     edx, edx; Val
0x18004deac  mov     r8d, 208h; Size
0x18004deb2  lea     rcx, [rbp+1D0h+psCatInfo.wszCatalogFile]; void *
0x18004deb6  call    memset_0
0x18004debb  mov     [rbp+1D0h+psCatInfo.cbStruct], 20Ch
0x18004dec2  xorps   xmm0, xmm0
0x18004dec5  movdqu  [rsp+2D0h+var_270], xmm0
0x18004decb  mov     ecx, 18h; Size
0x18004ded0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004ded5  mov     rbx, rax
0x18004ded8  mov     qword ptr [rsp+2D0h+var_270], rax
0x18004dedd  xorps   xmm0, xmm0
0x18004dee0  movups  xmmword ptr [rax], xmm0
0x18004dee3  mov     eax, 1
0x18004dee8  mov     [rbx+8], eax
0x18004deeb  mov     [rbx+0Ch], eax
0x18004deee  lea     rax, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CryptCATAdminReleaseContextNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@6B@
0x18004def5  mov     [rbx], rax
0x18004def8  lea     rdi, [rbx+10h]
0x18004defc  mov     [rdi], r13
0x18004deff  xor     r8d, r8d; dwFlags
0x18004df02  xor     edx, edx; pgSubsystem
0x18004df04  mov     rcx, rdi; phCatAdmin
0x18004df07  call    cs:__imp_CryptCATAdminAcquireContext
0x18004df0d  test    eax, eax
0x18004df0f  jnz     short loc_18004DF45
0x18004df11  mov     rcx, [rbp+1D8h]; this
0x18004df18  lea     r8, aOnecoreuapWind_16; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004df1f  mov     edx, 11Dh; void *
0x18004df24  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004df29  mov     edi, eax
0x18004df2b  mov     ecx, esi
0x18004df2d  lock xadd [rbx+8], ecx
0x18004df32  add     ecx, esi
0x18004df34  jnz     loc_18004E017
0x18004df3a  mov     rcx, [rbx]
0x18004df3d  mov     rax, [rcx]
0x18004df40  jmp     loc_18004DFF5
0x18004df45  mov     qword ptr [rsp+2D0h+pcbHash], r13
0x18004df4a  mov     r8d, dword ptr [rsp+2D0h+pbHash+8]
0x18004df4f  mov     rdx, [rsp+2D0h+pbHash]; pbHash
0x18004df54  sub     r8d, edx; cbHash
0x18004df57  test    rdi, rdi
0x18004df5a  jz      short loc_18004DF61
0x18004df5c  mov     rcx, [rdi]
0x18004df5f  jmp     short loc_18004DF64
0x18004df61  mov     rcx, r13; hCatAdmin
0x18004df64  lea     rax, [rsp+2D0h+pcbHash]
0x18004df69  mov     qword ptr [rsp+2D0h+dwCreationDisposition], rax; int
0x18004df6e  xor     r9d, r9d; dwFlags
0x18004df71  call    cs:__imp_CryptCATAdminEnumCatalogFromHash
0x18004df77  test    rax, rax
0x18004df7a  jnz     short loc_18004DF98
0x18004df7c  mov     rcx, [rbp+1D8h]; this
0x18004df83  lea     r8, aOnecoreuapWind_16; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004df8a  mov     edx, 127h; void *
0x18004df8f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004df94  mov     edi, eax
0x18004df96  jmp     short loc_18004DFE4
0x18004df98  lock inc dword ptr [rbx+8]
0x18004df9c  mov     qword ptr [rsp+2D0h+var_270], rax
0x18004dfa1  mov     qword ptr [rsp+2D0h+var_270+8], rdi
0x18004dfa6  mov     [rsp+2D0h+var_260], rbx
0x18004dfab  xor     r8d, r8d; dwFlags
0x18004dfae  lea     rdx, [rbp+1D0h+psCatInfo]; psCatInfo
0x18004dfb2  mov     rcx, rax; hCatInfo
0x18004dfb5  call    cs:__imp_CryptCATCatalogInfoFromContext
0x18004dfbb  test    eax, eax
0x18004dfbd  jnz     short loc_18004E03B
0x18004dfbf  mov     rcx, [rbp+1D8h]; this
0x18004dfc6  lea     r8, aOnecoreuapWind_16; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004dfcd  mov     edx, 12Ah; void *
0x18004dfd2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004dfd7  mov     edi, eax
0x18004dfd9  lea     rcx, [rsp+2D0h+var_270]
0x18004dfde  call    ??1?$unique_ptr@XUhcatinfo_deleter@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<void,wil::hcatinfo_deleter>::~unique_ptr<void,wil::hcatinfo_deleter>(void)
0x18004dfe3  nop
0x18004dfe4  mov     eax, esi
0x18004dfe6  lock xadd [rbx+8], eax
0x18004dfeb  add     eax, esi
0x18004dfed  jnz     short loc_18004E017
0x18004dfef  mov     rax, [rbx]
0x18004dff2  mov     rax, [rax]
0x18004dff5  mov     rcx, rbx
0x18004dff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dffd  mov     eax, esi
0x18004dfff  lock xadd [rbx+0Ch], eax
0x18004e004  add     eax, esi
0x18004e006  jnz     short loc_18004E017
0x18004e008  mov     rax, [rbx]
0x18004e00b  mov     rcx, rbx
0x18004e00e  mov     rax, [rax+8]
0x18004e012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e017  test    edi, edi
0x18004e019  jns     short loc_18004E079
0x18004e01b  mov     edx, 0E4h; void *
0x18004e020  lea     r8, aOnecoreuapWind_16; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004e027  mov     r9d, edi; char *
0x18004e02a  mov     rcx, [rbp+1D8h]; this
0x18004e031  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e036  jmp     loc_18004E0D2
0x18004e03b  lea     rcx, [rsp+2D0h+var_270]
0x18004e040  call    ??1?$unique_ptr@XUhcatinfo_deleter@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<void,wil::hcatinfo_deleter>::~unique_ptr<void,wil::hcatinfo_deleter>(void)
0x18004e045  nop
0x18004e046  mov     eax, esi
0x18004e048  lock xadd [rbx+8], eax
0x18004e04d  add     eax, esi
0x18004e04f  jnz     short loc_18004E079
0x18004e051  mov     rax, [rbx]
0x18004e054  mov     rcx, rbx
0x18004e057  mov     rax, [rax]
0x18004e05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e05f  mov     eax, esi
0x18004e061  lock xadd [rbx+0Ch], eax
0x18004e066  add     eax, esi
0x18004e068  jnz     short loc_18004E079
0x18004e06a  mov     rax, [rbx]
0x18004e06d  mov     rcx, rbx
0x18004e070  mov     rax, [rax+8]
0x18004e074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e079  xorps   xmm0, xmm0
0x18004e07c  movups  [rsp+2D0h+var_270], xmm0
0x18004e081  mov     [rsp+2D0h+var_260], r13
0x18004e086  mov     [rsp+2D0h+var_258], r13
0x18004e08b  lea     rax, [rbp+1D0h+psCatInfo.wszCatalogFile]
0x18004e08f  inc     rsi
0x18004e092  cmp     [rax+rsi*2], r13w
0x18004e097  jnz     short loc_18004E08F
0x18004e099  mov     r8, rsi
0x18004e09c  lea     rdx, [rbp+1D0h+psCatInfo.wszCatalogFile]
0x18004e0a0  lea     rcx, [rsp+2D0h+var_270]
0x18004e0a5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004e0aa  nop
0x18004e0ab  mov     qword ptr [rsp+2D0h+dwCreationDisposition], r12
0x18004e0b0  mov     r9, r15
0x18004e0b3  lea     r8, [rsp+2D0h+pbHash]
0x18004e0b8  lea     rdx, [rsp+2D0h+var_270]
0x18004e0bd  mov     rcx, r14
0x18004e0c0  call    ?PerformCatalogVerification@CertificateInfo@@CAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBV?$vector@EV?$allocator@E@std@@@3@AEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@AEAV1@@Z; CertificateInfo::PerformCatalogVerification(std::wstring const &,std::wstring const &,std::vector<uchar> const &,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &,CertificateInfo &)
0x18004e0c5  mov     edi, eax
0x18004e0c7  lea     rcx, [rsp+2D0h+var_270]
0x18004e0cc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e0d1  nop
0x18004e0d2  lea     rcx, [rsp+2D0h+pbHash]
0x18004e0d7  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18004e0dc  mov     eax, edi
0x18004e0de  mov     rcx, [rbp+1D0h+var_40]
0x18004e0e5  xor     rcx, rsp; StackCookie
0x18004e0e8  call    __security_check_cookie
0x18004e0ed  mov     rbx, [rsp+2D0h+arg_18]
0x18004e0f5  add     rsp, 2A0h
0x18004e0fc  pop     r15
0x18004e0fe  pop     r14
0x18004e100  pop     r13
0x18004e102  pop     r12
0x18004e104  pop     rdi
0x18004e105  pop     rsi
0x18004e106  pop     rbp
0x18004e107  retn
```
