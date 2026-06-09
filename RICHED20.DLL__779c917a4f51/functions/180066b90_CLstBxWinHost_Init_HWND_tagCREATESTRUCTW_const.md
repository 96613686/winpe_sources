# CLstBxWinHost::Init(HWND__ *,tagCREATESTRUCTW const *)

- ea: `0x180066b90`
- end: `0x180066e73`
- name: `?Init@CLstBxWinHost@@UEAAHPEAUHWND__@@PEBUtagCREATESTRUCTW@@@Z`
- size: `739`
- prototype: `__int64 __fastcall(CLstBxWinHost *__hidden this, HWND hWnd, const struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18005c14c`
- `0x18005ff60`
- `0x180066b90`
- `0x1800908dc`
- `0x18009110a`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x180066bd9`
- `USER32!SetWindowLongPtrW` at `0x180066bd9`

## pseudocode

```c
__int64 __fastcall CLstBxWinHost::Init(CLstBxWinHost *this, HWND hWnd, const struct tagCREATESTRUCTW *a3)
{
  LONG style; // eax
  LPVOID lpCreateParams; // rcx
  int *v8; // rdi
  int v9; // ecx
  __int64 result; // rax
  int v11; // r8d
  HWND v12; // rcx
  int v13; // r8d
  unsigned int v14; // edx
  int v15; // ecx
  unsigned int v16; // ecx
  int v17; // eax
  unsigned int v18; // edx
  int v19; // eax
  CTxtEdit *v20; // rcx
  bool v21; // zf
  int v22; // eax
  __int64 v23; // rcx
  int v24; // [rsp+30h] [rbp-C8h] BYREF
  int v25; // [rsp+34h] [rbp-C4h]
  __int16 v26; // [rsp+3Ah] [rbp-BEh]
  __int16 v27; // [rsp+48h] [rbp-B0h]

  if ( !a3->lpszClass )
    return 0;
  if ( hWnd )
    SetWindowLongPtrW(hWnd, 0, (LONG_PTR)this);
  *((_DWORD *)this + 13) |= 0x20u;
  *((_QWORD *)this + 2) = hWnd;
  *((_QWORD *)this + 3) = a3->hwndParent;
  *((_DWORD *)this + 12) = a3->dwExStyle;
  style = a3->style;
  *((_DWORD *)this + 11) = style;
  if ( (style & 0x8000) != 0 )
  {
    if ( a3->hMenu != (HMENU)1000 )
      return 0xFFFFFFFFLL;
    lpCreateParams = a3->lpCreateParams;
    if ( !a3->lpCreateParams )
      return 0xFFFFFFFFLL;
    *((_QWORD *)this + 286) = lpCreateParams;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)lpCreateParams + 8LL))(lpCreateParams);
    v8 = (int *)((char *)this + 128);
    *((_DWORD *)this + 33) = 8;
    *((_DWORD *)this + 32) |= 0x20u;
    v9 = *((_DWORD *)this + 32);
  }
  else
  {
    v8 = (int *)((char *)this + 128);
    *((_DWORD *)this + 32) &= ~0x20u;
    v9 = *((_DWORD *)this + 32);
    if ( (style & 0x800) != 0 )
    {
      *((_DWORD *)this + 33) = 3;
    }
    else if ( (style & 8) != 0 )
    {
      *((_DWORD *)this + 33) = 2;
    }
    else
    {
      v9 |= 0x20u;
      *((_DWORD *)this + 33) = 1;
      *v8 = v9;
    }
  }
  v11 = *((_DWORD *)this + 11);
  *v8 = v9 ^ ((unsigned __int8)v9 ^ (unsigned __int8)(16 * v11)) & 0x10;
  if ( (v11 & 0x40) == 0 )
  {
    v12 = (HWND)*((_QWORD *)this + 2);
    v13 = v11 | 0x40;
    *((_DWORD *)this + 11) = v13;
    CW32System::SetWindowLong(v12, (int)hWnd, v13);
  }
  *v8 &= ~8u;
  v14 = *((_DWORD *)this + 11);
  v15 = *v8;
  if ( (v14 & 0x1000) != 0 )
  {
    v15 |= 8u;
    *v8 = v15;
    v14 |= 0x2000u;
  }
  *((_DWORD *)this + 13) &= ~1u;
  v16 = v15 & 0xFFFFFFFA | (v14 >> 6) & 4 | (v14 >> 4) & 1;
  v17 = v14 & 2;
  v18 = v14 & 0xFFEFFFFF;
  *((_DWORD *)this + 11) = v18;
  *v8 = v17 | v16 & 0xFFFFFFFD;
  *((_DWORD *)this + 13) |= (v18 >> 23) & 1;
  v19 = *((_DWORD *)this + 13);
  if ( (*((_DWORD *)this + 12) & 0x200) != 0 )
  {
    v19 |= 1u;
    *((_DWORD *)this + 13) = v19;
  }
  if ( (v18 & 0x8000000) != 0 )
    *((_DWORD *)this + 13) = v19 | 0x800;
  if ( (int)CTxtWinHost::CreateTextServices(this) < 0 )
    return 0;
  v20 = (CTxtEdit *)*((_QWORD *)this + 4);
  *((_WORD *)this + 51) = 0;
  CTxtEdit::HandleSetUndoLimit(v20, 0);
  memset_0(&v24, 0, 0x9Cu);
  v21 = (*((_DWORD *)this + 12) & 0x1000) == 0;
  v22 = 0;
  v25 = 0;
  if ( !v21 )
  {
    v22 = 8;
    v27 = 2;
    v25 = 8;
  }
  if ( (*((_DWORD *)this + 12) & 0x2000) != 0 )
  {
    v22 |= 0x10000u;
    v26 = 1;
    v25 = v22;
  }
  if ( v22 )
  {
    v23 = *((_QWORD *)this + 4);
    v24 = 188;
    (*(void (__fastcall **)(__int64, __int64, __int64, int *, _QWORD))(*(_QWORD *)v23 + 24LL))(v23, 1095, 4, &v24, 0);
  }
  (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64, _QWORD))(**((_QWORD **)this + 4) + 24LL))(
    *((_QWORD *)this + 4),
    1228,
    4,
    4,
    0);
  (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 4) + 24LL))(
    *((_QWORD *)this + 4),
    1228,
    0,
    128,
    0);
  (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 4) + 24LL))(
    *((_QWORD *)this + 4),
    1144,
    0,
    50,
    0);
  (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 24LL))(
    *((_QWORD *)this + 4),
    1192,
    0,
    0,
    0);
  result = 1;
  *(_QWORD *)((char *)this + 60) = 0;
  *(_QWORD *)((char *)this + 68) = 0;
  return result;
}

