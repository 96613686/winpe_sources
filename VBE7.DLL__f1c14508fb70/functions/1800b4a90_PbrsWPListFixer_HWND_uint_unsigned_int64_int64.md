# _PbrsWPListFixer(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800b4a90`
- end: `0x1800b5099`
- name: `?_PbrsWPListFixer@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `1545`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800b5264`

## callees

- `0x180028b00`
- `0x1800b4a90`
- `0x1800b5b54`
- `0x1800b78e0`
- `0x1800b79fc`
- `0x1800b92ac`
- `0x1800b9374`
- `0x1800bd38c`
- `0x1800be974`
- `0x18013830c`
- `0x18013843c`
- `0x180139f00`
- `0x18013b71c`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!free` at `0x1800b4ea1`
- `MSVCR100!free` at `0x1800b4ea1`
- `MSVCR100!malloc` at `0x1800b4e58`
- `MSVCR100!malloc` at `0x1800b4e58`
- `MSVCR100!strncpy_s` at `0x1800b4f3a`
- `MSVCR100!strncpy_s` at `0x1800b4f3a`
- `MSVCR100!strcat_s` at `0x1800b4f5a`
- `MSVCR100!strcat_s` at `0x1800b4f69`
- `MSVCR100!strcat_s` at `0x1800b4f5a`
- `MSVCR100!strcat_s` at `0x1800b4f69`
- `KERNEL32!lstrlenA` at `0x1800b4e3b`
- `KERNEL32!lstrlenA` at `0x1800b4e4a`
- `KERNEL32!lstrlenA` at `0x1800b4e3b`
- `KERNEL32!lstrlenA` at `0x1800b4e4a`
- `KERNEL32!lstrcpyA` at `0x1800b4e75`
- `KERNEL32!lstrcpyA` at `0x1800b4e75`
- `KERNEL32!lstrcatA` at `0x1800b4e81`
- `KERNEL32!lstrcatA` at `0x1800b4e81`
- `USER32!GetMessageTime` at `0x1800b4d5c`
- `USER32!GetMessageTime` at `0x1800b4d5c`
- `USER32!CallWindowProcA` at `0x1800b4fb9`
- `USER32!CallWindowProcA` at `0x1800b4fb9`
- `USER32!ShowWindow` at `0x1800b4bab`
- `USER32!ShowWindow` at `0x1800b4bba`
- `USER32!ShowWindow` at `0x1800b4bab`
- `USER32!ShowWindow` at `0x1800b4bba`
- `USER32!GetClientRect` at `0x1800b4c39`
- `USER32!GetClientRect` at `0x1800b4c39`
- `USER32!GetSysColor` at `0x1800b4c4d`
- `USER32!GetSysColor` at `0x1800b4c4d`
- `USER32!GetParent` at `0x1800b4f81`
- `USER32!GetParent` at `0x1800b4f81`
- `USER32!SendMessageA` at `0x1800b4b3e`
- `USER32!SendMessageA` at `0x1800b4dce`
- `USER32!SendMessageA` at `0x1800b4df1`
- `USER32!SendMessageA` at `0x1800b4ed3`
- `USER32!SendMessageA` at `0x1800b4f92`
- `USER32!SendMessageA` at `0x1800b5010`
- `USER32!SendMessageA` at `0x1800b5033`
- `USER32!SendMessageA` at `0x1800b4b3e`
- `USER32!SendMessageA` at `0x1800b4dce`
- `USER32!SendMessageA` at `0x1800b4df1`
- `USER32!SendMessageA` at `0x1800b4ed3`
- `USER32!SendMessageA` at `0x1800b4f92`
- `USER32!SendMessageA` at `0x1800b5010`
- `USER32!SendMessageA` at `0x1800b5033`
- `GDI32!LineTo` at `0x1800b4ce6`
- `GDI32!LineTo` at `0x1800b4ce6`
- `GDI32!MoveToEx` at `0x1800b4ccb`
- `GDI32!MoveToEx` at `0x1800b4ccb`
- `GDI32!ExtTextOutA` at `0x1800b4c8b`
- `GDI32!ExtTextOutA` at `0x1800b4c8b`
- `GDI32!SelectObject` at `0x1800b4caa`
- `GDI32!SelectObject` at `0x1800b4caa`
- `GDI32!SetBkColor` at `0x1800b4c58`
- `GDI32!SetBkColor` at `0x1800b4c58`
- `GDI32!DeleteObject` at `0x1800b4cfa`
- `GDI32!DeleteObject` at `0x1800b4cfa`
- `GDI32!CreatePen` at `0x1800b4c9b`
- `GDI32!CreatePen` at `0x1800b4c9b`

## pseudocode

```c
LRESULT __fastcall _PbrsWPListFixer(HWND a1, unsigned int a2, HDC a3, char *a4)
{
  LRESULT v8; // rax
  __int64 v9; // rbx
  __int64 *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  LRESULT result; // rax
  IRawElementProviderSimple *v15; // r9
  COLORREF SysColor; // eax
  HPEN Pen; // rdi
  HPEN v18; // rbx
  IRawElementProviderSimple *v19; // rcx
  LONG MessageTime; // eax
  LRESULT v21; // rax
  __int64 v22; // rbx
  char *v23; // rax
  char *v24; // rsi
  char *v25; // r14
  const CHAR *v26; // rdi
  int v27; // ebx
  int v28; // eax
  char *v29; // rax
  CHAR *v30; // rbx
  char *v31; // rcx
  LRESULT v32; // rax
  char *v33; // rax
  const char *v34; // r8
  const char *v35; // rsi
  int v36; // edi
  HWND Parent; // rax
  int v38; // eax
  int v39; // edi
  LRESULT v40; // rax
  __int64 v41; // rcx
  __int64 v42; // [rsp+40h] [rbp-19h] BYREF
  struct tagRECT Rect; // [rsp+50h] [rbp-9h] BYREF
  RECT rect; // [rsp+60h] [rbp+7h] BYREF

  if ( (unsigned int)FIsPbrsMessage(a1, a2, (unsigned __int64)a3, (__int64)a4, &v42, 0) )
    return v42;
  if ( a2 <= 0x201 )
  {
    switch ( a2 )
    {
      case 0x201u:
        dword_1803FB084 = 1;
        MessageTime = GetMessageTime();
        qword_1803FB0A0 = (__int64)a4;
        dword_1803FB098 = MessageTime;
        goto LABEL_72;
      case 1u:
        dword_1803FB070 = 0;
        goto LABEL_72;
      case 2u:
        dword_1803FB070 = 1;
        if ( el )
        {
          DisconnectAutomationProvider(el);
          v19 = el;
          if ( el )
          {
            el = 0;
            ((void (__fastcall *)(IRawElementProviderSimple *))v19->lpVtbl->Release)(v19);
          }
        }
        goto LABEL_72;
    }
    if ( a2 != 20 )
    {
      if ( a2 != 61 )
      {
        if ( a2 == 161 )
        {
          ShowWindow(hWndInsertAfter, 0);
          ShowWindow(qword_1803F3330, 0);
        }
        else if ( a2 == 394 )
        {
          v8 = SendMessageA(hWndTo, 0x199u, (int)a3, 0);
          v9 = -1;
          if ( v8 != -1 )
          {
            v10 = (__int64 *)((char *)lprgpi + 80 * v8);
            if ( (_DWORD)v10 != -1 )
            {
              v11 = *v10;
              v12 = v10[1];
              if ( *v10 )
              {
                if ( v12 )
                {
                  v13 = -1;
                  do
                    ++v13;
                  while ( *(_BYTE *)(v12 + v13) );
                  do
                    ++v9;
                  while ( *(_BYTE *)(v11 + v9) );
                  return v9 + v13 + 1;
                }
                do
                  ++v9;
                while ( *(_BYTE *)(v11 + v9) );
              }
            }
          }
          return v9;
        }
        goto LABEL_72;
      }
      if ( a4 == (char *)-25LL && !(unsigned int)UIAProxiesDisabled() && !dword_1803FB070 )
      {
        v15 = el;
        if ( !el )
        {
          CreateListProvider(a1, &el);
          v15 = el;
        }
        return UiaReturnRawElementProvider_0(a1, (WPARAM)a3, -25, v15);
      }
LABEL_72:
      v42 = (int)CallWindowProcA(pfnwpList, a1, a2, (WPARAM)a3, (LPARAM)a4);
      if ( a2 == 277 )
      {
        _HideSel();
        if ( a3 == (HDC)8 && (unsigned int)_ComputeEditPos() )
          _RepositionEdit();
      }
      else if ( a2 == 513 && (dword_1803FB04C & 0x4000) != 0 && (__int16)a4 < nHeight + 3 )
      {
        _PickProp();
        v38 = SendMessageA(a1, 0x188u, 0, 0);
        v39 = v38;
        if ( v38 != -1 )
        {
          v40 = SendMessageA(hWndTo, 0x199u, v38, 0);
          if ( v40 == -1 )
            v41 = -1;
          else
            v41 = (__int64)lprgpi + 80 * v40;
          if ( *(_DWORD *)(v41 + 16) == -1 )
            _AddRemoveOutlineEntries((struct tagPropItem *)v41, v39);
        }
      }
      return v42;
    }
    if ( (dword_1803FB04C & 0x4000) == 0 )
      goto LABEL_72;
    GetClientRect(a1, &Rect);
    rect = Rect;
    SysColor = GetSysColor(5);
    SetBkColor(a3, SysColor);
    ExtTextOutA(a3, 0, 0, 2u, &rect, (LPCSTR)&Class, 0, 0);
    Pen = CreatePen(0, 0, 0xC0C0C0u);
    v18 = (HPEN)SelectObject(a3, Pen);
    MoveToEx(a3, nHeight + 2 + Rect.left, Rect.top, 0);
    LineTo(a3, nHeight + 2 + Rect.left, Rect.bottom);
    RestorePen(a3, v18);
    DeleteObject(Pen);
    return 1;
  }
  switch ( a2 )
  {
    case 0x203u:
      dword_1803FB084 = 0;
      goto LABEL_72;
    case 0x204u:
      dword_1803FB084 = 0;
      goto LABEL_70;
    case 0x205u:
LABEL_70:
      Parent = GetParent(a1);
      return SendMessageA(Parent, a2, (WPARAM)a3, (LPARAM)a4);
  }
  if ( a2 != 1125 )
  {
    if ( a2 <= 0x1082 || a2 > 0x1084 )
      goto LABEL_72;
    if ( (int)a3 >= (int)SendMessageA(hWndTo, 0x18Bu, 0, 0) )
      return 0;
    v21 = SendMessageA(hWndTo, 0x199u, (int)a3, 0);
    v22 = -1;
    if ( v21 != -1 )
      v22 = (__int64)lprgpi + 80 * v21;
    if ( a2 == 4227 )
    {
      v23 = *(char **)v22;
      v24 = 0;
      v25 = Rby_szNull;
      if ( *(_DWORD *)(v22 + 32) == 2 )
      {
        v26 = Rby_szNull;
        if ( v23 )
          v26 = *(const CHAR **)v22;
        v27 = lstrlenA(v26);
        v28 = lstrlenA("Object.");
        v29 = (char *)malloc(v27 + v28 + 1);
        v30 = Rby_szNull;
        v24 = v29;
        if ( v29 )
          v30 = v29;
        lstrcpyA(v30, "Object.");
        lstrcatA(v30, v26);
        v23 = v24;
      }
      if ( v23 )
        v25 = v23;
      TestStrCopy(v25);
      if ( v24 )
        free(v24);
    }
    else
    {
      v31 = *(char **)(v22 + 8);
      if ( v31 )
        TestStrCopy(v31);
    }
    return 1;
  }
  v32 = SendMessageA(hWndTo, 0x199u, (int)a3, 0);
  v9 = -1;
  if ( v32 == -1 )
    return v9;
  v33 = (char *)lprgpi + 80 * v32;
  if ( (_DWORD)v33 == -1 )
    return v9;
  v34 = *(const char **)v33;
  v35 = (const char *)*((_QWORD *)v33 + 1);
  result = -1;
  if ( v34 )
  {
    do
      ++result;
    while ( v34[result] );
    if ( v35 )
    {
      do
        ++v9;
      while ( v35[v9] );
    }
    else
    {
      LODWORD(v9) = 0;
    }
    v36 = v9 + result;
    strncpy_s(a4, (int)result + 1, v34, (int)result + 1);
    if ( v35 )
    {
      strcat_s(a4, ++v36 + 1, " ");
      strcat_s(a4, v36 + 1, v35);
    }
    return v36;
  }
  return result;
}

