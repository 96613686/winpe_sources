# WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ushort const *,bool *,ABI::Windows::Internal::Storage::PathAccessChecks)

- ea: `0x180015d50`
- end: `0x180015dc7`
- name: `?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@SA_NAEAVIdentity@Utilities@3@PEBGPEA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z`
- size: `119`
- prototype: `bool __fastcall(WindowsStorage::Utilities::Identity *, const unsigned __int16 *, bool *, unsigned int)`
- caller_count: `12`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017670`
- `0x1800176f0`
- `0x180017850`
- `0x180017940`
- `0x180017b70`
- `0x180017c60`
- `0x180017f70`
- `0x1800180b0`
- `0x180018440`
- `0x1800188a0`
- `0x180018990`
- `0x180018bb0`

## callees

- `0x180011f20`
- `0x1800139e0`
- `0x180015a3c`
- `0x180015b24`
- `0x180015d50`
- `0x1800160a4`
- `0x180021d6c`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180015d86`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180015d86`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
bool __fastcall WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(
        WindowsStorage::Utilities::Identity *a1,
        const unsigned __int16 *a2,
        bool *a3,
        unsigned int a4)
{
  bool result; // al
  void *v9; // rdx
  unsigned int v10; // r8d
  const char *v11; // r9
  char IsAllowed; // bl
  PCWSTR ppszExt[2]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v14[72]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  result = WindowsStorage::Utilities::Identity::IsFullTrust(a1);
  if ( a3 )
    *a3 = result;
  if ( !result )
  {
    WindowsStorage::Utilities::CanonicalPath::CanonicalPath(ppszExt, a2);
    if ( PathIsRelativeW(a2) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      wil::details::in1diag3::Throw_Win32(retaddr, v9, v10, v11, (unsigned int)ppszExt[0]);
    }
    IsAllowed = WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(
                  (WindowsStorage::Utilities *)ppszExt,
                  (__int64)a1,
                  a4);
    std::vector<unsigned short>::_Tidy(v14);
    return IsAllowed;
  }
  return result;
}

```

## disassembly

```asm
0x180015d50  push    rbx
0x180015d52  push    rbp
0x180015d53  push    rsi
0x180015d54  push    rdi
0x180015d55  sub     rsp, 58h
0x180015d59  mov     ebp, r9d
0x180015d5c  mov     rbx, r8
0x180015d5f  mov     rdi, rdx
0x180015d62  mov     rsi, rcx
0x180015d65  call    ?IsFullTrust@Identity@Utilities@WindowsStorage@@QEAA_NXZ; WindowsStorage::Utilities::Identity::IsFullTrust(void)
0x180015d6a  test    rbx, rbx
0x180015d6d  jz      short loc_180015D71
0x180015d6f  mov     [rbx], al
0x180015d71  test    al, al
0x180015d73  jnz     short loc_180015DBE
0x180015d75  mov     rdx, rdi; unsigned __int16 *
0x180015d78  lea     rcx, [rsp+78h+ppszExt]; ppszExt
0x180015d7d  call    ??0CanonicalPath@Utilities@WindowsStorage@@QEAA@PEBG@Z; WindowsStorage::Utilities::CanonicalPath::CanonicalPath(ushort const *)
0x180015d82  nop
0x180015d83  mov     rcx, rdi; pszPath
0x180015d86  call    cs:__imp_PathIsRelativeW
0x180015d8c  test    eax, eax
0x180015d8e  jz      short loc_180015DA0
0x180015d90  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015d95  mov     rcx, [rsp+78h]; this
0x180015d9a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180015da0  mov     r8d, ebp
0x180015da3  mov     rdx, rsi
0x180015da6  lea     rcx, [rsp+78h+ppszExt]
0x180015dab  call    ?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@QEBA_NAEAVIdentity@Utilities@3@W4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ABI::Windows::Internal::Storage::PathAccessChecks)
0x180015db0  mov     bl, al
0x180015db2  lea     rcx, [rsp+78h+var_48]
0x180015db7  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180015dbc  mov     al, bl
0x180015dbe  add     rsp, 58h
0x180015dc2  pop     rdi
0x180015dc3  pop     rsi
0x180015dc4  pop     rbp
0x180015dc5  pop     rbx
0x180015dc6  retn
```
