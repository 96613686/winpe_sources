# WindowsMidiServicesNamingLib::FullyCleanupBlockName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18002c0e0`
- end: `0x18002c413`
- name: `?FullyCleanupBlockName@WindowsMidiServicesNamingLib@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@V23@1@Z`
- size: `819`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x18002c41c`

## callees

- `0x180003d70`
- `0x180004180`
- `0x180004214`
- `0x180005000`
- `0x18000b740`
- `0x18000f0a4`
- `0x18001338c`
- `0x1800134cc`
- `0x18001396c`
- `0x180014ab8`
- `0x1800164f0`
- `0x18002c0e0`
- `0x18002cce0`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_OWORD *__fastcall WindowsMidiServicesNamingLib::FullyCleanupBlockName(_OWORD *Src, __int64 a2, void *a3, void *a4)
{
  void *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  const wchar_t *v11; // rcx
  unsigned __int64 v12; // rax
  __int128 *p_Srca; // rcx
  wchar_t **v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 *v17; // rsi
  unsigned __int64 v18; // r9
  _QWORD *v19; // r8
  wchar_t **v20; // r15
  unsigned __int64 v21; // rdi
  char *v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int128 *v25; // rax
  __int64 v26; // rbx
  unsigned __int64 v27; // rdx
  wchar_t **v28; // rax
  unsigned __int64 v29; // rbx
  void *v30; // rax
  _BYTE v32[32]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD *v33; // [rsp+50h] [rbp-B0h]
  _BYTE v34[32]; // [rsp+58h] [rbp-A8h] BYREF
  void *v35; // [rsp+78h] [rbp-88h]
  void *v36; // [rsp+80h] [rbp-80h]
  __int128 Srca; // [rsp+88h] [rbp-78h] BYREF
  __int128 v38; // [rsp+98h] [rbp-68h]
  wchar_t *S1[2]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v40; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v41; // [rsp+C0h] [rbp-40h]
  _BYTE v42[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v43[40]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v44[32]; // [rsp+110h] [rbp+10h] BYREF
  char v45[32]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v46; // [rsp+150h] [rbp+50h] BYREF

  v33 = Src;
  v35 = a3;
  v36 = a4;
  v7 = WindowsMidiServicesNamingLib::RemoveJustKSPinGeneratedSuffix(v32, a2);
  WindowsMidiServicesInternal::TrimmedWStringCopy(&Srca, v7);
  v8 = std::wstring::wstring(v34, &Srca);
  WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(S1, v8);
  v9 = std::wstring::wstring(v32, a3);
  WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v43, v9);
  v10 = std::wstring::wstring(v34, a4);
  WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v42, v10);
  v11 = (const wchar_t *)S1;
  if ( v41 > 7 )
    v11 = S1[0];
  if ( v40 == 4 )
  {
    LODWORD(v12) = wmemcmp(v11, L"MIDI", 4u);
    if ( !(_DWORD)v12 )
    {
      p_Srca = &Srca;
      if ( *((_QWORD *)&v38 + 1) > 7u )
        p_Srca = (__int128 *)Srca;
      *(_QWORD *)&v38 = 0;
      *(_WORD *)p_Srca = 0;
      v14 = S1;
      if ( v41 > 7 )
        v14 = (wchar_t **)S1[0];
      v40 = v12;
      *(_WORD *)v14 = 0;
    }
  }
  if ( (_QWORD)v38 )
  {
    std::wstring::wstring(v44, v43);
    std::wstring::wstring(v45, v42);
    v17 = (__int64 *)v44;
    while ( 1 )
    {
      v18 = v17[2];
      if ( (unsigned __int64)v38 < v18 )
        goto LABEL_35;
      if ( (unsigned __int64)v17[3] <= 7 )
        v19 = v17;
      else
        v19 = (_QWORD *)*v17;
      v20 = S1;
      if ( v41 > 7 )
        v20 = (wchar_t **)S1[0];
      if ( v18 > v40 )
        goto LABEL_35;
      if ( !v18 )
        break;
      v22 = (char *)v20 + 2 * v40;
      v23 = _std_search_2(v20, v22, v19);
      if ( (char *)v23 != v22 )
      {
        v21 = (v23 - (__int64)v20) >> 1;
        if ( v21 != -1 )
          goto LABEL_24;
      }
LABEL_35:
      v17 += 4;
      if ( v17 == &v46 )
      {
        v30 = (void *)std::wstring::wstring(v32, &Srca);
        WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v30);
        `eh vector destructor iterator'(v44, 0x20u, 2u, std::wstring::~wstring);
        goto LABEL_37;
      }
    }
    v21 = 0;
