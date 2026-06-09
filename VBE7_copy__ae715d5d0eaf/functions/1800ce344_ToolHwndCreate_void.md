# ToolHwndCreate(void)

- ea: `0x1800ce344`
- end: `0x1800ce5bb`
- name: `?ToolHwndCreate@@YAPEAUHWND__@@XZ`
- size: `631`
- prototype: `HWND(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002651c`

## callees

- `0x180001890`
- `0x180017944`
- `0x180090264`
- `0x1800ce344`
- `0x1800d0a20`
- `0x1800d0eb0`
- `0x180379380`
- `0x180379546`

## import_xrefs

- `USER32!RegisterClipboardFormatA` at `0x1800ce3a6`
- `USER32!RegisterClipboardFormatA` at `0x1800ce3b9`
- `USER32!RegisterClipboardFormatA` at `0x1800ce3cc`
- `USER32!RegisterClipboardFormatA` at `0x1800ce3a6`
- `USER32!RegisterClipboardFormatA` at `0x1800ce3b9`
- `USER32!RegisterClipboardFormatA` at `0x1800ce3cc`
- `USER32!GetSystemMetrics` at `0x1800ce4a6`
- `USER32!GetSystemMetrics` at `0x1800ce4a6`
- `USER32!GetDialogBaseUnits` at `0x1800ce490`
- `USER32!GetDialogBaseUnits` at `0x1800ce490`
- `USER32!LoadBitmapA` at `0x1800ce4bf`
- `USER32!LoadBitmapA` at `0x1800ce4bf`
- `USER32!LoadCursorA` at `0x1800ce45d`
- `USER32!LoadCursorA` at `0x1800ce45d`
- `USER32!DestroyWindow` at `0x1800ce58b`
- `USER32!DestroyWindow` at `0x1800ce58b`
- `GDI32!GetObjectA` at `0x1800ce4d5`
- `GDI32!GetObjectA` at `0x1800ce4d5`
- `GDI32!DeleteObject` at `0x1800ce4f4`
- `GDI32!DeleteObject` at `0x1800ce4f4`
- `ole32!CoCreateGuid` at `0x1800ce3ff`
- `ole32!CoCreateGuid` at `0x1800ce3ff`

## string_xrefs

- `0x1800ce39f`: `CLSID`

## pseudocode

```c
HWND ToolHwndCreate(void)
{
  UINT v0; // eax
  unsigned int v1; // ebx
  HBITMAP BitmapA; // rbx
  HWND Window; // rax
  HWND result; // rax
  _BYTE pv[4]; // [rsp+60h] [rbp-78h] BYREF
  __int64 v6; // [rsp+64h] [rbp-74h]
  int v7; // [rsp+80h] [rbp-58h] BYREF
  __int64 (__fastcall *v8)(HWND, unsigned int, unsigned __int64, __int64); // [rsp+88h] [rbp-50h]
  HINSTANCE v9; // [rsp+98h] [rbp-40h]
  HCURSOR CursorA; // [rsp+A8h] [rbp-30h]
  const char *v11; // [rsp+C0h] [rbp-18h]

  *(_QWORD *)&qword_1803F3894 = 0;
  dword_1803F3890 = 0;
  word_1803F389C = 1030;
  if ( !heapGrp && (int)ToolGroupInit() < 0 )
    return 0;
  if ( !(unsigned int)PalBuildCtlInfo() )
    return 0;
  cfCLSID = RegisterClipboardFormatA("CLSID");
  cfDesignerToolboxItem = RegisterClipboardFormatA("DesignerToolboxItem");
  v0 = RegisterClipboardFormatA("ClsdIdClassName");
  cfCLSIDClassName = v0;
  if ( !cfCLSID )
    return 0;
  if ( !cfDesignerToolboxItem )
    return 0;
  if ( !v0 )
    return 0;
  if ( CoCreateGuid(&guidMyDataObject) < 0 )
    return 0;
  dword_1803F393C = -1;
  dword_1803F38E0 = 0;
  memset_0(&v7, 0, 0x48u);
  v8 = FnwpPalette;
  v9 = Rby_hinstExe;
  v7 = 8;
  CursorA = LoadCursorA(0, (LPCSTR)0x7F00);
  v11 = "ToolsPalette";
  if ( !(unsigned __int16)IsolationAwareRegisterClassA(&v7) )
    return 0;
  v1 = (unsigned int)GetDialogBaseUnits() >> 16;
  _nTabHeight = v1 + 2 * GetSystemMetrics(46);
  BitmapA = LoadBitmapA(Rby_hmodThun, (LPCSTR)0x406);
  GetObjectA(BitmapA, 32, pv);
  qword_1803F38C8 = v6;
  DeleteObject(BitmapA);
  Window = (HWND)IsolationAwareCreateWindowExA(
                   16,
                   (int)"ToolsPalette",
                   0,
                   1140850688,
                   0,
                   0,
                   0,
                   0,
                   Main_hwndMainMenu,
                   0,
                   Rby_hinstExe,
                   0);
  hwnd = Window;
  Tool_hwnd = Window;
  if ( !Window )
    return 0;
  qword_1803F38B0 = CPane::Create(Window, 0, 6u, 0, 1, 0);
  g_ppaneTool = qword_1803F38B0;
  if ( !qword_1803F38B0 )
  {
    DestroyWindow(hwnd);
    return 0;
  }
  result = hwnd;
  dword_1803F38D8 = 1;
  return result;
}

```

