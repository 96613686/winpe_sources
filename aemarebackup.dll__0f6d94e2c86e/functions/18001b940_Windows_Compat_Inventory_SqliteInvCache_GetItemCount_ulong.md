# Windows::Compat::Inventory::SqliteInvCache::GetItemCount(ulong &)

- ea: `0x18001b940`
- end: `0x18001bb74`
- name: `?GetItemCount@SqliteInvCache@Inventory@Compat@Windows@@UEBAJAEAK@Z`
- size: `564`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180004ea0`
- `0x18001209c`
- `0x1800134b8`
- `0x18001b940`
- `0x1800276cc`
- `0x180027d3c`
- `0x18004c020`
- `0x1800a494c`
- `0x1800c2a60`
- `0x1800c4b00`
- `0x1800c5440`
- `0x1800c7810`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001bab8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001bab8`

## string_xrefs

- `0x18001ba81`: `Windows::Compat::Inventory::SqliteInvCache::GetItemCount`
- `0x18001bb1b`: `Windows::Compat::Inventory::SqliteInvCache::GetItemCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::GetItemCount(
        Windows::Compat::Inventory::SqliteInvCache *this,
        unsigned int *a2)
{
  _QWORD *v4; // r8
  __int64 v5; // rcx
  __int64 v6; // rax
  __int128 *v7; // rdx
  int v8; // eax
  int v9; // edi
  unsigned int v10; // ebx
  __int64 v11; // rax
  const char *v12; // r9
  __int64 v13; // r8
  int i; // ebx
  __int64 v16; // [rsp+20h] [rbp-29h]
  __int64 v17; // [rsp+40h] [rbp-9h] BYREF
  __int128 v18; // [rsp+48h] [rbp-1h] BYREF
  __int128 v19; // [rsp+58h] [rbp+Fh]
  char *Src[4]; // [rsp+68h] [rbp+1Fh] BYREF

  v4 = (_QWORD *)((char *)this + 72);
  v5 = *((_QWORD *)this + 11);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v5) < 0x15 )
    std::_Xlen_string();
  if ( v4[3] > 7u )
    v4 = (_QWORD *)*v4;
  std::wstring::wstring(Src, a2, v4, L"SELECT COUNT(*) FROM ", 21, v4, v5);
  v6 = std::wstring::append(Src, L";");
  v18 = 0;
  v19 = 0;
  v18 = *(_OWORD *)v6;
  v19 = *(_OWORD *)(v6 + 16);
  *(_QWORD *)(v6 + 16) = 0;
  *(_QWORD *)(v6 + 24) = 7;
  *(_WORD *)v6 = 0;
  std::wstring::~wstring(Src);
  *a2 = 0;
  v17 = 0;
  v7 = &v18;
  if ( *((_QWORD *)&v19 + 1) > 7u )
    LODWORD(v7) = v18;
  v8 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v7, -1, 128, (__int64)&v17, 0);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v10 = (unsigned __int16)v8 | 0x80070000;
    else
      v10 = v8;
    v11 = sqlite3_errmsg(*((_QWORD *)this + 1));
    v12 = "sqlite3_prepare_v2 failed: [%d] %hs";
    v13 = 760;
LABEL_11:
    LODWORD(v16) = v9;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::GetItemCount", v13, v12, v16, v11);
    goto LABEL_23;
  }
  if ( v17 )
  {
    for ( i = 0; i < 100; ++i )
    {
      v9 = sqlite3_step(v17);
      if ( (unsigned int)(v9 - 5) > 1 )
        break;
      Sleep(5u);
    }
    if ( v9 != 100 )
    {
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      else
        v10 = v9;
      v11 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v12 = "sqlite3_step failed: [%d] %hs";
      v13 = 773;
      goto LABEL_11;
    }
    v10 = 0;
    *a2 = sqlite3_column_int(v17, 0);
  }
  else
  {
    v10 = -2147467259;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::GetItemCount",
      766,
      "sqlite3_prepare_v2 returned a null statement [%#x]",
      -2147467259);
  }
LABEL_23:
  if ( v17 )
    sqlite3_finalize(v17);
  std::wstring::~wstring((char **)&v18);
  return v10;
}

```

