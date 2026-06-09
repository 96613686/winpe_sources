# ADPDatabase::CreateOrUpdateDatabase(sqlite3 *)

- ea: `0x180031bdc`
- end: `0x180031f5d`
- name: `?CreateOrUpdateDatabase@ADPDatabase@@AEAAXPEAUsqlite3@@@Z`
- size: `897`
- prototype: `void __fastcall(ADPDatabase *__hidden this, struct sqlite3 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update`

## callers

- `0x180033350`

## callees

- `0x180001008`
- `0x180002250`
- `0x1800033b0`
- `0x180005290`
- `0x18000e1d0`
- `0x1800120e4`
- `0x180013830`
- `0x180024d34`
- `0x18002888c`
- `0x18002d764`
- `0x180031bdc`
- `0x1800347ec`
- `0x180034998`
- `0x180034d54`
- `0x180034e98`
- `0x1800a90e0`

## string_xrefs

- `0x180031f04`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`
- `0x180031f19`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`
- `0x180031f36`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`
- `0x180031f48`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`

## pseudocode

```c
void __fastcall ADPDatabase::CreateOrUpdateDatabase(ADPDatabase *this, struct sqlite3 *a2)
{
  const char *v4; // r9
  int v5; // eax
  char **v6; // rsi
  __int64 *v7; // r14
  __int64 v8; // rbx
  char *v9; // rdi
  _DWORD *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  char *v13; // r15
  __int64 v14; // rdi
  const char *v15; // r9
  unsigned __int64 v16; // r8
  __int128 *p_Src; // rdi
  char *v18; // rbx
  __int64 v19; // rax
  size_t v20; // rdx
  char *v21; // r9
  __int128 *v22; // rdx
  const char *v23; // r9
  const char *Size; // [rsp+20h] [rbp-89h]
  int v25; // [rsp+30h] [rbp-79h] BYREF
  struct sqlite3_stmt *v26; // [rsp+38h] [rbp-71h] BYREF
  struct sqlite3_stmt *v27; // [rsp+40h] [rbp-69h] BYREF
  struct sqlite3_stmt *v28; // [rsp+48h] [rbp-61h]
  char *v29; // [rsp+50h] [rbp-59h] BYREF
  __int128 v30; // [rsp+60h] [rbp-49h] BYREF
  size_t v31[2]; // [rsp+70h] [rbp-39h]
  __int128 Src; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int64 v33; // [rsp+90h] [rbp-19h]
  unsigned __int64 v34; // [rsp+98h] [rbp-11h]
  _BYTE v35[3]; // [rsp+B5h] [rbp+Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  unique_sqlite3_transaction::begin((__int64)&v27, (__int64)a2);
  v25 = 0;
  if ( (unsigned int)sqlite3_exec(
                       (_DWORD)a2,
                       (unsigned int)"PRAGMA user_version;",
                       (unsigned int)ADPDatabase::GetLastUserVersion_::_2_::_lambda_1_::_lambda_invoker_cdecl_,
                       (unsigned int)&v25,
                       0) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
      v4);
  v5 = *((_DWORD *)this + 34);
  if ( v5 )
  {
    if ( v5 == 1 )
    {
      v6 = &off_1800CC730;
      v7 = &qword_1800CC738;
    }
    else
    {
      if ( v5 != 2 )
        wil::details::in1diag3::FailFast_UnexpectedMsg(
          retaddr,
          (void *)0x1D6,
          (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
          "Database is invalid!",
          Size);
      v6 = &off_1800CC720;
      v7 = &qword_1800CC728;
    }
  }
  else
  {
    v6 = &off_1800CC740;
    v7 = &qword_1800CC748;
  }
  v8 = v25;
  if ( v25 )
  {
    if ( v25 != 1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1EF,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
        v4);
  }
  else
  {
    v9 = (char *)this + 104;
    if ( *((_QWORD *)v9 + 3) > 7u )
      v9 = *(char **)v9;
    v10 = (_DWORD *)*((_QWORD *)ADPTraceLoggingProvider::Instance() + 1);
    if ( *v10 > 4u )
    {
      v26 = (struct sqlite3_stmt *)v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        (__int64)v10,
        (__int64)&unk_1801005C0,
        v11,
        v12,
        (const wchar_t **)&v26);
    }
    do
    {
      if ( v7[2 * v8] )
      {
        v13 = v6[2 * v8];
        v14 = (__int64)v6[2 * v8 + 1];
        while ( v14 )
        {
          v29 = 0;
          *(_QWORD *)&v30 = v13;
          *((_QWORD *)&v30 + 1) = v14;
          sqlite3_prepare_v2_cpp(&v26, a2, &v30, &v29);
          sqlite3_run_no_result_cpp(v26);
          if ( v29 )
          {
            v13 = v29;
            v14 = -1;
            do
              ++v14;
            while ( v29[v14] );
          }
          if ( v26 )
            unique_sqlite3_stmt::release_or_terminate(v26);
        }
      }
      ++v8;
    }
    while ( !v8 );
    Src = 0;
    v33 = 0;
    v34 = 0;
    std::string::_Construct<1,char const *>(&Src, "PRAGMA user_version = %d", 24);
    v15 = v35;
    v16 = 1;
    do
    {
      *--v15 = v16 % 0xA + 48;
      v16 /= 0xAu;
    }
    while ( v16 );
    v30 = 0;
    *(_OWORD *)v31 = 0;
    if ( v15 == v35 )
    {
      *(__m128i *)v31 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v30) = 0;
    }
    else
    {
      std::string::_Construct<1,char const *>(&v30, v15, v35 - v15);
    }
    p_Src = &Src;
    if ( v34 > 0xF )
      p_Src = (__int128 *)Src;
    if ( v33 < 2
      || (v18 = (char *)p_Src + v33, v19 = _std_search_1(p_Src, (char *)p_Src + v33, "%d", 2), (char *)v19 == v18) )
    {
      v20 = -1;
    }
    else
    {
      v20 = v19 - (_QWORD)p_Src;
    }
    v21 = (char *)&v30;
    if ( v31[1] > 0xF )
      v21 = (char *)v30;
    std::string::_Replace<char>(&Src, v20, v16, v21, v31[0]);
    std::string::~string((char **)&v30);
    v22 = &Src;
    if ( v34 > 0xF )
      LODWORD(v22) = Src;
    if ( (unsigned int)sqlite3_exec((_DWORD)a2, (_DWORD)v22, 0, 0, 0) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1FB,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
        v23);
    std::string::~string((char **)&Src);
  }
  sqlite3_run_no_result_cpp(v28);
  if ( v27 )
    unique_sqlite3_stmt::release_or_terminate(v27);
  v27 = 0;
  if ( v28 )
    unique_sqlite3_stmt::release_or_terminate(v28);
  v28 = 0;
  unique_sqlite3_transaction::rollback_if_needed_or_terminate((unique_sqlite3_transaction *)&v27);
  if ( v28 )
    unique_sqlite3_stmt::release_or_terminate(v28);
  if ( v27 )
    unique_sqlite3_stmt::release_or_terminate(v27);
}

```

