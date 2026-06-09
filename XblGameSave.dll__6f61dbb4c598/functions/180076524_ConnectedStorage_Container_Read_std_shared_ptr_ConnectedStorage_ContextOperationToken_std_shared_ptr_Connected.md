# ConnectedStorage::Container::Read(std::shared_ptr<ConnectedStorage::ContextOperationToken>,std::shared_ptr<ConnectedStorage::ReadData>)

- ea: `0x180076524`
- end: `0x1800767c3`
- name: `?Read@Container@ConnectedStorage@@QEAAXV?$shared_ptr@VContextOperationToken@ConnectedStorage@@@std@@V?$shared_ptr@UReadData@ConnectedStorage@@@4@@Z`
- size: `671`
- prototype: `__int64 __fastcall(ConnectedStorage::Container *this)`
- caller_count: `1`
- callee_count: `24`
- tags: ``

## callers

- `0x18005df14`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000cb9c`
- `0x180010f28`
- `0x1800113bc`
- `0x180011b94`
- `0x180012238`
- `0x1800124d0`
- `0x1800125ec`
- `0x180014e44`
- `0x180014e58`
- `0x1800150a8`
- `0x1800190f0`
- `0x18003ea50`
- `0x18005ca98`
- `0x18005caa8`
- `0x180075528`
- `0x180075c60`
- `0x180076524`
- `0x180077700`
- `0x180077738`
- `0x18007ac24`
- `0x180084ee0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800766d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800766d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800766b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800766b4`

## string_xrefs

- `0x1800767b1`: `Container::Read - TryGetAtom`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall ConnectedStorage::Container::Read(ConnectedStorage::Container *this, HSTRING a2, HSTRING a3)
{
  HSTRING *v6; // rdi
  HSTRING *v7; // r12
  HSTRING *v8; // rax
  __int64 v9; // rbx
  const struct ConnectedStorage::ContextDesc *v10; // rax
  __int128 v11; // xmm6
  std::_Ref_count_base *v12; // rcx
  std::_Ref_count_base *v13; // rcx
  const struct ConnectedStorage::ContextDesc *v14; // rax
  const unsigned __int16 *v15; // r8
  const unsigned __int16 *RawBuffer; // r14
  const struct _GUID *Guid; // rsi
  ConnectedStorage::Container *v18; // rcx
  ConnectedStorage::SimpleHStringWrapper *Name; // rax
  const unsigned __int16 *v20; // rdi
  ConnectedStorage::SimpleHStringWrapper *Xuid; // rax
  unsigned int v22; // ebx
  ConnectedStorage::SimpleHStringWrapper *Scid; // rax
  unsigned int v24; // eax
  int v25; // edx
  int v26; // ecx
  HSTRING string; // [rsp+48h] [rbp-C0h] BYREF
  HSTRING newString[4]; // [rsp+50h] [rbp-B8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+70h] [rbp-98h] BYREF
  HSTRING v30[6]; // [rsp+80h] [rbp-88h] BYREF
  HSTRING v31; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v32[48]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v33; // [rsp+E8h] [rbp-20h]
  _BYTE v34[8]; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v35; // [rsp+F8h] [rbp-10h]
  HSTRING v36[6]; // [rsp+118h] [rbp+10h] BYREF
  HSTRING v37; // [rsp+148h] [rbp+40h] BYREF
  __int128 v38; // [rsp+150h] [rbp+48h]
  __int64 v39; // [rsp+160h] [rbp+58h] BYREF
  _QWORD v40[3]; // [rsp+170h] [rbp+68h] BYREF

  newString[2] = a2;
  newString[3] = a3;
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 56),
    (char *)a3);
  v6 = *(HSTRING **)(*(_QWORD *)a3 + 160LL);
  v7 = *(HSTRING **)(*(_QWORD *)a3 + 168LL);
  while ( v6 != v7 )
  {
    v8 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(newString, v6);
    ConnectedStorage::BlobRecords::TryGetAtom((char *)this + 104, v34, v8);
    if ( !v35 || !*(_DWORD *)(v35 + 8) )
    {
      v14 = (const struct ConnectedStorage::ContextDesc *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5)
                                                                                            + 8LL))(*((_QWORD *)this + 5));
      ConnectedStorage::ContextDesc::ContextDesc(&v31, v14);
      if ( (ConnectedStorageEnableBits & 4) != 0 )
      {
        RawBuffer = ConnectedStorage::SimpleHStringWrapper::GetRawBuffer((ConnectedStorage::SimpleHStringWrapper *)v6);
        Guid = ConnectedStorage::Container::GetGuid(this);
        Name = ConnectedStorage::Container::GetName(v18);
        v20 = ConnectedStorage::SimpleHStringWrapper::GetRawBuffer(Name);
        Xuid = ConnectedStorage::ContextDesc::GetXuid((ConnectedStorage::ContextDesc *)&v31);
        v22 = (unsigned int)ConnectedStorage::SimpleHStringWrapper::GetRawBuffer(Xuid);
        Scid = ConnectedStorage::ContextDesc::GetScid((ConnectedStorage::ContextDesc *)&v31);
        v24 = (unsigned int)ConnectedStorage::SimpleHStringWrapper::GetRawBuffer(Scid);
        McTemplateU0zzzjz_EventWriteTransfer(v26, v25, v24, v22, (__int64)v20, (__int64)Guid, (__int64)RawBuffer);
      }
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80830008LL, (int)L"Container::Read - TryGetAtom", v15);
    }
    v9 = *(_QWORD *)a3;
    ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v31, v6);
    ConnectedStorage::Atom::Atom((ConnectedStorage::Atom *)v32, (const struct ConnectedStorage::Atom *)v34);
    std::vector<std::pair<ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::Atom>>::push_back(v9 + 184, &v31);
    std::pair<ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::Atom>::~pair<ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::Atom>(&v31);
    ConnectedStorage::Atom::~Atom((ConnectedStorage::Atom *)v34);
    ++v6;
  }
  v10 = (const struct ConnectedStorage::ContextDesc *)(*(__int64 (__fastcall **)(ConnectedStorage::Container *))(*(_QWORD *)this + 48LL))(this);
  ConnectedStorage::ContextDesc::ContextDesc(v30, v10);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, *((HSTRING **)this + 6));
  v11 = *(_OWORD *)(*((_QWORD *)this + 6) + 32LL);
  newString[1] = (HSTRING)&v31;
  ConnectedStorage::ContextDesc::ContextDesc(v36, (const struct ConnectedStorage::ContextDesc *)v30);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v37, &string);
  v38 = v11;
  std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(&v39, a2);
  std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(v40, a3);
  v33 = 0;
  v33 = std::_Global_new_std::_Func_impl_no_alloc__lambda_3321a51f527ae8d4eb078e5acabc742d__void___lambda_3321a51f527ae8d4eb078e5acabc742d___(v36);
  ConnectedStorage::ExecuteOnThreadPool(&v31);
  lambda_3321a51f527ae8d4eb078e5acabc742d_::__lambda_3321a51f527ae8d4eb078e5acabc742d_((ConnectedStorage::ContextDesc *)v36);
  WindowsDeleteString(string);
  string = 0;
  ConnectedStorage::ContextDesc::~ContextDesc(v30);
  LeaveCriticalSection(lpCriticalSection[0]);
  v12 = (std::_Ref_count_base *)*((_QWORD *)a2 + 1);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  v13 = (std::_Ref_count_base *)*((_QWORD *)a3 + 1);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
}

```

