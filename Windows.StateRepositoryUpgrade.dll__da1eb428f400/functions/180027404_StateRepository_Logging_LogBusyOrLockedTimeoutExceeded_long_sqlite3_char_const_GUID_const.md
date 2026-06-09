# StateRepository::Logging::LogBusyOrLockedTimeoutExceeded(long,sqlite3 *,char const *,_GUID const &)

- ea: `0x180027404`
- end: `0x1800279c1`
- name: `?LogBusyOrLockedTimeoutExceeded@Logging@StateRepository@@YAJJPEAUsqlite3@@PEBDAEBU_GUID@@@Z`
- size: `1469`
- prototype: `__int64 __fastcall(StateRepository::Logging *__hidden this, int, struct sqlite3 *, const char *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001a0e0`

## callees

- `0x180001aac`
- `0x1800028f4`
- `0x180002a18`
- `0x180003980`
- `0x1800041cc`
- `0x1800042f4`
- `0x18000a3c0`
- `0x18000c3bc`
- `0x180014ca0`
- `0x180015780`
- `0x1800157a4`
- `0x180017670`
- `0x180017c84`
- `0x180018254`
- `0x180019adc`
- `0x180024c54`
- `0x180026328`
- `0x180026440`
- `0x180026764`
- `0x180026888`
- `0x180027404`
- `0x180027e04`
- `0x180027e3c`
- `0x180028d98`
- `0x180029008`
- `0x180029a1c`

## import_xrefs

- `StateRepository.Core!sqlite3_db_filename` at `0x180027445`
- `StateRepository.Core!sqlite3_db_filename` at `0x180027445`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180027764`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180027764`

## string_xrefs

- `0x180027611`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`
- `0x1800279af`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`
- `0x18002791f`: `OpenProcess() failed on %u of %u for %hs`

## pseudocode

