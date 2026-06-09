# dwCommonROPBlt(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,_POINTL *,ulong)

- ea: `0x18003ce0c`
- end: `0x18003d0c9`
- name: `?dwCommonROPBlt@@YAKPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@6K@Z`
- size: `701`
- prototype: `unsigned int(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _BRUSHOBJ *, struct _RECTL *, struct _RECTL *, struct _POINTL *, struct _POINTL *, unsigned int)`
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180062830`
- `0x180063d60`
- `0x180063f50`
- `0x180064100`
- `0x180064210`
- `0x1800681f8`

## callees

- `0x18003949c`
- `0x18003ce0c`
- `0x180063328`
- `0x180063a48`
- `0x180063bdc`
- `0x180065874`
- `0x1800680fc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18003ce44`
- `KERNEL32!SetLastError` at `0x18003d0ab`
- `KERNEL32!SetLastError` at `0x18003ce44`
- `KERNEL32!SetLastError` at `0x18003d0ab`

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
        unsigned int a12)
{
  DHPDEV dhpdev; // r14
  __int64 v15; // rbp
  struct _RECTL *v16; // rsi
  int v17; // eax
  unsigned int v18; // r12d
  unsigned int v19; // ebx
  unsigned int v20; // r15d
  unsigned int v21; // eax
  struct _BRUSHOBJ *v22; // rax
  int v23; // eax
  int v24; // eax
  struct _POINTL *v25; // [rsp+28h] [rbp-A0h]
  struct _POINTL *v26; // [rsp+48h] [rbp-80h]
  unsigned int v27; // [rsp+60h] [rbp-68h]
  __int128 v28; // [rsp+70h] [rbp-58h] BYREF
  __int64 v29; // [rsp+80h] [rbp-48h]

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
          v29 = 0;
          v28 = 0;
          if ( ((unsigned __int8)a6 & 1) != 0 || (v22 = a7) == 0 )
          {
            v23 = v28;
            if ( (_BYTE)v18 == 0xFF )
              v23 = 0xFFFFFF;
            LODWORD(v28) = v23;
            v22 = (struct _BRUSHOBJ *)&v28;
          }
          v19 = (unsigned int)BPatternFill((struct _DEVOBJ *)dhpdev, v16, a4, v18, v22, v25) == 0 ? 2 : 0;
        }
        else if ( v16->top >= 0 && v16->left >= 0 && v16->bottom >= 0 && v16->right >= 0 )
        {
          if ( a2 )
          {
            BChangeAndTrackObjectType(dhpdev, 2);
            if ( *((char *)dhpdev + 116) < 0 && (*(_BYTE *)(v15 + 4424) & 0x20) != 0 )
              PCL_SelectTransparency(dhpdev, 0, 1);
            if ( *(_DWORD *)(*((_QWORD *)dhpdev + 1) + 4464LL) )
              v21 = DWColorPrinterCommonRoutine(
                      a1,
                      a2,
                      a3,
                      a4,
                      a5,
                      (struct tagCOLORADJUSTMENT *)v25,
                      a7,
                      a8,
                      v16,
                      v26,
                      a11,
                      v18,
                      v27);
            else
              v21 = DWMonochromePrinterCommonRoutine(
                      a1,
                      a2,
                      a3,
                      a4,
                      a5,
                      (struct tagCOLORADJUSTMENT *)v25,
                      a7,
                      a8,
                      v16,
                      a10,
                      a11,
                      v18,
                      v20);
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
0x18003ce0c  mov     rax, rsp
0x18003ce0f  mov     [rax+20h], r9
0x18003ce13  mov     [rax+18h], r8
0x18003ce17  mov     [rax+8], rcx
0x18003ce1b  push    rbx
0x18003ce1c  push    rbp
0x18003ce1d  push    rsi
0x18003ce1e  push    r12
0x18003ce20  push    r13
0x18003ce22  push    r14
0x18003ce24  push    r15
0x18003ce26  sub     rsp, 90h
0x18003ce2d  mov     r14, [rcx+10h]
0x18003ce31  mov     r13, rdx
0x18003ce34  mov     dword ptr [rax+30h], 0
0x18003ce3b  test    r14, r14
0x18003ce3e  jnz     short loc_18003CE51
0x18003ce40  lea     ecx, [r14+0Dh]; dwErrCode
0x18003ce44  call    cs:__imp_SetLastError
0x18003ce4a  xor     eax, eax
0x18003ce4c  jmp     loc_18003D0B6
0x18003ce51  mov     rbp, [r14+8]
0x18003ce55  test    rbp, rbp
0x18003ce58  jz      loc_18003D0A6
0x18003ce5e  mov     rsi, [rsp+0C8h+arg_40]
0x18003ce66  test    rsi, rsi
0x18003ce69  jz      loc_18003D0A6
0x18003ce6f  cmp     dword ptr [rbp+1170h], 0
0x18003ce76  jnz     short loc_18003CE8F
0x18003ce78  mov     eax, [rbp+114Ch]
0x18003ce7e  cmp     eax, 2
0x18003ce81  jge     loc_18003D0B1
0x18003ce87  inc     eax
0x18003ce89  mov     [rbp+114Ch], eax
0x18003ce8f  mov     eax, [rsi]
0x18003ce91  cmp     [rsi+8], eax
0x18003ce94  jl      loc_18003D07E
0x18003ce9a  mov     eax, [rsi+4]
0x18003ce9d  cmp     [rsi+0Ch], eax
0x18003cea0  jl      loc_18003D07E
0x18003cea6  mov     r12d, dword ptr [rsp+0C8h+arg_58]
0x18003ceae  lea     r8, [rsp+0C8h+arg_28]; unsigned int *
0x18003ceb6  mov     edx, r12d; unsigned int
0x18003ceb9  mov     rcx, r13; struct _SURFOBJ *
0x18003cebc  call    ?dwSimplifyROP@@YAKPEAU_SURFOBJ@@KPEAK@Z; dwSimplifyROP(_SURFOBJ *,ulong,ulong *)
0x18003cec1  mov     ebx, eax
0x18003cec3  test    eax, eax
0x18003cec5  jnz     loc_18003D083
0x18003cecb  mov     r15d, dword ptr [rsp+0C8h+arg_28]
0x18003ced3  test    r15d, r15d
0x18003ced6  jz      loc_18003D083
0x18003cedc  mov     ecx, r15d
0x18003cedf  lea     ebx, [rax+1]
0x18003cee2  and     ecx, ebx
0x18003cee4  jnz     loc_18003D01C
0x18003ceea  test    r15b, 40h
0x18003ceee  jnz     loc_18003D01C
0x18003cef4  mov     eax, r15d
0x18003cef7  and     al, 6
0x18003cef9  cmp     al, 2
0x18003cefb  jz      loc_18003D01C
0x18003cf01  cmp     [rsi+4], ecx
0x18003cf04  jl      loc_18003D083
0x18003cf0a  cmp     [rsi], ecx
0x18003cf0c  jl      loc_18003D083
0x18003cf12  cmp     [rsi+0Ch], ecx
0x18003cf15  jl      loc_18003D083
0x18003cf1b  cmp     [rsi+8], ecx
0x18003cf1e  jl      loc_18003D083
0x18003cf24  test    r13, r13
0x18003cf27  jnz     short loc_18003CF31
0x18003cf29  lea     ebx, [rcx+2]
0x18003cf2c  jmp     loc_18003D083
0x18003cf31  mov     edx, 2
0x18003cf36  mov     rcx, r14
0x18003cf39  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x18003cf3e  test    byte ptr [r14+74h], 80h
0x18003cf43  jz      short loc_18003CF5E
0x18003cf45  test    byte ptr [rbp+1148h], 20h
0x18003cf4c  jz      short loc_18003CF5E
0x18003cf4e  mov     r9b, 8
0x18003cf51  mov     r8d, ebx
0x18003cf54  xor     edx, edx
0x18003cf56  mov     rcx, r14
0x18003cf59  call    ?PCL_SelectTransparency@@YAHPEAU_DEVOBJ@@W4ETransparency@@1E@Z; PCL_SelectTransparency(_DEVOBJ *,ETransparency,ETransparency,uchar)
0x18003cf5e  mov     rax, [r14+8]
0x18003cf62  mov     rdx, r13; struct _SURFOBJ *
0x18003cf65  mov     r9, [rsp+0C8h+arg_18]; struct _CLIPOBJ *
0x18003cf6d  mov     r8, [rsp+0C8h+arg_10]; struct _SURFOBJ *
0x18003cf75  mov     rcx, [rsp+0C8h+arg_0]; struct _SURFOBJ *
0x18003cf7d  cmp     dword ptr [rax+1170h], 0
0x18003cf84  mov     rax, [rsp+0C8h+arg_50]
0x18003cf8c  jz      short loc_18003CFCB
0x18003cf8e  mov     dword ptr [rsp+0C8h+var_70], r12d; unsigned int
0x18003cf93  mov     [rsp+0C8h+var_78], rax; struct _POINTL *
0x18003cf98  mov     rax, [rsp+0C8h+arg_38]
0x18003cfa0  mov     [rsp+0C8h+var_88], rsi; struct _RECTL *
0x18003cfa5  mov     [rsp+0C8h+var_90], rax; struct _RECTL *
0x18003cfaa  mov     rax, [rsp+0C8h+arg_30]
0x18003cfb2  mov     [rsp+0C8h+var_98], rax; struct _BRUSHOBJ *
0x18003cfb7  mov     rax, [rsp+0C8h+arg_20]
0x18003cfbf  mov     [rsp+0C8h+var_A8], rax; struct _XLATEOBJ *
0x18003cfc4  call    ?DWColorPrinterCommonRoutine@@YAKPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@6KK@Z; DWColorPrinterCommonRoutine(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,_POINTL *,ulong,ulong)
0x18003cfc9  jmp     short loc_18003D018
0x18003cfcb  mov     [rsp+0C8h+var_68], r15d; unsigned int
0x18003cfd0  mov     dword ptr [rsp+0C8h+var_70], r12d; char
0x18003cfd5  mov     [rsp+0C8h+var_78], rax; struct _POINTL *
0x18003cfda  mov     rax, [rsp+0C8h+arg_48]
0x18003cfe2  mov     [rsp+0C8h+var_80], rax; struct _POINTL *
0x18003cfe7  mov     rax, [rsp+0C8h+arg_38]
0x18003cfef  mov     [rsp+0C8h+var_88], rsi; struct _RECTL *
0x18003cff4  mov     [rsp+0C8h+var_90], rax; struct _RECTL *
0x18003cff9  mov     rax, [rsp+0C8h+arg_30]
0x18003d001  mov     [rsp+0C8h+var_98], rax; struct _BRUSHOBJ *
0x18003d006  mov     rax, [rsp+0C8h+arg_20]
0x18003d00e  mov     [rsp+0C8h+var_A8], rax; struct _XLATEOBJ *
0x18003d013  call    ?DWMonochromePrinterCommonRoutine@@YAKPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@6KK@Z; DWMonochromePrinterCommonRoutine(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,_POINTL *,ulong,ulong)
0x18003d018  mov     ebx, eax
0x18003d01a  jmp     short loc_18003D083
0x18003d01c  xor     eax, eax
0x18003d01e  xorps   xmm0, xmm0
0x18003d021  mov     [rsp+0C8h+var_48], rax
0x18003d029  movups  [rsp+0C8h+var_58], xmm0
0x18003d02e  test    ecx, ecx
0x18003d030  jnz     short loc_18003D03F
0x18003d032  mov     rax, [rsp+0C8h+arg_30]
0x18003d03a  test    rax, rax
0x18003d03d  jnz     short loc_18003D058
0x18003d03f  mov     eax, dword ptr [rsp+0C8h+var_58]
0x18003d043  cmp     r12b, 0FFh
0x18003d047  mov     ecx, 0FFFFFFh
0x18003d04c  cmovz   eax, ecx
0x18003d04f  mov     dword ptr [rsp+0C8h+var_58], eax
0x18003d053  lea     rax, [rsp+0C8h+var_58]
0x18003d058  mov     r8, [rsp+0C8h+arg_18]; struct _CLIPOBJ *
0x18003d060  mov     r9d, r12d; unsigned int
0x18003d063  mov     rdx, rsi; struct _RECTL *
0x18003d066  mov     [rsp+0C8h+var_A8], rax; struct _BRUSHOBJ *
0x18003d06b  mov     rcx, r14; struct _DEVOBJ *
0x18003d06e  call    ?BPatternFill@@YAHPEAU_DEVOBJ@@PEAU_RECTL@@PEAU_CLIPOBJ@@KPEAU_BRUSHOBJ@@PEAU_POINTL@@@Z; BPatternFill(_DEVOBJ *,_RECTL *,_CLIPOBJ *,ulong,_BRUSHOBJ *,_POINTL *)
0x18003d073  neg     eax
0x18003d075  sbb     ebx, ebx
0x18003d077  not     ebx
0x18003d079  and     ebx, 2
0x18003d07c  jmp     short loc_18003D083
0x18003d07e  mov     ebx, 1
0x18003d083  mov     rax, [r14+8]
0x18003d087  cmp     dword ptr [rax+1170h], 0
0x18003d08e  jnz     short loc_18003D0A2
0x18003d090  mov     eax, [rbp+114Ch]
0x18003d096  test    eax, eax
0x18003d098  jle     short loc_18003D0A2
0x18003d09a  dec     eax
0x18003d09c  mov     [rbp+114Ch], eax
0x18003d0a2  mov     eax, ebx
0x18003d0a4  jmp     short loc_18003D0B6
0x18003d0a6  mov     ecx, 0Dh; dwErrCode
0x18003d0ab  call    cs:__imp_SetLastError
0x18003d0b1  mov     eax, 2
0x18003d0b6  add     rsp, 90h
0x18003d0bd  pop     r15
0x18003d0bf  pop     r14
0x18003d0c1  pop     r13
0x18003d0c3  pop     r12
0x18003d0c5  pop     rsi
0x18003d0c6  pop     rbp
0x18003d0c7  pop     rbx
0x18003d0c8  retn
```
