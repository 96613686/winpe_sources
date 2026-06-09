# CWnd::CreateDlgIndirect(DLGTEMPLATE const *,CWnd *,HINSTANCE__ *)

- ea: `0x1800081f0`
- end: `0x18000848d`
- name: `?CreateDlgIndirect@CWnd@@IEAAHPEBUDLGTEMPLATE@@PEAV1@PEAUHINSTANCE__@@@Z`
- size: `669`
- prototype: `__int64 __fastcall(CWnd *__hidden this, const struct DLGTEMPLATE *, struct CWnd *, HINSTANCE)`
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x18002cc90`
- `0x1800562b0`
- `0x180056350`
- `0x180056390`

## callees

- `0x1800067a0`
- `0x180006810`
- `0x1800081f0`
- `0x180008930`
- `0x180013330`
- `0x180019290`
- `0x18005bf00`
- `0x18005bf50`
- `0x18005bfb0`
- `0x18005c580`
- `0x1800d1faa`
- `0x1800d7010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18000846a`
- `KERNEL32!GlobalFree` at `0x18000846a`
- `KERNEL32!GlobalUnlock` at `0x180008461`
- `KERNEL32!GlobalUnlock` at `0x180008461`
- `KERNEL32!GlobalLock` at `0x18000837f`
- `KERNEL32!GlobalLock` at `0x18000837f`
- `USER32!GetSystemMetrics` at `0x1800082de`
- `USER32!GetSystemMetrics` at `0x1800082de`
- `USER32!DestroyWindow` at `0x180008450`
- `USER32!DestroyWindow` at `0x180008450`
- `USER32!CreateDialogIndirectParamW` at `0x1800083c1`
- `USER32!CreateDialogIndirectParamW` at `0x1800083c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CWnd::CreateDlgIndirect(CWnd *this, const struct DLGTEMPLATE *a2, struct CWnd *a3, HINSTANCE a4)
{
  HINSTANCE v4; // r13
  struct CWnd *v5; // rbx
  unsigned int v8; // edi
  __int64 v9; // r15
  HGLOBAL v10; // r14
  __int64 result; // rax
  wchar_t *v12; // rbx
  unsigned __int16 v13; // bx
  HWND v14; // r8
  HWND DialogIndirectParamW; // rbx
  wchar_t *String1; // [rsp+30h] [rbp-88h] BYREF
  HGLOBAL v17; // [rsp+38h] [rbp-80h]
  HWND v18; // [rsp+40h] [rbp-78h]
  __int64 v19; // [rsp+48h] [rbp-70h]
  HGLOBAL hMem[2]; // [rsp+58h] [rbp-60h] BYREF
  _OWORD v21[5]; // [rsp+68h] [rbp-50h] BYREF
  unsigned __int16 v23; // [rsp+D8h] [rbp+20h] BYREF

  v4 = a4;
  v5 = a3;
  v8 = 0;
  if ( !a4 )
    v4 = (HINSTANCE)*((_QWORD *)AfxGetModuleState() + 2);
  v21[0] = 0;
  v9 = *((_QWORD *)AfxGetModuleState() + 1043);
  v19 = v9;
  v10 = 0;
  v17 = 0;
  v18 = 0;
  AfxEndDeferRegisterClass(16);
  AfxEndDeferRegisterClass(245760);
  if ( v9 )
  {
    result = (*(__int64 (__fastcall **)(CWnd *, _OWORD *))(*(_QWORD *)this + 376LL))(this, v21);
    if ( !(_DWORD)result )
      return result;
    a2 = (const struct DLGTEMPLATE *)(*(__int64 (__fastcall **)(__int64, _OWORD *, const struct DLGTEMPLATE *))(*(_QWORD *)v9 + 32LL))(
                                       v9,
                                       v21,
                                       a2);
  }
  if ( !a2 )
    return 0;
  String1 = (wchar_t *)_afxPchNil;
  v23 = 0;
  if ( !(unsigned int)CDialogTemplate::GetFont(a2, (struct CString *)&String1, &v23) )
  {
    v13 = v23;
    goto LABEL_16;
  }
  if ( GetSystemMetrics(42) )
  {
    v12 = String1;
    if ( wcscmp_0(String1, L"MS Shell Dlg") && wcscmp_0(v12, L"MS Sans Serif") && wcscmp_0(v12, L"Helv") )
    {
LABEL_18:
      v5 = a3;
      goto LABEL_19;
    }
    v13 = v23;
    if ( v23 == 8 )
      v13 = 0;
LABEL_16:
    CDialogTemplate::CDialogTemplate((CDialogTemplate *)hMem, a2);
    CDialogTemplate::SetSystemFont((CDialogTemplate *)hMem, v13);
    v10 = hMem[0];
    hMem[0] = 0;
    v17 = v10;
    CDialogTemplate::~CDialogTemplate((CDialogTemplate *)hMem);
    if ( v10 )
      a2 = (const struct DLGTEMPLATE *)GlobalLock(v10);
    goto LABEL_18;
  }
LABEL_19:
  *((_DWORD *)this + 24) = -1;
  *((_DWORD *)this + 20) |= 0x10u;
  AfxHookWindowCreate(this);
  v14 = 0;
  if ( v5 )
    v14 = (HWND)*((_QWORD *)v5 + 8);
  DialogIndirectParamW = CreateDialogIndirectParamW(v4, a2, v14, AfxDlgProc, 0);
  v18 = DialogIndirectParamW;
  CString::~CString((CString *)&String1);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v9 + 40LL))(v9, v21);
    if ( DialogIndirectParamW )
      (*(void (__fastcall **)(CWnd *, _QWORD))(*(_QWORD *)this + 376LL))(this, 0);
  }
  if ( !(unsigned int)AfxUnhookWindowCreate() )
    (*(void (__fastcall **)(CWnd *))(*(_QWORD *)this + 344LL))(this);
  if ( DialogIndirectParamW && (*((_BYTE *)this + 80) & 0x10) == 0 )
  {
    DestroyWindow(DialogIndirectParamW);
    DialogIndirectParamW = 0;
  }
  if ( v10 )
  {
    GlobalUnlock(v10);
    GlobalFree(v10);
  }
  LOBYTE(v8) = DialogIndirectParamW != 0;
  return v8;
}

