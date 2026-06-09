# CSystemPopupWindow::_SetButtonsOnDialog(void)

- ea: `0x140008790`
- end: `0x140008a33`
- name: `?_SetButtonsOnDialog@CSystemPopupWindow@@AEAAJXZ`
- size: `675`
- prototype: `__int64 __fastcall(CSystemPopupWindow *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140008124`

## callees

- `0x140001460`
- `0x1400080f4`
- `0x140008368`
- `0x140008790`
- `0x14000a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSystemPopupWindow::_SetButtonsOnDialog(CSystemPopupWindow *this)
{
  int v2; // eax
  unsigned int v3; // esi
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // [rsp+20h] [rbp-38h] BYREF
  __int64 v22; // [rsp+28h] [rbp-30h] BYREF
  _QWORD v23[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]

  v21 = 0;
  if ( *((_DWORD *)this + 3) == 1 )
  {
    v22 = 0;
    v2 = CSystemPopupWindow::_CreateCommandButton(this, 1, 1002, &v21);
    v3 = v2;
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
        (const char *)(unsigned int)v2,
        v21);
      v4 = v22;
      if ( v22 )
      {
        v22 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      }
      v5 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      }
      return v3;
    }
    v7 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    v8 = CSystemPopupWindow::_CreateCommandButton(this, 0, 1001, &v22);
    v3 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
        (const char *)(unsigned int)v8,
        v21);
      v9 = v22;
      if ( v22 )
      {
        v22 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      v10 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      return v3;
    }
    v23[0] = v22;
    v23[1] = v21;
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *))(**(_QWORD **)this + 64LL))(*(_QWORD *)this, 2, v23);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
        (const char *)(unsigned int)v11,
        v21);
      v13 = v22;
      if ( v22 )
      {
        v22 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      v14 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      return v12;
    }
    v15 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  else
  {
    v16 = CSystemPopupWindow::_CreateCommandButton(this, 1, 1003, &v21);
    v3 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
        (const char *)(unsigned int)v16,
        v21);
      v17 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      return v3;
    }
    v22 = v21;
    v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)this + 64LL))(*(_QWORD *)this, 1, &v22);
    v12 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
        (const char *)(unsigned int)v18,
        v21);
      v19 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      return v12;
    }
  }
  v20 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  return 0;
}

```

## disassembly

