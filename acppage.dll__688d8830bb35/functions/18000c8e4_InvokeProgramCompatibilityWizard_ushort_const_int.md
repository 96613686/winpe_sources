# InvokeProgramCompatibilityWizard(ushort const *,int)

- ea: `0x18000c8e4`
- end: `0x18000c9fd`
- name: `?InvokeProgramCompatibilityWizard@@YAJPEBGH@Z`
- size: `281`
- prototype: `HRESULT __fastcall(PCWSTR pszUrl)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009650`
- `0x18000cb60`

## callees

- `0x180008878`
- `0x18000c8e4`
- `0x18001623a`
- `0x180016280`

## import_xrefs

- `SHLWAPI!UrlEscapeW` at `0x18000c95c`
- `SHLWAPI!UrlEscapeW` at `0x18000c95c`
- `SHELL32!ShellExecuteExW` at `0x18000c9d5`
- `SHELL32!ShellExecuteExW` at `0x18000c9d5`

## string_xrefs

- `0x18000c96b`: `ms-contact-support://compattroubleshooter/InvocationContextMenu/?Product=Windows&dialog_ExePath=`

## pseudocode

```c
HRESULT __fastcall InvokeProgramCompatibilityWizard(PCWSTR pszUrl)
{
  HRESULT result; // eax
  DWORD pcchEscaped[8]; // [rsp+20h] [rbp-E0h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszEscaped[360]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t pszDest[464]; // [rsp+380h] [rbp+280h] BYREF

  memset_0(pszEscaped, 0, sizeof(pszEscaped));
  pcchEscaped[0] = 359;
  memset_0(pszDest, 0, 0x398u);
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  result = UrlEscapeW(pszUrl, pszEscaped, pcchEscaped, 0x2000u);
  if ( result >= 0 )
  {
    result = StringCchCatW(
               pszDest,
               0x1CCu,
               L"ms-contact-support://compattroubleshooter/InvocationContextMenu/?Product=Windows&dialog_ExePath=");
    if ( result >= 0 )
    {
      result = StringCchCatW(pszDest, 0x1CCu, pszEscaped);
      if ( result >= 0 )
      {
        pExecInfo.cbSize = 112;
        pExecInfo.lpFile = pszDest;
        pExecInfo.fMask = 1024;
        pExecInfo.lpDirectory = 0;
        pExecInfo.lpParameters = 0;
        pExecInfo.nShow = 1;
        ShellExecuteExW(&pExecInfo);
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c8e4  mov     [rsp-8+arg_8], rbx
0x18000c8e9  push    rbp
0x18000c8ea  lea     rbp, [rsp-630h]
0x18000c8f2  sub     rsp, 730h
0x18000c8f9  mov     rax, cs:__security_cookie
0x18000c900  xor     rax, rsp
0x18000c903  mov     [rbp+630h+var_10], rax
0x18000c90a  mov     rbx, rcx
0x18000c90d  xor     edx, edx; Val
0x18000c90f  lea     rcx, [rbp+630h+pszEscaped]; void *
0x18000c913  mov     r8d, 2D0h; Size
0x18000c919  call    memset_0
0x18000c91e  xor     edx, edx; Val
0x18000c920  mov     [rsp+730h+pcchEscaped], 167h
0x18000c928  mov     r8d, 398h; Size
0x18000c92e  lea     rcx, [rbp+630h+pszDest]; void *
0x18000c935  call    memset_0
0x18000c93a  xor     edx, edx; Val
0x18000c93c  lea     rcx, [rsp+730h+pExecInfo]; void *
0x18000c941  lea     r8d, [rdx+70h]; Size
0x18000c945  call    memset_0
0x18000c94a  mov     r9d, 2000h; dwFlags
0x18000c950  lea     r8, [rsp+730h+pcchEscaped]; pcchEscaped
0x18000c955  lea     rdx, [rbp+630h+pszEscaped]; pszEscaped
0x18000c959  mov     rcx, rbx; pszUrl
0x18000c95c  call    cs:__imp_UrlEscapeW
0x18000c962  test    eax, eax
0x18000c964  js      short loc_18000C9DD
0x18000c966  mov     ebx, 1CCh
0x18000c96b  lea     r8, aMsContactSuppo; "ms-contact-support://compattroubleshoot"...
0x18000c972  mov     edx, ebx; cchDest
0x18000c974  lea     rcx, [rbp+630h+pszDest]; pszDest
0x18000c97b  call    StringCchCatW
0x18000c980  test    eax, eax
0x18000c982  js      short loc_18000C9DD
0x18000c984  lea     r8, [rbp+630h+pszEscaped]; pszSrc
0x18000c988  mov     edx, ebx; cchDest
0x18000c98a  lea     rcx, [rbp+630h+pszDest]; pszDest
0x18000c991  call    StringCchCatW
0x18000c996  test    eax, eax
0x18000c998  js      short loc_18000C9DD
0x18000c99a  lea     rax, [rbp+630h+pszDest]
0x18000c9a1  mov     [rsp+730h+pExecInfo.cbSize], 70h ; 'p'
0x18000c9a9  lea     rcx, [rsp+730h+pExecInfo]; pExecInfo
0x18000c9ae  mov     [rsp+730h+pExecInfo.lpFile], rax
0x18000c9b3  mov     [rsp+730h+pExecInfo.fMask], 400h
0x18000c9bb  mov     [rsp+730h+pExecInfo.lpDirectory], 0
0x18000c9c4  mov     [rsp+730h+pExecInfo.lpParameters], 0
0x18000c9cd  mov     [rsp+730h+pExecInfo.nShow], 1
0x18000c9d5  call    cs:__imp_ShellExecuteExW
0x18000c9db  xor     eax, eax
0x18000c9dd  mov     rcx, [rbp+630h+var_10]
0x18000c9e4  xor     rcx, rsp; StackCookie
0x18000c9e7  call    __security_check_cookie
0x18000c9ec  mov     rbx, [rsp+730h+arg_8]
0x18000c9f4  add     rsp, 730h
0x18000c9fb  pop     rbp
0x18000c9fc  retn
```
