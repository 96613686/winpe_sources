# F12::ProcessShortcutKeys(HWND__ * const,tagMSG const *)

- ea: `0x1800300f0`
- end: `0x18003030b`
- name: `?ProcessShortcutKeys@F12@@YA_NQEAUHWND__@@PEBUtagMSG@@@Z`
- size: `539`
- prototype: `bool __fastcall(HWND hWnd, HWND, const struct tagMSG *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800087c0`
- `0x180026c40`

## callees

- `0x1800300f0`

## import_xrefs

- `USER32!PostMessageW` at `0x1800302b6`
- `USER32!PostMessageW` at `0x1800302b6`
- `USER32!SendMessageW` at `0x180030182`
- `USER32!SendMessageW` at `0x1800302fa`
- `USER32!SendMessageW` at `0x180030182`
- `USER32!SendMessageW` at `0x1800302fa`
- `USER32!RegisterWindowMessageW` at `0x180030285`
- `USER32!RegisterWindowMessageW` at `0x180030285`
- `USER32!GetKeyState` at `0x180030120`
- `USER32!GetKeyState` at `0x18003012e`
- `USER32!GetKeyState` at `0x18003013c`
- `USER32!GetKeyState` at `0x1800301a5`
- `USER32!GetKeyState` at `0x1800301b7`
- `USER32!GetKeyState` at `0x1800301c9`
- `USER32!GetKeyState` at `0x180030120`
- `USER32!GetKeyState` at `0x18003012e`
- `USER32!GetKeyState` at `0x18003013c`
- `USER32!GetKeyState` at `0x1800301a5`
- `USER32!GetKeyState` at `0x1800301b7`
- `USER32!GetKeyState` at `0x1800301c9`

## string_xrefs

- `0x18003027e`: `WM_F12_PROC_COMMAND`

## pseudocode

