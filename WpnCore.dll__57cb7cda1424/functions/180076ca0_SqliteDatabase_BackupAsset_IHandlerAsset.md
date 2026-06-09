# SqliteDatabase::BackupAsset(IHandlerAsset *)

- ea: `0x180076ca0`
- end: `0x180076f1b`
- name: `?BackupAsset@SqliteDatabase@@AEAAXPEAUIHandlerAsset@@@Z`
- size: `635`
- prototype: `void __fastcall(SqliteDatabase *__hidden this, struct IHandlerAsset *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180047938`
- `0x180076a20`

## callees

- `0x18000e5f4`
- `0x180076ca0`
- `0x180076f24`
- `0x180082b28`
- `0x1800852dc`
- `0x1800f2460`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076d23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076d79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076ec8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076ee7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076f06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076d23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076d79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076ec8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076ee7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076f06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076e28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076ea3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076eb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076e28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076ea3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076eb7`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180076de5`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180076e58`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180076de5`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180076e58`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall SqliteDatabase::BackupAsset(LPCWSTR *this, struct IHandlerAsset *a2)
{
  int v4; // eax
  __int64 (__fastcall *v5)(struct IHandlerAsset *, LPVOID *); // rdi
  int v6; // eax
  __int64 (__fastcall *v7)(struct IHandlerAsset *, unsigned __int16 **); // rdi
  int v8; // eax
  unsigned int v9; // eax
  HKEY v10; // rbx
  unsigned int v11; // eax
  const char *v12; // r9
  unsigned __int16 *v13; // [rsp+20h] [rbp-78h] BYREF
  __int64 v14; // [rsp+28h] [rbp-70h]
  __int64 v15; // [rsp+30h] [rbp-68h]
  LPVOID pv; // [rsp+38h] [rbp-60h] BYREF
  __int64 v17; // [rsp+40h] [rbp-58h]
  __int64 v18; // [rsp+48h] [rbp-50h]
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-48h]
  __int64 v20; // [rsp+58h] [rbp-40h]
  __int64 v21; // [rsp+60h] [rbp-38h]
  SqliteDatabase *retaddr; // [rsp+98h] [rbp+0h]
  HKEY hKey; // [rsp+A8h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+B0h] [rbp+18h] BYREF
  char v25; // [rsp+B8h] [rbp+20h] BYREF

  lpSubKey = 0;
  pv = 0;
  v17 = 0;
  v18 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v20 = -1;
  v21 = -1;
  try
  {
    v4 = (*(__int64 (**)(void))(*(_QWORD *)a2 + 40LL))();
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE64,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v4,
        (int)v13);
    v5 = *(__int64 (__fastcall **)(struct IHandlerAsset *, LPVOID *))(*(_QWORD *)a2 + 24LL);
    v17 = -1;
    v18 = -1;
    v6 = v5(a2, &pv);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE65,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v6,
        (int)v13);
    v7 = *(__int64 (__fastcall **)(struct IHandlerAsset *, unsigned __int16 **))(*(_QWORD *)a2 + 32LL);
    v14 = -1;
    v15 = -1;
    v8 = v7(a2, &v13);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE66,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v8,
        (int)v13);
    hKey = 0;
    phkResult = 0;
    v9 = RegCreateKeyW(HKEY_CURRENT_USER, this[16], &phkResult);
    if ( v9 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xE6A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)v9,
        (unsigned int)v13);
    v10 = hKey;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v25);
      RegCloseKey(v10);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v25);
    }
    hKey = 0;
    v11 = RegCreateKeyW(phkResult, lpSubKey, &hKey);
    if ( v11 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xE6B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)v11,
        (unsigned int)v13);
    SqliteDatabase::WriteRegString(retaddr, hKey, (const unsigned __int16 *)pv, v13);
    if ( hKey )
      RegCloseKey(hKey);
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( v13 )
    {
      CoTaskMemFree(v13);
      v13 = 0;
    }
    v14 = 0;
    v15 = 0;
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v17 = 0;
    v18 = 0;
    if ( lpSubKey )
      CoTaskMemFree((LPVOID)lpSubKey);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xE6F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      v12);
  }
}

```

