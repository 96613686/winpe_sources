# TagKnownFolders(void *,SCAN_FUNCTION_ARGS,bool &)

- ea: `0x18001d020`
- end: `0x18001d1a2`
- name: `?TagKnownFolders@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z`
- size: `386`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800050f0`
- `0x180019de0`
- `0x18001cb04`
- `0x18001d020`
- `0x18001f76c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d161`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d16b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d161`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d16b`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001d09f`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001d0f1`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001d09f`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001d0f1`

## pseudocode

```c
__int64 __fastcall TagKnownFolders(void *a1, __int64 a2)
{
  wchar_t **v3; // rbx
  unsigned int v5; // edi
  __int128 v6; // xmm1
  PWSTR v7; // rcx
  PWSTR v8; // r9
  PWSTR v9; // rax
  int v10; // r10d
  int v11; // edx
  bool v13; // [rsp+20h] [rbp-40h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-38h] BYREF
  PWSTR v15; // [rsp+30h] [rbp-30h] BYREF
  KNOWNFOLDERID rfid; // [rsp+38h] [rbp-28h] BYREF
  __int128 v17; // [rsp+48h] [rbp-18h]

  v3 = &KnownFolderScanConfigTable;
  v5 = 0;
  while ( v3 != &RegScanConfigTable )
  {
    v6 = *((_OWORD *)v3 + 1);
    rfid = *(KNOWNFOLDERID *)v3;
    v17 = v6;
    if ( IsTaskCancelled(a1) )
      return (unsigned int)-2147023673;
    if ( DWORD2(v17) )
    {
      ppszPath = 0;
      v13 = 0;
      if ( SHGetKnownFolderPath((const KNOWNFOLDERID *const)rfid.Data4, 0, 0, &ppszPath) >= 0
        && (*(_DWORD *)(a2 + 12) == 2 || (int)IsDirectoryTagged(ppszPath, SDWORD2(v17), &v13) >= 0 && !v13) )
      {
        TagDirectoryTree(a1, ppszPath, DWORD2(v17));
      }
      v15 = 0;
      v13 = 0;
      if ( SHGetKnownFolderPath((const KNOWNFOLDERID *const)rfid.Data4, 0x400u, 0, &v15) < 0 )
        goto LABEL_21;
      v7 = ppszPath;
      v8 = v15;
      if ( !ppszPath )
        goto LABEL_16;
      v9 = ppszPath;
      do
      {
        v10 = *(PWSTR)((char *)v9 + (char *)v15 - (char *)ppszPath);
        v11 = *v9 - v10;
        if ( v11 )
          break;
        ++v9;
      }
      while ( v10 );
      if ( v11 )
      {
LABEL_16:
        if ( *(_DWORD *)(a2 + 12) == 2 )
          goto LABEL_20;
        if ( (int)IsDirectoryTagged(v15, SDWORD2(v17), &v13) >= 0 && !v13 )
        {
          v8 = v15;
LABEL_20:
          TagDirectoryTree(a1, v8, DWORD2(v17));
        }
LABEL_21:
        v7 = ppszPath;
      }
      CoTaskMemFree(v7);
      CoTaskMemFree(v15);
    }
    v3 += 4;
  }
  return v5;
}