## disassembly

```asm
0x180031bdc  push    rbp
0x180031bde  push    rbx
0x180031bdf  push    rsi
0x180031be0  push    rdi
0x180031be1  push    r12
0x180031be3  push    r13
0x180031be5  push    r14
0x180031be7  push    r15
0x180031be9  lea     rbp, [rsp-1Fh]
0x180031bee  sub     rsp, 0C8h
0x180031bf5  mov     rax, cs:__security_cookie
0x180031bfc  xor     rax, rsp
0x180031bff  mov     [rbp+57h+var_48], rax
0x180031c03  mov     r12, rdx
0x180031c06  mov     rdi, rcx
0x180031c09  xor     r13d, r13d
0x180031c0c  lea     rcx, [rbp+57h+var_C0]
0x180031c10  call    ?begin@unique_sqlite3_transaction@@SA?AU1@PEAUsqlite3@@@Z; unique_sqlite3_transaction::begin(sqlite3 *)
0x180031c15  nop
0x180031c16  mov     [rbp+57h+var_D0], r13d
0x180031c1a  mov     rbx, [rbp+5Fh]
0x180031c1e  mov     [rsp+100h+Size], r13; char *
0x180031c23  lea     r9, [rbp+57h+var_D0]
0x180031c27  lea     r8, _ADPDatabase__GetLastUserVersion____2____lambda_1____lambda_invoker_cdecl_
0x180031c2e  lea     rdx, aPragmaUserVers; "PRAGMA user_version;"
0x180031c35  mov     rcx, r12
0x180031c38  call    sqlite3_exec
0x180031c3d  test    eax, eax
0x180031c3f  jnz     loc_180031F48
0x180031c45  mov     eax, [rdi+88h]
0x180031c4b  test    eax, eax
0x180031c4d  jnz     short loc_180031C5F
0x180031c4f  lea     rsi, off_1800CC740; "\n                CREATE TABLE \"Entity"...
0x180031c56  lea     r14, qword_1800CC748
0x180031c5d  jmp     short loc_180031C8B
0x180031c5f  cmp     eax, 1
0x180031c62  jnz     short loc_180031C74
0x180031c64  lea     rsi, off_1800CC730; "\n                CREATE TABLE \"Custom"...
0x180031c6b  lea     r14, qword_1800CC738
0x180031c72  jmp     short loc_180031C8B
0x180031c74  cmp     eax, 2
0x180031c77  jnz     loc_180031F2B
0x180031c7d  lea     rsi, off_1800CC720; "\n                CREATE TABLE \"Action"...
0x180031c84  lea     r14, qword_1800CC728
0x180031c8b  movsxd  rbx, [rbp+57h+var_D0]
0x180031c8f  cmp     rbx, 1
0x180031c93  jnb     loc_180031EFC
0x180031c99  add     rdi, 68h ; 'h'
0x180031c9d  cmp     qword ptr [rdi+18h], 7
0x180031ca2  jbe     short loc_180031CA7
0x180031ca4  mov     rdi, [rdi]
0x180031ca7  call    ?Instance@ADPTraceLoggingProvider@@KAPEAV1@XZ; ADPTraceLoggingProvider::Instance(void)
0x180031cac  mov     rcx, [rax+8]
0x180031cb0  mov     eax, [rcx]
0x180031cb2  cmp     eax, 4
0x180031cb5  jbe     short loc_180031CD0
0x180031cb7  mov     [rbp+57h+var_C8], rdi
0x180031cbb  lea     rax, [rbp+57h+var_C8]
0x180031cbf  mov     [rsp+100h+Size], rax
0x180031cc4  lea     rdx, unk_1801005C0
0x180031ccb  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180031cd0  mov     rax, rbx
0x180031cd3  add     rax, rax
0x180031cd6  cmp     [r14+rax*8], r13
0x180031cda  jz      short loc_180031D3D
0x180031cdc  mov     r15, [rsi+rax*8]
0x180031ce0  mov     rdi, [rsi+rax*8+8]
0x180031ce5  test    rdi, rdi
0x180031ce8  jz      short loc_180031D3D
0x180031cea  mov     [rbp+57h+var_B0], r13
0x180031cee  mov     qword ptr [rbp+57h+var_A0], r15
0x180031cf2  mov     qword ptr [rbp+57h+var_A0+8], rdi
0x180031cf6  lea     r9, [rbp+57h+var_B0]
0x180031cfa  lea     r8, [rbp+57h+var_A0]
0x180031cfe  mov     rdx, r12
0x180031d01  lea     rcx, [rbp+57h+var_C8]
0x180031d05  call    ?sqlite3_prepare_v2_cpp@@YA?AUunique_sqlite3_stmt@@PEAUsqlite3@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@PEAPEBD@Z; sqlite3_prepare_v2_cpp(sqlite3 *,std::string_view,char const * *)
0x180031d0a  nop
0x180031d0b  mov     rcx, [rbp+57h+var_C8]; struct sqlite3_stmt *
0x180031d0f  call    ?sqlite3_run_no_result_cpp@@YAXPEAUsqlite3_stmt@@@Z; sqlite3_run_no_result_cpp(sqlite3_stmt *)
0x180031d14  mov     rax, [rbp+57h+var_B0]
0x180031d18  test    rax, rax
0x180031d1b  jz      short loc_180031D2D
0x180031d1d  mov     r15, rax
0x180031d20  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180031d24  inc     rdi
0x180031d27  cmp     [rax+rdi], r13b
0x180031d2b  jnz     short loc_180031D24
0x180031d2d  mov     rcx, [rbp+57h+var_C8]; struct sqlite3_stmt *
0x180031d31  test    rcx, rcx
0x180031d34  jz      short loc_180031CE5
0x180031d36  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180031d3b  jmp     short loc_180031CE5
0x180031d3d  inc     rbx
0x180031d40  cmp     rbx, 1
0x180031d44  jb      short loc_180031CD0
0x180031d46  xorps   xmm0, xmm0
0x180031d49  movups  [rbp+57h+Src], xmm0
0x180031d4d  mov     [rbp+57h+var_70], r13
0x180031d51  mov     [rbp+57h+var_68], r13
0x180031d55  mov     r8d, 18h
0x180031d5b  lea     rdx, aPragmaUserVers_0; "PRAGMA user_version = %d"
0x180031d62  lea     rcx, [rbp+57h+Src]
0x180031d66  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180031d6b  nop
0x180031d6c  lea     r9, [rbp+57h+var_4B]
0x180031d70  mov     r8d, 1
0x180031d76  dec     r9
0x180031d79  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180031d83  mul     r8
0x180031d86  shr     rdx, 3
0x180031d8a  mov     al, dl
0x180031d8c  shl     al, 2
0x180031d8f  lea     ecx, [rax+rdx]
0x180031d92  add     cl, cl
0x180031d94  sub     r8b, cl
0x180031d97  add     r8b, 30h ; '0'
0x180031d9b  mov     [r9], r8b
0x180031d9e  mov     r8, rdx
0x180031da1  test    rdx, rdx
0x180031da4  jnz     short loc_180031D76
0x180031da6  xorps   xmm0, xmm0
0x180031da9  movups  [rbp+57h+var_A0], xmm0
0x180031dad  xorps   xmm1, xmm1
0x180031db0  movdqu  xmmword ptr [rbp+57h+var_90], xmm1
0x180031db5  lea     rax, [rbp+57h+var_4B]
0x180031db9  cmp     r9, rax
0x180031dbc  jnz     short loc_180031DD1
0x180031dbe  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180031dc6  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180031dcb  mov     byte ptr [rbp+57h+var_A0], r13b
0x180031dcf  jmp     short loc_180031DE5
0x180031dd1  lea     r8, [rbp+57h+var_4B]
0x180031dd5  sub     r8, r9
0x180031dd8  mov     rdx, r9
0x180031ddb  lea     rcx, [rbp+57h+var_A0]
0x180031ddf  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180031de4  nop
0x180031de5  mov     rax, [rbp+57h+var_70]
0x180031de9  lea     rdi, [rbp+57h+Src]
0x180031ded  cmp     [rbp+57h+var_68], 0Fh
0x180031df2  cmova   rdi, qword ptr [rbp+57h+Src]
0x180031df7  cmp     rax, 2
0x180031dfb  jb      short loc_180031E26
0x180031dfd  lea     rbx, [rax+rdi]
0x180031e01  mov     r9d, 2
0x180031e07  lea     r8, aD; "%d"
0x180031e0e  mov     rdx, rbx
0x180031e11  mov     rcx, rdi
0x180031e14  call    __std_search_1
0x180031e19  mov     rdx, rax
0x180031e1c  cmp     rax, rbx
0x180031e1f  jz      short loc_180031E26
0x180031e21  sub     rdx, rdi
0x180031e24  jmp     short loc_180031E2A
0x180031e26  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180031e2a  mov     rax, [rbp+57h+var_90]
0x180031e2e  lea     r9, [rbp+57h+var_A0]
0x180031e32  cmp     [rbp+57h+var_90+8], 0Fh
0x180031e37  cmova   r9, qword ptr [rbp+57h+var_A0]
0x180031e3c  mov     [rsp+100h+Size], rax; Size
0x180031e41  lea     rcx, [rbp+57h+Src]; Src
0x180031e45  call    ??$_Replace@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_K_KQEBD0@Z; std::string::_Replace<char>(unsigned __int64,unsigned __int64,char const * const,unsigned __int64)
0x180031e4a  nop
0x180031e4b  lea     rcx, [rbp+57h+var_A0]
0x180031e4f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180031e54  lea     rdx, [rbp+57h+Src]
0x180031e58  cmp     [rbp+57h+var_68], 0Fh
0x180031e5d  cmova   rdx, qword ptr [rbp+57h+Src]
0x180031e62  mov     rbx, [rbp+5Fh]
0x180031e66  mov     [rsp+100h+Size], r13
0x180031e6b  xor     r9d, r9d
0x180031e6e  xor     r8d, r8d
0x180031e71  mov     rcx, r12
0x180031e74  call    sqlite3_exec
0x180031e79  test    eax, eax
0x180031e7b  jnz     loc_180031F04
0x180031e81  lea     rcx, [rbp+57h+Src]
0x180031e85  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180031e8a  mov     rcx, [rbp+57h+var_B8]; struct sqlite3_stmt *
0x180031e8e  call    ?sqlite3_run_no_result_cpp@@YAXPEAUsqlite3_stmt@@@Z; sqlite3_run_no_result_cpp(sqlite3_stmt *)
0x180031e93  mov     rcx, [rbp+57h+var_C0]; struct sqlite3_stmt *
0x180031e97  test    rcx, rcx
0x180031e9a  jz      short loc_180031EA1
0x180031e9c  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180031ea1  mov     [rbp+57h+var_C0], r13
0x180031ea5  mov     rcx, [rbp+57h+var_B8]; struct sqlite3_stmt *
0x180031ea9  test    rcx, rcx
0x180031eac  jz      short loc_180031EB3
0x180031eae  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180031eb3  mov     [rbp+57h+var_B8], r13
0x180031eb7  lea     rcx, [rbp+57h+var_C0]; this
0x180031ebb  call    ?rollback_if_needed_or_terminate@unique_sqlite3_transaction@@AEAAXXZ; unique_sqlite3_transaction::rollback_if_needed_or_terminate(void)
0x180031ec0  mov     rcx, [rbp+57h+var_B8]; struct sqlite3_stmt *
0x180031ec4  test    rcx, rcx
0x180031ec7  jz      short loc_180031ECE
0x180031ec9  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180031ece  mov     rcx, [rbp+57h+var_C0]; struct sqlite3_stmt *
0x180031ed2  test    rcx, rcx
0x180031ed5  jz      short loc_180031EDC
0x180031ed7  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180031edc  mov     rcx, [rbp+57h+var_48]
0x180031ee0  xor     rcx, rsp; StackCookie
0x180031ee3  call    __security_check_cookie
0x180031ee8  add     rsp, 0C8h
0x180031eef  pop     r15
0x180031ef1  pop     r14
0x180031ef3  pop     r13
0x180031ef5  pop     r12
0x180031ef7  pop     rdi
0x180031ef8  pop     rsi
0x180031ef9  pop     rbx
0x180031efa  pop     rbp
0x180031efb  retn
0x180031efc  mov     rcx, [rbp+5Fh]; this
0x180031f00  jnz     short loc_180031F19
0x180031f02  jmp     short loc_180031E8A
0x180031f04  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180031f0b  mov     edx, 1FBh; void *
0x180031f10  mov     rcx, rbx; this
0x180031f13  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180031f19  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180031f20  mov     edx, 1EFh; void *
0x180031f25  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180031f2b  mov     rcx, [rbp+5Fh]; this
0x180031f2f  lea     r9, aDatabaseIsInva; "Database is invalid!"
0x180031f36  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180031f3d  mov     edx, 1D6h; void *
0x180031f42  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x180031f48  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180031f4f  mov     edx, 1B6h; void *
0x180031f54  mov     rcx, rbx; this
0x180031f57  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