```c
__int64 __fastcall StateRepository::Logging::LogBusyOrLockedTimeoutExceeded(
        StateRepository::Logging *this,
        __int64 a2,
        struct sqlite3 *a3,
        const char *a4)
{
  unsigned int v4; // r13d
  const char *v7; // r15
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // ecx
  int v13; // edx
  int v14; // r8d
  int v15; // r9d
  int v16; // r10d
  int v17; // r11d
  int v18; // ebx
  int v19; // edi
  int v20; // esi
  int v21; // r9d
  int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  unsigned int v25; // edi
  int v26; // eax
  const unsigned __int16 *v27; // rdx
  DWORD v28; // eax
  void *v29; // rcx
  unsigned int v31; // esi
  __int64 i; // rdi
  DWORD v33; // r14d
  char *v34; // rax
  struct Common::FileInUseProcessInformation *v35; // r9
  int FileInUseProcessInformation; // eax
  int v37; // edx
  int v38; // ecx
  __int64 v39; // r12
  __int64 v40; // r13
  int v41; // r8d
  unsigned int v42; // r9d
  __int64 v43; // r10
  void *v44; // rcx
  int v45; // [rsp+20h] [rbp-E0h]
  char *v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+48h] [rbp-B8h]
  int v48; // [rsp+68h] [rbp-98h]
  unsigned int v49[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v50; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v51; // [rsp+90h] [rbp-70h] BYREF
  int v52; // [rsp+98h] [rbp-68h]
  struct sqlite3 *v53; // [rsp+A0h] [rbp-60h] BYREF
  const char *v54; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v55; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v56; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v57; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v58; // [rsp+C8h] [rbp-38h] BYREF
  char *v59; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE *v60; // [rsp+D8h] [rbp-28h] BYREF
  const char *v61; // [rsp+E0h] [rbp-20h] BYREF
  char *v62; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v63[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v64; // [rsp+100h] [rbp+0h]
  __int64 v65; // [rsp+108h] [rbp+8h]
  __int64 v66; // [rsp+110h] [rbp+10h]
  __int64 v67; // [rsp+118h] [rbp+18h]
  __int64 v68; // [rsp+120h] [rbp+20h]
  int v69; // [rsp+128h] [rbp+28h]
  __int64 v70; // [rsp+12Ch] [rbp+2Ch]
  int v71; // [rsp+134h] [rbp+34h]
  void *Block[2]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v73[528]; // [rsp+150h] [rbp+50h] BYREF
  char v74[256]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v75[288]; // [rsp+460h] [rbp+360h] BYREF
  __int64 v76; // [rsp+580h] [rbp+480h]
  __int64 v77; // [rsp+650h] [rbp+550h]
  __int64 v78; // [rsp+878h] [rbp+778h]
  __int64 v79; // [rsp+880h] [rbp+780h]
  unsigned int v80; // [rsp+888h] [rbp+788h]
  unsigned __int16 *v81; // [rsp+890h] [rbp+790h]
  unsigned int dwProcessId[100]; // [rsp+AB0h] [rbp+9B0h] BYREF
  char v83[16]; // [rsp+C40h] [rbp+B40h] BYREF
  _BYTE v84[21]; // [rsp+C50h] [rbp+B50h] BYREF
  unsigned __int16 v85[64]; // [rsp+C70h] [rbp+B70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D48h] [rbp+C48h]

  v52 = (int)this;
  v4 = (unsigned int)this;
  v7 = (const char *)sqlite3_db_filename(a2, 0);
  memset_0(v85, 0, sizeof(v85));
  memset_0(v63, 0, 0x48u);
  v65 = 0;
  v67 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v64 = 0;
  v66 = 0;
  v68 = 0;
  StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(
    (StateRepository::ResourcePriority::AutoPriority *)v63,
    (unsigned __int16 (*)[64])v85);
  if ( Microsoft_Windows_StateRepositoryEnableBits < 0 )
    McTemplateU0dssjz_EventWriteTransfer(v9, v8, v4, (_DWORD)v7, (__int64)a3, (__int64)a4, (__int64)v85);
  if ( *(_DWORD *)qword_18004BFB0 > 2u
    && (unsigned __int8)tlgKeywordOn(qword_18004BFB0, 0x400000000000LL, qword_18004BFB0) )
  {
    v50 = 0x1000000;
    v51 = v85;
    v54 = a4;
    v53 = a3;
    *(_QWORD *)v49 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v10,
      (unsigned int)&byte_180045DB7,
      v10,
      v11,
      (__int64)v49,
      (__int64)&v53,
      (__int64)&v54,
      (__int64)&v51,
      (__int64)&v50);
  }
  v12 = *((unsigned __int8 *)a4 + 14);
  v13 = *((unsigned __int8 *)a4 + 13);
  v14 = *((unsigned __int8 *)a4 + 12);
  v15 = *((unsigned __int8 *)a4 + 11);
  v16 = *((unsigned __int8 *)a4 + 10);
  v17 = *((unsigned __int8 *)a4 + 9);
  v18 = *((unsigned __int8 *)a4 + 8);
  v19 = *((unsigned __int16 *)a4 + 3);
  v20 = *((unsigned __int16 *)a4 + 2);
  memset(v84, 0, sizeof(v84));
  v48 = *((unsigned __int8 *)a4 + 15);
  v47 = v15;
  v21 = *(_DWORD *)a4;
  *(_OWORD *)v83 = 0;
  v22 = StringCchPrintfA(
          v83,
          0x25u,
          "%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X",
          v21,
          v20,
          v19,
          v18,
          v17,
          v16,
          v47,
          v14,
          v13,
          v12,
          v48);
  if ( v22 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x15A,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
      (const char *)(unsigned int)v22,
      v45);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x15C,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
    (const char *)v4,
    (int)"Filename:%hs, SQL:%hs, TxCallerId:%hs %ls",
    v7);
  *(_OWORD *)Block = 0;
  memset_0(v73, 0, 0x208u);
  v23 = StateRepository::Utf16String::Set((StateRepository::Utf16String *)Block, v7);
  v25 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x161,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
      (const char *)(unsigned int)v23,
      (int)v46);
LABEL_14:
    v29 = Block[1];
    Block[1] = 0;
    if ( v29 )
      operator delete(v29);
    StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)v63);
    return v25;
  }
  v50 = -1;
  v26 = wil::impersonate_token_nothrow(v24, (void **)&v50);
  v25 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x165,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
      (const char *)(unsigned int)v26,
      (int)v46);
LABEL_13:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v50);
    goto LABEL_14;
  }
  memset_0(dwProcessId, 0, sizeof(dwProcessId));
  v49[0] = 0;
  v28 = Common::FileInUseByProcesses((LPCWSTR)Block[0], v27, v49, dwProcessId);
  if ( v28 )
  {
    v25 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x16B,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
            (const char *)v28,
            (unsigned int)v46);
    goto LABEL_13;
  }
  Common::FileInUseProcessInformation::FileInUseProcessInformation((Common::FileInUseProcessInformation *)v74);
  v31 = v49[0];
  for ( i = 0; (unsigned int)i < v31; i = (unsigned int)(i + 1) )
  {
    v33 = dwProcessId[i];
    v34 = (char *)OpenProcess(0x1000u, 0, v33);
    v62 = v34;
    if ( (unsigned __int64)(v34 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LODWORD(v46) = i;
      wil::details::in1diag3::Log_GetLastErrorMsg(
        retaddr,
        (void *)0x176,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
        "OpenProcess() failed on %u of %u for %hs",
        v46);
    }
    else
    {
      FileInUseProcessInformation = Common::GetFileInUseProcessInformation((Common *)v33, v34, v74, v35);
      if ( FileInUseProcessInformation < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x17B,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
          (const char *)(unsigned int)FileInUseProcessInformation,
          (int)v46);
      v39 = v77;
      v40 = v76;
      v51 = v81;
      v49[0] = v80;
      if ( (Microsoft_Windows_StateRepositoryEnableBits & 0x40) != 0 )
        McTemplateU0dsqqqzzzzzzqz_EventWriteTransfer(
          v38,
          v37,
          v52,
          (_DWORD)v7,
          v31,
          i,
          v33,
          (__int64)v75,
          (__int64)v74,
          v77,
          v76,
          v78,
          v79,
          v80,
          (__int64)v81);
      if ( *(_DWORD *)qword_18004BFB0 > 2u
        && (unsigned __int8)tlgKeywordOn(qword_18004BFB0, 0x400000000000LL, qword_18004BFB0) )
      {
        v55 = 0x1000000;
        v59 = v74;
        v56 = v43;
        v60 = v75;
        v49[0] = v42;
        v57 = v40;
        v58 = v39;
        LODWORD(v53) = v33;
        LODWORD(v54) = v31;
        LODWORD(v51) = i;
        v61 = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
          v41,
          (unsigned int)byte_180045CD9,
          v41,
          v42,
          (__int64)&v61,
          (__int64)&v51,
          (__int64)&v54,
          (__int64)&v53,
          (__int64)&v60,
          (__int64)&v59,
          (__int64)&v58,
          (__int64)&v57,
          (__int64)v49,
          (__int64)&v56,
          (__int64)&v55);
      }
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v62);
  }
  Common::FileInUseProcessInformation::~FileInUseProcessInformation((Common::FileInUseProcessInformation *)v74);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v50);
  v44 = Block[1];
  Block[1] = 0;
  if ( v44 )
    operator delete(v44);
  StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)v63);
  return 0;
}

```

