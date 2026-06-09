# sub_1800C0BBC

- ea: `0x1800c0bbc`
- end: `0x1800c15c7`
- name: `sub_1800C0BBC`
- size: `2571`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x1800c3f24`

## callees

- `0x18000ca10`
- `0x180015920`
- `0x180017f04`
- `0x18001f208`
- `0x1800c0bbc`
- `0x18013c960`
- `0x180141350`
- `0x18018f7a0`

## string_xrefs

- `0x1800c0c37`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp`
- `0x1800c0d47`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp`
- `0x1800c0ea4`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp`
- `0x1800c0fb4`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp`
- `0x1800c110a`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp`
- `0x1800c121a`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp`
- `0x1800c135f`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp`
- `0x1800c146f`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp`

## pseudocode

```c
__int64 __fastcall sub_1800C0BBC(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int128 v13; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v14; // [rsp+58h] [rbp-A8h]
  __int128 v15; // [rsp+68h] [rbp-98h] BYREF
  __int128 v16; // [rsp+78h] [rbp-88h]
  _BYTE v17[32]; // [rsp+88h] [rbp-78h] BYREF
  char v18; // [rsp+A8h] [rbp-58h]
  _BYTE v19[72]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v20[16]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v21[5]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v22[4]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v23[5]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE *v24; // [rsp+180h] [rbp+80h] BYREF
  _BYTE *v25; // [rsp+188h] [rbp+88h] BYREF

  v24 = (_BYTE *)a1;
  if ( *(_BYTE *)(a2 + 40) && !*(_QWORD *)(a2 + 24) )
  {
    if ( *(_QWORD *)(a2 + 208) )
    {
      v15 = 0;
      v16 = 0;
      sub_18000CA10(
        (unsigned __int64 *)&v15,
        (__int64)"../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp",
        0x60u);
      v13 = 0;
      v14 = 0;
      sub_18000CA10((unsigned __int64 *)&v13, (__int64)"InvalidCustomId", 0xFu);
      LODWORD(v25) = 107;
      LODWORD(v24) = 22;
      v4 = *(_QWORD *)(a2 + 208);
      if ( !v4 )
        Concurrency::cancel_current_task();
      (*(void (__fastcall **)(__int64, _BYTE **, __int128 *, __int128 *, _BYTE **))(*(_QWORD *)v4 + 16LL))(
        v4,
        &v24,
        &v13,
        &v15,
        &v25);
      sub_180015920((__int64 *)&v13);
      sub_180015920((__int64 *)&v15);
    }
    v25 = v19;
    LODWORD(v24) = 0;
    sub_180017F04((__int64)v19, &v24);
    v24 = v17;
    v18 = 0;
    v13 = 0;
    v14 = 0;
    sub_18000CA10((unsigned __int64 *)&v13, (__int64)"InvalidCustomId", 0xFu);
    v15 = 0;
    v16 = 0;
    sub_18000CA10(
      (unsigned __int64 *)&v15,
      (__int64)"../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp",
      0x60u);
    v5 = sub_18001F208((__int64)v20, 22, (int)&v15, 109, (__int64)&v13, 0, (__int64)v17, (__int64)v19);
    *(_OWORD *)a1 = *(_OWORD *)v5;
    *(_OWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 40) = 0;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)(v5 + 16);
    *(_OWORD *)(a1 + 32) = *(_OWORD *)(v5 + 32);
    *(_QWORD *)(v5 + 32) = 0;
    *(_QWORD *)(v5 + 40) = 15;
    *(_BYTE *)(v5 + 16) = 0;
    *(_DWORD *)(a1 + 48) = *(_DWORD *)(v5 + 48);
    *(_OWORD *)(a1 + 56) = 0;
    *(_QWORD *)(a1 + 72) = 0;
    *(_QWORD *)(a1 + 80) = 0;
    *(_OWORD *)(a1 + 56) = *(_OWORD *)(v5 + 56);
    *(_OWORD *)(a1 + 72) = *(_OWORD *)(v5 + 72);
    *(_QWORD *)(v5 + 72) = 0;
    *(_QWORD *)(v5 + 80) = 15;
    *(_BYTE *)(v5 + 56) = 0;
    *(_OWORD *)(a1 + 88) = 0;
    *(_QWORD *)(a1 + 104) = 0;
    *(_QWORD *)(a1 + 112) = 0;
    *(_OWORD *)(a1 + 88) = *(_OWORD *)(v5 + 88);
    *(_OWORD *)(a1 + 104) = *(_OWORD *)(v5 + 104);
    *(_QWORD *)(v5 + 104) = 0;
    *(_QWORD *)(v5 + 112) = 15;
    *(_BYTE *)(v5 + 88) = 0;
    *(_BYTE *)(a1 + 120) = 0;
    sub_180015920(v23);
    sub_180015920(v22);
    sub_180015920(v21);
    sub_180015920((__int64 *)&v15);
LABEL_25:
    sub_180015920((__int64 *)&v13);
    return a1;
  }
  if ( *(_DWORD *)(a2 + 288) > 0xAu )
  {
    if ( *(_QWORD *)(a2 + 208) )
    {
      v13 = 0;
      v14 = 0;
      sub_18000CA10(
        (unsigned __int64 *)&v13,
        (__int64)"../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp",
        0x60u);
      v15 = 0;
      v16 = 0;
      sub_18000CA10((unsigned __int64 *)&v15, (__int64)"InvalidProduct", 0xEu);
      LODWORD(v24) = 117;
      LODWORD(v25) = 22;
      v10 = *(_QWORD *)(a2 + 208);
      if ( !v10 )
        Concurrency::cancel_current_task();
      (*(void (__fastcall **)(__int64, _BYTE **, __int128 *, __int128 *, _BYTE **))(*(_QWORD *)v10 + 16LL))(
        v10,
        &v25,
        &v15,
        &v13,
        &v24);
      sub_180015920((__int64 *)&v15);
      sub_180015920((__int64 *)&v13);
    }
    v25 = v19;
    LODWORD(v24) = 0;
    sub_180017F04((__int64)v19, &v24);
    v24 = v17;
    v18 = 0;
    v13 = 0;
    v14 = 0;
    sub_18000CA10((unsigned __int64 *)&v13, (__int64)"InvalidProduct", 0xEu);
    v15 = 0;
    v16 = 0;
    sub_18000CA10(
      (unsigned __int64 *)&v15,
      (__int64)"../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp",
      0x60u);
    v11 = sub_18001F208((__int64)v20, 22, (int)&v15, 119, (__int64)&v13, 0, (__int64)v17, (__int64)v19);
    *(_OWORD *)a1 = *(_OWORD *)v11;
    *(_OWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 40) = 0;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)(v11 + 16);
    *(_OWORD *)(a1 + 32) = *(_OWORD *)(v11 + 32);
    *(_QWORD *)(v11 + 32) = 0;
    *(_QWORD *)(v11 + 40) = 15;
    *(_BYTE *)(v11 + 16) = 0;
    *(_DWORD *)(a1 + 48) = *(_DWORD *)(v11 + 48);
    *(_OWORD *)(a1 + 56) = 0;
    *(_QWORD *)(a1 + 72) = 0;
    *(_QWORD *)(a1 + 80) = 0;
    *(_OWORD *)(a1 + 56) = *(_OWORD *)(v11 + 56);
    *(_OWORD *)(a1 + 72) = *(_OWORD *)(v11 + 72);
    *(_QWORD *)(v11 + 72) = 0;
    *(_QWORD *)(v11 + 80) = 15;
    *(_BYTE *)(v11 + 56) = 0;
    *(_OWORD *)(a1 + 88) = 0;
    *(_QWORD *)(a1 + 104) = 0;
    *(_QWORD *)(a1 + 112) = 0;
    *(_OWORD *)(a1 + 88) = *(_OWORD *)(v11 + 88);
    *(_OWORD *)(a1 + 104) = *(_OWORD *)(v11 + 104);
    *(_QWORD *)(v11 + 104) = 0;
    *(_QWORD *)(v11 + 112) = 15;
    *(_BYTE *)(v11 + 88) = 0;
    *(_BYTE *)(a1 + 120) = 0;
    sub_180015920(v23);
    sub_180015920(v22);
    sub_180015920(v21);
    sub_180015920((__int64 *)&v15);
    goto LABEL_25;
  }
  if ( *(_BYTE *)(a2 + 328) && !*(_QWORD *)(a2 + 312) )
  {
    if ( *(_QWORD *)(a2 + 208) )
    {
      v13 = 0;
      v14 = 0;
      sub_18000CA10(
        (unsigned __int64 *)&v13,
        (__int64)"../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp",
        0x60u);
      v15 = 0;
      v16 = 0;
      sub_18000CA10((unsigned __int64 *)&v15, (__int64)"InvalidLocale", 0xDu);
      LODWORD(v24) = 126;
      LODWORD(v25) = 22;
      v6 = *(_QWORD *)(a2 + 208);
      if ( !v6 )
        Concurrency::cancel_current_task();
      (*(void (__fastcall **)(__int64, _BYTE **, __int128 *, __int128 *, _BYTE **))(*(_QWORD *)v6 + 16LL))(
        v6,
        &v25,
        &v15,
        &v13,
        &v24);
      sub_180015920((__int64 *)&v15);
      sub_180015920((__int64 *)&v13);
    }
    v25 = v19;
    LODWORD(v24) = 0;
    sub_180017F04((__int64)v19, &v24);
    v24 = v17;
    v18 = 0;
    v13 = 0;
    v14 = 0;
    sub_18000CA10((unsigned __int64 *)&v13, (__int64)"InvalidLocale", 0xDu);
    v15 = 0;
    v16 = 0;
    sub_18000CA10(
      (unsigned __int64 *)&v15,
      (__int64)"../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp",
      0x60u);
    v7 = sub_18001F208((__int64)v20, 22, (int)&v15, 128, (__int64)&v13, 0, (__int64)v17, (__int64)v19);
    *(_OWORD *)a1 = *(_OWORD *)v7;
    *(_OWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 40) = 0;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)(v7 + 16);
    *(_OWORD *)(a1 + 32) = *(_OWORD *)(v7 + 32);
    *(_QWORD *)(v7 + 32) = 0;
    *(_QWORD *)(v7 + 40) = 15;
    *(_BYTE *)(v7 + 16) = 0;
    *(_DWORD *)(a1 + 48) = *(_DWORD *)(v7 + 48);
    *(_OWORD *)(a1 + 56) = 0;
    *(_QWORD *)(a1 + 72) = 0;
    *(_QWORD *)(a1 + 80) = 0;
    *(_OWORD *)(a1 + 56) = *(_OWORD *)(v7 + 56);
    *(_OWORD *)(a1 + 72) = *(_OWORD *)(v7 + 72);
    *(_QWORD *)(v7 + 72) = 0;
    *(_QWORD *)(v7 + 80) = 15;
    *(_BYTE *)(v7 + 56) = 0;
    *(_OWORD *)(a1 + 88) = 0;
    *(_QWORD *)(a1 + 104) = 0;
    *(_QWORD *)(a1 + 112) = 0;
    *(_OWORD *)(a1 + 88) = *(_OWORD *)(v7 + 88);
    *(_OWORD *)(a1 + 104) = *(_OWORD *)(v7 + 104);
    *(_QWORD *)(v7 + 104) = 0;
    *(_QWORD *)(v7 + 112) = 15;
    *(_BYTE *)(v7 + 88) = 0;
    *(_BYTE *)(a1 + 120) = 0;
    sub_180015920(v23);
    sub_180015920(v22);
    sub_180015920(v21);
    sub_180015920((__int64 *)&v15);
    goto LABEL_25;
  }
  if ( *(_BYTE *)(a2 + 280) && !*(_QWORD *)(a2 + 272) )
  {
    if ( *(_QWORD *)(a2 + 208) )
    {
      v13 = 0;
      v14 = 0;
      sub_18000CA10(
        (unsigned __int64 *)&v13,
        (__int64)"../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp",
        0x60u);
      v15 = 0;
      v16 = 0;
      sub_18000CA10((unsigned __int64 *)&v15, (__int64)"InvalidProxy", 0xCu);
      LODWORD(v24) = 135;
      LODWORD(v25) = 22;
      v8 = *(_QWORD *)(a2 + 208);
      if ( !v8 )
        Concurrency::cancel_current_task();
      (*(void (__fastcall **)(__int64, _BYTE **, __int128 *, __int128 *, _BYTE **))(*(_QWORD *)v8 + 16LL))(
        v8,
        &v25,
        &v15,
        &v13,
        &v24);
      sub_180015920((__int64 *)&v15);
      sub_180015920((__int64 *)&v13);
    }
    v25 = v19;
    LODWORD(v24) = 0;
    sub_180017F04((__int64)v19, &v24);
    v24 = v17;
    v18 = 0;
    v13 = 0;
    v14 = 0;
    sub_18000CA10((unsigned __int64 *)&v13, (__int64)"InvalidProxy", 0xCu);
    v15 = 0;
    v16 = 0;
    sub_18000CA10(
      (unsigned __int64 *)&v15,
      (__int64)"../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/smartscreen.cpp",
      0x60u);
    v9 = sub_18001F208((__int64)v20, 22, (int)&v15, 137, (__int64)&v13, 0, (__int64)v17, (__int64)v19);
    *(_OWORD *)a1 = *(_OWORD *)v9;
    *(_OWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 40) = 0;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)(v9 + 16);
    *(_OWORD *)(a1 + 32) = *(_OWORD *)(v9 + 32);
    *(_QWORD *)(v9 + 32) = 0;
    *(_QWORD *)(v9 + 40) = 15;
    *(_BYTE *)(v9 + 16) = 0;
    *(_DWORD *)(a1 + 48) = *(_DWORD *)(v9 + 48);
    *(_OWORD *)(a1 + 56) = 0;
    *(_QWORD *)(a1 + 72) = 0;
    *(_QWORD *)(a1 + 80) = 0;
    *(_OWORD *)(a1 + 56) = *(_OWORD *)(v9 + 56);
    *(_OWORD *)(a1 + 72) = *(_OWORD *)(v9 + 72);
    *(_QWORD *)(v9 + 72) = 0;
    *(_QWORD *)(v9 + 80) = 15;
    *(_BYTE *)(v9 + 56) = 0;
    *(_OWORD *)(a1 + 88) = 0;
    *(_QWORD *)(a1 + 104) = 0;
    *(_QWORD *)(a1 + 112) = 0;
    *(_OWORD *)(a1 + 88) = *(_OWORD *)(v9 + 88);
    *(_OWORD *)(a1 + 104) = *(_OWORD *)(v9 + 104);
    *(_QWORD *)(v9 + 104) = 0;
    *(_QWORD *)(v9 + 112) = 15;
    *(_BYTE *)(v9 + 88) = 0;
    *(_BYTE *)(a1 + 120) = 0;
    sub_180015920(v23);
    sub_180015920(v22);
    sub_180015920(v21);
    sub_180015920((__int64 *)&v15);
    goto LABEL_25;
  }
  *(_BYTE *)(a1 + 120) = 1;
  return a1;
}

