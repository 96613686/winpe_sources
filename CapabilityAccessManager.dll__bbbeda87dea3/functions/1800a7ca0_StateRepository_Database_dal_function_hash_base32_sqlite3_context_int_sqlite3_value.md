# StateRepository::Database::dal_function_hash_base32(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x1800a7ca0`
- end: `0x1800a7f64`
- name: `?dal_function_hash_base32@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `708`
- prototype: `void __fastcall(struct sqlite3_context *, int, struct sqlite3_value **)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180016490`
- `0x18001ab9c`
- `0x1800210d4`
- `0x1800a40c0`
- `0x1800a7ca0`
- `0x1800a9260`
- `0x1800a9d5c`
- `0x1800a9e2c`
- `0x1800a9f28`
- `0x1800aa008`
- `0x1800b8648`

## import_xrefs

- `winsqlite3!sqlite3_user_data` at `0x1800a7cbf`
- `winsqlite3!sqlite3_user_data` at `0x1800a7cbf`
- `winsqlite3!sqlite3_result_error_code` at `0x1800a7d2a`
- `winsqlite3!sqlite3_result_error_code` at `0x1800a7e85`
- `winsqlite3!sqlite3_result_error_code` at `0x1800a7d2a`
- `winsqlite3!sqlite3_result_error_code` at `0x1800a7e85`
- `winsqlite3!sqlite3_value_type` at `0x1800a7d4a`
- `winsqlite3!sqlite3_value_type` at `0x1800a7d4a`
- `winsqlite3!sqlite3_value_text16` at `0x1800a7dd9`
- `winsqlite3!sqlite3_value_text16` at `0x1800a7dd9`
- `winsqlite3!sqlite3_value_blob` at `0x1800a7d82`
- `winsqlite3!sqlite3_value_blob` at `0x1800a7d82`
- `winsqlite3!sqlite3_value_bytes` at `0x1800a7d97`
- `winsqlite3!sqlite3_value_bytes` at `0x1800a7d97`
- `winsqlite3!sqlite3_result_error16` at `0x1800a7d1f`
- `winsqlite3!sqlite3_result_error16` at `0x1800a7e7a`
- `winsqlite3!sqlite3_result_error16` at `0x1800a7eb4`
- `winsqlite3!sqlite3_result_error16` at `0x1800a7d1f`
- `winsqlite3!sqlite3_result_error16` at `0x1800a7e7a`
- `winsqlite3!sqlite3_result_error16` at `0x1800a7eb4`
- `winsqlite3!sqlite3_value_int64` at `0x1800a7dfa`
- `winsqlite3!sqlite3_value_int64` at `0x1800a7dfa`
- `winsqlite3!sqlite3_result_text16` at `0x1800a7ed0`
- `winsqlite3!sqlite3_result_text16` at `0x1800a7ed0`

## string_xrefs

- `0x1800a7cfd`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800a7dbb`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800a7e58`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800a7e92`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800a7f06`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800a7f4d`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800a7dca`: `Hasher.Update(text) failed`
- `0x1800a7ea6`: `Hasher.Update(integer) failed`
- `0x1800a7ce4`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-hasher.cpp`

## pseudocode

