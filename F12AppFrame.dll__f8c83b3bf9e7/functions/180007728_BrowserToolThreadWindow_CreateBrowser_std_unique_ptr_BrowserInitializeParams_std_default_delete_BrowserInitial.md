# BrowserToolThreadWindow::CreateBrowser(std::unique_ptr<BrowserInitializeParams,std::default_delete<BrowserInitializeParams>> &)

- ea: `0x180007728`
- end: `0x180007e86`
- name: `?CreateBrowser@BrowserToolThreadWindow@@AEAAJAEAV?$unique_ptr@UBrowserInitializeParams@@U?$default_delete@UBrowserInitializeParams@@@std@@@std@@@Z`
- size: `1886`
- prototype: `__int64 __fastcall(__int64, __int64 **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008520`

## callees

- `0x180002dd4`
- `0x180003858`
- `0x180007728`
- `0x18000bddc`
- `0x18000d66c`
- `0x18002c8cc`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007b23`
- `OLEAUT32!__imp_SysAllocString` at `0x180007b3e`
- `OLEAUT32!__imp_SysAllocString` at `0x180007b59`
- `OLEAUT32!__imp_SysAllocString` at `0x180007b74`
- `OLEAUT32!__imp_SysAllocString` at `0x180007b23`
- `OLEAUT32!__imp_SysAllocString` at `0x180007b3e`
- `OLEAUT32!__imp_SysAllocString` at `0x180007b59`
- `OLEAUT32!__imp_SysAllocString` at `0x180007b74`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ab9`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ac3`
- `OLEAUT32!__imp_SysFreeString` at `0x180007acd`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ad7`
- `OLEAUT32!__imp_SysFreeString` at `0x180007bcc`
- `OLEAUT32!__imp_SysFreeString` at `0x180007bd6`
- `OLEAUT32!__imp_SysFreeString` at `0x180007be0`
- `OLEAUT32!__imp_SysFreeString` at `0x180007bea`
- `OLEAUT32!__imp_SysFreeString` at `0x180007c62`
- `OLEAUT32!__imp_SysFreeString` at `0x180007c6c`
- `OLEAUT32!__imp_SysFreeString` at `0x180007c76`
- `OLEAUT32!__imp_SysFreeString` at `0x180007c80`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ce2`
- `OLEAUT32!__imp_SysFreeString` at `0x180007cec`
- `OLEAUT32!__imp_SysFreeString` at `0x180007cf6`
- `OLEAUT32!__imp_SysFreeString` at `0x180007d00`
- `OLEAUT32!__imp_SysFreeString` at `0x180007dde`
- `OLEAUT32!__imp_SysFreeString` at `0x180007de8`
- `OLEAUT32!__imp_SysFreeString` at `0x180007df2`
- `OLEAUT32!__imp_SysFreeString` at `0x180007dfc`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ab9`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ac3`
- `OLEAUT32!__imp_SysFreeString` at `0x180007acd`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ad7`
- `OLEAUT32!__imp_SysFreeString` at `0x180007bcc`
- `OLEAUT32!__imp_SysFreeString` at `0x180007bd6`
- `OLEAUT32!__imp_SysFreeString` at `0x180007be0`
- `OLEAUT32!__imp_SysFreeString` at `0x180007bea`
- `OLEAUT32!__imp_SysFreeString` at `0x180007c62`
- `OLEAUT32!__imp_SysFreeString` at `0x180007c6c`
- `OLEAUT32!__imp_SysFreeString` at `0x180007c76`
- `OLEAUT32!__imp_SysFreeString` at `0x180007c80`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ce2`
- `OLEAUT32!__imp_SysFreeString` at `0x180007cec`
- `OLEAUT32!__imp_SysFreeString` at `0x180007cf6`
- `OLEAUT32!__imp_SysFreeString` at `0x180007d00`
- `OLEAUT32!__imp_SysFreeString` at `0x180007dde`
- `OLEAUT32!__imp_SysFreeString` at `0x180007de8`
- `OLEAUT32!__imp_SysFreeString` at `0x180007df2`
- `OLEAUT32!__imp_SysFreeString` at `0x180007dfc`

## pseudocode

```c
__int64 __fastcall BrowserToolThreadWindow::CreateBrowser(__int64 a1, __int64 **a2)
{
  __int64 v5; // rbx
  int v6; // edx
  HWND v7; // rcx
  int PopupWindow; // esi
  __int64 v9; // r14
  __int64 v10; // r12
  void (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v12; // rax
  _QWORD *v13; // r13
  int HtmlDocument; // edi
  const OLECHAR *v15; // rcx
  OLECHAR *v16; // rbx
  const OLECHAR *v17; // rcx
  OLECHAR *v18; // rdi
  const OLECHAR *v19; // rcx
  OLECHAR *v20; // rsi
  const OLECHAR *v21; // rcx
  OLECHAR *v22; // r14
  int v23; // ecx
  int v24; // edx
  int v25; // r8d
  int v26; // r9d
  int v27; // r10d
  int v28; // r11d
  __int64 v29; // r13
  int v30; // r12d
  __int64 v31; // rcx
  _QWORD *v32; // rdx
  __int64 v33; // [rsp+C0h] [rbp-80h]
  __int64 v34; // [rsp+C8h] [rbp-78h] BYREF
  __int64 v35; // [rsp+D0h] [rbp-70h] BYREF
  OLECHAR *v36; // [rsp+D8h] [rbp-68h]
  OLECHAR *v37; // [rsp+E0h] [rbp-60h]
  OLECHAR *v38; // [rsp+E8h] [rbp-58h]
  OLECHAR *v39; // [rsp+F0h] [rbp-50h]
  __int64 (__fastcall *v40)(_QWORD, _QWORD, OLECHAR *, OLECHAR *, OLECHAR *, OLECHAR *, _DWORD, _QWORD, _QWORD, __int64, __int64, _DWORD, __int64, __int64, int, int, int, int, int, int, _DWORD, _DWORD, _DWORD); // [rsp+F8h] [rbp-48h]
  __int64 v41; // [rsp+100h] [rbp-40h]
  __int64 v44; // [rsp+170h] [rbp+30h] BYREF
  __int64 v45; // [rsp+178h] [rbp+38h] BYREF

  if ( !*a2 )
    return 2147942487LL;
  v5 = **a2;
  v33 = v5;
  v41 = v5;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  v6 = *((_DWORD *)*a2 + 2);
  *(_DWORD *)(a1 + 120) = v6;
  v7 = (HWND)(*a2)[9];
  *(_QWORD *)(a1 + 128) = v7;
  if ( v6 == 8 )
  {
    PopupWindow = PopupWindow::CreatePopupWindow(v7);
    if ( PopupWindow )
    {
      if ( PopupWindow >= 0 )
        PopupWindow = -2147467259;
      if ( !v5 )
        return (unsigned int)PopupWindow;
      goto LABEL_10;
    }
    v9 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL);
  }
  else
  {
    v9 = (*a2)[7];
  }
  v10 = a1 + 152;
  PopupWindow = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v5 + 40LL))(
                  v5,
                  *(unsigned int *)(a1 + 120),
                  a1 + 152);
  if ( PopupWindow )
  {
    if ( PopupWindow >= 0 )
      PopupWindow = -2147467259;
LABEL_10:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    return (unsigned int)PopupWindow;
  }
  v11 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))v10;
  v12 = 0;
  v44 = 0;
  if ( v11 )
  {
    (**v11)(v11, &GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9, &v44);
    v12 = v44;
  }
  if ( !v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    return 2147500034LL;
  }
  v13 = (_QWORD *)(a1 + 96);
  HtmlDocument = BrowserToolWindow::CreateBrowserToolWindow(
                   *(unsigned int *)(a1 + 120),
                   v9,
                   (*a2)[9],
                   *((unsigned int *)*a2 + 29),
                   &v44,
                   *(_DWORD *)(a1 + 120) == 8,
                   a1 + 96);
  if ( HtmlDocument )
  {
    if ( HtmlDocument >= 0 )
      HtmlDocument = -2147467259;
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
LABEL_27:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    return (unsigned int)HtmlDocument;
  }
  v45 = 0;
  HtmlDocument = BrowserToolWindow::GetHtmlDocument(*v13, &v45);
  if ( HtmlDocument )
  {
    if ( HtmlDocument >= 0 )
      HtmlDocument = -2147467259;
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    goto LABEL_27;
  }
  v15 = (const OLECHAR *)(*a2)[2];
  if ( v15 )
  {
    v16 = SysAllocString(v15);
    v36 = v16;
    if ( !v16 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    v16 = 0;
    v36 = 0;
  }
  v17 = (const OLECHAR *)(*a2)[3];
  if ( v17 )
  {
    v18 = SysAllocString(v17);
    v37 = v18;
    if ( !v18 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    v18 = 0;
    v37 = 0;
  }
  v19 = (const OLECHAR *)(*a2)[4];
  if ( v19 )
  {
    v20 = SysAllocString(v19);
    v38 = v20;
    if ( !v20 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    v20 = 0;
    v38 = 0;
  }
  v21 = (const OLECHAR *)(*a2)[5];
  if ( v21 )
  {
    v22 = SysAllocString(v21);
    v39 = v22;
    if ( !v22 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    v22 = 0;
    v39 = 0;
  }
  v23 = *((unsigned __int8 *)*a2 + 101);
  v24 = *((unsigned __int8 *)*a2 + 100);
  v25 = *((unsigned __int8 *)*a2 + 99);
  v26 = *((unsigned __int8 *)*a2 + 98);
  v27 = *((unsigned __int8 *)*a2 + 97);
  v28 = *((unsigned __int8 *)*a2 + 96);
  v29 = *v13;
  v40 = *(__int64 (__fastcall **)(_QWORD, _QWORD, OLECHAR *, OLECHAR *, OLECHAR *, OLECHAR *, _DWORD, _QWORD, _QWORD, __int64, __int64, _DWORD, __int64, __int64, int, int, int, int, int, int, _DWORD, _DWORD, _DWORD))(**(_QWORD **)v10 + 24LL);
  v30 = v40(
          *(_QWORD *)(a1 + 152),
          *(unsigned int *)(a1 + 120),
          v16,
          v18,
          v20,
          v22,
          *((unsigned __int8 *)*a2 + 48),
          *(_QWORD *)(v29 + 8),
          *(_QWORD *)(a1 + 8),
          (*a2)[8],
          (*a2)[9],
          *((_DWORD *)*a2 + 20),
          (*a2)[11],
          v45,
          v28,
          v27,
          v26,
          v25,
          v24,
          v23,
          *((_DWORD *)*a2 + 26),
          *((_DWORD *)*a2 + 27),
          *((_DWORD *)*a2 + 28));
  if ( v30 )
  {
    if ( v30 >= 0 )
      v30 = -2147467259;
    SysFreeString(v22);
    SysFreeString(v20);
    SysFreeString(v18);
    SysFreeString(v16);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
LABEL_51:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    return (unsigned int)v30;
  }
  if ( !*(_DWORD *)(a1 + 120) )
  {
    v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 152) + 40LL))(
            *(_QWORD *)(a1 + 152),
            0,
            a1 + 144);
    if ( v30 )
    {
      if ( v30 >= 0 )
        v30 = -2147467259;
      SysFreeString(v22);
      SysFreeString(v20);
      SysFreeString(v18);
      SysFreeString(v16);
      if ( v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      goto LABEL_51;
    }
  }
  v34 = 0;
  v30 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 152) + 32LL))(*(_QWORD *)(a1 + 152), &v34);
  if ( v30 != -2147483622 )
  {
    if ( v30 )
    {
      if ( v30 >= 0 )
        v30 = -2147467259;
      SysFreeString(v22);
      SysFreeString(v20);
      SysFreeString(v18);
      SysFreeString(v16);
      if ( v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    else
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v35,
        v34);
      v31 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 136LL) + 112LL);
      if ( v31 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v31 + 88LL))(
          v31,
          v35,
          0,
          0,
          0,
          0);
      if ( (*a2)[11] )
        v30 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 152) + 72LL))(*(_QWORD *)(a1 + 152));
      v32 = (_QWORD *)(v35 - 24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v35 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v32 + 8LL))(*v32);
      SysFreeString(v22);
      SysFreeString(v20);
      SysFreeString(v18);
      SysFreeString(v16);
      if ( v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    return (unsigned int)v30;
  }
  SysFreeString(v22);
  SysFreeString(v20);
  SysFreeString(v18);
  SysFreeString(v16);
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  return 2147483674LL;
}

