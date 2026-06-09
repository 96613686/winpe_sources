# Windows::Compat::Inventory::SqliteInvCache::GetItemList(std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,unsigned __int64)

- ea: `0x1800247b4`
- end: `0x180024af8`
- name: `?GetItemList@SqliteInvCache@Inventory@Compat@Windows@@QEBAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_K@Z`
- size: `836`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180023cd0`
- `0x180028ae0`

## callees

- `0x180002bf0`
- `0x180002c40`
- `0x180006a04`
- `0x1800074f0`
- `0x1800152d0`
- `0x18001f4a4`
- `0x1800247b4`
- `0x18002e028`
- `0x1800817cc`
- `0x18009e760`
- `0x18009f9e0`
- `0x1800a1980`
- `0x1800a22c0`
- `0x1800a4690`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180024a55`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180024a55`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800249b1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800249b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800247f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800247f9`

## string_xrefs

- `0x180024939`: `Windows::Compat::Inventory::SqliteInvCache::GetItemList`
- `0x180024aa6`: `Windows::Compat::Inventory::SqliteInvCache::GetItemList`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::GetItemList(
        __int64 a1,
        __int64 *a2,
        struct _FILETIME a3)
{
  struct _FILETIME v3; // rbx
  __int64 v6; // rax
  void *v7; // rax
  __int64 v8; // rax
  _QWORD *v9; // rdx
  int v10; // eax
  int v11; // edi
  struct _FILETIME v12; // rsi
  unsigned int v13; // ebx
  __int64 v14; // rax
  const char *v15; // r9
  __int64 v16; // r8
  int v17; // eax
  int i; // ebx
  __int64 v19; // rdi
  __int64 v20; // r13
  _OWORD *v21; // rbx
  __int64 v22; // r8
  _QWORD *v23; // rax
  __int64 v25; // [rsp+20h] [rbp-99h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-89h] BYREF
  __int128 v27; // [rsp+38h] [rbp-81h] BYREF
  __int128 v28; // [rsp+48h] [rbp-71h]
  __int128 v29; // [rsp+58h] [rbp-61h] BYREF
  __int64 v30; // [rsp+68h] [rbp-51h]
  __int64 v31; // [rsp+70h] [rbp-49h]
  _QWORD v32[4]; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v33[32]; // [rsp+98h] [rbp-21h] BYREF
  _BYTE v34[32]; // [rsp+B8h] [rbp-1h] BYREF

