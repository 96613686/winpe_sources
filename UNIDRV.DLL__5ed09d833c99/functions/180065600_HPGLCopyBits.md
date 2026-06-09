# HPGLCopyBits

- ea: `0x180065600`
- end: `0x1800657a2`
- name: `HPGLCopyBits`
- size: `418`
- prototype: `__int64 __fastcall(struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, POINTL *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180039f24`
- `0x18003dbfc`
- `0x180049d00`
- `0x180065600`
- `0x180066fb4`
- `0x180067780`
- `0x180069a64`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180065772`
- `KERNEL32!SetLastError` at `0x180065772`

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
  unsigned __int8 v11; // bp
  LONG x; // ecx
  LONG y; // edx
  POINTL *v16; // [rsp+28h] [rbp-A0h]
  struct _RECTL v17; // [rsp+60h] [rbp-68h] BYREF

  dhpdev = a1->dhpdev;
  *(_QWORD *)&v17.left = a4;
  if ( dhpdev && a5 && (v10 = *((_QWORD *)dhpdev + 1)) != 0 )
  {
    v11 = -52;
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
      BChangeAndTrackObjectType((__int64)dhpdev, 2);
      if ( (*(_BYTE *)(v10 + 4424) & 0x10) == 0 && !*(_QWORD *)(v10 + 4440) )
        SelectRop3((struct _DEVOBJ *)dhpdev, v11);
      if ( *((char *)dhpdev + 116) < 0 && (*(_BYTE *)(v10 + 4424) & 0x20) != 0 )
        PCL_SelectTransparency((__int64)dhpdev, 0, 1, 8);
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
0x180065600  push    rbx
0x180065602  push    rbp
0x180065603  push    rsi
0x180065604  push    rdi
0x180065605  push    r12
0x180065607  push    r13
0x180065609  push    r14
0x18006560b  push    r15
0x18006560d  sub     rsp, 88h
0x180065614  mov     rax, cs:__security_cookie
0x18006561b  xor     rax, rsp
0x18006561e  mov     [rsp+0C8h+var_58], rax
0x180065623  mov     rdi, [rcx+10h]
0x180065627  mov     r13, r8
0x18006562a  mov     r14, [rsp+0C8h+arg_20]
0x180065632  xor     r8d, r8d; struct _SURFOBJ *
0x180065635  mov     rsi, [rsp+0C8h+arg_28]
0x18006563d  mov     r12, rdx
0x180065640  mov     qword ptr [rsp+0C8h+var_68.left], r9
0x180065645  mov     r15, rcx
0x180065648  test    rdi, rdi
0x18006564b  jz      loc_18006576D
0x180065651  test    r14, r14
0x180065654  jz      loc_18006576D
0x18006565a  mov     rbx, [rdi+8]
0x18006565e  test    rbx, rbx
0x180065661  jz      loc_18006576D
0x180065667  mov     eax, [rbx+1150h]
0x18006566d  mov     ebp, 0CCCCh
0x180065672  test    eax, eax
0x180065674  cmovns  ebp, eax
0x180065677  cmp     [rbx+1170h], r8d
0x18006567e  jz      short loc_1800656F8
0x180065680  mov     qword ptr [rsp+0C8h+var_68.left], r8
0x180065685  test    rsi, rsi
0x180065688  jz      short loc_180065691
0x18006568a  mov     ecx, [rsi]
0x18006568c  mov     edx, [rsi+4]
0x18006568f  jmp     short loc_180065697
0x180065691  mov     edx, r8d
0x180065694  mov     ecx, r8d
0x180065697  mov     eax, [r14+8]
0x18006569b  sub     eax, [r14]
0x18006569e  add     eax, ecx
0x1800656a0  mov     [rsp+0C8h+var_70], ebp; unsigned int
0x1800656a4  mov     [rsp+0C8h+var_78], r8; struct _POINTL *
0x1800656a9  mov     [rsp+0C8h+var_68.right], eax
0x1800656ad  mov     eax, [r14+0Ch]
0x1800656b1  sub     eax, [r14+4]
0x1800656b5  mov     [rsp+0C8h+var_80], r8; struct _POINTL *
0x1800656ba  add     eax, edx
0x1800656bc  mov     [rsp+0C8h+var_88], r14; struct _RECTL *
0x1800656c1  mov     [rsp+0C8h+var_68.bottom], eax
0x1800656c5  lea     rax, [rsp+0C8h+var_68]
0x1800656ca  mov     [rsp+0C8h+var_90], rax; struct _RECTL *
0x1800656cf  mov     [rsp+0C8h+var_98], r8; struct _BRUSHOBJ *
0x1800656d4  mov     [rsp+0C8h+var_A8], r9; struct _XLATEOBJ *
0x1800656d9  mov     r9, r13; struct _CLIPOBJ *
0x1800656dc  mov     [rsp+0C8h+var_68.left], ecx
0x1800656e0  mov     rcx, r15; struct _SURFOBJ *
0x1800656e3  mov     [rsp+0C8h+var_68.top], edx
0x1800656e7  mov     rdx, r12; struct _SURFOBJ *
0x1800656ea  call    ?dwCommonROPBlt@@YAKPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@6K@Z; dwCommonROPBlt(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,_POINTL *,ulong)
0x1800656ef  xor     ecx, ecx
0x1800656f1  test    eax, eax
0x1800656f3  setz    cl
0x1800656f6  jmp     short loc_180065769
0x1800656f8  mov     edx, 2
0x1800656fd  mov     rcx, rdi
0x180065700  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x180065705  test    byte ptr [rbx+1148h], 10h
0x18006570c  jnz     short loc_180065724
0x18006570e  cmp     qword ptr [rbx+1158h], 0
0x180065716  jnz     short loc_180065724
0x180065718  movzx   edx, bpl; unsigned int
0x18006571c  mov     rcx, rdi; struct _DEVOBJ *
0x18006571f  call    ?SelectRop3@@YAHPEAU_DEVOBJ@@K@Z; SelectRop3(_DEVOBJ *,ulong)
0x180065724  test    byte ptr [rdi+74h], 80h
0x180065728  setnz   dl
0x18006572b  test    byte ptr [rbx+1148h], 20h
0x180065732  setnz   al
0x180065735  test    al, dl
0x180065737  jz      short loc_18006574A
0x180065739  xor     edx, edx
0x18006573b  mov     r9b, 8
0x18006573e  mov     rcx, rdi
0x180065741  lea     r8d, [rdx+1]
0x180065745  call    ?PCL_SelectTransparency@@YAHPEAU_DEVOBJ@@W4ETransparency@@1E@Z; PCL_SelectTransparency(_DEVOBJ *,ETransparency,ETransparency,uchar)
0x18006574a  mov     r9, qword ptr [rsp+0C8h+var_68.left]; struct _XLATEOBJ *
0x18006574f  mov     r8, r13; struct _CLIPOBJ *
0x180065752  mov     [rsp+0C8h+var_A0], rsi; POINTL *
0x180065757  mov     rdx, r12; struct _SURFOBJ *
0x18006575a  mov     rcx, r15; struct _SURFOBJ *
0x18006575d  mov     [rsp+0C8h+var_A8], r14; struct _RECTL *
0x180065762  call    ?HTCopyBits@@YAHPEAU_SURFOBJ@@0PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@PEAU_POINTL@@@Z; HTCopyBits(_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *)
0x180065767  mov     ecx, eax
0x180065769  mov     eax, ecx
0x18006576b  jmp     short loc_180065780
0x18006576d  mov     ecx, 0Dh; dwErrCode
0x180065772  call    cs:__imp_SetLastError
0x180065779  nop     dword ptr [rax+rax+00h]
0x18006577e  xor     eax, eax
0x180065780  mov     rcx, [rsp+0C8h+var_58]
0x180065785  xor     rcx, rsp; StackCookie
0x180065788  call    __security_check_cookie
0x18006578d  add     rsp, 88h
0x180065794  pop     r15
0x180065796  pop     r14
0x180065798  pop     r13
0x18006579a  pop     r12
0x18006579c  pop     rdi
0x18006579d  pop     rsi
0x18006579e  pop     rbp
0x18006579f  pop     rbx
0x1800657a0  retn
```
