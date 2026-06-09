# DWColorPrinterCommonRoutine(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,_POINTL *,ulong,ulong)

- ea: `0x180063a48`
- end: `0x180063bd4`
- name: `?DWColorPrinterCommonRoutine@@YAKPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@6KK@Z`
- size: `396`
- prototype: `unsigned int(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _BRUSHOBJ *, struct _RECTL *, struct _RECTL *, struct _POINTL *, struct _POINTL *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003ce0c`

## callees

- `0x18004048c`
- `0x180063494`
- `0x180063834`
- `0x180063a48`
- `0x180065fdc`
- `0x18006a0a8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180063bb4`
- `KERNEL32!SetLastError` at `0x180063bb4`

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
  struct _POINTL v18; // [rsp+50h] [rbp-10h] BYREF
  struct tagSIZE v19; // [rsp+80h] [rbp+20h] BYREF

  dhpdev = a1->dhpdev;
  a6 = 0;
  v19 = 0;
  v18 = 0;
  a10 = 0;
  if ( dhpdev && *((_QWORD *)dhpdev + 1) && a9 && a2 )
  {
    VGetOSBParams(a1, a2, a9, a8, (struct tagSIZE *)&a6, &v19, &v18, (struct _POINTL *)&a10);
    if ( !a3 )
    {
      SelectRop3((struct _DEVOBJ *)dhpdev, a12);
      if ( (unsigned int)BIsComplexClipPath(a4) )
      {
        v16 = ClipBitmapWithComplexClip(
                (struct _DEVOBJ *)dhpdev,
                a2,
                a7,
                &v18,
                (struct tagSIZE *)&a6,
                (struct _POINTL *)&a10,
                &v19,
                a4,
                a5,
                a11);
        return v16 == 0 ? 2 : 0;
      }
      if ( v19.cx * v19.cy <= (int)a6 * HIDWORD(a6) )
      {
        v16 = ClipBitmapWithRectangularClip(
                (struct _DEVOBJ *)dhpdev,
                a2,
                a7,
                &v18,
                (struct tagSIZE *)&a6,
                (struct _POINTL *)&a10,
                &v19,
                a4,
                a5,
                a11);
        return v16 == 0 ? 2 : 0;
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
0x180063a48  mov     r11, rsp
0x180063a4b  mov     [r11+10h], rbx
0x180063a4f  mov     [r11+18h], rsi
0x180063a53  push    rbp
0x180063a54  push    rdi
0x180063a55  push    r14
0x180063a57  mov     rbp, rsp
0x180063a5a  sub     rsp, 60h
0x180063a5e  mov     rbx, [rcx+10h]
0x180063a62  mov     rsi, r9
0x180063a65  mov     qword ptr [rbp+arg_28.cx], 0
0x180063a6d  mov     r14, r8
0x180063a70  mov     qword ptr [rbp+arg_0.cx], 0
0x180063a78  mov     rdi, rdx
0x180063a7b  mov     qword ptr [rbp+var_10.x], 0
0x180063a83  mov     qword ptr [rbp+arg_48.x], 0
0x180063a8b  test    rbx, rbx
0x180063a8e  jz      loc_180063BAF
0x180063a94  cmp     qword ptr [rbx+8], 0
0x180063a99  jz      loc_180063BAF
0x180063a9f  mov     r8, [rbp+arg_40]; struct _RECTL *
0x180063aa3  test    r8, r8
0x180063aa6  jz      loc_180063BAF
0x180063aac  test    rdx, rdx
0x180063aaf  jz      loc_180063BAF
0x180063ab5  mov     r9, [rbp+arg_38]; struct _RECTL *
0x180063ab9  lea     rax, [rbp+arg_48]
0x180063abd  mov     [r11-40h], rax
0x180063ac1  lea     rax, [rbp+var_10]
0x180063ac5  mov     [r11-48h], rax
0x180063ac9  lea     rax, [rbp+arg_0]
0x180063acd  mov     [r11-50h], rax
0x180063ad1  lea     rax, [rbp+arg_28]
0x180063ad5  mov     [r11-58h], rax
0x180063ad9  call    ?VGetOSBParams@@YAXPEAU_SURFOBJ@@0PEAU_RECTL@@1PEAUtagSIZE@@2PEAU_POINTL@@3@Z; VGetOSBParams(_SURFOBJ *,_SURFOBJ *,_RECTL *,_RECTL *,tagSIZE *,tagSIZE *,_POINTL *,_POINTL *)
0x180063ade  test    r14, r14
0x180063ae1  jnz     loc_180063BA8
0x180063ae7  movzx   edx, byte ptr [rbp+arg_58]; unsigned int
0x180063aeb  mov     rcx, rbx; struct _DEVOBJ *
0x180063aee  call    ?SelectRop3@@YAHPEAU_DEVOBJ@@K@Z; SelectRop3(_DEVOBJ *,ulong)
0x180063af3  mov     rcx, rsi; struct _CLIPOBJ *
0x180063af6  call    ?BIsComplexClipPath@@YAHPEAU_CLIPOBJ@@@Z; BIsComplexClipPath(_CLIPOBJ *)
0x180063afb  test    eax, eax
0x180063afd  jz      short loc_180063B4F
0x180063aff  mov     rax, [rbp+arg_50]
0x180063b03  lea     r9, [rbp+var_10]; struct _POINTL *
0x180063b07  mov     r8, [rbp+arg_30]; struct _BRUSHOBJ *
0x180063b0b  mov     rdx, rdi; struct _SURFOBJ *
0x180063b0e  mov     [rsp+60h+var_18], rax; struct _POINTL *
0x180063b13  mov     rcx, rbx; struct _DEVOBJ *
0x180063b16  mov     rax, [rbp+arg_20]
0x180063b1a  mov     [rsp+60h+var_20], rax; struct _XLATEOBJ *
0x180063b1f  lea     rax, [rbp+arg_0]
0x180063b23  mov     [rsp+60h+var_28], rsi; struct _CLIPOBJ *
0x180063b28  mov     [rsp+60h+var_30], rax; struct tagSIZE *
0x180063b2d  lea     rax, [rbp+arg_48]
0x180063b31  mov     [rsp+60h+var_38], rax; struct _POINTL *
0x180063b36  lea     rax, [rbp+arg_28]
0x180063b3a  mov     [rsp+60h+var_40], rax; struct tagSIZE *
0x180063b3f  call    ?ClipBitmapWithComplexClip@@YAHPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_BRUSHOBJ@@PEAU_POINTL@@PEAUtagSIZE@@34PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@3@Z; ClipBitmapWithComplexClip(_DEVOBJ *,_SURFOBJ *,_BRUSHOBJ *,_POINTL *,tagSIZE *,_POINTL *,tagSIZE *,_CLIPOBJ *,_XLATEOBJ *,_POINTL *)
0x180063b44  neg     eax
0x180063b46  sbb     eax, eax
0x180063b48  not     eax
0x180063b4a  and     eax, 2
0x180063b4d  jmp     short loc_180063BBF
0x180063b4f  mov     ecx, [rbp+arg_28.cy]
0x180063b52  mov     eax, [rbp+arg_0.cy]
0x180063b55  imul    ecx, [rbp+arg_28.cx]
0x180063b59  imul    eax, [rbp+arg_0.cx]
0x180063b5d  cmp     eax, ecx
0x180063b5f  jg      short loc_180063BA8
0x180063b61  mov     rax, [rbp+arg_50]
0x180063b65  lea     r9, [rbp+var_10]; struct _POINTL *
0x180063b69  mov     r8, [rbp+arg_30]; struct _BRUSHOBJ *
0x180063b6d  mov     rdx, rdi; struct _SURFOBJ *
0x180063b70  mov     [rsp+60h+var_18], rax; struct _POINTL *
0x180063b75  mov     rcx, rbx; struct _DEVOBJ *
0x180063b78  mov     rax, [rbp+arg_20]
0x180063b7c  mov     [rsp+60h+var_20], rax; struct _XLATEOBJ *
0x180063b81  lea     rax, [rbp+arg_0]
0x180063b85  mov     [rsp+60h+var_28], rsi; struct _CLIPOBJ *
0x180063b8a  mov     [rsp+60h+var_30], rax; struct tagSIZE *
0x180063b8f  lea     rax, [rbp+arg_48]
0x180063b93  mov     [rsp+60h+var_38], rax; struct _POINTL *
0x180063b98  lea     rax, [rbp+arg_28]
0x180063b9c  mov     [rsp+60h+var_40], rax; struct tagSIZE *
0x180063ba1  call    ?ClipBitmapWithRectangularClip@@YAHPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_BRUSHOBJ@@PEAU_POINTL@@PEAUtagSIZE@@34PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@3@Z; ClipBitmapWithRectangularClip(_DEVOBJ *,_SURFOBJ *,_BRUSHOBJ *,_POINTL *,tagSIZE *,_POINTL *,tagSIZE *,_CLIPOBJ *,_XLATEOBJ *,_POINTL *)
0x180063ba6  jmp     short loc_180063B44
0x180063ba8  mov     eax, 1
0x180063bad  jmp     short loc_180063BBF
0x180063baf  mov     ecx, 0Dh; dwErrCode
0x180063bb4  call    cs:__imp_SetLastError
0x180063bba  mov     eax, 2
0x180063bbf  lea     r11, [rsp+60h+var_s0]
0x180063bc4  mov     rbx, [r11+28h]
0x180063bc8  mov     rsi, [r11+30h]
0x180063bcc  mov     rsp, r11
0x180063bcf  pop     r14
0x180063bd1  pop     rdi
0x180063bd2  pop     rbp
0x180063bd3  retn
```
