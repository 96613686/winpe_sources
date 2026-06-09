# CbsOfflineUtil::CbsCreateSessionFromWindirWithVersion(int,wchar_t const * const,unsigned __int64 const *,ICbsSession * *)

- ea: `0x18003eea0`
- end: `0x18003f0aa`
- name: `?CbsCreateSessionFromWindirWithVersion@CbsOfflineUtil@@UEAAJHQEB_WPEB_KPEAPEAUICbsSession@@@Z`
- size: `522`
- prototype: `__int64 __fastcall(CbsOfflineUtil *this, unsigned int, WCHAR *, const unsigned __int64 *, struct ICbsSession **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800104e4`
- `0x18001e4fc`
- `0x18001e51c`
- `0x18001fd10`
- `0x1800293a0`
- `0x18003e344`
- `0x18003e810`
- `0x18003eea0`
- `0x180099cb0`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18003ef1c`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18003ef1c`

## string_xrefs

- `0x18003efb1`: `cbscore.dll`

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
  UINT SystemWindowsDirectoryW; // eax
  const char *v11; // r9
  int LastError; // ebx
  void (*v13)(void); // rax
  __int64 v15; // rdx
  struct ICbsSession **InitPointer; // rax
  int v17; // [rsp+20h] [rbp-E0h]
  struct ICbsSession *v18; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v19; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v18 = 0;
  v8 = 0;
  v19 = 0;
  *a5 = 0;
  v9 = (int)a4;
  memset(Buffer, 0, 0x208u);
  if ( !a3 )
  {
    SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
    if ( !SystemWindowsDirectoryW )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x16F,
                    (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
                    v11);
LABEL_4:
      Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v19);
      if ( !v18 )
        return (unsigned int)LastError;
      v13 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
LABEL_6:
      v13();
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
        v17);
      goto LABEL_4;
    }
    v8 = v19;
    a3 = Buffer;
  }
  if ( v8 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18003F0A9LL);
  }
  LastError = (*(__int64 (__fastcall **)(CbsOfflineUtil *, _QWORD, WCHAR *, const wchar_t *))(*(_QWORD *)this + 64LL))(
                this,
                a2,
                a3,
                L"cbscore.dll");
  if ( LastError < 0 )
  {
    v15 = 385;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
      (const char *)(unsigned int)LastError,
      v9);
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v19);
    if ( !v18 )
      return (unsigned int)LastError;
    v13 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
    goto LABEL_6;
  }
  InitPointer = (struct ICbsSession **)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v18);
  LastError = CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(this, v19, InitPointer);
  if ( LastError < 0 )
  {
    v15 = 387;
    goto LABEL_14;
  }
  *a5 = v18;
  v18 = 0;
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v19);
  if ( v18 )
    (*(void (__fastcall **)(struct ICbsSession *))(*(_QWORD *)v18 + 16LL))(v18);
  return 0;
}

