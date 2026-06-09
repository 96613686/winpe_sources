# CControlPanelPage::Notify(ushort const *)

- ea: `0x18002c8cc`
- end: `0x18002ca95`
- name: `?Notify@CControlPanelPage@@UEAAJPEBG@Z`
- size: `457`
- prototype: `int(CControlPanelPage *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001c610`

## callees

- `0x18001a6c0`
- `0x18002c8cc`
- `0x18002d220`
- `0x18002e010`

## import_xrefs

- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x18002c9a1`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x18002c9a1`
- `SHLWAPI!__imp_StrCmpCW` at `0x18002c912`
- `SHLWAPI!__imp_StrCmpCW` at `0x18002c912`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002c951`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002ca13`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002c951`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002ca13`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18002c927`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18002c927`
- `SHELL32!SHParseDisplayName` at `0x18002c9eb`
- `SHELL32!SHParseDisplayName` at `0x18002c9eb`
- `SHELL32!__imp_ILFree` at `0x18002ca53`
- `SHELL32!__imp_ILFree` at `0x18002ca53`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18002c977`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18002c977`

## pseudocode

```c
__int64 __fastcall CControlPanelPage::Notify(CControlPanelPage *this, const unsigned __int16 *a2)
{
  HRESULT Str; // ebx
  const CHAR *v4; // rdx
  IUnknown *v5; // rcx
  IUnknown *v6; // rcx
  void *v8; // [rsp+30h] [rbp-D0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+38h] [rbp-C8h] BYREF
  void *ppvOut; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[80]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszName[48]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR value[264]; // [rsp+100h] [rbp+0h] BYREF

  if ( *((_QWORD *)this - 1) )
  {
    Str = 0;
    if ( !StrCmpCW(a2, L"SearchText") && !SHWindowsPolicy(POLID_NoControlPanel, v4) )
    {
      v5 = (IUnknown *)*((_QWORD *)this - 1);
      ppvOut = 0;
      Str = IUnknown_QueryService(v5, &IID_IFrameManager, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppvOut);
      if ( Str >= 0 )
      {
        Str = PSPropertyBag_ReadStr((IPropertyBag *)ppvOut, L"SearchText", value, 260);
        if ( Str >= 0 )
        {
          if ( value[0] )
          {
            Str = SHStringFromGUIDW(&CLSID_ControlPanelCategory, v11, 39);
            if ( Str >= 0 )
            {
              Str = StringCchPrintfW(pszName, 0x29u, L"::%s", v11);
              if ( Str >= 0 )
              {
                ppidl = 0;
                Str = SHParseDisplayName(pszName, 0, &ppidl, 0, 0);
                if ( Str >= 0 )
                {
                  v6 = (IUnknown *)*((_QWORD *)this - 1);
                  v8 = 0;
                  Str = IUnknown_QueryService(
                          v6,
                          (const GUID *const)&SID_STopLevelBrowser,
                          &GUID_000214e2_0000_0000_c000_000000000046,
                          &v8);
                  if ( Str >= 0 )
                  {
                    Str = (*(__int64 (__fastcall **)(void *, LPITEMIDLIST, __int64))(*(_QWORD *)v8 + 88LL))(
                            v8,
                            ppidl,
                            1572865);
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
                  }
                  ILFree(ppidl);
                }
              }
            }
          }
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)Str;
}

```

## disassembly