```

## disassembly

```asm
0x180066b90  mov     [rsp+arg_10], rbx
0x180066b95  mov     [rsp+arg_18], rbp
0x180066b9a  push    rsi
0x180066b9b  push    rdi
0x180066b9c  push    r13
0x180066b9e  sub     rsp, 0E0h
0x180066ba5  mov     rax, cs:__security_cookie
0x180066bac  xor     rax, rsp
0x180066baf  mov     [rsp+0F8h+var_28], rax
0x180066bb7  xor     ebp, ebp
0x180066bb9  mov     rdi, r8
0x180066bbc  mov     rsi, rdx
0x180066bbf  mov     rbx, rcx
0x180066bc2  cmp     [r8+40h], rbp
0x180066bc6  jz      loc_180066E49
0x180066bcc  test    rdx, rdx
0x180066bcf  jz      short loc_180066BDF
0x180066bd1  mov     r8, rcx; dwNewLong
0x180066bd4  xor     edx, edx; nIndex
0x180066bd6  mov     rcx, rsi; hWnd
0x180066bd9  call    cs:__imp_SetWindowLongPtrW
0x180066bdf  or      dword ptr [rbx+34h], 20h
0x180066be3  mov     [rbx+10h], rsi
0x180066be7  mov     esi, 1
0x180066bec  mov     rax, [rdi+18h]
0x180066bf0  mov     [rbx+18h], rax
0x180066bf4  mov     eax, [rdi+48h]
0x180066bf7  mov     [rbx+30h], eax
0x180066bfa  lea     r13d, [rsi+1]
0x180066bfe  mov     eax, [rdi+30h]
0x180066c01  mov     [rbx+2Ch], eax
0x180066c04  bt      eax, 0Fh
0x180066c08  jnb     short loc_180066C4F
0x180066c0a  cmp     qword ptr [rdi+10h], 3E8h
0x180066c12  jnz     short loc_180066C47
0x180066c14  mov     rcx, [rdi]
0x180066c17  test    rcx, rcx
0x180066c1a  jz      short loc_180066C47
0x180066c1c  mov     [rbx+8F0h], rcx
0x180066c23  mov     rax, [rcx]
0x180066c26  mov     rax, [rax+8]
0x180066c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066c2f  lea     rdi, [rbx+80h]
0x180066c36  mov     dword ptr [rbx+84h], 8
0x180066c40  or      dword ptr [rdi], 20h
0x180066c43  mov     ecx, [rdi]
0x180066c45  jmp     short loc_180066C85
0x180066c47  or      eax, 0FFFFFFFFh
0x180066c4a  jmp     loc_180066E4B
0x180066c4f  lea     rdi, [rbx+80h]
0x180066c56  and     dword ptr [rdi], 0FFFFFFDFh
0x180066c59  mov     ecx, [rdi]
0x180066c5b  bt      eax, 0Bh
0x180066c5f  jnb     short loc_180066C6D
0x180066c61  mov     dword ptr [rbx+84h], 3
0x180066c6b  jmp     short loc_180066C85
0x180066c6d  test    al, 8
0x180066c6f  jz      short loc_180066C7A
0x180066c71  mov     [rbx+84h], r13d
0x180066c78  jmp     short loc_180066C85
0x180066c7a  or      ecx, 20h
0x180066c7d  mov     [rbx+84h], esi
0x180066c83  mov     [rdi], ecx
0x180066c85  mov     r8d, [rbx+2Ch]
0x180066c89  mov     eax, r8d
0x180066c8c  shl     eax, 4
0x180066c8f  xor     eax, ecx
0x180066c91  and     eax, 10h
0x180066c94  xor     eax, ecx
0x180066c96  mov     [rdi], eax
0x180066c98  test    r8b, 40h
0x180066c9c  jnz     short loc_180066CAF
0x180066c9e  mov     rcx, [rbx+10h]; HWND
0x180066ca2  or      r8d, 40h; int
0x180066ca6  mov     [rbx+2Ch], r8d
0x180066caa  call    ?SetWindowLong@CW32System@@SAJPEAUHWND__@@HJ@Z; CW32System::SetWindowLong(HWND__ *,int,long)
0x180066caf  and     dword ptr [rdi], 0FFFFFFF7h
0x180066cb2  mov     edx, [rbx+2Ch]
0x180066cb5  mov     ecx, [rdi]
0x180066cb7  bt      edx, 0Ch
0x180066cbb  jnb     short loc_180066CC6
0x180066cbd  or      ecx, 8
0x180066cc0  mov     [rdi], ecx
0x180066cc2  bts     edx, 0Dh
0x180066cc6  and     ecx, 0FFFFFFFBh
0x180066cc9  mov     eax, edx
0x180066ccb  shr     eax, 6
0x180066cce  mov     r8d, 0FFFFFFFEh
0x180066cd4  and     [rbx+34h], r8d
0x180066cd8  and     eax, 4
0x180066cdb  or      eax, ecx
0x180066cdd  mov     ecx, edx
0x180066cdf  and     eax, r8d
0x180066ce2  shr     ecx, 4
0x180066ce5  and     ecx, esi
0x180066ce7  or      ecx, eax
0x180066ce9  mov     eax, edx
0x180066ceb  and     eax, r13d
0x180066cee  btr     edx, 14h
0x180066cf2  and     ecx, 0FFFFFFFDh
0x180066cf5  mov     [rbx+2Ch], edx
0x180066cf8  or      ecx, eax
0x180066cfa  mov     eax, edx
0x180066cfc  shr     eax, 17h
0x180066cff  and     eax, esi
0x180066d01  mov     [rdi], ecx
0x180066d03  or      [rbx+34h], eax
0x180066d06  test    dword ptr [rbx+30h], 200h
0x180066d0d  mov     eax, [rbx+34h]
0x180066d10  jz      short loc_180066D17
0x180066d12  or      eax, esi
0x180066d14  mov     [rbx+34h], eax
0x180066d17  bt      edx, 1Bh
0x180066d1b  jnb     short loc_180066D24
0x180066d1d  bts     eax, 0Bh
0x180066d21  mov     [rbx+34h], eax
0x180066d24  mov     rcx, rbx; this
0x180066d27  call    ?CreateTextServices@CTxtWinHost@@QEAAJXZ; CTxtWinHost::CreateTextServices(void)
0x180066d2c  test    eax, eax
0x180066d2e  js      loc_180066E49
0x180066d34  mov     rcx, [rbx+20h]; this
0x180066d38  xor     edx, edx; int
0x180066d3a  mov     [rbx+66h], bp
0x180066d3e  call    ?HandleSetUndoLimit@CTxtEdit@@QEAA_JJ@Z; CTxtEdit::HandleSetUndoLimit(long)
0x180066d43  xor     edx, edx; Val
0x180066d45  lea     rcx, [rsp+0F8h+var_C8]; void *
0x180066d4a  mov     r8d, 9Ch; Size
0x180066d50  call    memset_0
0x180066d55  test    dword ptr [rbx+30h], 1000h
0x180066d5c  mov     eax, ebp
0x180066d5e  mov     [rsp+0F8h+var_C4], eax
0x180066d62  jz      short loc_180066D73
0x180066d64  mov     eax, 8
0x180066d69  mov     [rsp+0F8h+var_B0], r13w
0x180066d6f  mov     [rsp+0F8h+var_C4], eax
0x180066d73  test    dword ptr [rbx+30h], 2000h
0x180066d7a  jz      short loc_180066D89
0x180066d7c  bts     eax, 10h
0x180066d80  mov     [rsp+0F8h+var_BE], si
0x180066d85  mov     [rsp+0F8h+var_C4], eax
0x180066d89  mov     edi, 4
0x180066d8e  test    eax, eax
0x180066d90  jz      short loc_180066DBC
0x180066d92  mov     rcx, [rbx+20h]
0x180066d96  lea     r9, [rsp+0F8h+var_C8]
0x180066d9b  mov     [rsp+0F8h+var_C8], 0BCh
0x180066da3  mov     r8d, edi
0x180066da6  mov     edx, 447h
0x180066dab  mov     [rsp+0F8h+var_D8], rbp
0x180066db0  mov     rax, [rcx]
0x180066db3  mov     rax, [rax+18h]
0x180066db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066dbc  mov     rcx, [rbx+20h]
0x180066dc0  mov     r9, rdi
0x180066dc3  mov     r8, rdi
0x180066dc6  mov     [rsp+0F8h+var_D8], rbp
0x180066dcb  mov     edi, 4CCh
0x180066dd0  mov     edx, edi
0x180066dd2  mov     rax, [rcx]
0x180066dd5  mov     rax, [rax+18h]
0x180066dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066dde  mov     rcx, [rbx+20h]
0x180066de2  mov     r9d, 80h
0x180066de8  xor     r8d, r8d
0x180066deb  mov     [rsp+0F8h+var_D8], rbp
0x180066df0  mov     edx, edi
0x180066df2  mov     rax, [rcx]
0x180066df5  mov     rax, [rax+18h]
0x180066df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066dfe  mov     rcx, [rbx+20h]
0x180066e02  lea     edx, [rdi-54h]
0x180066e05  mov     r9d, 32h ; '2'
0x180066e0b  mov     [rsp+0F8h+var_D8], rbp
0x180066e10  xor     r8d, r8d
0x180066e13  mov     rax, [rcx]
0x180066e16  mov     rax, [rax+18h]
0x180066e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e1f  mov     rcx, [rbx+20h]
0x180066e23  xor     r9d, r9d
0x180066e26  xor     r8d, r8d
0x180066e29  mov     [rsp+0F8h+var_D8], rbp
0x180066e2e  mov     rdx, [rcx]
0x180066e31  mov     rax, [rdx+18h]
0x180066e35  lea     edx, [rdi-24h]
0x180066e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e3d  mov     eax, esi
0x180066e3f  mov     [rbx+3Ch], rbp
0x180066e43  mov     [rbx+44h], rbp
0x180066e47  jmp     short loc_180066E4B
0x180066e49  xor     eax, eax
0x180066e4b  mov     rcx, [rsp+0F8h+var_28]
0x180066e53  xor     rcx, rsp; StackCookie
0x180066e56  call    __security_check_cookie
0x180066e5b  lea     r11, [rsp+0F8h+var_18]
0x180066e63  mov     rbx, [r11+30h]
0x180066e67  mov     rbp, [r11+38h]
0x180066e6b  mov     rsp, r11
0x180066e6e  pop     r13
0x180066e70  pop     rdi
0x180066e71  pop     rsi
0x180066e72  retn
```
