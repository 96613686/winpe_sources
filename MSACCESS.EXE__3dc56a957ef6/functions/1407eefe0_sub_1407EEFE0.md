# sub_1407EEFE0

- ea: `0x1407eefe0`
- end: `0x1407ef2f3`
- name: `sub_1407EEFE0`
- size: `787`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x14002991c`
- `0x1400324b0`
- `0x14004d530`
- `0x1400e2ae0`
- `0x1400e3abc`
- `0x14017e378`
- `0x1404099e0`
- `0x140409ab0`
- `0x1407eefe0`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1407ef12c`
- `KERNEL32!MulDiv` at `0x1407ef1f1`
- `KERNEL32!MulDiv` at `0x1407ef212`
- `KERNEL32!MulDiv` at `0x1407ef276`
- `KERNEL32!MulDiv` at `0x1407ef290`
- `KERNEL32!MulDiv` at `0x1407ef12c`
- `KERNEL32!MulDiv` at `0x1407ef1f1`
- `KERNEL32!MulDiv` at `0x1407ef212`
- `KERNEL32!MulDiv` at `0x1407ef276`
- `KERNEL32!MulDiv` at `0x1407ef290`
- `Mso98Win32Client!Mso98Win32Client_51744` at `0x1407ef25a`
- `Mso98Win32Client!Mso98Win32Client_51744` at `0x1407ef25a`
- `Mso30Win32Client!Mso30Win32Client_55947` at `0x1407ef1a9`
- `Mso30Win32Client!Mso30Win32Client_55947` at `0x1407ef1a9`
- `GDI32!GetDeviceCaps` at `0x1407ef0ec`
- `GDI32!GetDeviceCaps` at `0x1407ef101`
- `GDI32!GetDeviceCaps` at `0x1407ef0ec`
- `GDI32!GetDeviceCaps` at `0x1407ef101`
- `GDI32!DeleteObject` at `0x1407ef19a`
- `GDI32!DeleteObject` at `0x1407ef2bb`
- `GDI32!DeleteObject` at `0x1407ef19a`
- `GDI32!DeleteObject` at `0x1407ef2bb`
- `GDI32!CreateFontIndirectW` at `0x1407ef158`
- `GDI32!CreateFontIndirectW` at `0x1407ef158`

## pseudocode

```c
__int64 __fastcall sub_1407EEFE0(
        __int64 a1,
        wchar_t *a2,
        int a3,
        LONG a4,
        BYTE a5,
        BYTE a6,
        int a7,
        __int64 a8,
        int a9,
        _DWORD *a10,
        _DWORD *a11,
        _WORD *a12)
{
  HDC v14; // rdi
  int DeviceCaps; // r15d
  HFONT v16; // rax
  HFONT v17; // r14
  void *v18; // r12
  int v19; // ecx
  int v20; // ecx
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  int v24; // ebx
  int v26; // [rsp+40h] [rbp-C0h]
  int nDenominator[2]; // [rsp+48h] [rbp-B8h] BYREF
  LONG v28; // [rsp+50h] [rbp-B0h]
  _DWORD *v29; // [rsp+58h] [rbp-A8h]
  __int64 v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall *v32)(_QWORD, _QWORD, _QWORD); // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+78h] [rbp-88h]
  HDC v34; // [rsp+80h] [rbp-80h]
  int v35; // [rsp+88h] [rbp-78h]
  __int128 v36; // [rsp+90h] [rbp-70h] BYREF
  __int128 v37; // [rsp+A0h] [rbp-60h]
  __int128 v38; // [rsp+B0h] [rbp-50h]
  __int64 v39; // [rsp+C0h] [rbp-40h]
  int v40; // [rsp+C8h] [rbp-38h]
  LOGFONTW lf; // [rsp+D0h] [rbp-30h] BYREF

  v30 = a8;
  v29 = a11;
  v28 = a4;
  if ( (*(_BYTE *)(*(_QWORD *)&qword_140E339F8 + 120LL) & 1) != 0 && a2 )
  {
    *a12 = -1;
    v39 = 0;
    v36 = 0;
    v40 = 0;
    v37 = 0;
    v38 = 0;
    if ( !*a2 || (v14 = (HDC)sub_1404099E0(0, 0)) == 0 )
    {
      *a12 = 0;
      return 0;
    }
    v31 = 1;
    v32 = sub_140409AB0;
    v33 = 0;
    v34 = v14;
    v35 = 0;
    memset(&lf, 0, sizeof(lf));
    if ( (int)sub_14004D530((__int64)a2) > 31 )
    {
      *a12 = 0;
LABEL_7:
      sub_14017E378(&v31);
      return 0;
    }
    DeviceCaps = GetDeviceCaps(v14, 88);
    nDenominator[0] = DeviceCaps;
    v26 = GetDeviceCaps(v14, 90);
    sub_14002991C(a2, lf.lfFaceName, 32);
    lf.lfHeight = -MulDiv(a3, v26, 72);
    lf.lfWeight = v28;
    lf.lfItalic = a5;
    lf.lfUnderline = a6;
    lf.lfCharSet = 1;
    v16 = CreateFontIndirectW(&lf);
    v17 = v16;
    if ( !v16 )
    {
LABEL_9:
      sub_140409AB0(0, v14, 0);
      *a12 = 0;
      goto LABEL_7;
    }
    v18 = (void *)sub_1400324B0(v14, v16);
    if ( !v18 )
    {
LABEL_11:
      DeleteObject(v17);
      goto LABEL_9;
    }
    if ( !(unsigned int)Mso30Win32Client_55947(v14, &v36) )
    {
      sub_1400324B0(v14, v18);
      goto LABEL_11;
    }
    if ( a7 )
    {
      v19 = a7;
      if ( a7 >= a9 )
        v19 = a9;
      *a10 = (__int16)MulDiv(DWORD2(v37) * v19, 1440, DeviceCaps);
      if ( a7 > a9 )
        *a10 += MulDiv(DWORD1(v37) * (a7 - a9), 1440, nDenominator[0]);
      v20 = v36;
    }
    else
    {
      if ( !v30 )
      {
        *a12 = 0;
        goto LABEL_24;
      }
      *(_QWORD *)nDenominator = 0;
      v21 = sub_14004D530(v30);
      Mso98Win32Client_51744(v14, v22, v21, nDenominator, dword_140E1D698, 4, v23);
      v24 = LOWORD(nDenominator[1]);
      *a10 = (__int16)MulDiv(LOWORD(nDenominator[0]), 1440, DeviceCaps);
      v20 = v24;
    }
    *v29 = (__int16)MulDiv(v37 + v20, 1440, v26);
LABEL_24:
    sub_1400324B0(v14, v18);
    DeleteObject(v17);
    goto LABEL_7;
  }
  return 0;
}

```

