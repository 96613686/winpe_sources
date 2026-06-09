# GameInputServerDevice::LogDeviceCreated(void)

- ea: `0x18003ca44`
- end: `0x18003ccc6`
- name: `?LogDeviceCreated@GameInputServerDevice@@AEAAXXZ`
- size: `642`
- prototype: `void __fastcall(GameInputServerDevice *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180030308`
- `0x180030ee0`
- `0x18003197c`

## callees

- `0x180001414`
- `0x18003ca44`
- `0x18004c8e0`

## string_xrefs

- `0x18003cc4f`: `GameInputServerDevice: Created device`

## pseudocode

```c
void __fastcall GameInputServerDevice::LogDeviceCreated(GameInputServerDevice *this)
{
  __int64 v1; // rdx
  char v2; // [rsp+30h] [rbp-D0h] BYREF
  char v3; // [rsp+31h] [rbp-CFh] BYREF
  __int16 v4; // [rsp+32h] [rbp-CEh] BYREF
  __int16 v5; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v6; // [rsp+36h] [rbp-CAh] BYREF
  __int16 v7; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v8; // [rsp+3Ah] [rbp-C6h] BYREF
  __int16 v9; // [rsp+3Ch] [rbp-C4h] BYREF
  __int16 v10; // [rsp+3Eh] [rbp-C2h] BYREF
  __int16 v11; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v12; // [rsp+42h] [rbp-BEh] BYREF
  __int16 v13; // [rsp+44h] [rbp-BCh] BYREF
  __int16 v14; // [rsp+46h] [rbp-BAh] BYREF
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  int v16; // [rsp+4Ch] [rbp-B4h] BYREF
  int v17; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v19[32]; // [rsp+60h] [rbp-A0h] BYREF
  const char *v20; // [rsp+80h] [rbp-80h]
  __int64 v21; // [rsp+88h] [rbp-78h]
  int *v22; // [rsp+90h] [rbp-70h]
  __int64 v23; // [rsp+98h] [rbp-68h]
  const char *v24; // [rsp+A0h] [rbp-60h]
  __int64 v25; // [rsp+A8h] [rbp-58h]
  __int16 *v26; // [rsp+B0h] [rbp-50h]
  __int64 v27; // [rsp+B8h] [rbp-48h]
  __int16 *v28; // [rsp+C0h] [rbp-40h]
  __int64 v29; // [rsp+C8h] [rbp-38h]
  __int16 *v30; // [rsp+D0h] [rbp-30h]
  __int64 v31; // [rsp+D8h] [rbp-28h]
  char *v32; // [rsp+E0h] [rbp-20h]
  __int64 v33; // [rsp+E8h] [rbp-18h]
  char *v34; // [rsp+F0h] [rbp-10h]
  __int64 v35; // [rsp+F8h] [rbp-8h]
  int *v36; // [rsp+100h] [rbp+0h]
  __int64 v37; // [rsp+108h] [rbp+8h]
  int *v38; // [rsp+110h] [rbp+10h]
  __int64 v39; // [rsp+118h] [rbp+18h]
  int *v40; // [rsp+120h] [rbp+20h]
  __int64 v41; // [rsp+128h] [rbp+28h]
  __int16 *v42; // [rsp+130h] [rbp+30h]
  __int64 v43; // [rsp+138h] [rbp+38h]
  __int16 *v44; // [rsp+140h] [rbp+40h]
  __int64 v45; // [rsp+148h] [rbp+48h]
  __int16 *v46; // [rsp+150h] [rbp+50h]
  __int64 v47; // [rsp+158h] [rbp+58h]
  __int16 *v48; // [rsp+160h] [rbp+60h]
  __int64 v49; // [rsp+168h] [rbp+68h]
  __int16 *v50; // [rsp+170h] [rbp+70h]
  __int64 v51; // [rsp+178h] [rbp+78h]
  __int16 *v52; // [rsp+180h] [rbp+80h]
  __int64 v53; // [rsp+188h] [rbp+88h]
  __int16 *v54; // [rsp+190h] [rbp+90h]
  __int64 v55; // [rsp+198h] [rbp+98h]
  __int16 *v56; // [rsp+1A0h] [rbp+A0h]
  __int64 v57; // [rsp+1A8h] [rbp+A8h]

  v1 = *((_QWORD *)this + 11);
  if ( (unsigned int)dword_180069000 > 4
    && (qword_180069010 & 0x400) != 0
    && (qword_180069018 & 0x400) == qword_180069018 )
  {
    v4 = *(_WORD *)(v1 + 30);
    v5 = *(_WORD *)(v1 + 28);
    v6 = *(_WORD *)(v1 + 26);
    v7 = *(_WORD *)(v1 + 24);
    v8 = *(_WORD *)(v1 + 22);
    v9 = *(_WORD *)(v1 + 20);
    v10 = *(_WORD *)(v1 + 18);
    v11 = *(_WORD *)(v1 + 16);
    v15 = *(_DWORD *)(v1 + 104);
    v16 = *(_DWORD *)(v1 + 100);
    v17 = *(_DWORD *)(v1 + 96);
    v2 = *(_BYTE *)(v1 + 11);
    v3 = *(_BYTE *)(v1 + 10);
    v12 = *(_WORD *)(v1 + 8);
    v13 = *(_WORD *)(v1 + 6);
    v14 = *(_WORD *)(v1 + 4);
    v56 = &v4;
    v54 = &v5;
    v52 = &v6;
    v50 = &v7;
    v48 = &v8;
    v46 = &v9;
    v44 = &v10;
    v42 = &v11;
    v40 = &v15;
    v38 = &v16;
    v36 = &v17;
    v34 = &v2;
    v32 = &v3;
    v30 = &v12;
    v28 = &v13;
    v26 = &v14;
    v18 = 2917;
    v57 = 2;
    v55 = 2;
    v53 = 2;
    v51 = 2;
    v49 = 2;
    v47 = 2;
    v45 = 2;
    v43 = 2;
    v41 = 4;
    v39 = 4;
    v37 = 4;
    v35 = 1;
    v33 = 1;
    v31 = 2;
    v29 = 2;
    v27 = 2;
    v23 = 4;
    v24 = "GameInputServerDevice: Created device";
    v25 = 38;
    v22 = &v18;
    v21 = 56;
    v20 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
    tlgWriteTransfer_GameInputEventWriteTransfer(
      (__int64)&dword_180069000,
      (unsigned __int8 *)byte_18006110D,
      0,
      0,
      21,
      (__int64)v19);
  }
}

```

