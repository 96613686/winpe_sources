# dwCommonROPBlt(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,_POINTL *,ulong)

- ea: `0x18003dbfc`
- end: `0x18003dec6`
- name: `?dwCommonROPBlt@@YAKPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@6K@Z`
- size: `714`
- prototype: `__int64 __fastcall(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _BRUSHOBJ *, struct _RECTL *, struct _RECTL *, struct _POINTL *, struct _POINTL *, unsigned int)`
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180063e10`
- `0x180065400`
- `0x180065600`
- `0x1800657b0`
- `0x1800658c0`
- `0x180069a64`

## callees

- `0x180039f24`
- `0x18003dbfc`
- `0x18006496c`
- `0x1800650d8`
- `0x180065274`
- `0x180066fb4`
- `0x180069964`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18003dc34`
- `KERNEL32!SetLastError` at `0x18003dea1`
- `KERNEL32!SetLastError` at `0x18003dc34`
- `KERNEL32!SetLastError` at `0x18003dea1`

## pseudocode

```c
__int64 __fastcall dwCommonROPBlt(
        struct _SURFOBJ *a1,
        struct _SURFOBJ *a2,
        struct _SURFOBJ *a3,
        struct _CLIPOBJ *a4,
        struct _XLATEOBJ *a5,
        struct tagCOLORADJUSTMENT *a6,
        struct _BRUSHOBJ *a7,
        struct _RECTL *a8,
        struct _RECTL *a9,
        struct _POINTL *a10,
        struct _POINTL *a11,
        char a12)
{
  DHPDEV dhpdev; // r14
  __int64 v15; // rbp
  struct _RECTL *v16; // rsi
  int v17; // eax
  unsigned __int8 v18; // r12
  unsigned int v19; // ebx
  unsigned int v20; // r15d
  unsigned int v21; // eax
  struct _BRUSHOBJ *v22; // rax
  int v23; // eax
  int v24; // eax
  struct tagCOLORADJUSTMENT *v25; // [rsp+28h] [rbp-A0h]
  struct _POINTL *v26; // [rsp+48h] [rbp-80h]
  __int128 v27; // [rsp+70h] [rbp-58h] BYREF
  __int64 v28; // [rsp+80h] [rbp-48h]

  dhpdev = a1->dhpdev;
  LODWORD(a6) = 0;
  if ( !dhpdev )
  {
    SetLastError(0xDu);
    return 0;
  }
  v15 = *((_QWORD *)dhpdev + 1);
  if ( !v15 || (v16 = a9) == 0 )
  {
    SetLastError(0xDu);
    return 2;
  }
  if ( *(_DWORD *)(v15 + 4464) )
    goto LABEL_8;
  v17 = *(_DWORD *)(v15 + 4428);
  if ( v17 >= 2 )
    return 2;
  *(_DWORD *)(v15 + 4428) = v17 + 1;
LABEL_8:
  if ( v16->right < v16->left || v16->bottom < v16->top )
  {
    v19 = 1;
  }
  else
  {
    v18 = a12;
    v19 = dwSimplifyROP(a2, a12, (unsigned int *)&a6);
    if ( !v19 )
    {
      v20 = (unsigned int)a6;
      if ( (_DWORD)a6 )
      {
        v19 = 1;
        if ( ((unsigned __int8)a6 & 1) != 0 || ((unsigned __int8)a6 & 0x40) != 0 || ((unsigned __int8)a6 & 6) == 2 )
        {
          v28 = 0;
          v27 = 0;
          if ( ((unsigned __int8)a6 & 1) != 0 || (v22 = a7) == 0 )
          {
            v23 = v27;
            if ( v18 == 0xFF )
              v23 = 0xFFFFFF;
            LODWORD(v27) = v23;
            v22 = (struct _BRUSHOBJ *)&v27;
          }
          v19 = (unsigned int)BPatternFill((struct _DEVOBJ *)dhpdev, v16, a4, v18, v22) == 0 ? 2 : 0;
        }
        else if ( v16->top >= 0 && v16->left >= 0 && v16->bottom >= 0 && v16->right >= 0 )
        {
          if ( a2 )
          {
            BChangeAndTrackObjectType((__int64)dhpdev, 2);
            if ( *((char *)dhpdev + 116) < 0 && (*(_BYTE *)(v15 + 4424) & 0x20) != 0 )
              PCL_SelectTransparency((__int64)dhpdev, 0, 1, 8);
            if ( *(_DWORD *)(*((_QWORD *)dhpdev + 1) + 4464LL) )
              v21 = DWColorPrinterCommonRoutine(a1, a2, a3, a4, a5, v25, a7, a8, v16, v26, a11, v18);
            else
              v21 = DWMonochromePrinterCommonRoutine(a1, a2, a3, a4, a5, v25, a7, a8, v16, a10, a11, v18, v20);
            v19 = v21;
          }
          else
          {
            v19 = 2;
          }
        }
      }
    }
  }
  if ( !*(_DWORD *)(*((_QWORD *)dhpdev + 1) + 4464LL) )
  {
    v24 = *(_DWORD *)(v15 + 4428);
    if ( v24 > 0 )
      *(_DWORD *)(v15 + 4428) = v24 - 1;
  }
  return v19;
}

```

