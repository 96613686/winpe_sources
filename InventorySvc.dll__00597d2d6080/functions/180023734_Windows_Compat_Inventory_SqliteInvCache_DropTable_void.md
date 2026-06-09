# Windows::Compat::Inventory::SqliteInvCache::DropTable(void)

- ea: `0x180023734`
- end: `0x180023a6d`
- name: `?DropTable@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ`
- size: `825`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180021940`

## callees

- `0x180002bf0`
- `0x1800074f0`
- `0x1800109dc`
- `0x1800152d0`
- `0x18001f4a4`
- `0x18001fd88`
- `0x180020ea4`
- `0x180023734`
- `0x18002e0b4`
- `0x1800817cc`
- `0x1800a1980`
- `0x1800a22c0`
- `0x1800a4690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023958`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023945`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023945`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180023873`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800239d6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180023873`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800239d6`

## string_xrefs

- `0x18002383c`: `Windows::Compat::Inventory::SqliteInvCache::DropTable`
- `0x1800238a6`: `Windows::Compat::Inventory::SqliteInvCache::DropTable`
- `0x180023a09`: `Windows::Compat::Inventory::SqliteInvCache::DropTable`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::DropTable(
        Windows::Compat::Inventory::SqliteInvCache *this,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v4; // rdx
  __int64 v5; // rcx
  _QWORD *v6; // rdx
  signed int v7; // edi
  const char *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  int i; // r12d
  int v12; // ebx
  const char *v13; // rax
  _QWORD *v14; // rax
  __int64 v15; // rax
  DWORD LastError; // ebx
  _QWORD *v17; // rdx
  int v18; // ebx
  __int64 v19; // r12
  __int64 v20; // rax
  const char *v21; // r9
  __int64 v22; // r8
  int j; // r15d
  __int64 v25; // [rsp+20h] [rbp-69h]
  __int64 v26; // [rsp+40h] [rbp-49h] BYREF
  _DWORD v27[6]; // [rsp+48h] [rbp-41h] BYREF
  unsigned __int64 v28; // [rsp+60h] [rbp-29h]
  _BYTE v29[32]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v30[32]; // [rsp+88h] [rbp-1h] BYREF

  v4 = (_QWORD *)((char *)this + 72);
  v5 = *((_QWORD *)this + 11);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v5) < 0x15 )
    std::_Xlen_string();
  if ( v4[3] > 7u )
    v4 = (_QWORD *)*v4;
  std::wstring::wstring(v29, v4, a3, L"DROP TABLE IF EXISTS ", 21, v4, v5);
  std::operator+<unsigned short>(v27, v29, L";");
  std::wstring::~wstring(v29);
  std::list<std::wstring>::clear((char *)this + 24);
  std::list<std::wstring>::clear((char *)this + 48);
  v26 = 0;
  v6 = v27;
  if ( v28 > 7 )
    LODWORD(v6) = v27[0];
  v7 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v6, -1, 128, (__int64)&v26, 0);
  if ( v7 )
  {
    v8 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::DropTable",
      1544,
      "sqlite3_exec failed: [%d] %hs",
      v7,
      v8);
    if ( v7 <= 0 )
      goto LABEL_17;
    v7 = (unsigned __int16)v7;
LABEL_16:
    v7 |= 0x80070000;
    goto LABEL_17;
  }
  v7 = 0;
  for ( i = 0; i < 100; ++i )
  {
    v12 = sqlite3_step(v26);
    if ( (unsigned int)(v12 - 5) > 1 )
      break;
    Sleep(5u);
  }
  if ( v12 != 101 )
  {
    v13 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::DropTable",
      1552,
      "sqlite3_step failed: [%d] %hs",
      v12,
      v13);
    if ( v12 <= 0 )
    {
      v7 = v12;
      goto LABEL_17;
    }
    v7 = (unsigned __int16)v12;
    goto LABEL_16;
  }
