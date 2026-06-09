# StateRepository::Database::dal_function_hash_base32(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x1800fe310`
- end: `0x1800fe800`
- name: `?dal_function_hash_base32@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `1264`
- prototype: `void __fastcall(struct sqlite3_context *, int, struct sqlite3_value **)`
- caller_count: `0`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000a740`
- `0x18000a7f0`
- `0x18000a8e0`
- `0x18000a9b0`
- `0x18000aaf0`
- `0x18000b1d0`
- `0x18000c180`
- `0x18000c240`
- `0x18000d8e0`
- `0x1800e5e6c`
- `0x1800eabf4`
- `0x1800f7630`
- `0x1800f94c4`
- `0x1800fb7f0`
- `0x1800fe310`
- `0x180100fcc`
- `0x1801011ac`
- `0x18010128c`
- `0x18010272c`
- `0x1801027d0`
- `0x180109368`
- `0x18010a3bc`
- `0x18010d010`

## string_xrefs

- `0x1800fe484`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fe5d7`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fe61d`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fe721`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fe7a3`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fe7e9`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fe631`: `Hasher.Update(integer) failed`
- `0x1800fe5e6`: `Hasher.Update(text) failed`
- `0x1800fe46c`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-hasher.cpp`
- `0x1800fe70b`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-hasher.cpp`
- `0x1800fe37b`: `onecore\base\appmodel\common\cryptoprovider.cpp`
- `0x1800fe39c`: `onecore\base\appmodel\common\cryptoprovider.cpp`
- `0x1800fe453`: `onecore\base\appmodel\common\cryptoprovider.cpp`
- `0x1800fe65a`: `onecore\base\appmodel\common\cryptoprovider.cpp`

## pseudocode

