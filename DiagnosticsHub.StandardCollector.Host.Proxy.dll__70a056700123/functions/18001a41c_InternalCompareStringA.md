# InternalCompareStringA

- ea: `0x18001a41c`
- end: `0x18001a7ab`
- name: `InternalCompareStringA`
- size: `911`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001a7ac`

## callees

- `0x1800078e0`
- `0x18000af1c`
- `0x18000cf0c`
- `0x180011f70`
- `0x180019d60`
- `0x18001a41c`
- `0x180032370`
- `0x180032760`

## import_xrefs

- `KERNEL32!GetCPInfo` at `0x18001a4ef`
- `KERNEL32!GetCPInfo` at `0x18001a4ef`

## pseudocode

```c
__int64 __fastcall InternalCompareStringA(
        __int64 a1,
        __int64 a2,
        DWORD a3,
        const char *a4,
        int a5,
        char *String,
        int a7,
        UINT CodePage)
{
  int v8; // edi
  int v11; // esi
  UINT v12; // r15d
  BYTE *LeadByte; // rax
  BYTE *v15; // rax
  signed int v16; // eax
  unsigned int v17; // r13d
  size_t v18; // rdx
  __int64 v19; // rax
  void *v20; // rsp
  const WCHAR *v21; // rbx
  WCHAR *v22; // rax
  int v23; // eax
  int v24; // r12d
  size_t v25; // rcx
  __int64 v26; // rax
  void *v27; // rsp
  const WCHAR *v28; // rdi
  WCHAR *v29; // rax
  WCHAR *v30; // r14
  WCHAR *v31; // rcx
  bool v32; // zf
  unsigned int v33; // edi
  _BYTE v34[32]; // [rsp+0h] [rbp-50h] BYREF
  DWORD v35; // [rsp+50h] [rbp+0h] BYREF
  char *v36; // [rsp+58h] [rbp+8h]
  __int64 v37; // [rsp+60h] [rbp+10h]
  struct _cpinfo CPInfo; // [rsp+68h] [rbp+18h] BYREF

  v8 = a5;
  v35 = a3;
  v37 = a2;
  v36 = String;
  if ( a5 <= 0 )
  {
    if ( a5 < -1 )
      return 0;
  }
  else
  {
    v8 = _strncnt(a4, a5);
  }
  v11 = a7;
  if ( a7 <= 0 )
  {
    if ( a7 < -1 )
      return 0;
  }
  else
  {
    v11 = _strncnt(String, a7);
  }
  v12 = CodePage;
  if ( !CodePage )
    v12 = *(_DWORD *)(*(_QWORD *)a1 + 12LL);
  if ( !v8 || !v11 )
  {
    memset(&CPInfo, 0, sizeof(CPInfo));
    if ( v8 == v11 )
      return 2;
    if ( v11 > 1 )
      return 1;
    if ( v8 > 1 )
      return 3;
    if ( !GetCPInfo(v12, &CPInfo) )
      return 0;
    if ( v8 > 0 )
    {
      if ( CPInfo.MaxCharSize >= 2 )
      {
        LeadByte = CPInfo.LeadByte;
        if ( CPInfo.LeadByte[0] )
        {
          while ( LeadByte[1] )
          {
            if ( (unsigned int)*a4 >= *LeadByte && (unsigned int)*a4 <= LeadByte[1] )
              return 2;
            LeadByte += 2;
            if ( !*LeadByte )
              return 3;
          }
        }
      }
      return 3;
    }
    if ( v11 > 0 )
    {
      if ( CPInfo.MaxCharSize >= 2 )
      {
        v15 = CPInfo.LeadByte;
        if ( CPInfo.LeadByte[0] )
        {
          while ( v15[1] )
          {
            if ( (unsigned __int8)*String >= *v15 && (unsigned __int8)*String <= v15[1] )
              return 2;
            v15 += 2;
            if ( !*v15 )
              return 1;
          }
        }
      }
      return 1;
    }
  }
  v16 = _acrt_MultiByteToWideChar(v12, 9, a4, (unsigned int)v8, 0, 0);
  v17 = v16;
  if ( !v16 )
    return 0;
  v18 = (2LL * v16 + 16) & -(__int64)(2LL * v16 < (unsigned __int64)(2LL * v16 + 16));
  if ( !v18 )
    return 0;
  if ( v18 > 0x400 )
  {
    v22 = (WCHAR *)malloc_base(v18);
    v21 = v22;
    if ( !v22 )
      goto LABEL_41;
    *(_DWORD *)v22 = 56797;
  }
  else
  {
    v19 = v18 + 15;
    if ( v18 + 15 < v18 )
      v19 = 0xFFFFFFFFFFFFFF0LL;
    v20 = alloca(v19 & 0xFFFFFFFFFFFFFFF0uLL);
    v21 = (const WCHAR *)&v35;
    if ( v34 == (_BYTE *)-80LL )
      return 0;
    v35 = 52428;
  }
  v21 += 8;
LABEL_41:
  if ( !v21 )
    return 0;
  if ( !(unsigned int)_acrt_MultiByteToWideChar(v12, 1, a4, (unsigned int)v8, v21, v17) )
    goto LABEL_63;
  v23 = _acrt_MultiByteToWideChar(v12, 9, String, (unsigned int)v11, 0, 0);
  v24 = v23;
  if ( !v23 )
    goto LABEL_63;
  v25 = (2LL * v23 + 16) & -(__int64)(2LL * v23 < (unsigned __int64)(2LL * v23 + 16));
  if ( !v25 )
    goto LABEL_63;
  if ( v25 > 0x400 )
  {
    v29 = (WCHAR *)malloc_base(v25);
    v28 = v29;
    if ( !v29 )
      goto LABEL_53;
    *(_DWORD *)v29 = 56797;
  }
  else
  {
    v26 = v25 + 15;
    if ( v25 + 15 < v25 )
      v26 = 0xFFFFFFFFFFFFFF0LL;
    v27 = alloca(v26 & 0xFFFFFFFFFFFFFFF0uLL);
    v28 = (const WCHAR *)&v35;
    if ( v34 == (_BYTE *)-80LL )
      goto LABEL_63;
    v35 = 52428;
  }
  v28 += 8;
LABEL_53:
  if ( !v28 )
  {
LABEL_63:
    v31 = (WCHAR *)(v21 - 8);
    v32 = *((_DWORD *)v21 - 4) == 56797;
LABEL_64:
    if ( v32 )
      free_base(v31);
    return 0;
  }
  v30 = (WCHAR *)(v28 - 8);
  if ( !(unsigned int)_acrt_MultiByteToWideChar(v12, 1, v36, (unsigned int)v11, v28, v24) )
  {
    if ( *(_DWORD *)v30 == 56797 )
      free_base(v30);
    v31 = (WCHAR *)(v21 - 8);
    v32 = *((_DWORD *)v21 - 4) == 56797;
    goto LABEL_64;
  }
  v33 = _acrt_CompareStringEx(v37, v35, v21, v17, v28, v24, 0, 0, 0);
  if ( *(_DWORD *)v30 == 56797 )
    free_base(v30);
  if ( *((_DWORD *)v21 - 4) == 56797 )
    free_base((void *)(v21 - 8));
  return v33;
}

