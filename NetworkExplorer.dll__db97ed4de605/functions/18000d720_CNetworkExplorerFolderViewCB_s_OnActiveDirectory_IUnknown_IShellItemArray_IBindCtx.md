# CNetworkExplorerFolderViewCB::s_OnActiveDirectory(IUnknown *,IShellItemArray *,IBindCtx *)

- ea: `0x18000d720`
- end: `0x18000d77d`
- name: `?s_OnActiveDirectory@CNetworkExplorerFolderViewCB@@SAJPEAUIUnknown@@PEAUIShellItemArray@@PEAUIBindCtx@@@Z`
- size: `93`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IShellItemArray *, struct IBindCtx *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000f076`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x18000d764`
- `SHELL32!ShellExecuteExW` at `0x18000d764`

## string_xrefs

- `0x18000d73f`: `rundll32.exe`
- `0x18000d758`: `dsquery.dll,OpenQueryWindow`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolderViewCB::s_OnActiveDirectory(
        struct IUnknown *a1,
        struct IShellItemArray *a2,
        struct IBindCtx *a3)
{
  SHELLEXECUTEINFOW pExecInfo; // [rsp+20h] [rbp-78h] BYREF

  pExecInfo.cbSize = 112;
  memset_0(&pExecInfo.fMask, 0, 0x6Cu);
  pExecInfo.nShow = 1;
  pExecInfo.lpFile = L"rundll32.exe";
  pExecInfo.lpParameters = L"dsquery.dll,OpenQueryWindow";
  return !ShellExecuteExW(&pExecInfo) ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x18000d720  sub     rsp, 98h
0x18000d727  xor     edx, edx; Val
0x18000d729  mov     [rsp+98h+pExecInfo.cbSize], 70h ; 'p'
0x18000d731  lea     rcx, [rsp+98h+pExecInfo.fMask]; void *
0x18000d736  lea     r8d, [rdx+6Ch]; Size
0x18000d73a  call    memset_0
0x18000d73f  lea     rax, aRundll32Exe; "rundll32.exe"
0x18000d746  mov     [rsp+98h+pExecInfo.nShow], 1
0x18000d74e  mov     [rsp+98h+pExecInfo.lpFile], rax
0x18000d753  lea     rcx, [rsp+98h+pExecInfo]; pExecInfo
0x18000d758  lea     rax, aDsqueryDllOpen; "dsquery.dll,OpenQueryWindow"
0x18000d75f  mov     [rsp+98h+pExecInfo.lpParameters], rax
0x18000d764  call    cs:__imp_ShellExecuteExW
0x18000d76a  neg     eax
0x18000d76c  sbb     eax, eax
0x18000d76e  not     eax
0x18000d770  and     eax, 80004005h
0x18000d775  add     rsp, 98h
0x18000d77c  retn
```
