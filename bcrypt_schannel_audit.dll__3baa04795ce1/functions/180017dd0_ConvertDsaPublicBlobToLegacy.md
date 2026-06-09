# ConvertDsaPublicBlobToLegacy

- ea: `0x180017dd0`
- end: `0x180017f40`
- name: `ConvertDsaPublicBlobToLegacy`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000edac`

## callees

- `0x180005060`
- `0x18000e0c0`
- `0x180017dd0`
- `0x18001b7a9`
- `0x18001b7e0`

## string_xrefs

- `0x180017f0e`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ConvertDsaPublicBlobToLegacy(__int64 a1, __int64 a2, _QWORD *a3, unsigned int a4, unsigned int *a5)
{
  int v7; // edx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int128 v10; // xmm1
  __int64 v11; // xmm0_8
  __int64 v12; // r9
  __int64 v13; // r10
  unsigned int v14; // r11d
  __int64 v15; // r10
  __int64 v16; // rcx
  __int64 v17; // r11
  __int64 v18; // r9
  __int64 v19; // rcx
  __int64 v20; // r9
  __int128 v22; // [rsp+28h] [rbp-38h]
  __int128 v23; // [rsp+38h] [rbp-28h] BYREF
  __int64 v24; // [rsp+48h] [rbp-18h]

  v7 = *(_DWORD *)(a1 + 4);
  if ( (unsigned int)(v7 - 64) > 0x40 )
  {
    v9 = -2146893783;
    DebugTraceError(2148073513LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c");
    return v9;
  }
  v8 = v7 + 2 * (v7 + 34);
  *a5 = v8;
  if ( a3 )
  {
    if ( a4 < v8 )
      return (unsigned int)-2146893784;
    memset_0(a3, 0, a4);
    DWORD1(v22) = 8 * *(_DWORD *)(a1 + 4);
    v23 = 0;
    v24 = 0;
    LODWORD(v22) = 861098820;
    *((_QWORD *)&v22 + 1) = 160;
    ReverseMemCopy(&v23, a1 + 8, 4);
    ReverseMemCopy((char *)&v23 + 4, a1 + 12, 20);
    v10 = v23;
    *a3 = 0x220000000306LL;
    *(_OWORD *)(a3 + 1) = v22;
    v11 = v24;
    *(_OWORD *)(a3 + 3) = v10;
    a3[5] = v11;
    ReverseMemCopy(v13, v12, *(unsigned int *)(a1 + 4));
    ReverseMemCopy(v15 + *(unsigned int *)(a1 + 4), a1 + 32, v14);
    ReverseMemCopy(v17 + v16, v18, *(unsigned int *)(a1 + 4));
    ReverseMemCopy(*(unsigned int *)(a1 + 4) + v19, *(unsigned int *)(a1 + 4) + v20, *(unsigned int *)(a1 + 4));
  }
  return 0;
}

```

## disassembly

