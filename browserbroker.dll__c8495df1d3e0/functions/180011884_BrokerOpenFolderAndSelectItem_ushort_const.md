# BrokerOpenFolderAndSelectItem(ushort const *)

- ea: `0x180011884`
- end: `0x1800119b7`
- name: `?BrokerOpenFolderAndSelectItem@@YAJPEBG@Z`
- size: `307`
- prototype: `__int64 __fastcall(PCWSTR pszName)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b240`

## callees

- `0x1800037ac`
- `0x180011884`
- `0x180013278`

## import_xrefs

- `api-ms-win-security-isolatedcontainer-l1-1-0!IsProcessInIsolatedContainer` at `0x1800118a9`
- `api-ms-win-security-isolatedcontainer-l1-1-0!IsProcessInIsolatedContainer` at `0x1800118a9`
- `ext-ms-win-shell32-shellfolders-l1-2-1!SHOpenFolderAndSelectItems` at `0x180011985`
- `ext-ms-win-shell32-shellfolders-l1-2-1!SHOpenFolderAndSelectItems` at `0x180011985`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x180011968`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x180011968`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180011990`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001199a`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180011990`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001199a`
- `api-ms-win-shell-namespace-l1-1-0!ILRemoveLastID` at `0x180011936`
- `api-ms-win-shell-namespace-l1-1-0!ILRemoveLastID` at `0x180011936`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x1800118f4`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x1800118f4`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x18001190d`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x18001190d`
- `IsolatedWindowsEnvironmentUtils!__imp_?OpenContainerDownloadsFolderOnHost@@YAJXZ` at `0x1800118c7`
- `IsolatedWindowsEnvironmentUtils!__imp_?OpenContainerDownloadsFolderOnHost@@YAJXZ` at `0x1800118c7`

## pseudocode

