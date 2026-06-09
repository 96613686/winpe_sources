# CDfsShellExtProp::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x180008eac`
- end: `0x180009099`
- name: `?OnInitDialog@CDfsShellExtProp@@QEAA_JI_K_JAEAH@Z`
- size: `493`
- prototype: `__int64 __fastcall(CDfsShellExtProp *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009170`

## callees

- `0x180004328`
- `0x180007090`
- `0x180008eac`
- `0x180009700`
- `0x180009dd8`
- `0x180009eb4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008fd5`
- `KERNEL32!GetLastError` at `0x180008fd5`
- `USER32!SendMessageW` at `0x180008f08`
- `USER32!SendMessageW` at `0x180008f1a`
- `USER32!SendMessageW` at `0x180008f08`
- `USER32!SendMessageW` at `0x180008f1a`
- `USER32!SetDlgItemTextW` at `0x180008f9f`
- `USER32!SetDlgItemTextW` at `0x180008f9f`
- `USER32!SendDlgItemMessageW` at `0x18000904d`
- `USER32!SendDlgItemMessageW` at `0x18000904d`
- `USER32!GetDlgItem` at `0x180008ed5`
- `USER32!GetDlgItem` at `0x180008ee7`
- `USER32!GetDlgItem` at `0x180008ed5`
- `USER32!GetDlgItem` at `0x180008ee7`
- `USER32!LoadImageW` at `0x180008fc7`
- `USER32!LoadImageW` at `0x180008fc7`
- `GDI32!DeleteObject` at `0x180009056`
- `GDI32!DeleteObject` at `0x180009056`
- `GDI32!GetObjectW` at `0x180008ffb`
- `GDI32!GetObjectW` at `0x180008ffb`
- `OLEAUT32!__imp_SysAllocString` at `0x180008f27`
- `OLEAUT32!__imp_SysAllocString` at `0x180008f27`
- `OLEAUT32!__imp_SysFreeString` at `0x180008f74`
- `OLEAUT32!__imp_SysFreeString` at `0x180009069`
- `OLEAUT32!__imp_SysFreeString` at `0x180008f74`
- `OLEAUT32!__imp_SysFreeString` at `0x180009069`
- `OLEAUT32!__imp_SysStringLen` at `0x180008f47`
- `OLEAUT32!__imp_SysStringLen` at `0x180008f47`
- `OLEAUT32!__imp_VarBstrCat` at `0x180008f63`
- `OLEAUT32!__imp_VarBstrCat` at `0x180008f63`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDfsShellExtProp::OnInitDialog(HWND *this, __int64 a2, OLECHAR *a3, const WCHAR *a4)
{
  HWND DlgItem; // rbx
  HWND v6; // rdi
  WCHAR *v7; // rbx
  OLECHAR *v8; // rdi
  HRESULT v9; // eax
  HANDLE ImageW; // rax
  void *v11; // rbx
  unsigned int v12; // edi
  unsigned int v13; // r14d
  __int64 v14; // r8
  __int64 v15; // rax
  LPARAM v16; // rdi
  _OWORD pv[2]; // [rsp+30h] [rbp-20h] BYREF
  BSTR pbstrResult; // [rsp+90h] [rbp+40h] BYREF
  LPCWSTR lpString; // [rsp+98h] [rbp+48h] BYREF

  lpString = a4;
  pbstrResult = a3;
  DlgItem = GetDlgItem(this[1], 206);
  v6 = GetDlgItem(this[1], 204);
  SendMessageW(DlgItem, 0x160Cu, 0, 1);
  SendMessageW(v6, 0x160Cu, 0, 1);
  v7 = SysAllocString(&word_18000FB48);
  lpString = v7;
  if ( !v7 )
    ATL::AtlThrowImpl(-2147024882);
  v8 = (OLECHAR *)this[24];
  if ( SysStringLen(v8) )
  {
    pbstrResult = 0;
    v9 = VarBstrCat(v7, v8, &pbstrResult);
    if ( v9 < 0 )
      ATL::AtlThrowImpl(v9);
    SysFreeString(v7);
    lpString = pbstrResult;
  }
  ATL::CComBSTR::operator+=(&lpString, &word_18000FB48);
  SetDlgItemTextW(this[1], 202, lpString);
  ImageW = LoadImageW(hInstance, (LPCWSTR)0xC8, 0, 0, 0, 0x8020u);
  v11 = ImageW;
  if ( ImageW )
  {
    v12 = 16;
    v13 = 6;
    memset(pv, 0, sizeof(pv));
    if ( GetObjectW(ImageW, 32, pv) && SDWORD2(pv[0]) > 0 )
    {
      v12 = DWORD2(pv[0]);
      v13 = SDWORD1(pv[0]) / SDWORD2(pv[0]);
    }
    v15 = IsolationAwareImageList_Create(v12, v12, v14, v13);
    v16 = v15;
    if ( v15 )
    {
      IsolationAwareImageList_Add(v15, v11);
      SendDlgItemMessageW(this[1], 203, 0x1003u, 1u, v16);
    }
    DeleteObject(v11);
  }
  else
  {
    GetLastError();
  }
  CDfsShellExtProp::_SetAlternateList((CDfsShellExtProp *)this);
  SysFreeString((BSTR)lpString);
  return 1;
}