```

## disassembly

```asm
0x1800c0bbc  mov     [rsp-8+arg_10], rbx
0x1800c0bc1  push    rbp
0x1800c0bc2  push    rsi
0x1800c0bc3  push    rdi
0x1800c0bc4  push    r12
0x1800c0bc6  push    r15
0x1800c0bc8  lea     rbp, [rsp-0A0h]
0x1800c0bd0  sub     rsp, 1A0h
0x1800c0bd7  mov     rax, cs:__security_cookie
0x1800c0bde  xor     rax, rsp
0x1800c0be1  mov     [rbp+0C0h+var_30], rax
0x1800c0be8  mov     rbx, rdx
0x1800c0beb  mov     rdi, rcx
0x1800c0bee  mov     [rbp+0C0h+var_40], rcx
0x1800c0bf5  xor     r12d, r12d
0x1800c0bf8  cmp     [rdx+28h], r12b
0x1800c0bfc  jz      loc_1800C0E53
0x1800c0c02  cmp     [rdx+18h], r12
0x1800c0c06  ja      loc_1800C0E53
0x1800c0c0c  lea     esi, [r12+60h]
0x1800c0c11  lea     r15d, [r12+0Fh]
0x1800c0c16  cmp     [rdx+0D0h], r12
0x1800c0c1d  jz      loc_1800C0CD3
0x1800c0c23  xorps   xmm0, xmm0
0x1800c0c26  movups  [rsp+1C0h+var_158], xmm0
0x1800c0c2b  xorps   xmm1, xmm1
0x1800c0c2e  movdqu  [rsp+1C0h+var_148], xmm1
0x1800c0c34  mov     r8d, esi
0x1800c0c37  lea     rdx, aThirdPartyWpCl_18; "../../../../third_party/wp.client/msint"...
0x1800c0c3e  lea     rcx, [rsp+1C0h+var_158]
0x1800c0c43  call    sub_18000CA10
0x1800c0c48  nop
0x1800c0c49  xorps   xmm0, xmm0
0x1800c0c4c  movups  [rsp+1C0h+var_178], xmm0
0x1800c0c51  xorps   xmm1, xmm1
0x1800c0c54  movdqu  [rsp+1C0h+var_168], xmm1
0x1800c0c5a  mov     r8d, r15d
0x1800c0c5d  lea     rdx, aInvalidcustomi; "InvalidCustomId"
0x1800c0c64  lea     rcx, [rsp+1C0h+var_178]
0x1800c0c69  call    sub_18000CA10
0x1800c0c6e  nop
0x1800c0c6f  mov     dword ptr [rbp+0C0h+var_38], 6Bh ; 'k'
0x1800c0c79  mov     dword ptr [rbp+0C0h+var_40], 16h
0x1800c0c83  mov     rcx, [rbx+0D0h]
0x1800c0c8a  test    rcx, rcx
0x1800c0c8d  jz      loc_1800C15B5
0x1800c0c93  mov     rax, [rcx]
0x1800c0c96  lea     rdx, [rbp+0C0h+var_38]
0x1800c0c9d  mov     [rsp+1C0h+var_1A0], rdx
0x1800c0ca2  lea     r9, [rsp+1C0h+var_158]
0x1800c0ca7  lea     r8, [rsp+1C0h+var_178]
0x1800c0cac  lea     rdx, [rbp+0C0h+var_40]
0x1800c0cb3  mov     rax, [rax+10h]
0x1800c0cb7  call    cs:__guard_dispatch_icall_fptr
0x1800c0cbd  nop
0x1800c0cbe  lea     rcx, [rsp+1C0h+var_178]
0x1800c0cc3  call    sub_180015920
0x1800c0cc8  nop
0x1800c0cc9  lea     rcx, [rsp+1C0h+var_158]
0x1800c0cce  call    sub_180015920
0x1800c0cd3  lea     rax, [rbp+0C0h+var_108]
0x1800c0cd7  mov     [rbp+0C0h+var_38], rax
0x1800c0cde  mov     dword ptr [rbp+0C0h+var_40], 0
0x1800c0ce8  lea     r8, [rsp+1C0h+var_180]
0x1800c0ced  lea     rdx, [rbp+0C0h+var_40]
0x1800c0cf4  lea     rcx, [rbp+0C0h+var_108]
0x1800c0cf8  call    sub_180017F04
0x1800c0cfd  nop
0x1800c0cfe  lea     rax, [rbp+0C0h+var_138]
0x1800c0d02  mov     [rbp+0C0h+var_40], rax
0x1800c0d09  mov     [rbp+0C0h+var_118], r12b
0x1800c0d0d  xorps   xmm0, xmm0
0x1800c0d10  movups  [rsp+1C0h+var_178], xmm0
0x1800c0d15  xorps   xmm1, xmm1
0x1800c0d18  movdqu  [rsp+1C0h+var_168], xmm1
0x1800c0d1e  mov     r8, r15
0x1800c0d21  lea     rdx, aInvalidcustomi; "InvalidCustomId"
0x1800c0d28  lea     rcx, [rsp+1C0h+var_178]
0x1800c0d2d  call    sub_18000CA10
0x1800c0d32  nop
0x1800c0d33  xorps   xmm0, xmm0
0x1800c0d36  movups  [rsp+1C0h+var_158], xmm0
0x1800c0d3b  xorps   xmm1, xmm1
0x1800c0d3e  movdqu  [rsp+1C0h+var_148], xmm1
0x1800c0d44  mov     r8, rsi
0x1800c0d47  lea     rdx, aThirdPartyWpCl_18; "../../../../third_party/wp.client/msint"...
0x1800c0d4e  lea     rcx, [rsp+1C0h+var_158]
0x1800c0d53  call    sub_18000CA10
0x1800c0d58  nop
0x1800c0d59  lea     rax, [rbp+0C0h+var_108]
0x1800c0d5d  mov     [rsp+1C0h+var_188], rax
0x1800c0d62  lea     rax, [rbp+0C0h+var_138]
0x1800c0d66  mov     [rsp+1C0h+var_190], rax
0x1800c0d6b  mov     [rsp+1C0h+var_198], r12
0x1800c0d70  lea     rax, [rsp+1C0h+var_178]
0x1800c0d75  mov     [rsp+1C0h+var_1A0], rax
0x1800c0d7a  mov     r9d, 6Dh ; 'm'
0x1800c0d80  lea     r8, [rsp+1C0h+var_158]
0x1800c0d85  lea     edx, [r9-57h]
0x1800c0d89  lea     rcx, [rbp+0C0h+var_C0]
0x1800c0d8d  call    sub_18001F208
0x1800c0d92  mov     rcx, rax
0x1800c0d95  movups  xmm0, xmmword ptr [rax]
0x1800c0d98  movdqu  xmmword ptr [rdi], xmm0
0x1800c0d9c  xorps   xmm0, xmm0
0x1800c0d9f  movups  xmmword ptr [rdi+10h], xmm0
0x1800c0da3  mov     [rdi+20h], r12
0x1800c0da7  mov     [rdi+28h], r12
0x1800c0dab  movups  xmm0, xmmword ptr [rax+10h]
0x1800c0daf  movups  xmmword ptr [rdi+10h], xmm0
0x1800c0db3  movups  xmm1, xmmword ptr [rax+20h]
0x1800c0db7  movups  xmmword ptr [rdi+20h], xmm1
0x1800c0dbb  mov     [rax+20h], r12
0x1800c0dbf  mov     [rax+28h], r15
0x1800c0dc3  mov     [rax+10h], r12b
0x1800c0dc7  mov     eax, [rax+30h]
0x1800c0dca  mov     [rdi+30h], eax
0x1800c0dcd  xorps   xmm0, xmm0
0x1800c0dd0  movups  xmmword ptr [rdi+38h], xmm0
0x1800c0dd4  mov     [rdi+48h], r12
0x1800c0dd8  mov     [rdi+50h], r12
0x1800c0ddc  movups  xmm0, xmmword ptr [rcx+38h]
0x1800c0de0  movups  xmmword ptr [rdi+38h], xmm0
0x1800c0de4  movups  xmm1, xmmword ptr [rcx+48h]
0x1800c0de8  movups  xmmword ptr [rdi+48h], xmm1
0x1800c0dec  mov     [rcx+48h], r12
0x1800c0df0  mov     [rcx+50h], r15
0x1800c0df4  mov     [rcx+38h], r12b
0x1800c0df8  xorps   xmm0, xmm0
0x1800c0dfb  movups  xmmword ptr [rdi+58h], xmm0
0x1800c0dff  mov     [rdi+68h], r12
0x1800c0e03  mov     [rdi+70h], r12
0x1800c0e07  movups  xmm0, xmmword ptr [rcx+58h]
0x1800c0e0b  movups  xmmword ptr [rdi+58h], xmm0
0x1800c0e0f  movups  xmm1, xmmword ptr [rcx+68h]
0x1800c0e13  movups  xmmword ptr [rdi+68h], xmm1
0x1800c0e17  mov     [rcx+68h], r12
0x1800c0e1b  mov     [rcx+70h], r15
0x1800c0e1f  mov     [rcx+58h], r12b
0x1800c0e23  mov     [rdi+78h], r12b
0x1800c0e27  lea     rcx, [rbp+0C0h+var_68]
0x1800c0e2b  call    sub_180015920
0x1800c0e30  lea     rcx, [rbp+0C0h+var_88]
0x1800c0e34  call    sub_180015920
0x1800c0e39  lea     rcx, [rbp+0C0h+var_B0]
0x1800c0e3d  call    sub_180015920
0x1800c0e42  nop
0x1800c0e43  lea     rcx, [rsp+1C0h+var_158]
0x1800c0e48  call    sub_180015920
0x1800c0e4d  nop
0x1800c0e4e  jmp     loc_1800C157C
0x1800c0e53  cmp     dword ptr [rdx+120h], 0Ah
0x1800c0e5a  ja      loc_1800C1335
0x1800c0e60  cmp     [rdx+148h], r12b
0x1800c0e67  jz      loc_1800C10C6
0x1800c0e6d  cmp     [rdx+138h], r12
0x1800c0e74  ja      loc_1800C10C6
0x1800c0e7a  mov     esi, 60h ; '`'
0x1800c0e7f  lea     r15d, [rsi-53h]
0x1800c0e83  cmp     [rdx+0D0h], r12
0x1800c0e8a  jz      loc_1800C0F40
0x1800c0e90  xorps   xmm0, xmm0
0x1800c0e93  movups  [rsp+1C0h+var_178], xmm0
0x1800c0e98  xorps   xmm1, xmm1
0x1800c0e9b  movdqu  [rsp+1C0h+var_168], xmm1
0x1800c0ea1  mov     r8d, esi
0x1800c0ea4  lea     rdx, aThirdPartyWpCl_18; "../../../../third_party/wp.client/msint"...
0x1800c0eab  lea     rcx, [rsp+1C0h+var_178]
0x1800c0eb0  call    sub_18000CA10
0x1800c0eb5  nop
0x1800c0eb6  xorps   xmm0, xmm0
0x1800c0eb9  movups  [rsp+1C0h+var_158], xmm0
0x1800c0ebe  xorps   xmm1, xmm1
0x1800c0ec1  movdqu  [rsp+1C0h+var_148], xmm1
0x1800c0ec7  mov     r8d, r15d
0x1800c0eca  lea     rdx, aInvalidlocale; "InvalidLocale"
0x1800c0ed1  lea     rcx, [rsp+1C0h+var_158]
0x1800c0ed6  call    sub_18000CA10
0x1800c0edb  nop
0x1800c0edc  mov     dword ptr [rbp+0C0h+var_40], 7Eh ; '~'
0x1800c0ee6  mov     dword ptr [rbp+0C0h+var_38], 16h
0x1800c0ef0  mov     rcx, [rbx+0D0h]
0x1800c0ef7  test    rcx, rcx
0x1800c0efa  jz      loc_1800C15BB
0x1800c0f00  mov     rax, [rcx]
0x1800c0f03  lea     rdx, [rbp+0C0h+var_40]
0x1800c0f0a  mov     [rsp+1C0h+var_1A0], rdx
0x1800c0f0f  lea     r9, [rsp+1C0h+var_178]
0x1800c0f14  lea     r8, [rsp+1C0h+var_158]
0x1800c0f19  lea     rdx, [rbp+0C0h+var_38]
0x1800c0f20  mov     rax, [rax+10h]
0x1800c0f24  call    cs:__guard_dispatch_icall_fptr
0x1800c0f2a  nop
0x1800c0f2b  lea     rcx, [rsp+1C0h+var_158]
0x1800c0f30  call    sub_180015920
0x1800c0f35  nop
0x1800c0f36  lea     rcx, [rsp+1C0h+var_178]
0x1800c0f3b  call    sub_180015920
0x1800c0f40  lea     rax, [rbp+0C0h+var_108]
0x1800c0f44  mov     [rbp+0C0h+var_38], rax
0x1800c0f4b  mov     dword ptr [rbp+0C0h+var_40], 0
0x1800c0f55  lea     r8, [rsp+1C0h+var_180]
0x1800c0f5a  lea     rdx, [rbp+0C0h+var_40]
0x1800c0f61  lea     rcx, [rbp+0C0h+var_108]
0x1800c0f65  call    sub_180017F04
0x1800c0f6a  nop
0x1800c0f6b  lea     rax, [rbp+0C0h+var_138]
0x1800c0f6f  mov     [rbp+0C0h+var_40], rax
0x1800c0f76  mov     [rbp+0C0h+var_118], r12b
0x1800c0f7a  xorps   xmm0, xmm0
0x1800c0f7d  movups  [rsp+1C0h+var_178], xmm0
0x1800c0f82  xorps   xmm1, xmm1
0x1800c0f85  movdqu  [rsp+1C0h+var_168], xmm1
0x1800c0f8b  mov     r8, r15
0x1800c0f8e  lea     rdx, aInvalidlocale; "InvalidLocale"
0x1800c0f95  lea     rcx, [rsp+1C0h+var_178]
0x1800c0f9a  call    sub_18000CA10
0x1800c0f9f  nop
0x1800c0fa0  xorps   xmm0, xmm0
0x1800c0fa3  movups  [rsp+1C0h+var_158], xmm0
0x1800c0fa8  xorps   xmm1, xmm1
0x1800c0fab  movdqu  [rsp+1C0h+var_148], xmm1
0x1800c0fb1  mov     r8, rsi
0x1800c0fb4  lea     rdx, aThirdPartyWpCl_18; "../../../../third_party/wp.client/msint"...
0x1800c0fbb  lea     rcx, [rsp+1C0h+var_158]
0x1800c0fc0  call    sub_18000CA10
0x1800c0fc5  nop
0x1800c0fc6  lea     rax, [rbp+0C0h+var_108]
0x1800c0fca  mov     [rsp+1C0h+var_188], rax
0x1800c0fcf  lea     rax, [rbp+0C0h+var_138]
0x1800c0fd3  mov     [rsp+1C0h+var_190], rax
0x1800c0fd8  mov     [rsp+1C0h+var_198], r12
0x1800c0fdd  lea     rax, [rsp+1C0h+var_178]
0x1800c0fe2  mov     [rsp+1C0h+var_1A0], rax
0x1800c0fe7  mov     r9d, 80h
0x1800c0fed  lea     r8, [rsp+1C0h+var_158]
0x1800c0ff2  lea     edx, [r9-6Ah]
0x1800c0ff6  lea     rcx, [rbp+0C0h+var_C0]
0x1800c0ffa  call    sub_18001F208
0x1800c0fff  mov     rcx, rax
0x1800c1002  movups  xmm0, xmmword ptr [rax]
0x1800c1005  movdqu  xmmword ptr [rdi], xmm0
0x1800c1009  xorps   xmm0, xmm0
0x1800c100c  movups  xmmword ptr [rdi+10h], xmm0
0x1800c1010  mov     [rdi+20h], r12
0x1800c1014  mov     [rdi+28h], r12
0x1800c1018  movups  xmm0, xmmword ptr [rax+10h]
0x1800c101c  movups  xmmword ptr [rdi+10h], xmm0
0x1800c1020  movups  xmm1, xmmword ptr [rax+20h]
0x1800c1024  movups  xmmword ptr [rdi+20h], xmm1
0x1800c1028  mov     [rax+20h], r12
0x1800c102c  mov     r15d, 0Fh
0x1800c1032  mov     [rax+28h], r15
0x1800c1036  mov     [rax+10h], r12b
0x1800c103a  mov     eax, [rax+30h]
0x1800c103d  mov     [rdi+30h], eax
0x1800c1040  xorps   xmm0, xmm0
0x1800c1043  movups  xmmword ptr [rdi+38h], xmm0
0x1800c1047  mov     [rdi+48h], r12
0x1800c104b  mov     [rdi+50h], r12
0x1800c104f  movups  xmm0, xmmword ptr [rcx+38h]
0x1800c1053  movups  xmmword ptr [rdi+38h], xmm0
0x1800c1057  movups  xmm1, xmmword ptr [rcx+48h]
0x1800c105b  movups  xmmword ptr [rdi+48h], xmm1
0x1800c105f  mov     [rcx+48h], r12
0x1800c1063  mov     [rcx+50h], r15
0x1800c1067  mov     [rcx+38h], r12b
0x1800c106b  xorps   xmm0, xmm0
0x1800c106e  movups  xmmword ptr [rdi+58h], xmm0
0x1800c1072  mov     [rdi+68h], r12
0x1800c1076  mov     [rdi+70h], r12
0x1800c107a  movups  xmm0, xmmword ptr [rcx+58h]
0x1800c107e  movups  xmmword ptr [rdi+58h], xmm0
0x1800c1082  movups  xmm1, xmmword ptr [rcx+68h]
0x1800c1086  movups  xmmword ptr [rdi+68h], xmm1
0x1800c108a  mov     [rcx+68h], r12
0x1800c108e  mov     [rcx+70h], r15
0x1800c1092  mov     [rcx+58h], r12b
0x1800c1096  mov     [rdi+78h], r12b
0x1800c109a  lea     rcx, [rbp+0C0h+var_68]
0x1800c109e  call    sub_180015920
0x1800c10a3  lea     rcx, [rbp+0C0h+var_88]
0x1800c10a7  call    sub_180015920
0x1800c10ac  lea     rcx, [rbp+0C0h+var_B0]
0x1800c10b0  call    sub_180015920
0x1800c10b5  nop
0x1800c10b6  lea     rcx, [rsp+1C0h+var_158]
0x1800c10bb  call    sub_180015920
0x1800c10c0  nop
0x1800c10c1  jmp     loc_1800C157C
0x1800c10c6  cmp     [rdx+118h], r12b
0x1800c10cd  jz      loc_1800C132C
0x1800c10d3  cmp     [rdx+110h], r12
0x1800c10da  jnz     loc_1800C132C
0x1800c10e0  mov     esi, 60h ; '`'
0x1800c10e5  lea     r15d, [rsi-54h]
0x1800c10e9  cmp     [rdx+0D0h], r12
0x1800c10f0  jz      loc_1800C11A6
0x1800c10f6  xorps   xmm0, xmm0
0x1800c10f9  movups  [rsp+1C0h+var_178], xmm0
  ... truncated ...
```