```

## disassembly

```asm
0x180007728  mov     [rsp-8+arg_8], rdx
0x18000772d  mov     [rsp-8+arg_0], rcx
0x180007732  push    rbp
0x180007733  push    rbx
0x180007734  push    rsi
0x180007735  push    rdi
0x180007736  push    r12
0x180007738  push    r13
0x18000773a  push    r14
0x18000773c  push    r15
0x18000773e  lea     rbp, [rsp+28h]
0x180007743  sub     rsp, 118h
0x18000774a  mov     r15, rdx
0x18000774d  mov     rdi, rcx
0x180007750  mov     rbx, [rdx]
0x180007753  test    rbx, rbx
0x180007756  jnz     short loc_180007762
0x180007758  mov     eax, 80070057h
0x18000775d  jmp     loc_180007E46
0x180007762  mov     rbx, [rbx]
0x180007765  mov     [rbp+10h+var_90], rbx
0x180007769  mov     [rbp+10h+var_50], rbx
0x18000776d  test    rbx, rbx
0x180007770  jz      short loc_180007782
0x180007772  mov     rax, [rbx]
0x180007775  mov     rcx, rbx
0x180007778  mov     rax, [rax+8]
0x18000777c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007781  nop
0x180007782  mov     rax, [r15]
0x180007785  mov     edx, [rax+8]
0x180007788  mov     [rdi+78h], edx
0x18000778b  mov     rax, [r15]
0x18000778e  mov     rcx, [rax+48h]; HWND
0x180007792  mov     [rdi+80h], rcx
0x180007799  cmp     edx, 8
0x18000779c  jnz     short loc_1800077DD
0x18000779e  lea     rdx, [rdi+68h]
0x1800077a2  call    ?CreatePopupWindow@PopupWindow@@SAJPEAUHWND__@@AEAV?$shared_ptr@VPopupWindow@@@std@@@Z; PopupWindow::CreatePopupWindow(HWND__ *,std::shared_ptr<PopupWindow> &)
0x1800077a7  mov     esi, eax
0x1800077a9  test    eax, eax
0x1800077ab  jz      short loc_1800077D3
0x1800077ad  mov     eax, 80004005h
0x1800077b2  test    esi, esi
0x1800077b4  cmovns  esi, eax
0x1800077b7  test    rbx, rbx
0x1800077ba  jz      short loc_1800077CC
0x1800077bc  mov     rdx, [rbx]
0x1800077bf  mov     rcx, rbx
0x1800077c2  mov     rax, [rdx+10h]
0x1800077c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077cb  nop
0x1800077cc  mov     eax, esi
0x1800077ce  jmp     loc_180007E46
0x1800077d3  mov     rax, [rdi+68h]
0x1800077d7  mov     r14, [rax+8]
0x1800077db  jmp     short loc_1800077E4
0x1800077dd  mov     rax, [r15]
0x1800077e0  mov     r14, [rax+38h]
0x1800077e4  lea     r12, [rdi+98h]
0x1800077eb  mov     rax, [rbx]
0x1800077ee  mov     r8, r12
0x1800077f1  mov     edx, [rdi+78h]
0x1800077f4  mov     rcx, rbx
0x1800077f7  mov     rax, [rax+28h]
0x1800077fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007800  mov     esi, eax
0x180007802  test    eax, eax
0x180007804  jz      short loc_180007822
0x180007806  mov     eax, 80004005h
0x18000780b  test    esi, esi
0x18000780d  cmovns  esi, eax
0x180007810  mov     rcx, [rbx]
0x180007813  mov     rax, [rcx+10h]
0x180007817  mov     rcx, rbx
0x18000781a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000781f  nop
0x180007820  jmp     short loc_1800077CC
0x180007822  mov     rcx, [r12]
0x180007826  xor     eax, eax
0x180007828  mov     [rbp+10h+arg_10], rax
0x18000782c  test    rcx, rcx
0x18000782f  jz      short loc_18000784B
0x180007831  mov     rax, [rcx]
0x180007834  lea     r8, [rbp+10h+arg_10]
0x180007838  lea     rdx, _GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9
0x18000783f  mov     rax, [rax]
0x180007842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007847  mov     rax, [rbp+10h+arg_10]
0x18000784b  test    rax, rax
0x18000784e  jnz     short loc_18000786A
0x180007850  mov     rax, [rbx]
0x180007853  mov     rcx, rbx
0x180007856  mov     rax, [rax+10h]
0x18000785a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000785f  nop
0x180007860  mov     eax, 80004002h
0x180007865  jmp     loc_180007E46
0x18000786a  mov     ecx, [rdi+78h]
0x18000786d  mov     r8, [r15]
0x180007870  lea     r13, [rdi+60h]
0x180007874  cmp     ecx, 8
0x180007877  setz    al
0x18000787a  mov     [rsp+150h+var_120], r13
0x18000787f  mov     byte ptr [rsp+150h+var_128], al
0x180007883  lea     rax, [rbp+10h+arg_10]
0x180007887  mov     [rsp+150h+var_130], rax
0x18000788c  mov     r9d, [r8+74h]
0x180007890  mov     r8, [r8+48h]
0x180007894  mov     rdx, r14
0x180007897  call    ?CreateBrowserToolWindow@BrowserToolWindow@@SAJW4PluginId@@PEAUHWND__@@1HAEAV?$CComPtr@UIDispatchEx@@@ATL@@_NAEAV?$CComObjPtr@UBrowserToolWindow@@@@@Z; BrowserToolWindow::CreateBrowserToolWindow(PluginId,HWND__ *,HWND__ *,int,ATL::CComPtr<IDispatchEx> &,bool,CComObjPtr<BrowserToolWindow> &)
0x18000789c  mov     edi, eax
0x18000789e  test    eax, eax
0x1800078a0  jz      short loc_1800078D9
0x1800078a2  mov     eax, 80004005h
0x1800078a7  test    edi, edi
0x1800078a9  cmovns  edi, eax
0x1800078ac  mov     rcx, [rbp+10h+arg_10]
0x1800078b0  test    rcx, rcx
0x1800078b3  jz      short loc_1800078C2
0x1800078b5  mov     rax, [rcx]
0x1800078b8  mov     rax, [rax+10h]
0x1800078bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078c1  nop
0x1800078c2  mov     rcx, [rbx]
0x1800078c5  mov     rax, [rcx+10h]
0x1800078c9  mov     rcx, rbx
0x1800078cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078d1  nop
0x1800078d2  mov     eax, edi
0x1800078d4  jmp     loc_180007E46
0x1800078d9  mov     [rbp+10h+arg_18], 0
0x1800078e1  lea     rdx, [rbp+10h+arg_18]
0x1800078e5  mov     rcx, [r13+0]
0x1800078e9  call    ?GetHtmlDocument@BrowserToolWindow@@QEBAJAEAV?$CComPtr@UIHTMLDocument2@@@ATL@@@Z; BrowserToolWindow::GetHtmlDocument(ATL::CComPtr<IHTMLDocument2> &)
0x1800078ee  mov     edi, eax
0x1800078f0  test    eax, eax
0x1800078f2  jz      short loc_18000793C
0x1800078f4  mov     eax, 80004005h
0x1800078f9  test    edi, edi
0x1800078fb  cmovns  edi, eax
0x1800078fe  mov     rcx, [rbp+10h+arg_18]
0x180007902  test    rcx, rcx
0x180007905  jz      short loc_180007914
0x180007907  mov     rax, [rcx]
0x18000790a  mov     rax, [rax+10h]
0x18000790e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007913  nop
0x180007914  mov     rcx, [rbp+10h+arg_10]
0x180007918  test    rcx, rcx
0x18000791b  jz      short loc_18000792A
0x18000791d  mov     rax, [rcx]
0x180007920  mov     rax, [rax+10h]
0x180007924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007929  nop
0x18000792a  mov     rcx, [rbx]
0x18000792d  mov     rax, [rcx+10h]
0x180007931  mov     rcx, rbx
0x180007934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007939  nop
0x18000793a  jmp     short loc_1800078D2
0x18000793c  mov     rax, [r15]
0x18000793f  mov     rcx, [rax+10h]; psz
0x180007943  test    rcx, rcx
0x180007946  jnz     loc_180007B23
0x18000794c  xor     ebx, ebx
0x18000794e  mov     [rbp+10h+var_78], rbx
0x180007952  mov     rax, [r15]
0x180007955  mov     rcx, [rax+18h]; psz
0x180007959  test    rcx, rcx
0x18000795c  jnz     loc_180007B3E
0x180007962  xor     edi, edi
0x180007964  mov     [rbp+10h+var_70], rdi
0x180007968  mov     rax, [r15]
0x18000796b  mov     rcx, [rax+20h]; psz
0x18000796f  test    rcx, rcx
0x180007972  jnz     loc_180007B59
0x180007978  xor     esi, esi
0x18000797a  mov     [rbp+10h+var_68], rsi
0x18000797e  mov     rax, [r15]
0x180007981  mov     rcx, [rax+28h]; psz
0x180007985  test    rcx, rcx
0x180007988  jnz     loc_180007B74
0x18000798e  xor     r14d, r14d
0x180007991  mov     [rbp+10h+var_60], r14
0x180007995  mov     rax, [r12]
0x180007999  mov     r12, [r15]
0x18000799c  mov     r15, [rbp+10h+arg_18]
0x1800079a0  mov     rax, [rax]
0x1800079a3  movzx   ecx, byte ptr [r12+65h]
0x1800079a9  movzx   edx, byte ptr [r12+64h]
0x1800079af  movzx   r8d, byte ptr [r12+63h]
0x1800079b5  movzx   r9d, byte ptr [r12+62h]
0x1800079bb  movzx   r10d, byte ptr [r12+61h]
0x1800079c1  movzx   r11d, byte ptr [r12+60h]
0x1800079c7  mov     r13, [r13+0]
0x1800079cb  mov     rax, [rax+18h]
0x1800079cf  mov     [rbp+10h+var_58], rax
0x1800079d3  mov     r12, [rbp+10h+arg_8]
0x1800079d7  mov     rax, [r12]
0x1800079db  mov     eax, [rax+70h]
0x1800079de  mov     [rsp+150h+var_A0], eax
0x1800079e5  mov     rax, [r12]
0x1800079e9  mov     eax, [rax+6Ch]
0x1800079ec  mov     [rsp+150h+var_A8], eax
0x1800079f3  mov     rax, [r12]
0x1800079f7  mov     eax, [rax+68h]
0x1800079fa  mov     [rsp+150h+var_B0], eax
0x180007a01  mov     [rsp+150h+var_B8], ecx
0x180007a08  mov     [rsp+150h+var_C0], edx
0x180007a0f  mov     [rsp+150h+var_C8], r8d
0x180007a17  mov     [rsp+150h+var_D0], r9d
0x180007a1f  mov     [rsp+150h+var_D8], r10d
0x180007a24  mov     [rsp+150h+var_E0], r11d
0x180007a29  mov     [rsp+150h+var_E8], r15
0x180007a2e  mov     r15, r12
0x180007a31  mov     rcx, [r12]
0x180007a35  mov     rax, [rcx+58h]
0x180007a39  mov     [rsp+150h+var_F0], rax
0x180007a3e  mov     eax, [rcx+50h]
0x180007a41  mov     [rsp+150h+var_F8], eax
0x180007a45  mov     rdx, [rcx+48h]
0x180007a49  mov     [rsp+150h+var_100], rdx
0x180007a4e  mov     rdx, [rcx+40h]
0x180007a52  mov     [rsp+150h+var_108], rdx
0x180007a57  mov     rdx, [rbp+10h+arg_0]
0x180007a5b  mov     rdx, [rdx+8]
0x180007a5f  mov     [rsp+150h+var_110], rdx
0x180007a64  mov     rdx, [r13+8]
0x180007a68  mov     [rsp+150h+var_118], rdx
0x180007a6d  movzx   r12d, byte ptr [rcx+30h]
0x180007a72  mov     dword ptr [rsp+150h+var_120], r12d
0x180007a77  mov     [rsp+150h+var_128], r14
0x180007a7c  mov     [rsp+150h+var_130], rsi
0x180007a81  mov     r9, rdi
0x180007a84  mov     r8, rbx
0x180007a87  mov     r13, [rbp+10h+arg_0]
0x180007a8b  mov     edx, [r13+78h]
0x180007a8f  mov     rcx, [r13+98h]
0x180007a96  mov     rax, [rbp+10h+var_58]
0x180007a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a9f  mov     r12d, eax
0x180007aa2  test    eax, eax
0x180007aa4  jz      loc_180007B8F
0x180007aaa  mov     eax, 80004005h
0x180007aaf  test    r12d, r12d
0x180007ab2  cmovns  r12d, eax
0x180007ab6  mov     rcx, r14; bstrString
0x180007ab9  call    cs:__imp_SysFreeString
0x180007abf  nop
0x180007ac0  mov     rcx, rsi; bstrString
0x180007ac3  call    cs:__imp_SysFreeString
0x180007ac9  nop
0x180007aca  mov     rcx, rdi; bstrString
0x180007acd  call    cs:__imp_SysFreeString
0x180007ad3  nop
0x180007ad4  mov     rcx, rbx; bstrString
0x180007ad7  call    cs:__imp_SysFreeString
0x180007add  nop
0x180007ade  mov     rcx, [rbp+10h+arg_18]
0x180007ae2  test    rcx, rcx
0x180007ae5  jz      short loc_180007AF4
0x180007ae7  mov     rax, [rcx]
0x180007aea  mov     rax, [rax+10h]
0x180007aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007af3  nop
0x180007af4  mov     rcx, [rbp+10h+arg_10]
0x180007af8  test    rcx, rcx
0x180007afb  jz      short loc_180007B0A
0x180007afd  mov     rax, [rcx]
0x180007b00  mov     rax, [rax+10h]
0x180007b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b09  nop
0x180007b0a  mov     rdx, [rbp+10h+var_90]
0x180007b0e  mov     rcx, [rdx]
0x180007b11  mov     rax, [rcx+10h]
0x180007b15  mov     rcx, rdx
0x180007b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b1d  nop
0x180007b1e  jmp     loc_180007E43
0x180007b23  call    cs:__imp_SysAllocString
0x180007b29  mov     rbx, rax
0x180007b2c  mov     [rbp+10h+var_78], rax
0x180007b30  test    rax, rax
0x180007b33  jz      loc_180007E5A
0x180007b39  jmp     loc_180007952
0x180007b3e  call    cs:__imp_SysAllocString
0x180007b44  mov     rdi, rax
0x180007b47  mov     [rbp+10h+var_70], rax
0x180007b4b  test    rax, rax
0x180007b4e  jz      loc_180007E65
0x180007b54  jmp     loc_180007968
0x180007b59  call    cs:__imp_SysAllocString
0x180007b5f  mov     rsi, rax
0x180007b62  mov     [rbp+10h+var_68], rax
0x180007b66  test    rax, rax
0x180007b69  jz      loc_180007E70
0x180007b6f  jmp     loc_18000797E
0x180007b74  call    cs:__imp_SysAllocString
0x180007b7a  mov     r14, rax
  ... truncated ...
```