## disassembly

```asm
0x180076ca0  mov     r11, rsp
0x180076ca3  push    rbx
0x180076ca4  push    rsi
0x180076ca5  push    rdi
0x180076ca6  push    r14
0x180076ca8  push    r15
0x180076caa  sub     rsp, 70h
0x180076cae  mov     rbx, rdx
0x180076cb1  mov     rsi, rcx
0x180076cb4  xor     r14d, r14d
0x180076cb7  mov     [r11-48h], r14
0x180076cbb  mov     [r11-60h], r14
0x180076cbf  mov     [r11-58h], r14
0x180076cc3  mov     [r11-50h], r14
0x180076cc7  mov     [r11-78h], r14
0x180076ccb  mov     [r11-70h], r14
0x180076ccf  mov     [r11-68h], r14
0x180076cd3  or      r15, 0FFFFFFFFFFFFFFFFh
0x180076cd7  mov     [r11-40h], r15
0x180076cdb  mov     [r11-38h], r15
0x180076cdf  mov     rax, [rdx]
0x180076ce2  lea     rdx, [r11-48h]
0x180076ce6  mov     rcx, rbx
0x180076ce9  mov     rax, [rax+28h]
0x180076ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076cf2  mov     rcx, [rsp+98h]; this
0x180076cfa  test    eax, eax
0x180076cfc  jns     short loc_180076D12
0x180076cfe  mov     r9d, eax; char *
0x180076d01  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180076d08  mov     edx, 0E64h; void *
0x180076d0d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180076d12  mov     rax, [rbx]
0x180076d15  mov     rdi, [rax+18h]
0x180076d19  mov     rcx, [rsp+98h+pv]; pv
0x180076d1e  test    rcx, rcx
0x180076d21  jz      short loc_180076D2E
0x180076d23  call    cs:__imp_CoTaskMemFree
0x180076d29  mov     [rsp+98h+pv], r14
0x180076d2e  mov     [rsp+98h+var_58], r15
0x180076d33  mov     [rsp+98h+var_50], r15
0x180076d38  lea     rdx, [rsp+98h+pv]
0x180076d3d  mov     rcx, rbx
0x180076d40  mov     rax, rdi
0x180076d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d48  mov     rcx, [rsp+98h]; this
0x180076d50  test    eax, eax
0x180076d52  jns     short loc_180076D68
0x180076d54  mov     r9d, eax; char *
0x180076d57  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180076d5e  mov     edx, 0E65h; void *
0x180076d63  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180076d68  mov     rax, [rbx]
0x180076d6b  mov     rdi, [rax+20h]
0x180076d6f  mov     rcx, [rsp+98h+var_78]; pv
0x180076d74  test    rcx, rcx
0x180076d77  jz      short loc_180076D84
0x180076d79  call    cs:__imp_CoTaskMemFree
0x180076d7f  mov     [rsp+98h+var_78], r14; unsigned int
0x180076d84  mov     [rsp+98h+var_70], r15
0x180076d89  mov     [rsp+98h+var_68], r15
0x180076d8e  lea     rdx, [rsp+98h+var_78]
0x180076d93  mov     rcx, rbx
0x180076d96  mov     rax, rdi
0x180076d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d9e  mov     rcx, [rsp+98h]; this
0x180076da6  test    eax, eax
0x180076da8  jns     short loc_180076DBF
0x180076daa  mov     r9d, eax; char *
0x180076dad  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180076db4  mov     edx, 0E66h; void *
0x180076db9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180076dbf  mov     [rsp+98h+hKey], r14
0x180076dc7  mov     [rsp+98h+phkResult], r14
0x180076dcf  lea     r8, [rsp+98h+phkResult]; phkResult
0x180076dd7  mov     rdx, [rsi+80h]; lpSubKey
0x180076dde  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180076de5  call    cs:__imp_RegCreateKeyW
0x180076deb  mov     rcx, [rsp+98h]; this
0x180076df3  test    eax, eax
0x180076df5  jz      short loc_180076E0B
0x180076df7  mov     r9d, eax; char *
0x180076dfa  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180076e01  mov     edx, 0E6Ah; void *
0x180076e06  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180076e0b  mov     rbx, [rsp+98h+hKey]
0x180076e13  test    rbx, rbx
0x180076e16  jz      short loc_180076E3B
0x180076e18  lea     rcx, [rsp+98h+arg_18]; this
0x180076e20  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180076e25  mov     rcx, rbx; hKey
0x180076e28  call    cs:__imp_RegCloseKey
0x180076e2e  lea     rcx, [rsp+98h+arg_18]; this
0x180076e36  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180076e3b  mov     [rsp+98h+hKey], r14
0x180076e43  lea     r8, [rsp+98h+hKey]; phkResult
0x180076e4b  mov     rdx, [rsp+98h+lpSubKey]; lpSubKey
0x180076e50  mov     rcx, [rsp+98h+phkResult]; hKey
0x180076e58  call    cs:__imp_RegCreateKeyW
0x180076e5e  mov     rcx, [rsp+98h]; this
0x180076e66  test    eax, eax
0x180076e68  jz      short loc_180076E7E
0x180076e6a  mov     r9d, eax; char *
0x180076e6d  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180076e74  mov     edx, 0E6Bh; void *
0x180076e79  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180076e7e  mov     r9, [rsp+98h+var_78]; unsigned __int16 *
0x180076e83  mov     r8, [rsp+98h+pv]; unsigned __int16 *
0x180076e88  mov     rdx, [rsp+98h+hKey]; HKEY
0x180076e90  call    ?WriteRegString@SqliteDatabase@@AEAAXPEAUHKEY__@@PEBG1@Z; SqliteDatabase::WriteRegString(HKEY__ *,ushort const *,ushort const *)
0x180076e95  nop
0x180076e96  mov     rcx, [rsp+98h+hKey]; hKey
0x180076e9e  test    rcx, rcx
0x180076ea1  jz      short loc_180076EAA
0x180076ea3  call    cs:__imp_RegCloseKey
0x180076ea9  nop
0x180076eaa  mov     rcx, [rsp+98h+phkResult]; hKey
0x180076eb2  test    rcx, rcx
0x180076eb5  jz      short loc_180076EBE
0x180076eb7  call    cs:__imp_RegCloseKey
0x180076ebd  nop
0x180076ebe  mov     rcx, [rsp+98h+var_78]; pv
0x180076ec3  test    rcx, rcx
0x180076ec6  jz      short loc_180076ED3
0x180076ec8  call    cs:__imp_CoTaskMemFree
0x180076ece  mov     [rsp+98h+var_78], r14
0x180076ed3  mov     [rsp+98h+var_70], r14
0x180076ed8  mov     [rsp+98h+var_68], r14
0x180076edd  mov     rcx, [rsp+98h+pv]; pv
0x180076ee2  test    rcx, rcx
0x180076ee5  jz      short loc_180076EF2
0x180076ee7  call    cs:__imp_CoTaskMemFree
0x180076eed  mov     [rsp+98h+pv], r14
0x180076ef2  mov     [rsp+98h+var_58], r14
0x180076ef7  mov     [rsp+98h+var_50], r14
0x180076efc  mov     rcx, [rsp+98h+lpSubKey]; pv
0x180076f01  test    rcx, rcx
0x180076f04  jz      short loc_180076F0D
0x180076f06  call    cs:__imp_CoTaskMemFree
0x180076f0c  nop
0x180076f0d  jmp     short $+2
0x180076f0f  add     rsp, 70h
0x180076f13  pop     r15
0x180076f15  pop     r14
0x180076f17  pop     rdi
0x180076f18  pop     rsi
0x180076f19  pop     rbx
0x180076f1a  retn
```