LABEL_17:
  v14 = (_QWORD *)((char *)this + 104);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - *((_QWORD *)this + 15)) < 0x15 )
    std::_Xlen_string();
  if ( *((_QWORD *)this + 16) > 7u )
    v14 = (_QWORD *)*v14;
  std::wstring::wstring(v29, v9, v10, L"DROP TABLE IF EXISTS ", 21, v14, *((_QWORD *)this + 15));
  v15 = std::operator+<unsigned short>(v30, v29, L";");
  std::wstring::operator=(v27, v15);
  std::wstring::~wstring(v30);
  std::wstring::~wstring(v29);
  if ( v26 )
  {
    LastError = GetLastError();
    sqlite3_finalize(v26);
    SetLastError(LastError);
  }
  v26 = 0;
  v17 = v27;
  if ( v28 > 7 )
    LODWORD(v17) = v27[0];
  v18 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v17, -1, 128, (__int64)&v26, 0);
  v19 = v26;
  if ( v18 )
  {
    v20 = sqlite3_errmsg(*((_QWORD *)this + 1));
    v21 = "sqlite3_exec failed: [%d] %hs";
    v22 = 1562;
  }
  else
  {
    for ( j = 0; j < 100; ++j )
    {
      v18 = sqlite3_step(v19);
      if ( (unsigned int)(v18 - 5) > 1 )
        break;
      Sleep(5u);
    }
    if ( v18 == 101 )
      goto LABEL_34;
    v20 = sqlite3_errmsg(*((_QWORD *)this + 1));
    v21 = "sqlite3_step failed: [%d] %hs";
    v22 = 1570;
  }
  LODWORD(v25) = v18;
  AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::DropTable", v22, v21, v25, v20);
  if ( v18 > 0 )
    v7 = (unsigned __int16)v18 | 0x80070000;
  else
    v7 = v18;
LABEL_34:
  if ( v19 )
    sqlite3_finalize(v19);
  std::wstring::~wstring(v27);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180023734  push    rbp
