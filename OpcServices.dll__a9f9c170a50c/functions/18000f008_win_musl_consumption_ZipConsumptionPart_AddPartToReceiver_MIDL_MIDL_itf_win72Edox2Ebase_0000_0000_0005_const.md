# win_musl::consumption::ZipConsumptionPart::AddPartToReceiver(__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 const *)

- ea: `0x18000f008`
- end: `0x18000f644`
- name: `?AddPartToReceiver@ZipConsumptionPart@consumption@win_musl@@AEAAXPEBU__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005@@@Z`
- size: `1596`
- prototype: `void __fastcall(win_musl::consumption::ZipConsumptionPart *__hidden this, const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000edbc`
- `0x180017e6c`

## callees

- `0x1800016b0`
- `0x18000405c`
- `0x18000ccec`
- `0x18000f008`
- `0x18000f64c`
- `0x18000fa84`
- `0x180015114`
- `0x1800155e8`
- `0x1800156a4`
- `0x180015a68`
- `0x180015af4`
- `0x180018c2c`
- `0x18001c5d0`
- `0x18001ca9c`
- `0x1800517a0`
- `0x18009c21c`
- `0x1800cd38c`
- `0x1800cdb60`
- `0x1800d04d8`
- `0x1800d5fe4`
- `0x1800e810c`
- `0x18010b29c`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000f4ab`
- `msvcrt!memcpy_s` at `0x18000f4ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f1db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f1db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f292`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f292`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f1c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f1c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall win_musl::consumption::ZipConsumptionPart::AddPartToReceiver(
        win_musl::consumption::ZipConsumptionPart *this,
        const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *a2)
{
  const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *v2; // r12
  __int64 v4; // rsi
  _QWORD *v5; // rax
  int v6; // edx
  const char *v7; // r8
  unsigned int v8; // r9d
  _QWORD *v9; // rbx
  void *v10; // rax
  __int64 v11; // rbx
  unsigned int v12; // r15d
  bool v13; // dl
  win_dox *v14; // rcx
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, _QWORD *, _QWORD, __int128 *, __int64, const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *); // r14
  __int64 v17; // rcx
  _QWORD *v18; // rdx
  signed int v19; // esi
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  _QWORD *v27; // r14
  unsigned __int64 v28; // r15
  _QWORD *v29; // r8
  unsigned __int64 v30; // rdx
  _QWORD *v31; // rcx
  const wchar_t *v32; // rax
  __int64 v33; // r10
  _QWORD *v34; // r9
  __int128 v35; // [rsp+48h] [rbp-C0h] BYREF
  const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *v36; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v37; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v38; // [rsp+70h] [rbp-98h] BYREF
  win_musl::consumption::ZipConsumptionPart *v39; // [rsp+80h] [rbp-88h] BYREF
  __int64 v40; // [rsp+88h] [rbp-80h]
  __int128 *v41; // [rsp+90h] [rbp-78h] BYREF
  _QWORD *v42; // [rsp+98h] [rbp-70h]
  __int64 v43; // [rsp+A0h] [rbp-68h] BYREF
  win_musl::consumption::ZipConsumptionPart *v44; // [rsp+A8h] [rbp-60h]
  __int64 v45; // [rsp+B0h] [rbp-58h]
  _BYTE v46[48]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v48[160]; // [rsp+128h] [rbp+20h] BYREF
  wchar_t v49[512]; // [rsp+1C8h] [rbp+C0h] BYREF

  v45 = -2;
  v2 = a2;
  v36 = a2;
  if ( *((_BYTE *)this + 152) )
    return;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
  {
    v32 = win_musl::StringOfCompressionOptions(*((_DWORD *)this + 14));
    v34 = (_QWORD *)((char *)this + 24);
    if ( *((_QWORD *)this + 6) >= 8u )
      v34 = (_QWORD *)*v34;
    WPP_SF_SS(
      *(_QWORD *)(v33 + 56),
      11,
      (unsigned int)&WPP_030c92eb782e391dc47680cbab48d7b3_Traceguids,
      (_DWORD)v34,
      (__int64)v32);
  }
  v44 = 0;
  v39 = this;
  v4 = *((_QWORD *)this + 1);
  v43 = v4;
  if ( !v4 )
  {
    win_scope::close_delete::close<win_musl::CallingThread>(&v39);
    win_scope::report_policy_throw::report_init_failure();
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)(v4 + 8)) == 1 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 12));
  v44 = this;
  v5 = operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v5;
  if ( !v5 )
    SplException::RealThrowFromHR((SplException *)0x8007000ELL, v6, v7, v8);
  v39 = (win_musl::consumption::ZipConsumptionPart *)v5;
  v41 = &v35;
  v35 = 0;
  if ( _InterlockedIncrement((volatile signed __int32 *)(v4 + 8)) == 1 )
    _InterlockedAdd((volatile signed __int32 *)(v4 + 12), 1u);
  *(_QWORD *)&v35 = v4;
  *((_QWORD *)&v35 + 1) = this;
  v41 = &v35;
  v37 = 0;
  v21 = *((_QWORD *)this + 13);
  if ( v21 )
  {
    v22 = *((_QWORD *)this + 14);
    if ( _InterlockedIncrement((volatile signed __int32 *)(v21 + 8)) == 1 )
      _InterlockedAdd((volatile signed __int32 *)(v21 + 12), 1u);
    *(_QWORD *)&v37 = v21;
    *((_QWORD *)&v37 + 1) = v22;
  }
  *(_QWORD *)&v38 = &v37;
  *v5 = 0;
  v5[1] = 0;
  v23 = v37;
  if ( (_QWORD)v37 )
  {
    v24 = *((_QWORD *)&v37 + 1);
    if ( _InterlockedIncrement((volatile signed __int32 *)(v37 + 8)) == 1 )
      _InterlockedAdd((volatile signed __int32 *)(v23 + 12), 1u);
    *v5 = v23;
    v5[1] = v24;
  }
  v5[2] = 0;
  v5[3] = -1;
  v5[4] = 0;
  v5[5] = 0;
  v25 = v35;
  if ( (_QWORD)v35 )
  {
    v26 = *((_QWORD *)&v35 + 1);
    if ( _InterlockedIncrement((volatile signed __int32 *)(v35 + 8)) == 1 )
      _InterlockedAdd((volatile signed __int32 *)(v25 + 12), 1u);
    v5[4] = v25;
    v5[5] = v26;
  }
  v5[10] = 7;
  v27 = v5 + 7;
  v5[9] = 0;
  *((_WORD *)v5 + 28) = 0;
  v28 = *((_QWORD *)this + 5);
  if ( v5 + 6 == (_QWORD *)((char *)this + 16) )
  {
    std::wstring::erase(v5 + 6, *((_QWORD *)this + 5), -1);
    std::wstring::erase(v9 + 6, 0, 0);
  }
  else
  {
    if ( v28 > 0x7FFFFFFFFFFFFFFELL )
      std::_String_base::_Xlen();
    if ( v5[10] >= v28 )
    {
      if ( !v28 )
      {
        if ( v5[10] >= 8u )
          v27 = (_QWORD *)*v27;
        v5[9] = 0;
        *(_WORD *)v27 = 0;
        goto LABEL_58;
      }
      goto LABEL_51;
    }
    std::wstring::_Copy(v5 + 6, *((_QWORD *)this + 5), v5[9]);
    if ( v28 )
    {
LABEL_51:
      v29 = (_QWORD *)((char *)this + 24);
      if ( *((_QWORD *)this + 6) >= 8u )
        v29 = (_QWORD *)*v29;
      v30 = v9[10];
      if ( v30 < 8 )
        v31 = v9 + 7;
      else
        v31 = (_QWORD *)*v27;
      memcpy_s(v31, 2 * v30, v29, 2 * v28);
      if ( v9[10] >= 8u )
        v27 = (_QWORD *)*v27;
      v9[9] = v28;
      *((_WORD *)v27 + v28) = 0;
      v2 = v36;
    }
  }