```asm
0x180017dd0  push    rbp
0x180017dd2  push    rbx
0x180017dd3  push    rdi
0x180017dd4  mov     rbp, rsp
0x180017dd7  sub     rsp, 60h
0x180017ddb  mov     rax, cs:__security_cookie
0x180017de2  xor     rax, rsp
0x180017de5  mov     [rbp+var_10], rax
0x180017de9  mov     rbx, rcx
0x180017dec  mov     rdi, r8
0x180017def  mov     rcx, [rbp+arg_20]
0x180017df3  mov     edx, [rbx+4]
0x180017df6  lea     eax, [rdx-40h]
0x180017df9  cmp     eax, 40h ; '@'
0x180017dfc  ja      loc_180017F09
0x180017e02  lea     eax, [rdx+22h]
0x180017e05  lea     eax, [rdx+rax*2]
0x180017e08  mov     [rcx], eax
0x180017e0a  test    r8, r8
0x180017e0d  jnz     short loc_180017E16
0x180017e0f  xor     ebx, ebx
0x180017e11  jmp     loc_180017F29
0x180017e16  cmp     r9d, eax
0x180017e19  jnb     short loc_180017E25
0x180017e1b  mov     ebx, 80090028h
0x180017e20  jmp     loc_180017F29
0x180017e25  mov     r8d, r9d; Size
0x180017e28  xor     edx, edx; Val
0x180017e2a  mov     rcx, rdi; void *
0x180017e2d  call    memset_0
0x180017e32  mov     eax, [rbx+4]
0x180017e35  lea     rdx, [rbx+8]
0x180017e39  shl     eax, 3
0x180017e3c  lea     rcx, [rbp+var_28]
0x180017e40  mov     [rbp+var_40], 0
0x180017e48  lea     r10, [rdi+30h]
0x180017e4c  xorps   xmm0, xmm0
0x180017e4f  mov     dword ptr [rbp+var_38+4], eax
0x180017e52  mov     r8d, 4
0x180017e58  mov     word ptr [rbp+var_40], 306h
0x180017e5e  lea     r9, [rbx+34h]
0x180017e62  mov     dword ptr [rbp+var_40+4], 2200h
0x180017e69  movdqu  [rbp+var_28], xmm0
0x180017e6e  mov     [rbp+var_18], 0
0x180017e76  mov     dword ptr [rbp+var_38], 33535344h
0x180017e7d  mov     qword ptr [rbp+var_38+8], 0A0h
0x180017e85  call    ReverseMemCopy
0x180017e8a  mov     r11d, 14h
0x180017e90  lea     rdx, [rbx+0Ch]
0x180017e94  mov     r8d, r11d
0x180017e97  lea     rcx, [rbp+var_28+4]
0x180017e9b  call    ReverseMemCopy
0x180017ea0  movups  xmm0, [rbp+var_38]
0x180017ea4  mov     rcx, [rbp+var_40]
0x180017ea8  mov     rdx, r9
0x180017eab  movups  xmm1, [rbp+var_28]
0x180017eaf  mov     [rdi], rcx
0x180017eb2  mov     rcx, r10
0x180017eb5  movups  xmmword ptr [rdi+8], xmm0
0x180017eb9  movsd   xmm0, [rbp+var_18]
0x180017ebe  movups  xmmword ptr [rdi+18h], xmm1
0x180017ec2  movsd   qword ptr [rdi+28h], xmm0
0x180017ec7  mov     r8d, [rbx+4]
0x180017ecb  call    ReverseMemCopy
0x180017ed0  mov     ecx, [rbx+4]
0x180017ed3  lea     rdx, [rbx+20h]
0x180017ed7  add     r9, rcx
0x180017eda  mov     r8d, r11d
0x180017edd  add     rcx, r10
0x180017ee0  call    ReverseMemCopy
0x180017ee5  mov     r8d, [rbx+4]
0x180017ee9  mov     rdx, r9
0x180017eec  add     rcx, r11
0x180017eef  call    ReverseMemCopy
0x180017ef4  mov     r8d, [rbx+4]
0x180017ef8  add     rcx, r8
0x180017efb  lea     rdx, [r8+r9]
0x180017eff  call    ReverseMemCopy
0x180017f04  jmp     loc_180017E0F
0x180017f09  mov     ebx, 80090029h
0x180017f0e  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017f15  mov     ecx, ebx
0x180017f17  lea     rdx, aStatus; "Status"
0x180017f1e  mov     r9d, 5F8h
0x180017f24  call    DebugTraceError
0x180017f29  mov     eax, ebx
0x180017f2b  mov     rcx, [rbp+var_10]
0x180017f2f  xor     rcx, rsp; StackCookie
0x180017f32  call    __security_check_cookie
0x180017f37  add     rsp, 60h
0x180017f3b  pop     rdi
0x180017f3c  pop     rbx
0x180017f3d  pop     rbp
0x180017f3e  retn
```