## disassembly

```asm
0x180027404  push    rbp
0x180027406  push    rbx
0x180027407  push    rsi
0x180027408  push    rdi
0x180027409  push    r12
0x18002740b  push    r13
0x18002740d  push    r14
0x18002740f  push    r15
0x180027411  lea     rbp, [rsp-0C08h]
0x180027419  sub     rsp, 0D08h
0x180027420  mov     rax, cs:__security_cookie
0x180027427  xor     rax, rsp
0x18002742a  mov     [rbp+0C40h+var_50], rax
0x180027431  mov     rax, rdx
0x180027434  mov     [rbp+0C40h+var_CA8], ecx
0x180027437  mov     r13d, ecx
0x18002743a  xor     edx, edx
0x18002743c  mov     rcx, rax
0x18002743f  mov     r14, r9
0x180027442  mov     r12, r8
0x180027445  call    cs:__imp_sqlite3_db_filename
0x18002744b  xor     edx, edx; Val
0x18002744d  lea     rcx, [rbp+0C40h+var_D0]; void *
0x180027454  mov     r8d, 80h; Size
0x18002745a  mov     r15, rax
0x18002745d  call    memset_0
0x180027462  xor     edx, edx; Val
0x180027464  lea     rcx, [rbp+0C40h+var_C50]; void *
0x180027468  lea     r8d, [rdx+48h]; Size
0x18002746c  call    memset_0
0x180027471  xor     ebx, ebx
0x180027473  lea     rdx, [rbp+0C40h+var_D0]; unsigned __int16 (*)[64]
0x18002747a  xor     eax, eax
0x18002747c  mov     [rbp+0C40h+var_C38], rbx
0x180027480  mov     [rbp+0C40h+var_C28], rbx
0x180027484  lea     rcx, [rbp+0C40h+var_C50]; this
0x180027488  mov     [rbp+0C40h+var_C18], rbx
0x18002748c  mov     qword ptr [rbp+0C40h+var_C10], rbx
0x180027490  mov     byte ptr [rbp+0C40h+var_C38], bl
0x180027493  mov     dword ptr [rbp+0C40h+var_C38+4], eax
0x180027496  mov     byte ptr [rbp+0C40h+var_C28], bl
0x180027499  mov     dword ptr [rbp+0C40h+var_C28+4], eax
0x18002749c  mov     byte ptr [rbp+0C40h+var_C18], bl
0x18002749f  mov     [rbp+0C40h+var_C18+4], rax
0x1800274a3  mov     [rbp+0C40h+var_C10+4], eax
0x1800274a6  mov     [rbp+0C40h+var_C40], rbx
0x1800274aa  mov     [rbp+0C40h+var_C30], rbx
0x1800274ae  mov     [rbp+0C40h+var_C20], rbx
0x1800274b2  call    ?GetCurrentFormattedForLogging@AutoPriority@ResourcePriority@StateRepository@@QEAAXAEAY0EA@G@Z; StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(ushort (&)[64])
0x1800274b7  cmp     cs:Microsoft_Windows_StateRepositoryEnableBits, bl
0x1800274bd  jge     short loc_1800274E0
0x1800274bf  lea     rax, [rbp+0C40h+var_D0]
0x1800274c6  mov     r9, r15
0x1800274c9  mov     [rsp+0D40h+var_D10], rax
0x1800274ce  mov     r8d, r13d
0x1800274d1  mov     [rsp+0D40h+var_D18], r14
0x1800274d6  mov     [rsp+0D40h+var_D20], r12
0x1800274db  call    McTemplateU0dssjz_EventWriteTransfer
0x1800274e0  mov     r8, cs:qword_18004BFB0
0x1800274e7  mov     eax, [r8]
0x1800274ea  cmp     eax, 2
0x1800274ed  jbe     short loc_180027560
0x1800274ef  mov     rdx, 400000000000h
0x1800274f9  mov     rcx, r8
0x1800274fc  call    _tlgKeywordOn
0x180027501  test    al, al
0x180027503  jz      short loc_180027560
0x180027505  lea     rax, [rbp+0C40h+var_D0]
0x18002750c  mov     [rbp+0C40h+var_CB8], 1000000h
0x180027514  mov     [rbp+0C40h+var_CB0], rax
0x180027518  lea     rdx, byte_180045DB7
0x18002751f  lea     rax, [rbp+0C40h+var_CB8]
0x180027523  mov     [rbp+0C40h+var_C98], r14
0x180027527  mov     [rsp+0D40h+var_D00], rax
0x18002752c  mov     rcx, r8
0x18002752f  lea     rax, [rbp+0C40h+var_CB0]
0x180027533  mov     [rbp+0C40h+var_CA0], r12
0x180027537  mov     [rsp+0D40h+var_D08], rax
0x18002753c  lea     rax, [rbp+0C40h+var_C98]
0x180027540  mov     [rsp+0D40h+var_D10], rax
0x180027545  lea     rax, [rbp+0C40h+var_CA0]
0x180027549  mov     [rsp+0D40h+var_D18], rax
0x18002754e  lea     rax, [rbp+0C40h+var_CC0]
0x180027552  mov     [rsp+0D40h+var_D20], rax
0x180027557  mov     qword ptr [rbp+0C40h+var_CC0], r15
0x18002755b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180027560  movzx   ecx, byte ptr [r14+0Eh]
0x180027565  xorps   xmm0, xmm0
0x180027568  movzx   edx, byte ptr [r14+0Dh]
0x18002756d  xor     eax, eax
0x18002756f  movzx   r8d, byte ptr [r14+0Ch]
0x180027574  movzx   r9d, byte ptr [r14+0Bh]
0x180027579  movzx   r10d, byte ptr [r14+0Ah]
0x18002757e  movzx   r11d, byte ptr [r14+9]
0x180027583  movzx   ebx, byte ptr [r14+8]
0x180027588  movzx   edi, word ptr [r14+6]
0x18002758d  movzx   esi, word ptr [r14+4]
0x180027592  movups  xmmword ptr [rbp+0C40h+var_F0], xmm0
0x180027599  mov     qword ptr [rbp+0C40h+var_F0+0Dh], rax
0x1800275a0  movzx   eax, byte ptr [r14+0Fh]
0x1800275a5  mov     dword ptr [rsp+0D40h+var_CD8], eax
0x1800275a9  mov     dword ptr [rsp+0D40h+var_CE0], ecx
0x1800275ad  lea     rcx, [rbp+0C40h+var_100]; char *
0x1800275b4  mov     dword ptr [rsp+0D40h+var_CE8], edx
0x1800275b8  mov     edx, 25h ; '%'; unsigned __int64
0x1800275bd  mov     dword ptr [rsp+0D40h+var_CF0], r8d
0x1800275c2  lea     r8, a08x04x04x02x02; "%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02"...
0x1800275c9  mov     dword ptr [rsp+0D40h+var_CF8], r9d
0x1800275ce  mov     r9d, [r14]
0x1800275d1  mov     dword ptr [rsp+0D40h+var_D00], r10d
0x1800275d6  mov     dword ptr [rsp+0D40h+var_D08], r11d
0x1800275db  mov     dword ptr [rsp+0D40h+var_D10], ebx
0x1800275df  mov     dword ptr [rsp+0D40h+var_D18], edi
0x1800275e3  mov     dword ptr [rsp+0D40h+var_D20], esi; int
0x1800275e7  movups  xmmword ptr [rbp+0C40h+var_100], xmm0
0x1800275ee  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800275f3  mov     rcx, [rbp+0C48h]; this
0x1800275fa  test    eax, eax
0x1800275fc  js      loc_1800279AC
0x180027602  lea     rax, [rbp+0C40h+var_D0]
0x180027609  mov     r9d, r13d; char *
0x18002760c  mov     [rsp+0D40h+var_D00], rax
0x180027611  lea     rbx, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x180027618  lea     rax, [rbp+0C40h+var_100]
0x18002761f  mov     r8, rbx; unsigned int
0x180027622  mov     [rsp+0D40h+var_D08], rax
0x180027627  mov     edx, 15Ch; void *
0x18002762c  mov     [rsp+0D40h+var_D10], r12
0x180027631  lea     rax, aFilenameHsSqlH; "Filename:%hs, SQL:%hs, TxCallerId:%hs %"...
0x180027638  mov     [rsp+0D40h+var_D18], r15; char *
0x18002763d  mov     [rsp+0D40h+var_D20], rax; int
0x180027642  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027647  xorps   xmm0, xmm0
0x18002764a  lea     rcx, [rbp+0C40h+var_BF0]; void *
0x18002764e  xor     edx, edx; Val
0x180027650  movdqa  xmmword ptr [rbp+0C40h+Block], xmm0
0x180027655  mov     r8d, 208h; Size
0x18002765b  call    memset_0
0x180027660  mov     rdx, r15; char *
0x180027663  lea     rcx, [rbp+0C40h+Block]; this
0x180027667  call    ?Set@Utf16String@StateRepository@@QEAAJPEBD@Z; StateRepository::Utf16String::Set(char const *)
0x18002766c  mov     edi, eax
0x18002766e  test    eax, eax
0x180027670  jns     short loc_18002768E
0x180027672  mov     rcx, [rbp+0C48h]; this
0x180027679  mov     r9d, eax; char *
0x18002767c  mov     r8, rbx; unsigned int
0x18002767f  mov     edx, 161h; void *
0x180027684  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027689  jmp     loc_180027713
0x18002768e  lea     rdx, [rbp+0C40h+var_CB8]
0x180027692  mov     [rbp+0C40h+var_CB8], 0FFFFFFFFFFFFFFFFh
0x18002769a  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x18002769f  mov     edi, eax
0x1800276a1  test    eax, eax
0x1800276a3  jns     short loc_1800276BE
0x1800276a5  mov     rcx, [rbp+0C48h]; this
0x1800276ac  mov     r9d, eax; char *
0x1800276af  mov     r8, rbx; unsigned int
0x1800276b2  mov     edx, 165h; void *
0x1800276b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800276bc  jmp     short loc_18002770A
0x1800276be  xor     edx, edx; Val
0x1800276c0  lea     rcx, [rbp+0C40h+dwProcessId]; void *
0x1800276c7  mov     r8d, 190h; Size
0x1800276cd  call    memset_0
0x1800276d2  mov     rcx, [rbp+0C40h+Block]; lpFileName
0x1800276d6  lea     r9, [rbp+0C40h+dwProcessId]; unsigned int *
0x1800276dd  lea     r8, [rbp+0C40h+var_CC0]; unsigned int
0x1800276e1  mov     [rbp+0C40h+var_CC0], 0
0x1800276e8  call    ?FileInUseByProcesses@Common@@YAJPEBGIPEAIPEAK@Z; Common::FileInUseByProcesses(ushort const *,uint,uint *,ulong *)
0x1800276ed  test    eax, eax
0x1800276ef  jz      short loc_180027739
0x1800276f1  mov     rcx, [rbp+0C48h]; this
0x1800276f8  mov     r9d, eax; char *
0x1800276fb  mov     r8, rbx; unsigned int
0x1800276fe  mov     edx, 16Bh; void *
0x180027703  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180027708  mov     edi, eax
0x18002770a  lea     rcx, [rbp+0C40h+var_CB8]
0x18002770e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180027713  mov     rcx, [rbp+0C40h+Block+8]; Block
0x180027717  mov     [rbp+0C40h+Block+8], 0
0x18002771f  test    rcx, rcx
0x180027722  jz      short loc_180027729
0x180027724  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027729  lea     rcx, [rbp+0C40h+var_C50]; this
0x18002772d  call    ??1AutoPriority@ResourcePriority@StateRepository@@QEAA@XZ; StateRepository::ResourcePriority::AutoPriority::~AutoPriority(void)
0x180027732  mov     eax, edi
0x180027734  jmp     loc_180027989
0x180027739  lea     rcx, [rbp+0C40h+var_9E0]; this
0x180027740  call    ??0FileInUseProcessInformation@Common@@QEAA@XZ; Common::FileInUseProcessInformation::FileInUseProcessInformation(void)
0x180027745  mov     esi, [rbp+0C40h+var_CC0]
0x180027748  xor     edi, edi
0x18002774a  test    esi, esi
0x18002774c  jz      loc_180027953
0x180027752  mov     r14d, [rbp+rdi*4+0C40h+dwProcessId]
0x18002775a  xor     edx, edx; bInheritHandle
0x18002775c  mov     r8d, r14d; dwProcessId
0x18002775f  mov     ecx, 1000h; dwDesiredAccess
0x180027764  call    cs:__imp_OpenProcess
0x18002776a  mov     [rbp+0C40h+var_C58], rax
0x18002776e  lea     rcx, [rax-1]
0x180027772  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180027776  ja      loc_180027918
0x18002777c  lea     r8, [rbp+0C40h+var_9E0]; void *
0x180027783  mov     rdx, rax; unsigned int
0x180027786  mov     ecx, r14d; this
0x180027789  call    ?GetFileInUseProcessInformation@Common@@YAJKPEAXAEAUFileInUseProcessInformation@1@@Z; Common::GetFileInUseProcessInformation(ulong,void *,Common::FileInUseProcessInformation &)
0x18002778e  test    eax, eax
0x180027790  jns     short loc_1800277A9
0x180027792  mov     rcx, [rbp+0C48h]; this
0x180027799  mov     r9d, eax; char *
0x18002779c  mov     r8, rbx; unsigned int
0x18002779f  mov     edx, 17Bh; void *
0x1800277a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800277a9  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 40h
0x1800277b0  mov     r10, [rbp+0C40h+var_4B0]
0x1800277b7  mov     r9d, [rbp+0C40h+var_4B8]
0x1800277be  mov     r12, [rbp+0C40h+var_6F0]
0x1800277c5  mov     r13, [rbp+0C40h+var_7C0]
0x1800277cc  mov     [rbp+0C40h+var_CB0], r10
0x1800277d0  mov     [rbp+0C40h+var_CC0], r9d
0x1800277d4  jz      short loc_18002783B
0x1800277d6  mov     rax, [rbp+0C40h+var_4C0]
0x1800277dd  mov     r8d, [rbp+0C40h+var_CA8]
0x1800277e1  mov     [rsp+0D40h+var_CD0], r10
0x1800277e6  mov     dword ptr [rsp+0D40h+var_CD8], r9d
0x1800277eb  mov     r9, r15
0x1800277ee  mov     [rsp+0D40h+var_CE0], rax
0x1800277f3  mov     rax, [rbp+0C40h+var_4C8]
0x1800277fa  mov     [rsp+0D40h+var_CE8], rax
0x1800277ff  lea     rax, [rbp+0C40h+var_9E0]
0x180027806  mov     [rsp+0D40h+var_CF0], r13
0x18002780b  mov     [rsp+0D40h+var_CF8], r12
0x180027810  mov     [rsp+0D40h+var_D00], rax
0x180027815  lea     rax, [rbp+0C40h+var_8E0]
0x18002781c  mov     [rsp+0D40h+var_D08], rax
0x180027821  mov     dword ptr [rsp+0D40h+var_D10], r14d
0x180027826  mov     dword ptr [rsp+0D40h+var_D18], edi
0x18002782a  mov     dword ptr [rsp+0D40h+var_D20], esi
0x18002782e  call    McTemplateU0dsqqqzzzzzzqz_EventWriteTransfer
0x180027833  mov     r9d, [rbp+0C40h+var_CC0]
0x180027837  mov     r10, [rbp+0C40h+var_CB0]
0x18002783b  mov     r8, cs:qword_18004BFB0
0x180027842  mov     eax, [r8]
0x180027845  cmp     eax, 2
0x180027848  jbe     loc_180027940
0x18002784e  mov     rdx, 400000000000h
0x180027858  mov     rcx, r8
0x18002785b  call    _tlgKeywordOn
0x180027860  test    al, al
0x180027862  jz      loc_180027940
0x180027868  lea     rax, [rbp+0C40h+var_9E0]
0x18002786f  mov     [rbp+0C40h+var_C90], 1000000h
0x180027877  mov     [rbp+0C40h+var_C70], rax
0x18002787b  lea     rdx, byte_180045CD9
0x180027882  lea     rax, [rbp+0C40h+var_8E0]
0x180027889  mov     [rbp+0C40h+var_C88], r10
0x18002788d  mov     [rbp+0C40h+var_C68], rax
0x180027891  mov     rcx, r8
0x180027894  lea     rax, [rbp+0C40h+var_C90]
0x180027898  mov     [rbp+0C40h+var_CC0], r9d
0x18002789c  mov     [rsp+0D40h+var_CD0], rax
0x1800278a1  lea     rax, [rbp+0C40h+var_C88]
0x1800278a5  mov     [rsp+0D40h+var_CD8], rax
0x1800278aa  lea     rax, [rbp+0C40h+var_CC0]
0x1800278ae  mov     [rsp+0D40h+var_CE0], rax
0x1800278b3  lea     rax, [rbp+0C40h+var_C80]
0x1800278b7  mov     [rsp+0D40h+var_CE8], rax
0x1800278bc  lea     rax, [rbp+0C40h+var_C78]
0x1800278c0  mov     [rsp+0D40h+var_CF0], rax
0x1800278c5  lea     rax, [rbp+0C40h+var_C70]
0x1800278c9  mov     [rsp+0D40h+var_CF8], rax
0x1800278ce  lea     rax, [rbp+0C40h+var_C68]
0x1800278d2  mov     [rsp+0D40h+var_D00], rax
0x1800278d7  lea     rax, [rbp+0C40h+var_CA0]
0x1800278db  mov     [rsp+0D40h+var_D08], rax
0x1800278e0  lea     rax, [rbp+0C40h+var_C98]
0x1800278e4  mov     [rsp+0D40h+var_D10], rax
0x1800278e9  lea     rax, [rbp+0C40h+var_CB0]
0x1800278ed  mov     [rsp+0D40h+var_D18], rax
0x1800278f2  lea     rax, [rbp+0C40h+var_C60]
0x1800278f6  mov     [rsp+0D40h+var_D20], rax
0x1800278fb  mov     [rbp+0C40h+var_C80], r13
0x1800278ff  mov     [rbp+0C40h+var_C78], r12
0x180027903  mov     dword ptr [rbp+0C40h+var_CA0], r14d
0x180027907  mov     dword ptr [rbp+0C40h+var_C98], esi
0x18002790a  mov     dword ptr [rbp+0C40h+var_CB0], edi
0x18002790d  mov     [rbp+0C40h+var_C60], r15
0x180027911  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapSz@G@@U3@U3@U3@U2@U3@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapSz@G@@55545AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180027916  jmp     short loc_180027940
0x180027918  mov     rcx, [rbp+0C48h]; this
0x18002791f  lea     r9, aOpenprocessFai; "OpenProcess() failed on %u of %u for %h"...
0x180027926  mov     [rsp+0D40h+var_D10], r15
0x18002792b  mov     r8, rbx; unsigned int
0x18002792e  mov     dword ptr [rsp+0D40h+var_D18], esi
0x180027932  mov     edx, 176h; void *
0x180027937  mov     dword ptr [rsp+0D40h+var_D20], edi; char *
0x18002793b  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
  ... truncated ...
```
