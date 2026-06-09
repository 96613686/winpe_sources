# HPGLCopyBits

- ea: `0x180063f50`
- end: `0x1800640eb`
- name: `HPGLCopyBits`
- size: `411`
- prototype: `__int64 __fastcall(struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18003949c`
- `0x18003ce0c`
- `0x1800487e0`
- `0x180063f50`
- `0x180065874`
- `0x180065fdc`
- `0x1800681f8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800640c2`
- `KERNEL32!SetLastError` at `0x1800640c2`

## pseudocode

```c
__int64 __fastcall HPGLCopyBits(
        struct _SURFOBJ *a1,
        struct _SURFOBJ *a2,
        struct _CLIPOBJ *a3,
        struct _XLATEOBJ *a4,
        struct _RECTL *a5,
        POINTL *a6)
{
  DHPDEV dhpdev; // rdi
  __int64 v10; // rbx
  unsigned int v11; // ebp
  LONG x; // ecx
  LONG y; // edx
  POINTL *v16; // [rsp+28h] [rbp-A0h]
  struct _RECTL v17; // [rsp+60h] [rbp-68h] BYREF

  dhpdev = a1->dhpdev;
  *(_QWORD *)&v17.left = a4;
  if ( dhpdev && a5 && (v10 = *((_QWORD *)dhpdev + 1)) != 0 )
  {
    v11 = 52428;
    if ( *(int *)(v10 + 4432) >= 0 )
      v11 = *(_DWORD *)(v10 + 4432);
    if ( *(_DWORD *)(v10 + 4464) )
    {
      *(_QWORD *)&v17.left = 0;
      if ( a6 )
      {
        x = a6->x;
        y = a6->y;
      }
      else
      {
        y = 0;
        x = 0;
      }
      v17.right = x + a5->right - a5->left;
      v17.bottom = y + a5->bottom - a5->top;
      v17.left = x;
      v17.top = y;
      return dwCommonROPBlt(a1, a2, 0, a3, a4, (struct tagCOLORADJUSTMENT *)v16, 0, &v17, a5, 0, 0, v11) == 0;
    }
    else
    {
      BChangeAndTrackObjectType(dhpdev, 2);
      if ( (*(_BYTE *)(v10 + 4424) & 0x10) == 0 && !*(_QWORD *)(v10 + 4440) )
        SelectRop3((struct _DEVOBJ *)dhpdev, (unsigned __int8)v11);
      if ( *((char *)dhpdev + 116) < 0 && (*(_BYTE *)(v10 + 4424) & 0x20) != 0 )
        PCL_SelectTransparency(dhpdev, 0, 1);
      return (unsigned int)HTCopyBits(a1, a2, a3, *(struct _XLATEOBJ **)&v17.left, a5, a6);
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
0x180063f50  push    rbx
0x180063f52  push    rbp
0x180063f53  push    rsi
0x180063f54  push    rdi
0x180063f55  push    r12
0x180063f57  push    r13
0x180063f59  push    r14
0x180063f5b  push    r15
0x180063f5d  sub     rsp, 88h
0x180063f64  mov     rax, cs:__security_cookie
0x180063f6b  xor     rax, rsp
0x180063f6e  mov     [rsp+0C8h+var_58], rax
0x180063f73  mov     rdi, [rcx+10h]
0x180063f77  mov     r13, r8
0x180063f7a  mov     r14, [rsp+0C8h+arg_20]
0x180063f82  xor     r8d, r8d; struct _SURFOBJ *
0x180063f85  mov     rsi, [rsp+0C8h+arg_28]
0x180063f8d  mov     r12, rdx
0x180063f90  mov     qword ptr [rsp+0C8h+var_68.left], r9
0x180063f95  mov     r15, rcx
0x180063f98  test    rdi, rdi
0x180063f9b  jz      loc_1800640BD
0x180063fa1  test    r14, r14
0x180063fa4  jz      loc_1800640BD
0x180063faa  mov     rbx, [rdi+8]
0x180063fae  test    rbx, rbx
0x180063fb1  jz      loc_1800640BD
0x180063fb7  mov     eax, [rbx+1150h]
0x180063fbd  mov     ebp, 0CCCCh
0x180063fc2  test    eax, eax
0x180063fc4  cmovns  ebp, eax
0x180063fc7  cmp     [rbx+1170h], r8d
0x180063fce  jz      short loc_180064048
0x180063fd0  mov     qword ptr [rsp+0C8h+var_68.left], r8
0x180063fd5  test    rsi, rsi
0x180063fd8  jz      short loc_180063FE1
0x180063fda  mov     ecx, [rsi]
0x180063fdc  mov     edx, [rsi+4]
0x180063fdf  jmp     short loc_180063FE7
0x180063fe1  mov     edx, r8d
0x180063fe4  mov     ecx, r8d
0x180063fe7  mov     eax, [r14+8]
0x180063feb  sub     eax, [r14]
0x180063fee  add     eax, ecx
0x180063ff0  mov     [rsp+0C8h+var_70], ebp; unsigned int
0x180063ff4  mov     [rsp+0C8h+var_78], r8; struct _POINTL *
0x180063ff9  mov     [rsp+0C8h+var_68.right], eax
0x180063ffd  mov     eax, [r14+0Ch]
0x180064001  sub     eax, [r14+4]
0x180064005  mov     [rsp+0C8h+var_80], r8; struct _POINTL *
0x18006400a  add     eax, edx
0x18006400c  mov     [rsp+0C8h+var_88], r14; struct _RECTL *
0x180064011  mov     [rsp+0C8h+var_68.bottom], eax
0x180064015  lea     rax, [rsp+0C8h+var_68]
0x18006401a  mov     [rsp+0C8h+var_90], rax; struct _RECTL *
0x18006401f  mov     [rsp+0C8h+var_98], r8; struct _BRUSHOBJ *
0x180064024  mov     [rsp+0C8h+var_A8], r9; struct _XLATEOBJ *
0x180064029  mov     r9, r13; struct _CLIPOBJ *
0x18006402c  mov     [rsp+0C8h+var_68.left], ecx
0x180064030  mov     rcx, r15; struct _SURFOBJ *
0x180064033  mov     [rsp+0C8h+var_68.top], edx
0x180064037  mov     rdx, r12; struct _SURFOBJ *
0x18006403a  call    ?dwCommonROPBlt@@YAKPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@6K@Z; dwCommonROPBlt(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,_POINTL *,ulong)
0x18006403f  xor     ecx, ecx
0x180064041  test    eax, eax
0x180064043  setz    cl
0x180064046  jmp     short loc_1800640B9
0x180064048  mov     edx, 2
0x18006404d  mov     rcx, rdi
0x180064050  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x180064055  test    byte ptr [rbx+1148h], 10h
0x18006405c  jnz     short loc_180064074
0x18006405e  cmp     qword ptr [rbx+1158h], 0
0x180064066  jnz     short loc_180064074
0x180064068  movzx   edx, bpl; unsigned int
0x18006406c  mov     rcx, rdi; struct _DEVOBJ *
0x18006406f  call    ?SelectRop3@@YAHPEAU_DEVOBJ@@K@Z; SelectRop3(_DEVOBJ *,ulong)
0x180064074  test    byte ptr [rdi+74h], 80h
0x180064078  setnz   dl
0x18006407b  test    byte ptr [rbx+1148h], 20h
0x180064082  setnz   al
0x180064085  test    al, dl
0x180064087  jz      short loc_18006409A
0x180064089  xor     edx, edx
0x18006408b  mov     r9b, 8
0x18006408e  mov     rcx, rdi
0x180064091  lea     r8d, [rdx+1]
0x180064095  call    ?PCL_SelectTransparency@@YAHPEAU_DEVOBJ@@W4ETransparency@@1E@Z; PCL_SelectTransparency(_DEVOBJ *,ETransparency,ETransparency,uchar)
0x18006409a  mov     r9, qword ptr [rsp+0C8h+var_68.left]; struct _XLATEOBJ *
0x18006409f  mov     r8, r13; struct _CLIPOBJ *
0x1800640a2  mov     [rsp+0C8h+var_A0], rsi; POINTL *
0x1800640a7  mov     rdx, r12; struct _SURFOBJ *
0x1800640aa  mov     rcx, r15; struct _SURFOBJ *
0x1800640ad  mov     [rsp+0C8h+var_A8], r14; struct _RECTL *
0x1800640b2  call    ?HTCopyBits@@YAHPEAU_SURFOBJ@@0PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@PEAU_POINTL@@@Z; HTCopyBits(_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *)
0x1800640b7  mov     ecx, eax
0x1800640b9  mov     eax, ecx
0x1800640bb  jmp     short loc_1800640CA
0x1800640bd  mov     ecx, 0Dh; dwErrCode
0x1800640c2  call    cs:__imp_SetLastError
0x1800640c8  xor     eax, eax
0x1800640ca  mov     rcx, [rsp+0C8h+var_58]
0x1800640cf  xor     rcx, rsp; StackCookie
0x1800640d2  call    __security_check_cookie
0x1800640d7  add     rsp, 88h
0x1800640de  pop     r15
0x1800640e0  pop     r14
0x1800640e2  pop     r13
0x1800640e4  pop     r12
0x1800640e6  pop     rdi
0x1800640e7  pop     rsi
0x1800640e8  pop     rbp
0x1800640e9  pop     rbx
0x1800640ea  retn
```