```c
char __fastcall F12::ProcessShortcutKeys(HWND hWnd, _DWORD *a2, const struct tagMSG *a3)
{
  __int64 v4; // rbp
  SHORT KeyState; // bx
  SHORT v6; // si
  SHORT v7; // ax
  WPARAM v8; // r8
  UINT v9; // edx
  LPARAM v10; // r9
  __int64 v12; // rbx
  __int16 v13; // bp
  __int16 v14; // si
  __int16 v15; // dx
  UINT v16; // edx
  UINT v17; // eax

  if ( !hWnd || !a2 )
    return 0;
  if ( a2[2] != 260 )
  {
    if ( a2[2] != 256 )
      return 0;
    v12 = *((_QWORD *)a2 + 2);
    v13 = (unsigned __int16)GetKeyState(17) >> 15;
    v14 = (unsigned __int16)GetKeyState(16) >> 15;
    v15 = (unsigned __int16)GetKeyState(18) >> 15;
    if ( !(_BYTE)v13 )
      goto LABEL_29;
    if ( (_BYTE)v14 )
    {
      if ( (_BYTE)v15 )
        goto LABEL_23;
    }
    else
    {
      if ( (_BYTE)v15 )
        goto LABEL_23;
      if ( (unsigned __int64)(v12 - 49) <= 8 )
      {
        v8 = v12 - 49;
        v10 = 0;
        v9 = 1857;
        goto LABEL_9;
      }
    }
    if ( v12 == 117 )
    {
      v9 = 1858;
      v8 = (unsigned __int8)v14 ^ 1LL;
      v10 = 0;
      goto LABEL_9;
    }
    if ( (_BYTE)v14 )
    {
      if ( ((v12 - 219) & 0xFFFFFFFFFFFFFFFDuLL) == 0 )
      {
        v9 = 1859;
        v8 = v12 == 221;
        v10 = 0;
        goto LABEL_9;
      }
      if ( v12 != 116 )
      {
LABEL_23:
        if ( v12 == 192 )
        {
          v16 = 1870;
          goto LABEL_40;
        }
LABEL_29:
        if ( v12 == 112 )
        {
          PostMessageW(hWnd, 0x759u, 0, 0);
          return 0;
        }
        if ( (_BYTE)v13 )
        {
          if ( (_BYTE)v14 || (_BYTE)v15 || v12 != 80 )
          {
            if ( v12 != 123 )
              return 0;
            v16 = 1872;
          }
          else
          {
            v16 = 1876;
          }
        }
        else
        {
          if ( v12 != 123 )
            return 0;
          v16 = 1890;
        }
LABEL_40:
        SendMessageW(hWnd, v16, 0, 0);
        return 0;
      }
    }
    else if ( v12 != 82 )
    {
      goto LABEL_23;
    }
    v17 = message;
    if ( !message )
    {
      v17 = RegisterWindowMessageW(L"WM_F12_PROC_COMMAND");
      message = v17;
    }
    v10 = 1;
    v9 = v17;
    v8 = 11;
    goto LABEL_9;
  }
  v4 = *((_QWORD *)a2 + 2);
  KeyState = GetKeyState(17);
  v6 = GetKeyState(16);
  v7 = GetKeyState(18);
  if ( KeyState >= 0 && v6 < 0 && v7 < 0 )
  {
    v8 = 73;
    if ( v4 == 73 )
    {
      v9 = 1871;
      v10 = 5;
LABEL_9:
      SendMessageW(hWnd, v9, v8, v10);
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800300f0  push    rbx
0x1800300f2  push    rbp
0x1800300f3  push    rsi
0x1800300f4  push    rdi
0x1800300f5  sub     rsp, 28h
0x1800300f9  mov     rdi, rcx
0x1800300fc  test    rcx, rcx
0x1800300ff  jz      loc_180030300
0x180030105  test    rdx, rdx
0x180030108  jz      loc_180030300
0x18003010e  cmp     dword ptr [rdx+8], 104h
0x180030115  jnz     short loc_18003018F
0x180030117  mov     rbp, [rdx+10h]
0x18003011b  mov     ecx, 11h; nVirtKey
0x180030120  call    cs:__imp_GetKeyState
0x180030126  mov     ecx, 10h; nVirtKey
0x18003012b  movzx   ebx, ax
0x18003012e  call    cs:__imp_GetKeyState
0x180030134  mov     ecx, 12h; nVirtKey
0x180030139  movzx   esi, ax
0x18003013c  call    cs:__imp_GetKeyState
0x180030142  shr     bx, 0Fh
0x180030146  test    bl, bl
0x180030148  jnz     loc_180030300
0x18003014e  shr     si, 0Fh
0x180030152  test    sil, sil
0x180030155  jz      loc_180030300
0x18003015b  shr     ax, 0Fh
0x18003015f  test    al, al
0x180030161  jz      loc_180030300
0x180030167  mov     r8d, 49h ; 'I'; wParam
0x18003016d  cmp     rbp, r8
0x180030170  jnz     loc_180030300
0x180030176  mov     edx, 74Fh; Msg
0x18003017b  lea     r9d, [r8-44h]; lParam
0x18003017f  mov     rcx, rdi; hWnd
0x180030182  call    cs:__imp_SendMessageW
0x180030188  mov     al, 1
0x18003018a  jmp     loc_180030302
0x18003018f  cmp     dword ptr [rdx+8], 100h
0x180030196  jnz     loc_180030300
0x18003019c  mov     rbx, [rdx+10h]
0x1800301a0  mov     ecx, 11h; nVirtKey
0x1800301a5  call    cs:__imp_GetKeyState
0x1800301ab  movzx   ebp, ax
0x1800301ae  mov     ecx, 10h; nVirtKey
0x1800301b3  shr     bp, 0Fh
0x1800301b7  call    cs:__imp_GetKeyState
0x1800301bd  movzx   esi, ax
0x1800301c0  mov     ecx, 12h; nVirtKey
0x1800301c5  shr     si, 0Fh
0x1800301c9  call    cs:__imp_GetKeyState
0x1800301cf  movzx   edx, ax
0x1800301d2  shr     dx, 0Fh
0x1800301d6  test    bpl, bpl
0x1800301d9  jz      loc_1800302A2
0x1800301df  test    sil, sil
0x1800301e2  jnz     short loc_180030203
0x1800301e4  test    dl, dl
0x1800301e6  jnz     short loc_18003025B
0x1800301e8  lea     rcx, [rbx-31h]
0x1800301ec  cmp     rcx, 8
0x1800301f0  ja      short loc_180030207
0x1800301f2  lea     r8, [rbx-31h]
0x1800301f6  xor     r9d, r9d
0x1800301f9  mov     edx, 741h
0x1800301fe  jmp     loc_18003017F
0x180030203  test    dl, dl
0x180030205  jnz     short loc_18003025B
0x180030207  cmp     rbx, 75h ; 'u'
0x18003020b  jnz     short loc_180030222
0x18003020d  movzx   r8d, sil
0x180030211  mov     edx, 742h
0x180030216  xor     r8, 1
0x18003021a  xor     r9d, r9d
0x18003021d  jmp     loc_18003017F
0x180030222  test    dl, dl
0x180030224  jnz     short loc_18003025B
0x180030226  test    sil, sil
0x180030229  jz      short loc_18003026E
0x18003022b  lea     rax, [rbx-0DBh]
0x180030232  test    rax, 0FFFFFFFFFFFFFFFDh
0x180030238  jnz     short loc_180030255
0x18003023a  xor     r8d, r8d
0x18003023d  mov     edx, 743h
0x180030242  cmp     rbx, 0DDh
0x180030249  setz    r8b
0x18003024d  xor     r9d, r9d
0x180030250  jmp     loc_18003017F
0x180030255  cmp     rbx, 74h ; 't'
0x180030259  jz      short loc_180030274
0x18003025b  cmp     rbx, 0C0h
0x180030262  jnz     short loc_1800302A2
0x180030264  mov     edx, 74Eh
0x180030269  jmp     loc_1800302F1
0x18003026e  cmp     rbx, 52h ; 'R'
0x180030272  jnz     short loc_18003025B
0x180030274  mov     eax, cs:message
0x18003027a  test    eax, eax
0x18003027c  jnz     short loc_180030291
0x18003027e  lea     rcx, aWmF12ProcComma; "WM_F12_PROC_COMMAND"
0x180030285  call    cs:__imp_RegisterWindowMessageW
0x18003028b  mov     cs:message, eax
0x180030291  mov     r9d, 1
0x180030297  mov     edx, eax
0x180030299  lea     r8d, [r9+0Ah]
0x18003029d  jmp     loc_18003017F
0x1800302a2  cmp     rbx, 70h ; 'p'
0x1800302a6  jnz     short loc_1800302BE
0x1800302a8  xor     r9d, r9d; lParam
0x1800302ab  xor     r8d, r8d; wParam
0x1800302ae  mov     edx, 759h; Msg
0x1800302b3  mov     rcx, rdi; hWnd
0x1800302b6  call    cs:__imp_PostMessageW
0x1800302bc  jmp     short loc_180030300
0x1800302be  test    bpl, bpl
0x1800302c1  jz      short loc_1800302E6
0x1800302c3  test    sil, sil
0x1800302c6  jnz     short loc_1800302D9
0x1800302c8  test    dl, dl
0x1800302ca  jnz     short loc_1800302D9
0x1800302cc  cmp     rbx, 50h ; 'P'
0x1800302d0  jnz     short loc_1800302D9
0x1800302d2  mov     edx, 754h
0x1800302d7  jmp     short loc_1800302F1
0x1800302d9  cmp     rbx, 7Bh ; '{'
0x1800302dd  jnz     short loc_180030300
0x1800302df  mov     edx, 750h
0x1800302e4  jmp     short loc_1800302F1
0x1800302e6  cmp     rbx, 7Bh ; '{'
0x1800302ea  jnz     short loc_180030300
0x1800302ec  mov     edx, 762h; Msg
0x1800302f1  xor     r9d, r9d; lParam
0x1800302f4  xor     r8d, r8d; wParam
0x1800302f7  mov     rcx, rdi; hWnd
0x1800302fa  call    cs:__imp_SendMessageW
0x180030300  xor     al, al
0x180030302  add     rsp, 28h
0x180030306  pop     rdi
0x180030307  pop     rsi
0x180030308  pop     rbp
0x180030309  pop     rbx
0x18003030a  retn
```