LABEL_24:
    if ( (unsigned __int64)v38 < v21 )
      goto LABEL_38;
    v24 = v38 - v21;
    if ( (unsigned __int64)v38 - v21 >= v17[2] )
      v24 = v17[2];
    v25 = &Srca;
    if ( *((_QWORD *)&v38 + 1) > 7u )
      v25 = (__int128 *)Srca;
    v26 = v38 - v24;
    memmove_0((char *)v25 + 2 * v21, (char *)v25 + 2 * v21 + 2 * v24, 2 * (v38 - v24 - v21) + 2);
    *(_QWORD *)&v38 = v26;
    std::wstring::operator=(&Srca, &Srca);
    if ( v40 < v21 )
LABEL_38:
      std::_String_val<std::_Simple_types<char>>::_Xran(v16, v15, v19);
    v27 = v40 - v21;
    if ( v40 - v21 >= v17[2] )
      v27 = v17[2];
    v28 = S1;
    if ( v41 > 7 )
      v28 = (wchar_t **)S1[0];
    v29 = v40 - v27;
    memmove_0((char *)v28 + 2 * v21, (char *)v28 + 2 * v21 + 2 * v27, 2 * (v40 - v27 - v21) + 2);
    v40 = v29;
    std::wstring::operator=(S1, S1);
    goto LABEL_35;
  }
  *((_QWORD *)Src + 2) = 0;
  *((_QWORD *)Src + 3) = 0;
  *Src = Srca;
  Src[1] = v38;
  *(_QWORD *)&v38 = 0;
  *((_QWORD *)&v38 + 1) = 7;
  LOWORD(Srca) = 0;
LABEL_37:
  std::wstring::~wstring(v42);
  std::wstring::~wstring(v43);
  std::wstring::~wstring(S1);
  std::wstring::~wstring(&Srca);
  std::wstring::~wstring(a3);
  std::wstring::~wstring(a4);
  return Src;
}