```c
__int64 __fastcall BrokerOpenFolderAndSelectItem(PCWSTR pszName)
{
  __int64 v2; // rdx
  HRESULT v3; // ebx
  ITEMIDLIST *v4; // rdi
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-19h] BYREF
  BOOL isProcessInIsolatedContainer; // [rsp+B8h] [rbp+6Fh] BYREF
  LPITEMIDLIST ppidl; // [rsp+C0h] [rbp+77h] BYREF

  isProcessInIsolatedContainer = 0;
  if ( IsProcessInIsolatedContainer(&isProcessInIsolatedContainer) < 0
    || !isProcessInIsolatedContainer
    || (LOBYTE(v2) = 1,
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_ApplicationGuardDownloadToHost>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_ApplicationGuardDownloadToHost>::GetImpl'::`2'::impl,
          v2),
        v3 = OpenContainerDownloadsFolderOnHost(),
        v3 < 0) )
  {
    ppidl = 0;
    v3 = SHParseDisplayName(pszName, 0, &ppidl, 0, 0);
    if ( v3 >= 0 )
    {
      if ( ppidl )
      {
        v4 = ILClone(ppidl);
        v3 = v4 == 0 ? 0x8007000E : 0;
      }
      else
      {
        v4 = 0;
        v3 = -2147024809;
      }
      if ( v3 >= 0 )
      {
        ILRemoveLastID(v4);
        pExecInfo.cbSize = 112;
        memset_0(&pExecInfo.fMask, 0, 0x6Cu);
        pExecInfo.lpIDList = v4;
        pExecInfo.fMask = 67109124;
        pExecInfo.nShow = 1;
        if ( ShellExecuteExW(&pExecInfo) )
          v3 = SHOpenFolderAndSelectItems(ppidl, 0, 0, 0);
        else
          v3 = -2147467259;
        ILFree(v4);
      }
      ILFree(ppidl);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180011884  mov     [rsp-8+arg_0], rbx
0x180011889  mov     [rsp-8+arg_18], rdi
0x18001188e  push    rbp
0x18001188f  lea     rbp, [rsp-57h]
0x180011894  sub     rsp, 0A0h
0x18001189b  mov     rdi, rcx
0x18001189e  mov     [rbp+57h+isProcessInIsolatedContainer], 0
0x1800118a5  lea     rcx, [rbp+57h+isProcessInIsolatedContainer]; isProcessInIsolatedContainer
0x1800118a9  call    cs:__imp_IsProcessInIsolatedContainer
0x1800118af  test    eax, eax
0x1800118b1  js      short loc_1800118D7
0x1800118b3  cmp     [rbp+57h+isProcessInIsolatedContainer], 0
0x1800118b7  jz      short loc_1800118D7
0x1800118b9  mov     dl, 1
0x1800118bb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ApplicationGuardDownloadToHost@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ApplicationGuardDownloadToHost@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ApplicationGuardDownloadToHost> `wil::Feature<__WilFeatureTraits_Feature_ApplicationGuardDownloadToHost>::GetImpl(void)'::`2'::impl
0x1800118c2  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ApplicationGuardDownloadToHost@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ApplicationGuardDownloadToHost>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800118c7  call    cs:__imp_?OpenContainerDownloadsFolderOnHost@@YAJXZ; OpenContainerDownloadsFolderOnHost(void)
0x1800118cd  mov     ebx, eax
0x1800118cf  test    eax, eax
0x1800118d1  jns     loc_1800119A0
0x1800118d7  xor     r9d, r9d; sfgaoIn
0x1800118da  mov     [rbp+57h+ppidl], 0
0x1800118e2  lea     r8, [rbp+57h+ppidl]; ppidl
0x1800118e6  mov     [rsp+0A0h+psfgaoOut], 0; psfgaoOut
0x1800118ef  xor     edx, edx; pbc
0x1800118f1  mov     rcx, rdi; pszName
0x1800118f4  call    cs:__imp_SHParseDisplayName
0x1800118fa  mov     ebx, eax
0x1800118fc  test    eax, eax
0x1800118fe  js      loc_1800119A0
0x180011904  mov     rcx, [rbp+57h+ppidl]; pidl
0x180011908  test    rcx, rcx
0x18001190b  jz      short loc_180011928
0x18001190d  call    cs:__imp_ILClone
0x180011913  mov     rcx, rax
0x180011916  mov     rdi, rax
0x180011919  neg     rcx
0x18001191c  sbb     ebx, ebx
0x18001191e  not     ebx
0x180011920  and     ebx, 8007000Eh
0x180011926  jmp     short loc_18001192F
0x180011928  xor     edi, edi
0x18001192a  mov     ebx, 80070057h
0x18001192f  test    ebx, ebx
0x180011931  js      short loc_180011996
0x180011933  mov     rcx, rdi; pidl
0x180011936  call    cs:__imp_ILRemoveLastID
0x18001193c  xor     edx, edx; Val
0x18001193e  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x180011945  lea     rcx, [rbp+57h+pExecInfo.fMask]; void *
0x180011949  lea     r8d, [rdx+6Ch]; Size
0x18001194d  call    memset_0
0x180011952  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x180011956  mov     [rbp+57h+pExecInfo.lpIDList], rdi
0x18001195a  mov     [rbp+57h+pExecInfo.fMask], 4000104h
0x180011961  mov     [rbp+57h+pExecInfo.nShow], 1
0x180011968  call    cs:__imp_ShellExecuteExW
0x18001196e  test    eax, eax
0x180011970  jnz     short loc_180011979
0x180011972  mov     ebx, 80004005h
0x180011977  jmp     short loc_18001198D
0x180011979  mov     rcx, [rbp+57h+ppidl]; pidlFolder
0x18001197d  xor     r9d, r9d; dwFlags
0x180011980  xor     r8d, r8d; apidl
0x180011983  xor     edx, edx; cidl
0x180011985  call    cs:__imp_SHOpenFolderAndSelectItems
0x18001198b  mov     ebx, eax
0x18001198d  mov     rcx, rdi; pidl
0x180011990  call    cs:__imp_ILFree
0x180011996  mov     rcx, [rbp+57h+ppidl]; pidl
0x18001199a  call    cs:__imp_ILFree
0x1800119a0  lea     r11, [rsp+0A0h+var_s0]
0x1800119a8  mov     eax, ebx
0x1800119aa  mov     rbx, [r11+10h]
0x1800119ae  mov     rdi, [r11+28h]
0x1800119b2  mov     rsp, r11
0x1800119b5  pop     rbp
0x1800119b6  retn
```
