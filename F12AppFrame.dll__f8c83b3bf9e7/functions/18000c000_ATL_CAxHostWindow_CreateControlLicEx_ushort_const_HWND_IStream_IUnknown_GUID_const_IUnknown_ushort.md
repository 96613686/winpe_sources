# ATL::CAxHostWindow::CreateControlLicEx(ushort const *,HWND__ *,IStream *,IUnknown * *,_GUID const &,IUnknown *,ushort *)

- ea: `0x18000c000`
- end: `0x18000c57a`
- name: `?CreateControlLicEx@CAxHostWindow@ATL@@UEAAJPEBGPEAUHWND__@@PEAUIStream@@PEAPEAUIUnknown@@AEBU_GUID@@PEAU5@PEAG@Z`
- size: `1402`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *this, const unsigned __int16 *, HWND, struct IStream *, struct IUnknown **, const struct _GUID *, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path`

## callees

- `0x180001800`
- `0x180003858`
- `0x180005704`
- `0x18000a37c`
- `0x18000c000`
- `0x18000cb14`
- `0x18001086c`
- `0x180010bfc`
- `0x180011158`
- `0x180035010`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x18000c37c`
- `KERNEL32!GlobalUnlock` at `0x18000c37c`
- `KERNEL32!GlobalLock` at `0x18000c361`
- `KERNEL32!GlobalLock` at `0x18000c361`
- `KERNEL32!GlobalAlloc` at `0x18000c348`
- `KERNEL32!GlobalAlloc` at `0x18000c348`
- `KERNEL32!lstrcmpW` at `0x18000c0f4`
- `KERNEL32!lstrcmpW` at `0x18000c0f4`
- `ole32!CreateStreamOnHGlobal` at `0x18000c38e`
- `ole32!CreateStreamOnHGlobal` at `0x18000c38e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c459`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c459`
- `OLEAUT32!__imp_VariantInit` at `0x18000c43c`
- `OLEAUT32!__imp_VariantInit` at `0x18000c43c`
- `OLEAUT32!__imp_VariantClear` at `0x18000c44b`
- `OLEAUT32!__imp_VariantClear` at `0x18000c4c1`
- `OLEAUT32!__imp_VariantClear` at `0x18000c4cb`
- `OLEAUT32!__imp_VariantClear` at `0x18000c44b`
- `OLEAUT32!__imp_VariantClear` at `0x18000c4c1`
- `OLEAUT32!__imp_VariantClear` at `0x18000c4cb`
- `USER32!IsWindow` at `0x18000c098`
- `USER32!IsWindow` at `0x18000c098`
- `USER32!SetWindowLongW` at `0x18000c265`
- `USER32!SetWindowLongW` at `0x18000c265`
- `USER32!GetWindowLongW` at `0x18000c22d`
- `USER32!GetWindowLongW` at `0x18000c250`
- `USER32!GetWindowLongW` at `0x18000c22d`
- `USER32!GetWindowLongW` at `0x18000c250`
- `USER32!GetParent` at `0x18000c0cc`
- `USER32!GetParent` at `0x18000c0cc`
- `USER32!RedrawWindow` at `0x18000c087`
- `USER32!RedrawWindow` at `0x18000c527`
- `USER32!RedrawWindow` at `0x18000c087`
- `USER32!RedrawWindow` at `0x18000c527`
- `USER32!SetWindowPos` at `0x18000c289`
- `USER32!SetWindowPos` at `0x18000c289`
- `USER32!GetSysColor` at `0x18000c108`
- `USER32!GetSysColor` at `0x18000c108`
- `USER32!GetClassNameW` at `0x18000c0df`
- `USER32!GetClassNameW` at `0x18000c0df`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ATL::CAxHostWindow::CreateControlLicEx(
        ATL::CAxHostWindow *this,
        const unsigned __int16 *a2,
        HWND a3,
        struct IStream *a4,
        struct IUnknown **a5,
        const struct _GUID *a6,
        struct IUnknown *a7,
        unsigned __int16 *a8)
{
  int NormalizedObject; // ebx
  ATL::CAxHostWindow *v13; // r12
  HWND v14; // rcx
  HWND Parent; // rax
  int v16; // eax
  int v17; // ecx
  struct IUnknown *v18; // rcx
  HWND v19; // rcx
  char v20; // [rsp+41h] [rbp-50h]
  LPSTREAM ppstm; // [rsp+48h] [rbp-49h] BYREF
  BSTR pbstr; // [rsp+50h] [rbp-41h] BYREF
  WCHAR ClassName; // [rsp+70h] [rbp-21h] BYREF

  ppstm = a4;
  pbstr = a8;
  if ( !a5 )
    return 2147500035LL;
  *a5 = 0;
  NormalizedObject = 1;
  v13 = (ATL::CAxHostWindow *)((char *)this - 72);
  ATL::CAxHostWindow::ReleaseAll((ATL::CAxHostWindow *)((char *)this - 72));
  v14 = (HWND)*((_QWORD *)this - 8);
  if ( v14 && v14 != a3 )
  {
    RedrawWindow(v14, 0, 0, 0x507u);
    ATL::CAxHostWindow::ReleaseWindow(v13);
  }
  if ( IsWindow(a3) )
  {
    v20 = 0;
    if ( *((HWND *)this - 8) != a3 )
    {
      ATL::CAxHostWindow::SubclassWindow((size_t)v13, a3);
      v20 = 1;
    }
    if ( !*((_DWORD *)this + 67) )
    {
      Parent = GetParent(*((HWND *)this - 8));
      if ( !GetClassNameW(Parent, &ClassName, 8) || (v16 = lstrcmpW(&ClassName, L"#32770"), v17 = 15, v16) )
        v17 = 5;
      *((_DWORD *)this + 67) = GetSysColor(v17);
    }
    NormalizedObject = ATL::CreateNormalizedObject(a2, pbstr);
    if ( NormalizedObject >= 0 )
      NormalizedObject = ATL::CAxHostWindow::ActivateAx(v13, *a5, 0, ppstm);
    *(struct _GUID *)((char *)this + 184) = *a6;
    if ( NormalizedObject < 0 )
      goto LABEL_27;
    v18 = *a5;
    if ( *a5 && a7 )
    {
      pbstr = 0;
      ppstm = 0;
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, BSTR *))v18->lpVtbl->QueryInterface)(
             v18,
             &GUID_b196b284_bab4_101a_b69c_00aa00341d07,
             &pbstr) >= 0
        && (*(int (__fastcall **)(BSTR, char *, LPSTREAM *))(*(_QWORD *)pbstr + 32LL))(
             pbstr,
             (char *)this + 184,
             &ppstm) >= 0 )
      {
        ((void (__fastcall *)(LPSTREAM, struct IUnknown *, char *))ppstm->lpVtbl->Seek)(ppstm, a7, (char *)this + 204);
      }
      if ( ppstm )
        ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
      if ( pbstr )
        (*(void (__fastcall **)(BSTR))(*(_QWORD *)pbstr + 16LL))(pbstr);
    }
    if ( !*((_QWORD *)this + 15) )
    {
LABEL_27:
      ATL::CAxHostWindow::ReleaseAll(v13);
      v19 = (HWND)*((_QWORD *)this - 8);
      if ( v19 )
      {
        RedrawWindow(v19, 0, 0, 0x507u);
        if ( NormalizedObject < 0 )
        {
          if ( v20 )
            ATL::CAxHostWindow::ReleaseWindow(v13);
        }
      }
    }
  }
  return (unsigned int)NormalizedObject;
}

```

