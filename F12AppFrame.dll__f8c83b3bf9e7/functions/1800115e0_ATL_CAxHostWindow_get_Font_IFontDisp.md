# ATL::CAxHostWindow::get_Font(IFontDisp * *)

- ea: `0x1800115e0`
- end: `0x1800117b8`
- name: `?get_Font@CAxHostWindow@ATL@@UEAAJPEAPEAUIFontDisp@@@Z`
- size: `472`
- prototype: `int __fastcall(ATL::CAxHostWindow *this, LPVOID *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001800`
- `0x180002678`
- `0x180005e44`
- `0x1800115e0`
- `0x180035010`

## import_xrefs

- `GDI32!GetStockObject` at `0x18001163e`
- `GDI32!GetStockObject` at `0x18001164f`
- `GDI32!GetStockObject` at `0x18001163e`
- `GDI32!GetStockObject` at `0x18001164f`
- `GDI32!GetDeviceCaps` at `0x1800116f9`
- `GDI32!GetDeviceCaps` at `0x18001172e`
- `GDI32!GetDeviceCaps` at `0x1800116f9`
- `GDI32!GetDeviceCaps` at `0x18001172e`
- `GDI32!GetObjectW` at `0x180011685`
- `GDI32!GetObjectW` at `0x180011685`
- `OLEAUT32!__imp_OleCreateFontIndirect` at `0x18001176c`
- `OLEAUT32!__imp_OleCreateFontIndirect` at `0x18001176c`
- `USER32!GetDesktopWindow` at `0x18001170b`
- `USER32!GetDesktopWindow` at `0x180011737`
- `USER32!GetDesktopWindow` at `0x18001170b`
- `USER32!GetDesktopWindow` at `0x180011737`
- `USER32!ReleaseDC` at `0x180011743`
- `USER32!ReleaseDC` at `0x180011743`
- `USER32!GetDC` at `0x1800116e0`
- `USER32!GetDC` at `0x180011714`
- `USER32!GetDC` at `0x1800116e0`
- `USER32!GetDC` at `0x180011714`

## pseudocode

```c
int __fastcall ATL::CAxHostWindow::get_Font(ATL::CAxHostWindow *this, LPVOID *a2)
{
  LPVOID *v5; // rbx
  HGDIOBJ StockObject; // rdi
  int v7; // r12d
  HWND v8; // rcx
  HDC v9; // rax
  HDC v10; // rdi
  int DeviceCaps; // r15d
  HWND v12; // rcx
  HWND DesktopWindow; // rax
  HDC DC; // rax
  tagFONTDESC FontDesc; // [rsp+20h] [rbp-69h] BYREF
  _DWORD pv[4]; // [rsp+50h] [rbp-39h] BYREF
  SHORT v17; // [rsp+60h] [rbp-29h]
  unsigned __int8 v18; // [rsp+64h] [rbp-25h]
  unsigned __int8 v19; // [rsp+65h] [rbp-24h]
  unsigned __int8 v20; // [rsp+66h] [rbp-23h]
  unsigned __int8 v21; // [rsp+67h] [rbp-22h]
  char v22; // [rsp+6Ch] [rbp-1Dh] BYREF

  if ( !a2 )
    return -2147467261;
  *a2 = 0;
  v5 = (LPVOID *)((char *)this + 200);
  if ( *((_QWORD *)this + 25) )
    goto LABEL_15;
  StockObject = GetStockObject(17);
  if ( !StockObject )
  {
    StockObject = GetStockObject(13);
    if ( !StockObject )
      return ATL::AtlHresultFromLastError();
  }
  memset_0(pv, 0, 0x5Cu);
  GetObjectW(StockObject, 92, pv);
  *(_QWORD *)&FontDesc.cbSizeofstruct = 40;
  FontDesc.cySize.int64 = 0;
  FontDesc.lpstrName = (LPOLESTR)&v22;
  FontDesc.sWeight = v17;
  FontDesc.sCharset = v21;
  FontDesc.fItalic = v18;
  FontDesc.fUnderline = v19;
  FontDesc.fStrikethrough = v20;
  v7 = -pv[0];
  if ( pv[0] > 0 )
    v7 = pv[0];
  v8 = (HWND)*((_QWORD *)this - 18);
  if ( !v8 )
  {
    DesktopWindow = GetDesktopWindow();
    DC = GetDC(DesktopWindow);
    v10 = DC;
    if ( DC )
    {
      DeviceCaps = GetDeviceCaps(DC, 90);
      v12 = GetDesktopWindow();
      goto LABEL_14;
    }
    return ATL::AtlHresultFromLastError();
  }
  v9 = GetDC(v8);
  v10 = v9;
  if ( !v9 )
    return ATL::AtlHresultFromLastError();
  DeviceCaps = GetDeviceCaps(v9, 90);
  v12 = (HWND)*((_QWORD *)this - 18);
LABEL_14:
  ReleaseDC(v12, v10);
  FontDesc.cySize.int64 = (unsigned int)(720000 * v7 / DeviceCaps);
  OleCreateFontIndirect(&FontDesc, &GUID_bef6e003_a874_101a_8bba_00aa00300cab, v5);
LABEL_15:
  *a2 = *v5;
  if ( *v5 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*v5 + 8LL))(*v5);
  return 0;
}

```

