# CbsOfflineUtil::CbsCreateOfflineSession(wchar_t const *,ICbsSession * *)

- ea: `0x1400244a0`
- end: `0x1400245fd`
- name: `?CbsCreateOfflineSession@CbsOfflineUtil@@UEAAJPEB_WPEAPEAUICbsSession@@@Z`
- size: `349`
- prototype: `__int64 __fastcall(CbsOfflineUtil *__hidden this, const wchar_t *, struct ICbsSession **)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002360`
- `0x140002900`
- `0x140002d98`
- `0x1400056ac`
- `0x140005bf0`
- `0x140005c44`
- `0x1400244a0`
- `0x140024604`
- `0x140024aa0`
- `0x14002a010`

## string_xrefs

- `0x140024582`: `\cbscore.dll`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CbsCreateOfflineSession(
        CbsOfflineUtil *this,
        const wchar_t *a2,
        struct ICbsSession **a3)
{
  unsigned __int64 v6; // r11
  int SessionFromCbsCorePath; // ebx
  __int64 v8; // rdx
  __int64 v10; // rax
  unsigned __int64 v11; // rcx
  struct ICbsSession **InitPointer; // rax
  int v13[3]; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t v15[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *(_QWORD *)v13 = 0;
  memset_0(v15, 0, 0x208u);
  v6 = 260;
  if ( a2 && *a2 )
  {
    SessionFromCbsCorePath = StringCchCopyW(v15, 0x104u, a2);
    if ( SessionFromCbsCorePath < 0 )
    {
      v8 = (unsigned int)(v6 - 9);
      goto LABEL_5;
    }
  }
  else
  {
    wcscpy(v15, L".");
  }
  v10 = -1;
  do
    ++v10;
  while ( v15[v10] );
  if ( v15[v10 - 1] == 92 )
  {
    v11 = 2 * v10 - 2;
    if ( v11 >= 0x208 )
      _report_rangecheckfailure();
    *(wchar_t *)((char *)v15 + v11) = 0;
  }
  SessionFromCbsCorePath = StringCchCatW(v15, v6, L"\\cbscore.dll");
  if ( SessionFromCbsCorePath >= 0 )
  {
    InitPointer = (struct ICbsSession **)Windows::AutoComPtr<ICbsSession>::GetInitPointer(v13);
    SessionFromCbsCorePath = CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(this, v15, InitPointer);
    if ( SessionFromCbsCorePath >= 0 )
    {
      *a3 = *(struct ICbsSession **)v13;
      return 0;
    }
    v8 = 266;
  }
  else
  {
    v8 = 264;
  }
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineutil.cpp",
    (const char *)(unsigned int)SessionFromCbsCorePath,
    v13[0]);
  if ( *(_QWORD *)v13 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 16LL))(*(_QWORD *)v13);
  return (unsigned int)SessionFromCbsCorePath;
}

