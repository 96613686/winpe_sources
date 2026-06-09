# PatchDb_InstallMergeSdb(ushort const *)

- ea: `0x1800877d0`
- end: `0x180087a78`
- name: `?PatchDb_InstallMergeSdb@@YAKPEBG@Z`
- size: `680`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000dc08`
- `0x180012920`
- `0x1800877d0`
- `0x180087a80`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x180087851`
- `ntdll!RtlDoesFileExists_U` at `0x180087851`
- `ntdll!RtlGetNtSystemRoot` at `0x18008785f`
- `ntdll!RtlGetNtSystemRoot` at `0x18008792f`
- `ntdll!RtlGetNtSystemRoot` at `0x1800879c1`
- `ntdll!RtlGetNtSystemRoot` at `0x18008785f`
- `ntdll!RtlGetNtSystemRoot` at `0x18008792f`
- `ntdll!RtlGetNtSystemRoot` at `0x1800879c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800878c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800878c0`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008790d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008790d`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800878b6`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800878b6`

## string_xrefs

- `0x180087961`: `Failed to expand cloud merge command string %d`
- `0x180087935`: `%s\system32\sdbinst.exe  -m -bg`
- `0x18008797e`: `Running command [%ws]`
- `0x180087a10`: `Running command [%ws]`
- `0x180087822`: `Failed to expand cloud merge extract path %d`
- `0x180087894`: `Failed to expand cloud merge path %d`
- `0x180087833`: `PatchDb_InstallMergeSdb`
- `0x18008798a`: `PatchDb_InstallMergeSdb`
- `0x180087a1c`: `PatchDb_InstallMergeSdb`
- `0x1800878ca`: `Failed to copy extracted cloud merge to the destination %d`
- `0x180087906`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\RemoteMergeStubSdbs`
- `0x1800879c7`: `%s\system32\pcaui.exe -noop`
- `0x1800879f3`: `Failed to expand PCAUI command string %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PatchDb_InstallMergeSdb(const unsigned __int16 *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  const char *v3; // r9
  int v4; // r8d
  __int64 NtSystemRoot; // rax
  int v6; // eax
  LSTATUS v7; // eax
  __int64 v8; // rax
  int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // eax
  LPCVOID lpData; // [rsp+20h] [rbp-658h]
  DWORD lpDatab; // [rsp+20h] [rbp-658h]
  LPCVOID lpDataa; // [rsp+20h] [rbp-658h]
  unsigned __int16 v18[264]; // [rsp+30h] [rbp-648h] BYREF
  WCHAR FileName[264]; // [rsp+240h] [rbp-438h] BYREF
  WCHAR NewFileName[264]; // [rsp+450h] [rbp-228h] BYREF

  v1 = StringCchPrintfW(FileName, 0x104u, L"%s\\cloudmerge.sdb", a1);
  v2 = v1;
  if ( v1 < 0 )
  {
    if ( (v1 & 0x1FFF0000) == 0x70000 )
      v2 = (unsigned __int16)v1;
    v3 = "Failed to expand cloud merge extract path %d";
    v4 = 2150;
LABEL_5:
    LODWORD(lpData) = v2;
    AslLogCallPrintf(1, (unsigned int)"PatchDb_InstallMergeSdb", v4, (_DWORD)v3, lpData);
    return v2;
  }
  if ( !RtlDoesFileExists_U(FileName) )
    return 0;
  NtSystemRoot = RtlGetNtSystemRoot();
  v6 = StringCchPrintfW(NewFileName, 0x104u, L"%s\\Apppatch\\cloudmerge.sdb", NtSystemRoot);
  v2 = v6;
  if ( v6 < 0 )
  {
    if ( (v6 & 0x1FFF0000) == 0x70000 )
      v2 = (unsigned __int16)v6;
    v3 = "Failed to expand cloud merge path %d";
    v4 = 2173;
    goto LABEL_5;
  }
  if ( CopyFileW(FileName, NewFileName, 0) )
  {
    v7 = RegSetKeyValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates\\RemoteMergeStubSdbs",
           L"cloudmerge.sdb",
           1u,
           L"%windir%\\Apppatch\\cloudmerge.sdb",
           0x42u);
    v2 = v7;
    if ( v7 )
    {
      LODWORD(lpData) = v7;
      AslLogCallPrintf(
        1,
        (unsigned int)"PatchDb_InstallMergeSdb",
        2194,
        (unsigned int)"Failed to set cloud merge key %d",
        lpData);
      return v2;
    }
    v8 = RtlGetNtSystemRoot();
    v9 = StringCchPrintfW(v18, 0x104u, L"%s\\system32\\sdbinst.exe  -m -bg", v8);
    v2 = v9;
    if ( v9 < 0 )
    {
      if ( (v9 & 0x1FFF0000) == 0x70000 )
        v2 = (unsigned __int16)v9;
      v3 = "Failed to expand cloud merge command string %d";
      v4 = 2205;
      goto LABEL_5;
    }
    AslLogCallPrintf(3, (unsigned int)"PatchDb_InstallMergeSdb", 2209, (unsigned int)"Running command [%ws]", v18);
    v10 = PatchDb_RunCommand(v18);
    v2 = v10;
    if ( v10 )
    {
      LODWORD(lpData) = v10;
      AslLogCallPrintf(
        1,
        (unsigned int)"PatchDb_InstallMergeSdb",
        2214,
        (unsigned int)"Failed to merge cloud merge sdb %d",
        lpData);
      return v2;
    }
    v11 = RtlGetNtSystemRoot();
    v12 = StringCchPrintfW(v18, 0x104u, L"%s\\system32\\pcaui.exe -noop", v11);
    v2 = v12;
    if ( v12 < 0 )
    {
      if ( (v12 & 0x1FFF0000) == 0x70000 )
        v2 = (unsigned __int16)v12;
      v3 = "Failed to expand PCAUI command string %d";
      v4 = 2228;
      goto LABEL_5;
    }
    AslLogCallPrintf(3, (unsigned int)"PatchDb_InstallMergeSdb", 2232, (unsigned int)"Running command [%ws]", v18);
    v13 = PatchDb_RunCommand(v18);
    v2 = v13;
    if ( v13 )
    {
      LODWORD(lpDataa) = v13;
      AslLogCallPrintf(
        1,
        (unsigned int)"PatchDb_InstallMergeSdb",
        2237,
        (unsigned int)"Failed to launch PCAUI %d",
        lpDataa);
      return v2;
    }
    return 0;
  }
  lpDatab = GetLastError();
  v2 = lpDatab;
  AslLogCallPrintf(
    1,
    (unsigned int)"PatchDb_InstallMergeSdb",
    2179,
    (unsigned int)"Failed to copy extracted cloud merge to the destination %d",
    lpDatab);
  return v2;
}

```