```asm
0x18002c8cc  mov     [rsp-8+arg_10], rbx
0x18002c8d1  push    rbp
0x18002c8d2  push    rsi
0x18002c8d3  push    rdi
0x18002c8d4  lea     rbp, [rsp-220h]
0x18002c8dc  sub     rsp, 320h
0x18002c8e3  mov     rax, cs:__security_cookie
0x18002c8ea  xor     rax, rsp
0x18002c8ed  mov     [rbp+230h+var_20], rax
0x18002c8f4  xor     esi, esi
0x18002c8f6  mov     rax, rdx
0x18002c8f9  mov     rdi, rcx
0x18002c8fc  cmp     [rcx-8], rsi
0x18002c900  jz      loc_18002CA6C
0x18002c906  lea     rdx, aSearchtext; "SearchText"
0x18002c90d  mov     rcx, rax; pszStr1
0x18002c910  mov     ebx, esi
0x18002c912  call    cs:__imp_StrCmpCW
0x18002c918  test    eax, eax
0x18002c91a  jnz     loc_18002CA71
0x18002c920  lea     rcx, POLID_NoControlPanel; "C"
0x18002c927  call    cs:__imp_SHWindowsPolicy
0x18002c92d  test    eax, eax
0x18002c92f  jnz     loc_18002CA71
0x18002c935  mov     rcx, [rdi-8]; punk
0x18002c939  lea     r9, [rsp+330h+ppvOut]; ppvOut
0x18002c93e  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18002c945  mov     [rsp+330h+ppvOut], rsi
0x18002c94a  lea     rdx, IID_IFrameManager; guidService
0x18002c951  call    cs:__imp_IUnknown_QueryService
0x18002c957  mov     ebx, eax
0x18002c959  test    eax, eax
0x18002c95b  js      loc_18002CA71
0x18002c961  mov     rcx, [rsp+330h+ppvOut]; propBag
0x18002c966  lea     r8, [rbp+230h+value]; value
0x18002c96a  mov     r9d, 104h; characterCount
0x18002c970  lea     rdx, aSearchtext; "SearchText"
0x18002c977  call    cs:__imp_PSPropertyBag_ReadStr
0x18002c97d  mov     ebx, eax
0x18002c97f  test    eax, eax
0x18002c981  js      loc_18002CA59
0x18002c987  cmp     [rbp+230h+value], si
0x18002c98b  jz      loc_18002CA59
0x18002c991  lea     r8d, [rsi+27h]
0x18002c995  lea     rdx, [rsp+330h+var_2E0]
0x18002c99a  lea     rcx, CLSID_ControlPanelCategory
0x18002c9a1  call    cs:__imp_SHStringFromGUIDW
0x18002c9a7  mov     ebx, eax
0x18002c9a9  test    eax, eax
0x18002c9ab  js      loc_18002CA59
0x18002c9b1  lea     r9, [rsp+330h+var_2E0]
0x18002c9b6  lea     r8, aS; "::%s"
0x18002c9bd  lea     edx, [rsi+29h]; unsigned __int64
0x18002c9c0  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x18002c9c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c9c9  mov     ebx, eax
0x18002c9cb  test    eax, eax
0x18002c9cd  js      loc_18002CA59
0x18002c9d3  xor     r9d, r9d; sfgaoIn
0x18002c9d6  mov     [rsp+330h+ppidl], rsi
0x18002c9db  lea     r8, [rsp+330h+ppidl]; ppidl
0x18002c9e0  mov     [rsp+330h+psfgaoOut], rsi; psfgaoOut
0x18002c9e5  xor     edx, edx; pbc
0x18002c9e7  lea     rcx, [rbp+230h+pszName]; pszName
0x18002c9eb  call    cs:__imp_SHParseDisplayName
0x18002c9f1  mov     ebx, eax
0x18002c9f3  test    eax, eax
0x18002c9f5  js      short loc_18002CA59
0x18002c9f7  mov     rcx, [rdi-8]; punk
0x18002c9fb  lea     r9, [rsp+330h+var_300]; ppvOut
0x18002ca00  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18002ca07  mov     [rsp+330h+var_300], rsi
0x18002ca0c  lea     rdx, SID_STopLevelBrowser; guidService
0x18002ca13  call    cs:__imp_IUnknown_QueryService
0x18002ca19  mov     ebx, eax
0x18002ca1b  test    eax, eax
0x18002ca1d  js      short loc_18002CA4E
0x18002ca1f  mov     rcx, [rsp+330h+var_300]
0x18002ca24  mov     r8d, 180001h
0x18002ca2a  mov     rdx, [rsp+330h+ppidl]
0x18002ca2f  mov     rax, [rcx]
0x18002ca32  mov     rax, [rax+58h]
0x18002ca36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca3b  mov     rcx, [rsp+330h+var_300]
0x18002ca40  mov     ebx, eax
0x18002ca42  mov     rax, [rcx]
0x18002ca45  mov     rax, [rax+10h]
0x18002ca49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca4e  mov     rcx, [rsp+330h+ppidl]; pidl
0x18002ca53  call    cs:__imp_ILFree
0x18002ca59  mov     rcx, [rsp+330h+ppvOut]
0x18002ca5e  mov     rax, [rcx]
0x18002ca61  mov     rax, [rax+10h]
0x18002ca65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca6a  jmp     short loc_18002CA71
0x18002ca6c  mov     ebx, 80070057h
0x18002ca71  mov     eax, ebx
0x18002ca73  mov     rcx, [rbp+230h+var_20]
0x18002ca7a  xor     rcx, rsp; StackCookie
0x18002ca7d  call    __security_check_cookie
0x18002ca82  mov     rbx, [rsp+330h+arg_10]
0x18002ca8a  add     rsp, 320h
0x18002ca91  pop     rdi
0x18002ca92  pop     rsi
0x18002ca93  pop     rbp
0x18002ca94  retn
```