## disassembly

```asm
0x180076524  mov     rax, rsp
0x180076527  mov     [rax+20h], rbx
0x18007652b  push    rbp
0x18007652c  push    rsi
0x18007652d  push    rdi
0x18007652e  push    r12
0x180076530  push    r13
0x180076532  push    r14
0x180076534  push    r15
0x180076536  lea     rbp, [rax-0D8h]
0x18007653d  sub     rsp, 1A0h
0x180076544  movaps  xmmword ptr [rax-48h], xmm6
0x180076548  mov     rax, cs:__security_cookie
0x18007654f  xor     rax, rsp
0x180076552  mov     [rbp+0D0h+var_50], rax
0x180076559  mov     rsi, r8
0x18007655c  mov     r14, rdx
0x18007655f  mov     r15, rcx
0x180076562  mov     [rsp+1D0h+var_178], rdx
0x180076567  mov     [rsp+1D0h+var_170], r8
0x18007656c  lea     rdx, [rcx+38h]; struct ConnectedStorage::Mutex *
0x180076570  lea     rcx, [rsp+1D0h+lpCriticalSection]; this
0x180076575  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18007657a  nop
0x18007657b  mov     rax, [rsi]
0x18007657e  mov     rdi, [rax+0A0h]
0x180076585  mov     r12, [rax+0A8h]
0x18007658c  jmp     short loc_180076609
0x18007658e  mov     rdx, rdi; struct ConnectedStorage::SimpleHStringWrapper *
0x180076591  lea     rcx, [rsp+1D0h+newString]; newString
0x180076596  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18007659b  mov     r8, rax
0x18007659e  lea     rdx, [rbp+0D0h+var_E8]
0x1800765a2  lea     rcx, [r15+68h]
0x1800765a6  call    ?TryGetAtom@BlobRecords@ConnectedStorage@@QEAA?AVAtom@2@VSimpleHStringWrapper@2@@Z; ConnectedStorage::BlobRecords::TryGetAtom(ConnectedStorage::SimpleHStringWrapper)
0x1800765ab  nop
0x1800765ac  mov     rax, [rbp+0D0h+var_E0]
0x1800765b0  test    rax, rax
0x1800765b3  jz      loc_180076726
0x1800765b9  cmp     dword ptr [rax+8], 0
0x1800765bd  jz      loc_180076726
0x1800765c3  mov     rbx, [rsi]
0x1800765c6  mov     rdx, rdi; struct ConnectedStorage::SimpleHStringWrapper *
0x1800765c9  lea     rcx, [rbp+0D0h+var_128]; newString
0x1800765cd  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x1800765d2  nop
0x1800765d3  lea     rdx, [rbp+0D0h+var_E8]; struct ConnectedStorage::Atom *
0x1800765d7  lea     rcx, [rbp+0D0h+var_120]; this
0x1800765db  call    ??0Atom@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::Atom::Atom(ConnectedStorage::Atom const &)
0x1800765e0  nop
0x1800765e1  lea     rdx, [rbp+0D0h+var_128]
0x1800765e5  lea     rcx, [rbx+0B8h]
0x1800765ec  call    ?push_back@?$vector@U?$pair@VSimpleHStringWrapper@ConnectedStorage@@VAtom@2@@std@@V?$allocator@U?$pair@VSimpleHStringWrapper@ConnectedStorage@@VAtom@2@@std@@@2@@std@@QEAAX$$QEAU?$pair@VSimpleHStringWrapper@ConnectedStorage@@VAtom@2@@2@@Z; std::vector<std::pair<ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::Atom>>::push_back(std::pair<ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::Atom> &&)
0x1800765f1  nop
0x1800765f2  lea     rcx, [rbp+0D0h+var_128]
0x1800765f6  call    ??1?$pair@VSimpleHStringWrapper@ConnectedStorage@@VAtom@2@@std@@QEAA@XZ; std::pair<ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::Atom>::~pair<ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::Atom>(void)
0x1800765fb  nop
0x1800765fc  lea     rcx, [rbp+0D0h+var_E8]; this
0x180076600  call    ??1Atom@ConnectedStorage@@QEAA@XZ; ConnectedStorage::Atom::~Atom(void)
0x180076605  add     rdi, 8
0x180076609  cmp     rdi, r12
0x18007660c  jnz     short loc_18007658E
0x18007660e  mov     rax, [r15]
0x180076611  mov     rcx, r15
0x180076614  mov     rax, [rax+30h]
0x180076618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007661d  mov     rdx, rax; struct ConnectedStorage::ContextDesc *
0x180076620  lea     rcx, [rsp+1D0h+var_158]; this
0x180076625  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::ContextDesc const &)
0x18007662a  nop
0x18007662b  mov     rdx, [r15+30h]; struct ConnectedStorage::SimpleHStringWrapper *
0x18007662f  lea     rcx, [rsp+1D0h+string]; newString
0x180076634  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x180076639  nop
0x18007663a  mov     rax, [r15+30h]
0x18007663e  movups  xmm6, xmmword ptr [rax+20h]
0x180076642  lea     rax, [rbp+0D0h+var_128]
0x180076646  mov     [rsp+1D0h+var_180], rax
0x18007664b  lea     rdx, [rsp+1D0h+var_158]; struct ConnectedStorage::ContextDesc *
0x180076650  lea     rcx, [rbp+0D0h+var_C0]; this
0x180076654  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::ContextDesc const &)
0x180076659  nop
0x18007665a  lea     rdx, [rsp+1D0h+string]; struct ConnectedStorage::SimpleHStringWrapper *
0x18007665f  lea     rcx, [rbp+0D0h+var_90]; newString
0x180076663  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x180076668  movdqu  [rbp+0D0h+var_88], xmm6
0x18007666d  mov     rdx, r14
0x180076670  lea     rcx, [rbp+0D0h+var_78]
0x180076674  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x180076679  mov     rdx, rsi
0x18007667c  lea     rcx, [rbp+0D0h+var_68]
0x180076680  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x180076685  nop
0x180076686  mov     [rbp+0D0h+var_F0], 0
0x18007668e  lea     rcx, [rbp+0D0h+var_C0]
0x180076692  call    std___Global_new_std___Func_impl_no_alloc__lambda_3321a51f527ae8d4eb078e5acabc742d__void___lambda_3321a51f527ae8d4eb078e5acabc742d___
0x180076697  mov     [rbp+0D0h+var_F0], rax
0x18007669b  lea     rcx, [rbp+0D0h+var_128]
0x18007669f  call    ?ExecuteOnThreadPool@ConnectedStorage@@YAXV?$function@$$A6AXXZ@std@@@Z; ConnectedStorage::ExecuteOnThreadPool(std::function<void (void)>)
0x1800766a4  nop
0x1800766a5  lea     rcx, [rbp+0D0h+var_C0]; this
0x1800766a9  call    _lambda_3321a51f527ae8d4eb078e5acabc742d_____lambda_3321a51f527ae8d4eb078e5acabc742d_
0x1800766ae  nop
0x1800766af  mov     rcx, [rsp+1D0h+string]; string
0x1800766b4  call    cs:__imp_WindowsDeleteString
0x1800766ba  mov     [rsp+1D0h+string], 0
0x1800766c3  lea     rcx, [rsp+1D0h+var_158]; this
0x1800766c8  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x1800766cd  nop
0x1800766ce  mov     rcx, [rsp+1D0h+lpCriticalSection]; lpCriticalSection
0x1800766d3  call    cs:__imp_LeaveCriticalSection
0x1800766d9  nop
0x1800766da  mov     rcx, [r14+8]; this
0x1800766de  test    rcx, rcx
0x1800766e1  jz      short loc_1800766E9
0x1800766e3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800766e8  nop
0x1800766e9  mov     rcx, [rsi+8]; this
0x1800766ed  test    rcx, rcx
0x1800766f0  jz      short loc_1800766F7
0x1800766f2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800766f7  mov     rcx, [rbp+0D0h+var_50]
0x1800766fe  xor     rcx, rsp; StackCookie
0x180076701  call    __security_check_cookie
0x180076706  lea     r11, [rsp+1D0h+var_30]
0x18007670e  mov     rbx, [r11+58h]
0x180076712  movaps  xmm6, xmmword ptr [r11-10h]
0x180076717  mov     rsp, r11
0x18007671a  pop     r15
0x18007671c  pop     r14
0x18007671e  pop     r13
0x180076720  pop     r12
0x180076722  pop     rdi
0x180076723  pop     rsi
0x180076724  pop     rbp
0x180076725  retn
0x180076726  mov     rcx, [r15+28h]
0x18007672a  mov     rax, [rcx]
0x18007672d  mov     rax, [rax+8]
0x180076731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076736  mov     rdx, rax; struct ConnectedStorage::ContextDesc *
0x180076739  lea     rcx, [rbp+0D0h+var_128]; this
0x18007673d  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::ContextDesc const &)
0x180076742  nop
0x180076743  test    cs:ConnectedStorageEnableBits, 4
0x18007674a  jz      short loc_1800767B1
0x18007674c  mov     rcx, rdi; this
0x18007674f  call    ?GetRawBuffer@SimpleHStringWrapper@ConnectedStorage@@QEBAPEBGXZ; ConnectedStorage::SimpleHStringWrapper::GetRawBuffer(void)
0x180076754  mov     r14, rax
0x180076757  mov     rcx, r15; this
0x18007675a  call    ?GetGuid@Container@ConnectedStorage@@QEBAAEBU_GUID@@XZ; ConnectedStorage::Container::GetGuid(void)
0x18007675f  mov     rsi, rax
0x180076762  call    ?GetName@Container@ConnectedStorage@@QEBAAEBVSimpleHStringWrapper@2@XZ; ConnectedStorage::Container::GetName(void)
0x180076767  mov     rcx, rax; this
0x18007676a  call    ?GetRawBuffer@SimpleHStringWrapper@ConnectedStorage@@QEBAPEBGXZ; ConnectedStorage::SimpleHStringWrapper::GetRawBuffer(void)
0x18007676f  mov     rdi, rax
0x180076772  lea     rcx, [rbp+0D0h+var_128]; this
0x180076776  call    ?GetXuid@ContextDesc@ConnectedStorage@@QEBAAEBVSimpleHStringWrapper@2@XZ; ConnectedStorage::ContextDesc::GetXuid(void)
0x18007677b  mov     rcx, rax; this
0x18007677e  call    ?GetRawBuffer@SimpleHStringWrapper@ConnectedStorage@@QEBAPEBGXZ; ConnectedStorage::SimpleHStringWrapper::GetRawBuffer(void)
0x180076783  mov     rbx, rax
0x180076786  lea     rcx, [rbp+0D0h+var_128]; this
0x18007678a  call    ?GetScid@ContextDesc@ConnectedStorage@@QEBAAEBVSimpleHStringWrapper@2@XZ; ConnectedStorage::ContextDesc::GetScid(void)
0x18007678f  mov     rcx, rax; this
0x180076792  call    ?GetRawBuffer@SimpleHStringWrapper@ConnectedStorage@@QEBAPEBGXZ; ConnectedStorage::SimpleHStringWrapper::GetRawBuffer(void)
0x180076797  mov     [rsp+1D0h+var_1A0], r14
0x18007679c  mov     [rsp+1D0h+var_1A8], rsi
0x1800767a1  mov     [rsp+1D0h+var_1B0], rdi
0x1800767a6  mov     r9, rbx
0x1800767a9  mov     r8, rax
0x1800767ac  call    McTemplateU0zzzjz_EventWriteTransfer
0x1800767b1  lea     rdx, aContainerReadT; "Container::Read - TryGetAtom"
0x1800767b8  mov     ecx, 80830008h; this
0x1800767bd  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