## disassembly

```asm
0x1800ce344  mov     [rsp+arg_0], rbx
0x1800ce349  mov     [rsp+arg_8], rbp
0x1800ce34e  mov     [rsp+arg_10], rsi
0x1800ce353  push    rdi
0x1800ce354  mov     eax, 0D0h
0x1800ce359  call    _alloca_probe
0x1800ce35e  sub     rsp, rax
0x1800ce361  xor     edi, edi
0x1800ce363  mov     esi, 406h
0x1800ce368  cmp     cs:?heapGrp@@3PEAXEA, rdi; void * heapGrp
0x1800ce36f  mov     cs:qword_1803F3894, rdi
0x1800ce376  mov     cs:dword_1803F3890, edi
0x1800ce37c  mov     cs:word_1803F389C, si
0x1800ce383  jnz     short loc_1800CE392
0x1800ce385  call    ?ToolGroupInit@@YAJXZ; ToolGroupInit(void)
0x1800ce38a  test    eax, eax
0x1800ce38c  js      loc_1800CE591
0x1800ce392  call    ?PalBuildCtlInfo@@YAHXZ; PalBuildCtlInfo(void)
0x1800ce397  test    eax, eax
0x1800ce399  jz      loc_1800CE591
0x1800ce39f  lea     rcx, aClsid_1; "CLSID"
0x1800ce3a6  call    cs:__imp_RegisterClipboardFormatA
0x1800ce3ac  lea     rcx, aDesignertoolbo; "DesignerToolboxItem"
0x1800ce3b3  mov     cs:?cfCLSID@@3IA, eax; uint cfCLSID
0x1800ce3b9  call    cs:__imp_RegisterClipboardFormatA
0x1800ce3bf  lea     rcx, aClsdidclassnam; "ClsdIdClassName"
0x1800ce3c6  mov     cs:?cfDesignerToolboxItem@@3IA, eax; uint cfDesignerToolboxItem
0x1800ce3cc  call    cs:__imp_RegisterClipboardFormatA
0x1800ce3d2  cmp     cs:?cfCLSID@@3IA, edi; uint cfCLSID
0x1800ce3d8  mov     cs:?cfCLSIDClassName@@3IA, eax; uint cfCLSIDClassName
0x1800ce3de  jz      loc_1800CE591
0x1800ce3e4  cmp     cs:?cfDesignerToolboxItem@@3IA, edi; uint cfDesignerToolboxItem
0x1800ce3ea  jz      loc_1800CE591
0x1800ce3f0  test    eax, eax
0x1800ce3f2  jz      loc_1800CE591
0x1800ce3f8  lea     rcx, ?guidMyDataObject@@3U_GUID@@A; pguid
0x1800ce3ff  call    cs:__imp_CoCreateGuid
0x1800ce405  test    eax, eax
0x1800ce407  js      loc_1800CE591
0x1800ce40d  or      cs:dword_1803F393C, 0FFFFFFFFh
0x1800ce414  xor     edx, edx; Val
0x1800ce416  lea     rcx, [rsp+0D8h+var_58]; void *
0x1800ce41e  lea     r8d, [rdx+48h]; Size
0x1800ce422  mov     cs:dword_1803F38E0, edi
0x1800ce428  call    memset_0
0x1800ce42d  lea     rax, ?FnwpPalette@@YA_JPEAUHWND__@@I_K_J@Z; FnwpPalette(HWND__ *,uint,unsigned __int64,__int64)
0x1800ce434  mov     edx, 7F00h; lpCursorName
0x1800ce439  mov     [rsp+0D8h+var_50], rax
0x1800ce441  mov     rax, cs:?Rby_hinstExe@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * Rby_hinstExe
0x1800ce448  xor     ecx, ecx; hInstance
0x1800ce44a  mov     [rsp+0D8h+var_40], rax
0x1800ce452  mov     [rsp+0D8h+var_58], 8
0x1800ce45d  call    cs:__imp_LoadCursorA
0x1800ce463  lea     rbp, ?szToolsPalClass@@3QBDB; "ToolsPalette"
0x1800ce46a  lea     rcx, [rsp+0D8h+var_58]
0x1800ce472  mov     [rsp+0D8h+var_30], rax
0x1800ce47a  mov     [rsp+0D8h+var_18], rbp
0x1800ce482  call    IsolationAwareRegisterClassA
0x1800ce487  test    ax, ax
0x1800ce48a  jz      loc_1800CE591
0x1800ce490  call    cs:__imp_GetDialogBaseUnits
0x1800ce496  mov     ecx, 2Eh ; '.'; nIndex
0x1800ce49b  mov     r11d, eax
0x1800ce49e  shr     r11, 10h
0x1800ce4a2  movzx   ebx, r11w
0x1800ce4a6  call    cs:__imp_GetSystemMetrics
0x1800ce4ac  mov     rdx, rsi; lpBitmapName
0x1800ce4af  lea     ecx, [rbx+rax*2]
0x1800ce4b2  mov     cs:?_nTabHeight@@3HA, ecx; int _nTabHeight
0x1800ce4b8  mov     rcx, cs:?Rby_hmodThun@@3PEAUHINSTANCE__@@EA; hInstance
0x1800ce4bf  call    cs:__imp_LoadBitmapA
0x1800ce4c5  lea     r8, [rsp+0D8h+pv]; pv
0x1800ce4ca  mov     edx, 20h ; ' '; c
0x1800ce4cf  mov     rcx, rax; h
0x1800ce4d2  mov     rbx, rax
0x1800ce4d5  call    cs:__imp_GetObjectA
0x1800ce4db  mov     ecx, dword ptr [rsp+0D8h+var_74+4]
0x1800ce4df  mov     r11d, dword ptr [rsp+0D8h+var_74]
0x1800ce4e4  mov     dword ptr cs:qword_1803F38C8+4, ecx
0x1800ce4ea  mov     rcx, rbx; ho
0x1800ce4ed  mov     dword ptr cs:qword_1803F38C8, r11d
0x1800ce4f4  call    cs:__imp_DeleteObject
0x1800ce4fa  mov     rax, cs:?Rby_hinstExe@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * Rby_hinstExe
0x1800ce501  mov     [rsp+0D8h+var_80], rdi; LPVOID
0x1800ce506  mov     [rsp+0D8h+var_88], rax; HINSTANCE
0x1800ce50b  mov     rax, cs:?Main_hwndMainMenu@@3PEAUHWND__@@EA; HWND__ * Main_hwndMainMenu
0x1800ce512  mov     [rsp+0D8h+var_90], rdi; HMENU
0x1800ce517  mov     [rsp+0D8h+var_98], rax; HWND
0x1800ce51c  mov     [rsp+0D8h+var_A0], edi; int
0x1800ce520  xor     r8d, r8d; int
0x1800ce523  mov     [rsp+0D8h+var_A8], edi; int
0x1800ce527  lea     ecx, [r8+10h]; int
0x1800ce52b  mov     r9d, 44000000h; int
0x1800ce531  mov     rdx, rbp; int
0x1800ce534  mov     dword ptr [rsp+0D8h+var_B0], edi; int
0x1800ce538  mov     dword ptr [rsp+0D8h+var_B8], edi; int
0x1800ce53c  call    IsolationAwareCreateWindowExA
0x1800ce541  mov     cs:hwnd, rax
0x1800ce548  mov     cs:?Tool_hwnd@@3PEAUHWND__@@EA, rax; HWND__ * Tool_hwnd
0x1800ce54f  test    rax, rax
0x1800ce552  jz      short loc_1800CE591
0x1800ce554  mov     ebx, 1
0x1800ce559  xor     r9d, r9d; int
0x1800ce55c  mov     r8b, 6; unsigned __int8
0x1800ce55f  xor     edx, edx; HWND (*)(unsigned __int8)
0x1800ce561  mov     rcx, rax; HWND
0x1800ce564  mov     dword ptr [rsp+0D8h+var_B0], edi; char
0x1800ce568  mov     dword ptr [rsp+0D8h+var_B8], ebx; char
0x1800ce56c  call    ?Create@CPane@@SAPEAV1@PEAUHWND__@@P6APEAU2@E@ZEHHH@Z; CPane::Create(HWND__ *,HWND__ * (*)(uchar),uchar,int,int,int)
0x1800ce571  mov     cs:qword_1803F38B0, rax
0x1800ce578  mov     cs:?g_ppaneTool@@3PEAVCPane@@EA, rax; CPane * g_ppaneTool
0x1800ce57f  test    rax, rax
0x1800ce582  jnz     short loc_1800CE5AC
0x1800ce584  mov     rcx, cs:hwnd; hWnd
0x1800ce58b  call    cs:__imp_DestroyWindow
0x1800ce591  xor     eax, eax
0x1800ce593  lea     r11, [rsp+0D8h+var_8]
0x1800ce59b  mov     rbx, [r11+10h]
0x1800ce59f  mov     rbp, [r11+18h]
0x1800ce5a3  mov     rsi, [r11+20h]
0x1800ce5a7  mov     rsp, r11
0x1800ce5aa  pop     rdi
0x1800ce5ab  retn
0x1800ce5ac  mov     rax, cs:hwnd
0x1800ce5b3  mov     cs:dword_1803F38D8, ebx
0x1800ce5b9  jmp     short loc_1800CE593
```
