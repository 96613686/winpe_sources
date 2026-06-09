# CFineReaderShim::LoadFineReaderKeys(ushort const *)

- ea: `0x180035500`
- end: `0x180035811`
- name: `?LoadFineReaderKeys@CFineReaderShim@@QEAAKPEBG@Z`
- size: `785`
- prototype: `unsigned int __fastcall(CFineReaderShim *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800353b0`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x1800028e0`
- `0x180035198`
- `0x180035500`
- `0x1800543c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180035659`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180035659`
- `KERNEL32!FindClose` at `0x1800357c5`
- `KERNEL32!FindClose` at `0x1800357c5`
- `KERNEL32!FindNextFileW` at `0x1800357b1`
- `KERNEL32!FindNextFileW` at `0x1800357b1`
- `KERNEL32!FindFirstFileW` at `0x180035589`
- `KERNEL32!FindFirstFileW` at `0x180035589`
- `KERNEL32!GetLastError` at `0x180035598`
- `KERNEL32!GetLastError` at `0x180035598`
- `ADVAPI32!RegCloseKey` at `0x180035778`
- `ADVAPI32!RegCloseKey` at `0x180035778`
- `ADVAPI32!RegCreateKeyExW` at `0x18003574b`
- `ADVAPI32!RegCreateKeyExW` at `0x18003574b`
- `ADVAPI32!RegRestoreKeyW` at `0x18003576b`
- `ADVAPI32!RegRestoreKeyW` at `0x18003576b`

## string_xrefs

- `0x18003559e`: `Failed to enum files for fine reader migration shim [%d]`
- `0x1800355ab`: `CFineReaderShim::LoadFineReaderKeys`
- `0x1800356df`: `CFineReaderShim::LoadFineReaderKeys`
- `0x180035709`: `CFineReaderShim::LoadFineReaderKeys`
- `0x180035798`: `CFineReaderShim::LoadFineReaderKeys`
- `0x1800357fe`: `CFineReaderShim::LoadFineReaderKeys`
- `0x18003561c`: `Software\Classes\CLSID\%s`
- `0x1800356ac`: `%s\Software\Classes\CLSID\%s`
- `0x1800357ed`: `Failed to create registry key for fine reader migration shim [%d]`
- `0x180035787`: `Failed to restore registry key for fine reader migration shim [%d]`

## pseudocode

