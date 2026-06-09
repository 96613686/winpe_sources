# WindowsMidiServicesNamingLib::GenerateFilterPlusBlockMidi1PortName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uchar)

- ea: `0x18002c41c`
- end: `0x18002c682`
- name: `?GenerateFilterPlusBlockMidi1PortName@WindowsMidiServicesNamingLib@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00E@Z`
- size: `614`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x18002cab8`

## callees

- `0x180004180`
- `0x18000b740`
- `0x18000e178`
- `0x18000f0a4`
- `0x18000feb0`
- `0x1800134cc`
- `0x18001393c`
- `0x18001c5d8`
- `0x180022654`
- `0x18002bda8`
- `0x18002c0e0`
- `0x18002c41c`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesNamingLib::GenerateFilterPlusBlockMidi1PortName(
        __int64 a1,
        wchar_t *a2,
        __int64 a3,
        __int64 a4,
        char a5)
{
  void *v9; // rbx
  void *v10; // rax
  void *v11; // rax
  __int64 v12; // rbx
  void *v13; // rax
  __int64 v14; // rax
  wchar_t *v15; // rdx
  __int64 v16; // rax
  __int128 *v17; // rdx
  __int64 v18; // rax
  void *v19; // rax
  _BYTE v21[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[32]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v23; // [rsp+80h] [rbp-80h] BYREF
  __int128 v24; // [rsp+90h] [rbp-70h]
  _BYTE Src[32]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v26; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v27; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v28; // [rsp+D8h] [rbp-28h]
  _BYTE v29[32]; // [rsp+E0h] [rbp-20h] BYREF

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  v9 = (void *)std::wstring::wstring(Src, a3);
  v10 = (void *)std::wstring::wstring(v29, a2);
  WindowsMidiServicesNamingLib::FullyCleanupBlockName(&v26, a4, v10, v9);
  v11 = (void *)std::wstring::wstring(v21, &v26);
  v12 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v11);
  if ( *(_QWORD *)(a3 + 16) == 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  std::wstring::wstring(&v23);
  v13 = (void *)std::operator+<unsigned short>(v22, &v23, v12);
  v14 = WindowsMidiServicesInternal::TrimmedWStringCopy(v29, v13);
  std::wstring::operator=(a1, v14);
  std::wstring::~wstring(v29);
  std::wstring::~wstring(&v23);
  std::wstring::~wstring(Src);
  if ( !*(_QWORD *)(a1 + 16) )
  {
    v23 = 0;
    v24 = 0;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v15 = a2;
    else
      v15 = *(wchar_t **)a2;
    std::wstring::_Construct<1,unsigned short const *>(&v23, v15);
    v16 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src, &v23);
    std::wstring::operator=(a1, v16);
    std::wstring::~wstring(Src);
  }
  if ( (unsigned __int64)(*(_QWORD *)(a1 + 16) + 1LL) > 0x20 )
  {
    v23 = 0;
    v24 = 0;
    if ( v27 )
    {
      v17 = &v26;
      if ( v28 > 7 )
        v17 = (__int128 *)v26;
    }
    else if ( *(_QWORD *)(a3 + 24) <= 7u )
    {
      v17 = (__int128 *)a3;
    }
    else
    {
      v17 = *(__int128 **)a3;
    }
    std::wstring::_Construct<1,unsigned short const *>(&v23, v17);
    v18 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src, &v23);
    std::wstring::operator=(a1, v18);
    std::wstring::~wstring(Src);
  }
  v19 = WindowsMidiServicesNamingLib::AddGroupNumberToNameIfNeeded(Src, a2, (wchar_t *)a3, (const wchar_t *)a1, a5);
  std::wstring::operator=(a1, v19);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(&v26);
  return a1;
}

```

## disassembly

