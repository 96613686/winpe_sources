# WindowsMidiServicesNamingLib::AddGroupNumberToNameIfNeeded(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uchar)

- ea: `0x140051ba8`
- end: `0x140051df4`
- name: `?AddGroupNumberToNameIfNeeded@WindowsMidiServicesNamingLib@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00E@Z`
- size: `588`
- prototype: `void *__fastcall(void *Src, wchar_t *S2, wchar_t *, __int64, unsigned __int8)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x140052478`

## callees

- `0x1400054c0`
- `0x1400072d4`
- `0x140007c20`
- `0x1400129b0`
- `0x140013a38`
- `0x14001440c`
- `0x14001ddc4`
- `0x14001f95c`
- `0x140021614`
- `0x1400216cc`
- `0x140035c60`
- `0x140051ba8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140051cf4`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140051cf4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void *__fastcall WindowsMidiServicesNamingLib::AddGroupNumberToNameIfNeeded(
        void *Src,
        wchar_t *S2,
        wchar_t *a3,
        __int64 a4,
        unsigned __int8 a5)
{
  const wchar_t *v5; // rbx
  __int64 v9; // rdx
  size_t v10; // r8
  const wchar_t *v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // rdx
  const wchar_t *v14; // rcx
  char **v15; // rcx
  __int64 v16; // rax
  unsigned __int64 v17; // r8
  __int64 v18; // rdx
  char **v19; // rax
  __int128 *v20; // rcx
  int v21; // eax
  char **v22; // rcx
  unsigned __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // rax
  void *v26; // rax
  __int128 v28; // [rsp+40h] [rbp-81h] BYREF
  __int128 v29; // [rsp+50h] [rbp-71h]
  char *v30[2]; // [rsp+60h] [rbp-61h] BYREF
  unsigned __int64 v31; // [rsp+70h] [rbp-51h]
  unsigned __int64 v32; // [rsp+78h] [rbp-49h]
  _BYTE v33[16]; // [rsp+80h] [rbp-41h] BYREF
  __int64 v34; // [rsp+90h] [rbp-31h]
  char *v35[4]; // [rsp+A0h] [rbp-21h] BYREF
  char *v36[4]; // [rsp+C0h] [rbp-1h] BYREF

  v5 = (const wchar_t *)a4;
  std::wstring::wstring((__int64)v30, a4);
  v9 = *((_QWORD *)S2 + 2);
  if ( *((_QWORD *)S2 + 3) > 7u )
    S2 = *(wchar_t **)S2;
  v10 = *((_QWORD *)v5 + 2);
  v11 = v5;
  v12 = *((_QWORD *)v5 + 3);
  if ( v12 > 7 )
    v11 = *(const wchar_t **)v5;
  if ( v10 != v9 )
  {
LABEL_9:
    v13 = *((_QWORD *)a3 + 2);
    if ( *((_QWORD *)a3 + 3) > 7u )
      a3 = *(wchar_t **)a3;
    v10 = *((_QWORD *)v5 + 2);
    v14 = v5;
    if ( v12 > 7 )
      v14 = *(const wchar_t **)v5;
    if ( v10 != v13 || v10 && wmemcmp(v14, a3, v10) )
      goto LABEL_35;
    goto LABEL_16;
  }
  if ( v10 && wmemcmp(v11, S2, v10) )
  {
    v12 = *((_QWORD *)v5 + 3);
    goto LABEL_9;
  }
LABEL_16:
  if ( a5 )
  {
    v15 = v30;
    if ( v32 > 7 )
      v15 = (char **)v30[0];
    v16 = std::_Traits_find_last_not_of<std::char_traits<unsigned short>>(v15, v31, v10, L"0123456789", 10);
    v17 = -1;
    if ( v16 != -1 )
    {
      v18 = v16 + 1;
      if ( v16 + 1 <= v31 )
      {
        v28 = 0;
        v29 = 0;
        if ( v31 - v18 != -1 )
          v17 = v31 - v18;
        v19 = v30;
        if ( v32 > 7 )
          v19 = (char **)v30[0];
        std::wstring::_Construct<1,unsigned short const *>((char **)&v28, (char *)v19 + 2 * v18, v17);
        v20 = &v28;
        if ( *((_QWORD *)&v29 + 1) > 7u )
          v20 = (__int128 *)v28;
        v21 = _o__wtoi(v20);
        v22 = (char **)&v28;
        if ( v21 == (unsigned __int16)(a5 + 1) )
          goto LABEL_34;
        std::wstring::~wstring((char **)&v28);
      }
    }
    std::to_wstring(v33, (unsigned int)a5 + 1);
    v28 = 0;
    v29 = 0;
    v23 = *((_QWORD *)v5 + 2);
    if ( v23 >= 30 - v34 )
      v23 = 30 - v34;
    if ( *((_QWORD *)v5 + 3) > 7u )
      v5 = *(const wchar_t **)v5;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v28, v5, v23);
    v24 = std::operator+<unsigned short>(v35, &v28, L" ");
    v25 = std::operator+<unsigned short>(v36, v24, v33);
    std::wstring::operator=(v30, v25);
    std::wstring::~wstring(v36);
    std::wstring::~wstring(v35);
    std::wstring::~wstring((char **)&v28);
    v22 = (char **)v33;
LABEL_34:
    std::wstring::~wstring(v22);
  }