```

## disassembly

```asm
0x1400244a0  push    rbp
0x1400244a2  push    rbx
0x1400244a3  push    rsi
0x1400244a4  push    rdi
0x1400244a5  push    r14
0x1400244a7  lea     rbp, [rsp-150h]
0x1400244af  sub     rsp, 250h
0x1400244b6  mov     rax, cs:__security_cookie
0x1400244bd  xor     rax, rsp
0x1400244c0  mov     [rbp+170h+var_30], rax
0x1400244c7  mov     rdi, r8
0x1400244ca  mov     rbx, rdx
0x1400244cd  mov     rsi, rcx
0x1400244d0  xor     r14d, r14d
0x1400244d3  xor     edx, edx; Val
0x1400244d5  mov     qword ptr [rsp+270h+var_250], r14; int
0x1400244da  mov     r8d, 208h; Size
0x1400244e0  lea     rcx, [rsp+270h+var_240]; void *
0x1400244e5  call    memset_0
0x1400244ea  mov     r11d, 104h
0x1400244f0  test    rbx, rbx
0x1400244f3  jz      short loc_140024548
0x1400244f5  cmp     [rbx], r14w
0x1400244f9  jz      short loc_140024548
0x1400244fb  mov     r8, rbx; wchar_t *
0x1400244fe  lea     rcx, [rsp+270h+var_240]; wchar_t *
0x140024503  mov     edx, r11d; unsigned __int64
0x140024506  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14002450b  mov     ebx, eax
0x14002450d  test    eax, eax
0x14002450f  jns     short loc_140024550
0x140024511  lea     edx, [r11-9]; void *
0x140024515  mov     rcx, [rbp+178h]; this
0x14002451c  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x140024523  mov     r9d, ebx; char *
0x140024526  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002452b  mov     rcx, qword ptr [rsp+270h+var_250]
0x140024530  test    rcx, rcx
0x140024533  jz      short loc_140024541
0x140024535  mov     rdx, [rcx]
0x140024538  mov     rax, [rdx+10h]
0x14002453c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024541  mov     eax, ebx
0x140024543  jmp     loc_1400245DA
0x140024548  mov     dword ptr [rsp+270h+var_240], 2Eh ; '.'
0x140024550  lea     rcx, [rsp+270h+var_240]
0x140024555  or      rax, 0FFFFFFFFFFFFFFFFh
0x140024559  inc     rax
0x14002455c  cmp     [rcx+rax*2], r14w
0x140024561  jnz     short loc_140024559
0x140024563  cmp     [rsp+rax*2+270h+var_242], 5Ch ; '\'
0x140024569  jnz     short loc_140024582
0x14002456b  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x140024573  cmp     rcx, 208h
0x14002457a  jnb     short loc_1400245F7
0x14002457c  mov     [rsp+rcx+270h+var_240], r14w
0x140024582  lea     r8, aCbscoreDll; "\\cbscore.dll"
0x140024589  mov     rdx, r11; unsigned __int64
0x14002458c  lea     rcx, [rsp+270h+var_240]; wchar_t *
0x140024591  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140024596  mov     ebx, eax
0x140024598  test    eax, eax
0x14002459a  jns     short loc_1400245A6
0x14002459c  mov     edx, 108h
0x1400245a1  jmp     loc_140024515
0x1400245a6  lea     rcx, [rsp+270h+var_250]
0x1400245ab  call    ?GetInitPointer@?$AutoComPtr@UICbsSession@@@Windows@@QEAAPEAPEAUICbsSession@@XZ; Windows::AutoComPtr<ICbsSession>::GetInitPointer(void)
0x1400245b0  mov     r8, rax; struct ICbsSession **
0x1400245b3  lea     rdx, [rsp+270h+var_240]; wchar_t *
0x1400245b8  mov     rcx, rsi; this
0x1400245bb  call    ?CbsCreateSessionFromCbsCorePath@CbsOfflineUtil@@QEAAJPEB_WPEAPEAUICbsSession@@@Z; CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(wchar_t const *,ICbsSession * *)
0x1400245c0  mov     ebx, eax
0x1400245c2  test    eax, eax
0x1400245c4  jns     short loc_1400245D0
0x1400245c6  mov     edx, 10Ah
0x1400245cb  jmp     loc_140024515
0x1400245d0  mov     rax, qword ptr [rsp+270h+var_250]
0x1400245d5  mov     [rdi], rax
0x1400245d8  xor     eax, eax
0x1400245da  mov     rcx, [rbp+170h+var_30]
0x1400245e1  xor     rcx, rsp; StackCookie
0x1400245e4  call    __security_check_cookie
0x1400245e9  add     rsp, 250h
0x1400245f0  pop     r14
0x1400245f2  pop     rdi
0x1400245f3  pop     rsi
0x1400245f4  pop     rbx
0x1400245f5  pop     rbp
0x1400245f6  retn
0x1400245f7  call    __report_rangecheckfailure
```
