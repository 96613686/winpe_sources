# sub_14002DCFC

- ea: `0x14002dcfc`
- end: `0x14002deef`
- name: `sub_14002DCFC`
- size: `499`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14002f150`
- `0x1400432e0`

## callees

- `0x140002efc`
- `0x140018140`
- `0x140018340`
- `0x14001df60`
- `0x14002dcfc`
- `0x140051ba0`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x14002dd44`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14002de11`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14002dd44`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14002de11`
- `KERNEL32!GetLastError` at `0x14002dd54`
- `KERNEL32!GetLastError` at `0x14002de1f`
- `KERNEL32!GetLastError` at `0x14002dd54`
- `KERNEL32!GetLastError` at `0x14002de1f`

## string_xrefs

- `0x14002dd81`: `Failed to expand environment strings in path`
- `0x14002de4c`: `Failed to expand environment strings in path after increasing buffer size`

## pseudocode

```c
__int64 __fastcall sub_14002DCFC(__int64 a1, const WCHAR *a2)
{
  const WCHAR *v3; // rdi
  const WCHAR *v4; // rcx
  DWORD v5; // eax
  DWORD v6; // esi
  DWORD v7; // esi
  _DWORD *v8; // rcx
  WCHAR *v9; // rdx
  const WCHAR *v10; // rcx
  DWORD LastError; // esi
  _DWORD *Ptr; // rcx
  __int128 v13; // xmm0
  __m128i v14; // xmm1
  __int64 v16; // [rsp+40h] [rbp-19h] BYREF
  __int64 v17; // [rsp+48h] [rbp-11h] BYREF
  __int64 v18[2]; // [rsp+50h] [rbp-9h] BYREF
  LPWSTR lpDst[2]; // [rsp+60h] [rbp+7h] BYREF
  __m128i si128; // [rsp+70h] [rbp+17h]

  v17 = a1;
  v3 = a2;
  v4 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v4 = *(const WCHAR **)a2;
  v5 = ExpandEnvironmentStringsW(v4, 0, 0);
  v6 = v5;
  if ( v5 )
  {
    *(_OWORD *)lpDst = 0;
    si128 = 0;
    sub_14001DF60(lpDst, 0, v5 - 1);
    v9 = (WCHAR *)lpDst;
    v10 = v3;
    if ( si128.m128i_i64[1] > 7uLL )
      v9 = lpDst[0];
    if ( *((_QWORD *)v3 + 3) > 7u )
      v10 = *(const WCHAR **)v3;
    if ( ExpandEnvironmentStringsW(v10, v9, v6) )
    {
      v13 = *(_OWORD *)lpDst;
      LOWORD(lpDst[0]) = 0;
      v14 = si128;
      *(_OWORD *)a1 = v13;
      si128 = _mm_load_si128((const __m128i *)&xmmword_14008B6E0);
      *(__m128i *)(a1 + 16) = v14;
    }
    else
    {
      LastError = GetLastError();
      Ptr = sub_140018340(&stru_1400C1280, sub_140015AD0)[1].Ptr;
      if ( *Ptr > 2u )
      {
        if ( *((_QWORD *)v3 + 3) > 7u )
          v3 = *(const WCHAR **)v3;
        v17 = (__int64)v3;
        v18[0] = (__int64)"Failed to expand environment strings in path after increasing buffer size";
        LODWORD(v16) = LastError;
        sub_140002EFC((int)Ptr, (int)&word_1400AD532, 0, 0, (__int64)&v16, (__int64)v18, (__int64)&v17);
      }
      *(_OWORD *)a1 = 0;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 7;
      *(_WORD *)a1 = 0;
    }
    sub_140018140((__int64)lpDst);
  }
  else
  {
    v7 = GetLastError();
    v8 = sub_140018340(&stru_1400C1280, sub_140015AD0)[1].Ptr;
    if ( *v8 > 2u )
    {
      if ( *((_QWORD *)v3 + 3) > 7u )
        v3 = *(const WCHAR **)v3;
      v18[0] = (__int64)v3;
      v17 = (__int64)"Failed to expand environment strings in path";
      LODWORD(v16) = v7;
      sub_140002EFC((int)v8, (int)&byte_1400AD4FD, 0, 0, (__int64)&v16, (__int64)&v17, (__int64)v18);
    }
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 7;
    *(_WORD *)a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x14002dcfc  mov     [rsp-8+arg_10], rbx
0x14002dd01  push    rbp
0x14002dd02  push    rsi
0x14002dd03  push    rdi
0x14002dd04  push    r14
0x14002dd06  push    r15
0x14002dd08  lea     rbp, [rsp-37h]
0x14002dd0d  sub     rsp, 90h
0x14002dd14  mov     rax, cs:__security_cookie
0x14002dd1b  xor     rax, rsp
0x14002dd1e  mov     [rbp+57h+var_30], rax
0x14002dd22  xor     r14d, r14d
0x14002dd25  mov     [rbp+57h+var_68], rcx
0x14002dd29  mov     rbx, rcx
0x14002dd2c  mov     rdi, rdx
0x14002dd2f  mov     rcx, rdx
0x14002dd32  lea     r15d, [r14+7]
0x14002dd36  cmp     [rdx+18h], r15
0x14002dd3a  jbe     short loc_14002DD3F
0x14002dd3c  mov     rcx, [rdx]; lpSrc
0x14002dd3f  xor     r8d, r8d; nSize
0x14002dd42  xor     edx, edx; lpDst
0x14002dd44  call    cs:ExpandEnvironmentStringsW
0x14002dd4a  mov     esi, eax
0x14002dd4c  test    eax, eax
0x14002dd4e  jnz     loc_14002DDD7
0x14002dd54  call    cs:GetLastError
0x14002dd5a  lea     rdx, sub_140015AD0; void (__cdecl *)()
0x14002dd61  mov     esi, eax
0x14002dd63  lea     rcx, stru_1400C1280; lpInitOnce
0x14002dd6a  call    sub_140018340
0x14002dd6f  mov     rcx, [rax+8]; int
0x14002dd73  cmp     dword ptr [rcx], 2
0x14002dd76  jbe     short loc_14002DDC0
0x14002dd78  cmp     [rdi+18h], r15
0x14002dd7c  jbe     short loc_14002DD81
0x14002dd7e  mov     rdi, [rdi]
0x14002dd81  lea     rax, aFailedToExpand; "Failed to expand environment strings in"...
0x14002dd88  mov     [rbp+57h+var_60], rdi
0x14002dd8c  mov     [rbp+57h+var_68], rax
0x14002dd90  lea     rdx, byte_1400AD4FD; int
0x14002dd97  lea     rax, [rbp+57h+var_60]
0x14002dd9b  mov     dword ptr [rbp+57h+var_70], esi
0x14002dd9e  mov     [rsp+0B0h+var_80], rax; __int64
0x14002dda3  xor     r9d, r9d; int
0x14002dda6  lea     rax, [rbp+57h+var_68]
0x14002ddaa  xor     r8d, r8d; int
0x14002ddad  mov     [rsp+0B0h+var_88], rax; __int64
0x14002ddb2  lea     rax, [rbp+57h+var_70]
0x14002ddb6  mov     [rsp+0B0h+var_90], rax; __int64
0x14002ddbb  call    sub_140002EFC
0x14002ddc0  xorps   xmm0, xmm0
0x14002ddc3  movups  xmmword ptr [rbx], xmm0
0x14002ddc6  mov     [rbx+10h], r14
0x14002ddca  mov     [rbx+18h], r15
0x14002ddce  mov     [rbx], r14w
0x14002ddd2  jmp     loc_14002DEC9
0x14002ddd7  xorps   xmm0, xmm0
0x14002ddda  lea     r8d, [rax-1]
0x14002ddde  xorps   xmm1, xmm1
0x14002dde1  lea     rcx, [rbp+57h+lpDst]
0x14002dde5  xor     edx, edx
0x14002dde7  movups  xmmword ptr [rbp+57h+lpDst], xmm0
0x14002ddeb  movdqu  [rbp+57h+var_40], xmm1
0x14002ddf0  call    sub_14001DF60
0x14002ddf5  cmp     qword ptr [rbp+57h+var_40+8], r15
0x14002ddf9  lea     rdx, [rbp+57h+lpDst]
0x14002ddfd  mov     rcx, rdi
0x14002de00  cmova   rdx, [rbp+57h+lpDst]; lpDst
0x14002de05  cmp     [rdi+18h], r15
0x14002de09  jbe     short loc_14002DE0E
0x14002de0b  mov     rcx, [rdi]; lpSrc
0x14002de0e  mov     r8d, esi; nSize
0x14002de11  call    cs:ExpandEnvironmentStringsW
0x14002de17  test    eax, eax
0x14002de19  jnz     loc_14002DE9F
0x14002de1f  call    cs:GetLastError
0x14002de25  lea     rdx, sub_140015AD0; void (__cdecl *)()
0x14002de2c  mov     esi, eax
0x14002de2e  lea     rcx, stru_1400C1280; lpInitOnce
0x14002de35  call    sub_140018340
0x14002de3a  mov     rcx, [rax+8]; int
0x14002de3e  cmp     dword ptr [rcx], 2
0x14002de41  jbe     short loc_14002DE8B
0x14002de43  cmp     [rdi+18h], r15
0x14002de47  jbe     short loc_14002DE4C
0x14002de49  mov     rdi, [rdi]
0x14002de4c  lea     rax, aFailedToExpand_0; "Failed to expand environment strings in"...
0x14002de53  mov     [rbp+57h+var_68], rdi
0x14002de57  mov     [rbp+57h+var_60], rax
0x14002de5b  lea     rdx, word_1400AD532; int
0x14002de62  lea     rax, [rbp+57h+var_68]
0x14002de66  mov     dword ptr [rbp+57h+var_70], esi
0x14002de69  mov     [rsp+0B0h+var_80], rax; __int64
0x14002de6e  xor     r9d, r9d; int
0x14002de71  lea     rax, [rbp+57h+var_60]
0x14002de75  xor     r8d, r8d; int
0x14002de78  mov     [rsp+0B0h+var_88], rax; __int64
0x14002de7d  lea     rax, [rbp+57h+var_70]
0x14002de81  mov     [rsp+0B0h+var_90], rax; __int64
0x14002de86  call    sub_140002EFC
0x14002de8b  xorps   xmm0, xmm0
0x14002de8e  movups  xmmword ptr [rbx], xmm0
0x14002de91  mov     [rbx+10h], r14
0x14002de95  mov     [rbx+18h], r15
0x14002de99  mov     [rbx], r14w
0x14002de9d  jmp     short loc_14002DEC0
0x14002de9f  movups  xmm0, xmmword ptr [rbp+57h+lpDst]
0x14002dea3  mov     word ptr [rbp+57h+lpDst], r14w
0x14002dea8  movups  xmm1, [rbp+57h+var_40]
0x14002deac  movups  xmmword ptr [rbx], xmm0
0x14002deaf  movdqa  xmm0, cs:xmmword_14008B6E0
0x14002deb7  movdqu  [rbp+57h+var_40], xmm0
0x14002debc  movups  xmmword ptr [rbx+10h], xmm1
0x14002dec0  lea     rcx, [rbp+57h+lpDst]
0x14002dec4  call    sub_140018140
0x14002dec9  mov     rax, rbx
0x14002decc  mov     rcx, [rbp+57h+var_30]
0x14002ded0  xor     rcx, rsp; StackCookie
0x14002ded3  call    __security_check_cookie
0x14002ded8  mov     rbx, [rsp+0B0h+arg_10]
0x14002dee0  add     rsp, 90h
0x14002dee7  pop     r15
0x14002dee9  pop     r14
0x14002deeb  pop     rdi
0x14002deec  pop     rsi
0x14002deed  pop     rbp
0x14002deee  retn
```