## disassembly

```asm
0x18001b940  mov     [rsp-8+arg_10], rbx
0x18001b945  mov     [rsp-8+arg_18], rdi
0x18001b94a  push    rbp
0x18001b94b  push    r14
0x18001b94d  push    r15
0x18001b94f  lea     rbp, [rsp-47h]
0x18001b954  sub     rsp, 90h
0x18001b95b  mov     rax, cs:__security_cookie
0x18001b962  xor     rax, rsp
0x18001b965  mov     [rbp+57h+var_18], rax
0x18001b969  mov     r15, rdx
0x18001b96c  mov     r14, rcx
0x18001b96f  lea     r8, [rcx+48h]
0x18001b973  mov     rcx, [r8+10h]
0x18001b977  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001b981  sub     rax, rcx
0x18001b984  cmp     rax, 15h
0x18001b988  jb      loc_18001BB6E
0x18001b98e  cmp     qword ptr [r8+18h], 7
0x18001b993  jbe     short loc_18001B998
0x18001b995  mov     r8, [r8]
0x18001b998  mov     [rsp+0A0h+var_70], rcx
0x18001b99d  mov     [rsp+0A0h+var_78], r8
0x18001b9a2  mov     [rsp+0A0h+var_80], 15h
0x18001b9ab  lea     r9, aSelectCountFro; "SELECT COUNT(*) FROM "
0x18001b9b2  lea     rcx, [rbp+57h+Src]
0x18001b9b6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001b9bb  nop
0x18001b9bc  lea     rdx, asc_1800F5790; ";"
0x18001b9c3  lea     rcx, [rbp+57h+Src]; Src
0x18001b9c7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001b9cc  xorps   xmm0, xmm0
0x18001b9cf  movups  [rbp+57h+var_58], xmm0
0x18001b9d3  xorps   xmm1, xmm1
0x18001b9d6  movdqu  [rbp+57h+var_48], xmm1
0x18001b9db  movups  xmm0, xmmword ptr [rax]
0x18001b9de  movups  [rbp+57h+var_58], xmm0
0x18001b9e2  movups  xmm1, xmmword ptr [rax+10h]
0x18001b9e6  movups  [rbp+57h+var_48], xmm1
0x18001b9ea  mov     qword ptr [rax+10h], 0
0x18001b9f2  mov     qword ptr [rax+18h], 7
0x18001b9fa  xor     ecx, ecx
0x18001b9fc  mov     [rax], cx
0x18001b9ff  lea     rcx, [rbp+57h+Src]
0x18001ba03  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ba08  nop
0x18001ba09  mov     dword ptr [r15], 0
0x18001ba10  mov     [rbp+57h+var_60], 0
0x18001ba18  lea     rdx, [rbp+57h+var_58]
0x18001ba1c  cmp     qword ptr [rbp+57h+var_48+8], 7
0x18001ba21  cmova   rdx, qword ptr [rbp+57h+var_58]
0x18001ba26  mov     [rsp+0A0h+var_78], 0
0x18001ba2f  lea     rax, [rbp+57h+var_60]
0x18001ba33  mov     [rsp+0A0h+var_80], rax
0x18001ba38  mov     r9d, 80h
0x18001ba3e  or      r8d, 0FFFFFFFFh
0x18001ba42  mov     rcx, [r14+8]
0x18001ba46  call    sqlite3Prepare16
0x18001ba4b  mov     edi, eax
0x18001ba4d  test    eax, eax
0x18001ba4f  jz      short loc_18001BA97
0x18001ba51  test    eax, eax
0x18001ba53  jg      short loc_18001BA59
0x18001ba55  mov     ebx, eax
0x18001ba57  jmp     short loc_18001BA62
0x18001ba59  movzx   ebx, di
0x18001ba5c  or      ebx, 80070000h
0x18001ba62  mov     rcx, [r14+8]
0x18001ba66  call    sqlite3_errmsg
0x18001ba6b  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x18001ba72  mov     r8d, 2F8h
0x18001ba78  mov     [rsp+0A0h+var_78], rax
0x18001ba7d  mov     dword ptr [rsp+0A0h+var_80], edi
0x18001ba81  lea     rdx, aWindowsCompatI_8; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001ba88  mov     ecx, 1
0x18001ba8d  call    AslLogCallPrintf
0x18001ba92  jmp     loc_18001BB2D
0x18001ba97  cmp     [rbp+57h+var_60], 0
0x18001ba9c  jz      short loc_18001BB05
0x18001ba9e  xor     ebx, ebx
0x18001baa0  mov     rcx, [rbp+57h+var_60]
0x18001baa4  call    sqlite3_step
0x18001baa9  mov     edi, eax
0x18001baab  lea     ecx, [rax-5]
0x18001baae  cmp     ecx, 1
0x18001bab1  ja      short loc_18001BAC5
0x18001bab3  mov     ecx, 5; dwMilliseconds
0x18001bab8  call    cs:__imp_Sleep
0x18001babe  inc     ebx
0x18001bac0  cmp     ebx, 64h ; 'd'
0x18001bac3  jl      short loc_18001BAA0
0x18001bac5  cmp     edi, 64h ; 'd'
0x18001bac8  jz      short loc_18001BAF3
0x18001baca  test    edi, edi
0x18001bacc  jg      short loc_18001BAD2
0x18001bace  mov     ebx, edi
0x18001bad0  jmp     short loc_18001BADB
0x18001bad2  movzx   ebx, di
0x18001bad5  or      ebx, 80070000h
0x18001badb  mov     rcx, [r14+8]
0x18001badf  call    sqlite3_errmsg
0x18001bae4  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x18001baeb  mov     r8d, 305h
0x18001baf1  jmp     short loc_18001BA78
0x18001baf3  xor     ebx, ebx
0x18001baf5  xor     edx, edx
0x18001baf7  mov     rcx, [rbp+57h+var_60]
0x18001bafb  call    sqlite3_column_int
0x18001bb00  mov     [r15], eax
0x18001bb03  jmp     short loc_18001BB2D
0x18001bb05  mov     ebx, 80004005h
0x18001bb0a  mov     dword ptr [rsp+0A0h+var_80], ebx
0x18001bb0e  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x18001bb15  mov     r8d, 2FEh
0x18001bb1b  lea     rdx, aWindowsCompatI_8; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001bb22  mov     ecx, 1
0x18001bb27  call    AslLogCallPrintf
0x18001bb2c  nop
0x18001bb2d  cmp     [rbp+57h+var_60], 0
0x18001bb32  jz      short loc_18001BB3E
0x18001bb34  mov     rcx, [rbp+57h+var_60]
0x18001bb38  call    sqlite3_finalize
0x18001bb3d  nop
0x18001bb3e  lea     rcx, [rbp+57h+var_58]
0x18001bb42  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bb47  mov     eax, ebx
0x18001bb49  mov     rcx, [rbp+57h+var_18]
0x18001bb4d  xor     rcx, rsp; StackCookie
0x18001bb50  call    __security_check_cookie
0x18001bb55  lea     r11, [rsp+0A0h+var_10]
0x18001bb5d  mov     rbx, [r11+30h]
0x18001bb61  mov     rdi, [r11+38h]
0x18001bb65  mov     rsp, r11
0x18001bb68  pop     r15
0x18001bb6a  pop     r14
0x18001bb6c  pop     rbp
0x18001bb6d  retn
0x18001bb6e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