```

## disassembly

```asm
0x18003eea0  push    rbp
0x18003eea2  push    rbx
0x18003eea3  push    rsi
0x18003eea4  push    rdi
0x18003eea5  push    r12
0x18003eea7  push    r14
0x18003eea9  push    r15
0x18003eeab  lea     rbp, [rsp-180h]
0x18003eeb3  sub     rsp, 280h
0x18003eeba  mov     rax, cs:__security_cookie
0x18003eec1  xor     rax, rsp
0x18003eec4  mov     [rbp+1B0h+var_40], rax
0x18003eecb  mov     r14, [rbp+1B0h+arg_20]
0x18003eed2  mov     rdi, r8
0x18003eed5  mov     r15d, edx
0x18003eed8  mov     [rsp+2B0h+var_260], 0
0x18003eee1  mov     rsi, rcx
0x18003eee4  xor     ebx, ebx
0x18003eee6  xor     edx, edx; Val
0x18003eee8  mov     [rsp+2B0h+var_258], rbx
0x18003eeed  mov     r8d, 208h; Size
0x18003eef3  mov     qword ptr [r14], 0
0x18003eefa  lea     rcx, [rsp+2B0h+Buffer]; void *
0x18003eeff  mov     r12, r9
0x18003ef02  call    memset
0x18003ef07  test    rdi, rdi
0x18003ef0a  jnz     loc_18003EF9B
0x18003ef10  mov     ebx, 104h
0x18003ef15  lea     rcx, [rsp+2B0h+Buffer]; lpBuffer
0x18003ef1a  mov     edx, ebx; uSize
0x18003ef1c  call    cs:__imp_GetSystemWindowsDirectoryW
0x18003ef23  nop     dword ptr [rax+rax+00h]
0x18003ef28  test    eax, eax
0x18003ef2a  jnz     short loc_18003EF6B
0x18003ef2c  mov     rcx, [rbp+1B8h]; this
0x18003ef33  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x18003ef3a  lea     edx, [rbx+6Bh]; void *
0x18003ef3d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003ef42  mov     ebx, eax
0x18003ef44  lea     rcx, [rsp+2B0h+var_258]
0x18003ef49  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x18003ef4e  mov     rcx, [rsp+2B0h+var_260]
0x18003ef53  test    rcx, rcx
0x18003ef56  jz      short loc_18003EF64
0x18003ef58  mov     rdx, [rcx]
0x18003ef5b  mov     rax, [rdx+10h]
0x18003ef5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef64  mov     eax, ebx
0x18003ef66  jmp     loc_18003F07D
0x18003ef6b  cmp     eax, ebx
0x18003ef6d  jb      short loc_18003EF91
0x18003ef6f  mov     rcx, [rbp+1B8h]; this
0x18003ef76  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x18003ef7d  mov     ebx, 8007007Ah
0x18003ef82  mov     edx, 170h; void *
0x18003ef87  mov     r9d, ebx; char *
0x18003ef8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ef8f  jmp     short loc_18003EF44
0x18003ef91  mov     rbx, [rsp+2B0h+var_258]
0x18003ef96  lea     rdi, [rsp+2B0h+Buffer]
0x18003ef9b  test    rbx, rbx
0x18003ef9e  jnz     loc_18003F09F
0x18003efa4  mov     rax, [rsi]
0x18003efa7  lea     rcx, [rsp+2B0h+var_258]
0x18003efac  mov     [rsp+2B0h+var_270], rbx
0x18003efb1  lea     r9, aCbscoreDll_0; "cbscore.dll"
0x18003efb8  mov     [rsp+2B0h+var_278], rcx
0x18003efbd  mov     r8, rdi
0x18003efc0  mov     [rsp+2B0h+var_280], rbx
0x18003efc5  mov     edx, r15d
0x18003efc8  mov     rax, [rax+40h]
0x18003efcc  mov     rcx, rsi
0x18003efcf  mov     [rsp+2B0h+var_288], rbx
0x18003efd4  mov     qword ptr [rsp+2B0h+var_290], r12; int
0x18003efd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003efde  mov     ebx, eax
0x18003efe0  test    eax, eax
0x18003efe2  jns     short loc_18003F023
0x18003efe4  mov     edx, 181h; void *
0x18003efe9  mov     rcx, [rbp+1B8h]; this
0x18003eff0  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x18003eff7  mov     r9d, ebx; char *
0x18003effa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003efff  lea     rcx, [rsp+2B0h+var_258]
0x18003f004  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x18003f009  mov     rcx, [rsp+2B0h+var_260]
0x18003f00e  test    rcx, rcx
0x18003f011  jz      loc_18003EF64
0x18003f017  mov     rax, [rcx]
0x18003f01a  mov     rax, [rax+10h]
0x18003f01e  jmp     loc_18003EF5F
0x18003f023  lea     rcx, [rsp+2B0h+var_260]
0x18003f028  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18003f02d  mov     rdx, [rsp+2B0h+var_258]; wchar_t *
0x18003f032  mov     r8, rax; struct ICbsSession **
0x18003f035  mov     rcx, rsi; this
0x18003f038  call    ?CbsCreateSessionFromCbsCorePath@CbsOfflineUtil@@QEAAJPEB_WPEAPEAUICbsSession@@@Z; CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(wchar_t const *,ICbsSession * *)
0x18003f03d  mov     ebx, eax
0x18003f03f  test    eax, eax
0x18003f041  jns     short loc_18003F04A
0x18003f043  mov     edx, 183h
0x18003f048  jmp     short loc_18003EFE9
0x18003f04a  mov     rax, [rsp+2B0h+var_260]
0x18003f04f  lea     rcx, [rsp+2B0h+var_258]
0x18003f054  mov     [r14], rax
0x18003f057  mov     [rsp+2B0h+var_260], 0
0x18003f060  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x18003f065  mov     rcx, [rsp+2B0h+var_260]
0x18003f06a  test    rcx, rcx
0x18003f06d  jz      short loc_18003F07B
0x18003f06f  mov     rax, [rcx]
0x18003f072  mov     rax, [rax+10h]
0x18003f076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f07b  xor     eax, eax
0x18003f07d  mov     rcx, [rbp+1B0h+var_40]
0x18003f084  xor     rcx, rsp; StackCookie
0x18003f087  call    __security_check_cookie
0x18003f08c  add     rsp, 280h
0x18003f093  pop     r15
0x18003f095  pop     r14
0x18003f097  pop     r12
0x18003f099  pop     rdi
0x18003f09a  pop     rsi
0x18003f09b  pop     rbx
0x18003f09c  pop     rbp
0x18003f09d  retn
0x18003f09f  mov     ecx, 0C00000E5h; int
0x18003f0a4  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
