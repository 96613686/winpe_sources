# AiGetTrustedPublisherNameFromCache

- ea: `0x140025964`
- end: `0x140025b98`
- name: `AiGetTrustedPublisherNameFromCache`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400339c0`

## callees

- `0x140006a20`
- `0x140006f40`
- `0x140025964`
- `0x140026c48`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140025a1d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140025a1d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140025a39`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140025a39`

## pseudocode

```c
__int64 __fastcall AiGetTrustedPublisherNameFromCache(
        __int64 a1,
        unsigned int a2,
        _BYTE *a3,
        struct _UNICODE_STRING *a4)
{
  __int64 result; // rax
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rax
  __int64 v11; // rbx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v15; // [rsp+30h] [rbp-D0h]
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h]
  _OWORD v18[3]; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v19[3]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v20[13]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v21[13]; // [rsp+120h] [rbp+20h] BYREF

  memset(v20, 0, 0x64u);
  LODWORD(v15) = 0;
  v14 = 0;
  memset(v21, 0, 0x64u);
  LODWORD(v17) = 0;
  v16 = 0;
  if ( a2 < 0x48 )
    return 4294967294LL;
  *a3 = 0;
  if ( *(_DWORD *)(a1 + 40) != 860113217 || a2 != *(unsigned __int16 *)(a1 + 48) + *(unsigned __int16 *)(a1 + 50) + 72 )
    return 4294967294LL;
  if ( *(_QWORD *)(a1 + 64) )
  {
    ExAcquirePushLockSharedEx(&qword_1400192E0, 0);
    v9 = qword_1400192D8;
    ExReleasePushLockSharedEx(&qword_1400192E0, 0);
    v10 = *(_QWORD *)(a1 + 64);
    if ( v9 > v10 )
      return 4294967294LL;
  }
  else
  {
    v10 = 0;
  }
  v11 = *(unsigned __int16 *)(a1 + 48);
  if ( !(_WORD)v11 )
  {
    if ( v10 )
      *a3 = 1;
    return 4294967294LL;
  }
  v19[0] = 0;
  LODWORD(v19[0]) = 48;
  v19[1] = (unsigned __int64)v20;
  v19[2] = 0;
  memset(v20, 0, sizeof(v20));
  LODWORD(v20[0]) = 104;
  LODWORD(v20[2]) = 1;
  v20[1] = &v14;
  LODWORD(v14) = v11;
  v15 = a1 + 72;
  v18[0] = 0;
  LODWORD(v18[0]) = 48;
  v18[1] = (unsigned __int64)v21;
  v18[2] = 0;
  memset(v21, 0, sizeof(v21));
  LODWORD(v21[0]) = 104;
  v21[1] = &v16;
  LODWORD(v16) = *(unsigned __int16 *)(a1 + 50);
  v12 = *(_QWORD *)(a1 + 56);
  LODWORD(v21[2]) = 1;
  v17 = v11 + a1 + 72;
  v13 = v12;
  if ( !v12 || (int)AipGetTrustedPublisherName((__int64)v18, &v13, 0, 0) < 0 )
    v13 = MEMORY[0xFFFFF78000000014];
  result = AipGetTrustedPublisherName((__int64)v19, &v13, a4, 0);
  if ( (int)result >= 0 )
    *a3 = 1;
  return result;
}

