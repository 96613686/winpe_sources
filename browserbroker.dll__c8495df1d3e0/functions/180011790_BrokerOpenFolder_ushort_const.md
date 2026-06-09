# BrokerOpenFolder(ushort const *)

- ea: `0x180011790`
- end: `0x18001187e`
- name: `?BrokerOpenFolder@@YAJPEBG@Z`
- size: `238`
- prototype: `__int64 __fastcall(PCWSTR pszName)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b200`

## callees

- `0x1800037ac`
- `0x180011790`
- `0x180013278`

## import_xrefs

- `api-ms-win-security-isolatedcontainer-l1-1-0!IsProcessInIsolatedContainer` at `0x1800117ae`
- `api-ms-win-security-isolatedcontainer-l1-1-0!IsProcessInIsolatedContainer` at `0x1800117ae`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x18001184e`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x18001184e`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001186b`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001186b`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x180011803`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x180011803`
- `IsolatedWindowsEnvironmentUtils!__imp_?OpenContainerDownloadsFolderOnHost@@YAJXZ` at `0x1800117cc`
- `IsolatedWindowsEnvironmentUtils!__imp_?OpenContainerDownloadsFolderOnHost@@YAJXZ` at `0x1800117cc`

## pseudocode

```c
__int64 __fastcall BrokerOpenFolder(PCWSTR pszName)
{
  __int64 v2; // rdx
  HRESULT v3; // ebx
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-29h] BYREF
  BOOL isProcessInIsolatedContainer; // [rsp+C8h] [rbp+6Fh] BYREF
  SFGAOF psfgaoOut; // [rsp+D0h] [rbp+77h] BYREF
  LPITEMIDLIST ppidl; // [rsp+D8h] [rbp+7Fh] BYREF

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
    psfgaoOut = 0;
    v3 = SHParseDisplayName(pszName, 0, &ppidl, 0x60400000u, &psfgaoOut);
    if ( v3 >= 0 )
    {
      if ( (psfgaoOut & 0x60400000) == 0x60000000 )
      {
        pExecInfo.cbSize = 112;
        memset_0(&pExecInfo.fMask, 0, 0x6Cu);
        pExecInfo.lpIDList = ppidl;
        pExecInfo.fMask = 67109124;
        pExecInfo.nShow = 1;
        v3 = !ShellExecuteExW(&pExecInfo) ? 0x80004005 : 0;
      }
      else
      {
        v3 = -2147024891;
      }
      ILFree(ppidl);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180011790  push    rbp
0x180011792  push    rbx
0x180011793  push    rdi
0x180011794  lea     rbp, [rsp-47h]
0x180011799  sub     rsp, 0A0h
0x1800117a0  mov     rdi, rcx
0x1800117a3  mov     [rbp+57h+isProcessInIsolatedContainer], 0
0x1800117aa  lea     rcx, [rbp+57h+isProcessInIsolatedContainer]; isProcessInIsolatedContainer
0x1800117ae  call    cs:__imp_IsProcessInIsolatedContainer
0x1800117b4  test    eax, eax
0x1800117b6  js      short loc_1800117DC
0x1800117b8  cmp     [rbp+57h+isProcessInIsolatedContainer], 0
0x1800117bc  jz      short loc_1800117DC
0x1800117be  mov     dl, 1
0x1800117c0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ApplicationGuardDownloadToHost@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ApplicationGuardDownloadToHost@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ApplicationGuardDownloadToHost> `wil::Feature<__WilFeatureTraits_Feature_ApplicationGuardDownloadToHost>::GetImpl(void)'::`2'::impl
0x1800117c7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ApplicationGuardDownloadToHost@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ApplicationGuardDownloadToHost>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800117cc  call    cs:__imp_?OpenContainerDownloadsFolderOnHost@@YAJXZ; OpenContainerDownloadsFolderOnHost(void)
0x1800117d2  mov     ebx, eax
0x1800117d4  test    eax, eax
0x1800117d6  jns     loc_180011871
0x1800117dc  lea     rax, [rbp+57h+arg_10]
0x1800117e0  mov     [rbp+57h+ppidl], 0
0x1800117e8  mov     r9d, 60400000h; sfgaoIn
0x1800117ee  mov     [rsp+0B0h+psfgaoOut], rax; psfgaoOut
0x1800117f3  lea     r8, [rbp+57h+ppidl]; ppidl
0x1800117f7  mov     [rbp+57h+arg_10], 0
0x1800117fe  xor     edx, edx; pbc
0x180011800  mov     rcx, rdi; pszName
0x180011803  call    cs:__imp_SHParseDisplayName
0x180011809  mov     ebx, eax
0x18001180b  test    eax, eax
0x18001180d  js      short loc_180011871
0x18001180f  mov     eax, [rbp+57h+arg_10]
0x180011812  and     eax, 60400000h
0x180011817  cmp     eax, 60000000h
0x18001181c  jnz     short loc_180011862
0x18001181e  xor     edx, edx; Val
0x180011820  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x180011827  lea     rcx, [rbp+57h+pExecInfo.fMask]; void *
0x18001182b  lea     r8d, [rdx+6Ch]; Size
0x18001182f  call    memset_0
0x180011834  mov     rax, [rbp+57h+ppidl]
0x180011838  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x18001183c  mov     [rbp+57h+pExecInfo.lpIDList], rax
0x180011840  mov     [rbp+57h+pExecInfo.fMask], 4000104h
0x180011847  mov     [rbp+57h+pExecInfo.nShow], 1
0x18001184e  call    cs:__imp_ShellExecuteExW
0x180011854  neg     eax
0x180011856  sbb     ebx, ebx
0x180011858  not     ebx
0x18001185a  and     ebx, 80004005h
0x180011860  jmp     short loc_180011867
0x180011862  mov     ebx, 80070005h
0x180011867  mov     rcx, [rbp+57h+ppidl]; pidl
0x18001186b  call    cs:__imp_ILFree
0x180011871  mov     eax, ebx
0x180011873  add     rsp, 0A0h
0x18001187a  pop     rdi
0x18001187b  pop     rbx
0x18001187c  pop     rbp
0x18001187d  retn
```
