# asg::Sqlite::DbConnection::Initialize(std::span<uchar const,-1>,asg::Sqlite::CreateDisposition,std::basic_string_view<char8_t,std::char_traits<char8_t>> const &)

- ea: `0x180179fb0`
- end: `0x18017a40b`
- name: `?Initialize@DbConnection@Sqlite@asg@@AEAAXV?$span@$$CBE$0?0@std@@W4CreateDisposition@23@AEBV?$basic_string_view@_QU?$char_traits@_Q@std@@@5@@Z`
- size: `1115`
- prototype: `__int64 __fastcall(asg::Sqlite::DbConnection *this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1801795e0`

## callees

- `0x180004140`
- `0x1800178d0`
- `0x18002bb20`
- `0x180078ed0`
- `0x180153420`
- `0x180153680`
- `0x180154450`
- `0x180154bc0`
- `0x180156080`
- `0x180156450`
- `0x180156790`
- `0x1801569d0`
- `0x180157280`
- `0x1801799b0`
- `0x180179fb0`
- `0x18017a930`
- `0x18017ae70`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206ec0`

## string_xrefs

- `0x18017a31a`: `Cannot specify both OpenAlways and CreateAlways for read-write connections`
- `0x18017a348`: `Cannot specify either OpenAlways or CreateAlways for read only connections`
- `0x18017a148`: `bool __cdecl asg::Sqlite::DbConnection::ReadProbe(void) const`
- `0x18017a392`: `void __cdecl asg::Sqlite::DbConnection::SQLDeleter::operator ()(struct sqlite3 *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall asg::Sqlite::DbConnection::Initialize(asg::Sqlite::DbConnection *this, _QWORD *a2, char a3, __int64 a4)
{
  int v7; // r15d
  int v8; // esi
  char v9; // cl
  unsigned int v10; // ebx
  int v11; // eax
  _QWORD *v12; // r9
  _QWORD *v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  int v18; // ebx
  unsigned int v19; // ebx
  __int64 v20; // r14
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int busy; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  void *v28; // rcx
  void *v29; // rcx
  _DWORD pExceptionObject[2]; // [rsp+30h] [rbp-D0h] BYREF
  const char *v31; // [rsp+38h] [rbp-C8h]
  const char *v32; // [rsp+40h] [rbp-C0h]
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v35[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+70h] [rbp-90h]
  unsigned __int64 v37; // [rsp+78h] [rbp-88h]
  _QWORD v38[3]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v39; // [rsp+98h] [rbp-68h]
  _QWORD v40[8]; // [rsp+A0h] [rbp-60h] BYREF
  int v41; // [rsp+E0h] [rbp-20h]
  int v42; // [rsp+E4h] [rbp-1Ch]
  const char *v43; // [rsp+E8h] [rbp-18h]
  const char *v44; // [rsp+F0h] [rbp-10h]

  *((_BYTE *)this + 256) = (a3 & 2) == 0;
  v7 = a3 & 4;
  v8 = a3 & 8;
  if ( (a3 & 2) != 0 )
  {
    if ( (a3 & 4) != 0 && (a3 & 8) != 0 )
    {
      std::invalid_argument::invalid_argument(
        (std::invalid_argument *)pExceptionObject,
        "Cannot specify both OpenAlways and CreateAlways for read-write connections");
      throw (std::invalid_argument *)pExceptionObject;
    }
  }
  else if ( (a3 & 4) != 0 || (a3 & 8) != 0 )
  {
    std::invalid_argument::invalid_argument(
      (std::invalid_argument *)pExceptionObject,
      "Cannot specify either OpenAlways or CreateAlways for read only connections");
    throw (std::invalid_argument *)pExceptionObject;
  }
  std::string::string(v38, (char *)this + 48);
  v34 = 0;
  v9 = *((_BYTE *)this + 256);
  v10 = 2 - (v9 != 0);
  if ( !v9 )
  {
    v11 = v10 | 4;
    if ( !v7 )
      v11 = 2 - (v9 != 0);
    v10 = v11;
    if ( v8 )
      v10 = v11 | 0x14;
  }
  asg::Sqlite::ResolveVfsName(v35, a4);
  if ( v36 )
  {
    v12 = v35;
    if ( v37 > 0xF )
      v12 = (_QWORD *)v35[0];
  }
  else
  {
    v12 = 0;
  }
  v13 = v38;
  if ( v39 > 0xF )
    v13 = (_QWORD *)v38[0];
  v14 = sqlite3_open_v2(v13, &v34, v10, v12);
  if ( v14 )
    asg::Sqlite::DbConnection::ThrowDbException(this, v14);
  v15 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = v34;
  if ( v15 && (unsigned int)sqlite3_close_v2() )
  {
    pExceptionObject[0] = 604;
    pExceptionObject[1] = 13;
    v31 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSqliteWrapper\\DbConnection.cpp";
    v32 = "void __cdecl asg::Sqlite::DbConnection::SQLDeleter::operator ()(struct sqlite3 *)";
    asg::details::AsgAssertFail(pExceptionObject);
  }
  v16 = a2[1];
  if ( v16 == 32 || v16 == 8 )
  {
    v33 = 0;
    v17 = sqlite3_prepare_v2(*((_QWORD *)this + 10), (unsigned int)"PRAGMA schema_version;", -1, (unsigned int)&v33, 0);
    if ( v17 )
      asg::Sqlite::DbConnection::ThrowDbException(this, v17);
    v40[0] = ___7___Func_impl_no_alloc_V_lambda_1___1__ReadProbe_DbConnection_Sqlite_asg__QEBA_NXZ_X__V_std__6B_;
    v40[1] = &v33;
    v40[7] = v40;
    v41 = 564;
    v42 = 40;
    v43 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSqliteWrapper\\DbConnection.cpp";
    v44 = "bool __cdecl asg::Sqlite::DbConnection::ReadProbe(void) const";
    v18 = sqlite3_step(v33);
    asg::OnScopeExit::~OnScopeExit((asg::OnScopeExit *)v40);
    if ( v18 == 100 )
    {
      if ( !*((_BYTE *)this + 256) )
        asg::Sqlite::DbConnection::EnsureNonceSupport(this);
      v19 = *((_DWORD *)a2 + 2);
      v20 = *a2;
      v21 = sqlite3_rekey_v2(*((_QWORD *)this + 10), 0, v20, v19);
      if ( v21 )
        asg::Sqlite::DbConnection::ThrowDbException(this, v21);
      v22 = sqlite3_key_v2(*((_QWORD *)this + 10), 0, v20, v19);
      if ( v22 )
        asg::Sqlite::DbConnection::ThrowDbException(this, v22);
    }
    else
    {
      v23 = sqlite3_key_v2(*((_QWORD *)this + 10), 0, *a2, *((unsigned int *)a2 + 2));
      if ( v23 )
        asg::Sqlite::DbConnection::ThrowDbException(this, v23);
    }
  }
  busy = sqlite3_busy_handler(v34, busy_handler_callback, 0);
  if ( busy )
    asg::Sqlite::DbConnection::ThrowDbException(this, busy);
  if ( v8 )
  {
    v25 = sqlite3_db_config(*((_QWORD *)this + 10), 1009, 1, 0);
    if ( v25 )
      asg::Sqlite::DbConnection::ThrowDbException(this, v25);
    v26 = sqlite3_exec(*((_QWORD *)this + 10), (unsigned int)"VACUUM", 0, 0, 0);
    if ( v26 )
      asg::Sqlite::DbConnection::ThrowDbException(this, v26);
    v27 = sqlite3_db_config(*((_QWORD *)this + 10), 1009, 0, 0);
    if ( v27 )
      asg::Sqlite::DbConnection::ThrowDbException(this, v27);
  }
  if ( v37 > 0xF )
  {
    v28 = (void *)v35[0];
    if ( v37 + 1 >= 0x1000 )
    {
      v28 = *(void **)(v35[0] - 8LL);
      if ( (unsigned __int64)(v35[0] - (_QWORD)v28 - 8LL) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v28);
  }
  v36 = 0;
  v37 = 15;
  LOBYTE(v35[0]) = 0;
  if ( v39 > 0xF )
  {
    v29 = (void *)v38[0];
    if ( v39 + 1 >= 0x1000 )
    {
      v29 = *(void **)(v38[0] - 8LL);
      if ( (unsigned __int64)(v38[0] - (_QWORD)v29 - 8LL) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v29);
  }
}

```

## disassembly

```asm
0x180179fb0  mov     [rsp-8+arg_10], rbx
0x180179fb5  push    rbp
0x180179fb6  push    rsi
0x180179fb7  push    rdi
0x180179fb8  push    r12
0x180179fba  push    r13
0x180179fbc  push    r14
0x180179fbe  push    r15
0x180179fc0  lea     rbp, [rsp-10h]
0x180179fc5  sub     rsp, 110h
0x180179fcc  mov     rax, cs:__security_cookie
0x180179fd3  xor     rax, rsp
0x180179fd6  mov     [rbp+40h+var_40], rax
0x180179fda  mov     r12, r9
0x180179fdd  mov     esi, r8d
0x180179fe0  mov     r14, rdx
0x180179fe3  mov     rdi, rcx
0x180179fe6  bt      r8d, 1
0x180179feb  setnb   al
0x180179fee  mov     [rcx+100h], al
0x180179ff4  mov     r15d, r8d
0x180179ff7  and     r15d, 4
0x180179ffb  and     esi, 8
0x180179ffe  bt      r8d, 1
0x18017a003  jnb     short loc_18017A014
0x18017a005  test    r15d, r15d
0x18017a008  jz      short loc_18017A025
0x18017a00a  test    esi, esi
0x18017a00c  jnz     loc_18017A31A
0x18017a012  jmp     short loc_18017A025
0x18017a014  test    r15d, r15d
0x18017a017  jnz     loc_18017A348
0x18017a01d  test    esi, esi
0x18017a01f  jnz     loc_18017A348
0x18017a025  lea     rdx, [rcx+30h]
0x18017a029  lea     rcx, [rbp+40h+var_C0]
0x18017a02d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18017a032  nop
0x18017a033  xor     r13d, r13d
0x18017a036  mov     [rsp+140h+var_E8], r13
0x18017a03b  movzx   ecx, byte ptr [rdi+100h]
0x18017a042  movzx   eax, cl
0x18017a045  neg     al
0x18017a047  sbb     ebx, ebx
0x18017a049  add     ebx, 2
0x18017a04c  test    cl, cl
0x18017a04e  jnz     short loc_18017A064
0x18017a050  mov     eax, ebx
0x18017a052  or      eax, 4
0x18017a055  test    r15d, r15d
0x18017a058  cmovz   eax, ebx
0x18017a05b  mov     ebx, eax
0x18017a05d  test    esi, esi
0x18017a05f  jz      short loc_18017A064
0x18017a061  or      ebx, 14h
0x18017a064  mov     rdx, r12
0x18017a067  lea     rcx, [rsp+140h+var_E0]
0x18017a06c  call    asg__Sqlite__ResolveVfsName
0x18017a071  nop
0x18017a072  cmp     [rsp+140h+var_D0], 0
0x18017a078  jnz     short loc_18017A07F
0x18017a07a  mov     r9, r13
0x18017a07d  jmp     short loc_18017A090
0x18017a07f  lea     r9, [rsp+140h+var_E0]
0x18017a084  cmp     [rsp+140h+var_C8], 0Fh
0x18017a08a  cmova   r9, [rsp+140h+var_E0]
0x18017a090  lea     rcx, [rbp+40h+var_C0]
0x18017a094  cmp     [rbp+40h+var_A8], 0Fh
0x18017a099  cmova   rcx, [rbp+40h+var_C0]
0x18017a09e  mov     r8d, ebx
0x18017a0a1  lea     rdx, [rsp+140h+var_E8]
0x18017a0a6  call    sqlite3_open_v2
0x18017a0ab  test    eax, eax
0x18017a0ad  jnz     loc_18017A36B
0x18017a0b3  mov     rcx, [rdi+50h]
0x18017a0b7  mov     rax, [rsp+140h+var_E8]
0x18017a0bc  mov     [rdi+50h], rax
0x18017a0c0  test    rcx, rcx
0x18017a0c3  jz      short loc_18017A0D2
0x18017a0c5  call    sqlite3_close_v2
0x18017a0ca  test    eax, eax
0x18017a0cc  jnz     loc_18017A376
0x18017a0d2  mov     rax, [r14+8]
0x18017a0d6  cmp     rax, 20h ; ' '
0x18017a0da  jz      short loc_18017A0E6
0x18017a0dc  cmp     rax, 8
0x18017a0e0  jnz     loc_18017A1D3
0x18017a0e6  mov     [rsp+140h+var_F0], r13
0x18017a0eb  mov     [rsp+140h+Reserved], r13
0x18017a0f0  lea     r9, [rsp+140h+var_F0]
0x18017a0f5  mov     r8d, 0FFFFFFFFh
0x18017a0fb  lea     rdx, aPragmaSchemaVe; "PRAGMA schema_version;"
0x18017a102  mov     rcx, [rdi+50h]
0x18017a106  call    sqlite3_prepare_v2
0x18017a10b  test    eax, eax
0x18017a10d  jnz     loc_18017A3A9
0x18017a113  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1??ReadProbe@DbConnection@Sqlite@asg@@QEBA_NXZ@X$$V@std@@6B@; const std::_Func_impl_no_alloc<`asg::Sqlite::DbConnection::ReadProbe(void)'::`2'::_lambda_1_,void,>::`vftable'
0x18017a11a  mov     [rbp+40h+var_A0], rax
0x18017a11e  lea     rax, [rsp+140h+var_F0]
0x18017a123  mov     [rbp+40h+var_98], rax
0x18017a127  lea     rax, [rbp+40h+var_A0]
0x18017a12b  mov     [rbp+40h+var_68], rax
0x18017a12f  mov     [rbp+40h+var_60], 234h
0x18017a136  mov     [rbp+40h+var_5C], 28h ; '('
0x18017a13d  lea     rax, aCW1SSrcSemanti_7; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18017a144  mov     [rbp+40h+var_58], rax
0x18017a148  lea     rax, aBoolCdeclAsgSq; "bool __cdecl asg::Sqlite::DbConnection:"...
0x18017a14f  mov     [rbp+40h+var_50], rax
0x18017a153  mov     rcx, [rsp+140h+var_F0]
0x18017a158  call    sqlite3_step
0x18017a15d  mov     ebx, eax
0x18017a15f  lea     rcx, [rbp+40h+var_A0]; this
0x18017a163  call    ??1OnScopeExit@asg@@QEAA@XZ; asg::OnScopeExit::~OnScopeExit(void)
0x18017a168  cmp     ebx, 64h ; 'd'
0x18017a16b  jnz     short loc_18017A1B9
0x18017a16d  cmp     byte ptr [rdi+100h], 0
0x18017a174  jnz     short loc_18017A17E
0x18017a176  mov     rcx, rdi; this
0x18017a179  call    ?EnsureNonceSupport@DbConnection@Sqlite@asg@@QEAAXXZ; asg::Sqlite::DbConnection::EnsureNonceSupport(void)
0x18017a17e  mov     ebx, [r14+8]
0x18017a182  mov     r14, [r14]
0x18017a185  mov     r9d, ebx
0x18017a188  mov     r8, r14
0x18017a18b  xor     edx, edx
0x18017a18d  mov     rcx, [rdi+50h]
0x18017a191  call    sqlite3_rekey_v2
0x18017a196  test    eax, eax
0x18017a198  jnz     loc_18017A3B4
0x18017a19e  mov     r9d, ebx
0x18017a1a1  mov     r8, r14
0x18017a1a4  xor     edx, edx
0x18017a1a6  mov     rcx, [rdi+50h]
0x18017a1aa  call    sqlite3_key_v2
0x18017a1af  test    eax, eax
0x18017a1b1  jnz     loc_18017A33D
0x18017a1b7  jmp     short loc_18017A1D3
0x18017a1b9  mov     r9d, [r14+8]
0x18017a1bd  mov     r8, [r14]
0x18017a1c0  xor     edx, edx
0x18017a1c2  mov     rcx, [rdi+50h]
0x18017a1c6  call    sqlite3_key_v2
0x18017a1cb  test    eax, eax
0x18017a1cd  jnz     loc_18017A3BF
0x18017a1d3  xor     r8d, r8d
0x18017a1d6  lea     rdx, busy_handler_callback
0x18017a1dd  mov     rcx, [rsp+140h+var_E8]
0x18017a1e2  call    sqlite3_busy_handler
0x18017a1e7  test    eax, eax
0x18017a1e9  jnz     loc_18017A3CA
0x18017a1ef  test    esi, esi
0x18017a1f1  jz      short loc_18017A251
0x18017a1f3  xor     r9d, r9d
0x18017a1f6  mov     edx, 3F1h
0x18017a1fb  mov     r8d, 1
0x18017a201  mov     rcx, [rdi+50h]
0x18017a205  call    sqlite3_db_config
0x18017a20a  test    eax, eax
0x18017a20c  jnz     loc_18017A3D5
0x18017a212  mov     [rsp+140h+Reserved], r13
0x18017a217  xor     r9d, r9d
0x18017a21a  xor     r8d, r8d
0x18017a21d  lea     rdx, aVacuum; "VACUUM"
0x18017a224  mov     rcx, [rdi+50h]
0x18017a228  call    sqlite3_exec
0x18017a22d  test    eax, eax
0x18017a22f  jnz     loc_18017A3E0
0x18017a235  xor     r9d, r9d
0x18017a238  xor     r8d, r8d
0x18017a23b  mov     edx, 3F1h
0x18017a240  mov     rcx, [rdi+50h]
0x18017a244  call    sqlite3_db_config
0x18017a249  test    eax, eax
0x18017a24b  jnz     loc_18017A3EB
0x18017a251  mov     rdx, [rsp+140h+var_C8]
0x18017a256  cmp     rdx, 0Fh
0x18017a25a  jbe     short loc_18017A291
0x18017a25c  inc     rdx
0x18017a25f  mov     rcx, [rsp+140h+var_E0]
0x18017a264  mov     rax, rcx
0x18017a267  cmp     rdx, 1000h
0x18017a26e  jb      short loc_18017A289
0x18017a270  add     rdx, 27h ; '''
0x18017a274  mov     rcx, [rcx-8]; Block
0x18017a278  sub     rax, rcx
0x18017a27b  sub     rax, 8
0x18017a27f  cmp     rax, 1Fh
0x18017a283  ja      loc_18017A3F6
0x18017a289  lfence
0x18017a28c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18017a291  mov     [rsp+140h+var_D0], r13
0x18017a296  mov     [rsp+140h+var_C8], 0Fh
0x18017a29f  mov     byte ptr [rsp+140h+var_E0], 0
0x18017a2a4  mov     rdx, [rbp+40h+var_A8]
0x18017a2a8  cmp     rdx, 0Fh
0x18017a2ac  jbe     short loc_18017A2DE
0x18017a2ae  inc     rdx
0x18017a2b1  mov     rcx, [rbp+40h+var_C0]
0x18017a2b5  mov     rax, rcx
0x18017a2b8  cmp     rdx, 1000h
0x18017a2bf  jb      short loc_18017A2D6
0x18017a2c1  add     rdx, 27h ; '''
0x18017a2c5  mov     rcx, [rcx-8]; Block
0x18017a2c9  sub     rax, rcx
0x18017a2cc  sub     rax, 8
0x18017a2d0  cmp     rax, 1Fh
0x18017a2d4  ja      short loc_18017A305
0x18017a2d6  lfence
0x18017a2d9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18017a2de  mov     rcx, [rbp+40h+var_40]
0x18017a2e2  xor     rcx, rsp; StackCookie
0x18017a2e5  call    __security_check_cookie
0x18017a2ea  mov     rbx, [rsp+140h+arg_10]
0x18017a2f2  add     rsp, 110h
0x18017a2f9  pop     r15
0x18017a2fb  pop     r14
0x18017a2fd  pop     r13
0x18017a2ff  pop     r12
0x18017a301  pop     rdi
0x18017a302  pop     rsi
0x18017a303  pop     rbp
0x18017a304  retn
0x18017a305  mov     [rsp+140h+Reserved], r13; Reserved
0x18017a30a  xor     r9d, r9d; LineNo
0x18017a30d  xor     r8d, r8d; FileName
0x18017a310  xor     edx, edx; FunctionName
0x18017a312  xor     ecx, ecx; Expression
0x18017a314  call    _invoke_watson
0x18017a31a  lea     rdx, aCannotSpecifyB_1; "Cannot specify both OpenAlways and Crea"...
0x18017a321  lea     rcx, [rsp+140h+pExceptionObject]; this
0x18017a326  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x18017a32b  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18017a332  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18017a337  call    _CxxThrowException
0x18017a33d  mov     edx, eax; int
0x18017a33f  mov     rcx, rdi; this
0x18017a342  call    ?ThrowDbException@DbConnection@Sqlite@asg@@AEBAXH@Z; asg::Sqlite::DbConnection::ThrowDbException(int)
0x18017a348  lea     rdx, aCannotSpecifyE; "Cannot specify either OpenAlways or Cre"...
0x18017a34f  lea     rcx, [rsp+140h+pExceptionObject]; this
0x18017a354  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x18017a359  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18017a360  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18017a365  call    _CxxThrowException
0x18017a36b  mov     edx, eax; int
0x18017a36d  mov     rcx, rdi; this
0x18017a370  call    ?ThrowDbException@DbConnection@Sqlite@asg@@AEBAXH@Z; asg::Sqlite::DbConnection::ThrowDbException(int)
0x18017a376  mov     [rsp+140h+pExceptionObject], 25Ch
0x18017a37e  mov     [rsp+140h+var_10C], 0Dh
0x18017a386  lea     rax, aCW1SSrcSemanti_7; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18017a38d  mov     [rsp+140h+var_108], rax
0x18017a392  lea     rdx, aVoidCdeclAsgSq_0; "void __cdecl asg::Sqlite::DbConnection:"...
0x18017a399  mov     [rsp+140h+var_100], rdx
0x18017a39e  lea     rcx, [rsp+140h+pExceptionObject]
0x18017a3a3  call    ?AsgAssertFail@details@asg@@YAXUsource_location@std@@PEBD@Z; asg::details::AsgAssertFail(std::source_location,char const *)
0x18017a3a9  mov     edx, eax; int
0x18017a3ab  mov     rcx, rdi; this
0x18017a3ae  call    ?ThrowDbException@DbConnection@Sqlite@asg@@AEBAXH@Z; asg::Sqlite::DbConnection::ThrowDbException(int)
0x18017a3b4  mov     edx, eax; int
0x18017a3b6  mov     rcx, rdi; this
0x18017a3b9  call    ?ThrowDbException@DbConnection@Sqlite@asg@@AEBAXH@Z; asg::Sqlite::DbConnection::ThrowDbException(int)
0x18017a3bf  mov     edx, eax; int
0x18017a3c1  mov     rcx, rdi; this
0x18017a3c4  call    ?ThrowDbException@DbConnection@Sqlite@asg@@AEBAXH@Z; asg::Sqlite::DbConnection::ThrowDbException(int)
0x18017a3ca  mov     edx, eax; int
0x18017a3cc  mov     rcx, rdi; this
0x18017a3cf  call    ?ThrowDbException@DbConnection@Sqlite@asg@@AEBAXH@Z; asg::Sqlite::DbConnection::ThrowDbException(int)
0x18017a3d5  mov     edx, eax; int
0x18017a3d7  mov     rcx, rdi; this
0x18017a3da  call    ?ThrowDbException@DbConnection@Sqlite@asg@@AEBAXH@Z; asg::Sqlite::DbConnection::ThrowDbException(int)
0x18017a3e0  mov     edx, eax; int
0x18017a3e2  mov     rcx, rdi; this
0x18017a3e5  call    ?ThrowDbException@DbConnection@Sqlite@asg@@AEBAXH@Z; asg::Sqlite::DbConnection::ThrowDbException(int)
0x18017a3eb  mov     edx, eax; int
0x18017a3ed  mov     rcx, rdi; this
0x18017a3f0  call    ?ThrowDbException@DbConnection@Sqlite@asg@@AEBAXH@Z; asg::Sqlite::DbConnection::ThrowDbException(int)
0x18017a3f6  mov     [rsp+140h+Reserved], r13; Reserved
0x18017a3fb  xor     r9d, r9d; LineNo
0x18017a3fe  xor     r8d, r8d; FileName
0x18017a401  xor     edx, edx; FunctionName
0x18017a403  xor     ecx, ecx; Expression
0x18017a405  call    _invoke_watson
```
