# CRequestServer::DoConnect(ulong,ulong &)

- ea: `0x18008ddb0`
- end: `0x18008e3d9`
- name: `?DoConnect@CRequestServer@@AEAA?AW4RequestState@@KAEAK@Z`
- size: `1577`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800728f4`

## callees

- `0x180038f08`
- `0x18006c66c`
- `0x180072768`
- `0x180073530`
- `0x1800736f8`
- `0x180073e68`
- `0x180078410`
- `0x18008a284`
- `0x18008ddb0`
- `0x18008e3e0`
- `0x18008e438`
- `0x18008e468`
- `0x18008f4c8`
- `0x1800983c0`
- `0x1800f4820`
- `0x180147190`
- `0x18017504c`
- `0x180188d90`
- `0x180189280`
- `0x18018e8cb`
- `0x1801a9604`
- `0x1801eeddc`
- `0x1801f0b3c`
- `0x180202bd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e13e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e13e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e1f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e1f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008e20b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008e20b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008e286`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008e286`
- `api-ms-win-core-namedpipe-l1-1-0!GetNamedPipeClientComputerNameW` at `0x18008e134`
- `api-ms-win-core-namedpipe-l1-1-0!GetNamedPipeClientComputerNameW` at `0x18008e134`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008e29c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008e29c`

## string_xrefs

- `0x18008e228`: `onecoreuap\base\appmodel\Search\common\include\usersidhelper.h`
- `0x1802badb1`: `onecoreuap\base\appmodel\Search\common\include\usersidhelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRequestServer::DoConnect(__int64 a1, unsigned int a2, _DWORD *a3)
{
  unsigned __int64 v3; // rbx
  char *v5; // rcx
  char *v6; // rsi
  int v7; // eax
  int v8; // eax
  char *v9; // r12
  __int64 v10; // r11
  size_t v11; // r14
  __int64 v12; // r15
  __int64 v13; // rax
  char *v14; // rax
  size_t v15; // r11
  size_t v16; // r13
  CDbProperties *v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rcx
  unsigned __int8 *BlobStartAddr; // rax
  CPMConnectIn *v21; // rcx
  __int64 v22; // r10
  unsigned __int8 *v23; // rax
  __int64 v24; // r10
  __int64 v25; // r11
  CDbProperties *v26; // rax
  struct IUnknown *v27; // rdx
  int v28; // eax
  __int64 v30; // rax
  int v31; // eax
  void **v32; // rbx
  HANDLE CurrentThread; // rax
  int v34; // eax
  int Error; // ebx
  unsigned __int64 v36; // r9
  __int64 v37; // rdx
  const char *v38; // r9
  __int64 v39; // rdx
  PDWORD ReturnLength; // [rsp+20h] [rbp-B9h]
  size_t pcchLength; // [rsp+40h] [rbp-99h] BYREF
  unsigned __int8 *v42; // [rsp+48h] [rbp-91h]
  unsigned __int8 *v43; // [rsp+50h] [rbp-89h]
  LPWSTR StringSid; // [rsp+60h] [rbp-79h] BYREF
  DWORD v45; // [rsp+68h] [rbp-71h] BYREF
  unsigned __int64 v46; // [rsp+70h] [rbp-69h]
  void *Src; // [rsp+78h] [rbp-61h]
  _DWORD *v48; // [rsp+80h] [rbp-59h]
  void *Block; // [rsp+88h] [rbp-51h]
  void *v50; // [rsp+90h] [rbp-49h]
  int v51; // [rsp+98h] [rbp-41h]
  PSID TokenInformation[10]; // [rsp+A0h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v48 = a3;
  v3 = a2;
  v5 = *(char **)(a1 + 176);
  Block = v5;
  v6 = (char *)(a1 + 624);
  if ( v5 )
    v6 = v5;
  v51 = *(_DWORD *)(a1 + 184);
  *(_QWORD *)(a1 + 176) = 0;
  *(_DWORD *)(a1 + 184) = 0;
  v50 = v5;
  if ( *(_QWORD *)(a1 + 128) || *(_QWORD *)(a1 + 104) || a2 < 0x30 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3E1,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)0xC000000DLL,
      (int)ReturnLength);
  v7 = *((_DWORD *)v6 + 4);
  if ( v7 < 258 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3E7,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)0xC0000030LL,
      (int)ReturnLength);
  *(_DWORD *)(a1 + 88) = v7;
  if ( !*((_DWORD *)v6 + 5) && (GetNamedPipeClientComputerNameW(*(HANDLE *)(a1 + 56), 0, 0) || GetLastError() != 229) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3F8,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)0xC000000DLL,
      (int)ReturnLength);
  v8 = *((_DWORD *)v6 + 5);
  *(_DWORD *)(a1 + 92) = v8;
  if ( v8 && !(unsigned int)RemoteQueryAllowed() )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x400,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)0xC00000BBLL,
      (int)ReturnLength);
  v9 = v6 + 48;
  pcchLength = 0;
  if ( v6 == (char *)-48LL
    || (v46 = v3, (v3 - 48) >> 1 > 0x7FFFFFFF)
    || StringLengthWorkerW((STRSAFE_PCNZWCH)v6 + 24, (v3 - 48) >> 1, &pcchLength) < 0 )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x408,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)0xC000000DLL,
      (int)ReturnLength);
  }
  if ( pcchLength >= 0x200 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40D,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)0xC000000DLL,
      (int)ReturnLength);
  v11 = pcchLength + 1;
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)&v9[2 * v13] );
  v14 = &v9[2 * v13 + 2];
  Src = v14;
  pcchLength = 0;
  if ( !v14 || (v15 = v10 - v11, v15 > 0x7FFFFFFF) || StringLengthWorkerW((STRSAFE_PCNZWCH)v14, v15, &pcchLength) < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x417,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)0xC000000DLL,
      (int)ReturnLength);
  if ( pcchLength >= 0x200 || v11 + pcchLength >= 0x200 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41C,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)0xC000000DLL,
      (int)ReturnLength);
  v16 = pcchLength + 1;
  XArray<wchar_t>::Init(a1 + 192, (unsigned int)v11);
  memcpy_0(*(void **)(a1 + 192), v6 + 48, (unsigned int)(2 * *(_DWORD *)(a1 + 200)));
  XArray<wchar_t>::Init(a1 + 208, (unsigned int)v16);
  memcpy_0(*(void **)(a1 + 208), Src, (unsigned int)(2 * *(_DWORD *)(a1 + 216)));
  v17 = 0;
  if ( IsCDPLEnabled() )
  {
    pcchLength = 0;
    StringSid = 0;
    v32 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&pcchLength);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, v32) || (v34 = ResultFromKnownLastError(), Error = v34, v34 >= 0) )
    {
      v45 = 0;
      if ( GetTokenInformation((HANDLE)pcchLength, TokenUser, TokenInformation, 0x44u, &v45)
        || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        if ( ConvertSidToStringSidW(TokenInformation[0], &StringSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          Error = 0;
          goto LABEL_49;
        }
        v39 = 18;
      }
      else
      {
        v39 = 16;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v39,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\usersidhelper.h",
        (const char *)(unsigned int)Error,
        (int)ReturnLength);
      v36 = (unsigned int)Error;
      v37 = 38;
    }
    else
    {
      v36 = (unsigned int)v34;
      v37 = 37;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v37,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\usersidhelper.h",
      (const char *)v36,
      (int)ReturnLength);
LABEL_49:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&pcchLength);
    if ( Error < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42A,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
        (const char *)(unsigned int)Error,
        (int)ReturnLength);
    v17 = 0;
    if ( !StringSid )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x42B,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
        v38);
    v30 = -1;
    do
      ++v30;
    while ( StringSid[v30] );
    pcchLength = (size_t)StringSid;
    v42 = (unsigned __int8 *)v30;
    v31 = DplUserValidator::Validate(*(_QWORD *)(a1 + 544), &pcchLength);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42C,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
        (const char *)(unsigned int)v31,
        (int)ReturnLength);
    do
      ++v12;
    while ( StringSid[v12] );
    std::wstring::_Assign<wchar_t>(a1 + 512, StringSid, v12);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&StringSid);
  }
  v18 = *((unsigned int *)v6 + 6);
  if ( !(_DWORD)v18
    || (v19 = *((unsigned int *)v6 + 8), !(_DWORD)v19)
    || (unsigned int)v18 > 0xFFFF
    || (unsigned int)v19 > 0xFFFF
    || ((v18 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + v19 + ((2 * (v11 + v16) + 55) & 0xFFFFFFFFFFFFFFF8uLL) > v46
    || (BlobStartAddr = CPMConnectIn::GetBlobStartAddr((CPMConnectIn *)v6), !&BlobStartAddr[v22]) )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)0xC000000DLL,
      (int)ReturnLength);
  }
  v23 = CPMConnectIn::GetBlobStartAddr(v21);
  pcchLength = (size_t)&CMemDeSerStream::`vftable';
  v42 = &v23[v24];
  v43 = &v23[v24 + v25];
  v26 = (CDbProperties *)CDbProperties::operator new((unsigned __int64)&v23[v24]);
  v46 = (unsigned __int64)v26;
  if ( v26 )
    v17 = CDbProperties::CDbProperties(v26, v27);
  v46 = (unsigned __int64)v17;
  if ( !v17 || !(unsigned int)CDbProperties::UnMarshall(v17, (struct PDeSerStream *)&pcchLength) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x444,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)0x8007000ELL,
      (int)ReturnLength);
  *(_QWORD *)(a1 + 280) = v17;
  LODWORD(ReturnLength) = *(_DWORD *)(a1 + 92);
  SearchIndexerDebug::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
    (const wchar_t *)0x44F,
    (unsigned int)L"[Proxy] connect clientver %d, remote %d, machine '%ws', user '%ws'\n",
    (const wchar_t *)*(unsigned int *)(a1 + 88),
    ReturnLength,
    v6 + 48,
    Src);
  *v48 = 40;
  *(_DWORD *)(a1 + 640) = 67840;
  CVersionStore::InitFromCurrentMachine((CVersionStore *)(a1 + 648));
  v28 = CRequestQueue::LookUpDocStore(
          *(_QWORD *)(a1 + 264),
          *(_QWORD *)(a1 + 280),
          a1 + 104,
          a1 + 320,
          a1 + 416,
          *(_QWORD *)(a1 + 56));
  if ( v28 < 0 )
    *(_DWORD *)(a1 + 628) = v28;
  else
    *(_DWORD *)(a1 + 112) = 5;
  operator delete(Block);
  return 0;
}

```

