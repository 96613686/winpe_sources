# MainEnableOneWindow(HWND__ *,int,ushort)

- ea: `0x180022c48`
- end: `0x180022dcf`
- name: `?MainEnableOneWindow@@YAXPEAUHWND__@@HG@Z`
- size: `391`
- prototype: `void __fastcall(HWND, int, unsigned __int16)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180021c00`
- `0x180022e10`

## callees

- `0x18000e708`
- `0x1800126d4`
- `0x180012a14`
- `0x180022c48`
- `0x180037ee4`
- `0x180379380`

## import_xrefs

- `USER32!RemovePropA` at `0x180022d37`
- `USER32!RemovePropA` at `0x180022d66`
- `USER32!RemovePropA` at `0x180022d37`
- `USER32!RemovePropA` at `0x180022d66`
- `USER32!GetPropA` at `0x180022d1b`
- `USER32!GetPropA` at `0x180022d1b`
- `USER32!SetPropA` at `0x180022d8f`
- `USER32!SetPropA` at `0x180022db4`
- `USER32!SetPropA` at `0x180022d8f`
- `USER32!SetPropA` at `0x180022db4`
- `USER32!GetWindowLongPtrA` at `0x180022cdf`
- `USER32!GetWindowLongPtrA` at `0x180022cf3`
- `USER32!GetWindowLongPtrA` at `0x180022cdf`
- `USER32!GetWindowLongPtrA` at `0x180022cf3`
- `USER32!EnableWindow` at `0x180022d9e`
- `USER32!EnableWindow` at `0x180022d9e`
- `USER32!IsWindowEnabled` at `0x180022cb1`
- `USER32!IsWindowEnabled` at `0x180022d09`
- `USER32!IsWindowEnabled` at `0x180022cb1`
- `USER32!IsWindowEnabled` at `0x180022d09`

## pseudocode

```c
void __fastcall MainEnableOneWindow(HWND a1, int a2, char a3)
{
  struct CTL *v6; // rax
  struct CTL *v7; // rdi
  int v8; // edx
  BOOL v9; // esi
  HANDLE PropA; // rax
  unsigned __int64 v11; // rdi
  void *v12; // r8
  BOOL v13; // edx

  v6 = CtlHctlOfHwnd(a1);
  v7 = v6;
  if ( !v6 )
  {
    if ( (a3 & 4) != 0
      && (HINSTANCE)GetWindowLongPtrA(a1, -6) != Rby_hinstExe
      && (HINSTANCE)GetWindowLongPtrA(a1, -6) != Rby_hIntlLib )
    {
      return;
    }
    v9 = IsWindowEnabled(a1);
    PropA = GetPropA(a1, (LPCSTR)Rby_atomVBDisabled);
    v11 = (unsigned __int64)PropA;
    if ( v9 && PropA )
      RemovePropA(a1, (LPCSTR)Rby_atomVBDisabled);
    if ( a2 )
    {
      if ( v11 == 1 || v9 )
      {
        if ( v11 && RemovePropA(a1, (LPCSTR)Rby_atomVBDisabled) )
        {
LABEL_24:
          v13 = 1;
LABEL_29:
          EnableWindow(a1, v13);
          return;
        }
        return;
      }
      if ( v11 <= 1 )
        return;
      v12 = (void *)(v11 - 1);
    }
    else
    {
      if ( !v11 )
      {
        if ( v9 && SetPropA(a1, (LPCSTR)Rby_atomVBDisabled, HANDLE_FLAG_INHERIT) )
          goto LABEL_28;
        return;
      }
      v12 = (void *)(v11 + 1);
    }
    SetPropA(a1, (LPCSTR)Rby_atomVBDisabled, v12);
    return;
  }
  if ( (a3 & 1) == 0 )
    OleCEnableModeless(*((struct DESK **)v6 + 8), a2);
  if ( (a3 & 2) == 0 )
  {
    if ( a2 )
    {
      if ( (unsigned int)DeskGetDisabledBeforeDlg(v7) )
      {
        v8 = 0;
LABEL_10:
        DeskSetDisabledBeforeDlg(v7, v8);
        return;
      }
      goto LABEL_24;
    }
    if ( !IsWindowEnabled(a1) )
    {
      v8 = 1;
      goto LABEL_10;
    }
LABEL_28:
    v13 = 0;
    goto LABEL_29;
  }
}

```

## disassembly