```c
void __fastcall StateRepository::Database::dal_function_hash_base32(
        struct sqlite3_context *a1,
        int a2,
        struct sqlite3_value **a3)
{
  StateRepository::DataType::Hasher *v6; // r14
  bool v7; // dl
  int started; // eax
  const wchar_t *v9; // r8
  const wchar_t *v10; // r9
  unsigned int v11; // edi
  __int64 v12; // rdx
  int v13; // edi
  struct sqlite3_value *v14; // rsi
  unsigned int v15; // eax
  const void *v16; // rbp
  int v17; // eax
  int v18; // esi
  __int64 v19; // rdx
  const wchar_t *v20; // rdx
  const wchar_t *v21; // rax
  int v22; // eax
  int DigestAsBase32; // eax
  unsigned int v24; // edi
  unsigned int v25; // eax
  unsigned int v26; // eax
  int v27; // r8d
  int v28; // [rsp+20h] [rbp-48h]
  int v29; // [rsp+20h] [rbp-48h]
  char *v30; // [rsp+28h] [rbp-40h]
  _QWORD v31[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v33; // [rsp+88h] [rbp+20h] BYREF

  v6 = (StateRepository::DataType::Hasher *)(sqlite3_user_data() + 96);
  StateRepository::DataType::Hasher::CreateHasher(v6, v7);
  started = Common::CryptoProvider::StartDigest(*(Common::CryptoProvider **)v6);
  v11 = started;
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-hasher.cpp",
      (const char *)(unsigned int)started,
      v28);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xE67,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)v11,
      v29);
    sqlite3_result_error16(a1, L"Hasher.Start() failed", 0xFFFFFFFFLL);
    v12 = v11;
    goto LABEL_3;
  }
  v13 = 0;
  if ( a2 <= 0 )
  {
LABEL_19:
    v31[0] = 0;
    v31[1] = 0;
    DigestAsBase32 = StateRepository::DataType::Hasher::GetDigestAsBase32(
                       v6,
                       (struct StateRepository::Text *)v31,
                       v9,
                       v10);
    v24 = DigestAsBase32;
    if ( DigestAsBase32 >= 0 )
    {
      sqlite3_result_text16(a1, v31[0], 0xFFFFFFFFLL);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xEA7,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)DigestAsBase32,
        v28);
      sqlite3_result_error16(a1, L"Hasher.GetDigestAsBase32(text) failed", 0xFFFFFFFFLL);
      sqlite3_result_error_code(a1, v24);
    }
    StateRepository::TextA::Reset((StateRepository::TextA *)v31);
    return;
  }
  while ( 1 )
  {
    v14 = a3[v13];
    v15 = sqlite3_value_type(v14);
    v9 = (const wchar_t *)v15;
    if ( v15 == 1 )
      break;
    switch ( v15 )
    {
      case 2u:
        v25 = wil::verify_hresult<long>(2147549183LL);
        LODWORD(v30) = 2;
        wil::details::in1diag3::FailFast_HrMsg(
          retaddr,
          (void *)0xE81,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
          (const char *)v25,
          (int)"hash_base32() doesn't support double (%d)",
          v30);
      case 3u:
        v21 = (const wchar_t *)sqlite3_value_text16(v14, v15 - 3, 3);
        v18 = StateRepository::DataType::Hasher::Update(v6, v21);
        if ( v18 < 0 )
        {
          v19 = 3718;
          goto LABEL_14;
        }
        break;
      case 4u:
        v16 = (const void *)sqlite3_value_blob(v14, v15 - 4, v15);
        if ( v16 )
        {
          v17 = sqlite3_value_bytes(v14);
          v18 = StateRepository::DataType::Hasher::Update(v6, v17, v16);
          if ( v18 < 0 )
          {
            v19 = 3733;
LABEL_14:
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)v19,
              (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
              (const char *)(unsigned int)v18,
              v28);
            v20 = L"Hasher.Update(text) failed";
            goto LABEL_22;
          }
        }
        break;
      case 5u:
        break;
      default:
        v26 = wil::verify_hresult<long>(2147549183LL);
        LODWORD(v30) = v27;
        wil::details::in1diag3::FailFast_HrMsg(
          retaddr,
          (void *)0xEA3,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
          (const char *)v26,
          (int)"Unknown SQLite datatype %d",
          v30);
    }
LABEL_18:
    if ( ++v13 >= a2 )
      goto LABEL_19;
  }
  v33 = sqlite3_value_int64(v14, v15 - 1, 1);
  v22 = StateRepository::DataType::Hasher::Update(v6, 8u, &v33);
  v18 = v22;
  if ( v22 >= 0 )
    goto LABEL_18;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xE77,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
    (const char *)(unsigned int)v22,
    v28);
  v20 = L"Hasher.Update(integer) failed";
LABEL_22:
  sqlite3_result_error16(a1, v20, 0xFFFFFFFFLL);
  v12 = (unsigned int)v18;
LABEL_3:
  sqlite3_result_error_code(a1, v12);
}

```

## disassembly

