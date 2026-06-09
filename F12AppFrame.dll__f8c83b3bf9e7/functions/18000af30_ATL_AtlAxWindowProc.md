# ATL::AtlAxWindowProc

- ea: `0x18000af30`
- end: `0x18000b28a`
- name: `ATL::AtlAxWindowProc`
- size: `858`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001800`
- `0x180005704`
- `0x18000af30`
- `0x180011ce0`
- `0x180032a50`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b203`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b255`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b203`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b255`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b05d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b05d`
- `KERNEL32!GlobalUnlock` at `0x18000b10c`
- `KERNEL32!GlobalUnlock` at `0x18000b10c`
- `KERNEL32!GlobalLock` at `0x18000b0ee`
- `KERNEL32!GlobalLock` at `0x18000b0ee`
- `KERNEL32!GlobalAlloc` at `0x18000b0d9`
- `KERNEL32!GlobalAlloc` at `0x18000b0d9`
- `ole32!CreateStreamOnHGlobal` at `0x18000b11e`
- `ole32!CreateStreamOnHGlobal` at `0x18000b11e`
- `ole32!OleInitialize` at `0x18000aff3`
- `ole32!OleInitialize` at `0x18000aff3`
- `ole32!OleUninitialize` at `0x18000afe6`
- `ole32!OleUninitialize` at `0x18000afe6`
- `USER32!SetWindowLongPtrW` at `0x18000b21a`
- `USER32!SetWindowLongPtrW` at `0x18000b21a`
- `USER32!GetWindowLongPtrW` at `0x18000afc9`
- `USER32!GetWindowLongPtrW` at `0x18000afc9`
- `USER32!DefWindowProcW` at `0x18000b267`
- `USER32!DefWindowProcW` at `0x18000b267`
- `USER32!SetWindowLongW` at `0x18000afb9`
- `USER32!SetWindowLongW` at `0x18000afb9`
- `USER32!GetWindowLongW` at `0x18000af91`
- `USER32!GetWindowLongW` at `0x18000afa9`
- `USER32!GetWindowLongW` at `0x18000af91`
- `USER32!GetWindowLongW` at `0x18000afa9`
- `USER32!SetWindowTextW` at `0x18000b0a1`
- `USER32!SetWindowTextW` at `0x18000b0a1`
- `USER32!GetWindowTextW` at `0x18000b091`
- `USER32!GetWindowTextW` at `0x18000b091`
- `USER32!GetWindowTextLengthW` at `0x18000affc`
- `USER32!GetWindowTextLengthW` at `0x18000affc`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
LRESULT __fastcall ATL::AtlAxWindowProc(HWND hWnd, UINT Msg, WPARAM wParam, HWND lParam)
{
  LONG WindowLongW; // eax
  LONG_PTR WindowLongPtrW; // rax
  int v10; // ebx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rdx
  __int64 v13; // rax
  void *v14; // rsp
  WCHAR *v15; // rdi
  WCHAR *v16; // rax
  int v18; // eax
  unsigned __int16 *v19; // rcx
  SIZE_T v20; // rbx
  HGLOBAL v21; // rax
  void *v22; // r15
  ATL::Checked *v23; // rax
  WCHAR *v24; // rcx
  bool v25; // zf
  __int64 v26; // rbx
  __int64 v27; // [rsp+0h] [rbp-30h] BYREF
  __int64 v28; // [rsp+20h] [rbp-10h]
  WCHAR String[4]; // [rsp+30h] [rbp+0h] BYREF
  __int64 v30; // [rsp+38h] [rbp+8h]
  LONG_PTR dwNewLong[3]; // [rsp+40h] [rbp+10h] BYREF

  if ( Msg == 1 )
  {
    OleInitialize(0);
    v10 = GetWindowTextLengthW(hWnd) + 1;
    v11 = 2LL * v10;
    v12 = (v11 + 16) & -(__int64)(v11 < v11 + 16);
    if ( v12 )
    {
      if ( v12 > 0x400 )
      {
        v16 = (WCHAR *)malloc((v11 + 16) & -(__int64)(v11 < v11 + 16));
        v15 = v16;
        if ( !v16 )
          goto LABEL_20;
        *(_DWORD *)v16 = 56797;
        goto LABEL_18;
      }
      v13 = v12 + 15;
      if ( v12 + 15 < v12 )
        v13 = 0xFFFFFFFFFFFFFF0LL;
      v14 = alloca(v13 & 0xFFFFFFFFFFFFFFF0uLL);
      v15 = String;
      if ( &v27 != (__int64 *)-48LL )
      {
        wcscpy(String, L"쳌");
LABEL_18:
        v15 += 8;
      }
    }
    else
    {
      v15 = 0;
    }
LABEL_20:
    dwNewLong[1] = (LONG_PTR)v15;
    if ( !v15 )
      return -1;
    GetWindowTextW(hWnd, v15, v10);
    SetWindowTextW(hWnd, &::String);
    dwNewLong[0] = 0;
    v18 = 0;
    if ( lParam && (v19 = *(unsigned __int16 **)lParam) != 0 )
    {
      v18 = *v19;
      v20 = *v19;
    }
    else
    {
      v20 = 0;
    }
    *(_QWORD *)String = 0;
    if ( v18 )
    {
      v21 = GlobalAlloc(0x42u, v20);
      v22 = v21;
      if ( !v21 )
      {
        if ( *(_QWORD *)String )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
        v24 = v15 - 8;
        v25 = *((_DWORD *)v15 - 4) == 56797;
LABEL_44:
        if ( v25 )
          free(v24);
        return -1;
      }
      v23 = (ATL::Checked *)GlobalLock(v21);
      ATL::Checked::memcpy_s(v23, (void *)v20, *(_QWORD *)lParam + 2LL, (const void *)v20, v28);
      GlobalUnlock(v22);
      CreateStreamOnHGlobal(v22, 1, (LPSTREAM *)String);
    }
    dwNewLong[2] = 0;
    v30 = 0;
    if ( (int)AtlAxCreateControlLic(v15, 0) >= 0 )
    {
      v26 = v30;
      if ( (**(int (__fastcall ***)(__int64, GUID *, LONG_PTR *))v30)(
             v30,
             &GUID_b6ea2050_048a_11d1_82b9_00c04fb9942e,
             dwNewLong) >= 0 )
      {
        SetWindowLongPtrW(hWnd, -21, dwNewLong[0]);
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        if ( *(_QWORD *)String )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
        if ( *((_DWORD *)v15 - 4) == 56797 )
          free(v15 - 8);
        return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
      }
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      if ( *(_QWORD *)String )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
    }
    else
    {
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      if ( *(_QWORD *)String )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
    }
    v24 = v15 - 8;
    v25 = *((_DWORD *)v15 - 4) == 56797;
    goto LABEL_44;
  }
  if ( Msg == 130 )
  {
    WindowLongPtrW = GetWindowLongPtrW(hWnd, -21);
    if ( WindowLongPtrW )
      (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)WindowLongPtrW + 16LL))(WindowLongPtrW);
    OleUninitialize();
  }
  else if ( Msg == 528 && (_DWORD)wParam == 1 && (GetWindowLongW(lParam, -20) & 0x10000) != 0 )
  {
    WindowLongW = GetWindowLongW(hWnd, -20);
    SetWindowLongW(hWnd, -20, WindowLongW | 0x10000);
  }
  return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
}