```c
__int64 __fastcall CFineReaderShim::LoadFineReaderKeys(CFineReaderShim *this, const unsigned __int16 *a2)
{
  CFineReaderShim *v4; // rcx
  DWORD LastError; // ebx
  HANDLE FirstFileW; // rsi
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int16 v9; // ax
  __int16 *v10; // rcx
  LSTATUS v11; // eax
  LSTATUS v12; // ebx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Buffer; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int16 v17; // [rsp+2B2h] [rbp+1B2h] BYREF
  wchar_t SubKey[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  wchar_t File[264]; // [rsp+6D0h] [rbp+5D0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  *((_QWORD *)this + 1) = a2;
  hKey = 0;
  LastError = CFineReaderShim::EnablePrivileges(v4);
  if ( LastError )
    return LastError;
  swprintf_s(&Buffer, 0x104u, L"%s\\*.reg", *((_QWORD *)this + 1));
  FirstFileW = FindFirstFileW(&Buffer, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    AslLogCallPrintf(
      1,
      "CFineReaderShim::LoadFineReaderKeys",
      394,
      "Failed to enum files for fine reader migration shim [%d]",
      LastError);
    return LastError;
  }
  while ( (FindFileData.dwFileAttributes & 0x10) != 0 )
  {
LABEL_21:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      LastError = 0;
      goto LABEL_23;
    }
  }
  swprintf_s(File, 0x104u, L"%s\\%s", *((_QWORD *)this + 1), FindFileData.cFileName);
  v7 = -1;
  do
    ++v7;
  while ( FindFileData.cFileName[v7] );
  *((_WORD *)&FindFileData.dwReserved0 + v7) = 0;
  if ( FindFileData.cFileName[0] == 123 )
  {
    swprintf_s(SubKey, 0x104u, L"Software\\Classes\\CLSID\\%s", FindFileData.cFileName);
    v8 = -2147483646;
  }
  else
  {
    if ( FindFileData.cFileName[0] != 83 && FindFileData.cFileName[0] != 46 )
      goto LABEL_21;
    _o_wcscpy_s(&Buffer, 260, FindFileData.cFileName);
    v9 = v17;
    if ( !v17 )
      goto LABEL_21;
    v10 = &v17;
    while ( v9 != 46 )
    {
      v9 = v10[1];
      ++v10;
      if ( !v9 )
        goto LABEL_21;
    }
    *v10 = 0;
    if ( v10 == (__int16 *)-2LL )
      goto LABEL_21;
    swprintf_s(SubKey, 0x104u, L"%s\\Software\\Classes\\CLSID\\%s", &Buffer, v10 + 1);
    v8 = -2147483645;
  }
  AslLogCallPrintf(3, "CFineReaderShim::LoadFineReaderKeys", 458, "Found key to restore [%ws]\n", SubKey);
  AslLogCallPrintf(3, "CFineReaderShim::LoadFineReaderKeys", 459, "From file [%ws]\n", File);
  v11 = RegCreateKeyExW((HKEY)v8, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  LastError = v11;
  if ( !v11 )
  {
    v12 = RegRestoreKeyW(hKey, File, 8u);
    RegCloseKey(hKey);
    hKey = 0;
    if ( v12 )
      AslLogCallPrintf(
        3,
        "CFineReaderShim::LoadFineReaderKeys",
        486,
        "Failed to restore registry key for fine reader migration shim [%d]",
        v12);
    goto LABEL_21;
  }
  AslLogCallPrintf(
    1,
    "CFineReaderShim::LoadFineReaderKeys",
    474,
    "Failed to create registry key for fine reader migration shim [%d]",
    v11);
LABEL_23:
  FindClose(FirstFileW);
  return LastError;
}

```

## disassembly

