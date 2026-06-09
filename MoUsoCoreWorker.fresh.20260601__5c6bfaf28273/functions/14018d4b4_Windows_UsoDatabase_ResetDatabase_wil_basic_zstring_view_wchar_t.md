# Windows::UsoDatabase::ResetDatabase(wil::basic_zstring_view<wchar_t>)

- ea: `0x14018d4b4`
- end: `0x14018d911`
- name: `?ResetDatabase@UsoDatabase@Windows@@AEAAXV?$basic_zstring_view@_W@wil@@@Z`
- size: `1117`
- prototype: `__int64 __fastcall(Windows::UsoDatabase *this, _OWORD *)`
- caller_count: `4`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14018eaa4`
- `0x14018ede0`
- `0x14018f420`
- `0x1401901cc`

## callees

- `0x14002cd5c`
- `0x140040184`
- `0x1400413a8`
- `0x140043354`
- `0x1400447ac`
- `0x140045404`
- `0x140057920`
- `0x140058e38`
- `0x1400dda90`
- `0x1401192c4`
- `0x14012d7d8`
- `0x140150f10`
- `0x14018c578`
- `0x14018d304`
- `0x14018d3d8`
- `0x14018d4b4`
- `0x14018f26c`
- `0x14018fb74`
- `0x140190e60`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14018d75c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14018d75c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14018d74a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14018d74a`
- `winsqlite3!sqlite3_open16` at `0x14018d5db`
- `winsqlite3!sqlite3_open16` at `0x14018d5db`
- `winsqlite3!sqlite3_db_config` at `0x14018d61a`
- `winsqlite3!sqlite3_db_config` at `0x14018d697`
- `winsqlite3!sqlite3_db_config` at `0x14018d61a`
- `winsqlite3!sqlite3_db_config` at `0x14018d697`

## string_xrefs