```

## disassembly

```asm
0x18002c0e0  push    rbp
0x18002c0e2  push    rbx
0x18002c0e3  push    rsi
0x18002c0e4  push    rdi
0x18002c0e5  push    r12
0x18002c0e7  push    r13
0x18002c0e9  push    r14
0x18002c0eb  push    r15
0x18002c0ed  lea     rbp, [rsp-68h]
0x18002c0f2  sub     rsp, 168h
0x18002c0f9  mov     rax, cs:__security_cookie
0x18002c100  xor     rax, rsp
0x18002c103  mov     [rbp+0A0h+var_50], rax
0x18002c107  mov     r13, r9
0x18002c10a  mov     r12, r8
0x18002c10d  mov     r14, rcx
0x18002c110  mov     [rsp+1A0h+var_150], rcx
0x18002c115  mov     [rsp+1A0h+var_128], r8
0x18002c11a  mov     [rbp+0A0h+var_120], r9
0x18002c11e  mov     [rsp+1A0h+var_178], 0
0x18002c126  lea     rcx, [rsp+1A0h+var_170]; Src
0x18002c12b  call    ?RemoveJustKSPinGeneratedSuffix@WindowsMidiServicesNamingLib@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; WindowsMidiServicesNamingLib::RemoveJustKSPinGeneratedSuffix(std::wstring const &)
0x18002c130  mov     rdx, rax; void *
0x18002c133  lea     rcx, [rbp+0A0h+Src]; Src
0x18002c137  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18002c13c  nop
0x18002c13d  lea     rdx, [rbp+0A0h+Src]
0x18002c141  lea     rcx, [rsp+1A0h+var_148]
0x18002c146  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c14b  mov     rdx, rax
0x18002c14e  lea     rcx, [rbp+0A0h+S1]
0x18002c152  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x18002c157  nop
0x18002c158  mov     rdx, r12
0x18002c15b  lea     rcx, [rsp+1A0h+var_170]
0x18002c160  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c165  mov     rdx, rax
0x18002c168  lea     rcx, [rbp+0A0h+var_B8]
0x18002c16c  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x18002c171  nop
0x18002c172  mov     rdx, r13
0x18002c175  lea     rcx, [rsp+1A0h+var_148]
0x18002c17a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c17f  mov     rdx, rax
0x18002c182  lea     rcx, [rbp+0A0h+var_D8]
0x18002c186  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x18002c18b  nop
0x18002c18c  lea     rcx, [rbp+0A0h+S1]
0x18002c190  cmp     [rbp+0A0h+var_E0], 7
0x18002c195  cmova   rcx, [rbp+0A0h+S1]; S1
0x18002c19a  mov     r8d, 4; N
0x18002c1a0  cmp     [rbp+0A0h+var_E8], r8
0x18002c1a4  jnz     short loc_18002C1E4
0x18002c1a6  lea     rdx, aMidi; "MIDI"
0x18002c1ad  call    wmemcmp
0x18002c1b2  test    eax, eax
0x18002c1b4  jnz     short loc_18002C1E4
0x18002c1b6  lea     rcx, [rbp+0A0h+Src]
0x18002c1ba  cmp     qword ptr [rbp+0A0h+var_108+8], 7
0x18002c1bf  cmova   rcx, qword ptr [rbp+0A0h+Src]
0x18002c1c4  mov     qword ptr [rbp+0A0h+var_108], 0
0x18002c1cc  mov     [rcx], ax
0x18002c1cf  lea     rcx, [rbp+0A0h+S1]
0x18002c1d3  cmp     [rbp+0A0h+var_E0], 7
0x18002c1d8  cmova   rcx, [rbp+0A0h+S1]
0x18002c1dd  mov     [rbp+0A0h+var_E8], rax
0x18002c1e1  mov     [rcx], ax
0x18002c1e4  cmp     qword ptr [rbp+0A0h+var_108], 0
0x18002c1e9  jnz     short loc_18002C227
0x18002c1eb  mov     qword ptr [r14+10h], 0
0x18002c1f3  mov     qword ptr [r14+18h], 0
0x18002c1fb  movups  xmm0, [rbp+0A0h+Src]
0x18002c1ff  movups  xmmword ptr [r14], xmm0
0x18002c203  movups  xmm1, [rbp+0A0h+var_108]
0x18002c207  movups  xmmword ptr [r14+10h], xmm1
0x18002c20c  mov     qword ptr [rbp+0A0h+var_108], 0
0x18002c214  mov     qword ptr [rbp+0A0h+var_108+8], 7
0x18002c21c  xor     eax, eax
0x18002c21e  mov     word ptr [rbp+0A0h+Src], ax
0x18002c222  jmp     loc_18002C3B1
0x18002c227  lea     rdx, [rbp+0A0h+var_B8]
0x18002c22b  lea     rcx, [rbp+0A0h+var_90]
0x18002c22f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c234  nop
0x18002c235  lea     rdx, [rbp+0A0h+var_D8]
0x18002c239  lea     rcx, [rbp+0A0h+var_70]
0x18002c23d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c242  nop
0x18002c243  lea     rsi, [rbp+0A0h+var_90]
0x18002c247  mov     r9, [rsi+10h]
0x18002c24b  cmp     qword ptr [rbp+0A0h+var_108], r9
0x18002c24f  jb      loc_18002C365
0x18002c255  cmp     qword ptr [rsi+18h], 7
0x18002c25a  jbe     short loc_18002C261
0x18002c25c  mov     r8, [rsi]
0x18002c25f  jmp     short loc_18002C264
0x18002c261  mov     r8, rsi
0x18002c264  mov     rax, [rbp+0A0h+var_E8]
0x18002c268  lea     r15, [rbp+0A0h+S1]
0x18002c26c  cmp     [rbp+0A0h+var_E0], 7
0x18002c271  cmova   r15, [rbp+0A0h+S1]
0x18002c276  cmp     r9, rax
0x18002c279  ja      loc_18002C365
0x18002c27f  test    r9, r9
0x18002c282  jnz     short loc_18002C288
0x18002c284  xor     edi, edi
0x18002c286  jmp     short loc_18002C2B3
0x18002c288  lea     rbx, [r15+rax*2]
0x18002c28c  mov     rdx, rbx
0x18002c28f  mov     rcx, r15
0x18002c292  call    __std_search_2
0x18002c297  mov     rdi, rax
0x18002c29a  cmp     rax, rbx
0x18002c29d  jz      loc_18002C365
0x18002c2a3  sub     rdi, r15
0x18002c2a6  sar     rdi, 1
0x18002c2a9  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002c2ad  jz      loc_18002C365
0x18002c2b3  mov     rbx, qword ptr [rbp+0A0h+var_108]
0x18002c2b7  cmp     rbx, rdi
0x18002c2ba  jb      loc_18002C40D
0x18002c2c0  mov     rdx, rbx
0x18002c2c3  sub     rdx, rdi
0x18002c2c6  cmp     rdx, [rsi+10h]
0x18002c2ca  cmovnb  rdx, [rsi+10h]
0x18002c2cf  lea     rax, [rbp+0A0h+Src]
0x18002c2d3  cmp     qword ptr [rbp+0A0h+var_108+8], 7
0x18002c2d8  cmova   rax, qword ptr [rbp+0A0h+Src]
0x18002c2dd  lea     rcx, [rax+rdi*2]; void *
0x18002c2e1  sub     rbx, rdx
0x18002c2e4  mov     r8, rbx
0x18002c2e7  sub     r8, rdi
0x18002c2ea  lea     r8, ds:2[r8*2]; Size
0x18002c2f2  lea     rdx, [rcx+rdx*2]; Src
0x18002c2f6  call    memmove_0
0x18002c2fb  mov     qword ptr [rbp+0A0h+var_108], rbx
0x18002c2ff  lea     rdx, [rbp+0A0h+Src]
0x18002c303  lea     rcx, [rbp+0A0h+Src]
0x18002c307  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002c30c  mov     rbx, [rbp+0A0h+var_E8]
0x18002c310  cmp     rbx, rdi
0x18002c313  jb      loc_18002C40D
0x18002c319  mov     rdx, rbx
0x18002c31c  sub     rdx, rdi
0x18002c31f  cmp     rdx, [rsi+10h]
0x18002c323  cmovnb  rdx, [rsi+10h]
0x18002c328  lea     rax, [rbp+0A0h+S1]
0x18002c32c  cmp     [rbp+0A0h+var_E0], 7
0x18002c331  cmova   rax, [rbp+0A0h+S1]
0x18002c336  lea     rcx, [rax+rdi*2]; void *
0x18002c33a  sub     rbx, rdx
0x18002c33d  mov     r8, rbx
0x18002c340  sub     r8, rdi
0x18002c343  lea     r8, ds:2[r8*2]; Size
0x18002c34b  lea     rdx, [rcx+rdx*2]; Src
0x18002c34f  call    memmove_0
0x18002c354  mov     [rbp+0A0h+var_E8], rbx
0x18002c358  lea     rdx, [rbp+0A0h+S1]
0x18002c35c  lea     rcx, [rbp+0A0h+S1]
0x18002c360  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002c365  add     rsi, 20h ; ' '
0x18002c369  lea     rax, [rbp+0A0h+var_50]
0x18002c36d  cmp     rsi, rax
0x18002c370  jnz     loc_18002C247
0x18002c376  lea     rdx, [rbp+0A0h+Src]
0x18002c37a  lea     rcx, [rsp+1A0h+var_170]
0x18002c37f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c384  mov     rdx, rax; void *
0x18002c387  mov     rcx, r14; Src
0x18002c38a  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18002c38f  mov     [rsp+1A0h+var_178], 1
0x18002c397  lea     r9, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x18002c39e  mov     edx, 20h ; ' '; unsigned __int64
0x18002c3a3  lea     r8d, [rdx-1Eh]; unsigned __int64
0x18002c3a7  lea     rcx, [rbp+0A0h+var_90]; void *
0x18002c3ab  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002c3b0  nop
0x18002c3b1  lea     rcx, [rbp+0A0h+var_D8]; void *
0x18002c3b5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c3ba  nop
0x18002c3bb  lea     rcx, [rbp+0A0h+var_B8]; void *
0x18002c3bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c3c4  nop
0x18002c3c5  lea     rcx, [rbp+0A0h+S1]; void *
0x18002c3c9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c3ce  nop
0x18002c3cf  lea     rcx, [rbp+0A0h+Src]; void *
0x18002c3d3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c3d8  nop
0x18002c3d9  mov     rcx, r12; void *
0x18002c3dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c3e1  nop
0x18002c3e2  mov     rcx, r13; void *
0x18002c3e5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c3ea  mov     rax, r14
0x18002c3ed  mov     rcx, [rbp+0A0h+var_50]
0x18002c3f1  xor     rcx, rsp; StackCookie
0x18002c3f4  call    __security_check_cookie
0x18002c3f9  add     rsp, 168h
0x18002c400  pop     r15
0x18002c402  pop     r14
0x18002c404  pop     r13
0x18002c406  pop     r12
0x18002c408  pop     rdi
0x18002c409  pop     rsi
0x18002c40a  pop     rbx
0x18002c40b  pop     rbp
0x18002c40c  retn
0x18002c40d  call    ?_Xran@?$_String_val@U?$_Simple_types@D@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<char>>::_Xran(void)
```
