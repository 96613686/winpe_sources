# HTCopyBits(_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *)

- ea: `0x180069a64`
- end: `0x180069c0c`
- name: `?HTCopyBits@@YAHPEAU_SURFOBJ@@0PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@PEAU_POINTL@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, POINTL *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180065600`

## callees

- `0x18003dbfc`
- `0x180049d00`
- `0x180069a64`
- `0x180069ec8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180069aae`
- `KERNEL32!SetLastError` at `0x180069aae`
- `GDI32!EngCopyBits` at `0x180069aea`
- `GDI32!EngCopyBits` at `0x180069aea`

## pseudocode

```c
__int64 __fastcall HTCopyBits(
        struct _SURFOBJ *a1,
        struct _SURFOBJ *a2,
        struct _CLIPOBJ *a3,
        struct _XLATEOBJ *a4,
        struct _RECTL *a5,
        POINTL *a6)
{
  DHPDEV dhpdev; // rbx
  __int64 v9; // r11
  SURFOBJ *v11; // rdi
  BOOL v12; // eax
  LONG x; // edx
  LONG y; // r8d
  int v16; // edi
  unsigned int v17; // edx
  int v18; // ecx
  POINTL *pptlSrc; // [rsp+28h] [rbp-80h]
  struct _RECTL v20; // [rsp+60h] [rbp-48h] BYREF

  dhpdev = a1->dhpdev;
  v9 = *((_QWORD *)dhpdev + 1);
  if ( v9 )
  {
    if ( a2->iBitmapFormat == 1 )
    {
      v11 = *(SURFOBJ **)(v9 + 4440);
      if ( v11 )
      {
        v12 = EngCopyBits(v11, a2, a3, 0, (RECTL *)(v9 + 4448), a6);
        *((_QWORD *)dhpdev + 1) = *((_QWORD *)dhpdev + 522);
        return v12;
      }
      else
      {
        return (unsigned int)OutputHTBitmap((struct _DEVOBJ *)dhpdev, a2, a3, a5, a6, a4);
      }
    }
    else
    {
      *(_QWORD *)&v20.left = 0;
      if ( a6 )
      {
        x = a6->x;
        y = a6->y;
        v20.left = a6->x;
        v20.top = y;
      }
      else
      {
        y = 0;
        *(_QWORD *)&v20.left = 0;
        x = 0;
      }
      v16 = 0;
      v20.right = x + a5->right - a5->left;
      v20.bottom = y + a5->bottom - a5->top;
      if ( *((_DWORD *)dhpdev + 1048) == 2 )
      {
        *((_DWORD *)dhpdev + 1048) = 48;
        v16 = 1;
      }
      v17 = 52428;
      if ( *(int *)(v9 + 4432) >= 0 )
        v17 = *(_DWORD *)(v9 + 4432);
      v18 = dwCommonROPBlt(a1, a2, 0, a3, a4, (struct tagCOLORADJUSTMENT *)pptlSrc, 0, &v20, a5, 0, 0, v17);
      if ( v16 )
        *((_DWORD *)dhpdev + 1048) = 2;
      return v18 == 0;
    }
  }
  else
  {
    SetLastError(0xDu);
    return 0;
  }
}

```

## disassembly