- `0x14018d8a2`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018d8ed`: `remove`
- `0x14018d904`: `remove`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::UsoDatabase::ResetDatabase(Windows::UsoDatabase *this, _OWORD *a2)
{
  _QWORD *System; // rax
  __int64 v6; // rcx
  volatile signed __int32 *v7; // rbx
  signed __int32 v8; // eax
  signed __int32 v9; // eax
  volatile signed __int32 *v10; // rbx
  signed __int32 v11; // eax
  signed __int32 v12; // eax
  _QWORD *v13; // rcx
  int v14; // eax
  unsigned __int64 v15; // r9
  int v16; // eax
  unsigned __int64 v17; // r9
  __int64 traits_1_unsigned_char; // rax
  const char *v19; // r9
  __int64 v20; // r11
  __int64 v21; // rax
  int v22; // eax
  unsigned __int64 v23; // r9
  __int64 result; // rax
  const char *v25; // r9
  __int64 v26; // rbx
  __int64 (__fastcall *v27)(__int64, _OWORD *, unsigned __int64); // rsi
  unsigned __int64 DatabaseSizeInBytes; // rax
  Windows::UsoDatabase *v29; // rsi
  struct sqlite3 *v30; // rdi
  DWORD LastError; // ebx
  char *v32; // rcx
  unsigned __int64 v33; // rax
  _QWORD *v34; // rcx
  unsigned __int64 v35; // rax
  _OWORD *v36; // r14
  __int64 v37; // rdi
  void (__fastcall *v38)(__int64, _OWORD *, unsigned __int64); // rbx
  unsigned __int64 v39; // rax
  int v40[2]; // [rsp+20h] [rbp-A8h] BYREF
  volatile signed __int32 *v41; // [rsp+28h] [rbp-A0h]
  __int128 v42; // [rsp+30h] [rbp-98h] BYREF
  Windows::UsoDatabase *v43; // [rsp+40h] [rbp-88h]
  _OWORD v44[2]; // [rsp+50h] [rbp-78h] BYREF
  _OWORD *v45; // [rsp+70h] [rbp-58h]
  _QWORD v46[4]; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v43 = this;
  v45 = a2;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::GetImpl'::`2'::impl) )
  {
    System = (_QWORD *)SystemInterface::Providers::GetSystem(v44);
    v6 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*System + 40LL))(*System, v40);
    v42 = *a2;
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v6 + 312LL))(v6, &v42);
    v7 = v41;
    if ( v41 )
    {
      v8 = _InterlockedExchangeAdd(v41 + 2, 0xFFFFFFFF);
      if ( v8 == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        v9 = _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF);
        if ( v9 == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    v10 = (volatile signed __int32 *)*((_QWORD *)&v44[0] + 1);
    if ( *((_QWORD *)&v44[0] + 1) )
    {
      v11 = _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v44[0] + 1) + 8LL), 0xFFFFFFFF);
      if ( v11 == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        v12 = _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF);
        if ( v12 == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
  }
  try
  {
    if ( !*((_QWORD *)this + 5) )
    {
      v13 = (_QWORD *)((char *)this + 8);
      if ( *((_QWORD *)this + 4) > 7u )
        v13 = (_QWORD *)*v13;
      v14 = sqlite3_open16(v13, (char *)this + 40);
      v15 = (unsigned __int16)v14 | 0x87AF0000;
      if ( v14 <= 0 )
        v15 = (unsigned int)v14;
      if ( (v15 & 0x80000000) != 0LL )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x15C,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
          (const char *)v15,
          v40[0]);
    }
    v16 = sqlite3_db_config(*((_QWORD *)this + 5), 1009, 1);
    v17 = (unsigned __int16)v16 | 0x87AF0000;
    if ( v16 <= 0 )
      v17 = (unsigned int)v16;
    if ( (v17 & 0x80000000) != 0LL )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15F,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
        (const char *)v17,
        v40[0]);
    traits_1_unsigned_char = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                               "VACUUM",
                               byte_14041AF53,
                               0);
    if ( traits_1_unsigned_char == v20 || (v21 = traits_1_unsigned_char - (_QWORD)"VACUUM", v21 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v19);
    *(_QWORD *)v40 = "VACUUM";
    v41 = (volatile signed __int32 *)v21;
    Windows::SqlExec((char *)this + 40, v40);
    v22 = sqlite3_db_config(*((_QWORD *)this + 5), 1009, 0);
    v23 = (unsigned __int16)v22 | 0x87AF0000;
    if ( v22 <= 0 )
      v23 = (unsigned int)v22;
    if ( (v23 & 0x80000000) != 0LL )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
        (const char *)v23,
        v40[0]);
    *(_QWORD *)v40 = *(_QWORD *)a2;
    *(_QWORD *)&v42 = L"UsoDatabase reset: {}";
    *((_QWORD *)&v42 + 1) = 21;
    SystemInterface::Log<wchar_t const *>(&v42, v40);
    Windows::UsoDatabase::PopulateTables(this);
    Windows::UsoDatabase::InsertVersion(this);
    result = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::GetImpl'::`2'::impl);
    if ( (_BYTE)result )
    {
      v26 = *((_QWORD *)this + 7);
      v27 = *(__int64 (__fastcall **)(__int64, _OWORD *, unsigned __int64))(*(_QWORD *)v26 + 32LL);
      DatabaseSizeInBytes = Windows::UsoDatabase::GetDatabaseSizeInBytes(this);
      v44[0] = *a2;
      result = v27(v26, v44, DatabaseSizeInBytes);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x16D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
      v25);
    v29 = v43;
    v30 = (struct sqlite3 *)*((_QWORD *)v43 + 5);
    if ( v30 )
    {
      LastError = GetLastError();
      Windows::SqliteDatabaseClose(v30);
      SetLastError(LastError);
    }
    *((_QWORD *)v29 + 5) = 0;
    v32 = (char *)v29 + 8;
    if ( *((_QWORD *)v29 + 4) > 7u )
      v32 = (char *)*((_QWORD *)v29 + 1);
    v33 = (unsigned __int64)_std_fs_remove(v32) >> 32;
    if ( (_DWORD)v33 )
      std::filesystem::_Throw_fs_error("remove", (unsigned int)v33, (char *)v29 + 8);
    std::wstring::wstring(v46, (char *)v29 + 8);
    *(_QWORD *)&v42 = L".bak";
    *((_QWORD *)&v42 + 1) = 4;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v44, &v42);
    std::filesystem::path::replace_extension((std::filesystem::path *)v46, (const struct std::filesystem::path *)v44);
    std::wstring::~wstring(v44);
    v34 = v46;
    if ( v46[3] > 7u )
      v34 = (_QWORD *)v46[0];
    v35 = (unsigned __int64)_std_fs_remove(v34) >> 32;
    if ( (_DWORD)v35 )
      std::filesystem::_Throw_fs_error("remove", (unsigned int)v35, v46);
    v36 = v45;
    v44[0] = *v45;
    Windows::UsoDatabase::CreateDatabase(v29);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::GetImpl'::`2'::impl) )
    {
      v37 = *((_QWORD *)v29 + 7);
      v38 = *(void (__fastcall **)(__int64, _OWORD *, unsigned __int64))(*(_QWORD *)v37 + 32LL);
      v39 = Windows::UsoDatabase::GetDatabaseSizeInBytes(v29);
      v44[0] = *v36;
      v38(v37, v44, v39);
    }
    return std::wstring::~wstring(v46);
  }
  return result;
}

