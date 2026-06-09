# CbsOfflineUtil::CbsCreateSessionFromWindirWithVersion(int,wchar_t const * const,unsigned __int64 const *,ICbsSession * *)

- ea: `0x140024fe0`
- end: `0x1400251de`
- name: `?CbsCreateSessionFromWindirWithVersion@CbsOfflineUtil@@UEAAJHQEB_WPEB_KPEAPEAUICbsSession@@@Z`
- size: `510`
- prototype: `__int64 __fastcall(CbsOfflineUtil *this, unsigned int, WCHAR *, const unsigned __int64 *, struct ICbsSession **)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002360`
- `0x140002d98`
- `0x140005684`
- `0x1400056ac`
- `0x14000731c`
- `0x140024604`
- `0x140024aa0`
- `0x140024fe0`
- `0x1400258f0`
- `0x14002a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14002505c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14002505c`

## string_xrefs

- `0x1400250eb`: `cbscore.dll`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CbsCreateSessionFromWindirWithVersion(
        CbsOfflineUtil *this,
        unsigned int a2,
        WCHAR *a3,
        const unsigned __int64 *a4,
        struct ICbsSession **a5)
{
  wchar_t *v8; // rbx
  int v9; // r12d
  int v10; // ecx
  UINT SystemWindowsDirectoryW; // eax
  const char *v12; // r9
  int LastError; // ebx
  void (*v14)(void); // rax
  __int64 v16; // rdx
  struct ICbsSession **InitPointer; // rax
  int v18; // [rsp+20h] [rbp-E0h]
  struct ICbsSession *v19; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v20; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v19 = 0;
  v8 = 0;
  v20 = 0;
  *a5 = 0;
  v9 = (int)a4;
  memset_0(Buffer, 0, 0x208u);
  if ( !a3 )
  {
    SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
    if ( !SystemWindowsDirectoryW )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x16F,
                    (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
                    v12);
LABEL_4:
      Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v20);
      if ( !v19 )
        return (unsigned int)LastError;
      v14 = *(void (**)(void))(*(_QWORD *)v19 + 16LL);
LABEL_6:
      v14();
      return (unsigned int)LastError;
    }
    if ( SystemWindowsDirectoryW >= 0x104 )
    {
      LastError = -2147024774;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x170,
        (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
        (const char *)0x8007007ALL,
        v18);
      goto LABEL_4;
    }
    v8 = v20;
    a3 = Buffer;
  }
  if ( v8 )
    INTERNAL_ERROR_ACTION(v10);
  LastError = (*(__int64 (__fastcall **)(CbsOfflineUtil *, _QWORD, WCHAR *, const wchar_t *))(*(_QWORD *)this + 64LL))(
                this,
                a2,
                a3,
                L"cbscore.dll");
  if ( LastError < 0 )
  {
    v16 = 385;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
      (const char *)(unsigned int)LastError,
      v9);
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v20);
    if ( !v19 )
      return (unsigned int)LastError;
    v14 = *(void (**)(void))(*(_QWORD *)v19 + 16LL);
    goto LABEL_6;
  }
  InitPointer = (struct ICbsSession **)Windows::AutoComPtr<ICbsSession>::GetInitPointer(&v19);
  LastError = CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(this, v20, InitPointer);
  if ( LastError < 0 )
  {
    v16 = 387;
    goto LABEL_14;
  }
  *a5 = v19;
  v19 = 0;
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v20);
  if ( v19 )
    (*(void (__fastcall **)(struct ICbsSession *))(*(_QWORD *)v19 + 16LL))(v19);
  return 0;
}

