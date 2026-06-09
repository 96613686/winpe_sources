# _AfxActivationWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18001b510`
- end: `0x18001b6ba`
- name: `?_AfxActivationWndProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `426`
- prototype: `__int64 __fastcall(HWND, UINT Msg, WPARAM wParam, HWND)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800410a0`

## callees

- `0x1800069d4`
- `0x180006a4c`
- `0x1800122f0`
- `0x18001b510`
- `0x18001b6c0`
- `0x180041118`
- `0x1800d1fe0`

## import_xrefs

- `KERNEL32!GlobalFindAtomW` at `0x18001b5ee`
- `KERNEL32!GlobalFindAtomW` at `0x18001b5ee`
- `KERNEL32!GlobalDeleteAtom` at `0x18001b5f7`
- `KERNEL32!GlobalDeleteAtom` at `0x18001b5f7`
- `USER32!GetPropW` at `0x18001b558`
- `USER32!GetPropW` at `0x18001b558`
- `USER32!CallWindowProcW` at `0x18001b599`
- `USER32!CallWindowProcW` at `0x18001b667`
- `USER32!CallWindowProcW` at `0x18001b599`
- `USER32!CallWindowProcW` at `0x18001b667`
- `USER32!SetWindowLongPtrW` at `0x18001b5d1`
- `USER32!SetWindowLongPtrW` at `0x18001b5d1`
- `USER32!RemovePropW` at `0x18001b5e1`
- `USER32!RemovePropW` at `0x18001b5e1`

## pseudocode

```c
LRESULT __fastcall _AfxActivationWndProc(HWND a1, UINT Msg, WPARAM wParam, HWND a4)
{
  LRESULT (__stdcall *PropW)(HWND, UINT, WPARAM, LPARAM); // rax
  LRESULT (__stdcall *v9)(HWND, UINT, WPARAM, LPARAM); // r12
  LRESULT v10; // rbx
  ATOM AtomW; // ax
  struct CWnd *v13; // rax
  int v14; // eax
  struct CWnd *v15; // rdi
  struct CWnd *v16; // rbx
  struct CWnd *v17; // rax
  struct CWinThread *Thread; // rax
  unsigned int v19; // [rsp+30h] [rbp-B8h] BYREF
  UINT v20; // [rsp+38h] [rbp-B0h]
  HWND v21; // [rsp+40h] [rbp-A8h]
  HWND v22; // [rsp+48h] [rbp-A0h]
  WPARAM v23; // [rsp+50h] [rbp-98h]
  __int128 v24; // [rsp+58h] [rbp-90h] BYREF
  WPARAM v25; // [rsp+68h] [rbp-80h]
  HWND v26; // [rsp+70h] [rbp-78h]
  __int128 v27; // [rsp+78h] [rbp-70h]
  CException *v28; // [rsp+88h] [rbp-60h] BYREF
  struct tagRECT v29; // [rsp+90h] [rbp-58h] BYREF

  v22 = a1;
  v20 = Msg;
  v23 = wParam;
  v21 = a4;
  PropW = (LRESULT (__stdcall *)(HWND, UINT, WPARAM, LPARAM))GetPropW(a1, L"AfxOldWndProc423");
  v9 = PropW;
  v10 = 0;
  if ( Msg == 6 )
  {
    v16 = CWnd::FromHandle(a4);
    v17 = CWnd::FromHandle(a1);
    _AfxHandleActivate(v17, wParam, v16);
    return CallWindowProcW(v9, a1, Msg, wParam, (LPARAM)a4);
  }
  if ( Msg != 32 )
  {
    if ( Msg == 130 )
    {
      SetWindowLongPtrW(a1, -4, (LONG_PTR)PropW);
      RemovePropW(a1, L"AfxOldWndProc423");
      AtomW = GlobalFindAtomW(L"AfxOldWndProc423");
      GlobalDeleteAtom(AtomW);
    }
    else if ( Msg == 272 )
    {
      v19 = 0;
      v15 = CWnd::FromHandle(a1);
      _AfxPreInitDialog(v15, &v29, &v19);
      v10 = CallWindowProcW(v9, a1, 0x110u, wParam, (LPARAM)a4);
      _AfxPostInitDialog(v15, &v29, v19);
      return v10;
    }
    return CallWindowProcW(v9, a1, Msg, wParam, (LPARAM)a4);
  }
  try
  {
    v13 = CWnd::FromHandle(a1);
    v14 = _AfxHandleSetCursor(v13, (__int16)a4, WORD1(a4));
  }
  catch ( CException *v28 )
  {
    v24 = 0;
    v27 = 0;
    *(_QWORD *)&v24 = v22;
    DWORD2(v24) = v20;
    v25 = v23;
    v26 = v21;
    Thread = AfxGetThread();
    v21 = (HWND)(*(__int64 (__fastcall **)(struct CWinThread *, CException *, __int128 *))(*(_QWORD *)Thread + 232LL))(
                  Thread,
                  v28,
                  &v24);
    CException::Delete(v28);
    return (LRESULT)v21;
  }
  if ( !v14 )
    return CallWindowProcW(v9, a1, Msg, wParam, (LPARAM)a4);
  return v10;
}

