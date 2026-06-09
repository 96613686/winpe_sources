# Csl::UnlockVolumeWithExternalKey(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,Csl::Path const &)

- ea: `0x180024afc`
- end: `0x180024d58`
- name: `?UnlockVolumeWithExternalKey@Csl@@YAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEBVPath@1@@Z`
- size: `604`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001ae40`

## callees

- `0x180002140`
- `0x180002534`
- `0x180002c48`
- `0x180003ce4`
- `0x1800045e4`
- `0x18000b004`
- `0x180024afc`

## import_xrefs

- `FVEAPI!FveUnlockVolume` at `0x180024cd8`
- `FVEAPI!FveUnlockVolume` at `0x180024cd8`
- `FVEAPI!FveCloseHandle` at `0x180024cc0`
- `FVEAPI!FveCloseHandle` at `0x180024cff`
- `FVEAPI!FveCloseHandle` at `0x180024cc0`
- `FVEAPI!FveCloseHandle` at `0x180024cff`
- `FVEAPI!FveOpenVolumeW` at `0x180024c84`
- `FVEAPI!FveOpenVolumeW` at `0x180024c84`
- `FVEAPI!FveAuthElementReadExternalKeyW` at `0x180024b5a`
- `FVEAPI!FveAuthElementReadExternalKeyW` at `0x180024bf1`
- `FVEAPI!FveAuthElementReadExternalKeyW` at `0x180024b5a`
- `FVEAPI!FveAuthElementReadExternalKeyW` at `0x180024bf1`

## pseudocode

```c
__int64 __fastcall Csl::UnlockVolumeWithExternalKey(__int64 *a1, _QWORD *a2)
{
  __int64 v4; // rcx
  int v5; // eax
  const char *v6; // r9
  unsigned int v7; // ebx
  size_t v9; // rbx
  void *v10; // rbx
  _DWORD *v11; // rdx
  int v12; // eax
  int v13; // edi
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // [rsp+20h] [rbp-29h] BYREF
  size_t Size; // [rsp+28h] [rbp-21h] BYREF
  void *v18[2]; // [rsp+30h] [rbp-19h] BYREF
  __int64 v19; // [rsp+40h] [rbp-9h]
  _OWORD v20[3]; // [rsp+48h] [rbp-1h] BYREF
  __int64 v21; // [rsp+78h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v21 = 0;
  Size = 0;
  v20[0] = 0x100000038uLL;
  v4 = *a2;
  memset(&v20[1], 0, 32);
  v5 = FveAuthElementReadExternalKeyW(v4, v20, 56, &Size);
  v7 = v5;
  if ( v5 >= 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x44E,
      (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
      v6);
  if ( v5 != -2147024774 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44F,
      (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
      (const char *)(unsigned int)v5);
    return v7;
  }
  v9 = Size;
  v19 = -1;
  *(__m128i *)v18 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( Size )
  {
    if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(v18, Size) )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x453,
        (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
        (const char *)0x8007000ELL);
      if ( v18[0] != (void *)-1LL )
        operator delete(v18[0], (const struct std::nothrow_t *)&std::nothrow);
      return v7;
    }
    memset_0(v18[1], 0, v9);
  }
  v10 = v18[0];
  v11 = v18[0];
  *((_DWORD *)v18[0] + 1) = 1;
  *v11 = 56;
  v12 = FveAuthElementReadExternalKeyW(*a2, v11, Size, &Size);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45D,
      (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
      (const char *)(unsigned int)v12);
