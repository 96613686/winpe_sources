# CbsOfflineUtil::CbsCreateOfflineSessionFromStackInImage(int,wchar_t const *,ICbsSession * *)

- ea: `0x140024ed0`
- end: `0x140024fcf`
- name: `?CbsCreateOfflineSessionFromStackInImage@CbsOfflineUtil@@UEAAJHPEB_WPEAPEAUICbsSession@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(CbsOfflineUtil *this, __int64, const wchar_t *, struct ICbsSession **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x140024604`
- `0x140024aa0`
- `0x140024ed0`
- `0x1400258f0`
- `0x14002a010`

## string_xrefs

- `0x140024f0b`: `cbscore.dll`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CbsCreateOfflineSessionFromStackInImage(
        CbsOfflineUtil *this,
        __int64 a2,
        const wchar_t *a3,
        struct ICbsSession **a4)
{
  __int64 v5; // rax
  int SessionFromCbsCorePath; // ebx
  __int64 v8; // rdx
  struct ICbsSession **InitPointer; // rax
  struct ICbsSession *v11; // [rsp+30h] [rbp-28h] BYREF
  wchar_t *v12; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]

  *a4 = 0;
  v5 = *(_QWORD *)this;
  v11 = 0;
  v12 = 0;
  SessionFromCbsCorePath = (*(__int64 (__fastcall **)(CbsOfflineUtil *, __int64, const wchar_t *, const wchar_t *))(v5 + 56))(
                             this,
                             a2,
                             a3,
                             L"cbscore.dll");
  if ( SessionFromCbsCorePath < 0 )
  {
    v8 = 340;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
      (const char *)(unsigned int)SessionFromCbsCorePath,
      (int)&v12);
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v12);
    if ( v11 )
      (*(void (__fastcall **)(struct ICbsSession *))(*(_QWORD *)v11 + 16LL))(v11);
    return (unsigned int)SessionFromCbsCorePath;
  }
  InitPointer = (struct ICbsSession **)Windows::AutoComPtr<ICbsSession>::GetInitPointer(&v11);
  SessionFromCbsCorePath = CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(this, v12, InitPointer);
  if ( SessionFromCbsCorePath < 0 )
  {
    v8 = 341;
    goto LABEL_3;
  }
  *a4 = v11;
  v11 = 0;
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v12);
  if ( v11 )
    (*(void (__fastcall **)(struct ICbsSession *))(*(_QWORD *)v11 + 16LL))(v11);
  return 0;
}

```

## disassembly

```asm
0x140024ed0  push    rbp
0x140024ed2  push    rbx
0x140024ed3  push    rsi
0x140024ed4  push    rdi
0x140024ed5  mov     rbp, rsp
0x140024ed8  sub     rsp, 58h
0x140024edc  mov     rax, cs:__security_cookie
0x140024ee3  xor     rax, rsp
0x140024ee6  mov     [rbp+var_18], rax
0x140024eea  mov     qword ptr [r9], 0
0x140024ef1  mov     rsi, rcx
0x140024ef4  mov     rax, [rcx]
0x140024ef7  mov     rdi, r9
0x140024efa  lea     rcx, [rbp+var_20]
0x140024efe  mov     [rbp+var_28], 0
0x140024f06  mov     qword ptr [rsp+58h+var_38], rcx; int
0x140024f0b  lea     r9, aCbscoreDll_0; "cbscore.dll"
0x140024f12  mov     rcx, rsi
0x140024f15  mov     [rbp+var_20], 0
0x140024f1d  mov     rax, [rax+38h]
0x140024f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024f26  mov     ebx, eax
0x140024f28  test    eax, eax
0x140024f2a  jns     short loc_140024F66
0x140024f2c  mov     edx, 154h; void *
0x140024f31  mov     rcx, [rbp+20h]; this
0x140024f35  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x140024f3c  mov     r9d, ebx; char *
0x140024f3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024f44  lea     rcx, [rbp+var_20]
0x140024f48  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x140024f4d  mov     rcx, [rbp+var_28]
0x140024f51  test    rcx, rcx
0x140024f54  jz      short loc_140024F62
0x140024f56  mov     rax, [rcx]
0x140024f59  mov     rax, [rax+10h]
0x140024f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024f62  mov     eax, ebx
0x140024f64  jmp     short loc_140024FBA
0x140024f66  lea     rcx, [rbp+var_28]
0x140024f6a  call    ?GetInitPointer@?$AutoComPtr@UICbsSession@@@Windows@@QEAAPEAPEAUICbsSession@@XZ; Windows::AutoComPtr<ICbsSession>::GetInitPointer(void)
0x140024f6f  mov     rdx, [rbp+var_20]; wchar_t *
0x140024f73  mov     r8, rax; struct ICbsSession **
0x140024f76  mov     rcx, rsi; this
0x140024f79  call    ?CbsCreateSessionFromCbsCorePath@CbsOfflineUtil@@QEAAJPEB_WPEAPEAUICbsSession@@@Z; CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(wchar_t const *,ICbsSession * *)
0x140024f7e  mov     ebx, eax
0x140024f80  test    eax, eax
0x140024f82  jns     short loc_140024F8B
0x140024f84  mov     edx, 155h
0x140024f89  jmp     short loc_140024F31
0x140024f8b  mov     rax, [rbp+var_28]
0x140024f8f  lea     rcx, [rbp+var_20]
0x140024f93  mov     [rdi], rax
0x140024f96  mov     [rbp+var_28], 0
0x140024f9e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x140024fa3  mov     rcx, [rbp+var_28]
0x140024fa7  test    rcx, rcx
0x140024faa  jz      short loc_140024FB8
0x140024fac  mov     rax, [rcx]
0x140024faf  mov     rax, [rax+10h]
0x140024fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024fb8  xor     eax, eax
0x140024fba  mov     rcx, [rbp+var_18]
0x140024fbe  xor     rcx, rsp; StackCookie
0x140024fc1  call    __security_check_cookie
0x140024fc6  add     rsp, 58h
0x140024fca  pop     rdi
0x140024fcb  pop     rsi
0x140024fcc  pop     rbx
0x140024fcd  pop     rbp
0x140024fce  retn
```
