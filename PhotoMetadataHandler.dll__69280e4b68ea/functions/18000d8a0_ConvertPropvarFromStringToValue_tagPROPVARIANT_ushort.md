# ConvertPropvarFromStringToValue(tagPROPVARIANT *,ushort)

- ea: `0x18000d8a0`
- end: `0x18000daee`
- name: `?ConvertPropvarFromStringToValue@@YAJPEAUtagPROPVARIANT@@G@Z`
- size: `590`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar, unsigned __int16)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002033c`
- `0x180020674`

## callees

- `0x18000d8a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000da87`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000daaa`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000da87`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000daaa`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000da44`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000da67`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000da44`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000da67`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18000d93f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18000d93f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000d917`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000d9f7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000d917`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000d9f7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d92c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d976`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000da10`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d92c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d976`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000da10`

## pseudocode

```c
__int64 __fastcall ConvertPropvarFromStringToValue(PROPVARIANT *pvar, unsigned __int16 a2)
{
  int v3; // esi
  HRESULT v4; // ebx
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
        break;
      case 0x1Eu:
        memset(&pvarDest, 0, sizeof(pvarDest));
        v4 = PropVariantCopy(&pvarDest, pvar);
        if ( v4 < 0 )
          return (unsigned int)v4;
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
            v9 = strtol(v13, 0, 10);
            goto LABEL_10;
          case 19:
            hVal = pvarDest.hVal;
            pvar->vt = 19;
            v9 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))_o_strtoul)((LARGE_INTEGER)hVal.QuadPart, 0, 10);
            goto LABEL_10;
          default:
            v11 = pvarDest.hVal;
            pvar->vt = 18;
            v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))_o_strtoul)((LARGE_INTEGER)v11.QuadPart, 0, 10);
            break;
        }
        pvar->iVal = v12;
        goto LABEL_11;
      case 0x1Fu:
        memset(&pvarDest, 0, sizeof(pvarDest));
        v4 = PropVariantCopy(&pvarDest, pvar);
        if ( v4 < 0 )
          return (unsigned int)v4;
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
LABEL_11:
        PropVariantClear(&pvarDest);
        return (unsigned int)v4;
      default:
        return (unsigned int)v4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000d8a0  mov     [rsp+arg_0], rbx
0x18000d8a5  mov     [rsp+arg_8], rsi
0x18000d8aa  push    rdi
0x18000d8ab  sub     rsp, 40h
0x18000d8af  movzx   eax, word ptr [rcx]
0x18000d8b2  mov     rdi, rcx
0x18000d8b5  movzx   esi, dx
0x18000d8b8  cmp     eax, 13h
0x18000d8bb  jnz     short loc_18000D8D2
0x18000d8bd  xor     ebx, ebx; jumptable 000000018000D8FA cases 2,3,16-18
0x18000d8bf  mov     eax, ebx; jumptable 000000018000D8FA default case, cases 4-15,19-29
0x18000d8c1  mov     rbx, [rsp+48h+arg_0]
0x18000d8c6  mov     rsi, [rsp+48h+arg_8]
0x18000d8cb  add     rsp, 40h
0x18000d8cf  pop     rdi
0x18000d8d0  retn
0x18000d8d2  add     eax, 0FFFFFFFEh; switch 30 cases
0x18000d8d5  mov     ebx, 8000FFFFh
0x18000d8da  cmp     eax, 1Dh
0x18000d8dd  ja      short def_18000D8FA; jumptable 000000018000D8FA default case, cases 4-15,19-29
0x18000d8df  lea     rcx, __ImageBase
0x18000d8e6  cdqe
0x18000d8e8  movzx   eax, ds:(byte_18000DAD0 - 180000000h)[rcx+rax]
0x18000d8f0  mov     edx, ds:(jpt_18000D8FA - 180000000h)[rcx+rax*4]
0x18000d8f7  add     rdx, rcx
0x18000d8fa  jmp     rdx; switch jump
0x18000d900  xorps   xmm0, xmm0; jumptable 000000018000D8FA case 31
0x18000d903  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x18000d908  xor     eax, eax
0x18000d90a  mov     rdx, rdi; pvarSrc
0x18000d90d  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x18000d912  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x18000d917  call    cs:__imp_PropVariantCopy
0x18000d91e  nop     dword ptr [rax+rax+00h]
0x18000d923  mov     ebx, eax
0x18000d925  test    eax, eax
0x18000d927  js      short def_18000D8FA; jumptable 000000018000D8FA default case, cases 4-15,19-29
0x18000d929  mov     rcx, rdi; pvar
0x18000d92c  call    cs:__imp_PropVariantClear
0x18000d933  nop     dword ptr [rax+rax+00h]
0x18000d938  mov     rcx, qword ptr [rsp+48h+pvarDest+8]
0x18000d93d  xor     edx, edx
0x18000d93f  call    cs:__imp__o_wcstod
0x18000d946  nop     dword ptr [rax+rax+00h]
0x18000d94b  xorps   xmm2, xmm2
0x18000d94e  comisd  xmm0, xmm2
0x18000d952  jbe     short loc_18000D995
0x18000d954  movsd   xmm1, cs:__real@3fe0000000000000
0x18000d95c  addsd   xmm1, xmm0
0x18000d960  mov     ecx, esi
0x18000d962  cmp     esi, 3
0x18000d965  jnz     short loc_18000D99F
0x18000d967  mov     [rdi], si
0x18000d96a  cvttsd2si eax, xmm1
0x18000d96e  mov     [rdi+8], eax
0x18000d971  lea     rcx, [rsp+48h+pvarDest]; pvar
0x18000d976  call    cs:__imp_PropVariantClear
0x18000d97d  nop     dword ptr [rax+rax+00h]
0x18000d982  mov     rsi, [rsp+48h+arg_8]
0x18000d987  mov     eax, ebx
0x18000d989  mov     rbx, [rsp+48h+arg_0]
0x18000d98e  add     rsp, 40h
0x18000d992  pop     rdi
0x18000d993  retn
0x18000d995  movsd   xmm1, cs:__real@bfe0000000000000
0x18000d99d  jmp     short loc_18000D95C
0x18000d99f  sub     ecx, 2
0x18000d9a2  jz      short loc_18000D9D1
0x18000d9a4  sub     ecx, 10h
0x18000d9a7  jz      short loc_18000D9BE
0x18000d9a9  cmp     ecx, 1
0x18000d9ac  jnz     short loc_18000D9BE
0x18000d9ae  maxsd   xmm2, xmm1
0x18000d9b2  mov     word ptr [rdi], 13h
0x18000d9b7  cvttsd2si rax, xmm2
0x18000d9bc  jmp     short loc_18000D96E
0x18000d9be  maxsd   xmm2, xmm1
0x18000d9c2  mov     word ptr [rdi], 12h
0x18000d9c7  cvttsd2si eax, xmm2
0x18000d9cb  mov     [rdi+8], ax
0x18000d9cf  jmp     short loc_18000D971
0x18000d9d1  cvttsd2si eax, xmm1
0x18000d9d5  mov     word ptr [rdi], 2
0x18000d9da  mov     [rdi+8], ax
0x18000d9de  jmp     short loc_18000D971
0x18000d9e0  xorps   xmm0, xmm0; jumptable 000000018000D8FA case 30
0x18000d9e3  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x18000d9e8  xor     eax, eax
0x18000d9ea  mov     rdx, rdi; pvarSrc
0x18000d9ed  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x18000d9f2  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x18000d9f7  call    cs:__imp_PropVariantCopy
0x18000d9fe  nop     dword ptr [rax+rax+00h]
0x18000da03  mov     ebx, eax
0x18000da05  test    eax, eax
0x18000da07  js      def_18000D8FA; jumptable 000000018000D8FA default case, cases 4-15,19-29
0x18000da0d  mov     rcx, rdi; pvar
0x18000da10  call    cs:__imp_PropVariantClear
0x18000da17  nop     dword ptr [rax+rax+00h]
0x18000da1c  mov     ecx, esi
0x18000da1e  sub     ecx, 2
0x18000da21  jz      short loc_18000DA98
0x18000da23  sub     ecx, 1
0x18000da26  jz      short loc_18000DA75
0x18000da28  sub     ecx, 0Fh
0x18000da2b  jz      short loc_18000DA55
0x18000da2d  cmp     ecx, 1
0x18000da30  jnz     short loc_18000DA55
0x18000da32  mov     rcx, qword ptr [rsp+48h+pvarDest+8]
0x18000da37  xor     edx, edx
0x18000da39  mov     r8d, 0Ah
0x18000da3f  mov     word ptr [rdi], 13h
0x18000da44  call    cs:__imp__o_strtoul
0x18000da4b  nop     dword ptr [rax+rax+00h]
0x18000da50  jmp     loc_18000D96E
0x18000da55  mov     rcx, qword ptr [rsp+48h+pvarDest+8]
0x18000da5a  xor     edx, edx
0x18000da5c  mov     r8d, 0Ah
0x18000da62  mov     word ptr [rdi], 12h
0x18000da67  call    cs:__imp__o_strtoul
0x18000da6e  nop     dword ptr [rax+rax+00h]
0x18000da73  jmp     short loc_18000DAB6
0x18000da75  mov     rcx, qword ptr [rsp+48h+pvarDest+8]; String
0x18000da7a  xor     edx, edx; EndPtr
0x18000da7c  mov     r8d, 0Ah; Radix
0x18000da82  mov     word ptr [rdi], 3
0x18000da87  call    cs:__imp_strtol
0x18000da8e  nop     dword ptr [rax+rax+00h]
0x18000da93  jmp     loc_18000D96E
0x18000da98  mov     rcx, qword ptr [rsp+48h+pvarDest+8]; String
0x18000da9d  xor     edx, edx; EndPtr
0x18000da9f  mov     r8d, 0Ah; Radix
0x18000daa5  mov     word ptr [rdi], 2
0x18000daaa  call    cs:__imp_strtol
0x18000dab1  nop     dword ptr [rax+rax+00h]
0x18000dab6  mov     [rdi+8], ax
0x18000daba  jmp     loc_18000D971
```