## disassembly

```asm
0x18008ddb0  mov     [rsp-8+arg_18], rbx
0x18008ddb5  push    rbp
0x18008ddb6  push    rsi
0x18008ddb7  push    rdi
0x18008ddb8  push    r12
0x18008ddba  push    r13
0x18008ddbc  push    r14
0x18008ddbe  push    r15
0x18008ddc0  lea     rbp, [rsp-27h]
0x18008ddc5  sub     rsp, 100h
0x18008ddcc  mov     rax, cs:__security_cookie
0x18008ddd3  xor     rax, rsp
0x18008ddd6  mov     [rbp+57h+var_40], rax
0x18008ddda  mov     [rbp+57h+var_B0], r8
0x18008ddde  mov     ebx, edx
0x18008dde0  mov     rdi, rcx
0x18008dde3  mov     rcx, [rcx+0B0h]
0x18008ddea  mov     [rbp+57h+Block], rcx
0x18008ddee  xor     r13d, r13d
0x18008ddf1  test    rcx, rcx
0x18008ddf4  lea     rsi, [rdi+270h]
0x18008ddfb  jz      short loc_18008DE00
0x18008ddfd  mov     rsi, rcx
0x18008de00  mov     eax, [rdi+0B8h]
0x18008de06  mov     [rbp+57h+var_98], eax
0x18008de09  mov     [rdi+0B0h], r13
0x18008de10  mov     [rdi+0B8h], r13d
0x18008de17  mov     [rbp+57h+var_A0], rcx
0x18008de1b  cmp     [rdi+80h], r13
0x18008de22  jz      short loc_18008DE40
0x18008de24  mov     rcx, [rbp+5Fh]; this
0x18008de28  mov     r9d, 0C000000Dh; char *
0x18008de2e  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18008de35  mov     edx, 3E1h; void *
0x18008de3a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008de40  cmp     [rdi+68h], r13
0x18008de44  jnz     short loc_18008DE24
0x18008de46  cmp     ebx, 30h ; '0'
0x18008de49  jb      short loc_18008DE24
0x18008de4b  mov     eax, [rsi+10h]
0x18008de4e  cmp     eax, 102h
0x18008de53  jl      loc_18008E2C3
0x18008de59  mov     [rdi+58h], eax
0x18008de5c  cmp     [rsi+14h], r13d
0x18008de60  jz      loc_18008E12B
0x18008de66  mov     eax, [rsi+14h]
0x18008de69  mov     [rdi+5Ch], eax
0x18008de6c  test    eax, eax
0x18008de6e  jnz     loc_18008E2DF
0x18008de74  lea     r12, [rsi+30h]
0x18008de78  mov     [rsp+130h+pcchLength], r13
0x18008de7d  test    r12, r12
0x18008de80  jz      loc_18008E3BD
0x18008de86  mov     [rbp+57h+var_C0], rbx
0x18008de8a  lea     r11, [rbx-30h]
0x18008de8e  shr     r11, 1
0x18008de91  cmp     r11, 7FFFFFFFh
0x18008de98  ja      loc_18008E3BD
0x18008de9e  lea     r8, [rsp+130h+pcchLength]; pcchLength
0x18008dea3  mov     rdx, r11; cchMax
0x18008dea6  mov     rcx, r12; psz
0x18008dea9  call    StringLengthWorkerW
0x18008deae  test    eax, eax
0x18008deb0  js      loc_18008E3BD
0x18008deb6  mov     r14, [rsp+130h+pcchLength]
0x18008debb  mov     ebx, 200h
0x18008dec0  cmp     r14, rbx
0x18008dec3  jnb     loc_18008E308
0x18008dec9  inc     r14
0x18008decc  or      r15, 0FFFFFFFFFFFFFFFFh
0x18008ded0  mov     rax, r15
0x18008ded3  inc     rax
0x18008ded6  cmp     [r12+rax*2], r13w
0x18008dedb  jnz     short loc_18008DED3
0x18008dedd  inc     rax
0x18008dee0  lea     rax, [r12+rax*2]
0x18008dee4  mov     [rbp+57h+Src], rax
0x18008dee8  mov     [rsp+130h+pcchLength], r13
0x18008deed  test    rax, rax
0x18008def0  jz      loc_18008E3A1
0x18008def6  sub     r11, r14
0x18008def9  cmp     r11, 7FFFFFFFh
0x18008df00  ja      loc_18008E3A1
0x18008df06  lea     r8, [rsp+130h+pcchLength]; pcchLength
0x18008df0b  mov     rdx, r11; cchMax
0x18008df0e  mov     rcx, rax; psz
0x18008df11  call    StringLengthWorkerW
0x18008df16  test    eax, eax
0x18008df18  js      loc_18008E3A1
0x18008df1e  mov     r13, [rsp+130h+pcchLength]
0x18008df23  cmp     r13, rbx
0x18008df26  jnb     loc_18008E385
0x18008df2c  lea     rax, [r14+r13]
0x18008df30  cmp     rax, rbx
0x18008df33  jnb     loc_18008E385
0x18008df39  inc     r13
0x18008df3c  lea     rbx, [rdi+0C0h]
0x18008df43  mov     edx, r14d
0x18008df46  mov     rcx, rbx
0x18008df49  call    ?Init@?$XArray@_W@@QEAAXI@Z; XArray<wchar_t>::Init(uint)
0x18008df4e  mov     eax, [rdi+0C8h]
0x18008df54  lea     r8d, [rax+rax]; Size
0x18008df58  mov     rdx, r12; Src
0x18008df5b  mov     rcx, [rbx]; void *
0x18008df5e  call    memcpy_0
0x18008df63  lea     rbx, [rdi+0D0h]
0x18008df6a  mov     edx, r13d
0x18008df6d  mov     rcx, rbx
0x18008df70  call    ?Init@?$XArray@_W@@QEAAXI@Z; XArray<wchar_t>::Init(uint)
0x18008df75  mov     eax, [rdi+0D8h]
0x18008df7b  lea     r8d, [rax+rax]; Size
0x18008df7f  mov     rdx, [rbp+57h+Src]; Src
0x18008df83  mov     rcx, [rbx]; void *
0x18008df86  call    memcpy_0
0x18008df8b  call    ?IsCDPLEnabled@@YA_NXZ; IsCDPLEnabled(void)
0x18008df90  xor     ebx, ebx
0x18008df92  test    al, al
0x18008df94  jnz     loc_18008E1E0
0x18008df9a  mov     eax, [rsi+18h]
0x18008df9d  test    eax, eax
0x18008df9f  jnz     short loc_18008DFBD
0x18008dfa1  mov     rcx, [rbp+5Fh]; this
0x18008dfa5  mov     r9d, 0C000000Dh; char *
0x18008dfab  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18008dfb2  mov     edx, 43Bh; void *
0x18008dfb7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008dfbd  mov     ecx, [rsi+20h]
0x18008dfc0  test    ecx, ecx
0x18008dfc2  jz      short loc_18008DFA1
0x18008dfc4  mov     edx, 0FFFFh
0x18008dfc9  cmp     eax, edx
0x18008dfcb  ja      short loc_18008DFA1
0x18008dfcd  cmp     ecx, edx
0x18008dfcf  ja      short loc_18008DFA1
0x18008dfd1  lea     r10, [rax+7]
0x18008dfd5  and     r10, 0FFFFFFFFFFFFFFF8h
0x18008dfd9  mov     r11d, ecx
0x18008dfdc  lea     rax, [r14+r13]
0x18008dfe0  lea     rax, ds:37h[rax*2]
0x18008dfe8  and     rax, 0FFFFFFFFFFFFFFF8h
0x18008dfec  add     rax, rcx
0x18008dfef  add     rax, r10
0x18008dff2  cmp     rax, [rbp+57h+var_C0]
0x18008dff6  ja      short loc_18008DFA1
0x18008dff8  mov     rcx, rsi; this
0x18008dffb  call    ?GetBlobStartAddr@CPMConnectIn@@QEBAPEAEXZ; CPMConnectIn::GetBlobStartAddr(void)
0x18008e000  add     rax, r10
0x18008e003  jz      short loc_18008DFA1
0x18008e005  call    ?GetBlobStartAddr@CPMConnectIn@@QEBAPEAEXZ; CPMConnectIn::GetBlobStartAddr(void)
0x18008e00a  lea     rcx, [rax+r10]; unsigned __int64
0x18008e00e  lea     rax, ??_7CMemDeSerStream@@6B@; const CMemDeSerStream::`vftable'
0x18008e015  mov     [rsp+130h+pcchLength], rax
0x18008e01a  mov     [rsp+130h+var_E8], rcx
0x18008e01f  lea     rax, [rcx+r11]
0x18008e023  mov     [rsp+130h+var_E0], rax
0x18008e028  call    ??2CDbProperties@@SAPEAX_K@Z; CDbProperties::operator new(unsigned __int64)
0x18008e02d  mov     [rbp+57h+var_C0], rax
0x18008e031  test    rax, rax
0x18008e034  jz      short loc_18008E041
0x18008e036  mov     rcx, rax; this
0x18008e039  call    ??0CDbProperties@@QEAA@PEAUIUnknown@@@Z; CDbProperties::CDbProperties(IUnknown *)
0x18008e03e  mov     rbx, rax
0x18008e041  mov     [rbp+57h+var_C0], rbx
0x18008e045  test    rbx, rbx
0x18008e048  jz      loc_18008E369
0x18008e04e  lea     rdx, [rsp+130h+pcchLength]; struct PDeSerStream *
0x18008e053  mov     rcx, rbx; this
0x18008e056  call    ?UnMarshall@CDbProperties@@QEAAHAEAVPDeSerStream@@@Z; CDbProperties::UnMarshall(PDeSerStream &)
0x18008e05b  test    eax, eax
0x18008e05d  jz      loc_18008E369
0x18008e063  mov     [rdi+118h], rbx
0x18008e06a  mov     rax, [rbp+57h+Src]
0x18008e06e  mov     [rsp+130h+var_100], rax
0x18008e073  mov     [rsp+130h+var_108], r12
0x18008e078  mov     eax, [rdi+5Ch]
0x18008e07b  mov     dword ptr [rsp+130h+ReturnLength], eax
0x18008e07f  mov     r9d, [rdi+58h]; wchar_t *
0x18008e083  lea     r8, aProxyConnectCl; "[Proxy] connect clientver %d, remote %d"...
0x18008e08a  mov     edx, 44Fh; wchar_t *
0x18008e08f  lea     rcx, aOnecoreuapBase_192; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18008e096  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18008e09b  mov     rax, [rbp+57h+var_B0]
0x18008e09f  mov     dword ptr [rax], 28h ; '('
0x18008e0a5  mov     dword ptr [rdi+280h], 10900h
0x18008e0af  lea     rcx, [rdi+288h]; this
0x18008e0b6  call    ?InitFromCurrentMachine@CVersionStore@@QEAAXXZ; CVersionStore::InitFromCurrentMachine(void)
0x18008e0bb  lea     rcx, [rdi+1A0h]
0x18008e0c2  lea     r9, [rdi+140h]
0x18008e0c9  mov     rax, [rdi+38h]
0x18008e0cd  mov     [rsp+130h+var_108], rax
0x18008e0d2  mov     [rsp+130h+ReturnLength], rcx
0x18008e0d7  lea     r8, [rdi+68h]
0x18008e0db  mov     rdx, [rdi+118h]
0x18008e0e2  mov     rcx, [rdi+108h]
0x18008e0e9  call    ?LookUpDocStore@CRequestQueue@@QEAAJPEAUIDBProperties@@PEAPEAUICiCDocStore@@AEAV?$TLMString@$0CA@$0CA@$0EAA@@@2PEAX@Z; CRequestQueue::LookUpDocStore(IDBProperties *,ICiCDocStore * *,TLMString<32,32,1024> &,TLMString<32,32,1024> &,void *)
0x18008e0ee  test    eax, eax
0x18008e0f0  js      short loc_18008E16B
0x18008e0f2  mov     dword ptr [rdi+70h], 5
0x18008e0f9  mov     rcx, [rbp+57h+Block]; Block
0x18008e0fd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008e102  xor     eax, eax
0x18008e104  mov     rcx, [rbp+57h+var_40]
0x18008e108  xor     rcx, rsp; StackCookie
0x18008e10b  call    __security_check_cookie
0x18008e110  mov     rbx, [rsp+130h+arg_18]
0x18008e118  add     rsp, 100h
0x18008e11f  pop     r15
0x18008e121  pop     r14
0x18008e123  pop     r13
0x18008e125  pop     r12
0x18008e127  pop     rdi
0x18008e128  pop     rsi
0x18008e129  pop     rbp
0x18008e12a  retn
0x18008e12b  xor     r8d, r8d; ClientComputerNameLength
0x18008e12e  xor     edx, edx; ClientComputerName
0x18008e130  mov     rcx, [rdi+38h]; Pipe
0x18008e134  call    cs:__imp_GetNamedPipeClientComputerNameW
0x18008e13a  test    eax, eax
0x18008e13c  jnz     short loc_18008E14F
0x18008e13e  call    cs:__imp_GetLastError
0x18008e144  cmp     eax, 0E5h
0x18008e149  jz      loc_18008DE66
0x18008e14f  mov     rcx, [rbp+5Fh]; this
0x18008e153  mov     r9d, 0C000000Dh; char *
0x18008e159  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18008e160  mov     edx, 3F8h; void *
0x18008e165  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008e16b  mov     [rdi+274h], eax
0x18008e171  jmp     short loc_18008E0F9
0x18008e173  inc     rax
0x18008e176  cmp     [rdx+rax*2], bx
0x18008e17a  jnz     short loc_18008E173
0x18008e17c  mov     [rsp+130h+pcchLength], rdx
0x18008e181  mov     [rsp+130h+var_E8], rax
0x18008e186  lea     rdx, [rsp+130h+pcchLength]
0x18008e18b  mov     rcx, [rdi+220h]
0x18008e192  call    ?Validate@DplUserValidator@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; DplUserValidator::Validate(std::wstring_view)
0x18008e197  mov     rcx, [rbp+5Fh]; this
0x18008e19b  test    eax, eax
0x18008e19d  js      short loc_18008E1CB
0x18008e19f  mov     rdx, [rbp+57h+StringSid]
0x18008e1a3  inc     r15
0x18008e1a6  cmp     [rdx+r15*2], bx
0x18008e1ab  jnz     short loc_18008E1A3
0x18008e1ad  lea     rcx, [rdi+200h]
0x18008e1b4  mov     r8, r15
0x18008e1b7  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18008e1bc  nop
0x18008e1bd  lea     rcx, [rbp+57h+StringSid]
0x18008e1c1  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18008e1c6  jmp     loc_18008DF9A
0x18008e1cb  mov     r9d, eax; char *
0x18008e1ce  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18008e1d5  mov     edx, 42Ch; void *
0x18008e1da  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008e1e0  mov     [rsp+130h+pcchLength], rbx
0x18008e1e5  mov     [rbp+57h+StringSid], rbx
0x18008e1e9  lea     rcx, [rsp+130h+pcchLength]
0x18008e1ee  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18008e1f3  mov     rbx, rax
0x18008e1f6  call    cs:__imp_GetCurrentThread
0x18008e1fc  mov     r9, rbx; TokenHandle
0x18008e1ff  mov     edx, 8; DesiredAccess
0x18008e204  lea     r8d, [rdx-7]; OpenAsSelf
0x18008e208  mov     rcx, rax; ThreadHandle
0x18008e20b  call    cs:__imp_OpenThreadToken
0x18008e211  test    eax, eax
0x18008e213  jnz     short loc_18008E263
0x18008e215  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18008e21a  mov     ebx, eax
0x18008e21c  test    eax, eax
0x18008e21e  jns     short loc_18008E263
0x18008e220  mov     r9d, eax; char *
0x18008e223  mov     edx, 25h ; '%'; void *
0x18008e228  lea     r8, aOnecoreuapBase_294; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18008e22f  mov     rcx, [rbp+5Fh]; this
0x18008e233  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e238  lea     rcx, [rsp+130h+pcchLength]
0x18008e23d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008e242  mov     rcx, [rbp+5Fh]; this
0x18008e246  test    ebx, ebx
0x18008e248  jns     loc_18008E344
0x18008e24e  mov     r9d, ebx; char *
0x18008e251  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18008e258  mov     edx, 42Ah; void *
0x18008e25d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008e263  mov     [rbp+57h+var_C8], 0
0x18008e26a  lea     rax, [rbp+57h+var_C8]
0x18008e26e  mov     [rsp+130h+ReturnLength], rax; int
0x18008e273  mov     r9d, 44h ; 'D'; TokenInformationLength
0x18008e279  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18008e27d  lea     edx, [r9-43h]; TokenInformationClass
0x18008e281  mov     rcx, [rsp+130h+pcchLength]; TokenHandle
0x18008e286  call    cs:__imp_GetTokenInformation
0x18008e28c  test    eax, eax
0x18008e28e  jz      loc_18008E324
0x18008e294  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18008e298  mov     rcx, [rbp+57h+TokenInformation]; Sid
0x18008e29c  call    cs:__imp_ConvertSidToStringSidW
  ... truncated ...
```