```

## disassembly

```asm
0x180008eac  mov     [rsp-28h+arg_0], rbx
0x180008eb1  mov     [rsp-28h+lpString], r9
0x180008eb6  mov     [rsp-28h+pbstrResult], r8
0x180008ebb  push    rbp
0x180008ebc  push    rsi
0x180008ebd  push    rdi
0x180008ebe  push    r14
0x180008ec0  push    r15
0x180008ec2  mov     rbp, rsp
0x180008ec5  sub     rsp, 50h
0x180008ec9  mov     rsi, rcx
0x180008ecc  mov     edx, 0CEh; nIDDlgItem
0x180008ed1  mov     rcx, [rcx+8]; hDlg
0x180008ed5  call    cs:__imp_GetDlgItem
0x180008edb  mov     rbx, rax
0x180008ede  mov     edx, 0CCh; nIDDlgItem
0x180008ee3  mov     rcx, [rsi+8]; hDlg
0x180008ee7  call    cs:__imp_GetDlgItem
0x180008eed  mov     rdi, rax
0x180008ef0  mov     r15d, 1
0x180008ef6  mov     r9d, r15d; lParam
0x180008ef9  xor     r8d, r8d; wParam
0x180008efc  mov     r14d, 160Ch
0x180008f02  mov     edx, r14d; Msg
0x180008f05  mov     rcx, rbx; hWnd
0x180008f08  call    cs:__imp_SendMessageW
0x180008f0e  mov     r9d, r15d; lParam
0x180008f11  xor     r8d, r8d; wParam
0x180008f14  mov     edx, r14d; Msg
0x180008f17  mov     rcx, rdi; hWnd
0x180008f1a  call    cs:__imp_SendMessageW
0x180008f20  lea     rcx, word_18000FB48; psz
0x180008f27  call    cs:__imp_SysAllocString
0x180008f2d  mov     rbx, rax
0x180008f30  mov     [rbp+lpString], rax
0x180008f34  test    rax, rax
0x180008f37  jz      loc_18000908E
0x180008f3d  mov     rdi, [rsi+0C0h]
0x180008f44  mov     rcx, rdi; pbstr
0x180008f47  call    cs:__imp_SysStringLen
0x180008f4d  test    eax, eax
0x180008f4f  jz      short loc_180008F82
0x180008f51  mov     [rbp+pbstrResult], 0
0x180008f59  lea     r8, [rbp+pbstrResult]; pbstrResult
0x180008f5d  mov     rdx, rdi; bstrRight
0x180008f60  mov     rcx, rbx; bstrLeft
0x180008f63  call    cs:__imp_VarBstrCat
0x180008f69  test    eax, eax
0x180008f6b  js      loc_180009086
0x180008f71  mov     rcx, rbx; bstrString
0x180008f74  call    cs:__imp_SysFreeString
0x180008f7a  mov     rax, [rbp+pbstrResult]
0x180008f7e  mov     [rbp+lpString], rax
0x180008f82  lea     rdx, word_18000FB48
0x180008f89  lea     rcx, [rbp+lpString]
0x180008f8d  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x180008f92  mov     r8, [rbp+lpString]; lpString
0x180008f96  mov     edx, 0CAh; nIDDlgItem
0x180008f9b  mov     rcx, [rsi+8]; hDlg
0x180008f9f  call    cs:__imp_SetDlgItemTextW
0x180008fa5  mov     [rsp+50h+fuLoad], 8020h; fuLoad
0x180008fad  mov     [rsp+50h+cy], 0; cy
0x180008fb5  xor     r9d, r9d; cx
0x180008fb8  xor     r8d, r8d; type
0x180008fbb  mov     edx, 0C8h; name
0x180008fc0  mov     rcx, cs:hInstance; hInst
0x180008fc7  call    cs:__imp_LoadImageW
0x180008fcd  mov     rbx, rax
0x180008fd0  test    rax, rax
0x180008fd3  jnz     short loc_180008FDD
0x180008fd5  call    cs:__imp_GetLastError
0x180008fdb  jmp     short loc_18000905C
0x180008fdd  mov     edi, 10h
0x180008fe2  lea     r14d, [rdi-0Ah]
0x180008fe6  xorps   xmm0, xmm0
0x180008fe9  movups  [rbp+pv], xmm0
0x180008fed  movups  [rbp+var_10], xmm0
0x180008ff1  lea     r8, [rbp+pv]; pv
0x180008ff5  lea     edx, [rdi+10h]; c
0x180008ff8  mov     rcx, rbx; h
0x180008ffb  call    cs:__imp_GetObjectW
0x180009001  test    eax, eax
0x180009003  jz      short loc_180009017
0x180009005  mov     eax, dword ptr [rbp+pv+8]
0x180009008  test    eax, eax
0x18000900a  jle     short loc_180009017
0x18000900c  mov     edi, eax
0x18000900e  mov     eax, dword ptr [rbp+pv+4]
0x180009011  cdq
0x180009012  idiv    edi
0x180009014  mov     r14d, eax
0x180009017  mov     r9d, r14d
0x18000901a  mov     edx, edi
0x18000901c  mov     ecx, edi
0x18000901e  call    IsolationAwareImageList_Create
0x180009023  mov     rdi, rax
0x180009026  test    rax, rax
0x180009029  jz      short loc_180009053
0x18000902b  mov     rdx, rbx
0x18000902e  mov     rcx, rax
0x180009031  call    IsolationAwareImageList_Add
0x180009036  mov     qword ptr [rsp+50h+cy], rdi; lParam
0x18000903b  mov     r9, r15; wParam
0x18000903e  mov     edx, 0CBh; nIDDlgItem
0x180009043  mov     r8d, 1003h; Msg
0x180009049  mov     rcx, [rsi+8]; hDlg
0x18000904d  call    cs:__imp_SendDlgItemMessageW
0x180009053  mov     rcx, rbx; ho
0x180009056  call    cs:__imp_DeleteObject
0x18000905c  mov     rcx, rsi; this
0x18000905f  call    ?_SetAlternateList@CDfsShellExtProp@@AEAAXXZ; CDfsShellExtProp::_SetAlternateList(void)
0x180009064  nop
0x180009065  mov     rcx, [rbp+lpString]; bstrString
0x180009069  call    cs:__imp_SysFreeString
0x18000906f  mov     rax, r15
0x180009072  mov     rbx, [rsp+50h+arg_0]
0x18000907a  add     rsp, 50h
0x18000907e  pop     r15
0x180009080  pop     r14
0x180009082  pop     rdi
0x180009083  pop     rsi
0x180009084  pop     rbp
0x180009085  retn
0x180009086  mov     ecx, eax; int
0x180009088  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000908e  mov     ecx, 8007000Eh; int
0x180009093  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
