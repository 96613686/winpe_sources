# Windows::Compat::Inventory::CacheUtilities::SqliteCache::ClearProvider(ushort const *)

- ea: `0x14000f190`
- end: `0x14000f4d5`
- name: `?ClearProvider@SqliteCache@CacheUtilities@Inventory@Compat@Windows@@UEAAXPEBG@Z`
- size: `837`
- prototype: `void __fastcall(Windows::Compat::Inventory::CacheUtilities::SqliteCache *this, const unsigned __int16 *, __int64)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001ba0`
- `0x1400026d8`
- `0x140002780`
- `0x14000e0d8`
- `0x14000e730`
- `0x14000e814`
- `0x14000ea3c`
- `0x14000eacc`
- `0x14000ec78`
- `0x14000f190`
- `0x140010280`
- `0x140010eb0`
- `0x140010ee0`
- `0x14005086c`
- `0x14006a0dc`
- `0x14008abd0`
- `0x14008bab0`
- `0x14008cfa0`

## string_xrefs

- `0x14000f303`: `DELETE FROM `

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::CacheUtilities::SqliteCache::ClearProvider(
        Windows::Compat::Inventory::CacheUtilities::SqliteCache *this,
        const unsigned __int16 *a2,
        __int64 a3)
{
  _QWORD *v5; // r9
  __int64 v6; // rcx
  __int64 v7; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rcx
  _QWORD *v10; // r15
  _QWORD *v11; // rbx
  _QWORD *v12; // r9
  __int64 v13; // r8
  unsigned __int64 v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // rax
  __int64 *v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rcx
  _QWORD *v22; // r9
  __int64 *v23; // rdx
  __int64 v24; // [rsp+40h] [rbp-79h] BYREF
  __int64 v25; // [rsp+48h] [rbp-71h] BYREF
  __int128 v26; // [rsp+50h] [rbp-69h] BYREF
  __int64 v27; // [rsp+60h] [rbp-59h]
  __int64 Src[3]; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int64 v29; // [rsp+80h] [rbp-39h]
  _QWORD v30[4]; // [rsp+88h] [rbp-31h] BYREF
  _BYTE v31[32]; // [rsp+A8h] [rbp-11h] BYREF
  _BYTE v32[32]; // [rsp+C8h] [rbp+Fh] BYREF

  v25 = 0;
  v5 = (_QWORD *)((char *)this + 72);
  v6 = *((_QWORD *)this + 11);
  if ( v6 == 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  std::wstring::wstring(Src, a2, a3, v5, v6, L"\\", 1);
  v7 = std::operator+<unsigned short>(v31, Src, a2);
  std::operator+<unsigned short>(v30, v7, L".db");
  std::wstring::~wstring(v31);
  std::wstring::~wstring(Src);
  v26 = 0;
  v27 = 0;
  v8 = v30;
  if ( v30[3] > 7u )
    v8 = (_QWORD *)v30[0];
  if ( !(unsigned int)sqlite3_open16(v8, &v25) )
  {
    if ( (int)Windows::Compat::Inventory::CacheUtilities::SqliteCache::GetTableVersions(v9, v25, a2, &v26) >= 0 )
    {
      v10 = (_QWORD *)*((_QWORD *)&v26 + 1);
      v11 = (_QWORD *)v26;
      if ( (_QWORD)v26 == *((_QWORD *)&v26 + 1) )
      {
        fprintf(*((FILE *const *)this + 8), "Failed to find any tables");
      }
      else
      {
        do
        {
          if ( v11[3] <= 7u )
            v12 = v11;
          else
            v12 = (_QWORD *)*v11;
          fwprintf(*((FILE *const *)this + 8), L"Provider name: %ls%ls\n", a2, v12);
          std::wstring::wstring(Src, L"DELETE FROM ");
          v14 = -1;
          do
            ++v14;
          while ( a2[v14] );
          v15 = v11[2];
          if ( 0x7FFFFFFFFFFFFFFELL - v15 < v14 )
            std::_Xlen_string();
          if ( v11[3] <= 7u )
            v16 = v11;
          else
            v16 = (_QWORD *)*v11;
          std::wstring::wstring(v31, v15, v13, a2, v14, v16, v11[2]);
          std::operator+<unsigned short>(v32, v31, L";");
          std::wstring::operator+=(Src);
          std::wstring::~wstring(v32);
          std::wstring::~wstring(v31);
          v24 = 0;
          v17 = Src;
          if ( v29 > 7 )
            LODWORD(v17) = Src[0];
          if ( !(unsigned int)sqlite3Prepare16(v25, (_DWORD)v17, -1, 128, (__int64)&v24, 0) )
          {
            sqlite3_step(v24);
            sqlite3_finalize(v24);
          }
          v24 = 0;
          std::wstring::assign(Src, v18);
          v21 = v11[2];
          if ( v21 == 0x7FFFFFFFFFFFFFFELL )
            std::_Xlen_string();
          if ( v11[3] <= 7u )
            v22 = v11;
          else
            v22 = (_QWORD *)*v11;
          std::wstring::wstring(v31, v19, v20, v22, v21, L";", 1);
          std::wstring::operator+=(Src);
          std::wstring::~wstring(v31);
          v23 = Src;
          if ( v29 > 7 )
            LODWORD(v23) = Src[0];
          if ( !(unsigned int)sqlite3Prepare16(v25, (_DWORD)v23, -1, 128, (__int64)&v24, 0) )
          {
            sqlite3_step(v24);
            sqlite3_finalize(v24);
          }
          std::wstring::~wstring(Src);
          v11 += 4;
        }
        while ( v11 != v10 );
        sqlite3Close(v25, 0);
      }
    }
    else
    {
      fprintf(*((FILE *const *)this + 8), "Failed to query provider versions");
    }
  }
  std::vector<std::wstring>::~vector<std::wstring>(&v26);
  std::wstring::~wstring(v30);
}

```

## disassembly

```asm
0x14000f190  mov     [rsp-8+arg_10], rbx
0x14000f195  push    rbp
0x14000f196  push    rsi
0x14000f197  push    rdi
0x14000f198  push    r12
0x14000f19a  push    r15
0x14000f19c  lea     rbp, [rsp-37h]
0x14000f1a1  sub     rsp, 0F0h
0x14000f1a8  mov     rax, cs:__security_cookie
0x14000f1af  xor     rax, rsp
0x14000f1b2  mov     [rbp+57h+var_28], rax
0x14000f1b6  mov     rsi, rdx
0x14000f1b9  mov     rdi, rcx
0x14000f1bc  xor     r12d, r12d
0x14000f1bf  mov     [rbp+57h+var_C8], r12
0x14000f1c3  lea     r9, [rcx+48h]
0x14000f1c7  mov     rcx, [r9+10h]
0x14000f1cb  mov     rax, 7FFFFFFFFFFFFFFEh
0x14000f1d5  sub     rax, rcx
0x14000f1d8  cmp     rax, 1
0x14000f1dc  jb      loc_14000F4CF
0x14000f1e2  cmp     qword ptr [r9+18h], 7
0x14000f1e7  jbe     short loc_14000F1EC
0x14000f1e9  mov     r9, [r9]
0x14000f1ec  mov     [rsp+110h+var_E0], 1
0x14000f1f5  lea     rax, Source; "\\"
0x14000f1fc  mov     [rsp+110h+var_E8], rax
0x14000f201  mov     [rsp+110h+var_F0], rcx
0x14000f206  lea     rcx, [rbp+57h+Src]
0x14000f20a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x14000f20f  nop
0x14000f210  mov     r8, rsi
0x14000f213  lea     rdx, [rbp+57h+Src]
0x14000f217  lea     rcx, [rbp+57h+var_68]
0x14000f21b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x14000f220  nop
0x14000f221  lea     r8, aDb; ".db"
0x14000f228  mov     rdx, rax
0x14000f22b  lea     rcx, [rbp+57h+var_88]
0x14000f22f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x14000f234  nop
0x14000f235  lea     rcx, [rbp+57h+var_68]
0x14000f239  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f23e  nop
0x14000f23f  lea     rcx, [rbp+57h+Src]
0x14000f243  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f248  xorps   xmm0, xmm0
0x14000f24b  movdqu  [rbp+57h+var_C0], xmm0
0x14000f250  mov     [rbp+57h+var_B0], r12
0x14000f254  lea     rcx, [rbp+57h+var_88]
0x14000f258  cmp     [rbp+57h+var_70], 7
0x14000f25d  cmova   rcx, [rbp+57h+var_88]
0x14000f262  lea     rdx, [rbp+57h+var_C8]
0x14000f266  call    sqlite3_open16
0x14000f26b  test    eax, eax
0x14000f26d  jz      short loc_14000F2A5
0x14000f26f  lea     rcx, [rbp+57h+var_C0]
0x14000f273  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x14000f278  nop
0x14000f279  lea     rcx, [rbp+57h+var_88]
0x14000f27d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f282  mov     rcx, [rbp+57h+var_28]
0x14000f286  xor     rcx, rsp; StackCookie
0x14000f289  call    __security_check_cookie
0x14000f28e  mov     rbx, [rsp+110h+arg_10]
0x14000f296  add     rsp, 0F0h
0x14000f29d  pop     r15
0x14000f29f  pop     r12
0x14000f2a1  pop     rdi
0x14000f2a2  pop     rsi
0x14000f2a3  pop     rbp
0x14000f2a4  retn
0x14000f2a5  lea     r9, [rbp+57h+var_C0]
0x14000f2a9  mov     r8, rsi
0x14000f2ac  mov     rdx, [rbp+57h+var_C8]
0x14000f2b0  call    ?GetTableVersions@SqliteCache@CacheUtilities@Inventory@Compat@Windows@@AEAAJPEAXPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Windows::Compat::Inventory::CacheUtilities::SqliteCache::GetTableVersions(void *,ushort const *,std::vector<std::wstring> &)
0x14000f2b5  test    eax, eax
0x14000f2b7  jns     short loc_14000F2CB
0x14000f2b9  lea     rdx, aFailedToQueryP; "Failed to query provider versions"
0x14000f2c0  mov     rcx, [rdi+40h]; Stream
0x14000f2c4  call    fprintf
0x14000f2c9  jmp     short loc_14000F26F
0x14000f2cb  mov     r15, qword ptr [rbp+57h+var_C0+8]
0x14000f2cf  mov     rbx, qword ptr [rbp+57h+var_C0]
0x14000f2d3  cmp     rbx, r15
0x14000f2d6  jnz     short loc_14000F2E1
0x14000f2d8  lea     rdx, aFailedToFindAn; "Failed to find any tables"
0x14000f2df  jmp     short loc_14000F2C0
0x14000f2e1  cmp     qword ptr [rbx+18h], 7
0x14000f2e6  jbe     short loc_14000F2ED
0x14000f2e8  mov     r9, [rbx]
0x14000f2eb  jmp     short loc_14000F2F0
0x14000f2ed  mov     r9, rbx
0x14000f2f0  mov     r8, rsi
0x14000f2f3  lea     rdx, aProviderNameLs_0; "Provider name: %ls%ls\n"
0x14000f2fa  mov     rcx, [rdi+40h]; Stream
0x14000f2fe  call    fwprintf
0x14000f303  lea     rdx, aDeleteFrom; "DELETE FROM "
0x14000f30a  lea     rcx, [rbp+57h+Src]
0x14000f30e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14000f313  nop
0x14000f314  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000f318  inc     rcx
0x14000f31b  cmp     [rsi+rcx*2], r12w
0x14000f320  jnz     short loc_14000F318
0x14000f322  mov     rdx, [rbx+10h]
0x14000f326  mov     rax, 7FFFFFFFFFFFFFFEh
0x14000f330  sub     rax, rdx
0x14000f333  cmp     rax, rcx
0x14000f336  jb      loc_14000F4C9
0x14000f33c  cmp     qword ptr [rbx+18h], 7
0x14000f341  jbe     short loc_14000F348
0x14000f343  mov     rax, [rbx]
0x14000f346  jmp     short loc_14000F34B
0x14000f348  mov     rax, rbx
0x14000f34b  mov     [rsp+110h+var_E0], rdx
0x14000f350  mov     [rsp+110h+var_E8], rax
0x14000f355  mov     [rsp+110h+var_F0], rcx
0x14000f35a  mov     r9, rsi
0x14000f35d  lea     rcx, [rbp+57h+var_68]
0x14000f361  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x14000f366  nop
0x14000f367  lea     r8, asc_1400AEF5C; ";"
0x14000f36e  lea     rdx, [rbp+57h+var_68]
0x14000f372  lea     rcx, [rbp+57h+var_48]
0x14000f376  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x14000f37b  nop
0x14000f37c  mov     rdx, rax
0x14000f37f  lea     rcx, [rbp+57h+Src]; Src
0x14000f383  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x14000f388  nop
0x14000f389  lea     rcx, [rbp+57h+var_48]
0x14000f38d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f392  nop
0x14000f393  lea     rcx, [rbp+57h+var_68]
0x14000f397  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f39c  mov     [rbp+57h+var_D0], r12
0x14000f3a0  lea     rdx, [rbp+57h+Src]
0x14000f3a4  cmp     [rbp+57h+var_90], 7
0x14000f3a9  cmova   rdx, [rbp+57h+Src]
0x14000f3ae  mov     [rsp+110h+var_E8], r12
0x14000f3b3  lea     rax, [rbp+57h+var_D0]
0x14000f3b7  mov     [rsp+110h+var_F0], rax
0x14000f3bc  mov     r9d, 80h
0x14000f3c2  or      r8d, 0FFFFFFFFh
0x14000f3c6  mov     rcx, [rbp+57h+var_C8]
0x14000f3ca  call    sqlite3Prepare16
0x14000f3cf  test    eax, eax
0x14000f3d1  jnz     short loc_14000F3E5
0x14000f3d3  mov     rcx, [rbp+57h+var_D0]
0x14000f3d7  call    sqlite3_step
0x14000f3dc  mov     rcx, [rbp+57h+var_D0]
0x14000f3e0  call    sqlite3_finalize
0x14000f3e5  mov     [rbp+57h+var_D0], r12
0x14000f3e9  lea     rcx, [rbp+57h+Src]
0x14000f3ed  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x14000f3f2  mov     rcx, [rbx+10h]
0x14000f3f6  mov     rax, 7FFFFFFFFFFFFFFEh
0x14000f400  sub     rax, rcx
0x14000f403  cmp     rax, 1
0x14000f407  jb      loc_14000F4C3
0x14000f40d  cmp     qword ptr [rbx+18h], 7
0x14000f412  jbe     short loc_14000F419
0x14000f414  mov     r9, [rbx]
0x14000f417  jmp     short loc_14000F41C
0x14000f419  mov     r9, rbx
0x14000f41c  mov     [rsp+110h+var_E0], 1
0x14000f425  lea     rax, asc_1400AEF5C; ";"
0x14000f42c  mov     [rsp+110h+var_E8], rax
0x14000f431  mov     [rsp+110h+var_F0], rcx
0x14000f436  lea     rcx, [rbp+57h+var_68]
0x14000f43a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x14000f43f  nop
0x14000f440  lea     rdx, [rbp+57h+var_68]
0x14000f444  lea     rcx, [rbp+57h+Src]; Src
0x14000f448  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x14000f44d  nop
0x14000f44e  lea     rcx, [rbp+57h+var_68]
0x14000f452  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f457  lea     rdx, [rbp+57h+Src]
0x14000f45b  cmp     [rbp+57h+var_90], 7
0x14000f460  cmova   rdx, [rbp+57h+Src]
0x14000f465  mov     [rsp+110h+var_E8], r12
0x14000f46a  lea     rax, [rbp+57h+var_D0]
0x14000f46e  mov     [rsp+110h+var_F0], rax
0x14000f473  mov     r9d, 80h
0x14000f479  or      r8d, 0FFFFFFFFh
0x14000f47d  mov     rcx, [rbp+57h+var_C8]
0x14000f481  call    sqlite3Prepare16
0x14000f486  test    eax, eax
0x14000f488  jnz     short loc_14000F49D
0x14000f48a  mov     rcx, [rbp+57h+var_D0]
0x14000f48e  call    sqlite3_step
0x14000f493  mov     rcx, [rbp+57h+var_D0]
0x14000f497  call    sqlite3_finalize
0x14000f49c  nop
0x14000f49d  lea     rcx, [rbp+57h+Src]
0x14000f4a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f4a6  add     rbx, 20h ; ' '
0x14000f4aa  cmp     rbx, r15
0x14000f4ad  jnz     loc_14000F2E1
0x14000f4b3  xor     edx, edx
0x14000f4b5  mov     rcx, [rbp+57h+var_C8]
0x14000f4b9  call    sqlite3Close
0x14000f4be  jmp     loc_14000F26F
0x14000f4c3  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x14000f4c9  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x14000f4cf  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