```asm
0x180035500  push    rbp
0x180035502  push    rbx
0x180035503  push    rsi
0x180035504  push    r12
0x180035506  push    r14
0x180035508  push    r15
0x18003550a  lea     rbp, [rsp-7F8h]
0x180035512  sub     rsp, 8F8h
0x180035519  mov     rax, cs:__security_cookie
0x180035520  xor     rax, rsp
0x180035523  mov     [rbp+820h+var_40], rax
0x18003552a  mov     rbx, rdx
0x18003552d  mov     r14, rcx
0x180035530  xor     edx, edx; Val
0x180035532  lea     rcx, [rsp+920h+FindFileData]; void *
0x180035537  mov     r8d, 250h; Size
0x18003553d  call    memset_0
0x180035542  xor     r15d, r15d
0x180035545  mov     [r14+8], rbx
0x180035549  mov     [rsp+920h+hKey], r15
0x18003554e  call    ?EnablePrivileges@CFineReaderShim@@AEAAKXZ; CFineReaderShim::EnablePrivileges(void)
0x180035553  mov     ebx, eax
0x180035555  test    eax, eax
0x180035557  jnz     loc_1800357CB
0x18003555d  mov     r9, [r14+8]
0x180035561  lea     r8, aSReg; "%s\\*.reg"
0x180035568  mov     r12d, 104h
0x18003556e  lea     rcx, [rbp+820h+Buffer]; Buffer
0x180035575  mov     edx, r12d; BufferCount
0x180035578  call    swprintf_s
0x18003557d  lea     rdx, [rsp+920h+FindFileData]; lpFindFileData
0x180035582  lea     rcx, [rbp+820h+Buffer]; lpFileName
0x180035589  call    cs:__imp_FindFirstFileW
0x18003558f  mov     rsi, rax
0x180035592  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180035596  jnz     short loc_1800355C5
0x180035598  call    cs:__imp_GetLastError
0x18003559e  lea     r9, aFailedToEnumFi; "Failed to enum files for fine reader mi"...
0x1800355a5  mov     r8d, 18Ah
0x1800355ab  lea     rdx, aCfinereadershi_0; "CFineReaderShim::LoadFineReaderKeys"
0x1800355b2  mov     [rsp+920h+dwOptions], eax
0x1800355b6  lea     ecx, [rsi+2]
0x1800355b9  mov     ebx, eax
0x1800355bb  call    AslLogCallPrintf
0x1800355c0  jmp     loc_1800357CB
0x1800355c5  test    byte ptr [rsp+920h+FindFileData.dwFileAttributes], 10h
0x1800355ca  jnz     loc_1800357A9
0x1800355d0  mov     r9, [r14+8]
0x1800355d4  lea     rax, [rbp+820h+FindFileData.cFileName]
0x1800355d8  lea     r8, aSS_0; "%s\\%s"
0x1800355df  mov     qword ptr [rsp+920h+dwOptions], rax
0x1800355e4  mov     rdx, r12; BufferCount
0x1800355e7  lea     rcx, [rbp+820h+File]; Buffer
0x1800355ee  call    swprintf_s
0x1800355f3  lea     rax, [rbp+820h+FindFileData.cFileName]
0x1800355f7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800355fb  inc     rcx
0x1800355fe  cmp     [rax+rcx*2], r15w
0x180035603  jnz     short loc_1800355FB
0x180035605  mov     word ptr [rbp+rcx*2+820h+FindFileData.dwReserved0], r15w
0x18003560b  movzx   eax, [rbp+820h+FindFileData.cFileName]
0x18003560f  cmp     ax, 7Bh ; '{'
0x180035613  jnz     short loc_18003563B
0x180035615  lea     r9, [rbp+820h+FindFileData.cFileName]
0x180035619  mov     rdx, r12; BufferCount
0x18003561c  lea     r8, aSoftwareClasse; "Software\\Classes\\CLSID\\%s"
0x180035623  lea     rcx, [rbp+820h+SubKey]; Buffer
0x18003562a  call    swprintf_s
0x18003562f  mov     rbx, 0FFFFFFFF80000002h
0x180035636  jmp     loc_1800356C6
0x18003563b  cmp     ax, 53h ; 'S'
0x18003563f  jz      short loc_18003564B
0x180035641  cmp     ax, 2Eh ; '.'
0x180035645  jnz     loc_1800357A9
0x18003564b  lea     r8, [rbp+820h+FindFileData.cFileName]
0x18003564f  mov     rdx, r12
0x180035652  lea     rcx, [rbp+820h+Buffer]
0x180035659  call    cs:__imp__o_wcscpy_s
0x18003565f  movzx   eax, [rbp+820h+var_66E]
0x180035666  test    ax, ax
0x180035669  jz      loc_1800357A9
0x18003566f  lea     rcx, [rbp+820h+var_66E]
0x180035676  lea     rdx, [rcx+2]
0x18003567a  cmp     ax, 2Eh ; '.'
0x18003567e  jz      short loc_180035690
0x180035680  movzx   eax, word ptr [rdx]
0x180035683  mov     rcx, rdx
0x180035686  test    ax, ax
0x180035689  jnz     short loc_180035676
0x18003568b  jmp     loc_1800357A9
0x180035690  mov     [rcx], r15w
0x180035694  test    rdx, rdx
0x180035697  jz      loc_1800357A9
0x18003569d  mov     qword ptr [rsp+920h+dwOptions], rdx
0x1800356a2  lea     r9, [rbp+820h+Buffer]
0x1800356a9  mov     rdx, r12; BufferCount
0x1800356ac  lea     r8, aSSoftwareClass; "%s\\Software\\Classes\\CLSID\\%s"
0x1800356b3  lea     rcx, [rbp+820h+SubKey]; Buffer
0x1800356ba  call    swprintf_s
0x1800356bf  mov     rbx, 0FFFFFFFF80000003h
0x1800356c6  lea     rax, [rbp+820h+SubKey]
0x1800356cd  mov     r8d, 1CAh
0x1800356d3  lea     r9, aFoundKeyToRest; "Found key to restore [%ws]\n"
0x1800356da  mov     qword ptr [rsp+920h+dwOptions], rax
0x1800356df  lea     rdx, aCfinereadershi_0; "CFineReaderShim::LoadFineReaderKeys"
0x1800356e6  mov     ecx, 3
0x1800356eb  call    AslLogCallPrintf
0x1800356f0  lea     rax, [rbp+820h+File]
0x1800356f7  mov     r8d, 1CBh
0x1800356fd  lea     r9, aFromFileWs; "From file [%ws]\n"
0x180035704  mov     qword ptr [rsp+920h+dwOptions], rax
0x180035709  lea     rdx, aCfinereadershi_0; "CFineReaderShim::LoadFineReaderKeys"
0x180035710  mov     ecx, 3
0x180035715  call    AslLogCallPrintf
0x18003571a  mov     [rsp+920h+lpdwDisposition], r15; lpdwDisposition
0x18003571f  lea     rax, [rsp+920h+hKey]
0x180035724  mov     [rsp+920h+phkResult], rax; phkResult
0x180035729  lea     rdx, [rbp+820h+SubKey]; lpSubKey
0x180035730  mov     [rsp+920h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180035735  xor     r9d, r9d; lpClass
0x180035738  mov     [rsp+920h+samDesired], 20006h; samDesired
0x180035740  xor     r8d, r8d; Reserved
0x180035743  mov     rcx, rbx; hKey
0x180035746  mov     [rsp+920h+dwOptions], r15d; dwOptions
0x18003574b  call    cs:__imp_RegCreateKeyExW
0x180035751  mov     ebx, eax
0x180035753  test    eax, eax
0x180035755  jnz     loc_1800357ED
0x18003575b  mov     rcx, [rsp+920h+hKey]; hKey
0x180035760  lea     r8d, [rax+8]; dwFlags
0x180035764  lea     rdx, [rbp+820h+File]; lpFile
0x18003576b  call    cs:__imp_RegRestoreKeyW
0x180035771  mov     rcx, [rsp+920h+hKey]; hKey
0x180035776  mov     ebx, eax
0x180035778  call    cs:__imp_RegCloseKey
0x18003577e  mov     [rsp+920h+hKey], r15
0x180035783  test    ebx, ebx
0x180035785  jz      short loc_1800357A9
0x180035787  lea     r9, aFailedToRestor; "Failed to restore registry key for fine"...
0x18003578e  mov     [rsp+920h+dwOptions], ebx
0x180035792  mov     r8d, 1E6h
0x180035798  lea     rdx, aCfinereadershi_0; "CFineReaderShim::LoadFineReaderKeys"
0x18003579f  mov     ecx, 3
0x1800357a4  call    AslLogCallPrintf
0x1800357a9  lea     rdx, [rsp+920h+FindFileData]; lpFindFileData
0x1800357ae  mov     rcx, rsi; hFindFile
0x1800357b1  call    cs:__imp_FindNextFileW
0x1800357b7  test    eax, eax
0x1800357b9  jnz     loc_1800355C5
0x1800357bf  mov     ebx, r15d
0x1800357c2  mov     rcx, rsi; hFindFile
0x1800357c5  call    cs:__imp_FindClose
0x1800357cb  mov     eax, ebx
0x1800357cd  mov     rcx, [rbp+820h+var_40]
0x1800357d4  xor     rcx, rsp; StackCookie
0x1800357d7  call    __security_check_cookie
0x1800357dc  add     rsp, 8F8h
0x1800357e3  pop     r15
0x1800357e5  pop     r14
0x1800357e7  pop     r12
0x1800357e9  pop     rsi
0x1800357ea  pop     rbx
0x1800357eb  pop     rbp
0x1800357ec  retn
0x1800357ed  lea     r9, aFailedToCreate_11; "Failed to create registry key for fine "...
0x1800357f4  mov     [rsp+920h+dwOptions], eax
0x1800357f8  mov     r8d, 1DAh
0x1800357fe  lea     rdx, aCfinereadershi_0; "CFineReaderShim::LoadFineReaderKeys"
0x180035805  mov     ecx, 1
0x18003580a  call    AslLogCallPrintf
0x18003580f  jmp     short loc_1800357C2
```