## disassembly

```asm
0x18000c000  push    rbp
0x18000c002  push    rbx
0x18000c003  push    rsi
0x18000c004  push    rdi
0x18000c005  push    r12
0x18000c007  push    r13
0x18000c009  push    r14
0x18000c00b  push    r15
0x18000c00d  lea     rbp, [rsp-7]
0x18000c012  sub     rsp, 98h
0x18000c019  mov     rax, cs:__security_cookie
0x18000c020  xor     rax, rsp
0x18000c023  mov     [rbp+3Fh+var_48], rax
0x18000c027  mov     [rbp+3Fh+ppstm], r9
0x18000c02b  mov     r15, r8
0x18000c02e  mov     r14, rdx
0x18000c031  mov     rdi, rcx
0x18000c034  mov     rsi, [rbp+3Fh+arg_20]
0x18000c038  mov     r13, [rbp+3Fh+arg_30]
0x18000c03c  mov     rax, [rbp+3Fh+arg_38]
0x18000c043  mov     [rbp+3Fh+var_80], rax
0x18000c047  test    rsi, rsi
0x18000c04a  jnz     short loc_18000C056
0x18000c04c  mov     eax, 80004003h
0x18000c051  jmp     loc_18000C541
0x18000c056  mov     qword ptr [rsi], 0
0x18000c05d  mov     ebx, 1
0x18000c062  lea     r12, [rcx-48h]
0x18000c066  mov     rcx, r12; this
0x18000c069  call    ?ReleaseAll@CAxHostWindow@ATL@@QEAAXXZ; ATL::CAxHostWindow::ReleaseAll(void)
0x18000c06e  mov     rcx, [rdi-40h]; hWnd
0x18000c072  test    rcx, rcx
0x18000c075  jz      short loc_18000C095
0x18000c077  cmp     rcx, r15
0x18000c07a  jz      short loc_18000C095
0x18000c07c  mov     r9d, 507h; flags
0x18000c082  xor     r8d, r8d; hrgnUpdate
0x18000c085  xor     edx, edx; lprcUpdate
0x18000c087  call    cs:__imp_RedrawWindow
0x18000c08d  mov     rcx, r12; this
0x18000c090  call    ?ReleaseWindow@CAxHostWindow@ATL@@QEAAXXZ; ATL::CAxHostWindow::ReleaseWindow(void)
0x18000c095  mov     rcx, r15; hWnd
0x18000c098  call    cs:__imp_IsWindow
0x18000c09e  test    eax, eax
0x18000c0a0  jz      loc_18000C53F
0x18000c0a6  xor     ebx, ebx
0x18000c0a8  mov     [rbp+3Fh+var_8F], bl
0x18000c0ab  cmp     [rdi-40h], r15
0x18000c0af  jz      short loc_18000C0C0
0x18000c0b1  mov     rdx, r15; hWnd
0x18000c0b4  mov     rcx, r12; FirstParameter
0x18000c0b7  call    ?SubclassWindow@CAxHostWindow@ATL@@QEAAXPEAUHWND__@@@Z; ATL::CAxHostWindow::SubclassWindow(HWND__ *)
0x18000c0bc  mov     [rbp+3Fh+var_8F], 1
0x18000c0c0  cmp     [rdi+10Ch], ebx
0x18000c0c6  jnz     short loc_18000C114
0x18000c0c8  mov     rcx, [rdi-40h]; hWnd
0x18000c0cc  call    cs:__imp_GetParent
0x18000c0d2  mov     r8d, 8; nMaxCount
0x18000c0d8  lea     rdx, [rbp+3Fh+ClassName]; lpClassName
0x18000c0dc  mov     rcx, rax; hWnd
0x18000c0df  call    cs:__imp_GetClassNameW
0x18000c0e5  test    eax, eax
0x18000c0e7  jz      short loc_18000C103
0x18000c0e9  lea     rdx, a32770; "#32770"
0x18000c0f0  lea     rcx, [rbp+3Fh+ClassName]; lpString1
0x18000c0f4  call    cs:__imp_lstrcmpW
0x18000c0fa  test    eax, eax
0x18000c0fc  mov     ecx, 0Fh
0x18000c101  jz      short loc_18000C108
0x18000c103  mov     ecx, 5; nIndex
0x18000c108  call    cs:__imp_GetSysColor
0x18000c10e  mov     [rdi+10Ch], eax
0x18000c114  mov     [rbp+3Fh+var_90], bl
0x18000c117  mov     rax, [rbp+3Fh+var_80]
0x18000c11b  mov     [rsp+0D0h+pbstr], rax; pbstr
0x18000c120  lea     r9, [rbp+3Fh+var_90]
0x18000c124  mov     r8, rsi
0x18000c127  mov     rcx, r14; lpszProgID
0x18000c12a  call    ATL__CreateNormalizedObject
0x18000c12f  mov     ebx, eax
0x18000c131  test    eax, eax
0x18000c133  js      short loc_18000C149
0x18000c135  mov     r9, [rbp+3Fh+ppstm]; struct IStream *
0x18000c139  xor     r8d, r8d; bool
0x18000c13c  mov     rdx, [rsi]; struct IUnknown *
0x18000c13f  mov     rcx, r12; this
0x18000c142  call    ?ActivateAx@CAxHostWindow@ATL@@QEAAJPEAUIUnknown@@_NPEAUIStream@@@Z; ATL::CAxHostWindow::ActivateAx(IUnknown *,bool,IStream *)
0x18000c147  mov     ebx, eax
0x18000c149  lea     r15, [rdi+0B8h]
0x18000c150  mov     rax, [rbp+3Fh+arg_28]
0x18000c154  movups  xmm0, xmmword ptr [rax]
0x18000c157  movdqu  xmmword ptr [r15], xmm0
0x18000c15c  test    ebx, ebx
0x18000c15e  js      loc_18000C508
0x18000c164  mov     rcx, [rsi]
0x18000c167  test    rcx, rcx
0x18000c16a  jz      loc_18000C20A
0x18000c170  test    r13, r13
0x18000c173  jz      loc_18000C20A
0x18000c179  mov     [rbp+3Fh+var_80], 0
0x18000c181  mov     [rbp+3Fh+ppstm], 0
0x18000c189  mov     rax, [rcx]
0x18000c18c  lea     r8, [rbp+3Fh+var_80]
0x18000c190  lea     rdx, _GUID_b196b284_bab4_101a_b69c_00aa00341d07
0x18000c197  mov     rax, [rax]
0x18000c19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c19f  test    eax, eax
0x18000c1a1  js      short loc_18000C1D9
0x18000c1a3  mov     rcx, [rbp+3Fh+var_80]
0x18000c1a7  mov     rax, [rcx]
0x18000c1aa  lea     r8, [rbp+3Fh+ppstm]
0x18000c1ae  mov     rdx, r15
0x18000c1b1  mov     rax, [rax+20h]
0x18000c1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1ba  test    eax, eax
0x18000c1bc  js      short loc_18000C1D9
0x18000c1be  mov     rcx, [rbp+3Fh+ppstm]
0x18000c1c2  mov     rax, [rcx]
0x18000c1c5  lea     r8, [rdi+0CCh]
0x18000c1cc  mov     rdx, r13
0x18000c1cf  mov     rax, [rax+28h]
0x18000c1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1d8  nop
0x18000c1d9  mov     rcx, [rbp+3Fh+ppstm]
0x18000c1dd  xor     r13d, r13d
0x18000c1e0  test    rcx, rcx
0x18000c1e3  jz      short loc_18000C1F2
0x18000c1e5  mov     rax, [rcx]
0x18000c1e8  mov     rax, [rax+10h]
0x18000c1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1f1  nop
0x18000c1f2  mov     rcx, [rbp+3Fh+var_80]
0x18000c1f6  test    rcx, rcx
0x18000c1f9  jz      short loc_18000C208
0x18000c1fb  mov     rax, [rcx]
0x18000c1fe  mov     rax, [rax+10h]
0x18000c202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c207  nop
0x18000c208  jmp     short loc_18000C20D
0x18000c20a  xor     r13d, r13d
0x18000c20d  cmp     [rbp+3Fh+var_90], r13b
0x18000c211  jz      loc_18000C500
0x18000c217  cmp     [rsi], r13
0x18000c21a  jz      loc_18000C500
0x18000c220  mov     r15d, 0FFFFFFF0h
0x18000c226  mov     edx, r15d; nIndex
0x18000c229  mov     rcx, [rdi-40h]; hWnd
0x18000c22d  call    cs:__imp_GetWindowLongW
0x18000c233  test    eax, 300000h
0x18000c238  jnz     short loc_18000C249
0x18000c23a  mov     r15d, 8
0x18000c240  or      [rdi+128h], r15d
0x18000c247  jmp     short loc_18000C295
0x18000c249  mov     edx, r15d; nIndex
0x18000c24c  mov     rcx, [rdi-40h]; hWnd
0x18000c250  call    cs:__imp_GetWindowLongW
0x18000c256  and     eax, 0FFCFFFFFh
0x18000c25b  mov     r8d, eax; dwNewLong
0x18000c25e  mov     edx, r15d; nIndex
0x18000c261  mov     rcx, [rdi-40h]; hWnd
0x18000c265  call    cs:__imp_SetWindowLongW
0x18000c26b  mov     [rsp+0D0h+uFlags], 37h ; '7'; uFlags
0x18000c273  mov     [rsp+0D0h+cy], r13d; cy
0x18000c278  mov     dword ptr [rsp+0D0h+pbstr], r13d; unsigned __int64
0x18000c27d  xor     r9d, r9d; Y
0x18000c280  xor     r8d, r8d; X
0x18000c283  xor     edx, edx; hWndInsertAfter
0x18000c285  mov     rcx, [rdi-40h]; hWnd
0x18000c289  call    cs:__imp_SetWindowPos
0x18000c28f  mov     r15d, 8
0x18000c295  mov     rsi, [rsi]
0x18000c298  test    rsi, rsi
0x18000c29b  jz      short loc_18000C2AD
0x18000c29d  mov     rax, [rsi]
0x18000c2a0  mov     rcx, rsi
0x18000c2a3  mov     rax, [rax+8]
0x18000c2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2ac  nop
0x18000c2ad  movzx   eax, word ptr [r14]
0x18000c2b1  sub     ax, 4Dh ; 'M'
0x18000c2b5  mov     ecx, 0FFDFh
0x18000c2ba  test    cx, ax
0x18000c2bd  jnz     loc_18000C40E
0x18000c2c3  movzx   eax, word ptr [r14+2]
0x18000c2c8  sub     ax, 53h ; 'S'
0x18000c2cc  test    cx, ax
0x18000c2cf  jnz     loc_18000C40E
0x18000c2d5  movzx   eax, word ptr [r14+4]
0x18000c2da  sub     ax, 48h ; 'H'
0x18000c2de  test    cx, ax
0x18000c2e1  jnz     loc_18000C40E
0x18000c2e7  movzx   eax, word ptr [r14+6]
0x18000c2ec  sub     ax, 54h ; 'T'
0x18000c2f0  test    cx, ax
0x18000c2f3  jnz     loc_18000C40E
0x18000c2f9  movzx   eax, word ptr [r14+8]
0x18000c2fe  sub     ax, 4Dh ; 'M'
0x18000c302  test    cx, ax
0x18000c305  jnz     loc_18000C40E
0x18000c30b  movzx   eax, word ptr [r14+0Ah]
0x18000c310  sub     ax, 4Ch ; 'L'
0x18000c314  test    cx, ax
0x18000c317  jnz     loc_18000C40E
0x18000c31d  cmp     word ptr [r14+0Ch], 3Ah ; ':'
0x18000c323  jnz     loc_18000C40E
0x18000c329  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000c32d  inc     rdx
0x18000c330  cmp     [r14+rdx*2], r13w
0x18000c335  jnz     short loc_18000C32D
0x18000c337  lea     eax, ds:0FFFFFFFFFFFFFFF2h[rdx*2]
0x18000c33e  mov     r15d, eax
0x18000c341  mov     edx, eax; dwBytes
0x18000c343  mov     ecx, 42h ; 'B'; uFlags
0x18000c348  call    cs:__imp_GlobalAlloc
0x18000c34e  mov     rbx, rax
0x18000c351  test    rax, rax
0x18000c354  jz      loc_18000C404
0x18000c35a  mov     [rbp+3Fh+ppstm], r13
0x18000c35e  mov     rcx, rax; hMem
0x18000c361  call    cs:__imp_GlobalLock
0x18000c367  lea     r8, [r14+0Eh]; unsigned __int64
0x18000c36b  mov     r9d, r15d; void *
0x18000c36e  mov     edx, r15d; void *
0x18000c371  mov     rcx, rax; this
0x18000c374  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18000c379  mov     rcx, rbx; hMem
0x18000c37c  call    cs:__imp_GlobalUnlock
0x18000c382  lea     r8, [rbp+3Fh+ppstm]; ppstm
0x18000c386  mov     edx, 1; fDeleteOnRelease
0x18000c38b  mov     rcx, rbx; hGlobal
0x18000c38e  call    cs:__imp_CreateStreamOnHGlobal
0x18000c394  mov     ebx, eax
0x18000c396  test    eax, eax
0x18000c398  js      short loc_18000C3E9
0x18000c39a  mov     [rbp+3Fh+var_80], r13
0x18000c39e  mov     rax, [rsi]
0x18000c3a1  lea     r8, [rbp+3Fh+var_80]
0x18000c3a5  lea     rdx, _GUID_7fd52380_4e07_101b_ae2d_08002b2ec713
0x18000c3ac  mov     rcx, rsi
0x18000c3af  mov     rax, [rax]
0x18000c3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3b7  mov     ebx, eax
0x18000c3b9  test    eax, eax
0x18000c3bb  js      short loc_18000C3D3
0x18000c3bd  mov     rcx, [rbp+3Fh+var_80]
0x18000c3c1  mov     rax, [rcx]
0x18000c3c4  mov     rdx, [rbp+3Fh+ppstm]
0x18000c3c8  mov     rax, [rax+28h]
0x18000c3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3d1  mov     ebx, eax
0x18000c3d3  mov     rcx, [rbp+3Fh+var_80]
0x18000c3d7  test    rcx, rcx
0x18000c3da  jz      short loc_18000C3E9
0x18000c3dc  mov     rax, [rcx]
0x18000c3df  mov     rax, [rax+10h]
0x18000c3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3e8  nop
0x18000c3e9  mov     rcx, [rbp+3Fh+ppstm]
0x18000c3ed  test    rcx, rcx
0x18000c3f0  jz      short loc_18000C3FF
0x18000c3f2  mov     rax, [rcx]
0x18000c3f5  mov     rax, [rax+10h]
0x18000c3f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3fe  nop
0x18000c3ff  jmp     loc_18000C4E7
0x18000c404  mov     ebx, 8007000Eh
0x18000c409  jmp     loc_18000C4E7
0x18000c40e  mov     [rbp+3Fh+ppstm], r13
0x18000c412  mov     rax, [rsi]
0x18000c415  lea     r8, [rbp+3Fh+ppstm]
0x18000c419  lea     rdx, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x18000c420  mov     rcx, rsi
0x18000c423  mov     rax, [rax]
0x18000c426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c42b  mov     rcx, [rbp+3Fh+ppstm]
0x18000c42f  test    rcx, rcx
0x18000c432  jz      loc_18000C4D5
0x18000c438  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x18000c43c  call    cs:__imp_VariantInit
0x18000c442  mov     [rbp+3Fh+ClassName], r13w
0x18000c447  lea     rcx, [rbp+3Fh+ClassName]; pvarg
0x18000c44b  call    cs:__imp_VariantClear
0x18000c451  mov     [rbp+3Fh+ClassName], r15w
0x18000c456  mov     rcx, r14; psz
0x18000c459  call    cs:__imp_SysAllocString
0x18000c45f  mov     dword ptr [rbp+3Fh+var_58], eax
0x18000c462  mov     rcx, rax
0x18000c465  sar     rcx, 20h
0x18000c469  mov     dword ptr [rbp+3Fh+var_58+4], ecx
0x18000c46c  test    rax, rax
0x18000c46f  jz      loc_18000C561
0x18000c475  mov     rcx, [rbp+3Fh+ppstm]
0x18000c479  mov     rax, [rcx]
0x18000c47c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000c480  mov     rax, [rax+148h]
0x18000c487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c48c  mov     rcx, [rbp+3Fh+ppstm]
0x18000c490  mov     rax, [rcx]
0x18000c493  lea     rdx, [rbp+3Fh+pvarg]
0x18000c497  mov     qword ptr [rsp+0D0h+cy], rdx
  ... truncated ...
```