```

## disassembly

```asm
0x1800b4a90  push    rbp
0x1800b4a92  push    rbx
0x1800b4a93  push    rsi
0x1800b4a94  push    rdi
0x1800b4a95  push    r14
0x1800b4a97  push    r15
0x1800b4a99  lea     rbp, [rsp-2Fh]
0x1800b4a9e  mov     eax, 88h
0x1800b4aa3  call    _alloca_probe
0x1800b4aa8  sub     rsp, rax
0x1800b4aab  mov     rax, cs:__security_cookie
0x1800b4ab2  xor     rax, rsp
0x1800b4ab5  mov     [rbp+57h+var_40], rax
0x1800b4ab9  lea     rax, [rbp+57h+var_70]
0x1800b4abd  xor     r15d, r15d
0x1800b4ac0  mov     r14, r9
0x1800b4ac3  mov     dword ptr [rsp+0B0h+lpString], r15d; int
0x1800b4ac8  mov     rsi, r8
0x1800b4acb  mov     edi, edx
0x1800b4acd  mov     [rsp+0B0h+lprect], rax; __int64 *
0x1800b4ad2  mov     rbx, rcx
0x1800b4ad5  call    ?FIsPbrsMessage@@YAHPEAUHWND__@@I_K_JPEA_JH@Z; FIsPbrsMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 *,int)
0x1800b4ada  test    eax, eax
0x1800b4adc  jnz     loc_1800B5079
0x1800b4ae2  cmp     edi, 201h
0x1800b4ae8  ja      loc_1800B4D74
0x1800b4aee  jz      loc_1800B4D52
0x1800b4af4  mov     eax, edi
0x1800b4af6  dec     eax
0x1800b4af8  jz      loc_1800B4D46
0x1800b4afe  dec     eax
0x1800b4b00  jz      loc_1800B4D05
0x1800b4b06  sub     eax, 12h
0x1800b4b09  jz      loc_1800B4C22
0x1800b4b0f  sub     eax, 29h ; ')'
0x1800b4b12  jz      loc_1800B4BC5
0x1800b4b18  sub     eax, 64h ; 'd'
0x1800b4b1b  jz      loc_1800B4BA2
0x1800b4b21  cmp     eax, 0E9h
0x1800b4b26  jnz     loc_1800B4FA4
0x1800b4b2c  mov     rcx, cs:hWndTo; hWnd
0x1800b4b33  movsxd  r8, esi; wParam
0x1800b4b36  xor     r9d, r9d; lParam
0x1800b4b39  mov     edx, 199h; Msg
0x1800b4b3e  call    cs:__imp_SendMessageA
0x1800b4b44  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b4b48  cmp     rax, rbx
0x1800b4b4b  jz      short loc_1800B4B9A
0x1800b4b4d  lea     rax, [rax+rax*4]
0x1800b4b51  shl     rax, 4
0x1800b4b55  add     rax, cs:?lprgpi@@3PEAUtagPropItem@@EA; tagPropItem * lprgpi
0x1800b4b5c  cmp     eax, ebx
0x1800b4b5e  jz      short loc_1800B4B9A
0x1800b4b60  mov     rcx, [rax]
0x1800b4b63  mov     rdx, [rax+8]
0x1800b4b67  test    rcx, rcx
0x1800b4b6a  jz      short loc_1800B4B9A
0x1800b4b6c  test    rdx, rdx
0x1800b4b6f  jz      short loc_1800B4B91
0x1800b4b71  mov     rax, rbx
0x1800b4b74  inc     rax
0x1800b4b77  cmp     [rdx+rax], r15b
0x1800b4b7b  jnz     short loc_1800B4B74
0x1800b4b7d  inc     rbx
0x1800b4b80  cmp     [rcx+rbx], r15b
0x1800b4b84  jnz     short loc_1800B4B7D
0x1800b4b86  inc     rax
0x1800b4b89  add     rax, rbx
0x1800b4b8c  jmp     loc_1800B507D
0x1800b4b91  inc     rbx
0x1800b4b94  cmp     [rcx+rbx], r15b
0x1800b4b98  jnz     short loc_1800B4B91
0x1800b4b9a  mov     rax, rbx
0x1800b4b9d  jmp     loc_1800B507D
0x1800b4ba2  mov     rcx, cs:hWndInsertAfter; hWnd
0x1800b4ba9  xor     edx, edx; nCmdShow
0x1800b4bab  call    cs:__imp_ShowWindow
0x1800b4bb1  mov     rcx, cs:qword_1803F3330; hWnd
0x1800b4bb8  xor     edx, edx; nCmdShow
0x1800b4bba  call    cs:__imp_ShowWindow
0x1800b4bc0  jmp     loc_1800B4FA4
0x1800b4bc5  cmp     r14, 0FFFFFFFFFFFFFFE7h
0x1800b4bc9  jnz     loc_1800B4FA4
0x1800b4bcf  call    ?UIAProxiesDisabled@@YAHXZ; UIAProxiesDisabled(void)
0x1800b4bd4  test    eax, eax
0x1800b4bd6  jnz     loc_1800B4FA4
0x1800b4bdc  cmp     cs:dword_1803FB070, r15d
0x1800b4be3  jnz     loc_1800B4FA4
0x1800b4be9  mov     r9, cs:el
0x1800b4bf0  test    r9, r9
0x1800b4bf3  jnz     short loc_1800B4C0B
0x1800b4bf5  lea     rdx, el; struct IRawElementProviderSimple **
0x1800b4bfc  mov     rcx, rbx; HWND
0x1800b4bff  call    ?CreateListProvider@@YAJPEAUHWND__@@PEAPEAUIRawElementProviderSimple@@@Z; CreateListProvider(HWND__ *,IRawElementProviderSimple * *)
0x1800b4c04  mov     r9, cs:el; el
0x1800b4c0b  mov     r8, 0FFFFFFFFFFFFFFE7h; lParam
0x1800b4c12  mov     rdx, rsi; wParam
0x1800b4c15  mov     rcx, rbx; hwnd
0x1800b4c18  call    UiaReturnRawElementProvider_0
0x1800b4c1d  jmp     loc_1800B507D
0x1800b4c22  test    cs:dword_1803FB04C, 4000h
0x1800b4c2c  jz      loc_1800B4FA4
0x1800b4c32  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800b4c36  mov     rcx, rbx; hWnd
0x1800b4c39  call    cs:__imp_GetClientRect
0x1800b4c3f  mov     ecx, 5; nIndex
0x1800b4c44  movaps  xmm5, xmmword ptr [rbp+57h+Rect.left]
0x1800b4c48  movdqa  xmmword ptr [rbp+57h+rect.left], xmm5
0x1800b4c4d  call    cs:__imp_GetSysColor
0x1800b4c53  mov     rcx, rsi; hdc
0x1800b4c56  mov     edx, eax; color
0x1800b4c58  call    cs:__imp_SetBkColor
0x1800b4c5e  mov     [rsp+0B0h+lpDx], r15; lpDx
0x1800b4c63  lea     rax, Class
0x1800b4c6a  mov     [rsp+0B0h+c], r15d; c
0x1800b4c6f  mov     [rsp+0B0h+lpString], rax; lpString
0x1800b4c74  lea     rax, [rbp+57h+rect]
0x1800b4c78  mov     r9d, 2; options
0x1800b4c7e  xor     r8d, r8d; y
0x1800b4c81  xor     edx, edx; x
0x1800b4c83  mov     rcx, rsi; hdc
0x1800b4c86  mov     [rsp+0B0h+lprect], rax; lprect
0x1800b4c8b  call    cs:__imp_ExtTextOutA
0x1800b4c91  xor     edx, edx; cWidth
0x1800b4c93  xor     ecx, ecx; iStyle
0x1800b4c95  mov     r8d, 0C0C0C0h; color
0x1800b4c9b  call    cs:__imp_CreatePen
0x1800b4ca1  mov     rcx, rsi; hdc
0x1800b4ca4  mov     rdx, rax; h
0x1800b4ca7  mov     rdi, rax
0x1800b4caa  call    cs:__imp_SelectObject
0x1800b4cb0  mov     ecx, cs:nHeight
0x1800b4cb6  mov     edx, [rbp+57h+Rect.left]
0x1800b4cb9  mov     r8d, [rbp+57h+Rect.top]; y
0x1800b4cbd  add     ecx, 2
0x1800b4cc0  xor     r9d, r9d; lppt
0x1800b4cc3  add     edx, ecx; x
0x1800b4cc5  mov     rcx, rsi; hdc
0x1800b4cc8  mov     rbx, rax
0x1800b4ccb  call    cs:__imp_MoveToEx
0x1800b4cd1  mov     ecx, cs:nHeight
0x1800b4cd7  mov     edx, [rbp+57h+Rect.left]
0x1800b4cda  mov     r8d, [rbp+57h+Rect.bottom]; y
0x1800b4cde  add     ecx, 2
0x1800b4ce1  add     edx, ecx; x
0x1800b4ce3  mov     rcx, rsi; hdc
0x1800b4ce6  call    cs:__imp_LineTo
0x1800b4cec  mov     rdx, rbx; HPEN
0x1800b4cef  mov     rcx, rsi; HDC
0x1800b4cf2  call    ?RestorePen@@YAXPEAUHDC__@@PEAUHPEN__@@@Z; RestorePen(HDC__ *,HPEN__ *)
0x1800b4cf7  mov     rcx, rdi; ho
0x1800b4cfa  call    cs:__imp_DeleteObject
0x1800b4d00  jmp     loc_1800B4EB7
0x1800b4d05  mov     rcx, cs:el; struct IRawElementProviderSimple *
0x1800b4d0c  mov     cs:dword_1803FB070, 1
0x1800b4d16  test    rcx, rcx
0x1800b4d19  jz      loc_1800B4FA4
0x1800b4d1f  call    ?DisconnectAutomationProvider@@YAJPEAUIRawElementProviderSimple@@@Z; DisconnectAutomationProvider(IRawElementProviderSimple *)
0x1800b4d24  mov     rcx, cs:el
0x1800b4d2b  test    rcx, rcx
0x1800b4d2e  jz      loc_1800B4FA4
0x1800b4d34  mov     cs:el, r15
0x1800b4d3b  mov     rax, [rcx]
0x1800b4d3e  call    qword ptr [rax+10h]
0x1800b4d41  jmp     loc_1800B4FA4
0x1800b4d46  mov     cs:dword_1803FB070, r15d
0x1800b4d4d  jmp     loc_1800B4FA4
0x1800b4d52  mov     cs:dword_1803FB084, 1
0x1800b4d5c  call    cs:__imp_GetMessageTime
0x1800b4d62  mov     cs:qword_1803FB0A0, r14
0x1800b4d69  mov     cs:dword_1803FB098, eax
0x1800b4d6f  jmp     loc_1800B4FA4
0x1800b4d74  cmp     edi, 203h
0x1800b4d7a  jz      loc_1800B4F9D
0x1800b4d80  cmp     edi, 204h
0x1800b4d86  jz      loc_1800B4F77
0x1800b4d8c  cmp     edi, 205h
0x1800b4d92  jz      loc_1800B4F7E
0x1800b4d98  cmp     edi, 465h
0x1800b4d9e  jz      loc_1800B4EC1
0x1800b4da4  cmp     edi, 1082h
0x1800b4daa  jbe     loc_1800B4FA4
0x1800b4db0  cmp     edi, 1084h
0x1800b4db6  ja      loc_1800B4FA4
0x1800b4dbc  mov     rcx, cs:hWndTo; hWnd
0x1800b4dc3  xor     r9d, r9d; lParam
0x1800b4dc6  xor     r8d, r8d; wParam
0x1800b4dc9  mov     edx, 18Bh; Msg
0x1800b4dce  call    cs:__imp_SendMessageA
0x1800b4dd4  cmp     esi, eax
0x1800b4dd6  jl      short loc_1800B4DDF
0x1800b4dd8  xor     eax, eax
0x1800b4dda  jmp     loc_1800B507D
0x1800b4ddf  mov     rcx, cs:hWndTo; hWnd
0x1800b4de6  movsxd  r8, esi; wParam
0x1800b4de9  xor     r9d, r9d; lParam
0x1800b4dec  mov     edx, 199h; Msg
0x1800b4df1  call    cs:__imp_SendMessageA
0x1800b4df7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b4dfb  cmp     rax, rbx
0x1800b4dfe  jz      short loc_1800B4E0F
0x1800b4e00  lea     rbx, [rax+rax*4]
0x1800b4e04  shl     rbx, 4
0x1800b4e08  add     rbx, cs:?lprgpi@@3PEAUtagPropItem@@EA; tagPropItem * lprgpi
0x1800b4e0f  cmp     edi, 1083h
0x1800b4e15  jnz     loc_1800B4EA9
0x1800b4e1b  cmp     dword ptr [rbx+20h], 2
0x1800b4e1f  mov     rax, [rbx]
0x1800b4e22  mov     rsi, r15
0x1800b4e25  lea     r14, ?Rby_szNull@@3PADA; char near * Rby_szNull
0x1800b4e2c  jnz     short loc_1800B4E8A
0x1800b4e2e  test    rax, rax
0x1800b4e31  mov     rdi, r14
0x1800b4e34  cmovnz  rdi, rax
0x1800b4e38  mov     rcx, rdi; lpString
0x1800b4e3b  call    cs:__imp_lstrlenA
0x1800b4e41  lea     rcx, aObject_1; "Object."
0x1800b4e48  mov     ebx, eax
0x1800b4e4a  call    cs:__imp_lstrlenA
0x1800b4e50  lea     ecx, [rax+1]
0x1800b4e53  add     ecx, ebx
0x1800b4e55  movsxd  rcx, ecx; Size
0x1800b4e58  call    cs:__imp_malloc
0x1800b4e5e  mov     rbx, r14
0x1800b4e61  lea     rdx, aObject_1; "Object."
0x1800b4e68  test    rax, rax
0x1800b4e6b  mov     rsi, rax
0x1800b4e6e  cmovnz  rbx, rax
0x1800b4e72  mov     rcx, rbx; lpString1
0x1800b4e75  call    cs:__imp_lstrcpyA
0x1800b4e7b  mov     rdx, rdi; lpString2
0x1800b4e7e  mov     rcx, rbx; lpString1
0x1800b4e81  call    cs:__imp_lstrcatA
0x1800b4e87  mov     rax, rsi
0x1800b4e8a  test    rax, rax
0x1800b4e8d  cmovnz  r14, rax
0x1800b4e91  mov     rcx, r14; char *
0x1800b4e94  call    ?TestStrCopy@@YAXPEAD@Z; TestStrCopy(char *)
0x1800b4e99  test    rsi, rsi
0x1800b4e9c  jz      short loc_1800B4EB7
0x1800b4e9e  mov     rcx, rsi; Block
0x1800b4ea1  call    cs:__imp_free
0x1800b4ea7  jmp     short loc_1800B4EB7
0x1800b4ea9  mov     rcx, [rbx+8]; char *
0x1800b4ead  test    rcx, rcx
0x1800b4eb0  jz      short loc_1800B4EB7
0x1800b4eb2  call    ?TestStrCopy@@YAXPEAD@Z; TestStrCopy(char *)
0x1800b4eb7  mov     eax, 1
0x1800b4ebc  jmp     loc_1800B507D
0x1800b4ec1  mov     rcx, cs:hWndTo; hWnd
0x1800b4ec8  movsxd  r8, esi; wParam
0x1800b4ecb  xor     r9d, r9d; lParam
0x1800b4ece  mov     edx, 199h; Msg
0x1800b4ed3  call    cs:__imp_SendMessageA
0x1800b4ed9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b4edd  cmp     rax, rbx
0x1800b4ee0  jz      loc_1800B4B9A
0x1800b4ee6  lea     rax, [rax+rax*4]
0x1800b4eea  shl     rax, 4
0x1800b4eee  add     rax, cs:?lprgpi@@3PEAUtagPropItem@@EA; tagPropItem * lprgpi
0x1800b4ef5  cmp     eax, ebx
0x1800b4ef7  jz      loc_1800B4B9A
0x1800b4efd  mov     r8, [rax]; Source
0x1800b4f00  mov     rsi, [rax+8]
0x1800b4f04  mov     rax, rbx
0x1800b4f07  test    r8, r8
0x1800b4f0a  jz      loc_1800B507D
0x1800b4f10  inc     rax
0x1800b4f13  cmp     [r8+rax], r15b
0x1800b4f17  jnz     short loc_1800B4F10
0x1800b4f19  test    rsi, rsi
0x1800b4f1c  jz      short loc_1800B4F29
0x1800b4f1e  inc     rbx
0x1800b4f21  cmp     [rsi+rbx], r15b
0x1800b4f25  jnz     short loc_1800B4F1E
0x1800b4f27  jmp     short loc_1800B4F2C
0x1800b4f29  mov     ebx, r15d
0x1800b4f2c  lea     edi, [rbx+rax]
0x1800b4f2f  inc     eax
0x1800b4f31  mov     rcx, r14; Destination
0x1800b4f34  movsxd  rdx, eax; SizeInBytes
0x1800b4f37  mov     r9, rdx; MaxCount
0x1800b4f3a  call    cs:__imp_strncpy_s
0x1800b4f40  test    rsi, rsi
0x1800b4f43  jz      short loc_1800B4F6F
0x1800b4f45  inc     edi
0x1800b4f47  lea     r8, asc_1803A37AC; " "
0x1800b4f4e  mov     rcx, r14; Destination
0x1800b4f51  lea     eax, [rdi+1]
0x1800b4f54  movsxd  rbx, eax
0x1800b4f57  mov     rdx, rbx; SizeInBytes
0x1800b4f5a  call    cs:__imp_strcat_s
0x1800b4f60  mov     r8, rsi; Source
0x1800b4f63  mov     rdx, rbx; SizeInBytes
0x1800b4f66  mov     rcx, r14; Destination
0x1800b4f69  call    cs:__imp_strcat_s
0x1800b4f6f  movsxd  rax, edi
0x1800b4f72  jmp     loc_1800B507D
0x1800b4f77  mov     cs:dword_1803FB084, r15d
0x1800b4f7e  mov     rcx, rbx; hWnd
  ... truncated ...
```
