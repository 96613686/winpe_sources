# DWColorPrinterCommonRoutine(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,_POINTL *,ulong,ulong)

- ea: `0x1800650d8`
- end: `0x18006526b`
- name: `?DWColorPrinterCommonRoutine@@YAKPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@6KK@Z`
- size: `403`
- prototype: `__int64 __fastcall(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _BRUSHOBJ *, struct _RECTL *, struct _RECTL *, struct _POINTL *, struct _POINTL *, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003dbfc`

## callees

- `0x180040e24`
- `0x180064ae4`
- `0x180064ea8`
- `0x1800650d8`
- `0x180067780`
- `0x18006b9b4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180065244`
- `KERNEL32!SetLastError` at `0x180065244`

## pseudocode

```c
__int64 __fastcall DWColorPrinterCommonRoutine(
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
        unsigned __int8 a12)
{
  DHPDEV dhpdev; // rbx
  int v16; // eax
  int v17; // eax
  struct _POINTL v19; // [rsp+50h] [rbp-10h] BYREF
  struct tagSIZE v20; // [rsp+80h] [rbp+20h] BYREF

  dhpdev = a1->dhpdev;
  a6 = 0;
  v20 = 0;
  v19 = 0;
  a10 = 0;
  if ( dhpdev && *((_QWORD *)dhpdev + 1) && a9 && a2 )
  {
    VGetOSBParams(a1, a2, a9, a8, (struct tagSIZE *)&a6, &v20, &v19, (struct _POINTL *)&a10);
    if ( !a3 )
    {
      SelectRop3((struct _DEVOBJ *)dhpdev, a12);
      LOBYTE(v16) = BIsComplexClipPath(a4);
      if ( v16 )
      {
        v17 = ClipBitmapWithComplexClip(
                (struct _DEVOBJ *)dhpdev,
                a2,
                a7,
                &v19,
                (struct tagSIZE *)&a6,
                (struct _POINTL *)&a10,
                &v20,
                a4,
                a5,
                a11);
        return v17 == 0 ? 2 : 0;
      }
      if ( v20.cx * v20.cy <= (int)a6 * HIDWORD(a6) )
      {
        v17 = ClipBitmapWithRectangularClip(
                (struct _DEVOBJ *)dhpdev,
                a2,
                a7,
                &v19,
                (struct tagSIZE *)&a6,
                (struct _POINTL *)&a10,
                &v20,
                a4,
                a5,
                a11);
        return v17 == 0 ? 2 : 0;
      }
    }
    return 1;
  }
  else
  {
    SetLastError(0xDu);
    return 2;
  }
}

```

## disassembly

