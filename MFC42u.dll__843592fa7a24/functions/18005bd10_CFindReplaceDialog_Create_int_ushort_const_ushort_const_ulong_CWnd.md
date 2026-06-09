# CFindReplaceDialog::Create(int,ushort const *,ushort const *,ulong,CWnd *)

- ea: `0x18005bd10`
- end: `0x18005be13`
- name: `?Create@CFindReplaceDialog@@QEAAHHPEBG0KPEAVCWnd@@@Z`
- size: `259`
- prototype: `__int64 __usercall@<rax>(CFindReplaceDialog *__hidden this@<rcx>, int@<edx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned int, struct CWnd *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002fa00`
- `0x180030270`

## callees

- `0x1800067a0`
- `0x180006810`
- `0x180014a00`
- `0x18005bd10`
- `0x1800d7010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18005bda6`
- `msvcrt!wcscpy_s` at `0x18005bdba`
- `msvcrt!wcscpy_s` at `0x18005bda6`
- `msvcrt!wcscpy_s` at `0x18005bdba`
- `COMDLG32!ReplaceTextW` at `0x18005bdd8`
- `COMDLG32!ReplaceTextW` at `0x18005bdd8`
- `COMDLG32!FindTextW` at `0x18005bdd0`
- `COMDLG32!FindTextW` at `0x18005bdd0`

## pseudocode

```c
_BOOL8 __fastcall CFindReplaceDialog::Create(
        CFindReplaceDialog *this,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        struct CWnd *a6)
{
  struct tagFINDREPLACEW *v6; // rdi
  wchar_t *v7; // r15
  struct CWnd *MainWnd; // rax
  int v11; // r14d
  HWND TextW; // rax
  HWND v14; // rdi

  v6 = (struct tagFINDREPLACEW *)((char *)this + 192);
  v7 = (wchar_t *)((char *)this + 528);
  *((_WORD *)this + 120) = 128;
  *((_DWORD *)this + 54) |= a5;
  MainWnd = a6;
  *((_DWORD *)this + 32) = 28683 - ((_DWORD)a2 != 0);
  *((_QWORD *)this + 29) = (char *)this + 528;
  v11 = a2;
  *((_WORD *)this + 121) = 128;
  if ( a6 || (MainWnd = AfxGetMainWnd()) != 0 )
    MainWnd = (struct CWnd *)*((_QWORD *)MainWnd + 8);
  v6->hwndOwner = (HWND)MainWnd;
  if ( a3 )
    wcscpy_s((wchar_t *)this + 136, 0x80u, a3);
  if ( a4 )
    wcscpy_s(v7, 0x80u, a4);
  AfxHookWindowCreate(this, a2);
  if ( v11 )
    TextW = FindTextW(v6);
  else
    TextW = ReplaceTextW(v6);
  v14 = TextW;
  if ( !(unsigned int)AfxUnhookWindowCreate() )
    (*(void (__fastcall **)(CFindReplaceDialog *))(*(_QWORD *)this + 344LL))(this);
  return v14 != 0;
}

```

## disassembly

```asm
0x18005bd10  push    rbx
0x18005bd12  push    rbp
0x18005bd13  push    rsi
0x18005bd14  push    rdi
0x18005bd15  push    r12
0x18005bd17  push    r14
0x18005bd19  push    r15
0x18005bd1b  sub     rsp, 20h
0x18005bd1f  mov     eax, edx
0x18005bd21  lea     rdi, [rcx+0C0h]
0x18005bd28  neg     eax
0x18005bd2a  lea     r15, [rcx+210h]
0x18005bd31  mov     eax, [rsp+58h+arg_20]
0x18005bd38  mov     r12d, 80h
0x18005bd3e  sbb     r10d, r10d
0x18005bd41  mov     [rdi+30h], r12w
0x18005bd46  or      [rcx+0D8h], eax
0x18005bd4c  add     r10d, 700Bh
0x18005bd53  mov     rax, [rsp+58h+arg_28]
0x18005bd5b  mov     rsi, r9
0x18005bd5e  mov     [rcx+80h], r10d
0x18005bd65  mov     rbp, r8
0x18005bd68  mov     [rcx+0E8h], r15
0x18005bd6f  mov     r14d, edx
0x18005bd72  mov     [rcx+0F2h], r12w
0x18005bd7a  mov     rbx, rcx
0x18005bd7d  test    rax, rax
0x18005bd80  jnz     short loc_18005BD8C
0x18005bd82  call    ?AfxGetMainWnd@@YAPEAVCWnd@@XZ; AfxGetMainWnd(void)
0x18005bd87  test    rax, rax
0x18005bd8a  jz      short loc_18005BD90
0x18005bd8c  mov     rax, [rax+40h]
0x18005bd90  mov     [rdi+8], rax
0x18005bd94  test    rbp, rbp
0x18005bd97  jz      short loc_18005BDAC
0x18005bd99  lea     rcx, [rbx+110h]; Destination
0x18005bda0  mov     r8, rbp; Source
0x18005bda3  mov     rdx, r12; SizeInWords
0x18005bda6  call    cs:__imp_wcscpy_s
0x18005bdac  test    rsi, rsi
0x18005bdaf  jz      short loc_18005BDC0
0x18005bdb1  mov     r8, rsi; Source
0x18005bdb4  mov     rdx, r12; SizeInWords
0x18005bdb7  mov     rcx, r15; Destination
0x18005bdba  call    cs:__imp_wcscpy_s
0x18005bdc0  mov     rcx, rbx; struct CWnd *
0x18005bdc3  call    ?AfxHookWindowCreate@@YAXPEAVCWnd@@@Z; AfxHookWindowCreate(CWnd *)
0x18005bdc8  mov     rcx, rdi; LPFINDREPLACEW
0x18005bdcb  test    r14d, r14d
0x18005bdce  jz      short loc_18005BDD8
0x18005bdd0  call    cs:__imp_FindTextW
0x18005bdd6  jmp     short loc_18005BDDE
0x18005bdd8  call    cs:__imp_ReplaceTextW
0x18005bdde  mov     rdi, rax
0x18005bde1  call    ?AfxUnhookWindowCreate@@YAHXZ; AfxUnhookWindowCreate(void)
0x18005bde6  test    eax, eax
0x18005bde8  jnz     short loc_18005BDFC
0x18005bdea  mov     rax, [rbx]
0x18005bded  mov     rcx, rbx
0x18005bdf0  mov     rax, [rax+158h]
0x18005bdf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdfc  xor     eax, eax
0x18005bdfe  test    rdi, rdi
0x18005be01  setnz   al
0x18005be04  add     rsp, 20h
0x18005be08  pop     r15
0x18005be0a  pop     r14
0x18005be0c  pop     r12
0x18005be0e  pop     rdi
0x18005be0f  pop     rsi
0x18005be10  pop     rbp
0x18005be11  pop     rbx
0x18005be12  retn
```
