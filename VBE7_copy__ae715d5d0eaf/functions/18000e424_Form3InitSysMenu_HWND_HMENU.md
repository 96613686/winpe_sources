# _Form3InitSysMenu(HWND__ *,HMENU__ *)

- ea: `0x18000e424`
- end: `0x18000e5aa`
- name: `?_Form3InitSysMenu@@YAJPEAUHWND__@@PEAUHMENU__@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(HWND, HMENU)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c098`

## callees

- `0x18000e424`
- `0x180379380`

## import_xrefs

- `USER32!GetWindowLongA` at `0x18000e452`
- `USER32!GetWindowLongA` at `0x18000e452`
- `USER32!RemoveMenu` at `0x18000e4c8`
- `USER32!RemoveMenu` at `0x18000e4f2`
- `USER32!RemoveMenu` at `0x18000e508`
- `USER32!RemoveMenu` at `0x18000e54a`
- `USER32!RemoveMenu` at `0x18000e4c8`
- `USER32!RemoveMenu` at `0x18000e4f2`
- `USER32!RemoveMenu` at `0x18000e508`
- `USER32!RemoveMenu` at `0x18000e54a`
- `USER32!EnableMenuItem` at `0x18000e4ae`
- `USER32!EnableMenuItem` at `0x18000e4dc`
- `USER32!EnableMenuItem` at `0x18000e51b`
- `USER32!EnableMenuItem` at `0x18000e534`
- `USER32!EnableMenuItem` at `0x18000e55e`
- `USER32!EnableMenuItem` at `0x18000e585`
- `USER32!EnableMenuItem` at `0x18000e4ae`
- `USER32!EnableMenuItem` at `0x18000e4dc`
- `USER32!EnableMenuItem` at `0x18000e51b`
- `USER32!EnableMenuItem` at `0x18000e534`
- `USER32!EnableMenuItem` at `0x18000e55e`
- `USER32!EnableMenuItem` at `0x18000e585`
- `USER32!IsZoomed` at `0x18000e45e`
- `USER32!IsZoomed` at `0x18000e45e`
- `USER32!IsIconic` at `0x18000e46a`
- `USER32!IsIconic` at `0x18000e46a`

## pseudocode

```c
__int64 __fastcall _Form3InitSysMenu(HWND a1, HMENU a2)
{
  int v2; // eax
  unsigned int WindowLongA; // r14d
  BOOL v6; // r15d
  BOOL v7; // eax
  UINT v8; // ebx
  BOOL v9; // ebp
  int v10; // esi
  unsigned int v11; // r13d
  int v12; // r12d
  int v13; // r14d
  int v14; // r13d

  WindowLongA = GetWindowLongA(a1, v2 - 48);
  v6 = IsZoomed(a1);
  v7 = IsIconic(a1);
  v8 = 0;
  v9 = v7;
  if ( v6 || (v10 = 1, v7) )
    v10 = 0;
  v11 = WindowLongA;
  v12 = WindowLongA & 0x20000;
  v13 = (WindowLongA >> 18) & 1;
  EnableMenuItem(a2, 0xF060u, Mode_break != 0 ? 3 : 0);
  v14 = v11 & 0x10000;
  if ( v14 )
    EnableMenuItem(a2, 0xF030u, v6 ? 3 : 0);
  else
    RemoveMenu(a2, 0xF030u, 0);
  if ( v12 )
  {
    EnableMenuItem(a2, 0xF020u, v9 ? 3 : 0);
  }
  else
  {
    RemoveMenu(a2, 0xF020u, 0);
    if ( !v14 )
    {
      RemoveMenu(a2, 0xF120u, 0);
      goto LABEL_12;
    }
  }
  EnableMenuItem(a2, 0xF120u, v10 != 0 ? 3 : 0);
LABEL_12:
  if ( v13 )
    EnableMenuItem(a2, 0xF000u, v10 == 0 ? 3 : 0);
  else
    RemoveMenu(a2, 0xF000u, 0);
  if ( v6 || Sys_fWin95Shell && v9 )
    v8 = 3;
  EnableMenuItem(a2, 0xF010u, v8);
  return 0;
}

```

## disassembly

