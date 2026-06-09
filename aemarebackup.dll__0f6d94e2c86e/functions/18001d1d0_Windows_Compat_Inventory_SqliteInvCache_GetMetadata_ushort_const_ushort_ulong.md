# Windows::Compat::Inventory::SqliteInvCache::GetMetadata(ushort const *,ushort *,ulong &)

- ea: `0x18001d1d0`
- end: `0x18001d4ca`
- name: `?GetMetadata@SqliteInvCache@Inventory@Compat@Windows@@UEBAJPEBGPEAGAEAK@Z`
- size: `762`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180004ea0`
- `0x18000d5b8`
- `0x18001209c`
- `0x1800134b8`
- `0x18001d1d0`
- `0x1800276cc`
- `0x180027d3c`
- `0x18004c020`
- `0x180059d64`
- `0x1800a494c`
- `0x1800c2b60`
- `0x1800c4b00`
- `0x1800c5440`
- `0x1800c7810`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d39d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d39d`

## string_xrefs

- `0x18001d30f`: `Windows::Compat::Inventory::SqliteInvCache::GetMetadata`
- `0x18001d47e`: `Windows::Compat::Inventory::SqliteInvCache::GetMetadata`
- `0x18001d43e`: `StringCchCopyW failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::GetMetadata(
        Windows::Compat::Inventory::SqliteInvCache *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  int v5; // ebx
  _QWORD *v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int128 *v10; // rdx
  __int64 v11; // r14
  int v12; // edi
  __int64 v13; // r15
  signed int v14; // ebx
  int v15; // esi
  __int64 v16; // rax
  const char *v17; // r9
  __int64 v18; // r8
  int i; // ebx
  const unsigned __int16 *v20; // rax
  __int64 v21; // r11
  const char *v22; // r9
  __int64 v23; // r8
  __int64 v25; // [rsp+20h] [rbp-69h]
  __int64 v26; // [rsp+28h] [rbp-61h]
  __int64 v27; // [rsp+28h] [rbp-61h]
  __int64 v28; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 *v29; // [rsp+48h] [rbp-41h]
  __int128 v30; // [rsp+50h] [rbp-39h] BYREF
  __int128 v31; // [rsp+60h] [rbp-29h]
  char *Src[4]; // [rsp+70h] [rbp-19h] BYREF

  v29 = a3;
  v5 = (int)a2;
  v7 = (_QWORD *)((char *)this + 104);
  v8 = *((_QWORD *)this + 15);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v8) < 0x12 )
    std::_Xlen_string();
  if ( v7[3] > 7u )
    v7 = (_QWORD *)*v7;
  std::wstring::wstring(Src, v7, a3, L"SELECT Value FROM ", 18, v7, v8);
  v9 = std::wstring::append(Src, L" WHERE Name = ?;");
  v30 = 0;
  v31 = 0;
  v30 = *(_OWORD *)v9;
  v31 = *(_OWORD *)(v9 + 16);
  *(_QWORD *)(v9 + 16) = 0;
  *(_QWORD *)(v9 + 24) = 7;
  *(_WORD *)v9 = 0;
  std::wstring::~wstring(Src);
  v28 = 0;
  v10 = &v30;
  if ( *((_QWORD *)&v31 + 1) > 7u )
    LODWORD(v10) = v30;
  v11 = -1;
  v12 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v10, -1, 128, (__int64)&v28, 0);
  v13 = v28;
  if ( v12 )
  {
    if ( v12 > 0 )
      v14 = (unsigned __int16)v12 | 0x80070000;
    else
      v14 = v12;
    v27 = sqlite3_errmsg(*((_QWORD *)this + 1));
    LODWORD(v25) = v12;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::GetMetadata",
      1090,
      "sqlite3_prepare_v2 failed: [%d] %hs",
      v25,
      v27);
    goto LABEL_38;
  }
  if ( v28 )
  {
    LOBYTE(v26) = 2;
    v15 = bindText(v28, 1, v5, -2, 0, v26);
    if ( v15 )
    {
      if ( v15 > 0 )
        v14 = (unsigned __int16)v15 | 0x80070000;
      else
        v14 = v15;
      v16 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v17 = "sqlite3_bind_text16 failed: [%d] %hs";
      v18 = 1104;
LABEL_18:
      LODWORD(v25) = v15;
      AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::GetMetadata", v18, v17, v25, v16);
      goto LABEL_38;
    }
    for ( i = 0; i < 100; ++i )
    {
      v15 = sqlite3_step(v13);
      if ( (unsigned int)(v15 - 5) > 1 )
        break;
      Sleep(5u);
    }
    if ( v15 == 101 )
    {
      v14 = -2147024894;
      goto LABEL_38;
    }
    if ( v15 != 100 )
    {
      if ( v15 > 0 )
        v14 = (unsigned __int16)v15 | 0x80070000;
      else
        v14 = v15;
      v16 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v17 = "sqlite3_step failed: [%d] %hs";
      v18 = 1116;
      goto LABEL_18;
    }
    v20 = (const unsigned __int16 *)sqlite3_column_text16(v13, 0);
    v14 = StringCchCopyW(v29, *a4, v20);
    if ( v14 == -2147024774 )
    {
      do
        ++v11;
      while ( *(_WORD *)(v21 + 2 * v11) );
      *a4 = v11 + 1;
      LODWORD(v25) = -2147024774;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::GetMetadata",
        1124,
        "StringValue buffer is too small [%#x]",
        v25);
      goto LABEL_38;
    }
    if ( v14 >= 0 )
    {
      do
        ++v11;
      while ( *(_WORD *)(v21 + 2 * v11) );
      *a4 = v11 + 1;
      goto LABEL_38;
    }
    v22 = "StringCchCopyW failed [%#x]";
    v23 = 1129;
  }
  else
  {
    v14 = -2147467259;
    v22 = "sqlite3_prepare_v2 returned a null statement [%#x]";
    v23 = 1096;
  }
  LODWORD(v25) = v14;
  AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::GetMetadata", v23, v22, v25);
LABEL_38:
  if ( v13 )
    sqlite3_finalize(v13);
  std::wstring::~wstring((char **)&v30);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001d1d0  push    rbp
0x18001d1d2  push    rbx
0x18001d1d3  push    rsi
0x18001d1d4  push    rdi
0x18001d1d5  push    r12
0x18001d1d7  push    r13
0x18001d1d9  push    r14
0x18001d1db  push    r15
0x18001d1dd  lea     rbp, [rsp-1Fh]
0x18001d1e2  sub     rsp, 0A8h
0x18001d1e9  mov     rax, cs:__security_cookie
0x18001d1f0  xor     rax, rsp
0x18001d1f3  mov     [rbp+57h+var_50], rax
0x18001d1f7  mov     r12, r9
0x18001d1fa  mov     [rbp+57h+var_98], r8
0x18001d1fe  mov     rbx, rdx
0x18001d201  mov     r13, rcx
0x18001d204  xor     edi, edi
0x18001d206  lea     rdx, [rcx+68h]
0x18001d20a  mov     rcx, [rdx+10h]
0x18001d20e  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001d218  sub     rax, rcx
0x18001d21b  cmp     rax, 12h
0x18001d21f  jb      loc_18001D4C4
0x18001d225  cmp     qword ptr [rdx+18h], 7
0x18001d22a  jbe     short loc_18001D22F
0x18001d22c  mov     rdx, [rdx]
0x18001d22f  mov     [rsp+0E0h+var_B0], rcx
0x18001d234  mov     [rsp+0E0h+var_B8], rdx
0x18001d239  mov     [rsp+0E0h+var_C0], 12h
0x18001d242  lea     r9, aSelectValueFro; "SELECT Value FROM "
0x18001d249  lea     rcx, [rbp+57h+Src]
0x18001d24d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001d252  nop
0x18001d253  lea     rdx, aWhereName; " WHERE Name = ?;"
0x18001d25a  lea     rcx, [rbp+57h+Src]; Src
0x18001d25e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001d263  xorps   xmm0, xmm0
0x18001d266  movups  [rbp+57h+var_90], xmm0
0x18001d26a  xorps   xmm1, xmm1
0x18001d26d  movdqu  [rbp+57h+var_80], xmm1
0x18001d272  movups  xmm0, xmmword ptr [rax]
0x18001d275  movups  [rbp+57h+var_90], xmm0
0x18001d279  movups  xmm1, xmmword ptr [rax+10h]
0x18001d27d  movups  [rbp+57h+var_80], xmm1
0x18001d281  mov     [rax+10h], rdi
0x18001d285  mov     qword ptr [rax+18h], 7
0x18001d28d  mov     [rax], di
0x18001d290  lea     rcx, [rbp+57h+Src]
0x18001d294  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d299  nop
0x18001d29a  mov     [rbp+57h+var_A0], rdi
0x18001d29e  lea     rdx, [rbp+57h+var_90]
0x18001d2a2  cmp     qword ptr [rbp+57h+var_80+8], 7
0x18001d2a7  cmova   rdx, qword ptr [rbp+57h+var_90]
0x18001d2ac  mov     [rsp+0E0h+var_B8], rdi
0x18001d2b1  lea     rax, [rbp+57h+var_A0]
0x18001d2b5  mov     [rsp+0E0h+var_C0], rax
0x18001d2ba  mov     r9d, 80h
0x18001d2c0  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001d2c4  mov     r8d, r14d
0x18001d2c7  mov     rcx, [r13+8]
0x18001d2cb  call    sqlite3Prepare16
0x18001d2d0  mov     edi, eax
0x18001d2d2  mov     r15, [rbp+57h+var_A0]
0x18001d2d6  xor     eax, eax
0x18001d2d8  test    edi, edi
0x18001d2da  jz      short loc_18001D320
0x18001d2dc  jg      short loc_18001D2E2
0x18001d2de  mov     ebx, edi
0x18001d2e0  jmp     short loc_18001D2EB
0x18001d2e2  movzx   ebx, di
0x18001d2e5  or      ebx, 80070000h
0x18001d2eb  mov     rcx, [r13+8]
0x18001d2ef  call    sqlite3_errmsg
0x18001d2f4  mov     [rsp+0E0h+var_B8], rax
0x18001d2f9  mov     dword ptr [rsp+0E0h+var_C0], edi
0x18001d2fd  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x18001d304  mov     r8d, 442h
0x18001d30a  mov     ecx, 1
0x18001d30f  lea     rdx, aWindowsCompatI_44; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001d316  call    AslLogCallPrintf
0x18001d31b  jmp     loc_18001D48B
0x18001d320  test    r15, r15
0x18001d323  jz      loc_18001D463
0x18001d329  mov     byte ptr [rsp+0E0h+var_B8], 2
0x18001d32e  mov     [rsp+0E0h+var_C0], rax
0x18001d333  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18001d33a  mov     r8, rbx
0x18001d33d  lea     edi, [r9+3]
0x18001d341  mov     edx, edi
0x18001d343  mov     rcx, r15
0x18001d346  call    bindText
0x18001d34b  mov     esi, eax
0x18001d34d  xor     eax, eax
0x18001d34f  test    esi, esi
0x18001d351  jz      short loc_18001D385
0x18001d353  jg      short loc_18001D359
0x18001d355  mov     ebx, esi
0x18001d357  jmp     short loc_18001D362
0x18001d359  movzx   ebx, si
0x18001d35c  or      ebx, 80070000h
0x18001d362  mov     rcx, [r13+8]
0x18001d366  call    sqlite3_errmsg
0x18001d36b  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x18001d372  mov     r8d, 450h
0x18001d378  mov     [rsp+0E0h+var_B8], rax
0x18001d37d  mov     dword ptr [rsp+0E0h+var_C0], esi
0x18001d381  mov     ecx, edi
0x18001d383  jmp     short loc_18001D30F
0x18001d385  mov     ebx, eax
0x18001d387  mov     rcx, r15
0x18001d38a  call    sqlite3_step
0x18001d38f  mov     esi, eax
0x18001d391  lea     ecx, [rax-5]
0x18001d394  cmp     ecx, edi
0x18001d396  ja      short loc_18001D3AA
0x18001d398  mov     ecx, 5; dwMilliseconds
0x18001d39d  call    cs:__imp_Sleep
0x18001d3a3  add     ebx, edi
0x18001d3a5  cmp     ebx, 64h ; 'd'
0x18001d3a8  jl      short loc_18001D387
0x18001d3aa  cmp     esi, 65h ; 'e'
0x18001d3ad  jnz     short loc_18001D3B9
0x18001d3af  mov     ebx, 80070002h
0x18001d3b4  jmp     loc_18001D48B
0x18001d3b9  cmp     esi, 64h ; 'd'
0x18001d3bc  jz      short loc_18001D3E7
0x18001d3be  test    esi, esi
0x18001d3c0  jg      short loc_18001D3C6
0x18001d3c2  mov     ebx, esi
0x18001d3c4  jmp     short loc_18001D3CF
0x18001d3c6  movzx   ebx, si
0x18001d3c9  or      ebx, 80070000h
0x18001d3cf  mov     rcx, [r13+8]
0x18001d3d3  call    sqlite3_errmsg
0x18001d3d8  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x18001d3df  mov     r8d, 45Ch
0x18001d3e5  jmp     short loc_18001D378
0x18001d3e7  xor     edx, edx
0x18001d3e9  mov     rcx, r15
0x18001d3ec  call    sqlite3_column_text16
0x18001d3f1  mov     r11, rax
0x18001d3f4  mov     edx, [r12]; unsigned __int64
0x18001d3f8  mov     r8, rax; unsigned __int16 *
0x18001d3fb  mov     rcx, [rbp+57h+var_98]; unsigned __int16 *
0x18001d3ff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d404  mov     ebx, eax
0x18001d406  mov     ecx, 8007007Ah
0x18001d40b  cmp     eax, ecx
0x18001d40d  jnz     short loc_18001D438
0x18001d40f  xor     eax, eax
0x18001d411  inc     r14
0x18001d414  cmp     [r11+r14*2], ax
0x18001d419  jnz     short loc_18001D411
0x18001d41b  lea     eax, [r14+1]
0x18001d41f  mov     [r12], eax
0x18001d423  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x18001d427  lea     r9, aStringvalueBuf; "StringValue buffer is too small [%#x]"
0x18001d42e  mov     r8d, 464h
0x18001d434  mov     ecx, edi
0x18001d436  jmp     short loc_18001D47E
0x18001d438  xor     eax, eax
0x18001d43a  test    ebx, ebx
0x18001d43c  jns     short loc_18001D44F
0x18001d43e  lea     r9, aStringcchcopyw; "StringCchCopyW failed [%#x]"
0x18001d445  mov     r8d, 469h
0x18001d44b  mov     ecx, edi
0x18001d44d  jmp     short loc_18001D47A
0x18001d44f  inc     r14
0x18001d452  cmp     [r11+r14*2], ax
0x18001d457  jnz     short loc_18001D44F
0x18001d459  lea     eax, [r14+1]
0x18001d45d  mov     [r12], eax
0x18001d461  jmp     short loc_18001D48B
0x18001d463  mov     ebx, 80004005h
0x18001d468  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x18001d46f  mov     r8d, 448h
0x18001d475  mov     ecx, 1
0x18001d47a  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18001d47e  lea     rdx, aWindowsCompatI_44; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001d485  call    AslLogCallPrintf
0x18001d48a  nop
0x18001d48b  test    r15, r15
0x18001d48e  jz      short loc_18001D499
0x18001d490  mov     rcx, r15
0x18001d493  call    sqlite3_finalize
0x18001d498  nop
0x18001d499  lea     rcx, [rbp+57h+var_90]
0x18001d49d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d4a2  mov     eax, ebx
0x18001d4a4  mov     rcx, [rbp+57h+var_50]
0x18001d4a8  xor     rcx, rsp; StackCookie
0x18001d4ab  call    __security_check_cookie
0x18001d4b0  add     rsp, 0A8h
0x18001d4b7  pop     r15
0x18001d4b9  pop     r14
0x18001d4bb  pop     r13
0x18001d4bd  pop     r12
0x18001d4bf  pop     rdi
0x18001d4c0  pop     rsi
0x18001d4c1  pop     rbx
0x18001d4c2  pop     rbp
0x18001d4c3  retn
0x18001d4c4  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
