# CMFRSA::MFRsaOaepDecrypt(void const *,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x18005e3c8`
- end: `0x18005e476`
- name: `?MFRsaOaepDecrypt@CMFRSA@@QEAAJPEBXPEBEKPEAPEAEPEAK@Z`
- size: `174`
- prototype: `__int64 __fastcall(CMFRSA *this, const struct DRM_RSA_PRIVATE_KEY *, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005dedc`

## callees

- `0x18004dccc`
- `0x18005e2b0`
- `0x18005e3c8`
- `0x18009606c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005e420`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005e420`

## pseudocode

```c
__int64 __fastcall CMFRSA::MFRsaOaepDecrypt(
        CMFRSA *this,
        const struct DRM_RSA_PRIVATE_KEY *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  unsigned __int8 **v6; // r14
  void *v7; // rbx
  unsigned int *v8; // rsi
  int v9; // edi
  unsigned __int8 *v10; // rax
  void *Src; // [rsp+60h] [rbp+8h] BYREF

  v6 = a5;
  v7 = 0;
  Src = 0;
  if ( a5 && (v8 = a6) != 0 )
  {
    v9 = MFRsaOaepDecrypt(a2, a3, a4, (unsigned __int8 **)&Src, a6);
    if ( v9 < 0 )
    {
      v7 = Src;
    }
    else
    {
      v10 = (unsigned __int8 *)CoTaskMemAlloc(*v8);
      v7 = Src;
      *v6 = v10;
      if ( v10 )
        memcpy_0(v10, v7, *v8);
      else
        v9 = -2147024882;
    }
  }
  else
  {
    v9 = -2147024809;
  }
  if ( v7 )
    free(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005e3c8  mov     [rsp+Src], rcx
0x18005e3cd  push    rbx
0x18005e3ce  push    rsi
0x18005e3cf  push    rdi
0x18005e3d0  push    r14
0x18005e3d2  sub     rsp, 38h
0x18005e3d6  mov     r14, [rsp+58h+arg_20]
0x18005e3de  xor     ebx, ebx
0x18005e3e0  mov     [rsp+58h+Src], rbx
0x18005e3e5  mov     eax, r9d
0x18005e3e8  mov     r10, r8
0x18005e3eb  mov     r11, rdx
0x18005e3ee  test    r14, r14
0x18005e3f1  jz      short loc_18005E457
0x18005e3f3  mov     rsi, [rsp+58h+arg_28]
0x18005e3fb  test    rsi, rsi
0x18005e3fe  jz      short loc_18005E457
0x18005e400  lea     r9, [rsp+58h+Src]; unsigned __int8 **
0x18005e405  mov     [rsp+58h+var_38], rsi; unsigned int *
0x18005e40a  mov     r8d, eax; unsigned int
0x18005e40d  mov     rdx, r10; unsigned __int8 *
0x18005e410  mov     rcx, r11; struct DRM_RSA_PRIVATE_KEY *
0x18005e413  call    ?MFRsaOaepDecrypt@@YAJPEBUDRM_RSA_PRIVATE_KEY@@PEBEKPEAPEAEPEAK@Z; MFRsaOaepDecrypt(DRM_RSA_PRIVATE_KEY const *,uchar const *,ulong,uchar * *,ulong *)
0x18005e418  mov     edi, eax
0x18005e41a  test    eax, eax
0x18005e41c  js      short loc_18005E450
0x18005e41e  mov     ecx, [rsi]; cb
0x18005e420  call    cs:__imp_CoTaskMemAlloc
0x18005e427  nop     dword ptr [rax+rax+00h]
0x18005e42c  mov     rbx, [rsp+58h+Src]
0x18005e431  mov     [r14], rax
0x18005e434  test    rax, rax
0x18005e437  jnz     short loc_18005E440
0x18005e439  mov     edi, 8007000Eh
0x18005e43e  jmp     short loc_18005E45C
0x18005e440  mov     r8d, [rsi]; Size
0x18005e443  mov     rdx, rbx; Src
0x18005e446  mov     rcx, rax; void *
0x18005e449  call    memcpy_0
0x18005e44e  jmp     short loc_18005E45C
0x18005e450  mov     rbx, [rsp+58h+Src]
0x18005e455  jmp     short loc_18005E45C
0x18005e457  mov     edi, 80070057h
0x18005e45c  test    rbx, rbx
0x18005e45f  jz      short loc_18005E469
0x18005e461  mov     rcx, rbx; Block
0x18005e464  call    free
0x18005e469  mov     eax, edi
0x18005e46b  add     rsp, 38h
0x18005e46f  pop     r14
0x18005e471  pop     rdi
0x18005e472  pop     rsi
0x18005e473  pop     rbx
0x18005e474  retn
```
