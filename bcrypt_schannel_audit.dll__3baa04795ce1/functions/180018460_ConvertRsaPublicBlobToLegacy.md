# ConvertRsaPublicBlobToLegacy

- ea: `0x180018460`
- end: `0x180018586`
- name: `ConvertRsaPublicBlobToLegacy`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e368`

## callees

- `0x180005060`
- `0x18000e0c0`
- `0x180018460`
- `0x18001b7e0`

## string_xrefs

- `0x18001855b`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ConvertRsaPublicBlobToLegacy(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, unsigned int *a5)
{
  unsigned int v6; // edx
  unsigned int v7; // edx
  unsigned int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r10
  int v12; // eax
  __int64 v13; // r11
  __int64 v15; // [rsp+28h] [rbp-20h]
  int v16; // [rsp+30h] [rbp-18h] BYREF

  if ( *(_DWORD *)(a1 + 8) > 4u || (v6 = *(_DWORD *)(a1 + 12), v6 > 0x800) || 8 * v6 - 256 > 0x3F00 )
  {
    v8 = -2146893783;
    DebugTraceError(2148073513LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c");
    return v8;
  }
  v7 = v6 + 20;
  *a5 = v7;
  if ( a3 )
  {
    if ( a4 < v7 )
      return (unsigned int)-2146893784;
    v9 = *(unsigned int *)(a1 + 8);
    HIDWORD(v15) = 8 * *(_DWORD *)(a1 + 12);
    v16 = 0;
    LODWORD(v15) = 826364754;
    ReverseMemCopy(&v16, a1 + 24, v9);
    v12 = v16;
    *(_QWORD *)(a3 + 8) = v15;
    *(_QWORD *)a3 = 0xA40000000206LL;
    *(_DWORD *)(a3 + 16) = v12;
    ReverseMemCopy(a3 + 20, v11 + v10, *(unsigned int *)(v13 + 12));
  }
  return 0;
}

```

## disassembly

```asm
0x180018460  push    rbx
0x180018462  sub     rsp, 40h
0x180018466  mov     rax, cs:__security_cookie
0x18001846d  xor     rax, rsp
0x180018470  mov     [rsp+48h+var_10], rax
0x180018475  mov     r11, rcx
0x180018478  mov     rbx, r8
0x18001847b  mov     rcx, [rsp+48h+arg_20]
0x180018480  cmp     dword ptr [r11+8], 4
0x180018485  ja      loc_180018550
0x18001848b  mov     edx, [r11+0Ch]
0x18001848f  cmp     edx, 800h
0x180018495  ja      loc_180018550
0x18001849b  lea     eax, ds:0FFFFFFFFFFFFFF00h[rdx*8]
0x1800184a2  cmp     eax, 3F00h
0x1800184a7  ja      loc_180018548
0x1800184ad  add     edx, 14h
0x1800184b0  mov     [rcx], edx
0x1800184b2  test    rbx, rbx
0x1800184b5  jnz     short loc_1800184BE
0x1800184b7  xor     ebx, ebx
0x1800184b9  jmp     loc_180018570
0x1800184be  cmp     r9d, edx
0x1800184c1  jnb     short loc_1800184CD
0x1800184c3  mov     ebx, 80090028h
0x1800184c8  jmp     loc_180018570
0x1800184cd  mov     eax, [r11+0Ch]
0x1800184d1  lea     r10, [r11+18h]
0x1800184d5  mov     r9d, [r11+8]
0x1800184d9  lea     rcx, [rsp+48h+var_18]
0x1800184de  shl     eax, 3
0x1800184e1  mov     r8d, r9d
0x1800184e4  mov     [rsp+48h+var_28], 0
0x1800184ed  mov     rdx, r10
0x1800184f0  mov     dword ptr [rsp+48h+var_20+4], eax
0x1800184f4  mov     word ptr [rsp+48h+var_28], 206h
0x1800184fb  mov     dword ptr [rsp+48h+var_28+4], 0A400h
0x180018503  mov     [rsp+48h+var_18], 0
0x18001850b  mov     dword ptr [rsp+48h+var_20], 31415352h
0x180018513  call    ReverseMemCopy
0x180018518  mov     rcx, [rsp+48h+var_28]
0x18001851d  lea     rdx, [r10+r9]
0x180018521  mov     eax, [rsp+48h+var_18]
0x180018525  movsd   xmm0, [rsp+48h+var_20]
0x18001852b  movsd   qword ptr [rbx+8], xmm0
0x180018530  mov     [rbx], rcx
0x180018533  lea     rcx, [rbx+14h]
0x180018537  mov     [rbx+10h], eax
0x18001853a  mov     r8d, [r11+0Ch]
0x18001853e  call    ReverseMemCopy
0x180018543  jmp     loc_1800184B7
0x180018548  mov     r9d, 1B8h
0x18001854e  jmp     short loc_180018556
0x180018550  mov     r9d, 1ADh
0x180018556  mov     ecx, 80090029h
0x18001855b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180018562  lea     rdx, aStatus; "Status"
0x180018569  mov     ebx, ecx
0x18001856b  call    DebugTraceError
0x180018570  mov     eax, ebx
0x180018572  mov     rcx, [rsp+48h+var_10]
0x180018577  xor     rcx, rsp; StackCookie
0x18001857a  call    __security_check_cookie
0x18001857f  add     rsp, 40h
0x180018583  pop     rbx
0x180018584  retn
```