```

## disassembly

```asm
0x14018d4b4  mov     [rsp+arg_10], rbx
0x14018d4b9  push    rsi
0x14018d4ba  push    rdi
0x14018d4bb  push    r14
0x14018d4bd  sub     rsp, 0B0h
0x14018d4c4  mov     rax, cs:__security_cookie
0x14018d4cb  xor     rax, rsp
0x14018d4ce  mov     [rsp+0C8h+var_28], rax
0x14018d4d6  mov     r14, rdx
0x14018d4d9  mov     rdi, rcx
0x14018d4dc  mov     [rsp+0C8h+var_88], rcx
0x14018d4e1  mov     [rsp+0C8h+var_58], rdx
0x14018d4e6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::GetImpl(void)'::`2'::impl
0x14018d4ed  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::__private_IsEnabled(void)
0x14018d4f2  test    al, al
0x14018d4f4  jnz     loc_14018D5C0
0x14018d4fa  lea     rcx, [rsp+0C8h+var_78]
0x14018d4ff  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x14018d504  nop
0x14018d505  mov     rcx, [rax]
0x14018d508  mov     rax, [rcx]
0x14018d50b  lea     rdx, [rsp+0C8h+var_A8]
0x14018d510  mov     rax, [rax+28h]
0x14018d514  call    _guard_dispatch_icall
0x14018d519  nop
0x14018d51a  mov     rcx, [rax]
0x14018d51d  movaps  xmm0, xmmword ptr [r14]
0x14018d521  movdqa  [rsp+0C8h+var_98], xmm0
0x14018d527  mov     rax, [rcx]
0x14018d52a  lea     rdx, [rsp+0C8h+var_98]
0x14018d52f  mov     rax, [rax+138h]
0x14018d536  call    _guard_dispatch_icall
0x14018d53b  nop
0x14018d53c  mov     rbx, [rsp+0C8h+var_A0]
0x14018d541  test    rbx, rbx
0x14018d544  jz      short loc_14018D57E
0x14018d546  or      eax, 0FFFFFFFFh
0x14018d549  lock xadd [rbx+8], eax
0x14018d54e  cmp     eax, 1
0x14018d551  jnz     short loc_14018D57E
0x14018d553  mov     rax, [rbx]
0x14018d556  mov     rcx, rbx
0x14018d559  mov     rax, [rax]
0x14018d55c  call    _guard_dispatch_icall
0x14018d561  or      eax, 0FFFFFFFFh
0x14018d564  lock xadd [rbx+0Ch], eax
0x14018d569  cmp     eax, 1
0x14018d56c  jnz     short loc_14018D57E
0x14018d56e  mov     rax, [rbx]
0x14018d571  mov     rcx, rbx
0x14018d574  mov     rax, [rax+8]
0x14018d578  call    _guard_dispatch_icall
0x14018d57d  nop
0x14018d57e  mov     rbx, qword ptr [rsp+0C8h+var_78+8]
0x14018d583  test    rbx, rbx
0x14018d586  jz      short loc_14018D5C0
0x14018d588  or      eax, 0FFFFFFFFh
0x14018d58b  lock xadd [rbx+8], eax
0x14018d590  cmp     eax, 1
0x14018d593  jnz     short loc_14018D5C0
0x14018d595  mov     rax, [rbx]
0x14018d598  mov     rcx, rbx
0x14018d59b  mov     rax, [rax]
0x14018d59e  call    _guard_dispatch_icall
0x14018d5a3  or      eax, 0FFFFFFFFh
0x14018d5a6  lock xadd [rbx+0Ch], eax
0x14018d5ab  cmp     eax, 1
0x14018d5ae  jnz     short loc_14018D5C0
0x14018d5b0  mov     rax, [rbx]
0x14018d5b3  mov     rcx, rbx
0x14018d5b6  mov     rax, [rax+8]
0x14018d5ba  call    _guard_dispatch_icall
0x14018d5bf  nop
0x14018d5c0  lea     rbx, [rdi+28h]
0x14018d5c4  cmp     qword ptr [rbx], 0
0x14018d5c8  jnz     short loc_14018D606
0x14018d5ca  lea     rcx, [rdi+8]
0x14018d5ce  cmp     qword ptr [rcx+18h], 7
0x14018d5d3  jbe     short loc_14018D5D8
0x14018d5d5  mov     rcx, [rcx]
0x14018d5d8  mov     rdx, rbx
0x14018d5db  call    cs:__imp_sqlite3_open16
0x14018d5e1  movzx   r9d, ax
0x14018d5e5  mov     esi, 87AF0000h
0x14018d5ea  or      r9d, esi
0x14018d5ed  test    eax, eax
0x14018d5ef  cmovle  r9d, eax; char *
0x14018d5f3  mov     rcx, [rsp+0C8h]; this
0x14018d5fb  test    r9d, r9d
0x14018d5fe  js      loc_14018D8B4
0x14018d604  jmp     short loc_14018D60B
0x14018d606  mov     esi, 87AF0000h
0x14018d60b  xor     r9d, r9d
0x14018d60e  mov     edx, 3F1h
0x14018d613  lea     r8d, [r9+1]
0x14018d617  mov     rcx, [rbx]
0x14018d61a  call    cs:__imp_sqlite3_db_config
0x14018d620  movzx   r9d, ax
0x14018d624  or      r9d, esi
0x14018d627  test    eax, eax
0x14018d629  cmovle  r9d, eax; char *
0x14018d62d  mov     rcx, [rsp+0C8h]; this
0x14018d635  test    r9d, r9d
0x14018d638  js      loc_14018D8C5
0x14018d63e  xor     r8d, r8d
0x14018d641  lea     r11, byte_14041AF53
0x14018d648  mov     rdx, r11
0x14018d64b  lea     rbx, aVacuum; "VACUUM"
0x14018d652  mov     rcx, rbx
0x14018d655  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018d65a  cmp     rax, r11
0x14018d65d  jz      loc_14018D89A
0x14018d663  sub     rax, rbx
0x14018d666  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018d66a  jz      loc_14018D89A
0x14018d670  mov     qword ptr [rsp+0C8h+var_A8], rbx; int
0x14018d675  mov     [rsp+0C8h+var_A0], rax
0x14018d67a  lea     rcx, [rdi+28h]
0x14018d67e  lea     rdx, [rsp+0C8h+var_A8]
0x14018d683  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018d688  xor     r9d, r9d
0x14018d68b  xor     r8d, r8d
0x14018d68e  mov     edx, 3F1h
0x14018d693  mov     rcx, [rdi+28h]
0x14018d697  call    cs:__imp_sqlite3_db_config
0x14018d69d  movzx   r9d, ax
0x14018d6a1  or      r9d, esi
0x14018d6a4  test    eax, eax
0x14018d6a6  cmovle  r9d, eax; char *
0x14018d6aa  mov     rcx, [rsp+0C8h]; this
0x14018d6b2  test    r9d, r9d
0x14018d6b5  js      loc_14018D8D6
0x14018d6bb  mov     rax, [r14]
0x14018d6be  mov     qword ptr [rsp+0C8h+var_A8], rax
0x14018d6c3  lea     rax, aUsodatabaseRes; "UsoDatabase reset: {}"
0x14018d6ca  mov     qword ptr [rsp+0C8h+var_98], rax
0x14018d6cf  mov     qword ptr [rsp+0C8h+var_98+8], 15h
0x14018d6d8  lea     rdx, [rsp+0C8h+var_A8]
0x14018d6dd  lea     rcx, [rsp+0C8h+var_98]
0x14018d6e2  call    ??$Log@PEB_W@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$$QEAPEB_W@Z; SystemInterface::Log<wchar_t const *>(std::wstring_view,wchar_t const * &&)
0x14018d6e7  mov     rcx, rdi; this
0x14018d6ea  call    ?PopulateTables@UsoDatabase@Windows@@AEAAXXZ; Windows::UsoDatabase::PopulateTables(void)
0x14018d6ef  mov     rcx, rdi; this
0x14018d6f2  call    ?InsertVersion@UsoDatabase@Windows@@AEAAXXZ; Windows::UsoDatabase::InsertVersion(void)
0x14018d6f7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::GetImpl(void)'::`2'::impl
0x14018d6fe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::__private_IsEnabled(void)
0x14018d703  test    al, al
0x14018d705  jz      short loc_14018D737
0x14018d707  mov     rbx, [rdi+38h]
0x14018d70b  mov     rax, [rbx]
0x14018d70e  mov     rsi, [rax+20h]
0x14018d712  mov     rcx, rdi; this
0x14018d715  call    ?GetDatabaseSizeInBytes@UsoDatabase@Windows@@UEBA_KXZ; Windows::UsoDatabase::GetDatabaseSizeInBytes(void)
0x14018d71a  movaps  xmm0, xmmword ptr [r14]
0x14018d71e  movdqa  [rsp+0C8h+var_78], xmm0
0x14018d724  mov     r8, rax
0x14018d727  lea     rdx, [rsp+0C8h+var_78]
0x14018d72c  mov     rcx, rbx
0x14018d72f  mov     rax, rsi
0x14018d732  call    _guard_dispatch_icall
0x14018d737  jmp     loc_14018D876
0x14018d73c  mov     rsi, [rsp+0C8h+var_88]
0x14018d741  mov     rdi, [rsi+28h]
0x14018d745  test    rdi, rdi
0x14018d748  jz      short loc_14018D763
0x14018d74a  call    cs:__imp_GetLastError
0x14018d750  mov     ebx, eax
0x14018d752  mov     rcx, rdi; struct sqlite3 *
0x14018d755  call    ?SqliteDatabaseClose@Windows@@YAXPEAUsqlite3@@@Z; Windows::SqliteDatabaseClose(sqlite3 *)
0x14018d75a  mov     ecx, ebx; dwErrCode
0x14018d75c  call    cs:__imp_SetLastError
0x14018d762  nop
0x14018d763  mov     qword ptr [rsi+28h], 0
0x14018d76b  lea     rbx, [rsi+8]
0x14018d76f  mov     rcx, rbx
0x14018d772  cmp     qword ptr [rbx+18h], 7
0x14018d777  jbe     short loc_14018D77C
0x14018d779  mov     rcx, [rbx]
0x14018d77c  call    __std_fs_remove
0x14018d781  shr     rax, 20h
0x14018d785  test    eax, eax
0x14018d787  jnz     loc_14018D8E8
0x14018d78d  mov     rdx, rbx
0x14018d790  lea     rcx, [rsp+0C8h+var_48]
0x14018d798  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14018d79d  nop
0x14018d79e  lea     rax, aBak; ".bak"
0x14018d7a5  mov     qword ptr [rsp+0C8h+var_98], rax
0x14018d7aa  mov     qword ptr [rsp+0C8h+var_98+8], 4
0x14018d7b3  lea     rdx, [rsp+0C8h+var_98]
0x14018d7b8  lea     rcx, [rsp+0C8h+var_78]
0x14018d7bd  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x14018d7c2  nop
0x14018d7c3  lea     rdx, [rsp+0C8h+var_78]; struct std::filesystem::path *
0x14018d7c8  lea     rcx, [rsp+0C8h+var_48]; this
0x14018d7d0  call    ?replace_extension@path@filesystem@std@@QEAAAEAV123@AEBV123@@Z; std::filesystem::path::replace_extension(std::filesystem::path const &)
0x14018d7d5  nop
0x14018d7d6  lea     rcx, [rsp+0C8h+var_78]
0x14018d7db  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14018d7e0  lea     rcx, [rsp+0C8h+var_48]
0x14018d7e8  cmp     [rsp+0C8h+var_30], 7
0x14018d7f1  cmova   rcx, [rsp+0C8h+var_48]
0x14018d7fa  call    __std_fs_remove
0x14018d7ff  shr     rax, 20h
0x14018d803  test    eax, eax
0x14018d805  jnz     loc_14018D8FA
0x14018d80b  mov     r14, [rsp+0C8h+var_58]
0x14018d810  movaps  xmm0, xmmword ptr [r14]
0x14018d814  movdqa  [rsp+0C8h+var_78], xmm0
0x14018d81a  lea     rdx, [rsp+0C8h+var_78]
0x14018d81f  mov     rcx, rsi; this
0x14018d822  call    ?CreateDatabase@UsoDatabase@Windows@@AEAAXV?$basic_zstring_view@_W@wil@@@Z; Windows::UsoDatabase::CreateDatabase(wil::basic_zstring_view<wchar_t>)
0x14018d827  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::GetImpl(void)'::`2'::impl
0x14018d82e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::__private_IsEnabled(void)
0x14018d833  test    al, al
0x14018d835  jz      short loc_14018D868
0x14018d837  mov     rdi, [rsi+38h]
0x14018d83b  mov     rax, [rdi]
0x14018d83e  mov     rbx, [rax+20h]
0x14018d842  mov     rcx, rsi; this
0x14018d845  call    ?GetDatabaseSizeInBytes@UsoDatabase@Windows@@UEBA_KXZ; Windows::UsoDatabase::GetDatabaseSizeInBytes(void)
0x14018d84a  movaps  xmm0, xmmword ptr [r14]
0x14018d84e  movdqa  [rsp+0C8h+var_78], xmm0
0x14018d854  mov     r8, rax
0x14018d857  lea     rdx, [rsp+0C8h+var_78]
0x14018d85c  mov     rcx, rdi
0x14018d85f  mov     rax, rbx
0x14018d862  call    _guard_dispatch_icall
0x14018d867  nop
0x14018d868  lea     rcx, [rsp+0C8h+var_48]
0x14018d870  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14018d875  nop
0x14018d876  mov     rcx, [rsp+0C8h+var_28]
0x14018d87e  xor     rcx, rsp; StackCookie
0x14018d881  call    __security_check_cookie
0x14018d886  mov     rbx, [rsp+0C8h+arg_10]
0x14018d88e  add     rsp, 0B0h
0x14018d895  pop     r14
0x14018d897  pop     rdi
0x14018d898  pop     rsi
0x14018d899  retn
0x14018d89a  mov     rcx, [rsp+0C8h]; this
0x14018d8a2  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14018d8a9  mov     edx, 0C9h; void *
0x14018d8ae  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14018d8b4  lea     r8, aCW1SSrcOrchest_31; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14018d8bb  mov     edx, 15Ch; void *
0x14018d8c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14018d8c5  lea     r8, aCW1SSrcOrchest_31; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14018d8cc  mov     edx, 15Fh; void *
0x14018d8d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14018d8d6  lea     r8, aCW1SSrcOrchest_31; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14018d8dd  mov     edx, 161h; void *
0x14018d8e2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14018d8e8  mov     r8, rbx
0x14018d8eb  mov     edx, eax
0x14018d8ed  lea     rcx, aRemove; "remove"
0x14018d8f4  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &)
0x14018d8fa  lea     r8, [rsp+0C8h+var_48]
0x14018d902  mov     edx, eax
0x14018d904  lea     rcx, aRemove; "remove"
0x14018d90b  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &)
```
