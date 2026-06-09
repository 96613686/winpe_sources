# Windows::Compat::Inventory::SqliteInvCache::SetMetadata(ushort const *,unsigned __int64)

- ea: `0x180023ec0`
- end: `0x1800241f3`
- name: `?SetMetadata@SqliteInvCache@Inventory@Compat@Windows@@UEAAJPEBG_K@Z`
- size: `819`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180004ea0`
- `0x18000ef60`
- `0x18001209c`
- `0x1800134b8`
- `0x180023ec0`
- `0x1800276cc`
- `0x180027d3c`
- `0x18004c020`
- `0x180059d64`
- `0x1800a494c`
- `0x1800c4b00`
- `0x1800c5440`
- `0x1800c7810`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180024144`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180024144`

## string_xrefs

- `0x180023f36`: `REPLACE INTO `
- `0x180024009`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`
- `0x18002419a`: `Windows::Compat::Inventory::SqliteInvCache::SetMetadata`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::SetMetadata(
        Windows::Compat::Inventory::SqliteInvCache *this,
        const unsigned __int16 *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // rbx
  int v4; // esi
  _QWORD *v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int128 *v9; // rdx
  int v10; // eax
  int v11; // edi
  __int64 v12; // r14
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // esi
  __int64 v16; // rax
  __int64 v17; // r8
  const char *v18; // r9
  _WORD *v19; // r10
  char **v20; // r8
  int i; // r12d
  __int64 v23; // [rsp+20h] [rbp-69h]
  __int64 v24; // [rsp+20h] [rbp-69h]
  __int64 v25; // [rsp+28h] [rbp-61h]
  __int64 v26; // [rsp+28h] [rbp-61h]
  __int64 v27; // [rsp+28h] [rbp-61h]
  __int64 v28; // [rsp+40h] [rbp-49h] BYREF
  __int128 v29; // [rsp+48h] [rbp-41h] BYREF
  __int128 v30; // [rsp+58h] [rbp-31h]
  char *Src[9]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v32[6]; // [rsp+B2h] [rbp+29h] BYREF

  v3 = a3;
  v4 = (int)a2;
  v6 = (_QWORD *)((char *)this + 104);
  v7 = *((_QWORD *)this + 15);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v7) < 0xD )
    std::_Xlen_string();
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  std::wstring::wstring(Src, v6, a3, L"REPLACE INTO ", 13, v6, v7);
  v8 = std::wstring::append(Src, L" (Name, Value) VALUES (?, ?);");
  v29 = 0;
  v30 = 0;
  v29 = *(_OWORD *)v8;
  v30 = *(_OWORD *)(v8 + 16);
  *(_QWORD *)(v8 + 16) = 0;
  *(_QWORD *)(v8 + 24) = 7;
  *(_WORD *)v8 = 0;
  std::wstring::~wstring(Src);
  v28 = 0;
  v9 = &v29;
  if ( *((_QWORD *)&v30 + 1) > 7u )
    LODWORD(v9) = v29;
  v10 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v9, -1, 128, (__int64)&v28, 0);
  v11 = v10;
  v12 = v28;
  if ( v10 )
  {
    if ( v10 > 0 )
      v13 = (unsigned __int16)v10 | 0x80070000;
    else
      v13 = v10;
    v26 = sqlite3_errmsg(*((_QWORD *)this + 1));
    LODWORD(v23) = v11;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
      1194,
      "sqlite3_prepare_v2 failed: [%d] %hs",
      v23,
      v26);
    goto LABEL_38;
  }
  if ( v28 )
  {
    LOBYTE(v25) = 2;
    v14 = bindText(v28, 1, v4, -2, 0, v25);
    v15 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v13 = (unsigned __int16)v14 | 0x80070000;
      else
        v13 = v14;
      v16 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v17 = 1208;
    }
    else
    {
      v19 = v32;
      do
      {
        *--v19 = v3 % 0xA + 48;
        v3 /= 0xAu;
      }
      while ( v3 );
      std::wstring::wstring(Src, v19, v32);
      v20 = Src;
      if ( Src[3] > (char *)7 )
        LODWORD(v20) = Src[0];
      LOBYTE(v27) = 2;
      v15 = bindText(v12, 2, (_DWORD)v20, -2, -1, v27);
      std::wstring::~wstring(Src);
      if ( !v15 )
      {
        v13 = 0;
        for ( i = 0; i < 100; ++i )
        {
          v15 = sqlite3_step(v12);
          if ( (unsigned int)(v15 - 5) > 1 )
            break;
          Sleep(5u);
        }
        if ( v15 == 101 )
          goto LABEL_38;
        if ( v15 > 0 )
          v13 = (unsigned __int16)v15 | 0x80070000;
        else
          v13 = v15;
        v16 = sqlite3_errmsg(*((_QWORD *)this + 1));
        v18 = "sqlite3_step failed: [%d] %hs";
        v17 = 1223;
        goto LABEL_19;
      }
      if ( v15 > 0 )
        v13 = (unsigned __int16)v15 | 0x80070000;
      else
        v13 = v15;
      v16 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v17 = 1216;
    }
    v18 = "sqlite3_bind_text16 failed: [%d] %hs";
