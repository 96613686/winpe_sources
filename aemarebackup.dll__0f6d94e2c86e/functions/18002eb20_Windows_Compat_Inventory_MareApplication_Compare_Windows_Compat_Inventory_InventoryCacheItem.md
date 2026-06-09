# Windows::Compat::Inventory::MareApplication::Compare(Windows::Compat::Inventory::InventoryCacheItem *)

- ea: `0x18002eb20`
- end: `0x18002ed6c`
- name: `?Compare@MareApplication@Inventory@Compat@Windows@@UEAA_NPEAVInventoryCacheItem@234@@Z`
- size: `588`
- prototype: `bool __fastcall(Windows::Compat::Inventory::MareApplication *this, struct Windows::Compat::Inventory::InventoryCacheItem *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180004ea0`
- `0x180013ec4`
- `0x18002b570`
- `0x18002d900`
- `0x18002eb20`
- `0x18002f100`
- `0x1800302e0`
- `0x1800308c0`
- `0x18004c020`

## string_xrefs

- `0x18002ec04`: `Windows::Compat::Inventory::MareApplication::Compare`
- `0x18002ec3d`: `Windows::Compat::Inventory::MareApplication::Compare`
- `0x18002ecb9`: `Windows::Compat::Inventory::MareApplication::Compare`
- `0x18002ed19`: `Windows::Compat::Inventory::MareApplication::Compare`
- `0x18002ec30`: `JsonHash this:%zu other:%zu`
- `0x18002ec68`: `updated`
- `0x18002ec75`: `installed`
- `0x18002ecac`: `SID:%ls AppState:%ls`
- `0x18002ed0c`: `%ls updated for %ls`

## pseudocode

```c
bool __fastcall Windows::Compat::Inventory::MareApplication::Compare(
        Windows::Compat::Inventory::MareApplication *this,
        struct Windows::Compat::Inventory::InventoryCacheItem *a2)
{
  const unsigned __int16 **v5; // rdi
  const unsigned __int16 *v6; // rdx
  unsigned __int64 JsonHash; // rax
  bool v8; // bp
  const wchar_t *v9; // rax
  unsigned __int64 v10; // rax
  __int64 i; // rbx
  int v12; // ecx
  const wchar_t *v13; // rax
  const wchar_t *v14; // rcx
  __int64 j; // rbx
  const wchar_t *v16; // rcx
  const wchar_t *v17; // rax
  _BYTE v18[8]; // [rsp+30h] [rbp-138h] BYREF
  _BYTE v19[72]; // [rsp+38h] [rbp-130h] BYREF
  __int64 v20; // [rsp+80h] [rbp-E8h] BYREF
  __int64 v21; // [rsp+88h] [rbp-E0h]
  size_t v22; // [rsp+138h] [rbp-30h]

  if ( !Windows::Compat::Inventory::MareApplication::s_updateMode )
    return 0;
  Windows::Compat::Inventory::MareApplication::MareApplication((Windows::Compat::Inventory::MareApplication *)v18);
  v5 = (const unsigned __int16 **)((char *)this + 40);
  v6 = (const unsigned __int16 *)((char *)this + 40);
  if ( *((_QWORD *)this + 8) > 7u )
    v6 = *v5;
  Windows::Compat::Inventory::MareApplication::SetItemKey((Windows::Compat::Inventory::MareApplication *)v19, v6);
  Windows::Compat::Inventory::MareApplication::Retrieve((Windows::Compat::Inventory::MareApplication *)v19, a2);
  if ( (__int64 *)((char *)this + 72) != &v20 )
    std::vector<std::pair<std::wstring,enum Windows::Compat::Inventory::MareApplication::AppState>>::_Assign_counted_range<std::pair<std::wstring,enum Windows::Compat::Inventory::MareApplication::AppState> *>(
      (__int64 *)this + 9,
      v20,
      0xCCCCCCCCCCCCCCCDuLL * ((v21 - v20) >> 3));
  JsonHash = Windows::Compat::Inventory::MareApplication::GetJsonHash((Windows::Compat::Inventory::MareApplication *)((char *)this - 8));
  v8 = v22 == JsonHash;
  if ( *((_QWORD *)this + 8) <= 7u )
    v9 = (const wchar_t *)((char *)this + 40);
  else
    v9 = *v5;
  AslLogCallPrintf(3, "Windows::Compat::Inventory::MareApplication::Compare", 561, "App: %ls", v9);
  v10 = Windows::Compat::Inventory::MareApplication::GetJsonHash((Windows::Compat::Inventory::MareApplication *)((char *)this - 8));
  AslLogCallPrintf(
    3,
    "Windows::Compat::Inventory::MareApplication::Compare",
    562,
    "JsonHash this:%zu other:%zu",
    v10,
    v22);
  for ( i = v20; i != v21; i += 40 )
  {
    v12 = *(_DWORD *)(i + 32);
    if ( v12 == 1 )
    {
      v13 = L"updated";
    }
    else if ( v12 )
    {
      v13 = L"backedUp";
      if ( v12 != 2 )
        v13 = L"INVALID";
    }
    else
    {
      v13 = L"installed";
    }
    if ( *(_QWORD *)(i + 24) <= 7u )
      v14 = (const wchar_t *)i;
    else
      v14 = *(const wchar_t **)i;
    AslLogCallPrintf(3, "Windows::Compat::Inventory::MareApplication::Compare", 568, "SID:%ls AppState:%ls", v14, v13);
  }
  if ( !v8 )
  {
    for ( j = *((_QWORD *)this + 9); j != *((_QWORD *)this + 10); j += 40 )
    {
      if ( *(_DWORD *)(j + 32) == 2 )
      {
        if ( *(_QWORD *)(j + 24) <= 7u )
          v16 = (const wchar_t *)j;
        else
          v16 = *(const wchar_t **)j;
        if ( *((_QWORD *)this + 8) <= 7u )
          v17 = (const wchar_t *)((char *)this + 40);
        else
          v17 = *v5;
        AslLogCallPrintf(
          3,
          "Windows::Compat::Inventory::MareApplication::Compare",
          580,
          "%ls updated for %ls",
          v17,
          v16);
        *(_DWORD *)(j + 32) = 1;
      }
    }
  }
  Windows::Compat::Inventory::MareApplication::~MareApplication((Windows::Compat::Inventory::MareApplication *)v18);
  return v8;
}

```