```asm
0x140008790  push    rbp
0x140008792  push    rbx
0x140008793  push    rsi
0x140008794  push    rdi
0x140008795  mov     rbp, rsp
0x140008798  sub     rsp, 58h
0x14000879c  mov     rax, cs:__security_cookie
0x1400087a3  xor     rax, rsp
0x1400087a6  mov     [rbp+var_18], rax
0x1400087aa  mov     rdi, rcx
0x1400087ad  xor     ebx, ebx
0x1400087af  mov     [rbp+var_38], rbx
0x1400087b3  cmp     dword ptr [rcx+0Ch], 1
0x1400087b7  jnz     loc_140008952
0x1400087bd  mov     [rbp+var_30], rbx
0x1400087c1  lea     r9, [rbp+var_38]
0x1400087c5  lea     edx, [rbx+1]
0x1400087c8  mov     r8d, 3EAh
0x1400087ce  call    ?_CreateCommandButton@CSystemPopupWindow@@AEAAJW4CommandButton@1@IPEAPEAUIPopupCommand@@@Z; CSystemPopupWindow::_CreateCommandButton(CSystemPopupWindow::CommandButton,uint,IPopupCommand * *)
0x1400087d3  mov     esi, eax
0x1400087d5  test    eax, eax
0x1400087d7  jns     short loc_14000882B
0x1400087d9  mov     rcx, [rbp+20h]; this
0x1400087dd  mov     r9d, eax; char *
0x1400087e0  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x1400087e7  lea     edx, [rbx+67h]; void *
0x1400087ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400087ef  nop
0x1400087f0  mov     rcx, [rbp+var_30]
0x1400087f4  test    rcx, rcx
0x1400087f7  jz      short loc_14000880A
0x1400087f9  mov     [rbp+var_30], rbx
0x1400087fd  mov     rax, [rcx]
0x140008800  mov     rax, [rax+10h]
0x140008804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008809  nop
0x14000880a  mov     rcx, [rbp+var_38]
0x14000880e  test    rcx, rcx
0x140008811  jz      short loc_140008824
0x140008813  mov     [rbp+var_38], rbx
0x140008817  mov     rax, [rcx]
0x14000881a  mov     rax, [rax+10h]
0x14000881e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008823  nop
0x140008824  mov     eax, esi
0x140008826  jmp     loc_140008A1E
0x14000882b  mov     rcx, [rbp+var_30]
0x14000882f  test    rcx, rcx
0x140008832  jz      short loc_140008845
0x140008834  mov     [rbp+var_30], rbx
0x140008838  mov     rax, [rcx]
0x14000883b  mov     rax, [rax+10h]
0x14000883f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008844  nop
0x140008845  lea     r9, [rbp+var_30]
0x140008849  xor     edx, edx
0x14000884b  mov     r8d, 3E9h
0x140008851  mov     rcx, rdi
0x140008854  call    ?_CreateCommandButton@CSystemPopupWindow@@AEAAJW4CommandButton@1@IPEAPEAUIPopupCommand@@@Z; CSystemPopupWindow::_CreateCommandButton(CSystemPopupWindow::CommandButton,uint,IPopupCommand * *)
0x140008859  mov     esi, eax
0x14000885b  test    eax, eax
0x14000885d  jns     short loc_1400088B1
0x14000885f  mov     rcx, [rbp+20h]; this
0x140008863  mov     r9d, eax; char *
0x140008866  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x14000886d  mov     edx, 68h ; 'h'; void *
0x140008872  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008877  nop
0x140008878  mov     rcx, [rbp+var_30]
0x14000887c  test    rcx, rcx
0x14000887f  jz      short loc_140008892
0x140008881  mov     [rbp+var_30], rbx
0x140008885  mov     rax, [rcx]
0x140008888  mov     rax, [rax+10h]
0x14000888c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008891  nop
0x140008892  mov     rcx, [rbp+var_38]
0x140008896  test    rcx, rcx
0x140008899  jz      short loc_1400088AC
0x14000889b  mov     [rbp+var_38], rbx
0x14000889f  mov     rax, [rcx]
0x1400088a2  mov     rax, [rax+10h]
0x1400088a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400088ab  nop
0x1400088ac  jmp     loc_140008824
0x1400088b1  mov     rax, [rbp+var_30]
0x1400088b5  mov     [rbp+var_28], rax
0x1400088b9  mov     rax, [rbp+var_38]
0x1400088bd  mov     [rbp+var_20], rax
0x1400088c1  mov     rcx, [rdi]
0x1400088c4  mov     rax, [rcx]
0x1400088c7  lea     r8, [rbp+var_28]
0x1400088cb  mov     edx, 2
0x1400088d0  mov     rax, [rax+40h]
0x1400088d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400088d9  mov     edi, eax
0x1400088db  test    eax, eax
0x1400088dd  jns     short loc_140008933
0x1400088df  mov     rcx, [rbp+20h]; this
0x1400088e3  mov     r9d, eax; char *
0x1400088e6  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x1400088ed  mov     edx, 6Ah ; 'j'; void *
0x1400088f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400088f7  nop
0x1400088f8  mov     rcx, [rbp+var_30]
0x1400088fc  test    rcx, rcx
0x1400088ff  jz      short loc_140008912
0x140008901  mov     [rbp+var_30], rbx
0x140008905  mov     rax, [rcx]
0x140008908  mov     rax, [rax+10h]
0x14000890c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008911  nop
0x140008912  mov     rcx, [rbp+var_38]
0x140008916  test    rcx, rcx
0x140008919  jz      short loc_14000892C
0x14000891b  mov     [rbp+var_38], rbx
0x14000891f  mov     rax, [rcx]
0x140008922  mov     rax, [rax+10h]
0x140008926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000892b  nop
0x14000892c  mov     eax, edi
0x14000892e  jmp     loc_140008A1E
0x140008933  mov     rcx, [rbp+var_30]
0x140008937  test    rcx, rcx
0x14000893a  jz      short loc_14000894D
0x14000893c  mov     [rbp+var_30], rbx
0x140008940  mov     rax, [rcx]
0x140008943  mov     rax, [rax+10h]
0x140008947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000894c  nop
0x14000894d  jmp     loc_140008A02
0x140008952  lea     r9, [rbp+var_38]
0x140008956  mov     edx, 1
0x14000895b  mov     r8d, 3EBh
0x140008961  call    ?_CreateCommandButton@CSystemPopupWindow@@AEAAJW4CommandButton@1@IPEAPEAUIPopupCommand@@@Z; CSystemPopupWindow::_CreateCommandButton(CSystemPopupWindow::CommandButton,uint,IPopupCommand * *)
0x140008966  mov     esi, eax
0x140008968  test    eax, eax
0x14000896a  jns     short loc_1400089A4
0x14000896c  mov     rcx, [rbp+20h]; this
0x140008970  mov     r9d, eax; char *
0x140008973  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x14000897a  mov     edx, 6Fh ; 'o'; void *
0x14000897f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008984  nop
0x140008985  mov     rcx, [rbp+var_38]
0x140008989  test    rcx, rcx
0x14000898c  jz      short loc_14000899F
0x14000898e  mov     [rbp+var_38], rbx
0x140008992  mov     rax, [rcx]
0x140008995  mov     rax, [rax+10h]
0x140008999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000899e  nop
0x14000899f  jmp     loc_140008824
0x1400089a4  mov     rax, [rbp+var_38]
0x1400089a8  mov     [rbp+var_30], rax
0x1400089ac  mov     rcx, [rdi]
0x1400089af  mov     rax, [rcx]
0x1400089b2  lea     r8, [rbp+var_30]
0x1400089b6  mov     edx, 1
0x1400089bb  mov     rax, [rax+40h]
0x1400089bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400089c4  mov     edi, eax
0x1400089c6  test    eax, eax
0x1400089c8  jns     short loc_140008A02
0x1400089ca  mov     rcx, [rbp+20h]; this
0x1400089ce  mov     r9d, eax; char *
0x1400089d1  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x1400089d8  mov     edx, 71h ; 'q'; void *
0x1400089dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400089e2  nop
0x1400089e3  mov     rcx, [rbp+var_38]
0x1400089e7  test    rcx, rcx
0x1400089ea  jz      short loc_1400089FD
0x1400089ec  mov     [rbp+var_38], rbx
0x1400089f0  mov     rax, [rcx]
0x1400089f3  mov     rax, [rax+10h]
0x1400089f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400089fc  nop
0x1400089fd  jmp     loc_14000892C
0x140008a02  mov     rcx, [rbp+var_38]
0x140008a06  test    rcx, rcx
0x140008a09  jz      short loc_140008A1C
0x140008a0b  mov     [rbp+var_38], rbx
0x140008a0f  mov     rax, [rcx]
0x140008a12  mov     rax, [rax+10h]
0x140008a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a1b  nop
0x140008a1c  xor     eax, eax
0x140008a1e  mov     rcx, [rbp+var_18]
0x140008a22  xor     rcx, rsp; StackCookie
0x140008a25  call    __security_check_cookie
0x140008a2a  add     rsp, 58h
0x140008a2e  pop     rdi
0x140008a2f  pop     rsi
0x140008a30  pop     rbx
0x140008a31  pop     rbp
0x140008a32  retn
```