```c
void __fastcall StateRepository::Database::dal_function_hash_base32(
        struct sqlite3_context *a1,
        int a2,
        struct sqlite3_value **a3)
{
  struct sqlite3_value **v3; // r14
  Common::CryptoProvider **v6; // r12
  Common::CryptoProvider *v7; // rdi
  Common::CryptoProvider *v8; // rcx
  int v9; // eax
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // r15d
  __int64 v15; // rdx
  char *v16; // r8
  const wchar_t *v17; // rdx
  int v18; // edi
  struct sqlite3_value *v19; // rbx
  int v20; // eax
  const void *v21; // r14
  int v22; // eax
  Common::CryptoProvider *v23; // rdi
  __m128i v24; // xmm6
  __int64 v25; // rcx
  int v26; // ebx
  __int64 v27; // r8
  char *v28; // r14
  const wchar_t *v29; // rax
  __int64 v30; // rdx
  int v31; // eax
  int v32; // eax
  int Chars; // ebx
  unsigned int v34; // r8d
  unsigned __int16 *v35; // rdi
  unsigned int v36; // eax
  unsigned int v37; // eax
  int v38; // r8d
  int v39; // [rsp+20h] [rbp-50h]
  int *v40; // [rsp+20h] [rbp-50h]
  char *v41; // [rsp+28h] [rbp-48h]
  int v42; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *v43[3]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  __int64 v46; // [rsp+C8h] [rbp+58h] BYREF

  v3 = a3;
  v6 = (Common::CryptoProvider **)(sqlite3_user_data() + 96);
  StateRepository::DataType::Hasher::CreateHasher(v6);
  v7 = *v6;
  v8 = *v6;
  LODWORD(v46) = 0;
  v42 = 0;
  v9 = ((__int64 (__fastcall *)(Common::CryptoProvider *, const wchar_t *, _QWORD, _QWORD))Common::BcryptLibrary::functions)(
         v8,
         L"SHA256",
         0,
         0);
  if ( v9 < 0 )
  {
    v10 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x4F,
            (unsigned int)"onecore\\base\\appmodel\\common\\cryptoprovider.cpp",
            (const char *)(unsigned int)v9,
            v39);
    v11 = v10;
    if ( v10 < 0 )
    {
      v12 = 97;
LABEL_4:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v12,
        (int)"onecore\\base\\appmodel\\common\\cryptoprovider.cpp",
        (const char *)(unsigned int)v10);
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-hasher.cpp",
        (const char *)(unsigned int)v11,
        (int)v40);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE67,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v11);
      v17 = L"Hasher.Start() failed";
      goto LABEL_16;
    }
  }
  v40 = &v42;
  v13 = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, __int64 *, __int64))xmmword_180140620)(
          *(_QWORD *)v7,
          L"ObjectLength",
          &v46,
          4);
  v14 = 124;
  if ( v13 < 0 )
  {
    v15 = 105;
    goto LABEL_14;
  }
  if ( (unsigned int)v46 > 0x2BC )
  {
    v10 = Common::ByteBuffer::SetLength((Common::CryptoProvider *)((char *)v7 + 16), v46);
    v11 = v10;
    if ( v10 < 0 )
    {
      v12 = 113;
      goto LABEL_4;
    }
    v16 = (char *)*((_QWORD *)v7 + 3);
  }
  else
  {
    v16 = (char *)v7 + 64;
  }
  LODWORD(v40) = 0;
  v13 = (*((__int64 (__fastcall **)(_QWORD, __int64, char *))&xmmword_180140620 + 1))(
          *(_QWORD *)v7,
          (__int64)v7 + 8,
          v16);
  if ( v13 < 0 )
  {
    v15 = 124;
LABEL_14:
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v15,
            (unsigned int)"onecore\\base\\appmodel\\common\\cryptoprovider.cpp",
            (const char *)(unsigned int)v13,
            (int)v40);
    if ( v11 < 0 )
      goto LABEL_15;
  }
  v18 = 0;
  if ( a2 <= 0 )
  {
LABEL_28:
    v23 = *v6;
    v24 = 0;
    v43[0] = 0;
    v43[1] = 0;
    LODWORD(v46) = 0;
    if ( !*((_DWORD *)v23 + 208) )
    {
      v25 = *(_QWORD *)v23;
      v40 = &v42;
      v42 = 0;
      v26 = ((__int64 (__fastcall *)(__int64, const wchar_t *, __int64 *, __int64))xmmword_180140620)(
              v25,
              L"HashDigestLength",
              &v46,
              4);
      if ( v26 )
        goto LABEL_42;
      v27 = (unsigned int)v46;
      if ( (unsigned int)v46 > 0x40 )
      {
        v32 = Common::ByteBuffer::SetLength((Common::CryptoProvider *)((char *)v23 + 40), v46);
        Chars = v32;
        if ( v32 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xB8,
            (int)"onecore\\base\\appmodel\\common\\cryptoprovider.cpp",
            (const char *)(unsigned int)v32);
LABEL_43:
          v14 = 113;
          goto LABEL_49;
        }
        v28 = (char *)*((_QWORD *)v23 + 6);
        v27 = (unsigned int)v46;
      }
      else
      {
        v28 = (char *)v23 + 764;
      }
      v26 = (*((__int64 (__fastcall **)(_QWORD, char *, __int64, _QWORD))&xmmword_180140630 + 1))(
              *((_QWORD *)v23 + 1),
              v28,
              v27,
              0);
      if ( v26 )
      {
LABEL_42:
        Chars = v26 | 0x10000000;
        if ( Chars < 0 )
          goto LABEL_43;
LABEL_46:
        Chars = StateRepository::Text::EnsureCapacity((StateRepository::Text *)v43, 0x35u, 0);
        if ( Chars >= 0 )
        {
          v35 = v43[0];
          LODWORD(v46) = 0;
          Chars = Common::Base32Encoding::GetChars(
                    (const unsigned __int8 *)_mm_srli_si128(v24, 8).m128i_i64[0],
                    _mm_cvtsi128_si32(v24),
                    v34,
                    v43[0],
                    (unsigned int *)&v46);
          if ( Chars >= 0 )
          {
            v35[(unsigned int)v46] = 0;
            sqlite3_result_text16(a1, v35, 0xFFFFFFFFLL);
            goto LABEL_51;
          }
          v14 = 128;
        }
LABEL_49:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-hasher.cpp",
          (const char *)(unsigned int)Chars,
          (int)v40);
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xEA7,
          (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
          (const char *)(unsigned int)Chars);
        sqlite3_result_error16(a1, L"Hasher.GetDigestAsBase32(text) failed", 0xFFFFFFFFLL);
        sqlite3_result_error_code(a1, (unsigned int)Chars);
LABEL_51:
        StateRepository::TextA::Reset((StateRepository::TextA *)v43);
        return;
      }
      *((_DWORD *)v23 + 208) = v46;
      *((_QWORD *)v23 + 105) = v28;
    }
    v24 = *((__m128i *)v23 + 52);
    goto LABEL_46;
  }
  while ( 1 )
  {
    v19 = v3[v18];
    v20 = sqlite3_value_type(v19);
    if ( v20 == 1 )
      break;
    switch ( v20 )
    {
      case 2:
        v36 = wil::verify_hresult<long>(2147549183LL);
        LODWORD(v41) = 2;
        wil::details::in1diag3::FailFast_HrMsg(
          retaddr,
          (void *)0xE81,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
          (const char *)v36,
          (int)"hash_base32() doesn't support double (%d)",
          v41);
      case 3:
        v29 = (const wchar_t *)sqlite3_value_text16le(v19);
        v11 = StateRepository::DataType::Hasher::Update((StateRepository::DataType::Hasher *)v6, v29);
        if ( v11 < 0 )
        {
          v30 = 3718;
LABEL_34:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v30,
            (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
            (const char *)(unsigned int)v11);
          v17 = L"Hasher.Update(text) failed";
          goto LABEL_16;
        }
        break;
      case 4:
        v21 = (const void *)sqlite3_value_blob(v19);
        if ( v21 )
        {
          v22 = sqlite3_value_bytes(v19);
          v11 = StateRepository::DataType::Hasher::Update((StateRepository::DataType::Hasher *)v6, v22, v21);
          if ( v11 < 0 )
          {
            v30 = 3733;
            goto LABEL_34;
          }
        }
        v3 = a3;
        break;
      case 5:
        break;
      default:
        v37 = wil::verify_hresult<long>(2147549183LL);
        LODWORD(v41) = v38;
        wil::details::in1diag3::FailFast_HrMsg(
          retaddr,
          (void *)0xEA3,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
          (const char *)v37,
          (int)"Unknown SQLite datatype %d",
          v41);
    }
LABEL_27:
    if ( ++v18 >= a2 )
      goto LABEL_28;
  }
  v46 = sqlite3_value_int64(v19);
  v31 = StateRepository::DataType::Hasher::Update((StateRepository::DataType::Hasher *)v6, 8u, &v46);
  v11 = v31;
  if ( v31 >= 0 )
    goto LABEL_27;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xE77,
    (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
    (const char *)(unsigned int)v31);
  v17 = L"Hasher.Update(integer) failed";
LABEL_16:
  sqlite3_result_error16(a1, v17, 0xFFFFFFFFLL);
  sqlite3_result_error_code(a1, (unsigned int)v11);
}

```