```

## disassembly

```asm
0x140025964  mov     [rsp-8+arg_0], rbx
0x140025969  mov     [rsp-8+arg_8], rsi
0x14002596e  push    rbp
0x14002596f  push    rdi
0x140025970  push    r12
0x140025972  push    r13
0x140025974  push    r14
0x140025976  lea     rbp, [rsp-0A0h]
0x14002597e  sub     rsp, 1A0h
0x140025985  mov     rax, cs:__security_cookie
0x14002598c  xor     rax, rsp
0x14002598f  mov     [rbp+0C0h+var_30], rax
0x140025996  xor     eax, eax
0x140025998  mov     rsi, r8
0x14002599b  mov     ebx, edx
0x14002599d  mov     [rbp+0C0h+var_10C], eax
0x1400259a0  mov     rdi, rcx
0x1400259a3  xor     edx, edx; Val
0x1400259a5  lea     rcx, [rbp+0C0h+var_110]; void *
0x1400259a9  mov     r14, r9
0x1400259ac  lea     r8d, [rax+64h]; Size
0x1400259b0  call    memset
0x1400259b5  xor     eax, eax
0x1400259b7  lea     rcx, [rbp+0C0h+var_A0]; void *
0x1400259bb  mov     [rsp+1C0h+var_198+4], rax
0x1400259c0  xor     edx, edx; Val
0x1400259c2  mov     [rsp+1C0h+var_198], rax
0x1400259c7  mov     [rbp+0C0h+var_9C], eax
0x1400259ca  lea     r8d, [rax+64h]; Size
0x1400259ce  call    memset
0x1400259d3  xor     eax, eax
0x1400259d5  mov     [rsp+1C0h+var_188+4], rax
0x1400259da  mov     [rsp+1C0h+var_188], rax
0x1400259df  cmp     ebx, 48h ; 'H'
0x1400259e2  jnb     short loc_1400259EE
0x1400259e4  mov     eax, 0FFFFFFFEh
0x1400259e9  jmp     loc_140025B6C
0x1400259ee  xor     r13d, r13d
0x1400259f1  mov     [rsi], r13b
0x1400259f4  cmp     dword ptr [rdi+28h], 33444941h
0x1400259fb  jnz     short loc_1400259E4
0x1400259fd  movzx   ecx, word ptr [rdi+32h]
0x140025a01  movzx   eax, word ptr [rdi+30h]
0x140025a05  add     ecx, 48h ; 'H'
0x140025a08  add     ecx, eax
0x140025a0a  cmp     ebx, ecx
0x140025a0c  jnz     short loc_1400259E4
0x140025a0e  cmp     [rdi+40h], r13
0x140025a12  jz      short loc_140025A50
0x140025a14  xor     edx, edx
0x140025a16  lea     rcx, qword_1400192E0
0x140025a1d  call    cs:__imp_ExAcquirePushLockSharedEx
0x140025a24  nop     dword ptr [rax+rax+00h]
0x140025a29  mov     rbx, cs:qword_1400192D8
0x140025a30  lea     rcx, qword_1400192E0
0x140025a37  xor     edx, edx
0x140025a39  call    cs:__imp_ExReleasePushLockSharedEx
0x140025a40  nop     dword ptr [rax+rax+00h]
0x140025a45  mov     rax, [rdi+40h]
0x140025a49  cmp     rbx, rax
0x140025a4c  jbe     short loc_140025A53
0x140025a4e  jmp     short loc_1400259E4
0x140025a50  mov     rax, r13
0x140025a53  movzx   ebx, word ptr [rdi+30h]
0x140025a57  test    bx, bx
0x140025a5a  jnz     short loc_140025A69
0x140025a5c  test    rax, rax
0x140025a5f  jz      short loc_1400259E4
0x140025a61  mov     byte ptr [rsi], 1
0x140025a64  jmp     loc_1400259E4
0x140025a69  xorps   xmm0, xmm0
0x140025a6c  lea     rax, [rbp+0C0h+var_110]
0x140025a70  movups  [rsp+1C0h+var_148], xmm0
0x140025a75  mov     r12d, 68h ; 'h'
0x140025a7b  xor     edx, edx; Val
0x140025a7d  movups  [rbp+0C0h+var_138], xmm0
0x140025a81  mov     r8d, r12d; Size
0x140025a84  mov     dword ptr [rsp+1C0h+var_148], 30h ; '0'
0x140025a8c  lea     rcx, [rbp+0C0h+var_110]; void *
0x140025a90  mov     qword ptr [rbp+0C0h+var_138], rax
0x140025a94  movups  [rbp+0C0h+var_128], xmm0
0x140025a98  call    memset
0x140025a9d  xorps   xmm0, xmm0
0x140025aa0  mov     [rbp+0C0h+var_110], r12d
0x140025aa4  lea     rax, [rsp+1C0h+var_198]
0x140025aa9  mov     [rbp+0C0h+var_100], 1
0x140025ab0  mov     [rbp+0C0h+var_108], rax
0x140025ab4  lea     rcx, [rbp+0C0h+var_A0]; void *
0x140025ab8  lea     rax, [rdi+48h]
0x140025abc  mov     dword ptr [rsp+1C0h+var_198], ebx
0x140025ac0  mov     [rsp+1C0h+var_190], rax
0x140025ac5  mov     r8d, r12d; Size
0x140025ac8  lea     rax, [rbp+0C0h+var_A0]
0x140025acc  xor     edx, edx; Val
0x140025ace  movups  [rsp+1C0h+var_178], xmm0
0x140025ad3  mov     dword ptr [rsp+1C0h+var_178], 30h ; '0'
0x140025adb  movups  [rsp+1C0h+var_168], xmm0
0x140025ae0  mov     qword ptr [rsp+1C0h+var_168], rax
0x140025ae5  movups  [rsp+1C0h+var_158], xmm0
0x140025aea  call    memset
0x140025aef  lea     rax, [rsp+1C0h+var_188]
0x140025af4  mov     [rbp+0C0h+var_A0], r12d
0x140025af8  mov     [rbp+0C0h+var_98], rax
0x140025afc  lea     rcx, [rdi+48h]
0x140025b00  movzx   eax, word ptr [rdi+32h]
0x140025b04  add     rcx, rbx
0x140025b07  mov     dword ptr [rsp+1C0h+var_188], eax
0x140025b0b  mov     rax, [rdi+38h]
0x140025b0f  mov     [rbp+0C0h+var_90], 1
0x140025b16  mov     [rsp+1C0h+var_180], rcx
0x140025b1b  mov     [rsp+1C0h+var_1A0], rax
0x140025b20  test    rax, rax
0x140025b23  jz      short loc_140025B3E
0x140025b25  xor     r9d, r9d
0x140025b28  lea     rdx, [rsp+1C0h+var_1A0]
0x140025b2d  xor     r8d, r8d
0x140025b30  lea     rcx, [rsp+1C0h+var_178]
0x140025b35  call    AipGetTrustedPublisherName
0x140025b3a  test    eax, eax
0x140025b3c  jns     short loc_140025B50
0x140025b3e  mov     rax, 0FFFFF78000000014h
0x140025b48  mov     rax, [rax]
0x140025b4b  mov     [rsp+1C0h+var_1A0], rax
0x140025b50  xor     r9d, r9d
0x140025b53  lea     rdx, [rsp+1C0h+var_1A0]
0x140025b58  mov     r8, r14
0x140025b5b  lea     rcx, [rsp+1C0h+var_148]
0x140025b60  call    AipGetTrustedPublisherName
0x140025b65  test    eax, eax
0x140025b67  js      short loc_140025B6C
0x140025b69  mov     byte ptr [rsi], 1
0x140025b6c  mov     rcx, [rbp+0C0h+var_30]
0x140025b73  xor     rcx, rsp; StackCookie
0x140025b76  call    __security_check_cookie
0x140025b7b  lea     r11, [rsp+1C0h+var_20]
0x140025b83  mov     rbx, [r11+30h]
0x140025b87  mov     rsi, [r11+38h]
0x140025b8b  mov     rsp, r11
0x140025b8e  pop     r14
0x140025b90  pop     r13
0x140025b92  pop     r12
0x140025b94  pop     rdi
0x140025b95  pop     rbp
0x140025b96  retn
```
