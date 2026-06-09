# UnpublishDriverPackageCatalog

- ea: `0x140014d40`
- end: `0x140014e01`
- name: `UnpublishDriverPackageCatalog`
- size: `193`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140013220`
- `0x14001ae4c`

## callees

- `0x140012ba0`
- `0x140014d40`
- `0x14002ed80`
- `0x140045f30`

## import_xrefs

- `DEVRTL!DevRtlWriteTextLog` at `0x140014db3`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014dd6`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014db3`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014dd6`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140014d69`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140014d69`

## string_xrefs

- `0x140014da3`: `Uninstalled catalog '%ws'.`
- `0x140014dbf`: `Unable to uninstall catalog '%ws'. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall UnpublishDriverPackageCatalog(STRSAFE_PCNZWCH pszSrc)
{
  unsigned int v2; // edi
  __int64 ThreadLogToken; // rsi
  int v4; // eax
  wchar_t pszDest[264]; // [rsp+30h] [rbp-238h] BYREF

  v2 = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  if ( (unsigned int)BuildDriverCatalogName(pszSrc, pszDest) )
  {
    v4 = SpSignUninstallCatalogInternal(pszDest);
    v2 = v4;
    if ( v4 )
      DevRtlWriteTextLog(ThreadLogToken, 32, 2, "Unable to uninstall catalog '%ws'. Error = 0x%08X", pszDest, v4);
    else
      DevRtlWriteTextLog(ThreadLogToken, 32, 4, "Uninstalled catalog '%ws'.", pszDest);
  }
  return v2;
}

```

## disassembly

```asm
0x140014d40  mov     [rsp+arg_10], rbx
0x140014d45  push    rbp
0x140014d46  push    rsi
0x140014d47  push    rdi
0x140014d48  sub     rsp, 250h
0x140014d4f  mov     rax, cs:__security_cookie
0x140014d56  xor     rax, rsp
0x140014d59  mov     [rsp+268h+var_28], rax
0x140014d61  mov     rbp, rdx
0x140014d64  mov     rbx, rcx
0x140014d67  xor     edi, edi
0x140014d69  call    cs:__imp_DevRtlGetThreadLogToken
0x140014d6f  lea     rdx, [rsp+268h+pszDest]; pszDest
0x140014d74  mov     rcx, rbx; pszSrc
0x140014d77  mov     rsi, rax
0x140014d7a  call    BuildDriverCatalogName
0x140014d7f  test    eax, eax
0x140014d81  jz      short loc_140014DDC
0x140014d83  mov     rdx, rbp
0x140014d86  lea     rcx, [rsp+268h+pszDest]; pwszCatalogFile
0x140014d8b  call    SpSignUninstallCatalogInternal
0x140014d90  mov     edi, eax
0x140014d92  mov     edx, 20h ; ' '
0x140014d97  mov     rcx, rsi
0x140014d9a  test    eax, eax
0x140014d9c  jnz     short loc_140014DBB
0x140014d9e  lea     rax, [rsp+268h+pszDest]
0x140014da3  lea     r9, aUninstalledCat; "Uninstalled catalog '%ws'."
0x140014daa  mov     [rsp+268h+var_248], rax
0x140014daf  lea     r8d, [rdi+4]
0x140014db3  call    cs:__imp_DevRtlWriteTextLog
0x140014db9  jmp     short loc_140014DDC
0x140014dbb  mov     [rsp+268h+var_240], eax
0x140014dbf  lea     r9, aUnableToUninst_0; "Unable to uninstall catalog '%ws'. Erro"...
0x140014dc6  lea     rax, [rsp+268h+pszDest]
0x140014dcb  mov     r8d, 2
0x140014dd1  mov     [rsp+268h+var_248], rax
0x140014dd6  call    cs:__imp_DevRtlWriteTextLog
0x140014ddc  mov     eax, edi
0x140014dde  mov     rcx, [rsp+268h+var_28]
0x140014de6  xor     rcx, rsp; StackCookie
0x140014de9  call    __security_check_cookie
0x140014dee  mov     rbx, [rsp+268h+arg_10]
0x140014df6  add     rsp, 250h
0x140014dfd  pop     rdi
0x140014dfe  pop     rsi
0x140014dff  pop     rbp
0x140014e00  retn
```