## disassembly

```asm
0x1800877d0  mov     [rsp+arg_8], rbx
0x1800877d5  push    rsi
0x1800877d6  sub     rsp, 670h
0x1800877dd  mov     rax, cs:__security_cookie
0x1800877e4  xor     rax, rsp
0x1800877e7  mov     [rsp+678h+var_18], rax
0x1800877ef  mov     r9, rcx
0x1800877f2  lea     r8, aSCloudmergeSdb; "%s\\cloudmerge.sdb"
0x1800877f9  mov     esi, 104h
0x1800877fe  lea     rcx, [rsp+678h+FileName]; unsigned __int16 *
0x180087806  mov     edx, esi; unsigned __int64
0x180087808  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008780d  mov     ebx, eax
0x18008780f  test    eax, eax
0x180087811  jns     short loc_180087849
0x180087813  and     eax, 1FFF0000h
0x180087818  cmp     eax, 70000h
0x18008781d  jnz     short loc_180087822
0x18008781f  movzx   ebx, bx
0x180087822  lea     r9, aFailedToExpand_6; "Failed to expand cloud merge extract pa"...
0x180087829  mov     r8d, 866h
0x18008782f  mov     dword ptr [rsp+678h+lpData], ebx
0x180087833  lea     rdx, aPatchdbInstall; "PatchDb_InstallMergeSdb"
0x18008783a  mov     ecx, 1
0x18008783f  call    AslLogCallPrintf
0x180087844  jmp     loc_180087A55
0x180087849  lea     rcx, [rsp+678h+FileName]; FileName
0x180087851  call    cs:__imp_RtlDoesFileExists_U
0x180087857  test    al, al
0x180087859  jz      loc_180087A53
0x18008785f  call    cs:__imp_RtlGetNtSystemRoot
0x180087865  lea     r8, aSApppatchCloud; "%s\\Apppatch\\cloudmerge.sdb"
0x18008786c  mov     rdx, rsi; unsigned __int64
0x18008786f  mov     r9, rax
0x180087872  lea     rcx, [rsp+678h+NewFileName]; unsigned __int16 *
0x18008787a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008787f  mov     ebx, eax
0x180087881  test    eax, eax
0x180087883  jns     short loc_1800878A3
0x180087885  and     eax, 1FFF0000h
0x18008788a  cmp     eax, 70000h
0x18008788f  jnz     short loc_180087894
0x180087891  movzx   ebx, bx
0x180087894  lea     r9, aFailedToExpand_4; "Failed to expand cloud merge path %d"
0x18008789b  mov     r8d, 87Dh
0x1800878a1  jmp     short loc_18008782F
0x1800878a3  xor     r8d, r8d; bFailIfExists
0x1800878a6  lea     rdx, [rsp+678h+NewFileName]; lpNewFileName
0x1800878ae  lea     rcx, [rsp+678h+FileName]; lpExistingFileName
0x1800878b6  call    cs:__imp_CopyFileW
0x1800878bc  test    eax, eax
0x1800878be  jnz     short loc_1800878DE
0x1800878c0  call    cs:__imp_GetLastError
0x1800878c6  mov     dword ptr [rsp+678h+lpData], eax
0x1800878ca  lea     r9, aFailedToCopyEx_1; "Failed to copy extracted cloud merge to"...
0x1800878d1  mov     ebx, eax
0x1800878d3  mov     r8d, 883h
0x1800878d9  jmp     loc_180087833
0x1800878de  lea     rax, aWindirApppatch; "%windir%\\Apppatch\\cloudmerge.sdb"
0x1800878e5  mov     [rsp+678h+cbData], 42h ; 'B'; cbData
0x1800878ed  mov     r9d, 1; dwType
0x1800878f3  mov     [rsp+678h+lpData], rax; lpData
0x1800878f8  lea     r8, aCloudmergeSdb; "cloudmerge.sdb"
0x1800878ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180087906  lea     rdx, aSoftwareMicros_20; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18008790d  call    cs:__imp_RegSetKeyValueW
0x180087913  mov     ebx, eax
0x180087915  test    eax, eax
0x180087917  jz      short loc_18008792F
0x180087919  mov     dword ptr [rsp+678h+lpData], eax
0x18008791d  lea     r9, aFailedToSetClo_0; "Failed to set cloud merge key %d"
0x180087924  mov     r8d, 892h
0x18008792a  jmp     loc_180087833
0x18008792f  call    cs:__imp_RtlGetNtSystemRoot
0x180087935  lea     r8, aSSystem32Sdbin; "%s\\system32\\sdbinst.exe  -m -bg"
0x18008793c  mov     rdx, rsi; unsigned __int64
0x18008793f  mov     r9, rax
0x180087942  lea     rcx, [rsp+678h+var_648]; unsigned __int16 *
0x180087947  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008794c  mov     ebx, eax
0x18008794e  test    eax, eax
0x180087950  jns     short loc_180087973
0x180087952  and     eax, 1FFF0000h
0x180087957  cmp     eax, 70000h
0x18008795c  jnz     short loc_180087961
0x18008795e  movzx   ebx, bx
0x180087961  lea     r9, aFailedToExpand_14; "Failed to expand cloud merge command st"...
0x180087968  mov     r8d, 89Dh
0x18008796e  jmp     loc_18008782F
0x180087973  lea     rax, [rsp+678h+var_648]
0x180087978  mov     r8d, 8A1h
0x18008797e  lea     r9, aRunningCommand; "Running command [%ws]"
0x180087985  mov     [rsp+678h+lpData], rax
0x18008798a  lea     rdx, aPatchdbInstall; "PatchDb_InstallMergeSdb"
0x180087991  mov     ecx, 3
0x180087996  call    AslLogCallPrintf
0x18008799b  lea     rcx, [rsp+678h+var_648]; unsigned __int16 *
0x1800879a0  call    ?PatchDb_RunCommand@@YAKPEAG@Z; PatchDb_RunCommand(ushort *)
0x1800879a5  mov     ebx, eax
0x1800879a7  test    eax, eax
0x1800879a9  jz      short loc_1800879C1
0x1800879ab  mov     dword ptr [rsp+678h+lpData], eax
0x1800879af  lea     r9, aFailedToMergeC; "Failed to merge cloud merge sdb %d"
0x1800879b6  mov     r8d, 8A6h
0x1800879bc  jmp     loc_180087833
0x1800879c1  call    cs:__imp_RtlGetNtSystemRoot
0x1800879c7  lea     r8, aSSystem32Pcaui; "%s\\system32\\pcaui.exe -noop"
0x1800879ce  mov     rdx, rsi; unsigned __int64
0x1800879d1  mov     r9, rax
0x1800879d4  lea     rcx, [rsp+678h+var_648]; unsigned __int16 *
0x1800879d9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800879de  mov     ebx, eax
0x1800879e0  test    eax, eax
0x1800879e2  jns     short loc_180087A05
0x1800879e4  and     eax, 1FFF0000h
0x1800879e9  cmp     eax, 70000h
0x1800879ee  jnz     short loc_1800879F3
0x1800879f0  movzx   ebx, bx
0x1800879f3  lea     r9, aFailedToExpand_9; "Failed to expand PCAUI command string %"...
0x1800879fa  mov     r8d, 8B4h
0x180087a00  jmp     loc_18008782F
0x180087a05  lea     rax, [rsp+678h+var_648]
0x180087a0a  mov     r8d, 8B8h
0x180087a10  lea     r9, aRunningCommand; "Running command [%ws]"
0x180087a17  mov     [rsp+678h+lpData], rax
0x180087a1c  lea     rdx, aPatchdbInstall; "PatchDb_InstallMergeSdb"
0x180087a23  mov     ecx, 3
0x180087a28  call    AslLogCallPrintf
0x180087a2d  lea     rcx, [rsp+678h+var_648]; unsigned __int16 *
0x180087a32  call    ?PatchDb_RunCommand@@YAKPEAG@Z; PatchDb_RunCommand(ushort *)
0x180087a37  mov     ebx, eax
0x180087a39  test    eax, eax
0x180087a3b  jz      short loc_180087A53
0x180087a3d  mov     dword ptr [rsp+678h+lpData], eax
0x180087a41  lea     r9, aFailedToLaunch; "Failed to launch PCAUI %d"
0x180087a48  mov     r8d, 8BDh
0x180087a4e  jmp     loc_180087833
0x180087a53  xor     ebx, ebx
0x180087a55  mov     eax, ebx
0x180087a57  mov     rcx, [rsp+678h+var_18]
0x180087a5f  xor     rcx, rsp; StackCookie
0x180087a62  call    __security_check_cookie
0x180087a67  mov     rbx, [rsp+678h+arg_8]
0x180087a6f  add     rsp, 670h
0x180087a76  pop     rsi
0x180087a77  retn
```