```

## disassembly

```asm
0x18001d020  mov     [rsp-18h+arg_8], rbx
0x18001d025  mov     [rsp-18h+arg_10], rsi
0x18001d02a  push    rbp
0x18001d02b  push    rdi
0x18001d02c  push    r14
0x18001d02e  mov     rbp, rsp
0x18001d031  sub     rsp, 60h
0x18001d035  mov     rax, cs:__security_cookie
0x18001d03c  xor     rax, rsp
0x18001d03f  mov     [rbp+var_8], rax
0x18001d043  mov     rsi, rdx
0x18001d046  lea     rbx, ?KnownFolderScanConfigTable@@3V?$array@UKNOWN_FOLDER_SCAN_CONFIG@@$06@std@@A; std::array<KNOWN_FOLDER_SCAN_CONFIG,7> KnownFolderScanConfigTable
0x18001d04d  mov     r14, rcx
0x18001d050  xor     edi, edi
0x18001d052  lea     rax, ?RegScanConfigTable@@3V?$array@UREG_SCAN_CONFIG@@$05@std@@A; std::array<REG_SCAN_CONFIG,6> RegScanConfigTable
0x18001d059  cmp     rbx, rax
0x18001d05c  jz      loc_18001D17F
0x18001d062  movups  xmm0, xmmword ptr [rbx]
0x18001d065  mov     rcx, r14; void *
0x18001d068  movups  xmm1, xmmword ptr [rbx+10h]
0x18001d06c  movups  xmmword ptr [rbp+rfid.Data1], xmm0
0x18001d070  movups  [rbp+var_18], xmm1
0x18001d074  call    ?IsTaskCancelled@@YA_NPEAX@Z; IsTaskCancelled(void *)
0x18001d079  test    al, al
0x18001d07b  jnz     loc_18001D17A
0x18001d081  cmp     dword ptr [rbp+var_18+8], edi
0x18001d084  jz      loc_18001D171
0x18001d08a  lea     r9, [rbp+ppszPath]; ppszPath
0x18001d08e  mov     [rbp+ppszPath], rdi
0x18001d092  xor     r8d, r8d; hToken
0x18001d095  mov     [rbp+var_40], dil
0x18001d099  xor     edx, edx; dwFlags
0x18001d09b  lea     rcx, [rbp+rfid.Data4]; rfid
0x18001d09f  call    cs:__imp_SHGetKnownFolderPath
0x18001d0a5  test    eax, eax
0x18001d0a7  js      short loc_18001D0D9
0x18001d0a9  cmp     dword ptr [rsi+0Ch], 2
0x18001d0ad  jz      short loc_18001D0C9
0x18001d0af  mov     edx, dword ptr [rbp+var_18+8]
0x18001d0b2  lea     r8, [rbp+var_40]
0x18001d0b6  mov     rcx, [rbp+ppszPath]
0x18001d0ba  call    ?IsDirectoryTagged@@YAJPEBGW4_FILE_KNOWN_FOLDER_TYPE@@AEA_N@Z; IsDirectoryTagged(ushort const *,_FILE_KNOWN_FOLDER_TYPE,bool &)
0x18001d0bf  test    eax, eax
0x18001d0c1  js      short loc_18001D0D9
0x18001d0c3  cmp     [rbp+var_40], dil
0x18001d0c7  jnz     short loc_18001D0D9
0x18001d0c9  mov     r8d, dword ptr [rbp+var_18+8]
0x18001d0cd  mov     rcx, r14
0x18001d0d0  mov     rdx, [rbp+ppszPath]
0x18001d0d4  call    ?TagDirectoryTree@@YAJPEAXPEBGW4_FILE_KNOWN_FOLDER_TYPE@@@Z; TagDirectoryTree(void *,ushort const *,_FILE_KNOWN_FOLDER_TYPE)
0x18001d0d9  lea     r9, [rbp+var_30]; ppszPath
0x18001d0dd  mov     [rbp+var_30], rdi
0x18001d0e1  xor     r8d, r8d; hToken
0x18001d0e4  mov     [rbp+var_40], dil
0x18001d0e8  mov     edx, 400h; dwFlags
0x18001d0ed  lea     rcx, [rbp+rfid.Data4]; rfid
0x18001d0f1  call    cs:__imp_SHGetKnownFolderPath
0x18001d0f7  test    eax, eax
0x18001d0f9  js      short loc_18001D15D
0x18001d0fb  mov     rcx, [rbp+ppszPath]
0x18001d0ff  mov     r9, [rbp+var_30]
0x18001d103  test    rcx, rcx
0x18001d106  jz      short loc_18001D12B
0x18001d108  mov     r8, r9
0x18001d10b  mov     rax, rcx
0x18001d10e  sub     r8, rcx
0x18001d111  movzx   edx, word ptr [rax]
0x18001d114  movzx   r10d, word ptr [rax+r8]
0x18001d119  sub     edx, r10d
0x18001d11c  jnz     short loc_18001D127
0x18001d11e  add     rax, 2
0x18001d122  test    r10d, r10d
0x18001d125  jnz     short loc_18001D111
0x18001d127  test    edx, edx
0x18001d129  jz      short loc_18001D161
0x18001d12b  cmp     dword ptr [rsi+0Ch], 2
0x18001d12f  jz      short loc_18001D14E
0x18001d131  mov     edx, dword ptr [rbp+var_18+8]
0x18001d134  lea     r8, [rbp+var_40]
0x18001d138  mov     rcx, r9
0x18001d13b  call    ?IsDirectoryTagged@@YAJPEBGW4_FILE_KNOWN_FOLDER_TYPE@@AEA_N@Z; IsDirectoryTagged(ushort const *,_FILE_KNOWN_FOLDER_TYPE,bool &)
0x18001d140  test    eax, eax
0x18001d142  js      short loc_18001D15D
0x18001d144  cmp     [rbp+var_40], dil
0x18001d148  jnz     short loc_18001D15D
0x18001d14a  mov     r9, [rbp+var_30]
0x18001d14e  mov     r8d, dword ptr [rbp+var_18+8]
0x18001d152  mov     rdx, r9
0x18001d155  mov     rcx, r14
0x18001d158  call    ?TagDirectoryTree@@YAJPEAXPEBGW4_FILE_KNOWN_FOLDER_TYPE@@@Z; TagDirectoryTree(void *,ushort const *,_FILE_KNOWN_FOLDER_TYPE)
0x18001d15d  mov     rcx, [rbp+ppszPath]; pv
0x18001d161  call    cs:__imp_CoTaskMemFree
0x18001d167  mov     rcx, [rbp+var_30]; pv
0x18001d16b  call    cs:__imp_CoTaskMemFree
0x18001d171  add     rbx, 20h ; ' '
0x18001d175  jmp     loc_18001D052
0x18001d17a  mov     edi, 800704C7h
0x18001d17f  mov     eax, edi
0x18001d181  mov     rcx, [rbp+var_8]
0x18001d185  xor     rcx, rsp; StackCookie
0x18001d188  call    __security_check_cookie
0x18001d18d  lea     r11, [rsp+60h+var_s0]
0x18001d192  mov     rbx, [r11+28h]
0x18001d196  mov     rsi, [r11+30h]
0x18001d19a  mov     rsp, r11
0x18001d19d  pop     r14
0x18001d19f  pop     rdi
0x18001d1a0  pop     rbp
0x18001d1a1  retn
```