## disassembly

```asm
0x1407eefe0  mov     [rsp-8+arg_0], rbx
0x1407eefe5  push    rbp
0x1407eefe6  push    rsi
0x1407eefe7  push    rdi
0x1407eefe8  push    r12
0x1407eefea  push    r13
0x1407eefec  push    r14
0x1407eefee  push    r15
0x1407eeff0  lea     rbp, [rsp-40h]
0x1407eeff5  sub     rsp, 140h
0x1407eeffc  mov     rax, cs:__security_cookie
0x1407ef003  xor     rax, rsp
0x1407ef006  mov     [rbp+70h+var_40], rax
0x1407ef00a  mov     rax, [rbp+70h+arg_38]
0x1407ef011  mov     r12d, r8d
0x1407ef014  mov     r13, [rbp+70h+arg_48]
0x1407ef01b  mov     rsi, rdx
0x1407ef01e  mov     rbx, [rbp+70h+arg_58]
0x1407ef025  mov     [rsp+170h+var_110], rax
0x1407ef02a  mov     rax, [rbp+70h+arg_50]
0x1407ef031  mov     [rsp+170h+var_118], rax
0x1407ef036  mov     rax, cs:qword_140E339F8
0x1407ef03d  mov     [rsp+170h+var_120], r9d
0x1407ef042  test    byte ptr [rax+78h], 1
0x1407ef046  jz      loc_1407EF2CA
0x1407ef04c  xor     r14d, r14d
0x1407ef04f  test    rdx, rdx
0x1407ef052  jz      loc_1407EF2CA
0x1407ef058  xor     eax, eax
0x1407ef05a  mov     word ptr [rbx], 0FFFFh
0x1407ef05f  xorps   xmm0, xmm0
0x1407ef062  mov     [rbp+70h+var_B0], rax
0x1407ef066  movups  [rbp+70h+var_E0], xmm0
0x1407ef06a  mov     [rbp+70h+var_A8], eax
0x1407ef06d  movups  [rbp+70h+var_D0], xmm0
0x1407ef071  movups  [rbp+70h+var_C0], xmm0
0x1407ef075  cmp     [rdx], r14w
0x1407ef079  jz      loc_1407EF2C6
0x1407ef07f  xor     edx, edx
0x1407ef081  xor     ecx, ecx
0x1407ef083  call    sub_1404099E0
0x1407ef088  mov     rdi, rax
0x1407ef08b  test    rax, rax
0x1407ef08e  jz      loc_1407EF2C6
0x1407ef094  lea     rax, sub_140409AB0
0x1407ef09b  mov     [rsp+170h+var_108], 1
0x1407ef0a3  xor     edx, edx; Val
0x1407ef0a5  mov     [rsp+170h+var_100], rax
0x1407ef0aa  lea     r8d, [r14+5Ch]; Size
0x1407ef0ae  mov     [rsp+170h+var_F8], r14
0x1407ef0b3  lea     rcx, [rbp+70h+lf]; void *
0x1407ef0b7  mov     [rbp+70h+var_F0], rdi
0x1407ef0bb  mov     [rbp+70h+var_E8], r14d
0x1407ef0bf  call    memset
0x1407ef0c4  mov     rcx, rsi
0x1407ef0c7  call    sub_14004D530
0x1407ef0cc  cmp     eax, 1Fh
0x1407ef0cf  jle     short loc_1407EF0E4
0x1407ef0d1  mov     [rbx], r14w
0x1407ef0d5  lea     rcx, [rsp+170h+var_108]
0x1407ef0da  call    sub_14017E378
0x1407ef0df  jmp     loc_1407EF2CA
0x1407ef0e4  mov     edx, 58h ; 'X'; index
0x1407ef0e9  mov     rcx, rdi; hdc
0x1407ef0ec  call    cs:GetDeviceCaps
0x1407ef0f2  mov     edx, 5Ah ; 'Z'; index
0x1407ef0f7  mov     rcx, rdi; hdc
0x1407ef0fa  mov     r15d, eax
0x1407ef0fd  mov     [rsp+170h+nDenominator], eax
0x1407ef101  call    cs:GetDeviceCaps
0x1407ef107  mov     r8d, 20h ; ' '
0x1407ef10d  lea     rdx, [rbp+70h+lf.lfFaceName]; Destination
0x1407ef111  mov     rcx, rsi; Source
0x1407ef114  mov     [rsp+170h+var_130], eax
0x1407ef118  mov     r14d, eax
0x1407ef11b  call    sub_14002991C
0x1407ef120  mov     r8d, 48h ; 'H'; nDenominator
0x1407ef126  mov     edx, r14d; nNumerator
0x1407ef129  mov     ecx, r12d; nNumber
0x1407ef12c  call    cs:MulDiv
0x1407ef132  mov     cl, [rbp+70h+arg_20]
0x1407ef138  neg     eax
0x1407ef13a  mov     [rbp+70h+lf.lfHeight], eax
0x1407ef13d  mov     eax, [rsp+170h+var_120]
0x1407ef141  mov     [rbp+70h+lf.lfWeight], eax
0x1407ef144  mov     al, [rbp+70h+arg_28]
0x1407ef14a  mov     [rbp+70h+lf.lfItalic], cl
0x1407ef14d  lea     rcx, [rbp+70h+lf]; lplf
0x1407ef151  mov     [rbp+70h+lf.lfUnderline], al
0x1407ef154  mov     [rbp+70h+lf.lfCharSet], 1
0x1407ef158  call    cs:CreateFontIndirectW
0x1407ef15e  xor     esi, esi
0x1407ef160  mov     r14, rax
0x1407ef163  test    rax, rax
0x1407ef166  jnz     short loc_1407EF17D
0x1407ef168  xor     r8d, r8d
0x1407ef16b  mov     rdx, rdi
0x1407ef16e  xor     ecx, ecx
0x1407ef170  call    sub_140409AB0
0x1407ef175  mov     [rbx], si
0x1407ef178  jmp     loc_1407EF0D5
0x1407ef17d  xor     r9d, r9d
0x1407ef180  mov     rdx, r14; h
0x1407ef183  mov     rcx, rdi; hdc
0x1407ef186  lea     r8d, [r9+3]
0x1407ef18a  call    sub_1400324B0
0x1407ef18f  mov     r12, rax
0x1407ef192  test    rax, rax
0x1407ef195  jnz     short loc_1407EF1A2
0x1407ef197  mov     rcx, r14; ho
0x1407ef19a  call    cs:DeleteObject
0x1407ef1a0  jmp     short loc_1407EF168
0x1407ef1a2  lea     rdx, [rbp+70h+var_E0]
0x1407ef1a6  mov     rcx, rdi
0x1407ef1a9  call    cs:Mso30Win32Client_55947
0x1407ef1af  xor     r8d, r8d
0x1407ef1b2  test    eax, eax
0x1407ef1b4  jnz     short loc_1407EF1CA
0x1407ef1b6  xor     r9d, r9d
0x1407ef1b9  lea     r8d, [rax+3]
0x1407ef1bd  mov     rdx, r12; h
0x1407ef1c0  mov     rcx, rdi; hdc
0x1407ef1c3  call    sub_1400324B0
0x1407ef1c8  jmp     short loc_1407EF197
0x1407ef1ca  mov     esi, [rbp+70h+arg_30]
0x1407ef1d0  test    esi, esi
0x1407ef1d2  jz      short loc_1407EF221
0x1407ef1d4  mov     ebx, [rbp+70h+arg_40]
0x1407ef1da  mov     ecx, esi
0x1407ef1dc  mov     r8d, r15d; nDenominator
0x1407ef1df  cmp     esi, ebx
0x1407ef1e1  mov     r15d, 5A0h
0x1407ef1e7  cmovge  ecx, ebx
0x1407ef1ea  mov     edx, r15d; nNumerator
0x1407ef1ed  imul    ecx, dword ptr [rbp+70h+var_D0+8]; nNumber
0x1407ef1f1  call    cs:MulDiv
0x1407ef1f7  movsx   edx, ax
0x1407ef1fa  mov     [r13+0], edx
0x1407ef1fe  cmp     esi, ebx
0x1407ef200  jle     short loc_1407EF21C
0x1407ef202  mov     r8d, [rsp+170h+nDenominator]; nDenominator
0x1407ef207  sub     esi, ebx
0x1407ef209  imul    esi, dword ptr [rbp+70h+var_D0+4]
0x1407ef20d  mov     edx, r15d; nNumerator
0x1407ef210  mov     ecx, esi; nNumber
0x1407ef212  call    cs:MulDiv
0x1407ef218  add     [r13+0], eax
0x1407ef21c  mov     ecx, dword ptr [rbp+70h+var_E0]
0x1407ef21f  jmp     short loc_1407EF285
0x1407ef221  mov     rdx, [rsp+170h+var_110]
0x1407ef226  test    rdx, rdx
0x1407ef229  jz      short loc_1407EF2A2
0x1407ef22b  mov     rcx, rdx
0x1407ef22e  mov     qword ptr [rsp+170h+nDenominator], r8
0x1407ef233  call    sub_14004D530
0x1407ef238  mov     ecx, cs:dword_140E1D698
0x1407ef23e  lea     r9, [rsp+170h+nDenominator]
0x1407ef243  mov     [rsp+170h+var_140], r8
0x1407ef248  mov     r8d, eax
0x1407ef24b  mov     [rsp+170h+var_148], 4
0x1407ef253  mov     [rsp+170h+var_150], ecx
0x1407ef257  mov     rcx, rdi
0x1407ef25a  call    cs:Mso98Win32Client_51744
0x1407ef260  movzx   ecx, word ptr [rsp+170h+nDenominator]; nNumber
0x1407ef265  mov     r8d, r15d; nDenominator
0x1407ef268  movzx   ebx, word ptr [rsp+170h+nDenominator+4]
0x1407ef26d  mov     r15d, 5A0h
0x1407ef273  mov     edx, r15d; nNumerator
0x1407ef276  call    cs:MulDiv
0x1407ef27c  movsx   ecx, ax
0x1407ef27f  mov     [r13+0], ecx
0x1407ef283  mov     ecx, ebx
0x1407ef285  add     ecx, dword ptr [rbp+70h+var_D0]; nNumber
0x1407ef288  mov     edx, r15d; nNumerator
0x1407ef28b  mov     r8d, [rsp+170h+var_130]; nDenominator
0x1407ef290  call    cs:MulDiv
0x1407ef296  movsx   ecx, ax
0x1407ef299  mov     rax, [rsp+170h+var_118]
0x1407ef29e  mov     [rax], ecx
0x1407ef2a0  jmp     short loc_1407EF2A6
0x1407ef2a2  mov     [rbx], r8w
0x1407ef2a6  xor     r9d, r9d
0x1407ef2a9  mov     rdx, r12; h
0x1407ef2ac  mov     rcx, rdi; hdc
0x1407ef2af  lea     r8d, [r9+3]
0x1407ef2b3  call    sub_1400324B0
0x1407ef2b8  mov     rcx, r14; ho
0x1407ef2bb  call    cs:DeleteObject
0x1407ef2c1  jmp     loc_1407EF0D5
0x1407ef2c6  mov     [rbx], r14w
0x1407ef2ca  xor     eax, eax
0x1407ef2cc  mov     rcx, [rbp+70h+var_40]
0x1407ef2d0  xor     rcx, rsp; StackCookie
0x1407ef2d3  call    __security_check_cookie
0x1407ef2d8  mov     rbx, [rsp+170h+arg_0]
0x1407ef2e0  add     rsp, 140h
0x1407ef2e7  pop     r15
0x1407ef2e9  pop     r14
0x1407ef2eb  pop     r13
0x1407ef2ed  pop     r12
0x1407ef2ef  pop     rdi
0x1407ef2f0  pop     rsi
0x1407ef2f1  pop     rbp
0x1407ef2f2  retn
```