## disassembly

```asm
0x18003dbfc  mov     rax, rsp
0x18003dbff  mov     [rax+20h], r9
0x18003dc03  mov     [rax+18h], r8
0x18003dc07  mov     [rax+8], rcx
0x18003dc0b  push    rbx
0x18003dc0c  push    rbp
0x18003dc0d  push    rsi
0x18003dc0e  push    r12
0x18003dc10  push    r13
0x18003dc12  push    r14
0x18003dc14  push    r15
0x18003dc16  sub     rsp, 90h
0x18003dc1d  mov     r14, [rcx+10h]
0x18003dc21  mov     r13, rdx
0x18003dc24  mov     dword ptr [rax+30h], 0
0x18003dc2b  test    r14, r14
0x18003dc2e  jnz     short loc_18003DC47
0x18003dc30  lea     ecx, [r14+0Dh]; dwErrCode
0x18003dc34  call    cs:__imp_SetLastError
0x18003dc3b  nop     dword ptr [rax+rax+00h]
0x18003dc40  xor     eax, eax
0x18003dc42  jmp     loc_18003DEB2
0x18003dc47  mov     rbp, [r14+8]
0x18003dc4b  test    rbp, rbp
0x18003dc4e  jz      loc_18003DE9C
0x18003dc54  mov     rsi, [rsp+0C8h+arg_40]
0x18003dc5c  test    rsi, rsi
0x18003dc5f  jz      loc_18003DE9C
0x18003dc65  cmp     dword ptr [rbp+1170h], 0
0x18003dc6c  jnz     short loc_18003DC85
0x18003dc6e  mov     eax, [rbp+114Ch]
0x18003dc74  cmp     eax, 2
0x18003dc77  jge     loc_18003DEAD
0x18003dc7d  inc     eax
0x18003dc7f  mov     [rbp+114Ch], eax
0x18003dc85  mov     eax, [rsi]
0x18003dc87  cmp     [rsi+8], eax
0x18003dc8a  jl      loc_18003DE74
0x18003dc90  mov     eax, [rsi+4]
0x18003dc93  cmp     [rsi+0Ch], eax
0x18003dc96  jl      loc_18003DE74
0x18003dc9c  mov     r12d, dword ptr [rsp+0C8h+arg_58]
0x18003dca4  lea     r8, [rsp+0C8h+arg_28]; unsigned int *
0x18003dcac  mov     edx, r12d; unsigned int
0x18003dcaf  mov     rcx, r13; struct _SURFOBJ *
0x18003dcb2  call    ?dwSimplifyROP@@YAKPEAU_SURFOBJ@@KPEAK@Z; dwSimplifyROP(_SURFOBJ *,ulong,ulong *)
0x18003dcb7  mov     ebx, eax
0x18003dcb9  test    eax, eax
0x18003dcbb  jnz     loc_18003DE79
0x18003dcc1  mov     r15d, dword ptr [rsp+0C8h+arg_28]
0x18003dcc9  test    r15d, r15d
0x18003dccc  jz      loc_18003DE79
0x18003dcd2  mov     ecx, r15d
0x18003dcd5  lea     ebx, [rax+1]
0x18003dcd8  and     ecx, ebx
0x18003dcda  jnz     loc_18003DE12
0x18003dce0  test    r15b, 40h
0x18003dce4  jnz     loc_18003DE12
0x18003dcea  mov     eax, r15d
0x18003dced  and     al, 6
0x18003dcef  cmp     al, 2
0x18003dcf1  jz      loc_18003DE12
0x18003dcf7  cmp     [rsi+4], ecx
0x18003dcfa  jl      loc_18003DE79
0x18003dd00  cmp     [rsi], ecx
0x18003dd02  jl      loc_18003DE79
0x18003dd08  cmp     [rsi+0Ch], ecx
0x18003dd0b  jl      loc_18003DE79
0x18003dd11  cmp     [rsi+8], ecx
0x18003dd14  jl      loc_18003DE79
0x18003dd1a  test    r13, r13
0x18003dd1d  jnz     short loc_18003DD27
0x18003dd1f  lea     ebx, [rcx+2]
0x18003dd22  jmp     loc_18003DE79
0x18003dd27  mov     edx, 2
0x18003dd2c  mov     rcx, r14
0x18003dd2f  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x18003dd34  test    byte ptr [r14+74h], 80h
0x18003dd39  jz      short loc_18003DD54
0x18003dd3b  test    byte ptr [rbp+1148h], 20h
0x18003dd42  jz      short loc_18003DD54
0x18003dd44  mov     r9b, 8
0x18003dd47  mov     r8d, ebx
0x18003dd4a  xor     edx, edx
0x18003dd4c  mov     rcx, r14
0x18003dd4f  call    ?PCL_SelectTransparency@@YAHPEAU_DEVOBJ@@W4ETransparency@@1E@Z; PCL_SelectTransparency(_DEVOBJ *,ETransparency,ETransparency,uchar)
0x18003dd54  mov     rax, [r14+8]
0x18003dd58  mov     rdx, r13; struct _SURFOBJ *
0x18003dd5b  mov     r9, [rsp+0C8h+arg_18]; struct _CLIPOBJ *
0x18003dd63  mov     r8, [rsp+0C8h+arg_10]; struct _SURFOBJ *
0x18003dd6b  mov     rcx, [rsp+0C8h+arg_0]; struct _SURFOBJ *
0x18003dd73  cmp     dword ptr [rax+1170h], 0
0x18003dd7a  mov     rax, [rsp+0C8h+arg_50]
0x18003dd82  jz      short loc_18003DDC1
0x18003dd84  mov     dword ptr [rsp+0C8h+var_70], r12d; unsigned int
0x18003dd89  mov     [rsp+0C8h+var_78], rax; struct _POINTL *
0x18003dd8e  mov     rax, [rsp+0C8h+arg_38]
0x18003dd96  mov     [rsp+0C8h+var_88], rsi; struct _RECTL *
0x18003dd9b  mov     [rsp+0C8h+var_90], rax; struct _RECTL *
0x18003dda0  mov     rax, [rsp+0C8h+arg_30]
0x18003dda8  mov     [rsp+0C8h+var_98], rax; struct _BRUSHOBJ *
0x18003ddad  mov     rax, [rsp+0C8h+arg_20]
0x18003ddb5  mov     [rsp+0C8h+var_A8], rax; struct _XLATEOBJ *
0x18003ddba  call    ?DWColorPrinterCommonRoutine@@YAKPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@6KK@Z; DWColorPrinterCommonRoutine(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,_POINTL *,ulong,ulong)
0x18003ddbf  jmp     short loc_18003DE0E
0x18003ddc1  mov     [rsp+0C8h+var_68], r15d; unsigned int
0x18003ddc6  mov     dword ptr [rsp+0C8h+var_70], r12d; char
0x18003ddcb  mov     [rsp+0C8h+var_78], rax; struct _POINTL *
0x18003ddd0  mov     rax, [rsp+0C8h+arg_48]
0x18003ddd8  mov     [rsp+0C8h+var_80], rax; struct _POINTL *
0x18003dddd  mov     rax, [rsp+0C8h+arg_38]
0x18003dde5  mov     [rsp+0C8h+var_88], rsi; struct _RECTL *
0x18003ddea  mov     [rsp+0C8h+var_90], rax; struct _RECTL *
0x18003ddef  mov     rax, [rsp+0C8h+arg_30]
0x18003ddf7  mov     [rsp+0C8h+var_98], rax; struct _BRUSHOBJ *
0x18003ddfc  mov     rax, [rsp+0C8h+arg_20]
0x18003de04  mov     [rsp+0C8h+var_A8], rax; struct _XLATEOBJ *
0x18003de09  call    ?DWMonochromePrinterCommonRoutine@@YAKPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@6KK@Z; DWMonochromePrinterCommonRoutine(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,_POINTL *,ulong,ulong)
0x18003de0e  mov     ebx, eax
0x18003de10  jmp     short loc_18003DE79
0x18003de12  xor     eax, eax
0x18003de14  xorps   xmm0, xmm0
0x18003de17  mov     [rsp+0C8h+var_48], rax
0x18003de1f  movups  [rsp+0C8h+var_58], xmm0
0x18003de24  test    ecx, ecx
0x18003de26  jnz     short loc_18003DE35
0x18003de28  mov     rax, [rsp+0C8h+arg_30]
0x18003de30  test    rax, rax
0x18003de33  jnz     short loc_18003DE4E
0x18003de35  mov     eax, dword ptr [rsp+0C8h+var_58]
0x18003de39  cmp     r12b, 0FFh
0x18003de3d  mov     ecx, 0FFFFFFh
0x18003de42  cmovz   eax, ecx
0x18003de45  mov     dword ptr [rsp+0C8h+var_58], eax
0x18003de49  lea     rax, [rsp+0C8h+var_58]
0x18003de4e  mov     r8, [rsp+0C8h+arg_18]; struct _CLIPOBJ *
0x18003de56  mov     r9d, r12d; unsigned int
0x18003de59  mov     rdx, rsi; struct _RECTL *
0x18003de5c  mov     [rsp+0C8h+var_A8], rax; struct _BRUSHOBJ *
0x18003de61  mov     rcx, r14; struct _DEVOBJ *
0x18003de64  call    ?BPatternFill@@YAHPEAU_DEVOBJ@@PEAU_RECTL@@PEAU_CLIPOBJ@@KPEAU_BRUSHOBJ@@PEAU_POINTL@@@Z; BPatternFill(_DEVOBJ *,_RECTL *,_CLIPOBJ *,ulong,_BRUSHOBJ *,_POINTL *)
0x18003de69  neg     eax
0x18003de6b  sbb     ebx, ebx
0x18003de6d  not     ebx
0x18003de6f  and     ebx, 2
0x18003de72  jmp     short loc_18003DE79
0x18003de74  mov     ebx, 1
0x18003de79  mov     rax, [r14+8]
0x18003de7d  cmp     dword ptr [rax+1170h], 0
0x18003de84  jnz     short loc_18003DE98
0x18003de86  mov     eax, [rbp+114Ch]
0x18003de8c  test    eax, eax
0x18003de8e  jle     short loc_18003DE98
0x18003de90  dec     eax
0x18003de92  mov     [rbp+114Ch], eax
0x18003de98  mov     eax, ebx
0x18003de9a  jmp     short loc_18003DEB2
0x18003de9c  mov     ecx, 0Dh; dwErrCode
0x18003dea1  call    cs:__imp_SetLastError
0x18003dea8  nop     dword ptr [rax+rax+00h]
0x18003dead  mov     eax, 2
0x18003deb2  add     rsp, 90h
0x18003deb9  pop     r15
0x18003debb  pop     r14
0x18003debd  pop     r13
0x18003debf  pop     r12
0x18003dec1  pop     rsi
0x18003dec2  pop     rbp
0x18003dec3  pop     rbx
0x18003dec4  retn
```