0x180023736  push    rbx
0x180023737  push    rdi
0x180023738  push    r12
0x18002373a  push    r14
0x18002373c  push    r15
0x18002373e  lea     rbp, [rsp-2Fh]
0x180023743  sub     rsp, 0B8h
0x18002374a  mov     rax, cs:__security_cookie
0x180023751  xor     rax, rsp
0x180023754  mov     [rbp+57h+var_38], rax
0x180023758  mov     r14, rcx
0x18002375b  lea     rdx, [rcx+48h]
0x18002375f  mov     rcx, [rdx+10h]
0x180023763  mov     r15, 7FFFFFFFFFFFFFFEh
0x18002376d  mov     rax, r15
0x180023770  sub     rax, rcx
0x180023773  cmp     rax, 15h
0x180023777  jb      loc_180023A67
0x18002377d  cmp     qword ptr [rdx+18h], 7
0x180023782  jbe     short loc_180023787
0x180023784  mov     rdx, [rdx]
0x180023787  mov     [rsp+0E0h+var_B0], rcx
0x18002378c  mov     [rsp+0E0h+var_B8], rdx
0x180023791  mov     [rsp+0E0h+var_C0], 15h
0x18002379a  lea     r9, aDropTableIfExi; "DROP TABLE IF EXISTS "
0x1800237a1  lea     rcx, [rbp+57h+var_78]
0x1800237a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800237aa  nop
0x1800237ab  lea     r8, Delimiter; ";"
0x1800237b2  lea     rdx, [rbp+57h+var_78]
0x1800237b6  lea     rcx, [rbp+57h+var_98]
0x1800237ba  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800237bf  nop
0x1800237c0  lea     rcx, [rbp+57h+var_78]; void *
0x1800237c4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800237c9  nop
0x1800237ca  lea     rcx, [r14+18h]
0x1800237ce  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x1800237d3  lea     rcx, [r14+30h]
0x1800237d7  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x1800237dc  mov     [rbp+57h+var_A0], 0
0x1800237e4  lea     rdx, [rbp+57h+var_98]
0x1800237e8  cmp     [rbp+57h+var_80], 7
0x1800237ed  cmova   rdx, qword ptr [rbp+57h+var_98]
0x1800237f2  mov     [rsp+0E0h+var_B8], 0
0x1800237fb  lea     rax, [rbp+57h+var_A0]
0x1800237ff  mov     [rsp+0E0h+var_C0], rax
0x180023804  mov     r9d, 80h
0x18002380a  or      r8d, 0FFFFFFFFh
0x18002380e  mov     rcx, [r14+8]
0x180023812  call    sqlite3Prepare16
0x180023817  mov     edi, eax
0x180023819  test    eax, eax
0x18002381b  jz      short loc_180023856
0x18002381d  mov     rcx, [r14+8]
0x180023821  call    sqlite3_errmsg
0x180023826  mov     [rsp+0E0h+var_B8], rax
0x18002382b  mov     dword ptr [rsp+0E0h+var_C0], edi
0x18002382f  lea     r9, aSqlite3ExecFai; "sqlite3_exec failed: [%d] %hs"
0x180023836  mov     r8d, 608h
0x18002383c  lea     rdx, aWindowsCompatI_3; "Windows::Compat::Inventory::SqliteInvCa"...
0x180023843  mov     ecx, 1
0x180023848  call    AslLogCallPrintf
0x18002384d  test    edi, edi
0x18002384f  jle     short loc_1800238C8
0x180023851  movzx   edi, di
0x180023854  jmp     short loc_1800238C2
0x180023856  xor     edi, edi
0x180023858  xor     r12d, r12d
0x18002385b  mov     rcx, [rbp+57h+var_A0]
0x18002385f  call    sqlite3_step
0x180023864  mov     ebx, eax
0x180023866  lea     ecx, [rax-5]
0x180023869  cmp     ecx, 1
0x18002386c  ja      short loc_180023882
0x18002386e  mov     ecx, 5; dwMilliseconds
0x180023873  call    cs:__imp_Sleep
0x180023879  inc     r12d
0x18002387c  cmp     r12d, 64h ; 'd'
0x180023880  jl      short loc_18002385B
0x180023882  cmp     ebx, 65h ; 'e'
0x180023885  jz      short loc_1800238C8
0x180023887  mov     rcx, [r14+8]
0x18002388b  call    sqlite3_errmsg
0x180023890  mov     [rsp+0E0h+var_B8], rax
0x180023895  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180023899  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x1800238a0  mov     r8d, 610h
0x1800238a6  lea     rdx, aWindowsCompatI_3; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800238ad  mov     ecx, 1
0x1800238b2  call    AslLogCallPrintf
0x1800238b7  test    ebx, ebx
0x1800238b9  jg      short loc_1800238BF
0x1800238bb  mov     edi, ebx
0x1800238bd  jmp     short loc_1800238C8
0x1800238bf  movzx   edi, bx
0x1800238c2  or      edi, 80070000h
0x1800238c8  lea     rax, [r14+68h]
0x1800238cc  mov     rcx, [rax+10h]
0x1800238d0  sub     r15, rcx
0x1800238d3  cmp     r15, 15h
0x1800238d7  jb      loc_180023A61
0x1800238dd  cmp     qword ptr [rax+18h], 7
0x1800238e2  jbe     short loc_1800238E7
0x1800238e4  mov     rax, [rax]
0x1800238e7  mov     [rsp+0E0h+var_B0], rcx
0x1800238ec  mov     [rsp+0E0h+var_B8], rax
0x1800238f1  mov     [rsp+0E0h+var_C0], 15h
0x1800238fa  lea     r9, aDropTableIfExi; "DROP TABLE IF EXISTS "
0x180023901  lea     rcx, [rbp+57h+var_78]
0x180023905  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002390a  nop
0x18002390b  lea     r8, Delimiter; ";"
0x180023912  lea     rdx, [rbp+57h+var_78]
0x180023916  lea     rcx, [rbp+57h+var_58]
0x18002391a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002391f  mov     rdx, rax
0x180023922  lea     rcx, [rbp+57h+var_98]
0x180023926  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002392b  lea     rcx, [rbp+57h+var_58]; void *
0x18002392f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023934  nop
0x180023935  lea     rcx, [rbp+57h+var_78]; void *
0x180023939  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002393e  cmp     [rbp+57h+var_A0], 0
0x180023943  jz      short loc_18002395F
0x180023945  call    cs:__imp_GetLastError
0x18002394b  mov     ebx, eax
0x18002394d  mov     rcx, [rbp+57h+var_A0]
0x180023951  call    sqlite3_finalize
0x180023956  mov     ecx, ebx; dwErrCode
0x180023958  call    cs:__imp_SetLastError
0x18002395e  nop
0x18002395f  mov     [rbp+57h+var_A0], 0
0x180023967  lea     rdx, [rbp+57h+var_98]
0x18002396b  cmp     [rbp+57h+var_80], 7
0x180023970  cmova   rdx, qword ptr [rbp+57h+var_98]
0x180023975  mov     [rsp+0E0h+var_B8], 0
0x18002397e  lea     rax, [rbp+57h+var_A0]
0x180023982  mov     [rsp+0E0h+var_C0], rax
0x180023987  mov     r9d, 80h
0x18002398d  or      r8d, 0FFFFFFFFh
0x180023991  mov     rcx, [r14+8]
0x180023995  call    sqlite3Prepare16
0x18002399a  mov     ebx, eax
0x18002399c  mov     r12, [rbp+57h+var_A0]
0x1800239a0  test    eax, eax
0x1800239a2  jz      short loc_1800239BC
0x1800239a4  mov     rcx, [r14+8]
0x1800239a8  call    sqlite3_errmsg
0x1800239ad  lea     r9, aSqlite3ExecFai; "sqlite3_exec failed: [%d] %hs"
0x1800239b4  mov     r8d, 61Ah
0x1800239ba  jmp     short loc_180023A00
0x1800239bc  xor     r15d, r15d
0x1800239bf  mov     rcx, r12
0x1800239c2  call    sqlite3_step
0x1800239c7  mov     ebx, eax
0x1800239c9  lea     ecx, [rax-5]
0x1800239cc  cmp     ecx, 1
0x1800239cf  ja      short loc_1800239E5
0x1800239d1  mov     ecx, 5; dwMilliseconds
0x1800239d6  call    cs:__imp_Sleep
0x1800239dc  inc     r15d
0x1800239df  cmp     r15d, 64h ; 'd'
0x1800239e3  jl      short loc_1800239BF
0x1800239e5  cmp     ebx, 65h ; 'e'
0x1800239e8  jz      short loc_180023A2B
0x1800239ea  mov     rcx, [r14+8]
0x1800239ee  call    sqlite3_errmsg
0x1800239f3  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x1800239fa  mov     r8d, 622h
0x180023a00  mov     [rsp+0E0h+var_B8], rax
0x180023a05  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180023a09  lea     rdx, aWindowsCompatI_3; "Windows::Compat::Inventory::SqliteInvCa"...
0x180023a10  mov     ecx, 1
0x180023a15  call    AslLogCallPrintf
0x180023a1a  test    ebx, ebx
0x180023a1c  jg      short loc_180023A22
0x180023a1e  mov     edi, ebx
0x180023a20  jmp     short loc_180023A2B
0x180023a22  movzx   edi, bx
0x180023a25  or      edi, 80070000h
0x180023a2b  test    r12, r12
0x180023a2e  jz      short loc_180023A39
0x180023a30  mov     rcx, r12
0x180023a33  call    sqlite3_finalize
0x180023a38  nop
0x180023a39  lea     rcx, [rbp+57h+var_98]; void *
0x180023a3d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023a42  mov     eax, edi
0x180023a44  mov     rcx, [rbp+57h+var_38]
0x180023a48  xor     rcx, rsp; StackCookie
0x180023a4b  call    __security_check_cookie
0x180023a50  add     rsp, 0B8h
0x180023a57  pop     r15
0x180023a59  pop     r14
0x180023a5b  pop     r12
0x180023a5d  pop     rdi
0x180023a5e  pop     rbx
0x180023a5f  pop     rbp
0x180023a60  retn
0x180023a61  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180023a67  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