```

## disassembly

```asm
0x1800081f0  mov     [rsp+arg_10], r8
0x1800081f5  mov     [rsp+arg_0], rcx
0x1800081fa  push    rbx
0x1800081fb  push    rsi
0x1800081fc  push    rdi
0x1800081fd  push    r12
0x1800081ff  push    r13
0x180008201  push    r14
0x180008203  push    r15
0x180008205  sub     rsp, 80h
0x18000820c  mov     r13, r9
0x18000820f  mov     rbx, r8
0x180008212  mov     r12, rdx
0x180008215  mov     rsi, rcx
0x180008218  xor     edi, edi
0x18000821a  test    r9, r9
0x18000821d  jnz     short loc_180008228
0x18000821f  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x180008224  mov     r13, [rax+10h]
0x180008228  xorps   xmm0, xmm0
0x18000822b  movups  [rsp+0B8h+var_50], xmm0
0x180008230  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x180008235  mov     r15, [rax+2098h]
0x18000823c  mov     [rsp+0B8h+var_70], r15
0x180008241  mov     r14, rdi
0x180008244  mov     [rsp+0B8h+var_80], rdi
0x180008249  mov     [rsp+0B8h+var_78], rdi
0x18000824e  mov     ecx, 10h; int
0x180008253  call    ?AfxEndDeferRegisterClass@@YAHJ@Z; AfxEndDeferRegisterClass(long)
0x180008258  mov     ecx, 3C000h; int
0x18000825d  call    ?AfxEndDeferRegisterClass@@YAHJ@Z; AfxEndDeferRegisterClass(long)
0x180008262  test    r15, r15
0x180008265  jz      short loc_1800082A0
0x180008267  mov     rax, [rsi]
0x18000826a  lea     rdx, [rsp+0B8h+var_50]
0x18000826f  mov     rcx, rsi
0x180008272  mov     rax, [rax+178h]
0x180008279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000827e  test    eax, eax
0x180008280  jz      loc_180008479
0x180008286  mov     rax, [r15]
0x180008289  mov     r8, r12
0x18000828c  lea     rdx, [rsp+0B8h+var_50]
0x180008291  mov     rcx, r15
0x180008294  mov     rax, [rax+20h]
0x180008298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000829d  mov     r12, rax
0x1800082a0  test    r12, r12
0x1800082a3  jnz     short loc_1800082AC
0x1800082a5  xor     eax, eax
0x1800082a7  jmp     loc_180008479
0x1800082ac  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x1800082b3  mov     [rsp+0B8h+String1], rax
0x1800082b8  mov     [rsp+0B8h+arg_18], di
0x1800082c0  lea     r8, [rsp+0B8h+arg_18]; unsigned __int16 *
0x1800082c8  lea     rdx, [rsp+0B8h+String1]; struct CString *
0x1800082cd  mov     rcx, r12; struct DLGTEMPLATE *
0x1800082d0  call    ?GetFont@CDialogTemplate@@SAHPEBUDLGTEMPLATE@@AEAVCString@@AEAG@Z; CDialogTemplate::GetFont(DLGTEMPLATE const *,CString &,ushort &)
0x1800082d5  test    eax, eax
0x1800082d7  jz      short loc_18000833C
0x1800082d9  mov     ecx, 2Ah ; '*'; nIndex
0x1800082de  call    cs:__imp_GetSystemMetrics
0x1800082e4  test    eax, eax
0x1800082e6  jz      loc_180008390
0x1800082ec  lea     rdx, aMsShellDlg; "MS Shell Dlg"
0x1800082f3  mov     rbx, [rsp+0B8h+String1]
0x1800082f8  mov     rcx, rbx; String1
0x1800082fb  call    wcscmp_0
0x180008300  test    eax, eax
0x180008302  jz      short loc_18000832A
0x180008304  lea     rdx, aMsSansSerif; "MS Sans Serif"
0x18000830b  mov     rcx, rbx; String1
0x18000830e  call    wcscmp_0
0x180008313  test    eax, eax
0x180008315  jz      short loc_18000832A
0x180008317  lea     rdx, aHelv; "Helv"
0x18000831e  mov     rcx, rbx; String1
0x180008321  call    wcscmp_0
0x180008326  test    eax, eax
0x180008328  jnz     short loc_180008388
0x18000832a  movzx   ebx, [rsp+0B8h+arg_18]
0x180008332  cmp     bx, 8
0x180008336  jnz     short loc_180008344
0x180008338  mov     ebx, edi
0x18000833a  jmp     short loc_180008344
0x18000833c  movzx   ebx, [rsp+0B8h+arg_18]
0x180008344  mov     rdx, r12; struct DLGTEMPLATE *
0x180008347  lea     rcx, [rsp+0B8h+hMem]; this
0x18000834c  call    ??0CDialogTemplate@@QEAA@PEBUDLGTEMPLATE@@@Z; CDialogTemplate::CDialogTemplate(DLGTEMPLATE const *)
0x180008351  movzx   edx, bx; unsigned __int16
0x180008354  lea     rcx, [rsp+0B8h+hMem]; this
0x180008359  call    ?SetSystemFont@CDialogTemplate@@QEAAHG@Z; CDialogTemplate::SetSystemFont(ushort)
0x18000835e  mov     r14, [rsp+0B8h+hMem]
0x180008363  mov     [rsp+0B8h+hMem], rdi
0x180008368  mov     [rsp+0B8h+var_80], r14
0x18000836d  lea     rcx, [rsp+0B8h+hMem]; this
0x180008372  call    ??1CDialogTemplate@@QEAA@XZ; CDialogTemplate::~CDialogTemplate(void)
0x180008377  test    r14, r14
0x18000837a  jz      short loc_180008388
0x18000837c  mov     rcx, r14; hMem
0x18000837f  call    cs:__imp_GlobalLock
0x180008385  mov     r12, rax
0x180008388  mov     rbx, [rsp+0B8h+arg_10]
0x180008390  mov     dword ptr [rsi+60h], 0FFFFFFFFh
0x180008397  or      dword ptr [rsi+50h], 10h
0x18000839b  mov     rcx, rsi; struct CWnd *
0x18000839e  call    ?AfxHookWindowCreate@@YAXPEAVCWnd@@@Z; AfxHookWindowCreate(CWnd *)
0x1800083a3  test    rbx, rbx
0x1800083a6  mov     r8, rdi
0x1800083a9  jz      short loc_1800083AF
0x1800083ab  mov     r8, [rbx+40h]; hWndParent
0x1800083af  mov     [rsp+0B8h+dwInitParam], rdi; dwInitParam
0x1800083b4  lea     r9, ?AfxDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1800083bb  mov     rdx, r12; lpTemplate
0x1800083be  mov     rcx, r13; hInstance
0x1800083c1  call    cs:__imp_CreateDialogIndirectParamW
0x1800083c7  mov     rbx, rax
0x1800083ca  mov     [rsp+0B8h+var_78], rax
0x1800083cf  lea     rcx, [rsp+0B8h+String1]; this
0x1800083d4  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800083d9  nop
0x1800083da  jmp     short loc_1800083F5
0x1800083dc  mov     rsi, [rsp+0B8h+arg_0]
0x1800083e4  xor     edi, edi
0x1800083e6  mov     r14, [rsp+0B8h+var_80]
0x1800083eb  mov     rbx, [rsp+0B8h+var_78]
0x1800083f0  mov     r15, [rsp+0B8h+var_70]
0x1800083f5  test    r15, r15
0x1800083f8  jz      short loc_180008427
0x1800083fa  mov     rax, [r15]
0x1800083fd  lea     rdx, [rsp+0B8h+var_50]
0x180008402  mov     rcx, r15
0x180008405  mov     rax, [rax+28h]
0x180008409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000840e  test    rbx, rbx
0x180008411  jz      short loc_180008427
0x180008413  mov     rax, [rsi]
0x180008416  xor     edx, edx
0x180008418  mov     rcx, rsi
0x18000841b  mov     rax, [rax+178h]
0x180008422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008427  call    ?AfxUnhookWindowCreate@@YAHXZ; AfxUnhookWindowCreate(void)
0x18000842c  test    eax, eax
0x18000842e  jnz     short loc_180008442
0x180008430  mov     rax, [rsi]
0x180008433  mov     rcx, rsi
0x180008436  mov     rax, [rax+158h]
0x18000843d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008442  test    rbx, rbx
0x180008445  jz      short loc_180008459
0x180008447  test    byte ptr [rsi+50h], 10h
0x18000844b  jnz     short loc_180008459
0x18000844d  mov     rcx, rbx; hWnd
0x180008450  call    cs:__imp_DestroyWindow
0x180008456  mov     rbx, rdi
0x180008459  test    r14, r14
0x18000845c  jz      short loc_180008470
0x18000845e  mov     rcx, r14; hMem
0x180008461  call    cs:__imp_GlobalUnlock
0x180008467  mov     rcx, r14; hMem
0x18000846a  call    cs:__imp_GlobalFree
0x180008470  test    rbx, rbx
0x180008473  setnz   dil
0x180008477  mov     eax, edi
0x180008479  add     rsp, 80h
0x180008480  pop     r15
0x180008482  pop     r14
0x180008484  pop     r13
0x180008486  pop     r12
0x180008488  pop     rdi
0x180008489  pop     rsi
0x18000848a  pop     rbx
0x18000848b  retn
```