```asm
0x1800650d8  mov     r11, rsp
0x1800650db  mov     [r11+10h], rbx
0x1800650df  mov     [r11+18h], rsi
0x1800650e3  push    rbp
0x1800650e4  push    rdi
0x1800650e5  push    r14
0x1800650e7  mov     rbp, rsp
0x1800650ea  sub     rsp, 60h
0x1800650ee  mov     rbx, [rcx+10h]
0x1800650f2  mov     rsi, r9
0x1800650f5  mov     qword ptr [rbp+arg_28.cx], 0
0x1800650fd  mov     r14, r8
0x180065100  mov     qword ptr [rbp+arg_0.cx], 0
0x180065108  mov     rdi, rdx
0x18006510b  mov     qword ptr [rbp+var_10.x], 0
0x180065113  mov     qword ptr [rbp+arg_48.x], 0
0x18006511b  test    rbx, rbx
0x18006511e  jz      loc_18006523F
0x180065124  cmp     qword ptr [rbx+8], 0
0x180065129  jz      loc_18006523F
0x18006512f  mov     r8, [rbp+arg_40]; struct _RECTL *
0x180065133  test    r8, r8
0x180065136  jz      loc_18006523F
0x18006513c  test    rdx, rdx
0x18006513f  jz      loc_18006523F
0x180065145  mov     r9, [rbp+arg_38]; struct _RECTL *
0x180065149  lea     rax, [rbp+arg_48]
0x18006514d  mov     [r11-40h], rax
0x180065151  lea     rax, [rbp+var_10]
0x180065155  mov     [r11-48h], rax
0x180065159  lea     rax, [rbp+arg_0]
0x18006515d  mov     [r11-50h], rax
0x180065161  lea     rax, [rbp+arg_28]
0x180065165  mov     [r11-58h], rax
0x180065169  call    ?VGetOSBParams@@YAXPEAU_SURFOBJ@@0PEAU_RECTL@@1PEAUtagSIZE@@2PEAU_POINTL@@3@Z; VGetOSBParams(_SURFOBJ *,_SURFOBJ *,_RECTL *,_RECTL *,tagSIZE *,tagSIZE *,_POINTL *,_POINTL *)
0x18006516e  test    r14, r14
0x180065171  jnz     loc_180065238
0x180065177  movzx   edx, byte ptr [rbp+arg_58]; unsigned int
0x18006517b  mov     rcx, rbx; struct _DEVOBJ *
0x18006517e  call    ?SelectRop3@@YAHPEAU_DEVOBJ@@K@Z; SelectRop3(_DEVOBJ *,ulong)
0x180065183  mov     rcx, rsi; struct _CLIPOBJ *
0x180065186  call    ?BIsComplexClipPath@@YAHPEAU_CLIPOBJ@@@Z; BIsComplexClipPath(_CLIPOBJ *)
0x18006518b  test    eax, eax
0x18006518d  jz      short loc_1800651DF
0x18006518f  mov     rax, [rbp+arg_50]
0x180065193  lea     r9, [rbp+var_10]; struct _POINTL *
0x180065197  mov     r8, [rbp+arg_30]; struct _BRUSHOBJ *
0x18006519b  mov     rdx, rdi; struct _SURFOBJ *
0x18006519e  mov     [rsp+60h+var_18], rax; struct _POINTL *
0x1800651a3  mov     rcx, rbx; struct _DEVOBJ *
0x1800651a6  mov     rax, [rbp+arg_20]
0x1800651aa  mov     [rsp+60h+var_20], rax; struct _XLATEOBJ *
0x1800651af  lea     rax, [rbp+arg_0]
0x1800651b3  mov     [rsp+60h+var_28], rsi; struct _CLIPOBJ *
0x1800651b8  mov     [rsp+60h+var_30], rax; struct tagSIZE *
0x1800651bd  lea     rax, [rbp+arg_48]
0x1800651c1  mov     [rsp+60h+var_38], rax; struct _POINTL *
0x1800651c6  lea     rax, [rbp+arg_28]
0x1800651ca  mov     [rsp+60h+var_40], rax; struct tagSIZE *
0x1800651cf  call    ?ClipBitmapWithComplexClip@@YAHPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_BRUSHOBJ@@PEAU_POINTL@@PEAUtagSIZE@@34PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@3@Z; ClipBitmapWithComplexClip(_DEVOBJ *,_SURFOBJ *,_BRUSHOBJ *,_POINTL *,tagSIZE *,_POINTL *,tagSIZE *,_CLIPOBJ *,_XLATEOBJ *,_POINTL *)
0x1800651d4  neg     eax
0x1800651d6  sbb     eax, eax
0x1800651d8  not     eax
0x1800651da  and     eax, 2
0x1800651dd  jmp     short loc_180065255
0x1800651df  mov     ecx, [rbp+arg_28.cy]
0x1800651e2  mov     eax, [rbp+arg_0.cy]
0x1800651e5  imul    ecx, [rbp+arg_28.cx]
0x1800651e9  imul    eax, [rbp+arg_0.cx]
0x1800651ed  cmp     eax, ecx
0x1800651ef  jg      short loc_180065238
0x1800651f1  mov     rax, [rbp+arg_50]
0x1800651f5  lea     r9, [rbp+var_10]; struct _POINTL *
0x1800651f9  mov     r8, [rbp+arg_30]; struct _BRUSHOBJ *
0x1800651fd  mov     rdx, rdi; struct _SURFOBJ *
0x180065200  mov     [rsp+60h+var_18], rax; struct _POINTL *
0x180065205  mov     rcx, rbx; struct _DEVOBJ *
0x180065208  mov     rax, [rbp+arg_20]
0x18006520c  mov     [rsp+60h+var_20], rax; struct _XLATEOBJ *
0x180065211  lea     rax, [rbp+arg_0]
0x180065215  mov     [rsp+60h+var_28], rsi; struct _CLIPOBJ *
0x18006521a  mov     [rsp+60h+var_30], rax; struct tagSIZE *
0x18006521f  lea     rax, [rbp+arg_48]
0x180065223  mov     [rsp+60h+var_38], rax; struct _POINTL *
0x180065228  lea     rax, [rbp+arg_28]
0x18006522c  mov     [rsp+60h+var_40], rax; struct tagSIZE *
0x180065231  call    ?ClipBitmapWithRectangularClip@@YAHPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_BRUSHOBJ@@PEAU_POINTL@@PEAUtagSIZE@@34PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@3@Z; ClipBitmapWithRectangularClip(_DEVOBJ *,_SURFOBJ *,_BRUSHOBJ *,_POINTL *,tagSIZE *,_POINTL *,tagSIZE *,_CLIPOBJ *,_XLATEOBJ *,_POINTL *)
0x180065236  jmp     short loc_1800651D4
0x180065238  mov     eax, 1
0x18006523d  jmp     short loc_180065255
0x18006523f  mov     ecx, 0Dh; dwErrCode
0x180065244  call    cs:__imp_SetLastError
0x18006524b  nop     dword ptr [rax+rax+00h]
0x180065250  mov     eax, 2
0x180065255  lea     r11, [rsp+60h+var_s0]
0x18006525a  mov     rbx, [r11+28h]
0x18006525e  mov     rsi, [r11+30h]
0x180065262  mov     rsp, r11
0x180065265  pop     r14
0x180065267  pop     rdi
0x180065268  pop     rbp
0x180065269  retn
```