```

## disassembly

```asm
0x140024fe0  push    rbp
0x140024fe2  push    rbx
0x140024fe3  push    rsi
0x140024fe4  push    rdi
0x140024fe5  push    r12
0x140024fe7  push    r14
0x140024fe9  push    r15
0x140024feb  lea     rbp, [rsp-180h]
0x140024ff3  sub     rsp, 280h
0x140024ffa  mov     rax, cs:__security_cookie
0x140025001  xor     rax, rsp
0x140025004  mov     [rbp+1B0h+var_40], rax
0x14002500b  mov     r14, [rbp+1B0h+arg_20]
0x140025012  mov     rdi, r8
0x140025015  mov     r15d, edx
0x140025018  mov     [rsp+2B0h+var_260], 0
0x140025021  mov     rsi, rcx
0x140025024  xor     ebx, ebx
0x140025026  xor     edx, edx; Val
0x140025028  mov     [rsp+2B0h+var_258], rbx
0x14002502d  mov     r8d, 208h; Size
0x140025033  mov     qword ptr [r14], 0
0x14002503a  lea     rcx, [rsp+2B0h+Buffer]; void *
0x14002503f  mov     r12, r9
0x140025042  call    memset_0
0x140025047  test    rdi, rdi
0x14002504a  jnz     loc_1400250D5
0x140025050  mov     ebx, 104h
0x140025055  lea     rcx, [rsp+2B0h+Buffer]; lpBuffer
0x14002505a  mov     edx, ebx; uSize
0x14002505c  call    cs:__imp_GetSystemWindowsDirectoryW
0x140025062  test    eax, eax
0x140025064  jnz     short loc_1400250A5
0x140025066  mov     rcx, [rbp+1B8h]; this
0x14002506d  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x140025074  lea     edx, [rbx+6Bh]; void *
0x140025077  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14002507c  mov     ebx, eax
0x14002507e  lea     rcx, [rsp+2B0h+var_258]
0x140025083  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x140025088  mov     rcx, [rsp+2B0h+var_260]
0x14002508d  test    rcx, rcx
0x140025090  jz      short loc_14002509E
0x140025092  mov     rdx, [rcx]
0x140025095  mov     rax, [rdx+10h]
0x140025099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002509e  mov     eax, ebx
0x1400250a0  jmp     loc_1400251B7
0x1400250a5  cmp     eax, ebx
0x1400250a7  jb      short loc_1400250CB
0x1400250a9  mov     rcx, [rbp+1B8h]; this
0x1400250b0  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x1400250b7  mov     ebx, 8007007Ah
0x1400250bc  mov     edx, 170h; void *
0x1400250c1  mov     r9d, ebx; char *
0x1400250c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400250c9  jmp     short loc_14002507E
0x1400250cb  mov     rbx, [rsp+2B0h+var_258]
0x1400250d0  lea     rdi, [rsp+2B0h+Buffer]
0x1400250d5  test    rbx, rbx
0x1400250d8  jnz     loc_1400251D8
0x1400250de  mov     rax, [rsi]
0x1400250e1  lea     rcx, [rsp+2B0h+var_258]
0x1400250e6  mov     [rsp+2B0h+var_270], rbx
0x1400250eb  lea     r9, aCbscoreDll_0; "cbscore.dll"
0x1400250f2  mov     [rsp+2B0h+var_278], rcx
0x1400250f7  mov     r8, rdi
0x1400250fa  mov     [rsp+2B0h+var_280], rbx
0x1400250ff  mov     edx, r15d
0x140025102  mov     rax, [rax+40h]
0x140025106  mov     rcx, rsi
0x140025109  mov     [rsp+2B0h+var_288], rbx
0x14002510e  mov     qword ptr [rsp+2B0h+var_290], r12; int
0x140025113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025118  mov     ebx, eax
0x14002511a  test    eax, eax
0x14002511c  jns     short loc_14002515D
0x14002511e  mov     edx, 181h; void *
0x140025123  mov     rcx, [rbp+1B8h]; this
0x14002512a  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x140025131  mov     r9d, ebx; char *
0x140025134  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025139  lea     rcx, [rsp+2B0h+var_258]
0x14002513e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x140025143  mov     rcx, [rsp+2B0h+var_260]
0x140025148  test    rcx, rcx
0x14002514b  jz      loc_14002509E
0x140025151  mov     rax, [rcx]
0x140025154  mov     rax, [rax+10h]
0x140025158  jmp     loc_140025099
0x14002515d  lea     rcx, [rsp+2B0h+var_260]
0x140025162  call    ?GetInitPointer@?$AutoComPtr@UICbsSession@@@Windows@@QEAAPEAPEAUICbsSession@@XZ; Windows::AutoComPtr<ICbsSession>::GetInitPointer(void)
0x140025167  mov     rdx, [rsp+2B0h+var_258]; wchar_t *
0x14002516c  mov     r8, rax; struct ICbsSession **
0x14002516f  mov     rcx, rsi; this
0x140025172  call    ?CbsCreateSessionFromCbsCorePath@CbsOfflineUtil@@QEAAJPEB_WPEAPEAUICbsSession@@@Z; CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(wchar_t const *,ICbsSession * *)
0x140025177  mov     ebx, eax
0x140025179  test    eax, eax
0x14002517b  jns     short loc_140025184
0x14002517d  mov     edx, 183h
0x140025182  jmp     short loc_140025123
0x140025184  mov     rax, [rsp+2B0h+var_260]
0x140025189  lea     rcx, [rsp+2B0h+var_258]
0x14002518e  mov     [r14], rax
0x140025191  mov     [rsp+2B0h+var_260], 0
0x14002519a  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x14002519f  mov     rcx, [rsp+2B0h+var_260]
0x1400251a4  test    rcx, rcx
0x1400251a7  jz      short loc_1400251B5
0x1400251a9  mov     rax, [rcx]
0x1400251ac  mov     rax, [rax+10h]
0x1400251b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400251b5  xor     eax, eax
0x1400251b7  mov     rcx, [rbp+1B0h+var_40]
0x1400251be  xor     rcx, rsp; StackCookie
0x1400251c1  call    __security_check_cookie
0x1400251c6  add     rsp, 280h
0x1400251cd  pop     r15
0x1400251cf  pop     r14
0x1400251d1  pop     r12
0x1400251d3  pop     rdi
0x1400251d4  pop     rsi
0x1400251d5  pop     rbx
0x1400251d6  pop     rbp
0x1400251d7  retn
0x1400251d8  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
