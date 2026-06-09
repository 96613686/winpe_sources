# ConvertCredUiInfoToInternal(_CREDUI_INFOW *,bool,CREDUI_INFO_INTERNAL *)

- ea: `0x14000ad2c`
- end: `0x14000aec0`
- name: `?ConvertCredUiInfoToInternal@@YAJPEAU_CREDUI_INFOW@@_NPEAUCREDUI_INFO_INTERNAL@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(struct _CREDUI_INFOW *, char, struct CREDUI_INFO_INTERNAL *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400137d4`

## callees

- `0x1400099a8`
- `0x14000ad2c`
- `0x1400136fc`

## string_xrefs

- `0x14000ad67`: `shellcommon\internal\shell\inc\CredUIApiCommon.h`

## pseudocode

```c
__int64 __fastcall ConvertCredUiInfoToInternal(struct _CREDUI_INFOW *a1, char a2, struct CREDUI_INFO_INTERNAL *a3)
{
  __int64 v6; // rcx
  struct CREDUI_INFO_INTERNAL *v7; // rax
  HWND hwndParent; // rax
  PCWSTR pszMessageText; // rax
  PCWSTR pszCaptionText; // rax
  HBITMAP hbmBanner; // rax
  __int64 v12; // rax
  HWND v13; // rax
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v16; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v17; // [rsp+48h] [rbp+20h] BYREF

  if ( a1 && a3 )
  {
    if ( a1->cbSize != 40 && a1->cbSize != 136 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE1,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\CredUIApiCommon.h",
        (const char *)0x80070057LL,
        v14);
      return 2147942487LL;
    }
    v6 = 136;
    v7 = a3;
    do
    {
      *(_BYTE *)v7 = 0;
      v7 = (struct CREDUI_INFO_INTERNAL *)((char *)v7 + 1);
      --v6;
    }
    while ( v6 );
    *(_DWORD *)a3 = 136;
    if ( a2 )
    {
      *((_QWORD *)a3 + 1) = a1->hwndParent;
    }
    else
    {
      v16 = 0;
      v17 = &v16;
      _lambda_031a225025799e5c99102519281e3460_::operator()(&v17);
      if ( v16 )
        *((_QWORD *)a3 + 1) = v16;
    }
    *((_QWORD *)a3 + 2) = a1->pszMessageText;
    *((_QWORD *)a3 + 3) = a1->pszCaptionText;
    if ( a1->cbSize == 136 )
    {
      if ( ((__int64)a1->hbmBanner & 0x100) != 0 )
        *((_QWORD *)a3 + 5) = *(_QWORD *)&a1[1].cbSize;
      if ( ((__int64)a1->hbmBanner & 0x200) != 0 )
        *((_QWORD *)a3 + 6) = a1[1].hwndParent;
      if ( ((__int64)a1->hbmBanner & 0x400) != 0 )
      {
        *((_QWORD *)a3 + 7) = a1[1].pszMessageText;
        *((_DWORD *)a3 + 16) = a1[1].pszCaptionText;
        *((_QWORD *)a3 + 9) = a1[1].hbmBanner;
      }
      if ( ((__int64)a1->hbmBanner & 0x800) != 0 )
        *((_QWORD *)a3 + 10) = *(_QWORD *)&a1[2].cbSize;
      hwndParent = a1[2].hwndParent;
      if ( hwndParent && *(_WORD *)hwndParent )
        *((_QWORD *)a3 + 11) = hwndParent;
      pszMessageText = a1[2].pszMessageText;
      if ( pszMessageText && *pszMessageText )
        *((_QWORD *)a3 + 12) = pszMessageText;
      pszCaptionText = a1[2].pszCaptionText;
      if ( pszCaptionText && *pszCaptionText )
        *((_QWORD *)a3 + 13) = pszCaptionText;
      hbmBanner = a1[2].hbmBanner;
      if ( hbmBanner )
        *((_QWORD *)a3 + 14) = hbmBanner;
      v12 = *(_QWORD *)&a1[3].cbSize;
      if ( v12 )
        *((_QWORD *)a3 + 15) = v12;
      v13 = a1[3].hwndParent;
      if ( v13 )
        *((_QWORD *)a3 + 16) = v13;
      *((_DWORD *)a3 + 8) = a1->hbmBanner;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000ad2c  mov     [rsp+arg_8], rbx
0x14000ad31  mov     [rsp+arg_10], rsi
0x14000ad36  push    rdi; int
0x14000ad37  sub     rsp, 20h
0x14000ad3b  xor     esi, esi
0x14000ad3d  mov     rdi, r8
0x14000ad40  mov     rbx, rcx
0x14000ad43  test    rcx, rcx
0x14000ad46  jz      loc_14000AEAE
0x14000ad4c  test    r8, r8
0x14000ad4f  jz      loc_14000AEAE
0x14000ad55  cmp     dword ptr [rcx], 28h ; '('
0x14000ad58  jz      short loc_14000AD87
0x14000ad5a  cmp     dword ptr [rcx], 88h
0x14000ad60  jz      short loc_14000AD87
0x14000ad62  mov     rcx, [rsp+28h]; this
0x14000ad67  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Cred"...
0x14000ad6e  mov     ebx, 80070057h
0x14000ad73  mov     edx, 0E1h; void *
0x14000ad78  mov     r9d, ebx; char *
0x14000ad7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ad80  mov     eax, ebx
0x14000ad82  jmp     loc_14000AEB0
0x14000ad87  mov     ecx, 88h
0x14000ad8c  mov     rax, rdi
0x14000ad8f  mov     [rax], sil
0x14000ad92  inc     rax
0x14000ad95  sub     rcx, 1
0x14000ad99  jnz     short loc_14000AD8F
0x14000ad9b  mov     dword ptr [r8], 88h
0x14000ada2  test    dl, dl
0x14000ada4  jz      short loc_14000ADB0
0x14000ada6  mov     rax, [rbx+8]
0x14000adaa  mov     [r8+8], rax
0x14000adae  jmp     short loc_14000ADD7
0x14000adb0  lea     rax, [rsp+28h+arg_0]
0x14000adb5  mov     [rsp+28h+arg_0], rsi
0x14000adba  lea     rcx, [rsp+28h+arg_18]
0x14000adbf  mov     [rsp+28h+arg_18], rax
0x14000adc4  call    ??R_lambda_031a225025799e5c99102519281e3460_@@QEBAJXZ; _lambda_031a225025799e5c99102519281e3460_::operator()(void)
0x14000adc9  mov     rax, [rsp+28h+arg_0]
0x14000adce  test    rax, rax
0x14000add1  jz      short loc_14000ADD7
0x14000add3  mov     [rdi+8], rax
0x14000add7  mov     rax, [rbx+10h]
0x14000addb  mov     [rdi+10h], rax
0x14000addf  mov     rax, [rbx+18h]
0x14000ade3  mov     [rdi+18h], rax
0x14000ade7  cmp     dword ptr [rbx], 88h
0x14000aded  jnz     loc_14000AEAE
0x14000adf3  test    dword ptr [rbx+20h], 100h
0x14000adfa  jz      short loc_14000AE04
0x14000adfc  mov     rax, [rbx+28h]
0x14000ae00  mov     [rdi+28h], rax
0x14000ae04  test    dword ptr [rbx+20h], 200h
0x14000ae0b  jz      short loc_14000AE15
0x14000ae0d  mov     rax, [rbx+30h]
0x14000ae11  mov     [rdi+30h], rax
0x14000ae15  test    dword ptr [rbx+20h], 400h
0x14000ae1c  jz      short loc_14000AE34
0x14000ae1e  mov     rax, [rbx+38h]
0x14000ae22  mov     [rdi+38h], rax
0x14000ae26  mov     eax, [rbx+40h]
0x14000ae29  mov     [rdi+40h], eax
0x14000ae2c  mov     rax, [rbx+48h]
0x14000ae30  mov     [rdi+48h], rax
0x14000ae34  test    dword ptr [rbx+20h], 800h
0x14000ae3b  jz      short loc_14000AE45
0x14000ae3d  mov     rax, [rbx+50h]
0x14000ae41  mov     [rdi+50h], rax
0x14000ae45  mov     rax, [rbx+58h]
0x14000ae49  test    rax, rax
0x14000ae4c  jz      short loc_14000AE57
0x14000ae4e  cmp     [rax], si
0x14000ae51  jz      short loc_14000AE57
0x14000ae53  mov     [rdi+58h], rax
0x14000ae57  mov     rax, [rbx+60h]
0x14000ae5b  test    rax, rax
0x14000ae5e  jz      short loc_14000AE69
0x14000ae60  cmp     [rax], si
0x14000ae63  jz      short loc_14000AE69
0x14000ae65  mov     [rdi+60h], rax
0x14000ae69  mov     rax, [rbx+68h]
0x14000ae6d  test    rax, rax
0x14000ae70  jz      short loc_14000AE7B
0x14000ae72  cmp     [rax], si
0x14000ae75  jz      short loc_14000AE7B
0x14000ae77  mov     [rdi+68h], rax
0x14000ae7b  mov     rax, [rbx+70h]
0x14000ae7f  test    rax, rax
0x14000ae82  jz      short loc_14000AE88
0x14000ae84  mov     [rdi+70h], rax
0x14000ae88  mov     rax, [rbx+78h]
0x14000ae8c  test    rax, rax
0x14000ae8f  jz      short loc_14000AE95
0x14000ae91  mov     [rdi+78h], rax
0x14000ae95  mov     rax, [rbx+80h]
0x14000ae9c  test    rax, rax
0x14000ae9f  jz      short loc_14000AEA8
0x14000aea1  mov     [rdi+80h], rax
0x14000aea8  mov     eax, [rbx+20h]
0x14000aeab  mov     [rdi+20h], eax
0x14000aeae  xor     eax, eax
0x14000aeb0  mov     rbx, [rsp+28h+arg_8]
0x14000aeb5  mov     rsi, [rsp+28h+arg_10]
0x14000aeba  add     rsp, 20h
0x14000aebe  pop     rdi
0x14000aebf  retn
```
