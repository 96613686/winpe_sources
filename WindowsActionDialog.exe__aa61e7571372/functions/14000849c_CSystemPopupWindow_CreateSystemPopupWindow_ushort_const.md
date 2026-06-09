# CSystemPopupWindow::_CreateSystemPopupWindow(ushort const *)

- ea: `0x14000849c`
- end: `0x140008691`
- name: `?_CreateSystemPopupWindow@CSystemPopupWindow@@AEAAJPEBG@Z`
- size: `501`
- prototype: `__int64 __fastcall(CSystemPopupWindow *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008124`

## callees

- `0x140001460`
- `0x1400080f4`
- `0x14000849c`
- `0x14000a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1400084ee`
- `ole32!CoCreateInstance` at `0x1400084ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSystemPopupWindow::_CreateSystemPopupWindow(CSystemPopupWindow *this, const unsigned __int16 *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  LPVOID v6; // rcx
  int v8; // eax
  LPVOID v9; // rcx
  LPVOID v10; // rbx
  __int64 (__fastcall *v11)(LPVOID, CSystemPopupWindow *); // rsi
  __int64 v12; // rcx
  int v13; // eax
  LPVOID v14; // rcx
  int v15; // eax
  LPVOID v16; // rcx
  LPVOID v17; // rcx
  int ppv; // [rsp+20h] [rbp-20h]
  LPVOID v19; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]

  v19 = 0;
  v4 = CoCreateInstance(&CLSID_PopupWindowFactory, 0, 1u, &GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1, &v19);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    v6 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return v5;
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v19 + 24LL))(v19, 1);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
      (const char *)(unsigned int)v8,
      ppv);
    v9 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v5;
  }
  v10 = v19;
  v11 = *(__int64 (__fastcall **)(LPVOID, CSystemPopupWindow *))(*(_QWORD *)v19 + 80LL);
  v12 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    *(_QWORD *)this = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = v11(v10, this);
  v5 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
      (const char *)(unsigned int)v13,
      ppv);
    v14 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return v5;
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(**(_QWORD **)this + 32LL))(*(_QWORD *)this, a2);
  v5 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
      (const char *)(unsigned int)v15,
      ppv);
    v16 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v5;
  }
  v17 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x14000849c  mov     [rsp-18h+arg_10], rbx
0x1400084a1  mov     [rsp-18h+arg_18], rsi
0x1400084a6  push    rbp
0x1400084a7  push    rdi
0x1400084a8  push    r14
0x1400084aa  mov     rbp, rsp
0x1400084ad  sub     rsp, 40h
0x1400084b1  mov     rax, cs:__security_cookie
0x1400084b8  xor     rax, rsp
0x1400084bb  mov     [rbp+var_8], rax
0x1400084bf  mov     r14, rdx
0x1400084c2  mov     rdi, rcx
0x1400084c5  mov     [rbp+var_10], 0
0x1400084cd  lea     rax, [rbp+var_10]
0x1400084d1  mov     qword ptr [rsp+40h+ppv], rax; int
0x1400084d6  lea     r9, _GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1; riid
0x1400084dd  mov     esi, 1
0x1400084e2  mov     r8d, esi; dwClsContext
0x1400084e5  xor     edx, edx; pUnkOuter
0x1400084e7  lea     rcx, CLSID_PopupWindowFactory; rclsid
0x1400084ee  call    cs:__imp_CoCreateInstance
0x1400084f4  mov     ebx, eax
0x1400084f6  test    eax, eax
0x1400084f8  jns     short loc_140008536
0x1400084fa  mov     rcx, [rbp+18h]; this
0x1400084fe  mov     r9d, eax; char *
0x140008501  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x140008508  lea     edx, [rsi+59h]; void *
0x14000850b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008510  nop
0x140008511  mov     rcx, [rbp+var_10]
0x140008515  test    rcx, rcx
0x140008518  jz      short loc_14000852F
0x14000851a  mov     [rbp+var_10], 0
0x140008522  mov     rax, [rcx]
0x140008525  mov     rax, [rax+10h]
0x140008529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000852e  nop
0x14000852f  mov     eax, ebx
0x140008531  jmp     loc_140008672
0x140008536  mov     rcx, [rbp+var_10]
0x14000853a  mov     rax, [rcx]
0x14000853d  mov     edx, esi
0x14000853f  mov     rax, [rax+18h]
0x140008543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008548  mov     ebx, eax
0x14000854a  test    eax, eax
0x14000854c  jns     short loc_140008587
0x14000854e  mov     rcx, [rbp+18h]; this
0x140008552  mov     r9d, eax; char *
0x140008555  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x14000855c  mov     edx, 5Bh ; '['; void *
0x140008561  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008566  nop
0x140008567  mov     rcx, [rbp+var_10]
0x14000856b  test    rcx, rcx
0x14000856e  jz      short loc_140008585
0x140008570  mov     [rbp+var_10], 0
0x140008578  mov     rax, [rcx]
0x14000857b  mov     rax, [rax+10h]
0x14000857f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008584  nop
0x140008585  jmp     short loc_14000852F
0x140008587  mov     rbx, [rbp+var_10]
0x14000858b  mov     rax, [rbx]
0x14000858e  mov     rsi, [rax+50h]
0x140008592  mov     rcx, [rdi]
0x140008595  test    rcx, rcx
0x140008598  jz      short loc_1400085AE
0x14000859a  mov     qword ptr [rdi], 0
0x1400085a1  mov     rdx, [rcx]
0x1400085a4  mov     rax, [rdx+10h]
0x1400085a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085ad  nop
0x1400085ae  mov     rdx, rdi
0x1400085b1  mov     rcx, rbx
0x1400085b4  mov     rax, rsi
0x1400085b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085bc  mov     ebx, eax
0x1400085be  test    eax, eax
0x1400085c0  jns     short loc_1400085FE
0x1400085c2  mov     rcx, [rbp+18h]; this
0x1400085c6  mov     r9d, eax; char *
0x1400085c9  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x1400085d0  mov     edx, 5Ch ; '\'; void *
0x1400085d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400085da  nop
0x1400085db  mov     rcx, [rbp+var_10]
0x1400085df  test    rcx, rcx
0x1400085e2  jz      short loc_1400085F9
0x1400085e4  mov     [rbp+var_10], 0
0x1400085ec  mov     rax, [rcx]
0x1400085ef  mov     rax, [rax+10h]
0x1400085f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085f8  nop
0x1400085f9  jmp     loc_14000852F
0x1400085fe  mov     rcx, [rdi]
0x140008601  mov     rax, [rcx]
0x140008604  mov     rdx, r14
0x140008607  mov     rax, [rax+20h]
0x14000860b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008610  mov     ebx, eax
0x140008612  test    eax, eax
0x140008614  jns     short loc_140008652
0x140008616  mov     rcx, [rbp+18h]; this
0x14000861a  mov     r9d, eax; char *
0x14000861d  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x140008624  mov     edx, 5Dh ; ']'; void *
0x140008629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000862e  nop
0x14000862f  mov     rcx, [rbp+var_10]
0x140008633  test    rcx, rcx
0x140008636  jz      short loc_14000864D
0x140008638  mov     [rbp+var_10], 0
0x140008640  mov     rax, [rcx]
0x140008643  mov     rax, [rax+10h]
0x140008647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000864c  nop
0x14000864d  jmp     loc_14000852F
0x140008652  mov     rcx, [rbp+var_10]
0x140008656  test    rcx, rcx
0x140008659  jz      short loc_140008670
0x14000865b  mov     [rbp+var_10], 0
0x140008663  mov     rax, [rcx]
0x140008666  mov     rax, [rax+10h]
0x14000866a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000866f  nop
0x140008670  xor     eax, eax
0x140008672  mov     rcx, [rbp+var_8]
0x140008676  xor     rcx, rsp; StackCookie
0x140008679  call    __security_check_cookie
0x14000867e  mov     rbx, [rsp+40h+arg_10]
0x140008683  mov     rsi, [rsp+40h+arg_18]
0x140008688  add     rsp, 40h
0x14000868c  pop     r14
0x14000868e  pop     rdi
0x14000868f  pop     rbp
0x140008690  retn
```