## disassembly

```asm
0x1800fe310  mov     [rsp-38h+arg_0], rbx
0x1800fe315  mov     [rsp-38h+arg_10], r8
0x1800fe31a  push    rbp
0x1800fe31b  push    rsi
0x1800fe31c  push    rdi
0x1800fe31d  push    r12
0x1800fe31f  push    r13
0x1800fe321  push    r14
0x1800fe323  push    r15
0x1800fe325  mov     rbp, rsp
0x1800fe328  sub     rsp, 70h
0x1800fe32c  movaps  [rsp+70h+var_10], xmm6
0x1800fe331  mov     r14, r8
0x1800fe334  mov     r13d, edx
0x1800fe337  mov     rsi, rcx
0x1800fe33a  call    sqlite3_user_data
0x1800fe33f  lea     r12, [rax+60h]
0x1800fe343  mov     rcx, r12; this
0x1800fe346  call    ?CreateHasher@Hasher@DataType@StateRepository@@AEAAJ_N@Z; StateRepository::DataType::Hasher::CreateHasher(bool)
0x1800fe34b  mov     rdi, [r12]
0x1800fe34f  lea     rdx, aSha256; "SHA256"
0x1800fe356  mov     rax, qword ptr cs:?functions@BcryptLibrary@Common@@0PAP6A_JXZA; __int64 (*near * Common::BcryptLibrary::functions)(void)
0x1800fe35d  xor     ebx, ebx
0x1800fe35f  mov     rcx, rdi
0x1800fe362  mov     dword ptr [rbp+arg_18], ebx
0x1800fe365  xor     r9d, r9d
0x1800fe368  mov     [rbp+var_30], ebx
0x1800fe36b  xor     r8d, r8d
0x1800fe36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe373  test    eax, eax
0x1800fe375  jns     short loc_1800FE3B2
0x1800fe377  mov     rcx, [rbp+38h]; this
0x1800fe37b  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\common\\crypto"...
0x1800fe382  mov     r9d, eax; char *
0x1800fe385  lea     edx, [rbx+4Fh]; void *
0x1800fe388  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800fe38d  mov     ebx, eax
0x1800fe38f  test    eax, eax
0x1800fe391  jns     short loc_1800FE3B0
0x1800fe393  mov     edx, 61h ; 'a'; void *
0x1800fe398  mov     rcx, [rbp+38h]; this
0x1800fe39c  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\common\\crypto"...
0x1800fe3a3  mov     r9d, eax; char *
0x1800fe3a6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fe3ab  jmp     loc_1800FE468
0x1800fe3b0  xor     ebx, ebx
0x1800fe3b2  mov     rcx, [rdi]
0x1800fe3b5  lea     rax, [rbp+var_30]
0x1800fe3b9  mov     dword ptr [rsp+70h+var_48], ebx
0x1800fe3bd  lea     r8, [rbp+arg_18]
0x1800fe3c1  mov     [rsp+70h+var_50], rax
0x1800fe3c6  lea     rdx, aObjectlength; "ObjectLength"
0x1800fe3cd  mov     rax, qword ptr cs:xmmword_180140620
0x1800fe3d4  mov     r9d, 4
0x1800fe3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe3df  mov     r15d, 7Ch ; '|'
0x1800fe3e5  test    eax, eax
0x1800fe3e7  jns     short loc_1800FE3EF
0x1800fe3e9  lea     edx, [r15-13h]
0x1800fe3ed  jmp     short loc_1800FE44F
0x1800fe3ef  mov     r9d, dword ptr [rbp+arg_18]
0x1800fe3f3  cmp     r9d, 2BCh
0x1800fe3fa  ja      short loc_1800FE402
0x1800fe3fc  lea     r8, [rdi+40h]
0x1800fe400  jmp     short loc_1800FE428
0x1800fe402  lea     rcx, [rdi+10h]; this
0x1800fe406  mov     edx, r9d; unsigned int
0x1800fe409  call    ?SetLength@ByteBuffer@Common@@QEAAJK@Z; Common::ByteBuffer::SetLength(ulong)
0x1800fe40e  mov     ebx, eax
0x1800fe410  test    eax, eax
0x1800fe412  jns     short loc_1800FE41E
0x1800fe414  mov     edx, 71h ; 'q'
0x1800fe419  jmp     loc_1800FE398
0x1800fe41e  mov     r8, [rdi+18h]
0x1800fe422  xor     ebx, ebx
0x1800fe424  mov     r9d, dword ptr [rbp+arg_18]
0x1800fe428  mov     rcx, [rdi]
0x1800fe42b  lea     rdx, [rdi+8]
0x1800fe42f  mov     rax, qword ptr cs:xmmword_180140620+8
0x1800fe436  mov     [rsp+70h+var_40], ebx
0x1800fe43a  mov     dword ptr [rsp+70h+var_48], ebx
0x1800fe43e  mov     [rsp+70h+var_50], rbx; int
0x1800fe443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe448  test    eax, eax
0x1800fe44a  jns     short loc_1800FE4BC
0x1800fe44c  mov     edx, r15d; void *
0x1800fe44f  mov     rcx, [rbp+38h]; this
0x1800fe453  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\common\\crypto"...
0x1800fe45a  mov     r9d, eax; char *
0x1800fe45d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800fe462  mov     ebx, eax
0x1800fe464  test    eax, eax
0x1800fe466  jns     short loc_1800FE4BA
0x1800fe468  mov     rcx, [rbp+38h]; this
0x1800fe46c  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\staterepositor"...
0x1800fe473  mov     r9d, ebx; char *
0x1800fe476  mov     edx, 11h; void *
0x1800fe47b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fe480  mov     rcx, [rbp+38h]; this
0x1800fe484  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fe48b  mov     r9d, ebx; char *
0x1800fe48e  mov     edx, 0E67h; void *
0x1800fe493  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fe498  lea     rdx, aHasherStartFai; "Hasher.Start() failed"
0x1800fe49f  or      r8d, 0FFFFFFFFh
0x1800fe4a3  mov     rcx, rsi
0x1800fe4a6  call    sqlite3_result_error16
0x1800fe4ab  mov     edx, ebx
0x1800fe4ad  mov     rcx, rsi
0x1800fe4b0  call    sqlite3_result_error_code
0x1800fe4b5  jmp     loc_1800FE778
0x1800fe4ba  xor     ebx, ebx
0x1800fe4bc  mov     edi, ebx
0x1800fe4be  test    r13d, r13d
0x1800fe4c1  jle     short loc_1800FE53F
0x1800fe4c3  movsxd  rax, edi
0x1800fe4c6  mov     rbx, [r14+rax*8]
0x1800fe4ca  mov     rcx, rbx
0x1800fe4cd  call    sqlite3_value_type
0x1800fe4d2  mov     edx, eax
0x1800fe4d4  mov     r8d, eax
0x1800fe4d7  sub     edx, 1
0x1800fe4da  jz      loc_1800FE5F2
0x1800fe4e0  sub     edx, 1
0x1800fe4e3  jz      loc_1800FE795
0x1800fe4e9  sub     edx, 1
0x1800fe4ec  jz      loc_1800FE5B1
0x1800fe4f2  sub     edx, 1
0x1800fe4f5  jz      short loc_1800FE502
0x1800fe4f7  cmp     edx, 1
0x1800fe4fa  jnz     loc_1800FE7CC
0x1800fe500  jmp     short loc_1800FE536
0x1800fe502  mov     rcx, rbx
0x1800fe505  call    sqlite3_value_blob
0x1800fe50a  mov     r14, rax
0x1800fe50d  test    rax, rax
0x1800fe510  jz      short loc_1800FE532
0x1800fe512  mov     rcx, rbx
0x1800fe515  call    sqlite3_value_bytes
0x1800fe51a  movsxd  rdx, eax; unsigned __int64
0x1800fe51d  mov     r8, r14; void *
0x1800fe520  mov     rcx, r12; this
0x1800fe523  call    ?Update@Hasher@DataType@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::DataType::Hasher::Update(unsigned __int64,void const *)
0x1800fe528  mov     ebx, eax
0x1800fe52a  test    eax, eax
0x1800fe52c  js      loc_1800FE63D
0x1800fe532  mov     r14, [rbp+arg_10]
0x1800fe536  inc     edi
0x1800fe538  cmp     edi, r13d
0x1800fe53b  jl      short loc_1800FE4C3
0x1800fe53d  xor     ebx, ebx
0x1800fe53f  mov     rdi, [r12]
0x1800fe543  xorps   xmm6, xmm6
0x1800fe546  mov     [rbp+var_28], rbx
0x1800fe54a  mov     [rbp+var_20], rbx
0x1800fe54e  mov     dword ptr [rbp+arg_18], ebx
0x1800fe551  cmp     [rdi+340h], ebx
0x1800fe557  jnz     loc_1800FE6B4
0x1800fe55d  mov     rcx, [rdi]
0x1800fe560  lea     rax, [rbp+var_30]
0x1800fe564  mov     dword ptr [rsp+70h+var_48], ebx
0x1800fe568  lea     r8, [rbp+arg_18]
0x1800fe56c  mov     [rsp+70h+var_50], rax; int
0x1800fe571  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800fe578  mov     rax, qword ptr cs:xmmword_180140620
0x1800fe57f  mov     r9d, 4
0x1800fe585  mov     [rbp+var_30], ebx
0x1800fe588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe58d  mov     ebx, eax
0x1800fe58f  test    eax, eax
0x1800fe591  jnz     loc_1800FE694
0x1800fe597  mov     r8d, dword ptr [rbp+arg_18]
0x1800fe59b  cmp     r8d, 40h ; '@'
0x1800fe59f  ja      loc_1800FE644
0x1800fe5a5  lea     r14, [rdi+2FCh]
0x1800fe5ac  jmp     loc_1800FE678
0x1800fe5b1  mov     rcx, rbx
0x1800fe5b4  call    sqlite3_value_text16le
0x1800fe5b9  mov     rdx, rax; wchar_t *
0x1800fe5bc  mov     rcx, r12; this
0x1800fe5bf  call    ?Update@Hasher@DataType@StateRepository@@QEAAJPEB_W@Z; StateRepository::DataType::Hasher::Update(wchar_t const *)
0x1800fe5c4  mov     ebx, eax
0x1800fe5c6  test    eax, eax
0x1800fe5c8  jns     loc_1800FE536
0x1800fe5ce  mov     edx, 0E86h; void *
0x1800fe5d3  mov     rcx, [rbp+38h]; this
0x1800fe5d7  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fe5de  mov     r9d, ebx; char *
0x1800fe5e1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fe5e6  lea     rdx, aHasherUpdateTe; "Hasher.Update(text) failed"
0x1800fe5ed  jmp     loc_1800FE49F
0x1800fe5f2  mov     rcx, rbx
0x1800fe5f5  call    sqlite3_value_int64
0x1800fe5fa  lea     r8, [rbp+arg_18]; void *
0x1800fe5fe  mov     [rbp+arg_18], rax
0x1800fe602  mov     edx, 8; unsigned __int64
0x1800fe607  mov     rcx, r12; this
0x1800fe60a  call    ?Update@Hasher@DataType@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::DataType::Hasher::Update(unsigned __int64,void const *)
0x1800fe60f  mov     ebx, eax
0x1800fe611  test    eax, eax
0x1800fe613  jns     loc_1800FE536
0x1800fe619  mov     rcx, [rbp+38h]; this
0x1800fe61d  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fe624  mov     r9d, eax; char *
0x1800fe627  mov     edx, 0E77h; void *
0x1800fe62c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fe631  lea     rdx, aHasherUpdateIn; "Hasher.Update(integer) failed"
0x1800fe638  jmp     loc_1800FE49F
0x1800fe63d  mov     edx, 0E95h
0x1800fe642  jmp     short loc_1800FE5D3
0x1800fe644  lea     rcx, [rdi+28h]; this
0x1800fe648  mov     edx, r8d; unsigned int
0x1800fe64b  call    ?SetLength@ByteBuffer@Common@@QEAAJK@Z; Common::ByteBuffer::SetLength(ulong)
0x1800fe650  mov     ebx, eax
0x1800fe652  test    eax, eax
0x1800fe654  jns     short loc_1800FE670
0x1800fe656  mov     rcx, [rbp+38h]; this
0x1800fe65a  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\common\\crypto"...
0x1800fe661  mov     r9d, eax; char *
0x1800fe664  mov     edx, 0B8h; void *
0x1800fe669  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fe66e  jmp     short loc_1800FE69C
0x1800fe670  mov     r14, [rdi+30h]
0x1800fe674  mov     r8d, dword ptr [rbp+arg_18]
0x1800fe678  mov     rcx, [rdi+8]
0x1800fe67c  xor     r9d, r9d
0x1800fe67f  mov     rax, qword ptr cs:xmmword_180140630+8
0x1800fe686  mov     rdx, r14
0x1800fe689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe68e  mov     ebx, eax
0x1800fe690  test    eax, eax
0x1800fe692  jz      short loc_1800FE6A4
0x1800fe694  or      ebx, 10000000h
0x1800fe69a  jge     short loc_1800FE6BB
0x1800fe69c  mov     r15d, 71h ; 'q'
0x1800fe6a2  jmp     short loc_1800FE707
0x1800fe6a4  mov     eax, dword ptr [rbp+arg_18]
0x1800fe6a7  mov     [rdi+340h], eax
0x1800fe6ad  mov     [rdi+348h], r14
0x1800fe6b4  movups  xmm6, xmmword ptr [rdi+340h]
0x1800fe6bb  xor     r8d, r8d; bool
0x1800fe6be  lea     rcx, [rbp+var_28]; this
0x1800fe6c2  lea     edx, [r8+35h]; unsigned __int64
0x1800fe6c6  call    ?EnsureCapacity@Text@StateRepository@@QEAAJ_K_N@Z; StateRepository::Text::EnsureCapacity(unsigned __int64,bool)
0x1800fe6cb  mov     ebx, eax
0x1800fe6cd  test    eax, eax
0x1800fe6cf  js      short loc_1800FE707
0x1800fe6d1  mov     rdi, [rbp+var_28]
0x1800fe6d5  lea     rax, [rbp+arg_18]
0x1800fe6d9  movd    edx, xmm6; unsigned int
0x1800fe6dd  mov     r9, rdi; unsigned __int16 *
0x1800fe6e0  psrldq  xmm6, 8
0x1800fe6e5  movq    rcx, xmm6; unsigned __int8 *
0x1800fe6ea  mov     dword ptr [rbp+arg_18], 0
0x1800fe6f1  mov     [rsp+70h+var_50], rax; int
0x1800fe6f6  call    ?GetChars@Base32Encoding@Common@@SAJPEBEKKPEAGPEAK@Z; Common::Base32Encoding::GetChars(uchar const *,ulong,ulong,ushort *,ulong *)
0x1800fe6fb  mov     ebx, eax
0x1800fe6fd  test    eax, eax
0x1800fe6ff  jns     short loc_1800FE754
0x1800fe701  mov     r15d, 80h
0x1800fe707  mov     rcx, [rbp+38h]; this
0x1800fe70b  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\staterepositor"...
0x1800fe712  mov     r9d, ebx; char *
0x1800fe715  mov     edx, r15d; void *
0x1800fe718  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fe71d  mov     rcx, [rbp+38h]; this
0x1800fe721  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fe728  mov     r9d, ebx; char *
0x1800fe72b  mov     edx, 0EA7h; void *
0x1800fe730  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fe735  or      r8d, 0FFFFFFFFh
0x1800fe739  lea     rdx, aHasherGetdiges; "Hasher.GetDigestAsBase32(text) failed"
0x1800fe740  mov     rcx, rsi
0x1800fe743  call    sqlite3_result_error16
0x1800fe748  mov     edx, ebx
0x1800fe74a  mov     rcx, rsi
0x1800fe74d  call    sqlite3_result_error_code
0x1800fe752  jmp     short loc_1800FE76F
0x1800fe754  mov     ecx, dword ptr [rbp+arg_18]
0x1800fe757  xor     eax, eax
0x1800fe759  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800fe75d  mov     rdx, rdi
0x1800fe760  or      r8d, r9d
0x1800fe763  mov     [rdi+rcx*2], ax
0x1800fe767  mov     rcx, rsi
0x1800fe76a  call    sqlite3_result_text16
0x1800fe76f  lea     rcx, [rbp+var_28]; this
0x1800fe773  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x1800fe778  mov     rbx, [rsp+70h+arg_0]
0x1800fe780  movaps  xmm6, [rsp+70h+var_10]
0x1800fe785  add     rsp, 70h
0x1800fe789  pop     r15
0x1800fe78b  pop     r14
0x1800fe78d  pop     r13
0x1800fe78f  pop     r12
0x1800fe791  pop     rdi
0x1800fe792  pop     rsi
0x1800fe793  pop     rbp
0x1800fe794  retn
0x1800fe795  mov     ecx, 8000FFFFh
  ... truncated ...
```