LABEL_58:
  *((_BYTE *)v9 + 88) = 0;
  if ( *((_QWORD *)&v37 + 1) && (_QWORD)v37 )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v37);
    v37 = 0;
  }
  if ( *((_QWORD *)&v35 + 1) && (_QWORD)v35 )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v35);
    v35 = 0;
  }
  v42 = 0;
  v36 = (const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *)v9;
  v10 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v10 )
  {
    win_scope::close_delete::close<win_musl::consumption::ZipConsumptionByteCollection>(&v36);
    win_scope::report_policy_throw::report_init_failure();
  }
  *((_QWORD *)v10 + 1) = 0;
  *(_QWORD *)v10 = &win_scope::counted_strong_weak<win_musl::consumption::ZipConsumptionByteCollection *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
  *((_QWORD *)v10 + 2) = v9;
  v41 = (__int128 *)v10;
  if ( _InterlockedIncrement((volatile signed __int32 *)v10 + 2) == 1 )
    _InterlockedAdd((volatile signed __int32 *)v10 + 3, 1u);
  v42 = v9;
  v38 = 0;
  if ( _InterlockedIncrement((volatile signed __int32 *)v10 + 2) == 1 )
    _InterlockedAdd((volatile signed __int32 *)v10 + 3, 1u);
  *(_QWORD *)&v38 = v10;
  *((_QWORD *)&v38 + 1) = v9;
  win_dox::CreateInstanceFromInner<IByteCollection,win_scope::scope<win_musl::consumption::ZipConsumptionByteCollection *,win_scope::const_policies<win_scope::shared_policies>>>(
    &v39,
    &v38);
  v11 = *((_QWORD *)this + 14);
  v12 = *((_DWORD *)this + 14);
  *(_QWORD *)&v38 = v11;
  EnterCriticalSection((LPCRITICAL_SECTION)v11);
  v14 = (win_dox *)*(unsigned int *)(v11 + 44);
  *(_DWORD *)(v11 + 44) = (_DWORD)v14 + 1;
  if ( !(_DWORD)v14 )
    *(_DWORD *)(v11 + 40) = GetCurrentThreadId();
  LOBYTE(v14) = *(_BYTE *)(v11 + 80);
  win_dox::ThrowIfFailed(v14, v13);
  if ( !*(_QWORD *)(v11 + 64) || !*(_QWORD *)(v11 + 72) || dword_1801C4E30 == -1 )
  {
    win_musl::DebugLogHelper(
      "(no filename)",
      &word_18013A0B6,
      124,
      1024,
      -2147418113,
      L"ZipDeinterleaverState::AddOpcStream() is called at invalid state");
    std::string::string(v46, "Program has entered an unexpected state");
    std::logic_error::logic_error(pExceptionObject, v46);
    throw (std::logic_error *)pExceptionObject;
  }
  v15 = *(_QWORD *)(*(_QWORD *)(v11 + 72) + 16LL);
  v16 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, __int128 *, __int64, const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *))(*(_QWORD *)v15 + 48LL);
  v17 = *(_QWORD *)win_dox::StartSendBase<IByteSender>::GetInterface(&v39, &v36);
  v18 = (_QWORD *)((char *)this + 24);
  if ( *((_QWORD *)this + 6) >= 8u )
    v18 = (_QWORD *)*v18;
  v35 = *((_OWORD *)this + 4);
  v19 = v16(v15, v18, v12, &v35, v17, v2);
  if ( v36 )
    (*(void (__fastcall **)(const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v19 < 0 )
  {
    memset_0(v49, 0, sizeof(v49));
    StringCchPrintfW(v49, 0x200u, L"Call to AddOpcStream failed with HResult 0x%X.", (unsigned int)v19);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v48,
      0x65u,
      v19,
      (struct win_musl::TStringEllipseBase *)v49);
    throw (SplException::THResultException *)v48;
  }
  if ( (*(_DWORD *)(v11 + 44))-- == 1 )
    *(_DWORD *)(v11 + 40) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v11);
  *((_BYTE *)this + 152) = 1;
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v41);
  win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v43);
}