  v3 = a3;
  if ( !*(_QWORD *)&a3 )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v3 = SystemTimeAsFileTime;
  }
  v29 = 0;
  v30 = 0;
  v31 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v29);
  v6 = std::operator+<unsigned short>(v34, &v29, L"ItemKey");
  v7 = (void *)std::operator+<unsigned short>(v33, v6, L" FROM ");
  v8 = std::wstring::append(v7);
  v27 = 0;
  v28 = 0u;
  v27 = *(_OWORD *)v8;
  v28 = *(_OWORD *)(v8 + 16);
  *(_QWORD *)(v8 + 16) = 0;
  *(_QWORD *)(v8 + 24) = 7;
  *(_WORD *)v8 = 0;
  std::operator+<unsigned short>(v32, &v27, L" WHERE LastModified <= ?;");
  std::wstring::~wstring(&v27);
  std::wstring::~wstring(v33);
  std::wstring::~wstring(v34);
  std::wstring::~wstring(&v29);
  SystemTimeAsFileTime = 0;
  v9 = v32;
  if ( v32[3] > 7u )
    LODWORD(v9) = v32[0];
  v10 = sqlite3Prepare16(*(_QWORD *)(a1 + 8), (_DWORD)v9, -1, 128, (__int64)&SystemTimeAsFileTime, 0);
  v11 = v10;
  v12 = SystemTimeAsFileTime;
  if ( v10 )
  {
    if ( v10 > 0 )
      v13 = (unsigned __int16)v10 | 0x80070000;
    else
      v13 = v10;
    v14 = sqlite3_errmsg(*(_QWORD *)(a1 + 8));
    v15 = "sqlite3_prepare_v2 failed: [%d] %hs";
    v16 = 884;
LABEL_10:
    LODWORD(v25) = v11;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::GetItemList", v16, v15, v25, v14);
    goto LABEL_33;
  }
  if ( SystemTimeAsFileTime )
  {
    v17 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))sqlite3_bind_int64)(SystemTimeAsFileTime, 1, v3);
    v11 = v17;
    if ( v17 )
    {
      if ( v17 > 0 )
        v13 = (unsigned __int16)v17 | 0x80070000;
      else
        v13 = v17;
      v14 = sqlite3_errmsg(*(_QWORD *)(a1 + 8));
      v15 = "sqlite3_bind_int64 failed: [%d] %hs";
      v16 = 897;
      goto LABEL_10;
    }
    while ( 1 )
    {
      for ( i = 0; i < 100; ++i )
      {
        v11 = ((__int64 (__fastcall *)(_QWORD))sqlite3_step)(v12);
        if ( (unsigned int)(v11 - 5) > 1 )
          break;
        Sleep(5u);
      }
      if ( v11 != 100 )
        break;
      v19 = ((__int64 (__fastcall *)(_QWORD, _QWORD))sqlite3_column_text16)(v12, 0);
      if ( v19 )
      {
        if ( a2[1] == 0x555555555555555LL )
          std::_Xlength_error("list too long");
        v20 = *a2;
        v27 = (unsigned __int64)a2;
        v21 = operator new(0x30u);
        *((_QWORD *)&v27 + 1) = v21;
        v21[1] = 0;
        *((_QWORD *)v21 + 4) = 0;
        *((_QWORD *)v21 + 5) = 0;
        v22 = -1;
        do
          ++v22;
        while ( *(_WORD *)(v19 + 2 * v22) );
        std::wstring::_Construct<1,unsigned short const *>(v21 + 1);
        ++a2[1];
        v23 = *(_QWORD **)(v20 + 8);
        *(_QWORD *)v21 = v20;
        *((_QWORD *)v21 + 1) = v23;
        *((_QWORD *)&v27 + 1) = 0;
        *(_QWORD *)(v20 + 8) = v21;
        *v23 = v21;
      }
    }
    v13 = 0;
    if ( v11 != 101 )
    {
      if ( v11 > 0 )
        v13 = (unsigned __int16)v11 | 0x80070000;
      else
        v13 = v11;
      v14 = sqlite3_errmsg(*(_QWORD *)(a1 + 8));
      v15 = "sqlite3_step failed: [%d] %hs";
      v16 = 911;
      goto LABEL_10;
    }
  }
  else
  {
    v13 = -2147467259;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::GetItemList",
      890,
      "sqlite3_prepare_v2 returned a null statement [%#x]",
      -2147467259);
  }
LABEL_33:
  if ( v12 )
    ((void (__fastcall *)(_QWORD))sqlite3_finalize)(v12);
  std::wstring::~wstring(v32);
  return v13;
}