```asm
0x18002c41c  push    rbp
0x18002c41e  push    rbx
0x18002c41f  push    rsi
0x18002c420  push    rdi
0x18002c421  push    r12
0x18002c423  push    r14
0x18002c425  push    r15
0x18002c427  lea     rbp, [rsp-10h]
0x18002c42c  sub     rsp, 110h
0x18002c433  mov     rax, cs:__security_cookie
0x18002c43a  xor     rax, rsp
0x18002c43d  mov     [rbp+40h+var_40], rax
0x18002c441  mov     rdi, r9
0x18002c444  mov     rsi, r8
0x18002c447  mov     r15, rdx
0x18002c44a  mov     r14, rcx
0x18002c44d  mov     r12b, [rbp+40h+arg_20]
0x18002c451  xorps   xmm0, xmm0
0x18002c454  movups  xmmword ptr [rcx], xmm0
0x18002c457  mov     qword ptr [rcx+10h], 0
0x18002c45f  mov     qword ptr [rcx+18h], 7
0x18002c467  xor     eax, eax
0x18002c469  mov     [rcx], ax
0x18002c46c  mov     rdx, r8
0x18002c46f  lea     rcx, [rbp+40h+Src]
0x18002c473  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c478  mov     rbx, rax
0x18002c47b  mov     rdx, r15
0x18002c47e  lea     rcx, [rbp+40h+var_60]
0x18002c482  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c487  mov     r9, rbx
0x18002c48a  mov     r8, rax
0x18002c48d  mov     rdx, rdi
0x18002c490  lea     rcx, [rbp+40h+var_80]; Src
0x18002c494  call    ?FullyCleanupBlockName@WindowsMidiServicesNamingLib@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@V23@1@Z; WindowsMidiServicesNamingLib::FullyCleanupBlockName(std::wstring const &,std::wstring,std::wstring)
0x18002c499  lea     rdx, [rbp+40h+var_80]
0x18002c49d  lea     rcx, [rsp+140h+var_100]
0x18002c4a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c4a7  mov     rdx, rax; void *
0x18002c4aa  lea     rcx, [rbp+40h+Src]; Src
0x18002c4ae  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18002c4b3  mov     rbx, rax
0x18002c4b6  mov     rcx, [rsi+10h]
0x18002c4ba  mov     rax, 7FFFFFFFFFFFFFFEh
0x18002c4c4  sub     rax, rcx
0x18002c4c7  cmp     rax, 1
0x18002c4cb  jb      loc_18002C67C
0x18002c4d1  cmp     qword ptr [rsi+18h], 7
0x18002c4d6  jbe     short loc_18002C4DD
0x18002c4d8  mov     r9, [rsi]
0x18002c4db  jmp     short loc_18002C4E0
0x18002c4dd  mov     r9, rsi
0x18002c4e0  mov     [rsp+140h+var_110], 1
0x18002c4e9  lea     rax, asc_180053C68; " "
0x18002c4f0  mov     [rsp+140h+var_118], rax
0x18002c4f5  mov     qword ptr [rsp+140h+var_120], rcx
0x18002c4fa  lea     rcx, [rbp+40h+var_C0]
0x18002c4fe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002c503  mov     r8, rbx
0x18002c506  lea     rdx, [rbp+40h+var_C0]
0x18002c50a  lea     rcx, [rsp+140h+var_E0]
0x18002c50f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18002c514  mov     rdx, rax; void *
0x18002c517  lea     rcx, [rbp+40h+var_60]; Src
0x18002c51b  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18002c520  mov     rdx, rax
0x18002c523  mov     rcx, r14
0x18002c526  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002c52b  lea     rcx, [rbp+40h+var_60]; void *
0x18002c52f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c534  lea     rcx, [rbp+40h+var_C0]; void *
0x18002c538  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c53d  lea     rcx, [rbp+40h+Src]; void *
0x18002c541  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c546  mov     ebx, 1Fh
0x18002c54b  cmp     qword ptr [r14+10h], 0
0x18002c550  jnz     short loc_18002C5A6
0x18002c552  xorps   xmm0, xmm0
0x18002c555  movups  [rbp+40h+var_C0], xmm0
0x18002c559  xorps   xmm1, xmm1
0x18002c55c  movdqu  [rbp+40h+var_B0], xmm1
0x18002c561  mov     r8d, ebx
0x18002c564  cmp     [r15+10h], rbx
0x18002c568  cmovb   r8, [r15+10h]
0x18002c56d  cmp     qword ptr [r15+18h], 7
0x18002c572  jbe     short loc_18002C579
0x18002c574  mov     rdx, [r15]
0x18002c577  jmp     short loc_18002C57C
0x18002c579  mov     rdx, r15
0x18002c57c  lea     rcx, [rbp+40h+var_C0]
0x18002c580  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002c585  lea     rdx, [rbp+40h+var_C0]; void *
0x18002c589  lea     rcx, [rbp+40h+Src]; Src
0x18002c58d  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18002c592  mov     rdx, rax
0x18002c595  mov     rcx, r14
0x18002c598  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002c59d  lea     rcx, [rbp+40h+Src]; void *
0x18002c5a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c5a6  mov     rax, [r14+10h]
0x18002c5aa  inc     rax
0x18002c5ad  cmp     rax, 20h ; ' '
0x18002c5b1  jbe     short loc_18002C627
0x18002c5b3  mov     rax, [rbp+40h+var_70]
0x18002c5b7  xorps   xmm0, xmm0
0x18002c5ba  xorps   xmm1, xmm1
0x18002c5bd  movups  [rbp+40h+var_C0], xmm0
0x18002c5c1  movdqu  [rbp+40h+var_B0], xmm1
0x18002c5c6  test    rax, rax
0x18002c5c9  jz      short loc_18002C5E2
0x18002c5cb  cmp     rax, rbx
0x18002c5ce  cmovb   rbx, rax
0x18002c5d2  lea     rdx, [rbp+40h+var_80]
0x18002c5d6  cmp     [rbp+40h+var_68], 7
0x18002c5db  cmova   rdx, qword ptr [rbp+40h+var_80]
0x18002c5e0  jmp     short loc_18002C5FA
0x18002c5e2  cmp     [rsi+10h], rbx
0x18002c5e6  cmovb   rbx, [rsi+10h]
0x18002c5eb  cmp     qword ptr [rsi+18h], 7
0x18002c5f0  jbe     short loc_18002C5F7
0x18002c5f2  mov     rdx, [rsi]
0x18002c5f5  jmp     short loc_18002C5FA
0x18002c5f7  mov     rdx, rsi
0x18002c5fa  mov     r8, rbx
0x18002c5fd  lea     rcx, [rbp+40h+var_C0]
0x18002c601  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002c606  lea     rdx, [rbp+40h+var_C0]; void *
0x18002c60a  lea     rcx, [rbp+40h+Src]; Src
0x18002c60e  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18002c613  mov     rdx, rax
0x18002c616  mov     rcx, r14
0x18002c619  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002c61e  lea     rcx, [rbp+40h+Src]; void *
0x18002c622  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c627  mov     [rsp+140h+var_120], r12b; char
0x18002c62c  mov     r9, r14
0x18002c62f  mov     r8, rsi; wchar_t *
0x18002c632  mov     rdx, r15; S2
0x18002c635  lea     rcx, [rbp+40h+Src]; Src
0x18002c639  call    ?AddGroupNumberToNameIfNeeded@WindowsMidiServicesNamingLib@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00E@Z; WindowsMidiServicesNamingLib::AddGroupNumberToNameIfNeeded(std::wstring const &,std::wstring const &,std::wstring const &,uchar)
0x18002c63e  mov     rdx, rax
0x18002c641  mov     rcx, r14
0x18002c644  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002c649  lea     rcx, [rbp+40h+Src]; void *
0x18002c64d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c652  lea     rcx, [rbp+40h+var_80]; void *
0x18002c656  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c65b  mov     rax, r14
0x18002c65e  mov     rcx, [rbp+40h+var_40]
0x18002c662  xor     rcx, rsp; StackCookie
0x18002c665  call    __security_check_cookie
0x18002c66a  add     rsp, 110h
0x18002c671  pop     r15
0x18002c673  pop     r14
0x18002c675  pop     r12
0x18002c677  pop     rdi
0x18002c678  pop     rsi
0x18002c679  pop     rbx
0x18002c67a  pop     rbp
0x18002c67b  retn
0x18002c67c  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