```

## disassembly

```asm
0x18000f008  mov     rax, rsp
0x18000f00b  push    rbp
0x18000f00c  push    rsi
0x18000f00d  push    rdi
0x18000f00e  push    r12
0x18000f010  push    r13
0x18000f012  push    r14
0x18000f014  push    r15
0x18000f016  lea     rbp, [rax-508h]
0x18000f01d  sub     rsp, 5D0h
0x18000f024  mov     [rbp+500h+var_558], 0FFFFFFFFFFFFFFFEh
0x18000f02c  mov     [rax+18h], rbx
0x18000f030  mov     rax, cs:__security_cookie
0x18000f037  xor     rax, rsp
0x18000f03a  mov     [rbp+500h+var_40], rax
0x18000f041  mov     r12, rdx
0x18000f044  mov     qword ptr [rsp+600h+var_5B0], rdx
0x18000f049  mov     rdi, rcx
0x18000f04c  xor     r15d, r15d
0x18000f04f  cmp     [rcx+98h], r15b
0x18000f056  jz      short loc_18000F082
0x18000f058  mov     rcx, [rbp+500h+var_40]
0x18000f05f  xor     rcx, rsp; StackCookie
0x18000f062  call    __security_check_cookie
0x18000f067  mov     rbx, [rsp+600h+arg_10]
0x18000f06f  add     rsp, 5D0h
0x18000f076  pop     r15
0x18000f078  pop     r14
0x18000f07a  pop     r13
0x18000f07c  pop     r12
0x18000f07e  pop     rdi
0x18000f07f  pop     rsi
0x18000f080  pop     rbp
0x18000f081  retn
0x18000f082  lea     rax, WPP_GLOBAL_Control
0x18000f089  mov     r10, cs:WPP_GLOBAL_Control
0x18000f090  cmp     r10, rax
0x18000f093  jz      short loc_18000F0A0
0x18000f095  test    byte ptr [r10+44h], 4
0x18000f09a  jnz     loc_18000F568
0x18000f0a0  mov     [rbp+500h+var_560], r15
0x18000f0a4  mov     [rsp+600h+var_588], rdi
0x18000f0a9  mov     rsi, [rdi+8]
0x18000f0ad  mov     [rbp+500h+var_568], rsi
0x18000f0b1  test    rsi, rsi
0x18000f0b4  jz      short loc_18000F0F9
0x18000f0b6  mov     eax, 1
0x18000f0bb  lock xadd [rsi+8], eax
0x18000f0c0  inc     eax
0x18000f0c2  cmp     eax, 1
0x18000f0c5  jz      short loc_18000F0F3
0x18000f0c7  mov     [rbp+500h+var_560], rdi
0x18000f0cb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f0d2  mov     ecx, 60h ; '`'; unsigned __int64
0x18000f0d7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f0dc  mov     rbx, rax
0x18000f0df  test    rax, rax
0x18000f0e2  jnz     loc_18000F344
0x18000f0e8  mov     ecx, 8007000Eh; this
0x18000f0ed  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x18000f0f3  lock inc dword ptr [rsi+0Ch]
0x18000f0f7  jmp     short loc_18000F0C7
0x18000f0f9  lea     rcx, [rsp+600h+var_588]
0x18000f0fe  call    ??$close@VCallingThread@win_musl@@@close_delete@win_scope@@SAXPEAPEAVCallingThread@win_musl@@@Z; win_scope::close_delete::close<win_musl::CallingThread>(win_musl::CallingThread * *)
0x18000f103  call    ?report_init_failure@report_policy_throw@win_scope@@SAXXZ; win_scope::report_policy_throw::report_init_failure(void)
0x18000f109  cmp     qword ptr [rsp+600h+var_5C8+8], r13
0x18000f10e  jz      short loc_18000F123
0x18000f110  lea     rcx, [rsp+600h+var_5C8+8]
0x18000f115  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18000f11a  xorps   xmm0, xmm0
0x18000f11d  movdqu  [rsp+600h+var_5C8+8], xmm0
0x18000f123  mov     [rbp+500h+var_570], r13
0x18000f127  mov     qword ptr [rsp+600h+var_5B0], rbx
0x18000f12c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f133  mov     ecx, 18h; unsigned __int64
0x18000f138  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f13d  mov     rdx, rax
0x18000f140  test    rax, rax
0x18000f143  jz      loc_18000F634
0x18000f149  mov     qword ptr [rax+8], 0
0x18000f151  lea     rax, ??_7?$counted_strong_weak@PEAVZipConsumptionByteCollection@consumption@win_musl@@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::counted_strong_weak<win_musl::consumption::ZipConsumptionByteCollection *,win_scope::const_policies<win_scope::resource_policies>>::`vftable'
0x18000f158  mov     [rdx], rax
0x18000f15b  mov     [rdx+10h], rbx
0x18000f15f  mov     [rbp+500h+var_578], rdx
0x18000f163  mov     r9d, 1
0x18000f169  mov     ecx, r9d
0x18000f16c  lock xadd [rdx+8], ecx
0x18000f171  add     ecx, r9d
0x18000f174  cmp     ecx, r9d
0x18000f177  jz      loc_18000F2CE
0x18000f17d  mov     [rbp+500h+var_570], rbx
0x18000f181  xorps   xmm0, xmm0
0x18000f184  movdqu  [rsp+600h+var_5A0+8], xmm0
0x18000f18a  mov     eax, r9d
0x18000f18d  lock xadd [rdx+8], eax
0x18000f192  add     eax, r9d
0x18000f195  cmp     eax, r9d
0x18000f198  jz      loc_18000F2D8
0x18000f19e  mov     qword ptr [rsp+600h+var_5A0+8], rdx
0x18000f1a3  mov     [rsp+600h+var_590], rbx
0x18000f1a8  lea     rdx, [rsp+600h+var_5A0+8]
0x18000f1ad  lea     rcx, [rsp+600h+var_588]
0x18000f1b2  call    ??$CreateInstanceFromInner@UIByteCollection@@V?$scope@PEAVZipConsumptionByteCollection@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVByteCollection@0@V?$scope@PEAVZipConsumptionByteCollection@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IByteCollection,win_scope::scope<win_musl::consumption::ZipConsumptionByteCollection *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_musl::consumption::ZipConsumptionByteCollection *,win_scope::const_policies<win_scope::shared_policies>>)
0x18000f1b7  nop
0x18000f1b8  mov     rbx, [rdi+70h]
0x18000f1bc  mov     r15d, [rdi+38h]
0x18000f1c0  mov     qword ptr [rsp+600h+var_5A0+8], rbx
0x18000f1c5  mov     rcx, rbx; lpCriticalSection
0x18000f1c8  call    cs:__imp_EnterCriticalSection
0x18000f1ce  mov     ecx, [rbx+2Ch]
0x18000f1d1  lea     eax, [rcx+1]
0x18000f1d4  mov     [rbx+2Ch], eax
0x18000f1d7  test    ecx, ecx
0x18000f1d9  jnz     short loc_18000F1E4
0x18000f1db  call    cs:__imp_GetCurrentThreadId
0x18000f1e1  mov     [rbx+28h], eax
0x18000f1e4  mov     cl, [rbx+50h]; this
0x18000f1e7  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x18000f1ec  cmp     [rbx+40h], r13
0x18000f1f0  jz      loc_18000F2E2
0x18000f1f6  cmp     [rbx+48h], r13
0x18000f1fa  jz      loc_18000F2E2
0x18000f200  cmp     cs:dword_1801C4E30, 0FFFFFFFFh
0x18000f207  jz      loc_18000F2E2
0x18000f20d  mov     rax, [rbx+48h]
0x18000f211  mov     rsi, [rax+10h]
0x18000f215  mov     rax, [rsi]
0x18000f218  mov     r14, [rax+30h]
0x18000f21c  lea     rdx, [rsp+600h+var_5B0]
0x18000f221  lea     rcx, [rsp+600h+var_588]
0x18000f226  call    ?GetInterface@?$StartSendBase@UIByteSender@@@win_dox@@QEBA?AV?$scope@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::StartSendBase<IByteSender>::GetInterface(void)
0x18000f22b  nop
0x18000f22c  mov     rcx, [rax]
0x18000f22f  lea     rdx, [rdi+18h]
0x18000f233  cmp     qword ptr [rdi+30h], 8
0x18000f238  jb      short loc_18000F23D
0x18000f23a  mov     rdx, [rdx]
0x18000f23d  movups  xmm0, xmmword ptr [rdi+40h]
0x18000f241  movdqu  [rsp+600h+var_5C8+8], xmm0
0x18000f247  mov     qword ptr [rsp+600h+var_5D8], r12
0x18000f24c  mov     qword ptr [rsp+600h+var_5E0], rcx
0x18000f251  lea     r9, [rsp+600h+var_5C8+8]
0x18000f256  mov     r8d, r15d
0x18000f259  mov     rcx, rsi
0x18000f25c  mov     rax, r14
0x18000f25f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f264  mov     esi, eax
0x18000f266  mov     rcx, qword ptr [rsp+600h+var_5B0]
0x18000f26b  test    rcx, rcx
0x18000f26e  jz      short loc_18000F27D
0x18000f270  mov     rdx, [rcx]
0x18000f273  mov     rax, [rdx+10h]
0x18000f277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f27c  nop
0x18000f27d  test    esi, esi
0x18000f27f  js      loc_18000F5C5
0x18000f285  sub     dword ptr [rbx+2Ch], 1
0x18000f289  jnz     short loc_18000F28F
0x18000f28b  mov     [rbx+28h], r13d
0x18000f28f  mov     rcx, rbx; lpCriticalSection
0x18000f292  call    cs:__imp_LeaveCriticalSection
0x18000f298  mov     byte ptr [rdi+98h], 1
0x18000f29f  mov     rcx, [rbp+500h+var_580]
0x18000f2a3  test    rcx, rcx
0x18000f2a6  jz      short loc_18000F2B5
0x18000f2a8  mov     rax, [rcx]
0x18000f2ab  mov     rax, [rax+10h]
0x18000f2af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2b4  nop
0x18000f2b5  lea     rcx, [rbp+500h+var_578]
0x18000f2b9  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18000f2be  nop
0x18000f2bf  lea     rcx, [rbp+500h+var_568]
0x18000f2c3  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18000f2c8  nop
0x18000f2c9  jmp     loc_18000F058
0x18000f2ce  lock add [rdx+0Ch], r9d
0x18000f2d3  jmp     loc_18000F17D
0x18000f2d8  lock add [rdx+0Ch], r9d
0x18000f2dd  jmp     loc_18000F19E
0x18000f2e2  lea     rax, aZipdeinterleav; "ZipDeinterleaverState::AddOpcStream() i"...
0x18000f2e9  mov     qword ptr [rsp+600h+var_5D8], rax
0x18000f2ee  mov     [rsp+600h+var_5E0], 8000FFFFh
0x18000f2f6  mov     r9d, 400h
0x18000f2fc  mov     r8d, 7Ch ; '|'
0x18000f302  lea     rdx, word_18013A0B6
0x18000f309  lea     rcx, aNoFilename; "(no filename)"
0x18000f310  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x18000f315  lea     rdx, aProgramHasEnte; "Program has entered an unexpected state"
0x18000f31c  lea     rcx, [rbp+500h+var_550]
0x18000f320  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18000f325  nop
0x18000f326  lea     rdx, [rbp+500h+var_550]
0x18000f32a  lea     rcx, [rbp+500h+pExceptionObject]
0x18000f32e  call    ??0logic_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::logic_error::logic_error(std::string const &)
0x18000f333  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x18000f33a  lea     rcx, [rbp+500h+pExceptionObject]; pExceptionObject
0x18000f33e  call    _CxxThrowException_0
0x18000f344  mov     [rsp+600h+var_588], rbx
0x18000f349  lea     rax, [rsp+600h+var_5C8+8]
0x18000f34e  mov     [rbp+500h+var_578], rax
0x18000f352  xorps   xmm0, xmm0
0x18000f355  movdqu  [rsp+600h+var_5C8+8], xmm0
0x18000f35b  mov     r8d, 1
0x18000f361  mov     eax, r8d
0x18000f364  lock xadd [rsi+8], eax
0x18000f369  add     eax, r8d
0x18000f36c  cmp     eax, r8d
0x18000f36f  jz      loc_18000F501
0x18000f375  mov     qword ptr [rsp+600h+var_5C8+8], rsi
0x18000f37a  mov     [rsp+600h+var_5B8], rdi
0x18000f37f  lea     rax, [rsp+600h+var_5C8+8]
0x18000f384  mov     [rbp+500h+var_578], rax
0x18000f388  movdqu  [rsp+600h+var_5B0+8], xmm0
0x18000f38e  mov     rcx, [rdi+68h]
0x18000f392  test    rcx, rcx
0x18000f395  jz      short loc_18000F3B9
0x18000f397  mov     rdx, [rdi+70h]
0x18000f39b  mov     eax, r8d
0x18000f39e  lock xadd [rcx+8], eax
0x18000f3a3  add     eax, r8d
0x18000f3a6  cmp     eax, r8d
0x18000f3a9  jz      loc_18000F50B
0x18000f3af  mov     qword ptr [rsp+600h+var_5B0+8], rcx
0x18000f3b4  mov     qword ptr [rsp+600h+var_5A0], rdx
0x18000f3b9  lea     rax, [rsp+600h+var_5B0+8]
0x18000f3be  mov     qword ptr [rsp+600h+var_5A0+8], rax
0x18000f3c3  lea     r13, [rdi+10h]
0x18000f3c7  mov     [rbx], r15
0x18000f3ca  mov     [rbx+8], r15
0x18000f3ce  mov     rcx, qword ptr [rsp+600h+var_5B0+8]
0x18000f3d3  test    rcx, rcx
0x18000f3d6  jz      short loc_18000F3F8
0x18000f3d8  mov     rdx, qword ptr [rsp+600h+var_5A0]
0x18000f3dd  mov     eax, r8d
0x18000f3e0  lock xadd [rcx+8], eax
0x18000f3e5  add     eax, r8d
0x18000f3e8  cmp     eax, r8d
0x18000f3eb  jz      loc_18000F515
0x18000f3f1  mov     [rbx], rcx
0x18000f3f4  mov     [rbx+8], rdx
0x18000f3f8  mov     [rbx+10h], r15
0x18000f3fc  mov     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x18000f404  mov     [rbx+20h], r15
0x18000f408  mov     [rbx+28h], r15
0x18000f40c  mov     rcx, qword ptr [rsp+600h+var_5C8+8]
0x18000f411  test    rcx, rcx
0x18000f414  jz      short loc_18000F437
0x18000f416  mov     rdx, [rsp+600h+var_5B8]
0x18000f41b  mov     eax, r8d
0x18000f41e  lock xadd [rcx+8], eax
0x18000f423  add     eax, r8d
0x18000f426  cmp     eax, r8d
0x18000f429  jz      loc_18000F51F
0x18000f42f  mov     [rbx+20h], rcx
0x18000f433  mov     [rbx+28h], rdx
0x18000f437  lea     rsi, [rbx+30h]
0x18000f43b  mov     qword ptr [rsi+20h], 7
0x18000f443  lea     r14, [rsi+8]
0x18000f447  mov     [rsi+18h], r15
0x18000f44b  mov     [r14], r15w
0x18000f44f  mov     r15, [r13+18h]
0x18000f453  cmp     rsi, r13
0x18000f456  jz      loc_18000F59D
0x18000f45c  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000f466  cmp     r15, rax
0x18000f469  ja      loc_18000F5BB
0x18000f46f  cmp     [rsi+20h], r15
0x18000f473  jb      loc_18000F529
0x18000f479  test    r15, r15
0x18000f47c  jz      loc_18000F54E
0x18000f482  lea     r8, [r13+8]
0x18000f486  cmp     qword ptr [r13+20h], 8
0x18000f48b  jb      short loc_18000F490
0x18000f48d  mov     r8, [r8]; Source
0x18000f490  mov     rdx, [rsi+20h]
0x18000f494  cmp     rdx, 8
0x18000f498  jb      loc_18000F546
0x18000f49e  mov     rcx, [r14]; Destination
0x18000f4a1  lea     r12, [r15+r15]
0x18000f4a5  add     rdx, rdx; DestinationSize
0x18000f4a8  mov     r9, r12; SourceSize
0x18000f4ab  call    cs:__imp_memcpy_s
0x18000f4b1  cmp     qword ptr [rsi+20h], 8
0x18000f4b6  jb      short loc_18000F4BB
0x18000f4b8  mov     r14, [r14]
0x18000f4bb  mov     [rsi+18h], r15
0x18000f4bf  xor     r13d, r13d
0x18000f4c2  mov     [r12+r14], r13w
0x18000f4c7  mov     r12, qword ptr [rsp+600h+var_5B0]
0x18000f4cc  mov     [rbx+58h], r13b
0x18000f4d0  cmp     qword ptr [rsp+600h+var_5A0], r13
0x18000f4d5  jz      short loc_18000F4F1
0x18000f4d7  cmp     qword ptr [rsp+600h+var_5B0+8], r13
0x18000f4dc  jz      short loc_18000F4F1
0x18000f4de  lea     rcx, [rsp+600h+var_5B0+8]
0x18000f4e3  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18000f4e8  xorps   xmm0, xmm0
0x18000f4eb  movdqu  [rsp+600h+var_5B0+8], xmm0
0x18000f4f1  cmp     [rsp+600h+var_5B8], r13
  ... truncated ...
```
