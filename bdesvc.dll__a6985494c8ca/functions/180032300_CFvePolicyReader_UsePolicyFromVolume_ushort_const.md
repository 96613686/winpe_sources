# CFvePolicyReader::UsePolicyFromVolume(ushort const *)

- ea: `0x180032300`
- end: `0x180032614`
- name: `?UsePolicyFromVolume@CFvePolicyReader@@UEAAJPEBG@Z`
- size: `788`
- prototype: `__int64 __fastcall(CFvePolicyReader *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x18000dcc0`
- `0x18000dd60`
- `0x180023ca0`
- `0x180027ef0`
- `0x18002f960`
- `0x180032300`
- `0x180034070`
- `0x180034d28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800323b2`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800323c8`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800323b2`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800323c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032571`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800325ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032571`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800325ae`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800324fd`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180032534`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800324fd`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180032534`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800323de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800323f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800323de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800323f4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003247b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800324dd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003247b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800324dd`

## string_xrefs

- `0x180032459`: `\Windows\System32\Config\SOFTWARE`
- `0x1800324b6`: `\Windows\System32\Config\SYSTEM`

## pseudocode

```c
__int64 __fastcall CFvePolicyReader::UsePolicyFromVolume(CFvePolicyReader *this, const unsigned __int16 *a2)
{
  signed int v4; // ebx
  LSTATUS KeyW; // eax
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR FileName[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR File[264]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(FileName, 0, 0x208u);
  hKey = 0;
  memset_0(File, 0, 0x208u);
  phkResult = 0;
  if ( a2 )
  {
    CFvePolicyReader::CloseRootPolicyKeys(this);
    CFvePolicyReader::UnloadVolumePolicy(this);
    v4 = StringCchCopyW(FileName, 0x104u, a2);
    if ( v4 < 0 )
      goto LABEL_4;
    v4 = StringCchCatW(FileName, 0x104u, L"\\Windows\\System32\\Config\\SOFTWARE");
    if ( v4 < 0 )
      goto LABEL_4;
    if ( GetFileAttributesW(FileName) == -1 )
      goto LABEL_13;
    v4 = StringCchCopyW(File, 0x104u, a2);
    if ( v4 < 0 )
      goto LABEL_4;
    v4 = StringCchCatW(File, 0x104u, L"\\Windows\\System32\\Config\\SYSTEM");
    if ( v4 < 0 )
      goto LABEL_4;
    if ( GetFileAttributesW(File) == -1 )
    {
LABEL_13:
      v4 = -2147024894;
LABEL_4:
      RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSoftwareRoot");
      RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSystemRoot");
      goto LABEL_5;
    }
    KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSoftwareRoot", FileName);
    v4 = KeyW;
    if ( KeyW > 0 )
      v4 = (unsigned __int16)KeyW | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_4;
    v7 = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSystemRoot", File);
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_4;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"BitLockerSoftwareRoot", 0, 0x20019u, &hKey);
    v4 = v8;
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_4;
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"BitLockerSystemRoot", 0, 0x20019u, &phkResult);
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_4;
    *((_QWORD *)this + 2) = hKey;
    *((_QWORD *)this + 3) = phkResult;
    hKey = 0;
    phkResult = 0;
    v4 = StringCchCopyW((unsigned __int16 *)this + 17, 0x104u, a2);
    if ( v4 < 0 )
      goto LABEL_4;
    *((_BYTE *)this + 32) = 1;
  }
  else
  {
    v4 = CFvePolicyReader::ResetRootPolicyKeys(this);
    if ( v4 < 0 )
      goto LABEL_4;
    v4 = StringCchCopyW((unsigned __int16 *)this + 17, 0x104u, &dword_180086574);
    if ( v4 < 0 )
      goto LABEL_4;
  }
LABEL_5:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180032300  mov     [rsp-8+arg_10], rbx
0x180032305  mov     [rsp-8+arg_18], rsi
0x18003230a  push    rbp
0x18003230b  push    rdi
0x18003230c  push    r12
0x18003230e  push    r13
0x180032310  push    r14
0x180032312  lea     rbp, [rsp-370h]
0x18003231a  sub     rsp, 470h
0x180032321  mov     rax, cs:__security_cookie
0x180032328  xor     rax, rsp
0x18003232b  mov     [rbp+390h+var_30], rax
0x180032332  mov     r14, rdx
0x180032335  mov     rdi, rcx
0x180032338  mov     ebx, 208h
0x18003233d  lea     rcx, [rsp+490h+FileName]; void *
0x180032342  mov     r8d, ebx; Size
0x180032345  xor     edx, edx; Val
0x180032347  call    memset_0
0x18003234c  mov     r8d, ebx; Size
0x18003234f  mov     [rsp+490h+hKey], 0
0x180032358  xor     edx, edx; Val
0x18003235a  lea     rcx, [rbp+390h+File]; void *
0x180032361  call    memset_0
0x180032366  mov     [rsp+490h+var_458], 0
0x18003236f  mov     r13, 0FFFFFFFF80000002h
0x180032376  mov     rcx, rdi; this
0x180032379  test    r14, r14
0x18003237c  jnz     loc_18003242E
0x180032382  call    ?ResetRootPolicyKeys@CFvePolicyReader@@AEAAJXZ; CFvePolicyReader::ResetRootPolicyKeys(void)
0x180032387  mov     ebx, eax
0x180032389  test    eax, eax
0x18003238b  js      short loc_1800323A8
0x18003238d  lea     rcx, [rdi+22h]; unsigned __int16 *
0x180032391  mov     edx, 104h; unsigned __int64
0x180032396  lea     r8, dword_180086574; unsigned __int16 *
0x18003239d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800323a2  mov     ebx, eax
0x1800323a4  test    eax, eax
0x1800323a6  jns     short loc_1800323D4
0x1800323a8  lea     rdx, aBitlockersoftw; "BitLockerSoftwareRoot"
0x1800323af  mov     rcx, r13; hKey
0x1800323b2  call    cs:__imp_RegUnLoadKeyW
0x1800323b9  nop     dword ptr [rax+rax+00h]
0x1800323be  lea     rdx, aBitlockersyste; "BitLockerSystemRoot"
0x1800323c5  mov     rcx, r13; hKey
0x1800323c8  call    cs:__imp_RegUnLoadKeyW
0x1800323cf  nop     dword ptr [rax+rax+00h]
0x1800323d4  mov     rcx, [rsp+490h+hKey]; hKey
0x1800323d9  test    rcx, rcx
0x1800323dc  jz      short loc_1800323EA
0x1800323de  call    cs:__imp_RegCloseKey
0x1800323e5  nop     dword ptr [rax+rax+00h]
0x1800323ea  mov     rcx, [rsp+490h+var_458]; hKey
0x1800323ef  test    rcx, rcx
0x1800323f2  jz      short loc_180032400
0x1800323f4  call    cs:__imp_RegCloseKey
0x1800323fb  nop     dword ptr [rax+rax+00h]
0x180032400  mov     eax, ebx
0x180032402  mov     rcx, [rbp+390h+var_30]
0x180032409  xor     rcx, rsp; StackCookie
0x18003240c  call    __security_check_cookie
0x180032411  lea     r11, [rsp+490h+var_20]
0x180032419  mov     rbx, [r11+40h]
0x18003241d  mov     rsi, [r11+48h]
0x180032421  mov     rsp, r11
0x180032424  pop     r14
0x180032426  pop     r13
0x180032428  pop     r12
0x18003242a  pop     rdi
0x18003242b  pop     rbp
0x18003242c  retn
0x18003242e  call    ?CloseRootPolicyKeys@CFvePolicyReader@@AEAAXXZ; CFvePolicyReader::CloseRootPolicyKeys(void)
0x180032433  mov     rcx, rdi; this
0x180032436  call    ?UnloadVolumePolicy@CFvePolicyReader@@AEAAXXZ; CFvePolicyReader::UnloadVolumePolicy(void)
0x18003243b  mov     esi, 104h
0x180032440  lea     rcx, [rsp+490h+FileName]; unsigned __int16 *
0x180032445  mov     edx, esi; unsigned __int64
0x180032447  mov     r8, r14; unsigned __int16 *
0x18003244a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003244f  mov     ebx, eax
0x180032451  test    eax, eax
0x180032453  js      loc_1800323A8
0x180032459  lea     r8, aWindowsSystem3; "\\Windows\\System32\\Config\\SOFTWARE"
0x180032460  mov     edx, esi; unsigned __int64
0x180032462  lea     rcx, [rsp+490h+FileName]; unsigned __int16 *
0x180032467  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003246c  mov     ebx, eax
0x18003246e  test    eax, eax
0x180032470  js      loc_1800323A8
0x180032476  lea     rcx, [rsp+490h+FileName]; lpFileName
0x18003247b  call    cs:__imp_GetFileAttributesW
0x180032482  nop     dword ptr [rax+rax+00h]
0x180032487  or      r12d, 0FFFFFFFFh
0x18003248b  cmp     eax, r12d
0x18003248e  jnz     short loc_18003249A
0x180032490  mov     ebx, 80070002h
0x180032495  jmp     loc_1800323A8
0x18003249a  mov     r8, r14; unsigned __int16 *
0x18003249d  lea     rcx, [rbp+390h+File]; unsigned __int16 *
0x1800324a4  mov     rdx, rsi; unsigned __int64
0x1800324a7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800324ac  mov     ebx, eax
0x1800324ae  test    eax, eax
0x1800324b0  js      loc_1800323A8
0x1800324b6  lea     r8, aWindowsSystem3_0; "\\Windows\\System32\\Config\\SYSTEM"
0x1800324bd  mov     rdx, rsi; unsigned __int64
0x1800324c0  lea     rcx, [rbp+390h+File]; unsigned __int16 *
0x1800324c7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800324cc  mov     ebx, eax
0x1800324ce  test    eax, eax
0x1800324d0  js      loc_1800323A8
0x1800324d6  lea     rcx, [rbp+390h+File]; lpFileName
0x1800324dd  call    cs:__imp_GetFileAttributesW
0x1800324e4  nop     dword ptr [rax+rax+00h]
0x1800324e9  cmp     eax, r12d
0x1800324ec  jz      short loc_180032490
0x1800324ee  lea     r8, [rsp+490h+FileName]; lpFile
0x1800324f3  mov     rcx, r13; hKey
0x1800324f6  lea     rdx, aBitlockersoftw; "BitLockerSoftwareRoot"
0x1800324fd  call    cs:__imp_RegLoadKeyW
0x180032504  nop     dword ptr [rax+rax+00h]
0x180032509  mov     ebx, eax
0x18003250b  mov     r12d, 80070000h
0x180032511  test    eax, eax
0x180032513  jle     short loc_18003251B
0x180032515  movzx   ebx, ax
0x180032518  or      ebx, r12d
0x18003251b  test    ebx, ebx
0x18003251d  js      loc_1800323A8
0x180032523  lea     r8, [rbp+390h+File]; lpFile
0x18003252a  mov     rcx, r13; hKey
0x18003252d  lea     rdx, aBitlockersyste; "BitLockerSystemRoot"
0x180032534  call    cs:__imp_RegLoadKeyW
0x18003253b  nop     dword ptr [rax+rax+00h]
0x180032540  mov     ebx, eax
0x180032542  test    eax, eax
0x180032544  jle     short loc_18003254C
0x180032546  movzx   ebx, ax
0x180032549  or      ebx, r12d
0x18003254c  test    ebx, ebx
0x18003254e  js      loc_1800323A8
0x180032554  lea     rax, [rsp+490h+hKey]
0x180032559  mov     r9d, 20019h; samDesired
0x18003255f  xor     r8d, r8d; ulOptions
0x180032562  mov     [rsp+490h+phkResult], rax; phkResult
0x180032567  lea     rdx, aBitlockersoftw; "BitLockerSoftwareRoot"
0x18003256e  mov     rcx, r13; hKey
0x180032571  call    cs:__imp_RegOpenKeyExW
0x180032578  nop     dword ptr [rax+rax+00h]
0x18003257d  mov     ebx, eax
0x18003257f  test    eax, eax
0x180032581  jle     short loc_180032589
0x180032583  movzx   ebx, ax
0x180032586  or      ebx, r12d
0x180032589  test    ebx, ebx
0x18003258b  js      loc_1800323A8
0x180032591  lea     rax, [rsp+490h+var_458]
0x180032596  mov     r9d, 20019h; samDesired
0x18003259c  xor     r8d, r8d; ulOptions
0x18003259f  mov     [rsp+490h+phkResult], rax; phkResult
0x1800325a4  lea     rdx, aBitlockersyste; "BitLockerSystemRoot"
0x1800325ab  mov     rcx, r13; hKey
0x1800325ae  call    cs:__imp_RegOpenKeyExW
0x1800325b5  nop     dword ptr [rax+rax+00h]
0x1800325ba  mov     ebx, eax
0x1800325bc  test    eax, eax
0x1800325be  jle     short loc_1800325C6
0x1800325c0  movzx   ebx, ax
0x1800325c3  or      ebx, r12d
0x1800325c6  test    ebx, ebx
0x1800325c8  js      loc_1800323A8
0x1800325ce  mov     rax, [rsp+490h+hKey]
0x1800325d3  lea     rcx, [rdi+22h]; unsigned __int16 *
0x1800325d7  mov     [rdi+10h], rax
0x1800325db  mov     r8, r14; unsigned __int16 *
0x1800325de  mov     rax, [rsp+490h+var_458]
0x1800325e3  mov     rdx, rsi; unsigned __int64
0x1800325e6  mov     [rdi+18h], rax
0x1800325ea  mov     [rsp+490h+hKey], 0
0x1800325f3  mov     [rsp+490h+var_458], 0
0x1800325fc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180032601  mov     ebx, eax
0x180032603  test    eax, eax
0x180032605  js      loc_1800323A8
0x18003260b  mov     byte ptr [rdi+20h], 1
0x18003260f  jmp     loc_1800323D4
```