LABEL_19:
    LODWORD(v24) = v15;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::SetMetadata", v17, v18, v24, v16);
    goto LABEL_38;
  }
  v13 = -2147467259;
  AslLogCallPrintf(
    1,
    "Windows::Compat::Inventory::SqliteInvCache::SetMetadata",
    1200,
    "sqlite3_prepare_v2 returned a null statement [%#x]",
    -2147467259);
LABEL_38:
  if ( v12 )
    sqlite3_finalize(v12);
  std::wstring::~wstring((char **)&v29);
  return v13;
}

```

## disassembly

```asm
0x180023ec0  mov     [rsp-8+arg_10], rbx
0x180023ec5  mov     [rsp-8+arg_18], rsi
0x180023eca  push    rbp
0x180023ecb  push    rdi
0x180023ecc  push    r12
0x180023ece  push    r14
0x180023ed0  push    r15
0x180023ed2  lea     rbp, [rsp-37h]
0x180023ed7  sub     rsp, 0C0h
0x180023ede  mov     rax, cs:__security_cookie
0x180023ee5  xor     rax, rsp
0x180023ee8  mov     [rbp+57h+var_28], rax
0x180023eec  mov     rbx, r8
0x180023eef  mov     rsi, rdx
0x180023ef2  mov     r15, rcx
0x180023ef5  lea     rdx, [rcx+68h]
0x180023ef9  mov     rcx, [rdx+10h]
0x180023efd  mov     rax, 7FFFFFFFFFFFFFFEh
0x180023f07  sub     rax, rcx
0x180023f0a  cmp     rax, 0Dh
0x180023f0e  jb      loc_1800241ED
0x180023f14  mov     r12d, 7
0x180023f1a  cmp     [rdx+18h], r12
0x180023f1e  jbe     short loc_180023F23
0x180023f20  mov     rdx, [rdx]
0x180023f23  mov     [rsp+0E0h+var_B0], rcx
0x180023f28  mov     [rsp+0E0h+var_B8], rdx
0x180023f2d  mov     [rsp+0E0h+var_C0], 0Dh
0x180023f36  lea     r9, aReplaceInto; "REPLACE INTO "
0x180023f3d  lea     rcx, [rbp+57h+Src]
0x180023f41  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180023f46  nop
0x180023f47  lea     rdx, aNameValueValue; " (Name, Value) VALUES (?, ?);"
0x180023f4e  lea     rcx, [rbp+57h+Src]; Src
0x180023f52  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180023f57  xorps   xmm0, xmm0
0x180023f5a  movups  [rbp+57h+var_98], xmm0
0x180023f5e  xorps   xmm1, xmm1
0x180023f61  movdqu  [rbp+57h+var_88], xmm1
0x180023f66  movups  xmm0, xmmword ptr [rax]
0x180023f69  movups  [rbp+57h+var_98], xmm0
0x180023f6d  movups  xmm1, xmmword ptr [rax+10h]
0x180023f71  movups  [rbp+57h+var_88], xmm1
0x180023f75  mov     qword ptr [rax+10h], 0
0x180023f7d  mov     [rax+18h], r12
0x180023f81  xor     ecx, ecx
0x180023f83  mov     [rax], cx
0x180023f86  lea     rcx, [rbp+57h+Src]
0x180023f8a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023f8f  nop
0x180023f90  mov     [rbp+57h+var_A0], 0
0x180023f98  lea     rdx, [rbp+57h+var_98]
0x180023f9c  cmp     qword ptr [rbp+57h+var_88+8], r12
0x180023fa0  cmova   rdx, qword ptr [rbp+57h+var_98]
0x180023fa5  mov     [rsp+0E0h+var_B8], 0
0x180023fae  lea     rax, [rbp+57h+var_A0]
0x180023fb2  mov     [rsp+0E0h+var_C0], rax
0x180023fb7  mov     r9d, 80h
0x180023fbd  or      r8d, 0FFFFFFFFh
0x180023fc1  mov     rcx, [r15+8]
0x180023fc5  call    sqlite3Prepare16
0x180023fca  mov     edi, eax
0x180023fcc  mov     r14, [rbp+57h+var_A0]
0x180023fd0  test    eax, eax
0x180023fd2  jz      short loc_18002401A
0x180023fd4  test    eax, eax
0x180023fd6  jg      short loc_180023FDC
0x180023fd8  mov     ebx, eax
0x180023fda  jmp     short loc_180023FE5
0x180023fdc  movzx   ebx, di
0x180023fdf  or      ebx, 80070000h
0x180023fe5  mov     rcx, [r15+8]
0x180023fe9  call    sqlite3_errmsg
0x180023fee  mov     [rsp+0E0h+var_B8], rax
0x180023ff3  mov     dword ptr [rsp+0E0h+var_C0], edi
0x180023ff7  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x180023ffe  mov     r8d, 4AAh
0x180024004  mov     ecx, 1
0x180024009  lea     rdx, aWindowsCompatI_23; "Windows::Compat::Inventory::SqliteInvCa"...
0x180024010  call    AslLogCallPrintf
0x180024015  jmp     loc_1800241AC
0x18002401a  test    r14, r14
0x18002401d  jz      loc_180024184
0x180024023  mov     byte ptr [rsp+0E0h+var_B8], 2
0x180024028  mov     [rsp+0E0h+var_C0], 0
0x180024031  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180024038  mov     r8, rsi
0x18002403b  lea     edi, [r9+3]
0x18002403f  mov     edx, edi
0x180024041  mov     rcx, r14
0x180024044  call    bindText
0x180024049  mov     esi, eax
0x18002404b  test    eax, eax
0x18002404d  jz      short loc_180024083
0x18002404f  test    eax, eax
0x180024051  jg      short loc_180024057
0x180024053  mov     ebx, eax
0x180024055  jmp     short loc_180024060
0x180024057  movzx   ebx, si
0x18002405a  or      ebx, 80070000h
0x180024060  mov     rcx, [r15+8]
0x180024064  call    sqlite3_errmsg
0x180024069  mov     r8d, 4B8h
0x18002406f  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180024076  mov     [rsp+0E0h+var_B8], rax
0x18002407b  mov     dword ptr [rsp+0E0h+var_C0], esi
0x18002407f  mov     ecx, edi
0x180024081  jmp     short loc_180024009
0x180024083  lea     r10, [rbp+57h+var_2E]
0x180024087  sub     r10, 2
0x18002408b  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180024095  mul     rbx
0x180024098  shr     rdx, 3
0x18002409c  movzx   eax, dx
0x18002409f  shl     ax, 2
0x1800240a3  lea     ecx, [rax+rdx]
0x1800240a6  add     cx, cx
0x1800240a9  sub     bx, cx
0x1800240ac  add     bx, 30h ; '0'
0x1800240b0  mov     [r10], bx
0x1800240b4  mov     rbx, rdx
0x1800240b7  test    rdx, rdx
0x1800240ba  jnz     short loc_180024087
0x1800240bc  lea     r8, [rbp+57h+var_2E]
0x1800240c0  mov     rdx, r10
0x1800240c3  lea     rcx, [rbp+57h+Src]
0x1800240c7  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x1800240cc  nop
0x1800240cd  lea     r8, [rbp+57h+Src]
0x1800240d1  cmp     [rbp+57h+var_60], r12
0x1800240d5  cmova   r8, [rbp+57h+Src]
0x1800240da  mov     byte ptr [rsp+0E0h+var_B8], 2
0x1800240df  mov     [rsp+0E0h+var_C0], 0FFFFFFFFFFFFFFFFh
0x1800240e8  lea     edx, [rbx+2]
0x1800240eb  lea     r9, [rbx-2]
0x1800240ef  mov     rcx, r14
0x1800240f2  call    bindText
0x1800240f7  mov     esi, eax
0x1800240f9  lea     rcx, [rbp+57h+Src]
0x1800240fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024102  test    esi, esi
0x180024104  jz      short loc_180024129
0x180024106  jg      short loc_18002410C
0x180024108  mov     ebx, esi
0x18002410a  jmp     short loc_180024115
0x18002410c  movzx   ebx, si
0x18002410f  or      ebx, 80070000h
0x180024115  mov     rcx, [r15+8]
0x180024119  call    sqlite3_errmsg
0x18002411e  mov     r8d, 4C0h
0x180024124  jmp     loc_18002406F
0x180024129  xor     ebx, ebx
0x18002412b  xor     r12d, r12d
0x18002412e  mov     rcx, r14
0x180024131  call    sqlite3_step
0x180024136  mov     esi, eax
0x180024138  lea     ecx, [rax-5]
0x18002413b  cmp     ecx, edi
0x18002413d  ja      short loc_180024153
0x18002413f  mov     ecx, 5; dwMilliseconds
0x180024144  call    cs:__imp_Sleep
0x18002414a  add     r12d, edi
0x18002414d  cmp     r12d, 64h ; 'd'
0x180024151  jl      short loc_18002412E
0x180024153  cmp     esi, 65h ; 'e'
0x180024156  jz      short loc_1800241AC
0x180024158  test    esi, esi
0x18002415a  jg      short loc_180024160
0x18002415c  mov     ebx, esi
0x18002415e  jmp     short loc_180024169
0x180024160  movzx   ebx, si
0x180024163  or      ebx, 80070000h
0x180024169  mov     rcx, [r15+8]
0x18002416d  call    sqlite3_errmsg
0x180024172  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x180024179  mov     r8d, 4C7h
0x18002417f  jmp     loc_180024076
0x180024184  mov     ebx, 80004005h
0x180024189  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18002418d  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x180024194  mov     r8d, 4B0h
0x18002419a  lea     rdx, aWindowsCompatI_23; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800241a1  mov     ecx, 1
0x1800241a6  call    AslLogCallPrintf
0x1800241ab  nop
0x1800241ac  test    r14, r14
0x1800241af  jz      short loc_1800241BA
0x1800241b1  mov     rcx, r14
0x1800241b4  call    sqlite3_finalize
0x1800241b9  nop
0x1800241ba  lea     rcx, [rbp+57h+var_98]
0x1800241be  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800241c3  mov     eax, ebx
0x1800241c5  mov     rcx, [rbp+57h+var_28]
0x1800241c9  xor     rcx, rsp; StackCookie
0x1800241cc  call    __security_check_cookie
0x1800241d1  lea     r11, [rsp+0E0h+var_20]
0x1800241d9  mov     rbx, [r11+40h]
0x1800241dd  mov     rsi, [r11+48h]
0x1800241e1  mov     rsp, r11
0x1800241e4  pop     r15
0x1800241e6  pop     r14
0x1800241e8  pop     r12
0x1800241ea  pop     rdi
0x1800241eb  pop     rbp
0x1800241ec  retn
0x1800241ed  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
