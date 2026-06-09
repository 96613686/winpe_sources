# HTCopyBits(_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *)

- ea: `0x1800681f8`
- end: `0x180068393`
- name: `?HTCopyBits@@YAHPEAU_SURFOBJ@@0PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@PEAU_POINTL@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, POINTL *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180063f50`

## callees

- `0x18003ce0c`
- `0x1800487e0`
- `0x1800681f8`
- `0x180068648`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180068242`
- `KERNEL32!SetLastError` at `0x180068242`
- `GDI32!EngCopyBits` at `0x180068278`
- `GDI32!EngCopyBits` at `0x180068278`

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
  unsigned int v18; // ecx
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
0x1800681f8  push    rbx
0x1800681fa  push    rbp
0x1800681fb  push    rsi
0x1800681fc  push    rdi
0x1800681fd  push    r14
0x1800681ff  sub     rsp, 80h
0x180068206  mov     rax, cs:__security_cookie
0x18006820d  xor     rax, rsp
0x180068210  mov     [rsp+0A8h+var_38], rax
0x180068215  mov     r14, rcx
0x180068218  mov     rbp, r9
0x18006821b  mov     r9, [rsp+0A8h+arg_20]; struct _RECTL *
0x180068223  mov     rsi, r8
0x180068226  mov     rcx, [rsp+0A8h+arg_28]
0x18006822e  mov     r10, rdx
0x180068231  mov     rbx, [r14+10h]
0x180068235  mov     r11, [rbx+8]
0x180068239  test    r11, r11
0x18006823c  jnz     short loc_18006824F
0x18006823e  lea     ecx, [r11+0Dh]; dwErrCode
0x180068242  call    cs:__imp_SetLastError
0x180068248  xor     eax, eax
0x18006824a  jmp     loc_180068378
0x18006824f  cmp     dword ptr [rdx+48h], 1
0x180068253  jnz     short loc_1800682AD
0x180068255  mov     rdi, [r11+1158h]
0x18006825c  test    rdi, rdi
0x18006825f  jz      short loc_180068292
0x180068261  mov     [rsp+0A8h+pptlSrc], rcx; pptlSrc
0x180068266  lea     rax, [r11+1160h]
0x18006826d  mov     rcx, rdi; psoDest
0x180068270  mov     [rsp+0A8h+prclDest], rax; prclDest
0x180068275  xor     r9d, r9d; pxlo
0x180068278  call    cs:__imp_EngCopyBits
0x18006827e  xor     ecx, ecx
0x180068280  test    eax, eax
0x180068282  mov     rax, [rbx+1050h]
0x180068289  mov     [rbx+8], rax
0x18006828d  setnz   cl
0x180068290  jmp     short loc_1800682A6
0x180068292  mov     [rsp+0A8h+pptlSrc], rbp; struct _XLATEOBJ *
0x180068297  mov     [rsp+0A8h+prclDest], rcx; struct _POINTL *
0x18006829c  mov     rcx, rbx; struct _DEVOBJ *
0x18006829f  call    ?OutputHTBitmap@@YAHPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_CLIPOBJ@@PEAU_RECTL@@PEAU_POINTL@@PEAU_XLATEOBJ@@@Z; OutputHTBitmap(_DEVOBJ *,_SURFOBJ *,_CLIPOBJ *,_RECTL *,_POINTL *,_XLATEOBJ *)
0x1800682a4  mov     ecx, eax
0x1800682a6  mov     eax, ecx
0x1800682a8  jmp     loc_180068378
0x1800682ad  mov     qword ptr [rsp+0A8h+var_48.left], 0
0x1800682b6  test    rcx, rcx
0x1800682b9  jz      short loc_1800682CC
0x1800682bb  mov     edx, [rcx]
0x1800682bd  mov     r8d, [rcx+4]
0x1800682c1  mov     [rsp+0A8h+var_48.left], edx
0x1800682c5  mov     [rsp+0A8h+var_48.top], r8d
0x1800682ca  jmp     short loc_1800682D6
0x1800682cc  xor     r8d, r8d
0x1800682cf  mov     qword ptr [rsp+0A8h+var_48.left], r8
0x1800682d4  xor     edx, edx
0x1800682d6  mov     eax, [r9+8]
0x1800682da  xor     edi, edi
0x1800682dc  sub     eax, [r9]
0x1800682df  add     eax, edx
0x1800682e1  mov     [rsp+0A8h+var_48.right], eax
0x1800682e5  mov     eax, [r9+0Ch]
0x1800682e9  sub     eax, [r9+4]
0x1800682ed  add     eax, r8d
0x1800682f0  mov     [rsp+0A8h+var_48.bottom], eax
0x1800682f4  cmp     dword ptr [rbx+1060h], 2
0x1800682fb  jnz     short loc_18006830C
0x1800682fd  mov     dword ptr [rbx+1060h], 30h ; '0'
0x180068307  mov     edi, 1
0x18006830c  mov     eax, [r11+1150h]
0x180068313  mov     edx, 0CCCCh
0x180068318  test    eax, eax
0x18006831a  mov     rcx, r14; struct _SURFOBJ *
0x18006831d  cmovns  edx, eax
0x180068320  lea     rax, [rsp+0A8h+var_48]
0x180068325  mov     [rsp+0A8h+var_50], edx; unsigned int
0x180068329  xor     r8d, r8d; struct _SURFOBJ *
0x18006832c  mov     [rsp+0A8h+var_58], 0; struct _POINTL *
0x180068335  mov     rdx, r10; struct _SURFOBJ *
0x180068338  mov     [rsp+0A8h+var_60], 0; struct _POINTL *
0x180068341  mov     [rsp+0A8h+var_68], r9; struct _RECTL *
0x180068346  mov     r9, rsi; struct _CLIPOBJ *
0x180068349  mov     [rsp+0A8h+var_70], rax; struct _RECTL *
0x18006834e  mov     [rsp+0A8h+var_78], 0; struct _BRUSHOBJ *
0x180068357  mov     [rsp+0A8h+prclDest], rbp; struct _XLATEOBJ *
0x18006835c  call    ?dwCommonROPBlt@@YAKPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@6K@Z; dwCommonROPBlt(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,_POINTL *,ulong)
0x180068361  mov     ecx, eax
0x180068363  test    edi, edi
0x180068365  jz      short loc_180068371
0x180068367  mov     dword ptr [rbx+1060h], 2
0x180068371  xor     eax, eax
0x180068373  test    ecx, ecx
0x180068375  setz    al
0x180068378  mov     rcx, [rsp+0A8h+var_38]
0x18006837d  xor     rcx, rsp; StackCookie
0x180068380  call    __security_check_cookie
0x180068385  add     rsp, 80h
0x18006838c  pop     r14
0x18006838e  pop     rdi
0x18006838f  pop     rsi
0x180068390  pop     rbp
0x180068391  pop     rbx
0x180068392  retn
```
