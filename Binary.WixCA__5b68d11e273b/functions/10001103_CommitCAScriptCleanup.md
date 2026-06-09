# CommitCAScriptCleanup

- ea: `0x10001103`
- end: `0x100011ab`
- name: `CommitCAScriptCleanup`
- size: `168`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10001103`
- `0x1000a952`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`
- `0x1000e662`
- `0x1000efcc`
- `0x1000f4bb`

## string_xrefs

- `0x1000110b`: `CommitCAScriptCleanup`

## pseudocode

```c
int __stdcall CommitCAScriptCleanup(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // esi
  wchar_t SubStr[2]; // [esp+8h] [ebp-Ch] BYREF
  DWORD pcchValueBuf; // [esp+Ch] [ebp-8h] BYREF
  int v6; // [esp+10h] [ebp-4h] BYREF

  v1 = 0;
  pcchValueBuf = 0;
  *(_DWORD *)SubStr = 0;
  v6 = 0;
  v2 = sub_1000D51F(hInstall, (int)"CommitCAScriptCleanup");
  if ( v2 >= 0 )
  {
    v2 = sub_1000E662(L"CustomActionData", (DWORD)&pcchValueBuf);
    if ( v2 >= 0 )
    {
      *(_DWORD *)SubStr = pcchValueBuf;
      v2 = sub_1000EFCC((wchar_t)SubStr, (int)&v6);
      if ( v2 >= 0 )
        sub_1000F4BB(v6, 0);
      else
        sub_1000DA66(v2, "failed to process CustomActionData");
    }
    else
    {
      sub_1000DA66(v2, "failed to get CustomActionData");
    }
  }
  else
  {
    sub_1000DA66(v2, "Failed to initialize.");
  }
  if ( v6 )
    sub_1000A952(v6);
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
  if ( v2 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x10001103  push    ebp
0x10001104  mov     ebp, esp
0x10001106  sub     esp, 0Ch
0x10001109  push    esi
0x1000110a  push    edi
0x1000110b  push    offset aCommitcascript_0; "CommitCAScriptCleanup"
0x10001110  push    [ebp+hInstall]; hInstall
0x10001113  xor     edi, edi
0x10001115  mov     [ebp+pcchValueBuf], edi
0x10001118  mov     dword ptr [ebp+SubStr], edi
0x1000111b  mov     [ebp+var_4], edi
0x1000111e  call    sub_1000D51F
0x10001123  mov     esi, eax
0x10001125  test    esi, esi
0x10001127  jns     short loc_10001138
0x10001129  push    offset aFailedToInitia_1; "Failed to initialize."
0x1000112e  push    esi
0x1000112f  call    sub_1000DA66
0x10001134  pop     ecx
0x10001135  pop     ecx
0x10001136  jmp     short loc_1000117C
0x10001138  lea     eax, [ebp+pcchValueBuf]
0x1000113b  push    eax; pcchValueBuf
0x1000113c  push    offset aCustomactionda; "CustomActionData"
0x10001141  call    sub_1000E662
0x10001146  mov     esi, eax
0x10001148  test    esi, esi
0x1000114a  jns     short loc_10001153
0x1000114c  push    offset aFailedToGetCus; "failed to get CustomActionData"
0x10001151  jmp     short loc_1000112E
0x10001153  mov     eax, [ebp+pcchValueBuf]
0x10001156  mov     dword ptr [ebp+SubStr], eax
0x10001159  lea     eax, [ebp+var_4]
0x1000115c  push    eax; int
0x1000115d  lea     eax, [ebp+SubStr]
0x10001160  push    eax; SubStr
0x10001161  call    sub_1000EFCC
0x10001166  mov     esi, eax
0x10001168  test    esi, esi
0x1000116a  jns     short loc_10001173
0x1000116c  push    offset aFailedToProces; "failed to process CustomActionData"
0x10001171  jmp     short loc_1000112E
0x10001173  push    edi
0x10001174  push    [ebp+var_4]
0x10001177  call    sub_1000F4BB
0x1000117c  cmp     [ebp+var_4], edi
0x1000117f  jz      short loc_10001189
0x10001181  push    [ebp+var_4]
0x10001184  call    sub_1000A952
0x10001189  cmp     [ebp+pcchValueBuf], edi
0x1000118c  jz      short loc_10001196
0x1000118e  push    [ebp+pcchValueBuf]
0x10001191  call    sub_1000A952
0x10001196  test    esi, esi
0x10001198  jns     short loc_1000119F
0x1000119a  mov     edi, 643h
0x1000119f  push    edi
0x100011a0  call    sub_1000D4AE
0x100011a5  pop     edi
0x100011a6  pop     esi
0x100011a7  leave
0x100011a8  retn    4
```
