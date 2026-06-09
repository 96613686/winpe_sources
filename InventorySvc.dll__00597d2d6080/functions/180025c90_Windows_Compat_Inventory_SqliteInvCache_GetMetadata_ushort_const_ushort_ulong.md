# Windows::Compat::Inventory::SqliteInvCache::GetMetadata(ushort const *,ushort *,ulong &)

- ea: `0x180025c90`
- end: `0x180025f6d`
- name: `?GetMetadata@SqliteInvCache@Inventory@Compat@Windows@@UEBAJPEBGPEAGAEAK@Z`
- size: `733`
- prototype: `int(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180002bf0`
- `0x1800074f0`
- `0x18000f748`
- `0x1800109dc`
- `0x1800152d0`
- `0x18001f4a4`
- `0x18001fd88`
- `0x180025c90`
- `0x180036be4`
- `0x1800817cc`
- `0x18009f9e0`
- `0x1800a1980`
- `0x1800a22c0`
- `0x1800a4690`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180025e3d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180025e3d`

## string_xrefs

- `0x180025daf`: `Windows::Compat::Inventory::SqliteInvCache::GetMetadata`
- `0x180025f1c`: `Windows::Compat::Inventory::SqliteInvCache::GetMetadata`
- `0x180025edf`: `StringCchCopyW failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::GetMetadata(
        Windows::Compat::Inventory::SqliteInvCache *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  int v6; // ebx
  _QWORD *v8; // rdx
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  __int64 v11; // rbp
  int v12; // edi
  __int64 v13; // r14
  unsigned int v14; // ebx
  int v15; // esi
  __int64 v16; // rax
  const char *v17; // r9
  __int64 v18; // r8
  int i; // ebx
  const unsigned __int16 *v20; // rax
  int v21; // eax
  __int64 v22; // r11
  __int64 v24; // [rsp+20h] [rbp-B8h]
  __int64 v25; // [rsp+20h] [rbp-B8h]
  __int64 v26; // [rsp+28h] [rbp-B0h]
  __int64 v27; // [rsp+28h] [rbp-B0h]
  __int64 v28; // [rsp+40h] [rbp-98h] BYREF
  _QWORD v29[4]; // [rsp+48h] [rbp-90h] BYREF
  _BYTE v30[32]; // [rsp+68h] [rbp-70h] BYREF

  v6 = (int)a2;
  v8 = (_QWORD *)((char *)this + 104);
  v9 = *((_QWORD *)this + 15);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v9) < 0x12 )
    std::_Xlen_string();
  if ( v8[3] > 7u )
    v8 = (_QWORD *)*v8;
  std::wstring::wstring(v30, v8, a3, L"SELECT Value FROM ", 18, v8, v9);
  std::operator+<unsigned short>(v29, v30, L" WHERE Name = ?;");
  std::wstring::~wstring(v30);
  v28 = 0;
  v10 = v29;
  if ( v29[3] > 7u )
    LODWORD(v10) = v29[0];
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
    LODWORD(v24) = v12;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::GetMetadata",
      1090,
      "sqlite3_prepare_v2 failed: [%d] %hs",
      v24,
      v27);
    goto LABEL_37;
  }
  if ( v28 )
  {
    LOBYTE(v26) = 2;
    v15 = bindText(v28, 1, v6, -2, 0, v26);
    if ( v15 )
    {
      if ( v15 > 0 )
        v14 = (unsigned __int16)v15 | 0x80070000;
      else
        v14 = v15;
      v16 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v17 = "sqlite3_bind_text16 failed: [%d] %hs";
      v18 = 1104;
LABEL_17:
      LODWORD(v25) = v15;
      AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::GetMetadata", v18, v17, v25, v16);
      goto LABEL_37;
    }
    for ( i = 0; i < 100; ++i )
    {
      v15 = sqlite3_step(v13);
      if ( (unsigned int)(v15 - 5) > 1 )
        break;
      Sleep(5u);
    }
    if ( v15 != 101 )
    {
      if ( v15 == 100 )
      {
        v20 = (const unsigned __int16 *)sqlite3_column_text16(v13, 0);
        v21 = StringCchCopyW(a3, *a4, v20);
        v14 = v21;
        if ( v21 == -2147024774 )
        {
          do
            ++v11;
          while ( *(_WORD *)(v22 + 2 * v11) );
          *a4 = v11 + 1;
          LODWORD(v25) = -2147024774;
          AslLogCallPrintf(
            1,
            "Windows::Compat::Inventory::SqliteInvCache::GetMetadata",
            1124,
            "StringValue buffer is too small [%#x]",
            v25);
        }
        else if ( v21 >= 0 )
        {
          do
            ++v11;
          while ( *(_WORD *)(v22 + 2 * v11) );
          *a4 = v11 + 1;
        }
        else
        {
          LODWORD(v25) = v21;
          AslLogCallPrintf(
            1,
            "Windows::Compat::Inventory::SqliteInvCache::GetMetadata",
            1129,
            "StringCchCopyW failed [%#x]",
            v25);
        }
        goto LABEL_37;
      }
      if ( v15 > 0 )
        v14 = (unsigned __int16)v15 | 0x80070000;
      else
        v14 = v15;
      v16 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v17 = "sqlite3_step failed: [%d] %hs";
      v18 = 1116;
      goto LABEL_17;
    }
    v14 = -2147024894;
  }
  else
  {
    v14 = -2147467259;
    LODWORD(v24) = -2147467259;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::GetMetadata",
      1096,
      "sqlite3_prepare_v2 returned a null statement [%#x]",
      v24);
  }