## disassembly

```asm
0x18002eb20  mov     [rsp+arg_10], rbx
0x18002eb25  mov     [rsp+arg_18], rbp
0x18002eb2a  push    rsi
0x18002eb2b  push    rdi
0x18002eb2c  push    r14
0x18002eb2e  sub     rsp, 150h
0x18002eb35  mov     rax, cs:__security_cookie
0x18002eb3c  xor     rax, rsp
0x18002eb3f  mov     [rsp+168h+var_28], rax
0x18002eb47  mov     rbx, rdx
0x18002eb4a  mov     rsi, rcx
0x18002eb4d  cmp     cs:?s_updateMode@MareApplication@Inventory@Compat@Windows@@0W4CacheUpdateMode@1234@A, 0; Windows::Compat::Inventory::MareApplication::CacheUpdateMode Windows::Compat::Inventory::MareApplication::s_updateMode
0x18002eb54  jnz     short loc_18002EB5D
0x18002eb56  xor     al, al
0x18002eb58  jmp     loc_18002ED44
0x18002eb5d  lea     rcx, [rsp+168h+var_138]; this
0x18002eb62  call    ??0MareApplication@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::MareApplication::MareApplication(void)
0x18002eb67  nop
0x18002eb68  lea     rdi, [rsi+28h]
0x18002eb6c  mov     rdx, rdi
0x18002eb6f  cmp     qword ptr [rdi+18h], 7
0x18002eb74  jbe     short loc_18002EB79
0x18002eb76  mov     rdx, [rdi]; unsigned __int16 *
0x18002eb79  lea     rcx, [rsp+168h+var_130]; this
0x18002eb7e  call    ?SetItemKey@MareApplication@Inventory@Compat@Windows@@UEAAKPEBG@Z; Windows::Compat::Inventory::MareApplication::SetItemKey(ushort const *)
0x18002eb83  mov     rdx, rbx; struct Windows::Compat::Inventory::InventoryCacheItem *
0x18002eb86  lea     rcx, [rsp+168h+var_130]; this
0x18002eb8b  call    ?Retrieve@MareApplication@Inventory@Compat@Windows@@UEAAKPEAVInventoryCacheItem@234@@Z; Windows::Compat::Inventory::MareApplication::Retrieve(Windows::Compat::Inventory::InventoryCacheItem *)
0x18002eb90  lea     r14, [rsi+48h]
0x18002eb94  lea     rax, [rsp+168h+var_E8]
0x18002eb9c  cmp     r14, rax
0x18002eb9f  jz      short loc_18002EBCE
0x18002eba1  mov     rdx, [rsp+168h+var_E8]
0x18002eba9  mov     r8, [rsp+168h+var_E0]
0x18002ebb1  sub     r8, rdx
0x18002ebb4  sar     r8, 3
0x18002ebb8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002ebc2  imul    r8, rax
0x18002ebc6  mov     rcx, r14
0x18002ebc9  call    ??$_Assign_counted_range@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AppState@MareApplication@Inventory@Compat@Windows@@@std@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AppState@MareApplication@Inventory@Compat@Windows@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AppState@MareApplication@Inventory@Compat@Windows@@@std@@@2@@std@@AEAAXPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AppState@MareApplication@Inventory@Compat@Windows@@@1@_K@Z; std::vector<std::pair<std::wstring,Windows::Compat::Inventory::MareApplication::AppState>>::_Assign_counted_range<std::pair<std::wstring,Windows::Compat::Inventory::MareApplication::AppState> *>(std::pair<std::wstring,Windows::Compat::Inventory::MareApplication::AppState> *,unsigned __int64)
0x18002ebce  lea     rcx, [rsi-8]; this
0x18002ebd2  call    ?GetJsonHash@MareApplication@Inventory@Compat@Windows@@QEAA_KXZ; Windows::Compat::Inventory::MareApplication::GetJsonHash(void)
0x18002ebd7  cmp     [rsp+168h+var_30], rax
0x18002ebdf  setz    bpl
0x18002ebe3  cmp     qword ptr [rdi+18h], 7
0x18002ebe8  jbe     short loc_18002EBEF
0x18002ebea  mov     rax, [rdi]
0x18002ebed  jmp     short loc_18002EBF2
0x18002ebef  mov     rax, rdi
0x18002ebf2  mov     [rsp+168h+var_148], rax
0x18002ebf7  lea     r9, aAppLs; "App: %ls"
0x18002ebfe  mov     r8d, 231h
0x18002ec04  lea     rdx, aWindowsCompatI_18; "Windows::Compat::Inventory::MareApplica"...
0x18002ec0b  mov     ecx, 3
0x18002ec10  call    AslLogCallPrintf
0x18002ec15  lea     rcx, [rsi-8]; this
0x18002ec19  call    ?GetJsonHash@MareApplication@Inventory@Compat@Windows@@QEAA_KXZ; Windows::Compat::Inventory::MareApplication::GetJsonHash(void)
0x18002ec1e  mov     rcx, [rsp+168h+var_30]
0x18002ec26  mov     [rsp+168h+var_140], rcx
0x18002ec2b  mov     [rsp+168h+var_148], rax
0x18002ec30  lea     r9, aJsonhashThisZu; "JsonHash this:%zu other:%zu"
0x18002ec37  mov     r8d, 232h
0x18002ec3d  lea     rdx, aWindowsCompatI_18; "Windows::Compat::Inventory::MareApplica"...
0x18002ec44  mov     ecx, 3
0x18002ec49  call    AslLogCallPrintf
0x18002ec4e  mov     rbx, [rsp+168h+var_E8]
0x18002ec56  cmp     rbx, [rsp+168h+var_E0]
0x18002ec5e  jz      short loc_18002ECD0
0x18002ec60  mov     ecx, [rbx+20h]
0x18002ec63  cmp     ecx, 1
0x18002ec66  jnz     short loc_18002EC71
0x18002ec68  lea     rax, aUpdated; "updated"
0x18002ec6f  jmp     short loc_18002EC93
0x18002ec71  test    ecx, ecx
0x18002ec73  jnz     short loc_18002EC7E
0x18002ec75  lea     rax, aInstalled; "installed"
0x18002ec7c  jmp     short loc_18002EC93
0x18002ec7e  lea     rax, aBackedup; "backedUp"
0x18002ec85  lea     rdx, aInvalid_0; "INVALID"
0x18002ec8c  cmp     ecx, 2
0x18002ec8f  cmovnz  rax, rdx
0x18002ec93  cmp     qword ptr [rbx+18h], 7
0x18002ec98  jbe     short loc_18002EC9F
0x18002ec9a  mov     rcx, [rbx]
0x18002ec9d  jmp     short loc_18002ECA2
0x18002ec9f  mov     rcx, rbx
0x18002eca2  mov     [rsp+168h+var_140], rax
0x18002eca7  mov     [rsp+168h+var_148], rcx
0x18002ecac  lea     r9, aSidLsAppstateL; "SID:%ls AppState:%ls"
0x18002ecb3  mov     r8d, 238h
0x18002ecb9  lea     rdx, aWindowsCompatI_18; "Windows::Compat::Inventory::MareApplica"...
0x18002ecc0  mov     ecx, 3
0x18002ecc5  call    AslLogCallPrintf
0x18002ecca  add     rbx, 28h ; '('
0x18002ecce  jmp     short loc_18002EC56
0x18002ecd0  test    bpl, bpl
0x18002ecd3  jnz     short loc_18002ED37
0x18002ecd5  mov     rbx, [r14]
0x18002ecd8  cmp     rbx, [rsi+50h]
0x18002ecdc  jz      short loc_18002ED37
0x18002ecde  cmp     dword ptr [rbx+20h], 2
0x18002ece2  jnz     short loc_18002ED31
0x18002ece4  cmp     qword ptr [rbx+18h], 7
0x18002ece9  jbe     short loc_18002ECF0
0x18002eceb  mov     rcx, [rbx]
0x18002ecee  jmp     short loc_18002ECF3
0x18002ecf0  mov     rcx, rbx
0x18002ecf3  cmp     qword ptr [rsi+40h], 7
0x18002ecf8  jbe     short loc_18002ECFF
0x18002ecfa  mov     rax, [rdi]
0x18002ecfd  jmp     short loc_18002ED02
0x18002ecff  mov     rax, rdi
0x18002ed02  mov     [rsp+168h+var_140], rcx
0x18002ed07  mov     [rsp+168h+var_148], rax
0x18002ed0c  lea     r9, aLsUpdatedForLs; "%ls updated for %ls"
0x18002ed13  mov     r8d, 244h
0x18002ed19  lea     rdx, aWindowsCompatI_18; "Windows::Compat::Inventory::MareApplica"...
0x18002ed20  mov     ecx, 3
0x18002ed25  call    AslLogCallPrintf
0x18002ed2a  mov     dword ptr [rbx+20h], 1
0x18002ed31  add     rbx, 28h ; '('
0x18002ed35  jmp     short loc_18002ECD8
0x18002ed37  lea     rcx, [rsp+168h+var_138]; this
0x18002ed3c  call    ??1MareApplication@Inventory@Compat@Windows@@UEAA@XZ; Windows::Compat::Inventory::MareApplication::~MareApplication(void)
0x18002ed41  mov     al, bpl
0x18002ed44  mov     rcx, [rsp+168h+var_28]
0x18002ed4c  xor     rcx, rsp; StackCookie
0x18002ed4f  call    __security_check_cookie
0x18002ed54  lea     r11, [rsp+168h+var_18]
0x18002ed5c  mov     rbx, [r11+30h]
0x18002ed60  mov     rbp, [r11+38h]
0x18002ed64  mov     rsp, r11
0x18002ed67  pop     r14
0x18002ed69  pop     rdi
0x18002ed6a  pop     rsi
0x18002ed6b  retn
```