LABEL_10:
    if ( v10 != (void *)-1LL )
      operator delete(v10, (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)v13;
  }
  v14 = *a1;
  v16 = 0;
  v13 = FveOpenVolumeW(v14, 0, &v16);
  if ( v13 < 0 )
  {
    v15 = 1120;
    goto LABEL_17;
  }
  v13 = FveUnlockVolume(v16, v10);
  if ( v13 < 0 )
  {
    v15 = 1124;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
      (const char *)(unsigned int)v13);
    if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      FveCloseHandle();
    goto LABEL_10;
  }
  if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FveCloseHandle();
  if ( v10 != (void *)-1LL )
    operator delete(v10, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x180024afc  mov     [rsp-8+arg_10], rbx
0x180024b01  push    rbp
0x180024b02  push    rsi
0x180024b03  push    rdi
0x180024b04  lea     rbp, [rsp-47h]
0x180024b09  sub     rsp, 90h
0x180024b10  mov     rax, cs:__security_cookie
0x180024b17  xor     rax, rsp
0x180024b1a  mov     [rbp+57h+var_20], rax
0x180024b1e  xor     eax, eax
0x180024b20  lea     r9, [rbp+57h+Size]
0x180024b24  xorps   xmm0, xmm0
0x180024b27  mov     [rbp+57h+var_28], rax
0x180024b2b  mov     rdi, rdx
0x180024b2e  mov     [rbp+57h+Size], rax
0x180024b32  movups  [rbp+57h+var_58], xmm0
0x180024b36  mov     rsi, rcx
0x180024b39  mov     dword ptr [rbp+57h+var_58+4], 1
0x180024b40  lea     r8d, [rax+38h]
0x180024b44  mov     dword ptr [rbp+57h+var_58], 38h ; '8'
0x180024b4b  mov     rcx, [rdi]
0x180024b4e  lea     rdx, [rbp+57h+var_58]
0x180024b52  movups  [rbp+57h+var_48], xmm0
0x180024b56  movups  [rbp+57h+var_38], xmm0
0x180024b5a  call    cs:__imp_FveAuthElementReadExternalKeyW
0x180024b61  nop     dword ptr [rax+rax+00h]
0x180024b66  mov     ebx, eax
0x180024b68  test    eax, eax
0x180024b6a  jns     loc_180024D42
0x180024b70  cmp     eax, 8007007Ah
0x180024b75  jz      short loc_180024B96
0x180024b77  mov     rcx, [rbp+5Fh]; this
0x180024b7b  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180024b82  mov     r9d, eax; char *
0x180024b85  mov     edx, 44Fh; void *
0x180024b8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024b8f  mov     eax, ebx
0x180024b91  jmp     loc_180024D22
0x180024b96  mov     rbx, [rbp+57h+Size]
0x180024b9a  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180024ba2  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFFh
0x180024baa  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180024baf  test    rbx, rbx
0x180024bb2  jz      short loc_180024BD2
0x180024bb4  mov     rdx, rbx
0x180024bb7  lea     rcx, [rbp+57h+var_70]
0x180024bbb  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x180024bc0  test    al, al
0x180024bc2  jz      short loc_180024C37
0x180024bc4  mov     rcx, [rbp+57h+var_70+8]; void *
0x180024bc8  mov     r8, rbx; Size
0x180024bcb  xor     edx, edx; Val
0x180024bcd  call    memset_0
0x180024bd2  mov     rbx, [rbp+57h+var_70]
0x180024bd6  lea     r9, [rbp+57h+Size]
0x180024bda  mov     rdx, rbx
0x180024bdd  mov     dword ptr [rbx+4], 1
0x180024be4  mov     dword ptr [rbx], 38h ; '8'
0x180024bea  mov     r8, [rbp+57h+Size]
0x180024bee  mov     rcx, [rdi]
0x180024bf1  call    cs:__imp_FveAuthElementReadExternalKeyW
0x180024bf8  nop     dword ptr [rax+rax+00h]
0x180024bfd  mov     edi, eax
0x180024bff  test    eax, eax
0x180024c01  jns     short loc_180024C73
0x180024c03  mov     rcx, [rbp+5Fh]; this
0x180024c07  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180024c0e  mov     r9d, eax; char *
0x180024c11  mov     edx, 45Dh; void *
0x180024c16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024c1b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180024c1f  jz      short loc_180024C30
0x180024c21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024c28  mov     rcx, rbx; void *
0x180024c2b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024c30  mov     eax, edi
0x180024c32  jmp     loc_180024D22
0x180024c37  mov     rcx, [rbp+5Fh]; this
0x180024c3b  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180024c42  mov     ebx, 8007000Eh
0x180024c47  mov     edx, 453h; void *
0x180024c4c  mov     r9d, ebx; char *
0x180024c4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024c54  mov     rcx, [rbp+57h+var_70]; void *
0x180024c58  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180024c5c  jz      loc_180024B8F
0x180024c62  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024c69  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024c6e  jmp     loc_180024B8F
0x180024c73  mov     rcx, [rsi]
0x180024c76  lea     r8, [rbp+57h+var_80]
0x180024c7a  xor     edx, edx
0x180024c7c  mov     [rbp+57h+var_80], 0
0x180024c84  call    cs:__imp_FveOpenVolumeW
0x180024c8b  nop     dword ptr [rax+rax+00h]
0x180024c90  mov     edi, eax
0x180024c92  test    eax, eax
0x180024c94  jns     short loc_180024CD1
0x180024c96  mov     edx, 460h; void *
0x180024c9b  mov     rcx, [rbp+5Fh]; this
0x180024c9f  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180024ca6  mov     r9d, edi; char *
0x180024ca9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024cae  mov     rcx, [rbp+57h+var_80]
0x180024cb2  lea     rdx, [rcx-1]
0x180024cb6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180024cba  ja      loc_180024C1B
0x180024cc0  call    cs:__imp_FveCloseHandle
0x180024cc7  nop     dword ptr [rax+rax+00h]
0x180024ccc  jmp     loc_180024C1B
0x180024cd1  mov     rcx, [rbp+57h+var_80]
0x180024cd5  mov     rdx, rbx
0x180024cd8  call    cs:__imp_FveUnlockVolume
0x180024cdf  nop     dword ptr [rax+rax+00h]
0x180024ce4  mov     edi, eax
0x180024ce6  test    eax, eax
0x180024ce8  jns     short loc_180024CF1
0x180024cea  mov     edx, 464h
0x180024cef  jmp     short loc_180024C9B
0x180024cf1  mov     rcx, [rbp+57h+var_80]
0x180024cf5  lea     rax, [rcx-1]
0x180024cf9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024cfd  ja      short loc_180024D0B
0x180024cff  call    cs:__imp_FveCloseHandle
0x180024d06  nop     dword ptr [rax+rax+00h]
0x180024d0b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180024d0f  jz      short loc_180024D20
0x180024d11  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024d18  mov     rcx, rbx; void *
0x180024d1b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024d20  xor     eax, eax
0x180024d22  mov     rcx, [rbp+57h+var_20]
0x180024d26  xor     rcx, rsp; StackCookie
0x180024d29  call    __security_check_cookie
0x180024d2e  mov     rbx, [rsp+0A0h+arg_10]
0x180024d36  add     rsp, 90h
0x180024d3d  pop     rdi
0x180024d3e  pop     rsi
0x180024d3f  pop     rbp
0x180024d40  retn
0x180024d42  mov     rcx, [rbp+5Fh]; this
0x180024d46  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180024d4d  mov     edx, 44Eh; void *
0x180024d52  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