```asm
0x1800a7ca0  mov     [rsp+arg_0], rbx
0x1800a7ca5  mov     [rsp+arg_8], rbp
0x1800a7caa  push    rsi
0x1800a7cab  push    rdi
0x1800a7cac  push    r12
0x1800a7cae  push    r14
0x1800a7cb0  push    r15
0x1800a7cb2  sub     rsp, 40h
0x1800a7cb6  mov     r12, r8
0x1800a7cb9  mov     r15d, edx
0x1800a7cbc  mov     rbx, rcx
0x1800a7cbf  call    cs:__imp_sqlite3_user_data
0x1800a7cc5  lea     r14, [rax+60h]
0x1800a7cc9  mov     rcx, r14; this
0x1800a7ccc  call    ?CreateHasher@Hasher@DataType@StateRepository@@AEAAJ_N@Z; StateRepository::DataType::Hasher::CreateHasher(bool)
0x1800a7cd1  mov     rcx, [r14]; this
0x1800a7cd4  call    ?StartDigest@CryptoProvider@Common@@QEAAJXZ; Common::CryptoProvider::StartDigest(void)
0x1800a7cd9  mov     edi, eax
0x1800a7cdb  test    eax, eax
0x1800a7cdd  jns     short loc_1800A7D35
0x1800a7cdf  mov     rcx, [rsp+68h]; this
0x1800a7ce4  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\staterepositor"...
0x1800a7ceb  mov     r9d, eax; char *
0x1800a7cee  mov     edx, 11h; void *
0x1800a7cf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7cf8  mov     rcx, [rsp+68h]; this
0x1800a7cfd  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800a7d04  mov     r9d, edi; char *
0x1800a7d07  mov     edx, 0E67h; void *
0x1800a7d0c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a7d11  or      r8d, 0FFFFFFFFh
0x1800a7d15  lea     rdx, aHasherStartFai; "Hasher.Start() failed"
0x1800a7d1c  mov     rcx, rbx
0x1800a7d1f  call    cs:__imp_sqlite3_result_error16
0x1800a7d25  mov     edx, edi
0x1800a7d27  mov     rcx, rbx
0x1800a7d2a  call    cs:__imp_sqlite3_result_error_code
0x1800a7d30  jmp     loc_1800A7EE0
0x1800a7d35  xor     edi, edi
0x1800a7d37  test    r15d, r15d
0x1800a7d3a  jle     loc_1800A7E2E
0x1800a7d40  movsxd  rax, edi
0x1800a7d43  mov     rsi, [r12+rax*8]
0x1800a7d47  mov     rcx, rsi
0x1800a7d4a  call    cs:__imp_sqlite3_value_type
0x1800a7d50  mov     edx, eax
0x1800a7d52  mov     r8d, eax
0x1800a7d55  sub     edx, 1
0x1800a7d58  jz      loc_1800A7DF7
0x1800a7d5e  sub     edx, 1
0x1800a7d61  jz      loc_1800A7EF7
0x1800a7d67  sub     edx, 1
0x1800a7d6a  jz      short loc_1800A7DD6
0x1800a7d6c  sub     edx, 1
0x1800a7d6f  jz      short loc_1800A7D7F
0x1800a7d71  cmp     edx, 1
0x1800a7d74  jnz     loc_1800A7F2F
0x1800a7d7a  jmp     loc_1800A7E23
0x1800a7d7f  mov     rcx, rsi
0x1800a7d82  call    cs:__imp_sqlite3_value_blob
0x1800a7d88  mov     rbp, rax
0x1800a7d8b  test    rax, rax
0x1800a7d8e  jz      loc_1800A7E23
0x1800a7d94  mov     rcx, rsi
0x1800a7d97  call    cs:__imp_sqlite3_value_bytes
0x1800a7d9d  movsxd  rdx, eax; unsigned __int64
0x1800a7da0  mov     r8, rbp; void *
0x1800a7da3  mov     rcx, r14; this
0x1800a7da6  call    ?Update@Hasher@DataType@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::DataType::Hasher::Update(unsigned __int64,void const *)
0x1800a7dab  mov     esi, eax
0x1800a7dad  test    eax, eax
0x1800a7daf  jns     short loc_1800A7E23
0x1800a7db1  mov     edx, 0E95h; void *
0x1800a7db6  mov     rcx, [rsp+68h]; this
0x1800a7dbb  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800a7dc2  mov     r9d, esi; char *
0x1800a7dc5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a7dca  lea     rdx, aHasherUpdateTe; "Hasher.Update(text) failed"
0x1800a7dd1  jmp     loc_1800A7EAD
0x1800a7dd6  mov     rcx, rsi
0x1800a7dd9  call    cs:__imp_sqlite3_value_text16
0x1800a7ddf  mov     rdx, rax; wchar_t *
0x1800a7de2  mov     rcx, r14; this
0x1800a7de5  call    ?Update@Hasher@DataType@StateRepository@@QEAAJPEB_W@Z; StateRepository::DataType::Hasher::Update(wchar_t const *)
0x1800a7dea  mov     esi, eax
0x1800a7dec  test    eax, eax
0x1800a7dee  jns     short loc_1800A7E23
0x1800a7df0  mov     edx, 0E86h
0x1800a7df5  jmp     short loc_1800A7DB6
0x1800a7df7  mov     rcx, rsi
0x1800a7dfa  call    cs:__imp_sqlite3_value_int64
0x1800a7e00  lea     r8, [rsp+68h+arg_18]; void *
0x1800a7e08  mov     edx, 8; unsigned __int64
0x1800a7e0d  mov     rcx, r14; this
0x1800a7e10  mov     [rsp+68h+arg_18], rax
0x1800a7e18  call    ?Update@Hasher@DataType@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::DataType::Hasher::Update(unsigned __int64,void const *)
0x1800a7e1d  mov     esi, eax
0x1800a7e1f  test    eax, eax
0x1800a7e21  js      short loc_1800A7E8D
0x1800a7e23  inc     edi
0x1800a7e25  cmp     edi, r15d
0x1800a7e28  jl      loc_1800A7D40
0x1800a7e2e  lea     rdx, [rsp+68h+var_38]; struct StateRepository::Text *
0x1800a7e33  mov     [rsp+68h+var_38], 0
0x1800a7e3c  mov     rcx, r14; this
0x1800a7e3f  mov     [rsp+68h+var_30], 0
0x1800a7e48  call    ?GetDigestAsBase32@Hasher@DataType@StateRepository@@QEAAJAEAVText@3@PEB_W1@Z; StateRepository::DataType::Hasher::GetDigestAsBase32(StateRepository::Text &,wchar_t const *,wchar_t const *)
0x1800a7e4d  mov     edi, eax
0x1800a7e4f  test    eax, eax
0x1800a7e51  jns     short loc_1800A7EC1
0x1800a7e53  mov     rcx, [rsp+68h]; this
0x1800a7e58  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800a7e5f  mov     r9d, eax; char *
0x1800a7e62  mov     edx, 0EA7h; void *
0x1800a7e67  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a7e6c  or      r8d, 0FFFFFFFFh
0x1800a7e70  lea     rdx, aHasherGetdiges; "Hasher.GetDigestAsBase32(text) failed"
0x1800a7e77  mov     rcx, rbx
0x1800a7e7a  call    cs:__imp_sqlite3_result_error16
0x1800a7e80  mov     edx, edi
0x1800a7e82  mov     rcx, rbx
0x1800a7e85  call    cs:__imp_sqlite3_result_error_code
0x1800a7e8b  jmp     short loc_1800A7ED6
0x1800a7e8d  mov     rcx, [rsp+68h]; this
0x1800a7e92  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800a7e99  mov     r9d, esi; char *
0x1800a7e9c  mov     edx, 0E77h; void *
0x1800a7ea1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a7ea6  lea     rdx, aHasherUpdateIn; "Hasher.Update(integer) failed"
0x1800a7ead  or      r8d, 0FFFFFFFFh
0x1800a7eb1  mov     rcx, rbx
0x1800a7eb4  call    cs:__imp_sqlite3_result_error16
0x1800a7eba  mov     edx, esi
0x1800a7ebc  jmp     loc_1800A7D27
0x1800a7ec1  mov     rdx, [rsp+68h+var_38]
0x1800a7ec6  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800a7eca  or      r8d, r9d
0x1800a7ecd  mov     rcx, rbx
0x1800a7ed0  call    cs:__imp_sqlite3_result_text16
0x1800a7ed6  lea     rcx, [rsp+68h+var_38]; this
0x1800a7edb  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x1800a7ee0  mov     rbx, [rsp+68h+arg_0]
0x1800a7ee5  mov     rbp, [rsp+68h+arg_8]
0x1800a7eea  add     rsp, 40h
0x1800a7eee  pop     r15
0x1800a7ef0  pop     r14
0x1800a7ef2  pop     r12
0x1800a7ef4  pop     rdi
0x1800a7ef5  pop     rsi
0x1800a7ef6  retn
0x1800a7ef7  mov     ecx, 8000FFFFh
0x1800a7efc  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800a7f01  mov     rcx, [rsp+68h]; this
0x1800a7f06  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800a7f0d  mov     r9d, eax; char *
0x1800a7f10  mov     dword ptr [rsp+68h+var_40], 2; char *
0x1800a7f18  lea     rax, aHashBase32Does; "hash_base32() doesn't support double (%"...
0x1800a7f1f  mov     edx, 0E81h; void *
0x1800a7f24  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800a7f29  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a7f2f  mov     ecx, 8000FFFFh
0x1800a7f34  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800a7f39  mov     rcx, [rsp+68h]; this
0x1800a7f3e  mov     r9d, eax; char *
0x1800a7f41  mov     dword ptr [rsp+68h+var_40], r8d; char *
0x1800a7f46  lea     rax, aUnknownSqliteD; "Unknown SQLite datatype %d"
0x1800a7f4d  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800a7f54  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800a7f59  mov     edx, 0EA3h; void *
0x1800a7f5e  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
```
