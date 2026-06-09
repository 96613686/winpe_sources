# SaferpIsV2PolicyPresent

- ea: `0x1800109ec`
- end: `0x180010bf3`
- name: `SaferpIsV2PolicyPresent`
- size: `519`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180010870`
- `0x180010c00`

## callees

- `0x1800109ec`
- `0x18006505a`
- `0x180065090`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180010a3e`
- `ntdll!NtOpenKey` at `0x180010a3e`
- `ntdll!NtQueryValueKey` at `0x180010a73`
- `ntdll!NtQueryValueKey` at `0x180010a73`
- `ntdll!NtClose` at `0x180010b43`
- `ntdll!NtClose` at `0x180010b43`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180010aab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180010aab`
- `KERNEL32!CloseHandle` at `0x180010bd0`
- `KERNEL32!CloseHandle` at `0x180010bd0`
- `KERNEL32!CreateFileW` at `0x180010bc1`
- `KERNEL32!CreateFileW` at `0x180010bc1`

## string_xrefs

- `0x180010af3`: `\System32\AppLocker\MDM`

## pseudocode

```c
__int64 __fastcall SaferpIsV2PolicyPresent(_DWORD *a1)
{
  NTSTATUS v2; // eax
  NTSTATUS v3; // ebx
  UINT SystemWindowsDirectoryW; // eax
  __int64 v5; // rdx
  WCHAR *v6; // rax
  __int64 v7; // r8
  __int64 v8; // rcx
  WCHAR *v9; // rax
  const wchar_t *v10; // rdx
  __int64 v11; // rdi
  WCHAR *v12; // rcx
  HANDLE FileW; // rax
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+54h] [rbp-ACh]
  int v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+5Ch] [rbp-A4h]
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF

  *a1 = 0;
  KeyHandle = 0;
  ResultLength = 0;
  v2 = NtOpenKey(&KeyHandle, 0x20119u, (POBJECT_ATTRIBUTES)&stru_1800670C0);
  if ( v2 < 0 )
  {
    v3 = 0;
    if ( v2 != -1073741772 )
      v3 = v2;
  }
  else
  {
    v3 = NtQueryValueKey(
           KeyHandle,
           (PUNICODE_STRING)&stru_1800670F0,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x50u,
           &ResultLength);
    if ( v3 >= 0 && v18 == 4 && v19 == 4 )
      *a1 = v20 != 0;
    else
      v3 = 0;
    if ( !*a1 )
    {
      memset_0(Buffer, 0, 0x208u);
      SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
      if ( !SystemWindowsDirectoryW || SystemWindowsDirectoryW >= 0x104 )
        goto LABEL_18;
      v5 = 260;
      v6 = Buffer;
      do
      {
        if ( !*v6 )
          break;
        ++v6;
        --v5;
      }
      while ( v5 );
      v7 = (260 - v5) & -(__int64)(v5 != 0);
      if ( !v5 )
        goto LABEL_18;
      v8 = 2147483646;
      v9 = &Buffer[v7];
      v10 = L"\\System32\\AppLocker\\MDM";
      v11 = 260 - v7;
      if ( 260 != v7 )
      {
        do
        {
          if ( !v8 )
            break;
          if ( !*v10 )
            break;
          *v9++ = *v10++;
          --v8;
          --v11;
        }
        while ( v11 );
      }
      v12 = v9 - 1;
      if ( v11 )
        v12 = v9;
      *v12 = 0;
      if ( v11 )
      {
        FileW = CreateFileW(Buffer, 1u, 1u, 0, 3u, 0x2000080u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        if ( FileW != (HANDLE)-1LL )
          *a1 = 1;
        CloseHandle(FileW);
      }
      else
      {
LABEL_18:
        v3 = -1073741801;
      }
    }
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800109ec  mov     [rsp-8+arg_8], rbx
0x1800109f1  mov     [rsp-8+arg_10], rsi
0x1800109f6  push    rbp
0x1800109f7  push    rdi
0x1800109f8  push    r14
0x1800109fa  lea     rbp, [rsp-1C0h]
0x180010a02  sub     rsp, 2C0h
0x180010a09  mov     rax, cs:__security_cookie
0x180010a10  xor     rax, rsp
0x180010a13  mov     [rbp+1D0h+var_20], rax
0x180010a1a  xor     r14d, r14d
0x180010a1d  lea     r8, stru_1800670C0; ObjectAttributes
0x180010a24  mov     [rcx], r14d
0x180010a27  mov     rsi, rcx
0x180010a2a  lea     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x180010a2f  mov     [rsp+2D0h+KeyHandle], r14
0x180010a34  mov     edx, 20119h; DesiredAccess
0x180010a39  mov     [rsp+2D0h+var_290], r14d
0x180010a3e  call    cs:__imp_NtOpenKey
0x180010a44  test    eax, eax
0x180010a46  js      loc_180010BDB
0x180010a4c  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x180010a51  lea     rax, [rsp+2D0h+var_290]
0x180010a56  mov     [rsp+2D0h+ResultLength], rax; ResultLength
0x180010a5b  lea     r9, [rsp+2D0h+KeyValueInformation]; KeyValueInformation
0x180010a60  lea     r8d, [r14+2]; KeyValueInformationClass
0x180010a64  mov     [rsp+2D0h+Length], 50h ; 'P'; Length
0x180010a6c  lea     rdx, stru_1800670F0; ValueName
0x180010a73  call    cs:__imp_NtQueryValueKey
0x180010a79  mov     ebx, eax
0x180010a7b  test    eax, eax
0x180010a7d  jns     loc_180010B72
0x180010a83  mov     ebx, r14d
0x180010a86  cmp     [rsi], r14d
0x180010a89  jnz     loc_180010B39
0x180010a8f  xor     edx, edx; Val
0x180010a91  lea     rcx, [rbp+1D0h+Buffer]; void *
0x180010a95  mov     r8d, 208h; Size
0x180010a9b  call    memset_0
0x180010aa0  mov     edi, 104h
0x180010aa5  lea     rcx, [rbp+1D0h+Buffer]; lpBuffer
0x180010aa9  mov     edx, edi; uSize
0x180010aab  call    cs:__imp_GetSystemWindowsDirectoryW
0x180010ab1  test    eax, eax
0x180010ab3  jz      short loc_180010B34
0x180010ab5  cmp     eax, edi
0x180010ab7  jnb     short loc_180010B34
0x180010ab9  mov     edx, edi
0x180010abb  lea     rax, [rbp+1D0h+Buffer]
0x180010abf  cmp     [rax], r14w
0x180010ac3  jz      short loc_180010ACF
0x180010ac5  add     rax, 2
0x180010ac9  sub     rdx, 1
0x180010acd  jnz     short loc_180010ABF
0x180010acf  mov     rcx, rdi
0x180010ad2  mov     rax, rdx
0x180010ad5  sub     rcx, rdx
0x180010ad8  neg     rax
0x180010adb  sbb     r8, r8
0x180010ade  and     r8, rcx
0x180010ae1  test    rdx, rdx
0x180010ae4  jz      short loc_180010B34
0x180010ae6  lea     rax, [rbp+1D0h+Buffer]
0x180010aea  mov     ecx, 7FFFFFFEh
0x180010aef  lea     rax, [rax+r8*2]
0x180010af3  lea     rdx, aSystem32Apploc; "\\System32\\AppLocker\\MDM"
0x180010afa  sub     rdi, r8
0x180010afd  jz      short loc_180010B23
0x180010aff  test    rcx, rcx
0x180010b02  jz      short loc_180010B23
0x180010b04  movzx   r8d, word ptr [rdx]
0x180010b08  test    r8w, r8w
0x180010b0c  jz      short loc_180010B23
0x180010b0e  mov     [rax], r8w
0x180010b12  add     rdx, 2
0x180010b16  add     rax, 2
0x180010b1a  dec     rcx
0x180010b1d  sub     rdi, 1
0x180010b21  jnz     short loc_180010AFF
0x180010b23  test    rdi, rdi
0x180010b26  lea     rcx, [rax-2]
0x180010b2a  cmovnz  rcx, rax
0x180010b2e  mov     [rcx], r14w
0x180010b32  jnz     short loc_180010B9A
0x180010b34  mov     ebx, 0C0000017h
0x180010b39  mov     rcx, [rsp+2D0h+KeyHandle]; Handle
0x180010b3e  test    rcx, rcx
0x180010b41  jz      short loc_180010B49
0x180010b43  call    cs:__imp_NtClose
0x180010b49  mov     eax, ebx
0x180010b4b  mov     rcx, [rbp+1D0h+var_20]
0x180010b52  xor     rcx, rsp; StackCookie
0x180010b55  call    __security_check_cookie
0x180010b5a  lea     r11, [rsp+2D0h+var_10]
0x180010b62  mov     rbx, [r11+28h]
0x180010b66  mov     rsi, [r11+30h]
0x180010b6a  mov     rsp, r11
0x180010b6d  pop     r14
0x180010b6f  pop     rdi
0x180010b70  pop     rbp
0x180010b71  retn
0x180010b72  cmp     [rsp+2D0h+var_27C], 4
0x180010b77  jnz     loc_180010A83
0x180010b7d  cmp     [rsp+2D0h+var_278], 4
0x180010b82  jnz     loc_180010A83
0x180010b88  cmp     [rsp+2D0h+var_274], r14d
0x180010b8d  mov     ecx, r14d
0x180010b90  setnz   cl
0x180010b93  mov     [rsi], ecx
0x180010b95  jmp     loc_180010A86
0x180010b9a  xor     r9d, r9d; lpSecurityAttributes
0x180010b9d  mov     [rsp+2D0h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x180010ba6  mov     dword ptr [rsp+2D0h+ResultLength], 2000080h; dwFlagsAndAttributes
0x180010bae  lea     rcx, [rbp+1D0h+Buffer]; lpFileName
0x180010bb2  mov     [rsp+2D0h+Length], 3; dwCreationDisposition
0x180010bba  lea     edx, [r9+1]; dwDesiredAccess
0x180010bbe  mov     r8d, edx; dwShareMode
0x180010bc1  call    cs:__imp_CreateFileW
0x180010bc7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010bcb  jnz     short loc_180010BEB
0x180010bcd  mov     rcx, rax; hObject
0x180010bd0  call    cs:__imp_CloseHandle
0x180010bd6  jmp     loc_180010B39
0x180010bdb  cmp     eax, 0C0000034h
0x180010be0  mov     ebx, r14d
0x180010be3  cmovnz  ebx, eax
0x180010be6  jmp     loc_180010B39
0x180010beb  mov     dword ptr [rsi], 1
0x180010bf1  jmp     short loc_180010BCD
```