```asm
0x180022c48  mov     [rsp+arg_0], rbx
0x180022c4d  mov     [rsp+arg_8], rbp
0x180022c52  mov     [rsp+arg_10], rsi
0x180022c57  push    rdi
0x180022c58  mov     eax, 20h
0x180022c5d  call    _alloca_probe
0x180022c62  sub     rsp, rax
0x180022c65  movzx   esi, r8w
0x180022c69  mov     ebp, edx
0x180022c6b  mov     rbx, rcx
0x180022c6e  call    ?CtlHctlOfHwnd@@YAPEAUCTL@@PEAUHWND__@@@Z; CtlHctlOfHwnd(HWND__ *)
0x180022c73  mov     rdi, rax
0x180022c76  test    rax, rax
0x180022c79  jz      short loc_180022CCF
0x180022c7b  test    sil, 1
0x180022c7f  jnz     short loc_180022C8C
0x180022c81  mov     rcx, [rax+40h]; struct DESK *
0x180022c85  mov     edx, ebp; int
0x180022c87  call    ?OleCEnableModeless@@YAXPEAVDESK@@H@Z; OleCEnableModeless(DESK *,int)
0x180022c8c  test    sil, 2
0x180022c90  jnz     loc_180022DBA
0x180022c96  test    ebp, ebp
0x180022c98  jz      short loc_180022CAE
0x180022c9a  mov     rcx, rdi; struct CTL *
0x180022c9d  call    ?DeskGetDisabledBeforeDlg@@YAHPEAUCTL@@@Z; DeskGetDisabledBeforeDlg(CTL *)
0x180022ca2  test    eax, eax
0x180022ca4  jz      loc_180022D71
0x180022caa  xor     edx, edx
0x180022cac  jmp     short loc_180022CC2
0x180022cae  mov     rcx, rbx; hWnd
0x180022cb1  call    cs:__imp_IsWindowEnabled
0x180022cb7  test    eax, eax
0x180022cb9  jnz     loc_180022D99
0x180022cbf  lea     edx, [rax+1]; int
0x180022cc2  mov     rcx, rdi; struct CTL *
0x180022cc5  call    ?DeskSetDisabledBeforeDlg@@YAXPEAUCTL@@H@Z; DeskSetDisabledBeforeDlg(CTL *,int)
0x180022cca  jmp     loc_180022DBA
0x180022ccf  test    sil, 4
0x180022cd3  jz      short loc_180022D06
0x180022cd5  mov     edi, 0FFFFFFFAh
0x180022cda  mov     rcx, rbx; hWnd
0x180022cdd  mov     edx, edi; nIndex
0x180022cdf  call    cs:__imp_GetWindowLongPtrA
0x180022ce5  cmp     rax, cs:?Rby_hinstExe@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * Rby_hinstExe
0x180022cec  jz      short loc_180022D06
0x180022cee  mov     edx, edi; nIndex
0x180022cf0  mov     rcx, rbx; hWnd
0x180022cf3  call    cs:__imp_GetWindowLongPtrA
0x180022cf9  cmp     rax, cs:?Rby_hIntlLib@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * Rby_hIntlLib
0x180022d00  jnz     loc_180022DBA
0x180022d06  mov     rcx, rbx; hWnd
0x180022d09  call    cs:__imp_IsWindowEnabled
0x180022d0f  movzx   edx, cs:?Rby_atomVBDisabled@@3GA; lpString
0x180022d16  mov     rcx, rbx; hWnd
0x180022d19  mov     esi, eax
0x180022d1b  call    cs:__imp_GetPropA
0x180022d21  mov     rdi, rax
0x180022d24  test    esi, esi
0x180022d26  jz      short loc_180022D3D
0x180022d28  test    rax, rax
0x180022d2b  jz      short loc_180022D3D
0x180022d2d  movzx   edx, cs:?Rby_atomVBDisabled@@3GA; lpString
0x180022d34  mov     rcx, rbx; hWnd
0x180022d37  call    cs:__imp_RemovePropA
0x180022d3d  test    ebp, ebp
0x180022d3f  jz      short loc_180022D78
0x180022d41  cmp     rdi, 1
0x180022d45  jz      short loc_180022D57
0x180022d47  test    esi, esi
0x180022d49  jnz     short loc_180022D57
0x180022d4b  cmp     rdi, 1
0x180022d4f  jbe     short loc_180022DBA
0x180022d51  lea     r8, [rdi-1]
0x180022d55  jmp     short loc_180022DAA
0x180022d57  test    rdi, rdi
0x180022d5a  jz      short loc_180022DBA
0x180022d5c  movzx   edx, cs:?Rby_atomVBDisabled@@3GA; lpString
0x180022d63  mov     rcx, rbx; hWnd
0x180022d66  call    cs:__imp_RemovePropA
0x180022d6c  test    rax, rax
0x180022d6f  jz      short loc_180022DBA
0x180022d71  mov     edx, 1
0x180022d76  jmp     short loc_180022D9B
0x180022d78  test    rdi, rdi
0x180022d7b  jnz     short loc_180022DA6
0x180022d7d  test    esi, esi
0x180022d7f  jz      short loc_180022DBA
0x180022d81  movzx   edx, cs:?Rby_atomVBDisabled@@3GA; lpString
0x180022d88  lea     r8d, [rdi+1]; hData
0x180022d8c  mov     rcx, rbx; hWnd
0x180022d8f  call    cs:__imp_SetPropA
0x180022d95  test    eax, eax
0x180022d97  jz      short loc_180022DBA
0x180022d99  xor     edx, edx; bEnable
0x180022d9b  mov     rcx, rbx; hWnd
0x180022d9e  call    cs:__imp_EnableWindow
0x180022da4  jmp     short loc_180022DBA
0x180022da6  lea     r8, [rdi+1]; hData
0x180022daa  movzx   edx, cs:?Rby_atomVBDisabled@@3GA; lpString
0x180022db1  mov     rcx, rbx; hWnd
0x180022db4  call    cs:__imp_SetPropA
0x180022dba  mov     rbx, [rsp+28h+arg_0]
0x180022dbf  mov     rbp, [rsp+28h+arg_8]
0x180022dc4  mov     rsi, [rsp+28h+arg_10]
0x180022dc9  add     rsp, 20h
0x180022dcd  pop     rdi
0x180022dce  retn
```