```

## disassembly

```asm
0x18000af30  push    rbp
0x18000af32  push    rbx
0x18000af33  push    rsi
0x18000af34  push    rdi
0x18000af35  push    r12
0x18000af37  push    r13
0x18000af39  push    r14
0x18000af3b  push    r15
0x18000af3d  sub     rsp, 68h
0x18000af41  lea     rbp, [rsp+30h]
0x18000af46  mov     rax, cs:__security_cookie
0x18000af4d  xor     rax, rbp
0x18000af50  mov     [rbp+70h+var_48], rax
0x18000af54  mov     r14, r9
0x18000af57  mov     r12, r8
0x18000af5a  mov     r13d, edx
0x18000af5d  mov     rsi, rcx
0x18000af60  mov     eax, edx
0x18000af62  sub     eax, 1
0x18000af65  jz      loc_18000AFF1
0x18000af6b  sub     eax, 81h
0x18000af70  jz      short loc_18000AFC4
0x18000af72  cmp     eax, 18Eh
0x18000af77  jnz     loc_18000B25B
0x18000af7d  cmp     r12d, 1
0x18000af81  jnz     loc_18000B25B
0x18000af87  lea     ebx, [r12-15h]
0x18000af8c  mov     edx, ebx; nIndex
0x18000af8e  mov     rcx, r9; hWnd
0x18000af91  call    cs:__imp_GetWindowLongW
0x18000af97  mov     edi, 10000h
0x18000af9c  test    edi, eax
0x18000af9e  jz      loc_18000B25B
0x18000afa4  mov     edx, ebx; nIndex
0x18000afa6  mov     rcx, rsi; hWnd
0x18000afa9  call    cs:__imp_GetWindowLongW
0x18000afaf  or      eax, edi
0x18000afb1  mov     r8d, eax; dwNewLong
0x18000afb4  mov     edx, ebx; nIndex
0x18000afb6  mov     rcx, rsi; hWnd
0x18000afb9  call    cs:__imp_SetWindowLongW
0x18000afbf  jmp     loc_18000B25B
0x18000afc4  mov     edx, 0FFFFFFEBh; nIndex
0x18000afc9  call    cs:__imp_GetWindowLongPtrW
0x18000afcf  mov     rdx, rax
0x18000afd2  test    rax, rax
0x18000afd5  jz      short loc_18000AFE6
0x18000afd7  mov     rcx, [rax]
0x18000afda  mov     rax, [rcx+10h]
0x18000afde  mov     rcx, rdx
0x18000afe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afe6  call    cs:__imp_OleUninitialize
0x18000afec  jmp     loc_18000B25B
0x18000aff1  xor     ecx, ecx; pvReserved
0x18000aff3  call    cs:__imp_OleInitialize
0x18000aff9  mov     rcx, rsi; hWnd
0x18000affc  call    cs:__imp_GetWindowTextLengthW
0x18000b002  lea     ebx, [rax+1]
0x18000b005  movsxd  rax, ebx
0x18000b008  add     rax, rax
0x18000b00b  lea     rcx, [rax+10h]
0x18000b00f  cmp     rax, rcx
0x18000b012  sbb     rdx, rdx
0x18000b015  mov     r15d, 0DDDDh
0x18000b01b  and     rdx, rcx
0x18000b01e  jz      short loc_18000B074
0x18000b020  cmp     rdx, 400h
0x18000b027  ja      short loc_18000B05A
0x18000b029  lea     rax, [rdx+0Fh]
0x18000b02d  cmp     rax, rdx
0x18000b030  ja      short loc_18000B03C
0x18000b032  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000b03c  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000b040  call    _alloca_probe
0x18000b045  sub     rsp, rax
0x18000b048  lea     rdi, [rsp+0A0h+String]
0x18000b04d  test    rdi, rdi
0x18000b050  jz      short loc_18000B076
0x18000b052  mov     dword ptr [rdi], 0CCCCh
0x18000b058  jmp     short loc_18000B06E
0x18000b05a  mov     rcx, rdx; Size
0x18000b05d  call    cs:__imp_malloc
0x18000b063  mov     rdi, rax
0x18000b066  test    rax, rax
0x18000b069  jz      short loc_18000B076
0x18000b06b  mov     [rax], r15d
0x18000b06e  add     rdi, 10h
0x18000b072  jmp     short loc_18000B076
0x18000b074  xor     edi, edi
0x18000b076  mov     [rbp+70h+var_58], rdi
0x18000b07a  test    rdi, rdi
0x18000b07d  jnz     short loc_18000B088
0x18000b07f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b083  jmp     loc_18000B26D
0x18000b088  mov     r8d, ebx; nMaxCount
0x18000b08b  mov     rdx, rdi; lpString
0x18000b08e  mov     rcx, rsi; hWnd
0x18000b091  call    cs:__imp_GetWindowTextW
0x18000b097  lea     rdx, String; lpString
0x18000b09e  mov     rcx, rsi; hWnd
0x18000b0a1  call    cs:__imp_SetWindowTextW
0x18000b0a7  mov     [rbp+70h+dwNewLong], 0
0x18000b0af  xor     eax, eax
0x18000b0b1  test    r14, r14
0x18000b0b4  jz      short loc_18000B0C5
0x18000b0b6  mov     rcx, [r14]
0x18000b0b9  test    rcx, rcx
0x18000b0bc  jz      short loc_18000B0C5
0x18000b0be  movzx   eax, word ptr [rcx]
0x18000b0c1  mov     ebx, eax
0x18000b0c3  jmp     short loc_18000B0C7
0x18000b0c5  xor     ebx, ebx
0x18000b0c7  xor     r8d, r8d
0x18000b0ca  mov     qword ptr [rbp+70h+String], r8
0x18000b0ce  test    eax, eax
0x18000b0d0  jz      short loc_18000B12E
0x18000b0d2  mov     rdx, rbx; dwBytes
0x18000b0d5  lea     ecx, [r8+42h]; uFlags
0x18000b0d9  call    cs:__imp_GlobalAlloc
0x18000b0df  mov     r15, rax
0x18000b0e2  test    rax, rax
0x18000b0e5  jz      loc_18000B188
0x18000b0eb  mov     rcx, rax; hMem
0x18000b0ee  call    cs:__imp_GlobalLock
0x18000b0f4  mov     r8, [r14]
0x18000b0f7  add     r8, 2; unsigned __int64
0x18000b0fb  mov     r9, rbx; void *
0x18000b0fe  mov     rdx, rbx; void *
0x18000b101  mov     rcx, rax; this
0x18000b104  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18000b109  mov     rcx, r15; hMem
0x18000b10c  call    cs:__imp_GlobalUnlock
0x18000b112  lea     r8, [rbp+70h+String]; ppstm
0x18000b116  mov     edx, 1; fDeleteOnRelease
0x18000b11b  mov     rcx, r15; hGlobal
0x18000b11e  call    cs:__imp_CreateStreamOnHGlobal
0x18000b124  mov     r8, qword ptr [rbp+70h+String]
0x18000b128  mov     r15d, 0DDDDh
0x18000b12e  mov     [rbp+70h+var_50], 0
0x18000b136  mov     [rbp+70h+var_68], 0
0x18000b13e  mov     [rsp+0A0h+var_80], 0; __int64
0x18000b147  lea     r9, [rbp+70h+var_68]
0x18000b14b  mov     rdx, rsi
0x18000b14e  mov     rcx, rdi; psz
0x18000b151  call    AtlAxCreateControlLic
0x18000b156  test    eax, eax
0x18000b158  jns     short loc_18000B1AA
0x18000b15a  mov     rcx, [rbp+70h+var_68]
0x18000b15e  test    rcx, rcx
0x18000b161  jz      short loc_18000B170
0x18000b163  mov     rax, [rcx]
0x18000b166  mov     rax, [rax+10h]
0x18000b16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b16f  nop
0x18000b170  mov     rcx, qword ptr [rbp+70h+String]
0x18000b174  test    rcx, rcx
0x18000b177  jz      short loc_18000B186
0x18000b179  mov     rax, [rcx]
0x18000b17c  mov     rax, [rax+10h]
0x18000b180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b185  nop
0x18000b186  jmp     short loc_18000B1F6
0x18000b188  mov     rcx, qword ptr [rbp+70h+String]
0x18000b18c  test    rcx, rcx
0x18000b18f  jz      short loc_18000B19E
0x18000b191  mov     rax, [rcx]
0x18000b194  mov     rax, [rax+10h]
0x18000b198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b19d  nop
0x18000b19e  lea     rcx, [rdi-10h]
0x18000b1a2  cmp     dword ptr [rcx], 0DDDDh
0x18000b1a8  jmp     short loc_18000B1FD
0x18000b1aa  mov     rbx, [rbp+70h+var_68]
0x18000b1ae  mov     rax, [rbx]
0x18000b1b1  lea     r8, [rbp+70h+dwNewLong]
0x18000b1b5  lea     rdx, _GUID_b6ea2050_048a_11d1_82b9_00c04fb9942e
0x18000b1bc  mov     rcx, rbx
0x18000b1bf  mov     rax, [rax]
0x18000b1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1c7  test    eax, eax
0x18000b1c9  jns     short loc_18000B20E
0x18000b1cb  test    rbx, rbx
0x18000b1ce  jz      short loc_18000B1E0
0x18000b1d0  mov     rax, [rbx]
0x18000b1d3  mov     rcx, rbx
0x18000b1d6  mov     rax, [rax+10h]
0x18000b1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1df  nop
0x18000b1e0  mov     rcx, qword ptr [rbp+70h+String]
0x18000b1e4  test    rcx, rcx
0x18000b1e7  jz      short loc_18000B1F6
0x18000b1e9  mov     rax, [rcx]
0x18000b1ec  mov     rax, [rax+10h]
0x18000b1f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1f5  nop
0x18000b1f6  lea     rcx, [rdi-10h]; Block
0x18000b1fa  cmp     [rcx], r15d
0x18000b1fd  jnz     loc_18000B07F
0x18000b203  call    cs:__imp_free
0x18000b209  jmp     loc_18000B07F
0x18000b20e  mov     r8, [rbp+70h+dwNewLong]; dwNewLong
0x18000b212  mov     edx, 0FFFFFFEBh; nIndex
0x18000b217  mov     rcx, rsi; hWnd
0x18000b21a  call    cs:__imp_SetWindowLongPtrW
0x18000b220  nop
0x18000b221  test    rbx, rbx
0x18000b224  jz      short loc_18000B236
0x18000b226  mov     rax, [rbx]
0x18000b229  mov     rcx, rbx
0x18000b22c  mov     rax, [rax+10h]
0x18000b230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b235  nop
0x18000b236  mov     rcx, qword ptr [rbp+70h+String]
0x18000b23a  test    rcx, rcx
0x18000b23d  jz      short loc_18000B24C
0x18000b23f  mov     rax, [rcx]
0x18000b242  mov     rax, [rax+10h]
0x18000b246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b24b  nop
0x18000b24c  lea     rcx, [rdi-10h]; Block
0x18000b250  cmp     [rcx], r15d
0x18000b253  jnz     short loc_18000B25B
0x18000b255  call    cs:__imp_free
0x18000b25b  mov     r9, r14; lParam
0x18000b25e  mov     r8, r12; wParam
0x18000b261  mov     edx, r13d; Msg
0x18000b264  mov     rcx, rsi; hWnd
0x18000b267  call    cs:__imp_DefWindowProcW
0x18000b26d  mov     rcx, [rbp+70h+var_48]
0x18000b271  xor     rcx, rbp; StackCookie
0x18000b274  call    __security_check_cookie
0x18000b279  lea     rsp, [rbp+38h]
0x18000b27d  pop     r15
0x18000b27f  pop     r14
0x18000b281  pop     r13
0x18000b283  pop     r12
0x18000b285  pop     rdi
0x18000b286  pop     rsi
0x18000b287  pop     rbx
0x18000b288  pop     rbp
0x18000b289  retn
```