```asm
0x180069a64  push    rbx
0x180069a66  push    rbp
0x180069a67  push    rsi
0x180069a68  push    rdi
0x180069a69  push    r14
0x180069a6b  sub     rsp, 80h
0x180069a72  mov     rax, cs:__security_cookie
0x180069a79  xor     rax, rsp
0x180069a7c  mov     [rsp+0A8h+var_38], rax
0x180069a81  mov     r14, rcx
0x180069a84  mov     rbp, r9
0x180069a87  mov     r9, [rsp+0A8h+arg_20]; struct _RECTL *
0x180069a8f  mov     rsi, r8
0x180069a92  mov     rcx, [rsp+0A8h+arg_28]
0x180069a9a  mov     r10, rdx
0x180069a9d  mov     rbx, [r14+10h]
0x180069aa1  mov     r11, [rbx+8]
0x180069aa5  test    r11, r11
0x180069aa8  jnz     short loc_180069AC1
0x180069aaa  lea     ecx, [r11+0Dh]; dwErrCode
0x180069aae  call    cs:__imp_SetLastError
0x180069ab5  nop     dword ptr [rax+rax+00h]
0x180069aba  xor     eax, eax
0x180069abc  jmp     loc_180069BF0
0x180069ac1  cmp     dword ptr [rdx+48h], 1
0x180069ac5  jnz     short loc_180069B25
0x180069ac7  mov     rdi, [r11+1158h]
0x180069ace  test    rdi, rdi
0x180069ad1  jz      short loc_180069B0A
0x180069ad3  mov     [rsp+0A8h+pptlSrc], rcx; pptlSrc
0x180069ad8  lea     rax, [r11+1160h]
0x180069adf  mov     rcx, rdi; psoDest
0x180069ae2  mov     [rsp+0A8h+prclDest], rax; prclDest
0x180069ae7  xor     r9d, r9d; pxlo
0x180069aea  call    cs:__imp_EngCopyBits
0x180069af1  nop     dword ptr [rax+rax+00h]
0x180069af6  xor     ecx, ecx
0x180069af8  test    eax, eax
0x180069afa  mov     rax, [rbx+1050h]
0x180069b01  mov     [rbx+8], rax
0x180069b05  setnz   cl
0x180069b08  jmp     short loc_180069B1E
0x180069b0a  mov     [rsp+0A8h+pptlSrc], rbp; struct _XLATEOBJ *
0x180069b0f  mov     [rsp+0A8h+prclDest], rcx; struct _POINTL *
0x180069b14  mov     rcx, rbx; struct _DEVOBJ *
0x180069b17  call    ?OutputHTBitmap@@YAHPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_CLIPOBJ@@PEAU_RECTL@@PEAU_POINTL@@PEAU_XLATEOBJ@@@Z; OutputHTBitmap(_DEVOBJ *,_SURFOBJ *,_CLIPOBJ *,_RECTL *,_POINTL *,_XLATEOBJ *)
0x180069b1c  mov     ecx, eax
0x180069b1e  mov     eax, ecx
0x180069b20  jmp     loc_180069BF0
0x180069b25  mov     qword ptr [rsp+0A8h+var_48.left], 0
0x180069b2e  test    rcx, rcx
0x180069b31  jz      short loc_180069B44
0x180069b33  mov     edx, [rcx]
0x180069b35  mov     r8d, [rcx+4]
0x180069b39  mov     [rsp+0A8h+var_48.left], edx
0x180069b3d  mov     [rsp+0A8h+var_48.top], r8d
0x180069b42  jmp     short loc_180069B4E
0x180069b44  xor     r8d, r8d
0x180069b47  mov     qword ptr [rsp+0A8h+var_48.left], r8
0x180069b4c  xor     edx, edx
0x180069b4e  mov     eax, [r9+8]
0x180069b52  xor     edi, edi
0x180069b54  sub     eax, [r9]
0x180069b57  add     eax, edx
0x180069b59  mov     [rsp+0A8h+var_48.right], eax
0x180069b5d  mov     eax, [r9+0Ch]
0x180069b61  sub     eax, [r9+4]
0x180069b65  add     eax, r8d
0x180069b68  mov     [rsp+0A8h+var_48.bottom], eax
0x180069b6c  cmp     dword ptr [rbx+1060h], 2
0x180069b73  jnz     short loc_180069B84
0x180069b75  mov     dword ptr [rbx+1060h], 30h ; '0'
0x180069b7f  mov     edi, 1
0x180069b84  mov     eax, [r11+1150h]
0x180069b8b  mov     edx, 0CCCCh
0x180069b90  test    eax, eax
0x180069b92  mov     rcx, r14; struct _SURFOBJ *
0x180069b95  cmovns  edx, eax
0x180069b98  lea     rax, [rsp+0A8h+var_48]
0x180069b9d  mov     [rsp+0A8h+var_50], edx; unsigned int
0x180069ba1  xor     r8d, r8d; struct _SURFOBJ *
0x180069ba4  mov     [rsp+0A8h+var_58], 0; struct _POINTL *
0x180069bad  mov     rdx, r10; struct _SURFOBJ *
0x180069bb0  mov     [rsp+0A8h+var_60], 0; struct _POINTL *
0x180069bb9  mov     [rsp+0A8h+var_68], r9; struct _RECTL *
0x180069bbe  mov     r9, rsi; struct _CLIPOBJ *
0x180069bc1  mov     [rsp+0A8h+var_70], rax; struct _RECTL *
0x180069bc6  mov     [rsp+0A8h+var_78], 0; struct _BRUSHOBJ *
0x180069bcf  mov     [rsp+0A8h+prclDest], rbp; struct _XLATEOBJ *
0x180069bd4  call    ?dwCommonROPBlt@@YAKPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@6K@Z; dwCommonROPBlt(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,_POINTL *,ulong)
0x180069bd9  mov     ecx, eax
0x180069bdb  test    edi, edi
0x180069bdd  jz      short loc_180069BE9
0x180069bdf  mov     dword ptr [rbx+1060h], 2
0x180069be9  xor     eax, eax
0x180069beb  test    ecx, ecx
0x180069bed  setz    al
0x180069bf0  mov     rcx, [rsp+0A8h+var_38]
0x180069bf5  xor     rcx, rsp; StackCookie
0x180069bf8  call    __security_check_cookie
0x180069bfd  add     rsp, 80h
0x180069c04  pop     r14
0x180069c06  pop     rdi
0x180069c07  pop     rsi
0x180069c08  pop     rbp
0x180069c09  pop     rbx
0x180069c0a  retn
```
