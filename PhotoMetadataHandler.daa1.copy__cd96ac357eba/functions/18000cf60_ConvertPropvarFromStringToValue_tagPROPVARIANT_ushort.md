# ConvertPropvarFromStringToValue(tagPROPVARIANT *,ushort)

- ea: `0x18000cf60`
- end: `0x18000d176`
- name: `?ConvertPropvarFromStringToValue@@YAJPEAUtagPROPVARIANT@@G@Z`
- size: `534`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar, unsigned __int16)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001f40c`
- `0x18001f724`

## callees

- `0x18000cf60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000d111`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000d12e`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000d111`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000d12e`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000d0da`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000d0f7`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000d0da`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000d0f7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18000cfee`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18000cfee`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000cfd2`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000d099`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000cfd2`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000d099`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000cfe1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d01f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d0ac`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d13d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000cfe1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d01f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d0ac`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d13d`

## pseudocode

```c
__int64 __fastcall ConvertPropvarFromStringToValue(PROPVARIANT *pvar, unsigned __int16 a2)
{
  int v3; // esi
  unsigned int v4; // ebx
  double v6; // xmm0_8
  double v7; // xmm1_8
  double v8; // xmm1_8
  LONG v9; // eax
  LARGE_INTEGER hVal; // rcx
  LARGE_INTEGER v11; // rcx
  SHORT v12; // ax
  const char *v13; // rcx
  const char *pszVal; // rcx
  PROPVARIANT pvarDest; // [rsp+20h] [rbp-28h] BYREF

  v3 = a2;
  if ( pvar->vt != 19 )
  {
    v4 = -2147418113;
    switch ( pvar->vt )
    {
      case 2u:
      case 3u:
      case 0x10u:
      case 0x11u:
      case 0x12u:
        return 0;
      case 0x1Eu:
        memset(&pvarDest, 0, sizeof(pvarDest));
        v4 = PropVariantCopy(&pvarDest, pvar);
        if ( (v4 & 0x80000000) != 0 )
          return v4;
        PropVariantClear(pvar);
        switch ( v3 )
        {
          case 2:
            pszVal = pvarDest.pszVal;
            pvar->vt = 2;
            v12 = strtol(pszVal, 0, 10);
            break;
          case 3:
            v13 = pvarDest.pszVal;
            pvar->vt = 3;
            pvar->lVal = strtol(v13, 0, 10);
            goto LABEL_27;
          case 19:
            hVal = pvarDest.hVal;
            pvar->vt = 19;
            pvar->lVal = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))_o_strtoul)(
                           (LARGE_INTEGER)hVal.QuadPart,
                           0,
                           10);
            goto LABEL_27;
          default:
            v11 = pvarDest.hVal;
            pvar->vt = 18;
            v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))_o_strtoul)((LARGE_INTEGER)v11.QuadPart, 0, 10);
            break;
        }
        pvar->iVal = v12;
LABEL_27:
        PropVariantClear(&pvarDest);
        return v4;
      case 0x1Fu:
        memset(&pvarDest, 0, sizeof(pvarDest));
        v4 = PropVariantCopy(&pvarDest, pvar);
        if ( (v4 & 0x80000000) != 0 )
          return v4;
        PropVariantClear(pvar);
        v6 = ((double (__fastcall *)(_QWORD, _QWORD))_o_wcstod)((LARGE_INTEGER)pvarDest.hVal.QuadPart, 0);
        if ( v6 <= 0.0 )
          v7 = DOUBLE_N0_5;
        else
          v7 = DOUBLE_0_5;
        v8 = v7 + v6;
        switch ( v3 )
        {
          case 3:
            pvar->vt = 3;
            v9 = (int)v8;
LABEL_10:
            pvar->lVal = v9;
            break;
          case 2:
            pvar->vt = 2;
            pvar->iVal = (int)v8;
            break;
          case 19:
            pvar->vt = 19;
            v9 = (int)fmax(0.0, v8);
            goto LABEL_10;
          default:
            pvar->vt = 18;
            pvar->iVal = (int)fmax(0.0, v8);
            break;
        }
        PropVariantClear(&pvarDest);
        return v4;
      default:
        return v4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000cf60  mov     [rsp+arg_0], rbx
0x18000cf65  mov     [rsp+arg_8], rsi
0x18000cf6a  push    rdi
0x18000cf6b  sub     rsp, 40h
0x18000cf6f  movzx   eax, word ptr [rcx]
0x18000cf72  mov     rdi, rcx
0x18000cf75  movzx   esi, dx
0x18000cf78  cmp     eax, 13h
0x18000cf7b  jnz     short loc_18000CF91
0x18000cf7d  xor     ebx, ebx; jumptable 000000018000CFB9 cases 2,3,16-18
0x18000cf7f  mov     eax, ebx; jumptable 000000018000CFB9 default case, cases 4-15,19-29
0x18000cf81  mov     rbx, [rsp+48h+arg_0]
0x18000cf86  mov     rsi, [rsp+48h+arg_8]
0x18000cf8b  add     rsp, 40h
0x18000cf8f  pop     rdi
0x18000cf90  retn
0x18000cf91  add     eax, 0FFFFFFFEh; switch 30 cases
0x18000cf94  mov     ebx, 8000FFFFh
0x18000cf99  cmp     eax, 1Dh
0x18000cf9c  ja      short def_18000CFB9; jumptable 000000018000CFB9 default case, cases 4-15,19-29
0x18000cf9e  lea     rcx, __ImageBase
0x18000cfa5  cdqe
0x18000cfa7  movzx   eax, ds:(byte_18000D158 - 180000000h)[rcx+rax]
0x18000cfaf  mov     edx, ds:(jpt_18000CFB9 - 180000000h)[rcx+rax*4]
0x18000cfb6  add     rdx, rcx
0x18000cfb9  jmp     rdx; switch jump
0x18000cfbb  xorps   xmm0, xmm0; jumptable 000000018000CFB9 case 31
0x18000cfbe  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x18000cfc3  xor     eax, eax
0x18000cfc5  mov     rdx, rdi; pvarSrc
0x18000cfc8  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x18000cfcd  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x18000cfd2  call    cs:__imp_PropVariantCopy
0x18000cfd8  mov     ebx, eax
0x18000cfda  test    eax, eax
0x18000cfdc  js      short def_18000CFB9; jumptable 000000018000CFB9 default case, cases 4-15,19-29
0x18000cfde  mov     rcx, rdi; pvar
0x18000cfe1  call    cs:__imp_PropVariantClear
0x18000cfe7  mov     rcx, qword ptr [rsp+48h+pvarDest+8]
0x18000cfec  xor     edx, edx
0x18000cfee  call    cs:__imp__o_wcstod
0x18000cff4  xorps   xmm2, xmm2
0x18000cff7  comisd  xmm0, xmm2
0x18000cffb  jbe     short loc_18000D037
0x18000cffd  movsd   xmm1, cs:__real@3fe0000000000000
0x18000d005  addsd   xmm1, xmm0
0x18000d009  mov     ecx, esi
0x18000d00b  cmp     esi, 3
0x18000d00e  jnz     short loc_18000D041
0x18000d010  mov     [rdi], si
0x18000d013  cvttsd2si eax, xmm1
0x18000d017  mov     [rdi+8], eax
0x18000d01a  lea     rcx, [rsp+48h+pvarDest]; pvar
0x18000d01f  call    cs:__imp_PropVariantClear
0x18000d025  mov     rsi, [rsp+48h+arg_8]
0x18000d02a  mov     eax, ebx
0x18000d02c  mov     rbx, [rsp+48h+arg_0]
0x18000d031  add     rsp, 40h
0x18000d035  pop     rdi
0x18000d036  retn
0x18000d037  movsd   xmm1, cs:__real@bfe0000000000000
0x18000d03f  jmp     short loc_18000D005
0x18000d041  sub     ecx, 2
0x18000d044  jz      short loc_18000D073
0x18000d046  sub     ecx, 10h
0x18000d049  jz      short loc_18000D060
0x18000d04b  cmp     ecx, 1
0x18000d04e  jnz     short loc_18000D060
0x18000d050  maxsd   xmm2, xmm1
0x18000d054  mov     word ptr [rdi], 13h
0x18000d059  cvttsd2si rax, xmm2
0x18000d05e  jmp     short loc_18000D017
0x18000d060  maxsd   xmm2, xmm1
0x18000d064  mov     word ptr [rdi], 12h
0x18000d069  cvttsd2si eax, xmm2
0x18000d06d  mov     [rdi+8], ax
0x18000d071  jmp     short loc_18000D01A
0x18000d073  cvttsd2si eax, xmm1
0x18000d077  mov     word ptr [rdi], 2
0x18000d07c  mov     [rdi+8], ax
0x18000d080  jmp     short loc_18000D01A
0x18000d082  xorps   xmm0, xmm0; jumptable 000000018000CFB9 case 30
0x18000d085  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x18000d08a  xor     eax, eax
0x18000d08c  mov     rdx, rdi; pvarSrc
0x18000d08f  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x18000d094  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x18000d099  call    cs:__imp_PropVariantCopy
0x18000d09f  mov     ebx, eax
0x18000d0a1  test    eax, eax
0x18000d0a3  js      def_18000CFB9; jumptable 000000018000CFB9 default case, cases 4-15,19-29
0x18000d0a9  mov     rcx, rdi; pvar
0x18000d0ac  call    cs:__imp_PropVariantClear
0x18000d0b2  mov     ecx, esi
0x18000d0b4  sub     ecx, 2
0x18000d0b7  jz      short loc_18000D11C
0x18000d0b9  sub     ecx, 1
0x18000d0bc  jz      short loc_18000D0FF
0x18000d0be  sub     ecx, 0Fh
0x18000d0c1  jz      short loc_18000D0E5
0x18000d0c3  cmp     ecx, 1
0x18000d0c6  jnz     short loc_18000D0E5
0x18000d0c8  mov     rcx, qword ptr [rsp+48h+pvarDest+8]
0x18000d0cd  xor     edx, edx
0x18000d0cf  mov     r8d, 0Ah
0x18000d0d5  mov     word ptr [rdi], 13h
0x18000d0da  call    cs:__imp__o_strtoul
0x18000d0e0  mov     [rdi+8], eax
0x18000d0e3  jmp     short loc_18000D138
0x18000d0e5  mov     rcx, qword ptr [rsp+48h+pvarDest+8]
0x18000d0ea  xor     edx, edx
0x18000d0ec  mov     r8d, 0Ah
0x18000d0f2  mov     word ptr [rdi], 12h
0x18000d0f7  call    cs:__imp__o_strtoul
0x18000d0fd  jmp     short loc_18000D134
0x18000d0ff  mov     rcx, qword ptr [rsp+48h+pvarDest+8]; String
0x18000d104  xor     edx, edx; EndPtr
0x18000d106  mov     r8d, 0Ah; Radix
0x18000d10c  mov     word ptr [rdi], 3
0x18000d111  call    cs:__imp_strtol
0x18000d117  mov     [rdi+8], eax
0x18000d11a  jmp     short loc_18000D138
0x18000d11c  mov     rcx, qword ptr [rsp+48h+pvarDest+8]; String
0x18000d121  xor     edx, edx; EndPtr
0x18000d123  mov     r8d, 0Ah; Radix
0x18000d129  mov     word ptr [rdi], 2
0x18000d12e  call    cs:__imp_strtol
0x18000d134  mov     [rdi+8], ax
0x18000d138  lea     rcx, [rsp+48h+pvarDest]; pvar
0x18000d13d  call    cs:__imp_PropVariantClear
0x18000d143  jmp     def_18000CFB9; jumptable 000000018000CFB9 default case, cases 4-15,19-29
```