## disassembly

```asm
0x18003ca44  push    rbp
0x18003ca46  lea     rbp, [rsp-0C0h]
0x18003ca4e  sub     rsp, 1C0h
0x18003ca55  mov     rax, cs:__security_cookie
0x18003ca5c  xor     rax, rsp
0x18003ca5f  mov     [rbp+0C0h+var_10], rax
0x18003ca66  mov     eax, cs:dword_180069000
0x18003ca6c  mov     r9d, 4
0x18003ca72  mov     rdx, [rcx+58h]
0x18003ca76  cmp     eax, r9d
0x18003ca79  jbe     loc_18003CCAD
0x18003ca7f  mov     rcx, cs:qword_180069018
0x18003ca86  mov     r8d, 400h
0x18003ca8c  mov     rax, cs:qword_180069010
0x18003ca93  test    r8, rax
0x18003ca96  jz      loc_18003CCAD
0x18003ca9c  mov     rax, rcx
0x18003ca9f  and     rax, r8
0x18003caa2  cmp     rax, rcx
0x18003caa5  jnz     loc_18003CCAD
0x18003caab  movzx   eax, word ptr [rdx+1Eh]
0x18003caaf  mov     [rsp+1C0h+var_18E], ax
0x18003cab4  movzx   eax, word ptr [rdx+1Ch]
0x18003cab8  mov     [rsp+1C0h+var_18C], ax
0x18003cabd  movzx   eax, word ptr [rdx+1Ah]
0x18003cac1  mov     [rsp+1C0h+var_18A], ax
0x18003cac6  movzx   eax, word ptr [rdx+18h]
0x18003caca  mov     [rsp+1C0h+var_188], ax
0x18003cacf  movzx   eax, word ptr [rdx+16h]
0x18003cad3  mov     [rsp+1C0h+var_186], ax
0x18003cad8  movzx   eax, word ptr [rdx+14h]
0x18003cadc  mov     [rsp+1C0h+var_184], ax
0x18003cae1  movzx   eax, word ptr [rdx+12h]
0x18003cae5  mov     [rsp+1C0h+var_182], ax
0x18003caea  movzx   eax, word ptr [rdx+10h]
0x18003caee  mov     [rsp+1C0h+var_180], ax
0x18003caf3  mov     eax, [rdx+68h]
0x18003caf6  mov     [rsp+1C0h+var_178], eax
0x18003cafa  mov     eax, [rdx+64h]
0x18003cafd  mov     [rsp+1C0h+var_174], eax
0x18003cb01  mov     eax, [rdx+60h]
0x18003cb04  mov     [rsp+1C0h+var_170], eax
0x18003cb08  mov     al, [rdx+0Bh]
0x18003cb0b  mov     [rsp+1C0h+var_190], al
0x18003cb0f  mov     al, [rdx+0Ah]
0x18003cb12  mov     [rsp+1C0h+var_18F], al
0x18003cb16  movzx   eax, word ptr [rdx+8]
0x18003cb1a  mov     [rsp+1C0h+var_17E], ax
0x18003cb1f  movzx   eax, word ptr [rdx+6]
0x18003cb23  mov     [rsp+1C0h+var_17C], ax
0x18003cb28  movzx   eax, word ptr [rdx+4]
0x18003cb2c  mov     [rsp+1C0h+var_17A], ax
0x18003cb31  lea     rax, [rsp+1C0h+var_18E]
0x18003cb36  mov     [rbp+0C0h+var_20], rax
0x18003cb3d  lea     rax, [rsp+1C0h+var_18C]
0x18003cb42  mov     [rbp+0C0h+var_30], rax
0x18003cb49  lea     rax, [rsp+1C0h+var_18A]
0x18003cb4e  mov     [rbp+0C0h+var_40], rax
0x18003cb55  lea     rax, [rsp+1C0h+var_188]
0x18003cb5a  mov     [rbp+0C0h+var_50], rax
0x18003cb5e  lea     rax, [rsp+1C0h+var_186]
0x18003cb63  mov     [rbp+0C0h+var_60], rax
0x18003cb67  lea     rax, [rsp+1C0h+var_184]
0x18003cb6c  mov     [rbp+0C0h+var_70], rax
0x18003cb70  lea     rax, [rsp+1C0h+var_182]
0x18003cb75  mov     [rbp+0C0h+var_80], rax
0x18003cb79  lea     rax, [rsp+1C0h+var_180]
0x18003cb7e  mov     [rbp+0C0h+var_90], rax
0x18003cb82  lea     rax, [rsp+1C0h+var_178]
0x18003cb87  mov     [rbp+0C0h+var_A0], rax
0x18003cb8b  lea     rax, [rsp+1C0h+var_174]
0x18003cb90  mov     [rbp+0C0h+var_B0], rax
0x18003cb94  lea     rax, [rsp+1C0h+var_170]
0x18003cb99  mov     [rbp+0C0h+var_C0], rax
0x18003cb9d  lea     rax, [rsp+1C0h+var_190]
0x18003cba2  mov     [rbp+0C0h+var_D0], rax
0x18003cba6  lea     rax, [rsp+1C0h+var_18F]
0x18003cbab  mov     [rbp+0C0h+var_E0], rax
0x18003cbaf  lea     rax, [rsp+1C0h+var_17E]
0x18003cbb4  mov     [rbp+0C0h+var_F0], rax
0x18003cbb8  lea     rax, [rsp+1C0h+var_17C]
0x18003cbbd  mov     [rbp+0C0h+var_100], rax
0x18003cbc1  lea     rax, [rsp+1C0h+var_17A]
0x18003cbc6  mov     [rbp+0C0h+var_110], rax
0x18003cbca  mov     [rsp+1C0h+var_16C], 0B65h
0x18003cbd2  mov     [rbp+0C0h+var_18], 2
0x18003cbdd  mov     [rbp+0C0h+var_28], 2
0x18003cbe8  mov     [rbp+0C0h+var_38], 2
0x18003cbf3  mov     [rbp+0C0h+var_48], 2
0x18003cbfb  mov     [rbp+0C0h+var_58], 2
0x18003cc03  mov     [rbp+0C0h+var_68], 2
0x18003cc0b  mov     [rbp+0C0h+var_78], 2
0x18003cc13  mov     [rbp+0C0h+var_88], 2
0x18003cc1b  mov     [rbp+0C0h+var_98], r9
0x18003cc1f  mov     [rbp+0C0h+var_A8], r9
0x18003cc23  mov     [rbp+0C0h+var_B8], r9
0x18003cc27  mov     [rbp+0C0h+var_C8], 1
0x18003cc2f  mov     [rbp+0C0h+var_D8], 1
0x18003cc37  mov     [rbp+0C0h+var_E8], 2
0x18003cc3f  mov     [rbp+0C0h+var_F8], 2
0x18003cc47  mov     [rbp+0C0h+var_108], 2
0x18003cc4f  lea     rax, aGameinputserve_0; "GameInputServerDevice: Created device"
0x18003cc56  mov     [rbp+0C0h+var_128], r9
0x18003cc5a  mov     [rbp+0C0h+var_120], rax
0x18003cc5e  lea     rdx, byte_18006110D
0x18003cc65  lea     rax, [rsp+1C0h+var_16C]
0x18003cc6a  mov     [rbp+0C0h+var_118], 26h ; '&'
0x18003cc72  mov     [rbp+0C0h+var_130], rax
0x18003cc76  lea     rcx, dword_180069000
0x18003cc7d  lea     rax, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x18003cc84  mov     [rbp+0C0h+var_138], 38h ; '8'
0x18003cc8c  mov     [rbp+0C0h+var_140], rax
0x18003cc90  xor     r9d, r9d
0x18003cc93  lea     rax, [rsp+1C0h+var_160]
0x18003cc98  xor     r8d, r8d
0x18003cc9b  mov     [rsp+1C0h+var_198], rax
0x18003cca0  mov     [rsp+1C0h+var_1A0], 15h
0x18003cca8  call    _tlgWriteTransfer_GameInputEventWriteTransfer
0x18003ccad  mov     rcx, [rbp+0C0h+var_10]
0x18003ccb4  xor     rcx, rsp; StackCookie
0x18003ccb7  call    __security_check_cookie
0x18003ccbc  add     rsp, 1C0h
0x18003ccc3  pop     rbp
0x18003ccc4  retn
```