```asm
0x18000e424  mov     [rsp+arg_0], rbx
0x18000e429  mov     [rsp+arg_8], rbp
0x18000e42e  mov     [rsp+arg_10], rsi
0x18000e433  push    rdi
0x18000e434  push    r12
0x18000e436  push    r13
0x18000e438  push    r14
0x18000e43a  push    r15
0x18000e43c  mov     eax, 20h
0x18000e441  call    _alloca_probe
0x18000e446  sub     rsp, rax
0x18000e449  mov     rdi, rdx
0x18000e44c  lea     edx, [rax-30h]; nIndex
0x18000e44f  mov     rbx, rcx
0x18000e452  call    cs:__imp_GetWindowLongA
0x18000e458  mov     rcx, rbx; hWnd
0x18000e45b  mov     r14d, eax
0x18000e45e  call    cs:__imp_IsZoomed
0x18000e464  mov     rcx, rbx; hWnd
0x18000e467  mov     r15d, eax
0x18000e46a  call    cs:__imp_IsIconic
0x18000e470  xor     ebx, ebx
0x18000e472  mov     ebp, eax
0x18000e474  test    r15d, r15d
0x18000e477  jnz     short loc_18000E480
0x18000e479  lea     esi, [rbx+1]
0x18000e47c  test    eax, eax
0x18000e47e  jz      short loc_18000E482
0x18000e480  mov     esi, ebx
0x18000e482  mov     eax, cs:?Mode_break@@3W4BREAKMODE@@A; BREAKMODE Mode_break
0x18000e488  mov     r12d, r14d
0x18000e48b  mov     r13d, r14d
0x18000e48e  shr     r14d, 12h
0x18000e492  and     r12d, 20000h
0x18000e499  mov     edx, 0F060h; uIDEnableItem
0x18000e49e  and     r14d, 1
0x18000e4a2  neg     eax
0x18000e4a4  mov     rcx, rdi; hMenu
0x18000e4a7  sbb     r8d, r8d
0x18000e4aa  and     r8d, 3; uEnable
0x18000e4ae  call    cs:__imp_EnableMenuItem
0x18000e4b4  mov     edx, 0F030h; uIDEnableItem
0x18000e4b9  mov     rcx, rdi; hMenu
0x18000e4bc  and     r13d, 10000h
0x18000e4c3  jnz     short loc_18000E4D0
0x18000e4c5  xor     r8d, r8d; uFlags
0x18000e4c8  call    cs:__imp_RemoveMenu
0x18000e4ce  jmp     short loc_18000E4E2
0x18000e4d0  mov     eax, r15d
0x18000e4d3  neg     eax
0x18000e4d5  sbb     r8d, r8d
0x18000e4d8  and     r8d, 3; uEnable
0x18000e4dc  call    cs:__imp_EnableMenuItem
0x18000e4e2  mov     edx, 0F020h; uIDEnableItem
0x18000e4e7  mov     rcx, rdi; hMenu
0x18000e4ea  test    r12d, r12d
0x18000e4ed  jnz     short loc_18000E510
0x18000e4ef  xor     r8d, r8d; uFlags
0x18000e4f2  call    cs:__imp_RemoveMenu
0x18000e4f8  test    r13d, r13d
0x18000e4fb  jnz     short loc_18000E521
0x18000e4fd  xor     r8d, r8d; uFlags
0x18000e500  mov     edx, 0F120h; uPosition
0x18000e505  mov     rcx, rdi; hMenu
0x18000e508  call    cs:__imp_RemoveMenu
0x18000e50e  jmp     short loc_18000E53A
0x18000e510  mov     eax, ebp
0x18000e512  neg     eax
0x18000e514  sbb     r8d, r8d
0x18000e517  and     r8d, 3; uEnable
0x18000e51b  call    cs:__imp_EnableMenuItem
0x18000e521  mov     eax, esi
0x18000e523  mov     edx, 0F120h; uIDEnableItem
0x18000e528  mov     rcx, rdi; hMenu
0x18000e52b  neg     eax
0x18000e52d  sbb     r8d, r8d
0x18000e530  and     r8d, 3; uEnable
0x18000e534  call    cs:__imp_EnableMenuItem
0x18000e53a  mov     edx, 0F000h; uIDEnableItem
0x18000e53f  mov     rcx, rdi; hMenu
0x18000e542  test    r14d, r14d
0x18000e545  jnz     short loc_18000E552
0x18000e547  xor     r8d, r8d; uFlags
0x18000e54a  call    cs:__imp_RemoveMenu
0x18000e550  jmp     short loc_18000E564
0x18000e552  neg     esi
0x18000e554  sbb     r8d, r8d
0x18000e557  not     r8d
0x18000e55a  and     r8d, 3; uEnable
0x18000e55e  call    cs:__imp_EnableMenuItem
0x18000e564  test    r15d, r15d
0x18000e567  jnz     short loc_18000E575
0x18000e569  cmp     cs:?Sys_fWin95Shell@@3HA, ebx; int Sys_fWin95Shell
0x18000e56f  jz      short loc_18000E57A
0x18000e571  test    ebp, ebp
0x18000e573  jz      short loc_18000E57A
0x18000e575  mov     ebx, 3
0x18000e57a  mov     r8d, ebx; uEnable
0x18000e57d  mov     edx, 0F010h; uIDEnableItem
0x18000e582  mov     rcx, rdi; hMenu
0x18000e585  call    cs:__imp_EnableMenuItem
0x18000e58b  mov     rbx, [rsp+48h+arg_0]
0x18000e590  mov     rbp, [rsp+48h+arg_8]
0x18000e595  mov     rsi, [rsp+48h+arg_10]
0x18000e59a  xor     eax, eax
0x18000e59c  add     rsp, 20h
0x18000e5a0  pop     r15
0x18000e5a2  pop     r14
0x18000e5a4  pop     r13
0x18000e5a6  pop     r12
0x18000e5a8  pop     rdi
0x18000e5a9  retn
```