```

## disassembly

```asm
0x18001a41c  push    rbp
0x18001a41e  push    rbx
0x18001a41f  push    rsi
0x18001a420  push    rdi
0x18001a421  push    r12
0x18001a423  push    r13
0x18001a425  push    r14
0x18001a427  push    r15
0x18001a429  sub     rsp, 98h
0x18001a430  lea     rbp, [rsp+50h]
0x18001a435  mov     rax, cs:__security_cookie
0x18001a43c  xor     rax, rbp
0x18001a43f  mov     [rbp+80h+var_50], rax
0x18001a443  movsxd  rdi, [rbp+80h+arg_20]
0x18001a44a  xor     r13d, r13d
0x18001a44d  mov     r12, [rbp+80h+String]
0x18001a454  mov     r14, r9
0x18001a457  mov     [rbp+80h+var_80], r8d
0x18001a45b  mov     rbx, rcx
0x18001a45e  mov     [rbp+80h+var_70], rdx
0x18001a462  mov     [rbp+80h+var_78], r12
0x18001a466  test    edi, edi
0x18001a468  jle     short loc_18001A47A
0x18001a46a  mov     rdx, rdi; Count
0x18001a46d  mov     rcx, r9; String
0x18001a470  call    __strncnt
0x18001a475  mov     rdi, rax
0x18001a478  jmp     short loc_18001A483
0x18001a47a  cmp     edi, 0FFFFFFFFh
0x18001a47d  jl      loc_18001A785
0x18001a483  movsxd  rsi, [rbp+80h+arg_30]
0x18001a48a  test    esi, esi
0x18001a48c  jle     short loc_18001A49E
0x18001a48e  mov     rdx, rsi; Count
0x18001a491  mov     rcx, r12; String
0x18001a494  call    __strncnt
0x18001a499  mov     rsi, rax
0x18001a49c  jmp     short loc_18001A4A7
0x18001a49e  cmp     esi, 0FFFFFFFFh
0x18001a4a1  jl      loc_18001A785
0x18001a4a7  mov     r15d, [rbp+80h+CodePage]
0x18001a4ae  test    r15d, r15d
0x18001a4b1  jnz     short loc_18001A4BA
0x18001a4b3  mov     rax, [rbx]
0x18001a4b6  mov     r15d, [rax+0Ch]
0x18001a4ba  test    edi, edi
0x18001a4bc  jz      short loc_18001A4C6
0x18001a4be  test    esi, esi
0x18001a4c0  jnz     loc_18001A578
0x18001a4c6  xor     eax, eax
0x18001a4c8  xorps   xmm0, xmm0
0x18001a4cb  mov     dword ptr [rbp+80h+CPInfo.LeadByte+0Ah], eax
0x18001a4ce  movups  xmmword ptr [rbp+80h+CPInfo.MaxCharSize], xmm0
0x18001a4d2  cmp     edi, esi
0x18001a4d4  jz      loc_18001A7A4
0x18001a4da  cmp     esi, 1
0x18001a4dd  jg      loc_18001A56E
0x18001a4e3  cmp     edi, 1
0x18001a4e6  jg      short loc_18001A530
0x18001a4e8  lea     rdx, [rbp+80h+CPInfo]; lpCPInfo
0x18001a4ec  mov     ecx, r15d; CodePage
0x18001a4ef  call    cs:__imp_GetCPInfo
0x18001a4f5  test    eax, eax
0x18001a4f7  jz      loc_18001A785
0x18001a4fd  test    edi, edi
0x18001a4ff  jle     short loc_18001A53A
0x18001a501  cmp     [rbp+80h+CPInfo.MaxCharSize], 2
0x18001a505  jb      short loc_18001A530
0x18001a507  lea     rax, [rbp+80h+CPInfo.LeadByte]
0x18001a50b  cmp     [rbp+80h+CPInfo.LeadByte], r13b
0x18001a50f  jz      short loc_18001A530
0x18001a511  cmp     [rax+1], r13b
0x18001a515  jz      short loc_18001A530
0x18001a517  mov     cl, [r14]
0x18001a51a  cmp     cl, [rax]
0x18001a51c  jb      short loc_18001A527
0x18001a51e  cmp     cl, [rax+1]
0x18001a521  jbe     loc_18001A7A4
0x18001a527  add     rax, 2
0x18001a52b  cmp     [rax], r13b
0x18001a52e  jnz     short loc_18001A511
0x18001a530  mov     eax, 3
0x18001a535  jmp     loc_18001A787
0x18001a53a  test    esi, esi
0x18001a53c  jle     short loc_18001A578
0x18001a53e  cmp     [rbp+80h+CPInfo.MaxCharSize], 2
0x18001a542  jb      short loc_18001A56E
0x18001a544  lea     rax, [rbp+80h+CPInfo.LeadByte]
0x18001a548  cmp     [rbp+80h+CPInfo.LeadByte], r13b
0x18001a54c  jz      short loc_18001A56E
0x18001a54e  cmp     [rax+1], r13b
0x18001a552  jz      short loc_18001A56E
0x18001a554  mov     cl, [r12]
0x18001a558  cmp     cl, [rax]
0x18001a55a  jb      short loc_18001A565
0x18001a55c  cmp     cl, [rax+1]
0x18001a55f  jbe     loc_18001A7A4
0x18001a565  add     rax, 2
0x18001a569  cmp     [rax], r13b
0x18001a56c  jnz     short loc_18001A54E
0x18001a56e  mov     eax, 1
0x18001a573  jmp     loc_18001A787
0x18001a578  mov     [rsp+0D0h+var_A8], r13d
0x18001a57d  mov     r9d, edi
0x18001a580  mov     r8, r14
0x18001a583  mov     [rsp+0D0h+var_B0], r13
0x18001a588  mov     edx, 9
0x18001a58d  mov     ecx, r15d
0x18001a590  call    __acrt_MultiByteToWideChar
0x18001a595  movsxd  r13, eax
0x18001a598  test    eax, eax
0x18001a59a  jz      loc_18001A785
0x18001a5a0  mov     rdx, r13
0x18001a5a3  add     rdx, rdx
0x18001a5a6  lea     rcx, [rdx+10h]
0x18001a5aa  cmp     rdx, rcx
0x18001a5ad  sbb     rdx, rdx
0x18001a5b0  and     rdx, rcx
0x18001a5b3  jz      loc_18001A785
0x18001a5b9  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001a5c3  cmp     rdx, 400h
0x18001a5ca  ja      short loc_18001A5FA
0x18001a5cc  lea     rax, [rdx+0Fh]
0x18001a5d0  cmp     rax, rdx
0x18001a5d3  ja      short loc_18001A5D8
0x18001a5d5  mov     rax, rcx
0x18001a5d8  and     rax, 0FFFFFFFFFFFFFFF0h
0x18001a5dc  call    _alloca_probe
0x18001a5e1  sub     rsp, rax
0x18001a5e4  lea     rbx, [rsp+0D0h+var_80]
0x18001a5e9  test    rbx, rbx
0x18001a5ec  jz      loc_18001A785
0x18001a5f2  mov     dword ptr [rbx], 0CCCCh
0x18001a5f8  jmp     short loc_18001A610
0x18001a5fa  mov     rcx, rdx; Size
0x18001a5fd  call    _malloc_base
0x18001a602  mov     rbx, rax
0x18001a605  test    rax, rax
0x18001a608  jz      short loc_18001A614
0x18001a60a  mov     dword ptr [rax], 0DDDDh
0x18001a610  add     rbx, 10h
0x18001a614  test    rbx, rbx
0x18001a617  jz      loc_18001A785
0x18001a61d  mov     [rsp+0D0h+var_A8], r13d
0x18001a622  mov     r9d, edi
0x18001a625  mov     r8, r14
0x18001a628  mov     [rsp+0D0h+var_B0], rbx
0x18001a62d  mov     edx, 1
0x18001a632  mov     ecx, r15d
0x18001a635  call    __acrt_MultiByteToWideChar
0x18001a63a  test    eax, eax
0x18001a63c  jz      loc_18001A774
0x18001a642  and     [rsp+0D0h+var_A8], 0
0x18001a647  mov     r9d, esi
0x18001a64a  and     [rsp+0D0h+var_B0], 0
0x18001a650  mov     r8, r12
0x18001a653  mov     edx, 9
0x18001a658  mov     ecx, r15d
0x18001a65b  call    __acrt_MultiByteToWideChar
0x18001a660  movsxd  r12, eax
0x18001a663  test    eax, eax
0x18001a665  jz      loc_18001A774
0x18001a66b  mov     rcx, r12
0x18001a66e  add     rcx, rcx
0x18001a671  lea     rax, [rcx+10h]
0x18001a675  cmp     rcx, rax
0x18001a678  sbb     rcx, rcx
0x18001a67b  and     rcx, rax; Size
0x18001a67e  jz      loc_18001A774
0x18001a684  cmp     rcx, 400h
0x18001a68b  ja      short loc_18001A6C2
0x18001a68d  lea     rax, [rcx+0Fh]
0x18001a691  cmp     rax, rcx
0x18001a694  ja      short loc_18001A6A0
0x18001a696  mov     rax, 0FFFFFFFFFFFFFF0h
0x18001a6a0  and     rax, 0FFFFFFFFFFFFFFF0h
0x18001a6a4  call    _alloca_probe
0x18001a6a9  sub     rsp, rax
0x18001a6ac  lea     rdi, [rsp+0D0h+var_80]
0x18001a6b1  test    rdi, rdi
0x18001a6b4  jz      loc_18001A774
0x18001a6ba  mov     dword ptr [rdi], 0CCCCh
0x18001a6c0  jmp     short loc_18001A6D5
0x18001a6c2  call    _malloc_base
0x18001a6c7  mov     rdi, rax
0x18001a6ca  test    rax, rax
0x18001a6cd  jz      short loc_18001A6D9
0x18001a6cf  mov     dword ptr [rax], 0DDDDh
0x18001a6d5  add     rdi, 10h
0x18001a6d9  test    rdi, rdi
0x18001a6dc  jz      loc_18001A774
0x18001a6e2  mov     r8, [rbp+80h+var_78]
0x18001a6e6  lea     r14, [rdi-10h]
0x18001a6ea  mov     [rsp+0D0h+var_A8], r12d
0x18001a6ef  mov     r9d, esi
0x18001a6f2  mov     edx, 1
0x18001a6f7  mov     [rsp+0D0h+var_B0], rdi
0x18001a6fc  mov     ecx, r15d
0x18001a6ff  call    __acrt_MultiByteToWideChar
0x18001a704  xor     ecx, ecx
0x18001a706  test    eax, eax
0x18001a708  jnz     short loc_18001A724
0x18001a70a  mov     edi, 0DDDDh
0x18001a70f  cmp     [r14], edi
0x18001a712  jnz     short loc_18001A71C
0x18001a714  mov     rcx, r14; Block
0x18001a717  call    _free_base
0x18001a71c  lea     rcx, [rbx-10h]
0x18001a720  cmp     [rcx], edi
0x18001a722  jmp     short loc_18001A77E
0x18001a724  mov     edx, [rbp+80h+var_80]
0x18001a727  mov     r9d, r13d
0x18001a72a  mov     [rsp+0D0h+var_90], rcx
0x18001a72f  mov     r8, rbx
0x18001a732  mov     [rsp+0D0h+var_98], rcx
0x18001a737  mov     [rsp+0D0h+var_A0], rcx
0x18001a73c  mov     rcx, [rbp+80h+var_70]
0x18001a740  mov     [rsp+0D0h+var_A8], r12d
0x18001a745  mov     [rsp+0D0h+var_B0], rdi
0x18001a74a  call    __acrt_CompareStringEx
0x18001a74f  mov     esi, 0DDDDh
0x18001a754  mov     edi, eax
0x18001a756  cmp     [r14], esi
0x18001a759  jnz     short loc_18001A763
0x18001a75b  mov     rcx, r14; Block
0x18001a75e  call    _free_base
0x18001a763  lea     rcx, [rbx-10h]; Block
0x18001a767  cmp     [rcx], esi
0x18001a769  jnz     short loc_18001A770
0x18001a76b  call    _free_base
0x18001a770  mov     eax, edi
0x18001a772  jmp     short loc_18001A787
0x18001a774  lea     rcx, [rbx-10h]; Block
0x18001a778  cmp     dword ptr [rcx], 0DDDDh
0x18001a77e  jnz     short loc_18001A785
0x18001a780  call    _free_base
0x18001a785  xor     eax, eax
0x18001a787  mov     rcx, [rbp+80h+var_50]
0x18001a78b  xor     rcx, rbp; StackCookie
0x18001a78e  call    __security_check_cookie
0x18001a793  lea     rsp, [rbp+48h]
0x18001a797  pop     r15
0x18001a799  pop     r14
0x18001a79b  pop     r13
0x18001a79d  pop     r12
0x18001a79f  pop     rdi
0x18001a7a0  pop     rsi
0x18001a7a1  pop     rbx
0x18001a7a2  pop     rbp
0x18001a7a3  retn
0x18001a7a4  mov     eax, 2
0x18001a7a9  jmp     short loc_18001A787
```
