# wpc::LogRecorder::LogRecorderChannel::LogRecorderChannel(wpc::LogRecorder::RecorderOptions,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800670c8`
- end: `0x1800676aa`
- name: `??0LogRecorderChannel@LogRecorder@wpc@@QEAA@W4RecorderOptions@12@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1506`
- prototype: `wpc::LogRecorder::LogRecorderChannel *__fastcall(wpc::LogRecorder::LogRecorderChannel *this, char, _QWORD *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180067034`

## callees

- `0x1800060a0`
- `0x1800082bc`
- `0x180008d50`
- `0x1800093ac`
- `0x180009a80`
- `0x180009de0`
- `0x18000bba8`
- `0x18000e880`
- `0x18001484c`
- `0x18001f4c8`
- `0x18003e060`
- `0x180040888`
- `0x1800591d4`
- `0x180059228`
- `0x18005a648`
- `0x180062d28`
- `0x180066b80`
- `0x180066cd8`
- `0x1800670c8`
- `0x180067c30`
- `0x18006826c`
- `0x180095dc0`
- `0x180095f48`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180067612`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180067612`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006755c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067576`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006755c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067576`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800671b0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800671b0`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18006750e`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18006750e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800674cf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800674cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
wpc::LogRecorder::LogRecorderChannel *__fastcall wpc::LogRecorder::LogRecorderChannel::LogRecorderChannel(
        wpc::LogRecorder::LogRecorderChannel *this,
        char a2,
        _QWORD *a3)
{
  int v6; // esi
  __int64 v7; // rcx
  __int64 *v8; // rax
  __int64 v9; // rdx
  volatile signed __int32 *v10; // rbx
  volatile signed __int32 *v11; // rbx
  __int64 *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rcx
  _QWORD *v20; // r9
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rax
  _QWORD *v25; // r9
  __int64 v26; // rax
  const WCHAR *v27; // rcx
  char *v28; // rbx
  __int64 v29; // rax
  int v30; // esi
  __int64 Current; // rcx
  Private::Format *v32; // rbx
  __int64 v33; // rax
  Private::Format *v34; // rbx
  __int64 v35; // rax
  _BYTE v37[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v38; // [rsp+44h] [rbp-BCh]
  HANDLE hFile; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME CreationTime; // [rsp+50h] [rbp-B0h] BYREF
  wpc::LogRecorder::LogRecorderChannel *v41; // [rsp+58h] [rbp-A8h]
  _BYTE v42[16]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v43; // [rsp+70h] [rbp-90h]
  __int128 v44; // [rsp+78h] [rbp-88h] BYREF
  char *v45; // [rsp+88h] [rbp-78h]
  __int64 v46; // [rsp+90h] [rbp-70h]
  _BYTE v47[8]; // [rsp+98h] [rbp-68h] BYREF
  volatile signed __int32 *v48; // [rsp+A0h] [rbp-60h]
  WCHAR v49[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v50[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v51[40]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v52[72]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v53[40]; // [rsp+168h] [rbp+68h] BYREF

  v41 = this;
  v43 = a3;
  v38 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v44, &SubKey, 0);
  IO::Path::Path(this, &v44);
  v44 = 0;
  v45 = 0;
  v46 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v44, &SubKey, 0);
  IO::Path::Path((char *)this + 32, &v44);
  DateTime::GetCurrent((char *)this + 64);
  DateTime::GetCurrent((char *)this + 76);
  *((_QWORD *)this + 11) = &LockBox<std::wstring,4294967295>::`vftable';
  *(_OWORD *)((char *)this + 104) = 0;
  *((_QWORD *)this + 15) = 0;
  v6 = 7;
  *((_QWORD *)this + 16) = 7;
  *((_WORD *)this + 52) = 0;
  InitializeSRWLock((PSRWLOCK)this + 12);
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  if ( (a2 & 2) != 0 )
  {
    CreationTime = (struct _FILETIME)this;
    v8 = (__int64 *)Threadpool::QueueTimerCallback__lambda_cbf5b5fb35637c87aa327395232b2d2a___(v7, v47, &CreationTime);
    v7 = *v8;
    v9 = v8[1];
    *v8 = 0;
    v8[1] = 0;
    *((_QWORD *)this + 17) = v7;
    v10 = (volatile signed __int32 *)*((_QWORD *)this + 18);
    *((_QWORD *)this + 18) = v9;
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    v11 = v48;
    if ( v48 )
    {
      if ( _InterlockedExchangeAdd(v48 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
  }
  if ( (a2 & 4) != 0 )
  {
    CreationTime = (struct _FILETIME)1200000000LL;
    hFile = this;
    v12 = (__int64 *)Threadpool::QueueTimerCallback__lambda_3be6e2c04033393fb85ca8d5efb592b1___(
                       v7,
                       v47,
                       &hFile,
                       &CreationTime);
    v13 = *v12;
    v14 = v12[1];
    *v12 = 0;
    v12[1] = 0;
    *((_QWORD *)this + 19) = v13;
    v15 = (volatile signed __int32 *)*((_QWORD *)this + 20);
    *((_QWORD *)this + 20) = v14;
    if ( v15 )
    {
      if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    v16 = v48;
    if ( v48 )
    {
      if ( _InterlockedExchangeAdd(v48 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
  }
  v37[0] = a2 & 1;
  lambda_6b4353445c5d79bdb48dad0cdc4514c8_::operator()(v37, v49);
  v38 = 1;
  if ( !IO::Directory::Exists((const struct Path *)v49) )
  {
    IO::Directory::Create((IO::Directory *)&v44, v49, 0);
    std::wstring::~wstring(&v44);
  }
  v19 = a3[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v19) < 8 )
    std::_Xlen_string();
  if ( a3[3] <= 7u )
    v20 = a3;
  else
    v20 = (_QWORD *)*a3;
  std::wstring::wstring(&v44, v17, v18, v20, v19, L"-old.log", 8);
  v38 = 3;
  IO::Path::Path(v47, &v44);
  v21 = IO::operator/(v50, v49, v47);
  std::wstring::operator=((char *)this + 32, v21);
  std::wstring::~wstring(v50);
  std::wstring::~wstring(v47);
  v24 = a3[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v24) < 4 )
    std::_Xlen_string();
  if ( a3[3] <= 7u )
    v25 = a3;
  else
    v25 = (_QWORD *)*a3;
  std::wstring::wstring(&v44, v22, v23, v25, v24, L".log", 4);
  v38 = 7;
  IO::Path::Path(v47, &v44);
  v26 = IO::operator/(v50, v49, v47);
  std::wstring::operator=(this, v26);
  std::wstring::~wstring(v50);
  std::wstring::~wstring(v47);
  if ( *((_QWORD *)this + 3) <= 7u )
    v27 = (const WCHAR *)this;
  else
    v27 = *(const WCHAR **)this;
  if ( (GetFileAttributesW(v27) & 0x10) != 0 )
    goto LABEL_40;
  IO::File::Open(&hFile, (const WCHAR *)this, 0);
  v6 = 23;
  v38 = 23;
  CreationTime = 0;
  v28 = (char *)hFile;
  if ( !GetFileTime(hFile, &CreationTime, 0, 0) )
  {
    if ( v28 && (unsigned __int64)(v28 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v28);
LABEL_40:
    v45 = 0;
    v30 = v6 | 8;
    v38 = v30;
    goto LABEL_41;
  }
  v29 = DateTime::DateTime(v42, &CreationTime);
  *(_QWORD *)((char *)&v44 + 4) = *(_QWORD *)v29;
  HIDWORD(v44) = *(_DWORD *)(v29 + 8);
  v45 = (char *)&v44 + 4;
  v30 = 31;
  v38 = 31;
  if ( v28 && (unsigned __int64)(v28 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v28);
LABEL_41:
  Current = DateTime::GetCurrent(v47);
  if ( v45 )
    Current = (__int64)v45;
  *(_QWORD *)((char *)this + 76) = *(_QWORD *)Current;
  *((_DWORD *)this + 21) = *(_DWORD *)(Current + 8);
  v44 = 0;
  v45 = 0;
  v46 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v44, L"Logging started for user:{0}, pid:{1}", 37);
  v32 = (Private::Format *)StringAlgo::FormatString(v51, &v44);
  v33 = Sid::GetCurrent(v52);
  std::wstring::wstring(v47, v33 + 72);
  v38 = v30 | 0x20;
  v34 = (Private::Format *)Private::Format::operator%<std::wstring>(v32);
  CreationTime.dwLowDateTime = GetCurrentProcessId();
  v35 = Private::Format::operator%<unsigned long>(v34);
  std::wstring::wstring(v50, v35);
  wpc::LogRecorder::LogRecorderChannel::AddLogEntry(this);
  std::wstring::~wstring(v47);
  std::wstring::~wstring(v53);
  std::wstring::~wstring(v51);
  std::wstring::~wstring(v49);
  std::wstring::~wstring(a3);
  return this;
}

```

## disassembly

```asm
0x1800670c8  mov     [rsp-8+arg_8], rbx
0x1800670cd  push    rbp
0x1800670ce  push    rsi
0x1800670cf  push    rdi
0x1800670d0  push    r12
0x1800670d2  push    r13
0x1800670d4  push    r14
0x1800670d6  push    r15
0x1800670d8  lea     rbp, [rsp-0A0h]
0x1800670e0  sub     rsp, 1A0h
0x1800670e7  mov     rax, cs:__security_cookie
0x1800670ee  xor     rax, rsp
0x1800670f1  mov     [rbp+0D0h+var_40], rax
0x1800670f8  mov     r14, r8
0x1800670fb  mov     r15d, edx
0x1800670fe  mov     rdi, rcx
0x180067101  mov     [rsp+1D0h+var_178], rcx
0x180067106  mov     [rsp+1D0h+var_160], r8
0x18006710b  xor     ebx, ebx
0x18006710d  mov     [rsp+1D0h+var_18C], ebx
0x180067111  xorps   xmm0, xmm0
0x180067114  movups  [rsp+1D0h+var_158], xmm0
0x180067119  mov     [rbp+0D0h+var_148], rbx
0x18006711d  mov     [rbp+0D0h+var_140], rbx
0x180067121  xor     r8d, r8d
0x180067124  lea     rdx, SubKey
0x18006712b  lea     rcx, [rsp+1D0h+var_158]
0x180067130  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180067135  lea     rdx, [rsp+1D0h+var_158]
0x18006713a  mov     rcx, rdi
0x18006713d  call    ??0Path@IO@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IO::Path::Path(std::wstring)
0x180067142  nop
0x180067143  xorps   xmm0, xmm0
0x180067146  movups  [rsp+1D0h+var_158], xmm0
0x18006714b  mov     [rbp+0D0h+var_148], rbx
0x18006714f  mov     [rbp+0D0h+var_140], rbx
0x180067153  xor     r8d, r8d
0x180067156  lea     rdx, SubKey
0x18006715d  lea     rcx, [rsp+1D0h+var_158]
0x180067162  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180067167  lea     rdx, [rsp+1D0h+var_158]
0x18006716c  lea     rcx, [rdi+20h]
0x180067170  call    ??0Path@IO@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IO::Path::Path(std::wstring)
0x180067175  nop
0x180067176  lea     rcx, [rdi+40h]
0x18006717a  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x18006717f  lea     rcx, [rdi+4Ch]
0x180067183  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x180067188  lea     rax, ??_7?$LockBox@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0PPPPPPPP@@@6B@; const LockBox<std::wstring,4294967295>::`vftable'
0x18006718f  mov     [rdi+58h], rax
0x180067193  xorps   xmm0, xmm0
0x180067196  movups  xmmword ptr [rdi+68h], xmm0
0x18006719a  mov     [rdi+78h], rbx
0x18006719e  lea     esi, [rbx+7]
0x1800671a1  mov     [rdi+80h], rsi
0x1800671a8  mov     [rdi+68h], bx
0x1800671ac  lea     rcx, [rdi+60h]; SRWLock
0x1800671b0  call    cs:__imp_InitializeSRWLock
0x1800671b6  nop
0x1800671b7  mov     [rdi+88h], rbx
0x1800671be  mov     [rdi+90h], rbx
0x1800671c5  mov     [rdi+98h], rbx
0x1800671cc  mov     [rdi+0A0h], rbx
0x1800671d3  test    r15b, 2
0x1800671d7  jz      loc_180067291
0x1800671dd  mov     qword ptr [rsp+1D0h+CreationTime.dwLowDateTime], rdi
0x1800671e2  lea     r8, [rsp+1D0h+CreationTime]
0x1800671e7  lea     rdx, [rbp+0D0h+var_138]
0x1800671eb  call    Threadpool__QueueTimerCallback__lambda_cbf5b5fb35637c87aa327395232b2d2a___
0x1800671f0  mov     rcx, [rax]
0x1800671f3  mov     rdx, [rax+8]
0x1800671f7  mov     [rax], rbx
0x1800671fa  mov     [rax+8], rbx
0x1800671fe  mov     [rdi+88h], rcx
0x180067205  mov     rbx, [rdi+90h]
0x18006720c  mov     [rdi+90h], rdx
0x180067213  test    rbx, rbx
0x180067216  jz      short loc_18006724F
0x180067218  or      eax, 0FFFFFFFFh
0x18006721b  lock xadd [rbx+8], eax
0x180067220  cmp     eax, 1
0x180067223  jnz     short loc_18006724F
0x180067225  mov     rax, [rbx]
0x180067228  mov     rcx, rbx
0x18006722b  mov     rax, [rax]
0x18006722e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067233  or      eax, 0FFFFFFFFh
0x180067236  lock xadd [rbx+0Ch], eax
0x18006723b  cmp     eax, 1
0x18006723e  jnz     short loc_18006724F
0x180067240  mov     rax, [rbx]
0x180067243  mov     rcx, rbx
0x180067246  mov     rax, [rax+8]
0x18006724a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006724f  mov     rbx, [rbp+0D0h+var_130]
0x180067253  test    rbx, rbx
0x180067256  jz      short loc_18006728F
0x180067258  or      eax, 0FFFFFFFFh
0x18006725b  lock xadd [rbx+8], eax
0x180067260  cmp     eax, 1
0x180067263  jnz     short loc_18006728F
0x180067265  mov     rax, [rbx]
0x180067268  mov     rcx, rbx
0x18006726b  mov     rax, [rax]
0x18006726e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067273  or      eax, 0FFFFFFFFh
0x180067276  lock xadd [rbx+0Ch], eax
0x18006727b  cmp     eax, 1
0x18006727e  jnz     short loc_18006728F
0x180067280  mov     rax, [rbx]
0x180067283  mov     rcx, rbx
0x180067286  mov     rax, [rax+8]
0x18006728a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006728f  xor     ebx, ebx
0x180067291  test    r15b, 4
0x180067295  jz      loc_18006735B
0x18006729b  mov     qword ptr [rsp+1D0h+CreationTime.dwLowDateTime], 47868C00h
0x1800672a4  mov     [rsp+1D0h+hFile], rdi
0x1800672a9  lea     r9, [rsp+1D0h+CreationTime]
0x1800672ae  lea     r8, [rsp+1D0h+hFile]
0x1800672b3  lea     rdx, [rbp+0D0h+var_138]
0x1800672b7  call    Threadpool__QueueTimerCallback__lambda_3be6e2c04033393fb85ca8d5efb592b1___
0x1800672bc  mov     rcx, [rax]
0x1800672bf  mov     rdx, [rax+8]
0x1800672c3  mov     [rax], rbx
0x1800672c6  mov     [rax+8], rbx
0x1800672ca  mov     [rdi+98h], rcx
0x1800672d1  mov     rbx, [rdi+0A0h]
0x1800672d8  mov     [rdi+0A0h], rdx
0x1800672df  test    rbx, rbx
0x1800672e2  jz      short loc_18006731B
0x1800672e4  or      eax, 0FFFFFFFFh
0x1800672e7  lock xadd [rbx+8], eax
0x1800672ec  cmp     eax, 1
0x1800672ef  jnz     short loc_18006731B
0x1800672f1  mov     rax, [rbx]
0x1800672f4  mov     rcx, rbx
0x1800672f7  mov     rax, [rax]
0x1800672fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800672ff  or      eax, 0FFFFFFFFh
0x180067302  lock xadd [rbx+0Ch], eax
0x180067307  cmp     eax, 1
0x18006730a  jnz     short loc_18006731B
0x18006730c  mov     rax, [rbx]
0x18006730f  mov     rcx, rbx
0x180067312  mov     rax, [rax+8]
0x180067316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006731b  mov     rbx, [rbp+0D0h+var_130]
0x18006731f  test    rbx, rbx
0x180067322  jz      short loc_18006735B
0x180067324  or      eax, 0FFFFFFFFh
0x180067327  lock xadd [rbx+8], eax
0x18006732c  cmp     eax, 1
0x18006732f  jnz     short loc_18006735B
0x180067331  mov     rax, [rbx]
0x180067334  mov     rcx, rbx
0x180067337  mov     rax, [rax]
0x18006733a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006733f  or      eax, 0FFFFFFFFh
0x180067342  lock xadd [rbx+0Ch], eax
0x180067347  cmp     eax, 1
0x18006734a  jnz     short loc_18006735B
0x18006734c  mov     rax, [rbx]
0x18006734f  mov     rcx, rbx
0x180067352  mov     rax, [rax+8]
0x180067356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006735b  and     r15d, 1
0x18006735f  mov     [rsp+1D0h+var_190], r15b
0x180067364  lea     rdx, [rbp+0D0h+var_118]
0x180067368  lea     rcx, [rsp+1D0h+var_190]
0x18006736d  call    _lambda_6b4353445c5d79bdb48dad0cdc4514c8___operator__
0x180067372  mov     [rsp+1D0h+var_18C], 1
0x18006737a  lea     rcx, [rbp+0D0h+var_118]; struct Path *
0x18006737e  call    ?Exists@Directory@IO@@SA_NAEBVPath@2@@Z; IO::Directory::Exists(IO::Path const &)
0x180067383  xor     r15d, r15d
0x180067386  test    al, al
0x180067388  jnz     short loc_1800673A5
0x18006738a  xor     r8d, r8d
0x18006738d  lea     rdx, [rbp+0D0h+var_118]
0x180067391  lea     rcx, [rsp+1D0h+var_158]
0x180067396  call    ?Create@Directory@IO@@SA?AV12@AEBVPath@2@PEBVSecurityDescriptor@@@Z; IO::Directory::Create(IO::Path const &,SecurityDescriptor const *)
0x18006739b  lea     rcx, [rsp+1D0h+var_158]
0x1800673a0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800673a5  mov     rcx, [r14+10h]
0x1800673a9  mov     rbx, 7FFFFFFFFFFFFFFEh
0x1800673b3  mov     rax, rbx
0x1800673b6  sub     rax, rcx
0x1800673b9  cmp     rax, 8
0x1800673bd  jb      loc_1800676A4
0x1800673c3  cmp     [r14+18h], rsi
0x1800673c7  jbe     short loc_1800673CE
0x1800673c9  mov     r9, [r14]
0x1800673cc  jmp     short loc_1800673D1
0x1800673ce  mov     r9, r14
0x1800673d1  mov     [rsp+1D0h+var_1A0], 8
0x1800673da  lea     rax, aOldLog; "-old.log"
0x1800673e1  mov     [rsp+1D0h+var_1A8], rax
0x1800673e6  mov     [rsp+1D0h+var_1B0], rcx
0x1800673eb  lea     rcx, [rsp+1D0h+var_158]
0x1800673f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800673f5  mov     [rsp+1D0h+var_18C], 3
0x1800673fd  lea     rdx, [rsp+1D0h+var_158]
0x180067402  lea     rcx, [rbp+0D0h+var_138]
0x180067406  call    ??0Path@IO@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IO::Path::Path(std::wstring)
0x18006740b  nop
0x18006740c  lea     r8, [rbp+0D0h+var_138]
0x180067410  lea     rdx, [rbp+0D0h+var_118]
0x180067414  lea     rcx, [rbp+0D0h+var_F8]
0x180067418  call    ??KIO@@YA?AVPath@0@AEBV10@0@Z; IO::operator/(IO::Path const &,IO::Path const &)
0x18006741d  mov     rdx, rax
0x180067420  lea     rcx, [rdi+20h]
0x180067424  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180067429  lea     rcx, [rbp+0D0h+var_F8]
0x18006742d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180067432  nop
0x180067433  lea     rcx, [rbp+0D0h+var_138]
0x180067437  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006743c  mov     rax, [r14+10h]
0x180067440  sub     rbx, rax
0x180067443  cmp     rbx, 4
0x180067447  jb      loc_18006769E
0x18006744d  cmp     [r14+18h], rsi
0x180067451  jbe     short loc_180067458
0x180067453  mov     r9, [r14]
0x180067456  jmp     short loc_18006745B
0x180067458  mov     r9, r14
0x18006745b  mov     [rsp+1D0h+var_1A0], 4
0x180067464  lea     rcx, aLog; ".log"
0x18006746b  mov     [rsp+1D0h+var_1A8], rcx
0x180067470  mov     [rsp+1D0h+var_1B0], rax
0x180067475  lea     rcx, [rsp+1D0h+var_158]
0x18006747a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18006747f  mov     [rsp+1D0h+var_18C], esi
0x180067483  lea     rdx, [rsp+1D0h+var_158]
0x180067488  lea     rcx, [rbp+0D0h+var_138]
0x18006748c  call    ??0Path@IO@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IO::Path::Path(std::wstring)
0x180067491  nop
0x180067492  lea     r8, [rbp+0D0h+var_138]
0x180067496  lea     rdx, [rbp+0D0h+var_118]
0x18006749a  lea     rcx, [rbp+0D0h+var_F8]
0x18006749e  call    ??KIO@@YA?AVPath@0@AEBV10@0@Z; IO::operator/(IO::Path const &,IO::Path const &)
0x1800674a3  mov     rdx, rax
0x1800674a6  mov     rcx, rdi
0x1800674a9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800674ae  lea     rcx, [rbp+0D0h+var_F8]
0x1800674b2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800674b7  nop
0x1800674b8  lea     rcx, [rbp+0D0h+var_138]
0x1800674bc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800674c1  cmp     [rdi+18h], rsi
0x1800674c5  jbe     short loc_1800674CC
0x1800674c7  mov     rcx, [rdi]
0x1800674ca  jmp     short loc_1800674CF
0x1800674cc  mov     rcx, rdi; lpFileName
0x1800674cf  call    cs:__imp_GetFileAttributesW
0x1800674d5  test    al, 10h
0x1800674d7  jnz     loc_18006757C
0x1800674dd  xor     r8d, r8d
0x1800674e0  mov     rdx, rdi
0x1800674e3  lea     rcx, [rsp+1D0h+hFile]
0x1800674e8  call    ?Open@File@IO@@YA?AV?$unique_ptr@XUHandleClose@Private@@@std@@AEBVPath@2@W4Access@12@UAssumeDirectoryExists@2@@Z; IO::File::Open(IO::Path const &,IO::File::Access,IO::AssumeDirectoryExists)
0x1800674ed  mov     esi, 17h
0x1800674f2  mov     [rsp+1D0h+var_18C], esi
0x1800674f6  mov     qword ptr [rsp+1D0h+CreationTime.dwLowDateTime], r15
0x1800674fb  xor     r9d, r9d; lpLastWriteTime
0x1800674fe  xor     r8d, r8d; lpLastAccessTime
0x180067501  lea     rdx, [rsp+1D0h+CreationTime]; lpCreationTime
0x180067506  mov     rbx, [rsp+1D0h+hFile]
0x18006750b  mov     rcx, rbx; hFile
0x18006750e  call    cs:__imp_GetFileTime
0x180067514  test    eax, eax
0x180067516  jz      short loc_180067564
0x180067518  lea     rdx, [rsp+1D0h+CreationTime]
0x18006751d  lea     rcx, [rsp+1D0h+var_170]
0x180067522  call    ??0DateTime@@QEAA@AEBU_FILETIME@@W4TimeType@@@Z; DateTime::DateTime(_FILETIME const &,TimeType)
0x180067527  mov     rcx, rax
0x18006752a  mov     rax, [rax]
0x18006752d  mov     qword ptr [rsp+1D0h+var_158+4], rax
0x180067532  mov     eax, [rcx+8]
0x180067535  mov     dword ptr [rbp+0D0h+var_158+0Ch], eax
0x180067538  lea     rax, [rsp+1D0h+var_158+4]
0x18006753d  mov     [rbp+0D0h+var_148], rax
0x180067541  mov     esi, 1Fh
0x180067546  mov     [rsp+1D0h+var_18C], esi
0x18006754a  test    rbx, rbx
0x18006754d  jz      short loc_180067587
0x18006754f  lea     rax, [rbx-1]
0x180067553  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180067557  ja      short loc_180067587
0x180067559  mov     rcx, rbx; hObject
0x18006755c  call    cs:__imp_CloseHandle
0x180067562  jmp     short loc_180067587
0x180067564  test    rbx, rbx
0x180067567  jz      short loc_18006757C
0x180067569  lea     rax, [rbx-1]
0x18006756d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180067571  ja      short loc_18006757C
0x180067573  mov     rcx, rbx; hObject
0x180067576  call    cs:__imp_CloseHandle
0x18006757c  mov     [rbp+0D0h+var_148], r15
  ... truncated ...
```