```

## disassembly

```asm
0x18001b510  push    rbx
0x18001b512  push    rsi
0x18001b513  push    rdi
0x18001b514  push    r12
0x18001b516  push    r14
0x18001b518  push    r15
0x18001b51a  sub     rsp, 0B8h
0x18001b521  mov     rax, cs:__security_cookie
0x18001b528  xor     rax, rsp
0x18001b52b  mov     [rsp+0E8h+var_48], rax
0x18001b533  mov     r14, r9
0x18001b536  mov     r15, r8
0x18001b539  mov     edi, edx
0x18001b53b  mov     rsi, rcx
0x18001b53e  mov     [rsp+0E8h+var_A0], rcx
0x18001b543  mov     [rsp+0E8h+var_B0], edx
0x18001b547  mov     [rsp+0E8h+var_98], r8
0x18001b54c  mov     [rsp+0E8h+var_A8], r9
0x18001b551  lea     rdx, ?_afxOldWndProc@@3QBGB; "AfxOldWndProc423"
0x18001b558  call    cs:__imp_GetPropW
0x18001b55e  mov     r12, rax
0x18001b561  xor     ebx, ebx
0x18001b563  mov     ecx, edi
0x18001b565  sub     ecx, 6
0x18001b568  jz      loc_18001B68A
0x18001b56e  sub     ecx, 1Ah
0x18001b571  jz      loc_18001B5FF
0x18001b577  sub     ecx, 62h ; 'b'
0x18001b57a  jz      short loc_18001B5C6
0x18001b57c  cmp     ecx, 8Eh
0x18001b582  jz      loc_18001B62B
0x18001b588  mov     [rsp+0E8h+lParam], r14; lParam
0x18001b58d  mov     r9, r15; wParam
0x18001b590  mov     r8d, edi; Msg
0x18001b593  mov     rdx, rsi; hWnd
0x18001b596  mov     rcx, r12; lpPrevWndFunc
0x18001b599  call    cs:__imp_CallWindowProcW
0x18001b59f  mov     rbx, rax
0x18001b5a2  mov     rax, rbx
0x18001b5a5  mov     rcx, [rsp+0E8h+var_48]
0x18001b5ad  xor     rcx, rsp; StackCookie
0x18001b5b0  call    __security_check_cookie
0x18001b5b5  add     rsp, 0B8h
0x18001b5bc  pop     r15
0x18001b5be  pop     r14
0x18001b5c0  pop     r12
0x18001b5c2  pop     rdi
0x18001b5c3  pop     rsi
0x18001b5c4  pop     rbx
0x18001b5c5  retn
0x18001b5c6  mov     r8, r12; dwNewLong
0x18001b5c9  mov     edx, 0FFFFFFFCh; nIndex
0x18001b5ce  mov     rcx, rsi; hWnd
0x18001b5d1  call    cs:__imp_SetWindowLongPtrW
0x18001b5d7  lea     rdx, ?_afxOldWndProc@@3QBGB; "AfxOldWndProc423"
0x18001b5de  mov     rcx, rsi; hWnd
0x18001b5e1  call    cs:__imp_RemovePropW
0x18001b5e7  lea     rcx, ?_afxOldWndProc@@3QBGB; "AfxOldWndProc423"
0x18001b5ee  call    cs:__imp_GlobalFindAtomW
0x18001b5f4  movzx   ecx, ax; nAtom
0x18001b5f7  call    cs:__imp_GlobalDeleteAtom
0x18001b5fd  jmp     short loc_18001B588
0x18001b5ff  mov     rcx, rsi; HWND
0x18001b602  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x18001b607  mov     rcx, r14
0x18001b60a  shr     rcx, 10h
0x18001b60e  movzx   r8d, cx; unsigned int
0x18001b612  movsx   edx, r14w; unsigned int
0x18001b616  mov     rcx, rax; struct CWnd *
0x18001b619  call    ?_AfxHandleSetCursor@@YAHPEAVCWnd@@II@Z; _AfxHandleSetCursor(CWnd *,uint,uint)
0x18001b61e  test    eax, eax
0x18001b620  jz      loc_18001B588
0x18001b626  jmp     loc_18001B5A2
0x18001b62b  mov     [rsp+0E8h+var_B8], 0
0x18001b633  mov     rcx, rsi; HWND
0x18001b636  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x18001b63b  mov     rdi, rax
0x18001b63e  lea     r8, [rsp+0E8h+var_B8]; unsigned int *
0x18001b643  lea     rdx, [rsp+0E8h+var_58]; struct tagRECT *
0x18001b64b  mov     rcx, rax; this
0x18001b64e  call    ?_AfxPreInitDialog@@YAXPEAVCWnd@@PEAUtagRECT@@PEAK@Z; _AfxPreInitDialog(CWnd *,tagRECT *,ulong *)
0x18001b653  mov     [rsp+0E8h+lParam], r14; lParam
0x18001b658  mov     r9, r15; wParam
0x18001b65b  mov     r8d, 110h; Msg
0x18001b661  mov     rdx, rsi; hWnd
0x18001b664  mov     rcx, r12; lpPrevWndFunc
0x18001b667  call    cs:__imp_CallWindowProcW
0x18001b66d  mov     rbx, rax
0x18001b670  mov     r8d, [rsp+0E8h+var_B8]; unsigned int
0x18001b675  lea     rdx, [rsp+0E8h+var_58]; struct tagRECT *
0x18001b67d  mov     rcx, rdi; this
0x18001b680  call    ?_AfxPostInitDialog@@YAXPEAVCWnd@@AEBUtagRECT@@K@Z; _AfxPostInitDialog(CWnd *,tagRECT const &,ulong)
0x18001b685  jmp     loc_18001B5A2
0x18001b68a  mov     rcx, r14; HWND
0x18001b68d  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x18001b692  mov     rbx, rax
0x18001b695  mov     rcx, rsi; HWND
0x18001b698  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x18001b69d  mov     r8, rbx; struct CWnd *
0x18001b6a0  mov     rdx, r15; wParam
0x18001b6a3  mov     rcx, rax; this
0x18001b6a6  call    ?_AfxHandleActivate@@YAXPEAVCWnd@@_K0@Z; _AfxHandleActivate(CWnd *,unsigned __int64,CWnd *)
0x18001b6ab  jmp     loc_18001B588
0x18001b6b0  mov     rax, [rsp+0E8h+var_A8]
0x18001b6b5  jmp     loc_18001B5A5
```