LABEL_37:
  if ( v13 )
    sqlite3_finalize(v13);
  std::wstring::~wstring(v29);
  return v14;
}

```

## disassembly

```asm
0x180025c90  push    rbx
0x180025c92  push    rbp
0x180025c93  push    rsi
0x180025c94  push    rdi
0x180025c95  push    r12
0x180025c97  push    r13
0x180025c99  push    r14
0x180025c9b  push    r15
0x180025c9d  sub     rsp, 98h
0x180025ca4  mov     rax, cs:__security_cookie
0x180025cab  xor     rax, rsp
0x180025cae  mov     [rsp+0D8h+var_50], rax
0x180025cb6  mov     r12, r9
0x180025cb9  mov     r13, r8
0x180025cbc  mov     rbx, rdx
0x180025cbf  mov     r15, rcx
0x180025cc2  xor     edi, edi
0x180025cc4  lea     rdx, [rcx+68h]
0x180025cc8  mov     rcx, [rdx+10h]
0x180025ccc  mov     rax, 7FFFFFFFFFFFFFFEh
0x180025cd6  sub     rax, rcx
0x180025cd9  cmp     rax, 12h
0x180025cdd  jb      loc_180025F67
0x180025ce3  cmp     qword ptr [rdx+18h], 7
0x180025ce8  jbe     short loc_180025CED
0x180025cea  mov     rdx, [rdx]
0x180025ced  mov     [rsp+0D8h+var_A8], rcx
0x180025cf2  mov     [rsp+0D8h+var_B0], rdx
0x180025cf7  mov     [rsp+0D8h+var_B8], 12h
0x180025d00  lea     r9, aSelectValueFro; "SELECT Value FROM "
0x180025d07  lea     rcx, [rsp+0D8h+var_70]
0x180025d0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180025d11  nop
0x180025d12  lea     r8, aWhereName; " WHERE Name = ?;"
0x180025d19  lea     rdx, [rsp+0D8h+var_70]
0x180025d1e  lea     rcx, [rsp+0D8h+var_90]
0x180025d23  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180025d28  nop
0x180025d29  lea     rcx, [rsp+0D8h+var_70]; void *
0x180025d2e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025d33  nop
0x180025d34  mov     [rsp+0D8h+var_98], rdi
0x180025d39  lea     rdx, [rsp+0D8h+var_90]
0x180025d3e  cmp     [rsp+0D8h+var_78], 7
0x180025d44  cmova   rdx, [rsp+0D8h+var_90]
0x180025d4a  mov     [rsp+0D8h+var_B0], rdi
0x180025d4f  lea     rax, [rsp+0D8h+var_98]
0x180025d54  mov     [rsp+0D8h+var_B8], rax
0x180025d59  mov     r9d, 80h
0x180025d5f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180025d63  mov     r8d, ebp
0x180025d66  mov     rcx, [r15+8]
0x180025d6a  call    sqlite3Prepare16
0x180025d6f  mov     edi, eax
0x180025d71  mov     r14, [rsp+0D8h+var_98]
0x180025d76  xor     eax, eax
0x180025d78  test    edi, edi
0x180025d7a  jz      short loc_180025DC0
0x180025d7c  jg      short loc_180025D82
0x180025d7e  mov     ebx, edi
0x180025d80  jmp     short loc_180025D8B
0x180025d82  movzx   ebx, di
0x180025d85  or      ebx, 80070000h
0x180025d8b  mov     rcx, [r15+8]
0x180025d8f  call    sqlite3_errmsg
0x180025d94  mov     [rsp+0D8h+var_B0], rax
0x180025d99  mov     dword ptr [rsp+0D8h+var_B8], edi
0x180025d9d  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x180025da4  mov     r8d, 442h
0x180025daa  mov     ecx, 1
0x180025daf  lea     rdx, aWindowsCompatI_82; "Windows::Compat::Inventory::SqliteInvCa"...
0x180025db6  call    AslLogCallPrintf
0x180025dbb  jmp     loc_180025F29
0x180025dc0  test    r14, r14
0x180025dc3  jz      loc_180025F01
0x180025dc9  mov     byte ptr [rsp+0D8h+var_B0], 2
0x180025dce  mov     [rsp+0D8h+var_B8], rax
0x180025dd3  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180025dda  mov     r8, rbx
0x180025ddd  lea     edi, [r9+3]
0x180025de1  mov     edx, edi
0x180025de3  mov     rcx, r14
0x180025de6  call    bindText
0x180025deb  mov     esi, eax
0x180025ded  xor     eax, eax
0x180025def  test    esi, esi
0x180025df1  jz      short loc_180025E25
0x180025df3  jg      short loc_180025DF9
0x180025df5  mov     ebx, esi
0x180025df7  jmp     short loc_180025E02
0x180025df9  movzx   ebx, si
0x180025dfc  or      ebx, 80070000h
0x180025e02  mov     rcx, [r15+8]
0x180025e06  call    sqlite3_errmsg
0x180025e0b  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180025e12  mov     r8d, 450h
0x180025e18  mov     [rsp+0D8h+var_B0], rax
0x180025e1d  mov     dword ptr [rsp+0D8h+var_B8], esi
0x180025e21  mov     ecx, edi
0x180025e23  jmp     short loc_180025DAF
0x180025e25  mov     ebx, eax
0x180025e27  mov     rcx, r14
0x180025e2a  call    sqlite3_step
0x180025e2f  mov     esi, eax
0x180025e31  lea     ecx, [rax-5]
0x180025e34  cmp     ecx, edi
0x180025e36  ja      short loc_180025E4A
0x180025e38  mov     ecx, 5; dwMilliseconds
0x180025e3d  call    cs:__imp_Sleep
0x180025e43  add     ebx, edi
0x180025e45  cmp     ebx, 64h ; 'd'
0x180025e48  jl      short loc_180025E27
0x180025e4a  cmp     esi, 65h ; 'e'
0x180025e4d  jnz     short loc_180025E59
0x180025e4f  mov     ebx, 80070002h
0x180025e54  jmp     loc_180025F29
0x180025e59  cmp     esi, 64h ; 'd'
0x180025e5c  jz      short loc_180025E87
0x180025e5e  test    esi, esi
0x180025e60  jg      short loc_180025E66
0x180025e62  mov     ebx, esi
0x180025e64  jmp     short loc_180025E6F
0x180025e66  movzx   ebx, si
0x180025e69  or      ebx, 80070000h
0x180025e6f  mov     rcx, [r15+8]
0x180025e73  call    sqlite3_errmsg
0x180025e78  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x180025e7f  mov     r8d, 45Ch
0x180025e85  jmp     short loc_180025E18
0x180025e87  xor     edx, edx
0x180025e89  mov     rcx, r14
0x180025e8c  call    sqlite3_column_text16
0x180025e91  mov     r11, rax
0x180025e94  mov     edx, [r12]; unsigned __int64
0x180025e98  mov     r8, rax; unsigned __int16 *
0x180025e9b  mov     rcx, r13; unsigned __int16 *
0x180025e9e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025ea3  mov     ebx, eax
0x180025ea5  mov     ecx, 8007007Ah
0x180025eaa  xor     r13d, r13d
0x180025ead  cmp     eax, ecx
0x180025eaf  jnz     short loc_180025ED7
0x180025eb1  inc     rbp
0x180025eb4  cmp     [r11+rbp*2], r13w
0x180025eb9  jnz     short loc_180025EB1
0x180025ebb  lea     eax, [rbp+1]
0x180025ebe  mov     [r12], eax
0x180025ec2  mov     dword ptr [rsp+0D8h+var_B8], ecx
0x180025ec6  lea     r9, aStringvalueBuf; "StringValue buffer is too small [%#x]"
0x180025ecd  mov     r8d, 464h
0x180025ed3  mov     ecx, edi
0x180025ed5  jmp     short loc_180025F1C
0x180025ed7  test    eax, eax
0x180025ed9  jns     short loc_180025EEE
0x180025edb  mov     dword ptr [rsp+0D8h+var_B8], eax
0x180025edf  lea     r9, aStringcchcopyw; "StringCchCopyW failed [%#x]"
0x180025ee6  mov     r8d, 469h
0x180025eec  jmp     short loc_180025ED3
0x180025eee  inc     rbp
0x180025ef1  cmp     [r11+rbp*2], r13w
0x180025ef6  jnz     short loc_180025EEE
0x180025ef8  lea     eax, [rbp+1]
0x180025efb  mov     [r12], eax
0x180025eff  jmp     short loc_180025F29
0x180025f01  mov     ebx, 80004005h
0x180025f06  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x180025f0a  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x180025f11  mov     r8d, 448h
0x180025f17  mov     ecx, 1
0x180025f1c  lea     rdx, aWindowsCompatI_82; "Windows::Compat::Inventory::SqliteInvCa"...
0x180025f23  call    AslLogCallPrintf
0x180025f28  nop
0x180025f29  test    r14, r14
0x180025f2c  jz      short loc_180025F37
0x180025f2e  mov     rcx, r14
0x180025f31  call    sqlite3_finalize
0x180025f36  nop
0x180025f37  lea     rcx, [rsp+0D8h+var_90]; void *
0x180025f3c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025f41  mov     eax, ebx
0x180025f43  mov     rcx, [rsp+0D8h+var_50]
0x180025f4b  xor     rcx, rsp; StackCookie
0x180025f4e  call    __security_check_cookie
0x180025f53  add     rsp, 98h
0x180025f5a  pop     r15
0x180025f5c  pop     r14
0x180025f5e  pop     r13
0x180025f60  pop     r12
0x180025f62  pop     rdi
0x180025f63  pop     rsi
0x180025f64  pop     rbp
0x180025f65  pop     rbx
0x180025f66  retn
0x180025f67  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