## disassembly

```asm
0x1800115e0  mov     [rsp-8+arg_10], rbx
0x1800115e5  mov     [rsp-8+arg_18], rsi
0x1800115ea  push    rbp
0x1800115eb  push    rdi
0x1800115ec  push    r12
0x1800115ee  push    r14
0x1800115f0  push    r15
0x1800115f2  lea     rbp, [rsp-37h]
0x1800115f7  sub     rsp, 0C0h
0x1800115fe  mov     rax, cs:__security_cookie
0x180011605  xor     rax, rsp
0x180011608  mov     [rbp+57h+var_30], rax
0x18001160c  mov     rsi, rdx
0x18001160f  mov     r14, rcx
0x180011612  test    rdx, rdx
0x180011615  jnz     short loc_180011621
0x180011617  mov     eax, 80004003h
0x18001161c  jmp     loc_180011790
0x180011621  mov     qword ptr [rdx], 0
0x180011628  lea     rbx, [rcx+0C8h]
0x18001162f  cmp     qword ptr [rbx], 0
0x180011633  jnz     loc_180011773
0x180011639  mov     ecx, 11h; i
0x18001163e  call    cs:__imp_GetStockObject
0x180011644  mov     rdi, rax
0x180011647  test    rax, rax
0x18001164a  jnz     short loc_180011667
0x18001164c  lea     ecx, [rax+0Dh]; i
0x18001164f  call    cs:__imp_GetStockObject
0x180011655  mov     rdi, rax
0x180011658  test    rax, rax
0x18001165b  jnz     short loc_180011667
0x18001165d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180011662  jmp     loc_180011790
0x180011667  mov     r15d, 5Ch ; '\'
0x18001166d  mov     r8d, r15d; Size
0x180011670  xor     edx, edx; Val
0x180011672  lea     rcx, [rbp+57h+pv]; void *
0x180011676  call    memset_0
0x18001167b  lea     r8, [rbp+57h+pv]; pv
0x18001167f  mov     edx, r15d; c
0x180011682  mov     rcx, rdi; h
0x180011685  call    cs:__imp_GetObjectW
0x18001168b  mov     qword ptr [rbp+57h+FontDesc.cbSizeofstruct], 28h ; '('
0x180011693  mov     qword ptr [rbp+57h+FontDesc.cySize], 0
0x18001169b  lea     rax, [rbp+57h+var_74]
0x18001169f  mov     [rbp+57h+FontDesc.lpstrName], rax
0x1800116a3  movzx   eax, [rbp+57h+var_80]
0x1800116a7  mov     [rbp+57h+FontDesc.sWeight], ax
0x1800116ab  movzx   eax, [rbp+57h+var_79]
0x1800116af  mov     [rbp+57h+FontDesc.sCharset], ax
0x1800116b3  movzx   eax, [rbp+57h+var_7C]
0x1800116b7  mov     [rbp+57h+FontDesc.fItalic], eax
0x1800116ba  movzx   eax, [rbp+57h+var_7B]
0x1800116be  mov     [rbp+57h+FontDesc.fUnderline], eax
0x1800116c1  movzx   eax, [rbp+57h+var_7A]
0x1800116c5  mov     [rbp+57h+FontDesc.fStrikethrough], eax
0x1800116c8  mov     r12d, [rbp+57h+pv]
0x1800116cc  neg     r12d
0x1800116cf  cmovs   r12d, [rbp+57h+pv]
0x1800116d4  mov     rcx, [r14-90h]; hWnd
0x1800116db  test    rcx, rcx
0x1800116de  jz      short loc_18001170B
0x1800116e0  call    cs:__imp_GetDC
0x1800116e6  mov     rdi, rax
0x1800116e9  test    rax, rax
0x1800116ec  jz      loc_18001165D
0x1800116f2  lea     edx, [r15-2]; index
0x1800116f6  mov     rcx, rax; hdc
0x1800116f9  call    cs:__imp_GetDeviceCaps
0x1800116ff  mov     r15d, eax
0x180011702  mov     rcx, [r14-90h]
0x180011709  jmp     short loc_180011740
0x18001170b  call    cs:__imp_GetDesktopWindow
0x180011711  mov     rcx, rax; hWnd
0x180011714  call    cs:__imp_GetDC
0x18001171a  mov     rdi, rax
0x18001171d  test    rax, rax
0x180011720  jz      loc_18001165D
0x180011726  mov     edx, 5Ah ; 'Z'; index
0x18001172b  mov     rcx, rax; hdc
0x18001172e  call    cs:__imp_GetDeviceCaps
0x180011734  mov     r15d, eax
0x180011737  call    cs:__imp_GetDesktopWindow
0x18001173d  mov     rcx, rax; hWnd
0x180011740  mov     rdx, rdi; hDC
0x180011743  call    cs:__imp_ReleaseDC
0x180011749  imul    eax, r12d, 0AFC80h
0x180011750  cdq
0x180011751  idiv    r15d
0x180011754  mov     dword ptr [rbp+57h+FontDesc.cySize], eax
0x180011757  mov     dword ptr [rbp+57h+FontDesc.cySize+4], 0
0x18001175e  mov     r8, rbx; lplpvObj
0x180011761  lea     rdx, _GUID_bef6e003_a874_101a_8bba_00aa00300cab; riid
0x180011768  lea     rcx, [rbp+57h+FontDesc]; lpFontDesc
0x18001176c  call    cs:__imp_OleCreateFontIndirect
0x180011772  nop
0x180011773  mov     rax, [rbx]
0x180011776  mov     [rsi], rax
0x180011779  mov     rcx, [rbx]
0x18001177c  test    rcx, rcx
0x18001177f  jz      short loc_18001178E
0x180011781  mov     rax, [rcx]
0x180011784  mov     rax, [rax+8]
0x180011788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001178d  nop
0x18001178e  xor     eax, eax
0x180011790  mov     rcx, [rbp+57h+var_30]
0x180011794  xor     rcx, rsp; StackCookie
0x180011797  call    __security_check_cookie
0x18001179c  lea     r11, [rsp+0E0h+var_20]
0x1800117a4  mov     rbx, [r11+40h]
0x1800117a8  mov     rsi, [r11+48h]
0x1800117ac  mov     rsp, r11
0x1800117af  pop     r15
0x1800117b1  pop     r14
0x1800117b3  pop     r12
0x1800117b5  pop     rdi
0x1800117b6  pop     rbp
0x1800117b7  retn
```