LABEL_35:
  v26 = (void *)std::wstring::wstring((__int64)v35, (__int64)v30);
  WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v26);
  std::wstring::~wstring(v30);
  return Src;
}

```

## disassembly

```asm
0x140051ba8  push    rbp
0x140051baa  push    rbx
0x140051bab  push    rsi
0x140051bac  push    rdi
0x140051bad  push    r14
0x140051baf  lea     rbp, [rsp-2Fh]
0x140051bb4  sub     rsp, 0F0h
0x140051bbb  mov     rax, cs:__security_cookie
0x140051bc2  xor     rax, rsp
0x140051bc5  mov     [rbp+4Fh+var_30], rax
0x140051bc9  mov     rbx, r9
0x140051bcc  mov     rdi, r8
0x140051bcf  mov     rsi, rdx
0x140051bd2  mov     r14, rcx
0x140051bd5  mov     [rsp+110h+var_D8], rcx
0x140051bda  mov     rdx, r9
0x140051bdd  lea     rcx, [rbp+4Fh+var_B0]
0x140051be1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140051be6  nop
0x140051be7  mov     rdx, [rsi+10h]
0x140051beb  cmp     qword ptr [rsi+18h], 7
0x140051bf0  jbe     short loc_140051BF5
0x140051bf2  mov     rsi, [rsi]
0x140051bf5  mov     r8, [rbx+10h]; N
0x140051bf9  mov     rcx, rbx
0x140051bfc  mov     rax, [rbx+18h]
0x140051c00  cmp     rax, 7
0x140051c04  jbe     short loc_140051C09
0x140051c06  mov     rcx, [rbx]; S1
0x140051c09  cmp     r8, rdx
0x140051c0c  jnz     short loc_140051C23
0x140051c0e  test    r8, r8
0x140051c11  jz      short loc_140051C5F
0x140051c13  mov     rdx, rsi; S2
0x140051c16  call    wmemcmp
0x140051c1b  test    eax, eax
0x140051c1d  jz      short loc_140051C5F
0x140051c1f  mov     rax, [rbx+18h]
0x140051c23  mov     rdx, [rdi+10h]
0x140051c27  cmp     qword ptr [rdi+18h], 7
0x140051c2c  jbe     short loc_140051C31
0x140051c2e  mov     rdi, [rdi]
0x140051c31  mov     r8, [rbx+10h]; N
0x140051c35  mov     rcx, rbx
0x140051c38  cmp     rax, 7
0x140051c3c  jbe     short loc_140051C41
0x140051c3e  mov     rcx, [rbx]; S1
0x140051c41  cmp     r8, rdx
0x140051c44  jnz     loc_140051DB5
0x140051c4a  test    r8, r8
0x140051c4d  jz      short loc_140051C5F
0x140051c4f  mov     rdx, rdi; S2
0x140051c52  call    wmemcmp
0x140051c57  test    eax, eax
0x140051c59  jnz     loc_140051DB5
0x140051c5f  movzx   edi, [rbp+4Fh+arg_20]
0x140051c63  test    dil, dil
0x140051c66  jz      loc_140051DB5
0x140051c6c  lea     rcx, [rbp+4Fh+var_B0]
0x140051c70  cmp     [rbp+4Fh+var_98], 7
0x140051c75  cmova   rcx, [rbp+4Fh+var_B0]
0x140051c7a  mov     [rsp+110h+var_F0], 0Ah
0x140051c83  lea     r9, a0123456789; "0123456789"
0x140051c8a  mov     rdx, [rbp+4Fh+var_A0]
0x140051c8e  call    ??$_Traits_find_last_not_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_last_not_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x140051c93  mov     esi, 1
0x140051c98  or      r8, 0FFFFFFFFFFFFFFFFh
0x140051c9c  cmp     rax, r8
0x140051c9f  jz      short loc_140051D12
0x140051ca1  mov     rcx, [rbp+4Fh+var_A0]
0x140051ca5  lea     rdx, [rax+1]
0x140051ca9  cmp     rdx, rcx
0x140051cac  ja      short loc_140051D12
0x140051cae  xorps   xmm0, xmm0
0x140051cb1  movups  [rsp+110h+var_D0], xmm0
0x140051cb6  xorps   xmm1, xmm1
0x140051cb9  movdqu  [rbp+4Fh+var_C0], xmm1
0x140051cbe  sub     rcx, rdx
0x140051cc1  cmp     rcx, r8
0x140051cc4  cmovb   r8, rcx
0x140051cc8  lea     rax, [rbp+4Fh+var_B0]
0x140051ccc  cmp     [rbp+4Fh+var_98], 7
0x140051cd1  cmova   rax, [rbp+4Fh+var_B0]
0x140051cd6  lea     rdx, [rax+rdx*2]
0x140051cda  lea     rcx, [rsp+110h+var_D0]
0x140051cdf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140051ce4  lea     rcx, [rsp+110h+var_D0]
0x140051ce9  cmp     qword ptr [rbp+4Fh+var_C0+8], 7
0x140051cee  cmova   rcx, qword ptr [rsp+110h+var_D0]
0x140051cf4  call    cs:__imp__o__wtoi
0x140051cfa  lea     ecx, [rsi+rdi]
0x140051cfd  movzx   ecx, cx
0x140051d00  cmp     eax, ecx
0x140051d02  lea     rcx, [rsp+110h+var_D0]; void *
0x140051d07  jz      loc_140051DB0
0x140051d0d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051d12  lea     edx, [rsi+rdi]
0x140051d15  lea     rcx, [rbp+4Fh+var_90]
0x140051d19  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x140051d1e  nop
0x140051d1f  xorps   xmm0, xmm0
0x140051d22  movups  [rsp+110h+var_D0], xmm0
0x140051d27  xorps   xmm1, xmm1
0x140051d2a  movdqu  [rbp+4Fh+var_C0], xmm1
0x140051d2f  mov     r8, [rbx+10h]
0x140051d33  mov     eax, 1Eh
0x140051d38  sub     rax, [rbp+4Fh+var_80]
0x140051d3c  cmp     r8, rax
0x140051d3f  cmovnb  r8, rax
0x140051d43  cmp     qword ptr [rbx+18h], 7
0x140051d48  jbe     short loc_140051D4D
0x140051d4a  mov     rbx, [rbx]
0x140051d4d  mov     rdx, rbx
0x140051d50  lea     rcx, [rsp+110h+var_D0]
0x140051d55  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140051d5a  nop
0x140051d5b  lea     r8, asc_14007D9A4; " "
0x140051d62  lea     rdx, [rsp+110h+var_D0]
0x140051d67  lea     rcx, [rbp+4Fh+var_70]
0x140051d6b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x140051d70  nop
0x140051d71  lea     r8, [rbp+4Fh+var_90]
0x140051d75  mov     rdx, rax
0x140051d78  lea     rcx, [rbp+4Fh+var_50]
0x140051d7c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x140051d81  mov     rdx, rax
0x140051d84  lea     rcx, [rbp+4Fh+var_B0]
0x140051d88  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140051d8d  lea     rcx, [rbp+4Fh+var_50]; void *
0x140051d91  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051d96  nop
0x140051d97  lea     rcx, [rbp+4Fh+var_70]; void *
0x140051d9b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051da0  nop
0x140051da1  lea     rcx, [rsp+110h+var_D0]; void *
0x140051da6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051dab  nop
0x140051dac  lea     rcx, [rbp+4Fh+var_90]; void *
0x140051db0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051db5  lea     rdx, [rbp+4Fh+var_B0]
0x140051db9  lea     rcx, [rbp+4Fh+var_70]
0x140051dbd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140051dc2  mov     rdx, rax; void *
0x140051dc5  mov     rcx, r14; Src
0x140051dc8  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x140051dcd  nop
0x140051dce  lea     rcx, [rbp+4Fh+var_B0]; void *
0x140051dd2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051dd7  mov     rax, r14
0x140051dda  mov     rcx, [rbp+4Fh+var_30]
0x140051dde  xor     rcx, rsp; StackCookie
0x140051de1  call    __security_check_cookie
0x140051de6  add     rsp, 0F0h
0x140051ded  pop     r14
0x140051def  pop     rdi
0x140051df0  pop     rsi
0x140051df1  pop     rbx
0x140051df2  pop     rbp
0x140051df3  retn
```