```

## disassembly

```asm
0x1800247b4  mov     [rsp-8+arg_18], rbx
0x1800247b9  push    rbp
0x1800247ba  push    rsi
0x1800247bb  push    rdi
0x1800247bc  push    r12
0x1800247be  push    r13
0x1800247c0  push    r14
0x1800247c2  push    r15
0x1800247c4  lea     rbp, [rsp-27h]
0x1800247c9  sub     rsp, 0E0h
0x1800247d0  mov     rax, cs:__security_cookie
0x1800247d7  xor     rax, rsp
0x1800247da  mov     [rbp+57h+var_38], rax
0x1800247de  mov     rbx, r8
0x1800247e1  mov     r14, rdx
0x1800247e4  mov     r15, rcx
0x1800247e7  xor     r12d, r12d
0x1800247ea  test    r8, r8
0x1800247ed  jnz     short loc_180024804
0x1800247ef  mov     qword ptr [rsp+110h+SystemTimeAsFileTime.dwLowDateTime], r12
0x1800247f4  lea     rcx, [rsp+110h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800247f9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800247ff  mov     rbx, qword ptr [rsp+110h+SystemTimeAsFileTime.dwLowDateTime]
0x180024804  xorps   xmm0, xmm0
0x180024807  movups  [rbp+57h+var_B8], xmm0
0x18002480b  mov     [rbp+57h+var_A8], r12
0x18002480f  mov     [rbp+57h+var_A0], r12
0x180024813  mov     edi, 7
0x180024818  mov     r8d, edi
0x18002481b  lea     rdx, aSelect; "SELECT "
0x180024822  lea     rcx, [rbp+57h+var_B8]
0x180024826  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002482b  nop
0x18002482c  lea     r8, aItemkey; "ItemKey"
0x180024833  lea     rdx, [rbp+57h+var_B8]
0x180024837  lea     rcx, [rbp+57h+var_58]
0x18002483b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180024840  nop
0x180024841  lea     r8, aFrom_0; " FROM "
0x180024848  mov     rdx, rax
0x18002484b  lea     rcx, [rbp+57h+var_78]
0x18002484f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180024854  nop
0x180024855  lea     rdx, [r15+48h]
0x180024859  mov     rcx, rax; Src
0x18002485c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180024861  xorps   xmm0, xmm0
0x180024864  movups  [rsp+110h+var_D8], xmm0
0x180024869  mov     qword ptr [rbp+57h+var_C8], r12
0x18002486d  mov     qword ptr [rbp+57h+var_C8+8], r12
0x180024871  movups  xmm0, xmmword ptr [rax]
0x180024874  movups  [rsp+110h+var_D8], xmm0
0x180024879  movups  xmm1, xmmword ptr [rax+10h]
0x18002487d  movups  [rbp+57h+var_C8], xmm1
0x180024881  mov     [rax+10h], r12
0x180024885  mov     [rax+18h], rdi
0x180024889  mov     [rax], r12w
0x18002488d  lea     r8, aWhereLastmodif; " WHERE LastModified <= ?;"
0x180024894  lea     rdx, [rsp+110h+var_D8]
0x180024899  lea     rcx, [rbp+57h+var_98]
0x18002489d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800248a2  nop
0x1800248a3  lea     rcx, [rsp+110h+var_D8]; void *
0x1800248a8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800248ad  nop
0x1800248ae  lea     rcx, [rbp+57h+var_78]; void *
0x1800248b2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800248b7  nop
0x1800248b8  lea     rcx, [rbp+57h+var_58]; void *
0x1800248bc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800248c1  nop
0x1800248c2  lea     rcx, [rbp+57h+var_B8]; void *
0x1800248c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800248cb  nop
0x1800248cc  mov     qword ptr [rsp+110h+SystemTimeAsFileTime.dwLowDateTime], r12
0x1800248d1  lea     rdx, [rbp+57h+var_98]
0x1800248d5  cmp     [rbp+57h+var_80], rdi
0x1800248d9  cmova   rdx, [rbp+57h+var_98]
0x1800248de  mov     [rsp+110h+var_E8], r12
0x1800248e3  lea     rax, [rsp+110h+SystemTimeAsFileTime]
0x1800248e8  mov     [rsp+110h+var_F0], rax
0x1800248ed  lea     r9d, [rdi+79h]
0x1800248f1  or      r8d, 0FFFFFFFFh
0x1800248f5  mov     rcx, [r15+8]
0x1800248f9  call    sqlite3Prepare16
0x1800248fe  mov     edi, eax
0x180024900  mov     rsi, qword ptr [rsp+110h+SystemTimeAsFileTime.dwLowDateTime]
0x180024905  test    eax, eax
0x180024907  jz      short loc_18002494F
0x180024909  test    eax, eax
0x18002490b  jg      short loc_180024911
0x18002490d  mov     ebx, eax
0x18002490f  jmp     short loc_18002491A
0x180024911  movzx   ebx, di
0x180024914  or      ebx, 80070000h
0x18002491a  mov     rcx, [r15+8]
0x18002491e  call    sqlite3_errmsg
0x180024923  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x18002492a  mov     r8d, 374h
0x180024930  mov     [rsp+110h+var_E8], rax
0x180024935  mov     dword ptr [rsp+110h+var_F0], edi
0x180024939  lea     rdx, aWindowsCompatI_88; "Windows::Compat::Inventory::SqliteInvCa"...
0x180024940  mov     ecx, 1
0x180024945  call    AslLogCallPrintf
0x18002494a  jmp     loc_180024AB8
0x18002494f  test    rsi, rsi
0x180024952  jz      loc_180024A90
0x180024958  mov     r8, rbx
0x18002495b  mov     edx, 1
0x180024960  mov     rcx, rsi
0x180024963  call    sqlite3_bind_int64
0x180024968  mov     edi, eax
0x18002496a  test    eax, eax
0x18002496c  jz      short loc_180024997
0x18002496e  test    eax, eax
0x180024970  jg      short loc_180024976
0x180024972  mov     ebx, eax
0x180024974  jmp     short loc_18002497F
0x180024976  movzx   ebx, di
0x180024979  or      ebx, 80070000h
0x18002497f  mov     rcx, [r15+8]
0x180024983  call    sqlite3_errmsg
0x180024988  lea     r9, aSqlite3BindInt; "sqlite3_bind_int64 failed: [%d] %hs"
0x18002498f  mov     r8d, 381h
0x180024995  jmp     short loc_180024930
0x180024997  mov     ebx, r12d
0x18002499a  mov     rcx, rsi
0x18002499d  call    sqlite3_step
0x1800249a2  mov     edi, eax
0x1800249a4  lea     ecx, [rax-5]
0x1800249a7  cmp     ecx, 1
0x1800249aa  ja      short loc_1800249BE
0x1800249ac  mov     ecx, 5; dwMilliseconds
0x1800249b1  call    cs:__imp_Sleep
0x1800249b7  inc     ebx
0x1800249b9  cmp     ebx, 64h ; 'd'
0x1800249bc  jl      short loc_18002499A
0x1800249be  cmp     edi, 64h ; 'd'
0x1800249c1  jnz     loc_180024A5C
0x1800249c7  xor     edx, edx
0x1800249c9  mov     rcx, rsi
0x1800249cc  call    sqlite3_column_text16
0x1800249d1  mov     rdi, rax
0x1800249d4  test    rax, rax
0x1800249d7  jz      short loc_180024997
0x1800249d9  mov     rax, 555555555555555h
0x1800249e3  cmp     [r14+8], rax
0x1800249e7  jz      short loc_180024A4E
0x1800249e9  mov     r13, [r14]
0x1800249ec  mov     qword ptr [rsp+110h+var_D8], r14
0x1800249f1  mov     qword ptr [rbp+57h+var_D8+8], r12
0x1800249f5  mov     ecx, 30h ; '0'; Size
0x1800249fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800249ff  mov     rbx, rax
0x180024a02  mov     qword ptr [rbp+57h+var_D8+8], rax
0x180024a06  lea     rcx, [rax+10h]
0x180024a0a  xorps   xmm0, xmm0
0x180024a0d  movups  xmmword ptr [rcx], xmm0
0x180024a10  mov     [rcx+10h], r12
0x180024a14  mov     [rcx+18h], r12
0x180024a18  or      r8, 0FFFFFFFFFFFFFFFFh
0x180024a1c  inc     r8
0x180024a1f  cmp     [rdi+r8*2], r12w
0x180024a24  jnz     short loc_180024A1C
0x180024a26  mov     rdx, rdi
0x180024a29  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180024a2e  nop
0x180024a2f  inc     qword ptr [r14+8]
0x180024a33  mov     rax, [r13+8]
0x180024a37  mov     [rbx], r13
0x180024a3a  mov     [rbx+8], rax
0x180024a3e  mov     qword ptr [rbp+57h+var_D8+8], r12
0x180024a42  mov     [r13+8], rbx
0x180024a46  mov     [rax], rbx
0x180024a49  jmp     loc_180024997
0x180024a4e  lea     rcx, aListTooLong; "list too long"
0x180024a55  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180024a5c  mov     ebx, r12d
0x180024a5f  cmp     edi, 65h ; 'e'
0x180024a62  jz      short loc_180024AB8
0x180024a64  test    edi, edi
0x180024a66  jg      short loc_180024A6C
0x180024a68  mov     ebx, edi
0x180024a6a  jmp     short loc_180024A75
0x180024a6c  movzx   ebx, di
0x180024a6f  or      ebx, 80070000h
0x180024a75  mov     rcx, [r15+8]
0x180024a79  call    sqlite3_errmsg
0x180024a7e  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x180024a85  mov     r8d, 38Fh
0x180024a8b  jmp     loc_180024930
0x180024a90  mov     ebx, 80004005h
0x180024a95  mov     dword ptr [rsp+110h+var_F0], ebx
0x180024a99  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x180024aa0  mov     r8d, 37Ah
0x180024aa6  lea     rdx, aWindowsCompatI_88; "Windows::Compat::Inventory::SqliteInvCa"...
0x180024aad  mov     ecx, 1
0x180024ab2  call    AslLogCallPrintf
0x180024ab7  nop
0x180024ab8  test    rsi, rsi
0x180024abb  jz      short loc_180024AC6
0x180024abd  mov     rcx, rsi
0x180024ac0  call    sqlite3_finalize
0x180024ac5  nop
0x180024ac6  lea     rcx, [rbp+57h+var_98]; void *
0x180024aca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024acf  mov     eax, ebx
0x180024ad1  mov     rcx, [rbp+57h+var_38]
0x180024ad5  xor     rcx, rsp; StackCookie
0x180024ad8  call    __security_check_cookie
0x180024add  mov     rbx, [rsp+110h+arg_18]
0x180024ae5  add     rsp, 0E0h
0x180024aec  pop     r15
0x180024aee  pop     r14
0x180024af0  pop     r13
0x180024af2  pop     r12
0x180024af4  pop     rdi
0x180024af5  pop     rsi
0x180024af6  pop     rbp
0x180024af7  retn
```
