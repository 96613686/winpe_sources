# StructuredQuery1::GetSchemaChangedLast

- ea: `0x1800354d4`
- end: `0x180035664`
- name: `StructuredQuery1::GetSchemaChangedLast`
- size: `400`
- prototype: `__int64 __fastcall(LPBYTE lpData)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034f50`

## callees

- `0x1800354d4`
- `0x180035f08`
- `0x18005daf0`
- `0x1800849bc`
- `0x180084b10`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180035581`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180035581`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800355ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800355ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003554d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003554d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035618`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035618`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180035511`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180035511`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::GetSchemaChangedLast(LPBYTE lpData)
{
  bool v2; // al
  wchar_t *v3; // rdx
  LSTATUS v4; // eax
  signed int v5; // ebx
  LSTATUS v7; // eax
  unsigned int v8; // r9d
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData[2]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  FILETIME FileTime2; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t v13[264]; // [rsp+50h] [rbp-B0h] BYREF

  *(_QWORD *)lpData = 0;
  hKey = 0;
  *(_QWORD *)cbData = 0;
  v2 = (unsigned __int8)RtlIsStateSeparationEnabled()
    && GetSearchRegistryRedirect(L"StructuredQuery", (struct CSearchRegistryRedirectHelper **)cbData)
    && CSearchRegistryRedirectHelper::MapRegistryKeyPath(
         *(CSearchRegistryRedirectHelper **)cbData,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\StructuredQuery",
         v13,
         v8) >= 0;
  v3 = v13;
  if ( !v2 )
    v3 = (wchar_t *)L"Software\\Microsoft\\Windows\\CurrentVersion\\StructuredQuery";
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 1u, &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    Type = 0;
    cbData[0] = 8;
    v7 = RegQueryValueExW(hKey, L"SchemaChangedLast", 0, &Type, lpData, cbData);
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    if ( v5 >= 0 && (Type != 11 || cbData[0] != 8) )
      v5 = -2147418113;
    RegCloseKey(hKey);
  }
  FileTime2 = 0;
  StructuredQuery1::GetPropSysLastWriteTime(&FileTime2);
  if ( CompareFileTime((const FILETIME *)lpData, &FileTime2) < 0 )
    *(FILETIME *)lpData = FileTime2;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800354d4  mov     [rsp-8+arg_8], rbx
0x1800354d9  mov     [rsp-8+arg_10], rdi
0x1800354de  push    rbp
0x1800354df  lea     rbp, [rsp-170h]
0x1800354e7  sub     rsp, 270h
0x1800354ee  mov     rax, cs:__security_cookie
0x1800354f5  xor     rax, rsp
0x1800354f8  mov     [rbp+170h+var_10], rax
0x1800354ff  xor     eax, eax
0x180035501  mov     rdi, rcx
0x180035504  mov     [rcx], rax
0x180035507  mov     [rsp+270h+hKey], rax
0x18003550c  mov     qword ptr [rsp+270h+cbData], rax
0x180035511  call    cs:__imp_RtlIsStateSeparationEnabled
0x180035517  lea     rbx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003551e  test    al, al
0x180035520  jnz     loc_180035623
0x180035526  xor     al, al
0x180035528  test    al, al
0x18003552a  lea     rdx, [rsp+270h+var_220]
0x18003552f  lea     rax, [rsp+270h+hKey]
0x180035534  mov     r9d, 1; samDesired
0x18003553a  cmovz   rdx, rbx; lpSubKey
0x18003553e  mov     [rsp+270h+phkResult], rax; phkResult
0x180035543  xor     r8d, r8d; ulOptions
0x180035546  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003554d  call    cs:__imp_RegOpenKeyExW
0x180035553  mov     ebx, eax
0x180035555  test    eax, eax
0x180035557  jle     short loc_180035562
0x180035559  movzx   ebx, ax
0x18003555c  or      ebx, 80070000h
0x180035562  test    ebx, ebx
0x180035564  jns     short loc_1800355B9
0x180035566  lea     rcx, [rsp+270h+FileTime2]
0x18003556b  mov     qword ptr [rsp+270h+FileTime2.dwLowDateTime], 0
0x180035574  call    StructuredQuery1__GetPropSysLastWriteTime
0x180035579  lea     rdx, [rsp+270h+FileTime2]; lpFileTime2
0x18003557e  mov     rcx, rdi; lpFileTime1
0x180035581  call    cs:__imp_CompareFileTime
0x180035587  test    eax, eax
0x180035589  jns     short loc_180035593
0x18003558b  mov     rcx, qword ptr [rsp+270h+FileTime2.dwLowDateTime]
0x180035590  mov     [rdi], rcx
0x180035593  mov     eax, ebx
0x180035595  mov     rcx, [rbp+170h+var_10]
0x18003559c  xor     rcx, rsp; StackCookie
0x18003559f  call    __security_check_cookie
0x1800355a4  lea     r11, [rsp+270h+var_s0]
0x1800355ac  mov     rbx, [r11+18h]
0x1800355b0  mov     rdi, [r11+20h]
0x1800355b4  mov     rsp, r11
0x1800355b7  pop     rbp
0x1800355b8  retn
0x1800355b9  mov     rcx, [rsp+270h+hKey]; hKey
0x1800355be  lea     rax, [rsp+270h+cbData]
0x1800355c3  mov     [rsp+270h+lpcbData], rax; lpcbData
0x1800355c8  lea     r9, [rsp+270h+Type]; lpType
0x1800355cd  xor     r8d, r8d; lpReserved
0x1800355d0  mov     [rsp+270h+phkResult], rdi; lpData
0x1800355d5  lea     rdx, ValueName; "SchemaChangedLast"
0x1800355dc  mov     [rsp+270h+Type], 0
0x1800355e4  mov     [rsp+270h+cbData], 8
0x1800355ec  call    cs:__imp_RegQueryValueExW
0x1800355f2  mov     ebx, eax
0x1800355f4  test    eax, eax
0x1800355f6  jle     short loc_180035601
0x1800355f8  movzx   ebx, ax
0x1800355fb  or      ebx, 80070000h
0x180035601  test    ebx, ebx
0x180035603  js      short loc_180035613
0x180035605  cmp     [rsp+270h+Type], 0Bh
0x18003560a  jnz     short loc_18003565D
0x18003560c  cmp     [rsp+270h+cbData], 8
0x180035611  jnz     short loc_18003565D
0x180035613  mov     rcx, [rsp+270h+hKey]; hKey
0x180035618  call    cs:__imp_RegCloseKey
0x18003561e  jmp     loc_180035566
0x180035623  lea     rdx, [rsp+270h+cbData]; struct CSearchRegistryRedirectHelper **
0x180035628  lea     rcx, aStructuredquer_0; "StructuredQuery"
0x18003562f  call    ?GetSearchRegistryRedirect@@YA_NPEB_WPEAPEAVCSearchRegistryRedirectHelper@@@Z; GetSearchRegistryRedirect(wchar_t const *,CSearchRegistryRedirectHelper * *)
0x180035634  test    al, al
0x180035636  jz      loc_180035526
0x18003563c  mov     rcx, qword ptr [rsp+270h+cbData]; this
0x180035641  lea     r8, [rsp+270h+var_220]; wchar_t *
0x180035646  mov     rdx, rbx; wchar_t *
0x180035649  call    ?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z; CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)
0x18003564e  test    eax, eax
0x180035650  js      loc_180035526
0x180035656  mov     al, 1
0x180035658  jmp     loc_180035528
0x18003565d  mov     ebx, 8000FFFFh
0x180035662  jmp     short loc_180035613
```
