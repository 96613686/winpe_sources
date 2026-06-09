# PublishDriverPackageCatalog

- ea: `0x1400143b8`
- end: `0x1400144c9`
- name: `PublishDriverPackageCatalog`
- size: `273`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140013220`
- `0x14001ae4c`

## callees

- `0x14000bcbc`
- `0x140012ba0`
- `0x1400143b8`
- `0x14002e91c`
- `0x140045f30`

## import_xrefs

- `DEVRTL!DevRtlWriteTextLog` at `0x140014447`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014483`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001449a`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014447`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014483`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001449a`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x1400143eb`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x1400143eb`

## string_xrefs

- `0x140014431`: `Installed catalog '%ws' as '%ws'.`
- `0x140014478`: `Unable to install catalog '%ws' as '%ws'. Error = 0x%08X`
- `0x14001448d`: `Failed to install catalog '%ws' as '%ws'. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall PublishDriverPackageCatalog(STRSAFE_PCNZWCH pszSrc, __int64 a2, unsigned __int16 *a3, int a4)
{
  unsigned int v7; // edi
  __int64 ThreadLogToken; // rbp
  __int64 v9; // rax
  __int64 FileTitle; // rax
  wchar_t pszDest[264]; // [rsp+40h] [rbp-248h] BYREF

  v7 = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  if ( (unsigned int)BuildDriverCatalogName(pszSrc, pszDest) )
  {
    v7 = SpSignInstallCatalogInternal(a3);
    if ( v7 )
    {
      FileTitle = pSetupGetFileTitle(a3);
      if ( (a4 & 0xF0000000) != 0 )
      {
        DevRtlWriteTextLog(
          ThreadLogToken,
          32,
          2,
          "Unable to install catalog '%ws' as '%ws'. Error = 0x%08X",
          FileTitle,
          pszDest,
          v7);
        return 0;
      }
      else
      {
        DevRtlWriteTextLog(
          ThreadLogToken,
          32,
          1,
          "Failed to install catalog '%ws' as '%ws'. Error = 0x%08X",
          FileTitle,
          pszDest,
          v7);
      }
    }
    else
    {
      v9 = pSetupGetFileTitle(a3);
      DevRtlWriteTextLog(ThreadLogToken, 32, 4, "Installed catalog '%ws' as '%ws'.", v9, pszDest);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1400143b8  mov     [rsp+arg_18], rbx
0x1400143bd  push    rbp
0x1400143be  push    rsi
0x1400143bf  push    rdi
0x1400143c0  push    r14
0x1400143c2  push    r15
0x1400143c4  sub     rsp, 260h
0x1400143cb  mov     rax, cs:__security_cookie
0x1400143d2  xor     rax, rsp
0x1400143d5  mov     [rsp+288h+var_38], rax
0x1400143dd  mov     r14d, r9d
0x1400143e0  mov     rsi, r8
0x1400143e3  mov     r15, rdx
0x1400143e6  mov     rbx, rcx
0x1400143e9  xor     edi, edi
0x1400143eb  call    cs:__imp_DevRtlGetThreadLogToken
0x1400143f1  lea     rdx, [rsp+288h+pszDest]; pszDest
0x1400143f6  mov     rcx, rbx; pszSrc
0x1400143f9  mov     rbp, rax
0x1400143fc  call    BuildDriverCatalogName
0x140014401  test    eax, eax
0x140014403  jz      loc_1400144A0
0x140014409  lea     r8, [rsp+288h+pszDest]
0x14001440e  mov     rdx, r15
0x140014411  mov     rcx, rsi; unsigned __int16 *
0x140014414  call    SpSignInstallCatalogInternal
0x140014419  mov     edi, eax
0x14001441b  mov     rcx, rsi
0x14001441e  test    eax, eax
0x140014420  jnz     short loc_14001444F
0x140014422  call    pSetupGetFileTitle
0x140014427  lea     rcx, [rsp+288h+pszDest]
0x14001442c  mov     [rsp+288h+var_260], rcx
0x140014431  lea     r9, aInstalledCatal; "Installed catalog '%ws' as '%ws'."
0x140014438  mov     rcx, rbp
0x14001443b  mov     [rsp+288h+var_268], rax
0x140014440  lea     edx, [rdi+20h]
0x140014443  lea     r8d, [rdi+4]
0x140014447  call    cs:__imp_DevRtlWriteTextLog
0x14001444d  jmp     short loc_1400144A0
0x14001444f  call    pSetupGetFileTitle
0x140014454  mov     [rsp+288h+var_258], edi
0x140014458  lea     rcx, [rsp+288h+pszDest]
0x14001445d  mov     [rsp+288h+var_260], rcx
0x140014462  mov     rcx, rbp
0x140014465  mov     [rsp+288h+var_268], rax
0x14001446a  mov     edx, 20h ; ' '
0x14001446f  test    r14d, 0F0000000h
0x140014476  jz      short loc_14001448D
0x140014478  lea     r9, aUnableToInstal_1; "Unable to install catalog '%ws' as '%ws"...
0x14001447f  lea     r8d, [rdx-1Eh]
0x140014483  call    cs:__imp_DevRtlWriteTextLog
0x140014489  xor     edi, edi
0x14001448b  jmp     short loc_1400144A0
0x14001448d  lea     r9, aFailedToInstal_6; "Failed to install catalog '%ws' as '%ws"...
0x140014494  mov     r8d, 1
0x14001449a  call    cs:__imp_DevRtlWriteTextLog
0x1400144a0  mov     eax, edi
0x1400144a2  mov     rcx, [rsp+288h+var_38]
0x1400144aa  xor     rcx, rsp; StackCookie
0x1400144ad  call    __security_check_cookie
0x1400144b2  mov     rbx, [rsp+288h+arg_18]
0x1400144ba  add     rsp, 260h
0x1400144c1  pop     r15
0x1400144c3  pop     r14
0x1400144c5  pop     rdi
0x1400144c6  pop     rsi
0x1400144c7  pop     rbp
0x1400144c8  retn
```
