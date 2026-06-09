# SaferpIsV2PolicyPresent

- ea: `0x180015d60`
- end: `0x180015f8c`
- name: `SaferpIsV2PolicyPresent`
- size: `556`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180015bd0`
- `0x1800160c0`

## callees

- `0x180015d60`
- `0x18007205a`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180015db2`
- `ntdll!NtOpenKey` at `0x180015db2`
- `ntdll!NtQueryValueKey` at `0x180015ded`
- `ntdll!NtQueryValueKey` at `0x180015ded`
- `ntdll!NtClose` at `0x180015ec9`
- `ntdll!NtClose` at `0x180015ec9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180015e2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180015e2b`
- `KERNEL32!CloseHandle` at `0x180015f63`
- `KERNEL32!CloseHandle` at `0x180015f63`
- `KERNEL32!CreateFileW` at `0x180015f4e`
- `KERNEL32!CreateFileW` at `0x180015f4e`

## string_xrefs

- `0x180015e79`: `\System32\AppLocker\MDM`

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
  v2 = NtOpenKey(&KeyHandle, 0x20119u, (POBJECT_ATTRIBUTES)&stru_1800750C0);
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
           (PUNICODE_STRING)&stru_1800750F0,
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
0x180015d60  mov     [rsp-8+arg_8], rbx
0x180015d65  mov     [rsp-8+arg_10], rsi
0x180015d6a  push    rbp
0x180015d6b  push    rdi
0x180015d6c  push    r14
0x180015d6e  lea     rbp, [rsp-1C0h]
0x180015d76  sub     rsp, 2C0h
0x180015d7d  mov     rax, cs:__security_cookie
0x180015d84  xor     rax, rsp
0x180015d87  mov     [rbp+1D0h+var_20], rax
0x180015d8e  xor     r14d, r14d
0x180015d91  lea     r8, stru_1800750C0; ObjectAttributes
0x180015d98  mov     [rcx], r14d
0x180015d9b  mov     rsi, rcx
0x180015d9e  lea     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x180015da3  mov     [rsp+2D0h+KeyHandle], r14
0x180015da8  mov     edx, 20119h; DesiredAccess
0x180015dad  mov     [rsp+2D0h+var_290], r14d
0x180015db2  call    cs:__imp_NtOpenKey
0x180015db9  nop     dword ptr [rax+rax+00h]
0x180015dbe  test    eax, eax
0x180015dc0  js      loc_180015F74
0x180015dc6  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x180015dcb  lea     rax, [rsp+2D0h+var_290]
0x180015dd0  mov     [rsp+2D0h+ResultLength], rax; ResultLength
0x180015dd5  lea     r9, [rsp+2D0h+KeyValueInformation]; KeyValueInformation
0x180015dda  lea     r8d, [r14+2]; KeyValueInformationClass
0x180015dde  mov     [rsp+2D0h+Length], 50h ; 'P'; Length
0x180015de6  lea     rdx, stru_1800750F0; ValueName
0x180015ded  call    cs:__imp_NtQueryValueKey
0x180015df4  nop     dword ptr [rax+rax+00h]
0x180015df9  mov     ebx, eax
0x180015dfb  test    eax, eax
0x180015dfd  jns     loc_180015EFF
0x180015e03  mov     ebx, r14d
0x180015e06  cmp     [rsi], r14d
0x180015e09  jnz     loc_180015EBF
0x180015e0f  xor     edx, edx; Val
0x180015e11  lea     rcx, [rbp+1D0h+Buffer]; void *
0x180015e15  mov     r8d, 208h; Size
0x180015e1b  call    memset_0
0x180015e20  mov     edi, 104h
0x180015e25  lea     rcx, [rbp+1D0h+Buffer]; lpBuffer
0x180015e29  mov     edx, edi; uSize
0x180015e2b  call    cs:__imp_GetSystemWindowsDirectoryW
0x180015e32  nop     dword ptr [rax+rax+00h]
0x180015e37  test    eax, eax
0x180015e39  jz      short loc_180015EBA
0x180015e3b  cmp     eax, edi
0x180015e3d  jnb     short loc_180015EBA
0x180015e3f  mov     edx, edi
0x180015e41  lea     rax, [rbp+1D0h+Buffer]
0x180015e45  cmp     [rax], r14w
0x180015e49  jz      short loc_180015E55
0x180015e4b  add     rax, 2
0x180015e4f  sub     rdx, 1
0x180015e53  jnz     short loc_180015E45
0x180015e55  mov     rcx, rdi
0x180015e58  mov     rax, rdx
0x180015e5b  sub     rcx, rdx
0x180015e5e  neg     rax
0x180015e61  sbb     r8, r8
0x180015e64  and     r8, rcx
0x180015e67  test    rdx, rdx
0x180015e6a  jz      short loc_180015EBA
0x180015e6c  lea     rax, [rbp+1D0h+Buffer]
0x180015e70  mov     ecx, 7FFFFFFEh
0x180015e75  lea     rax, [rax+r8*2]
0x180015e79  lea     rdx, aSystem32Apploc; "\\System32\\AppLocker\\MDM"
0x180015e80  sub     rdi, r8
0x180015e83  jz      short loc_180015EA9
0x180015e85  test    rcx, rcx
0x180015e88  jz      short loc_180015EA9
0x180015e8a  movzx   r8d, word ptr [rdx]
0x180015e8e  test    r8w, r8w
0x180015e92  jz      short loc_180015EA9
0x180015e94  mov     [rax], r8w
0x180015e98  add     rdx, 2
0x180015e9c  add     rax, 2
0x180015ea0  dec     rcx
0x180015ea3  sub     rdi, 1
0x180015ea7  jnz     short loc_180015E85
0x180015ea9  test    rdi, rdi
0x180015eac  lea     rcx, [rax-2]
0x180015eb0  cmovnz  rcx, rax
0x180015eb4  mov     [rcx], r14w
0x180015eb8  jnz     short loc_180015F27
0x180015eba  mov     ebx, 0C0000017h
0x180015ebf  mov     rcx, [rsp+2D0h+KeyHandle]; Handle
0x180015ec4  test    rcx, rcx
0x180015ec7  jz      short loc_180015ED5
0x180015ec9  call    cs:__imp_NtClose
0x180015ed0  nop     dword ptr [rax+rax+00h]
0x180015ed5  mov     eax, ebx
0x180015ed7  mov     rcx, [rbp+1D0h+var_20]
0x180015ede  xor     rcx, rsp; StackCookie
0x180015ee1  call    __security_check_cookie
0x180015ee6  lea     r11, [rsp+2D0h+var_10]
0x180015eee  mov     rbx, [r11+28h]
0x180015ef2  mov     rsi, [r11+30h]
0x180015ef6  mov     rsp, r11
0x180015ef9  pop     r14
0x180015efb  pop     rdi
0x180015efc  pop     rbp
0x180015efd  retn
0x180015eff  cmp     [rsp+2D0h+var_27C], 4
0x180015f04  jnz     loc_180015E03
0x180015f0a  cmp     [rsp+2D0h+var_278], 4
0x180015f0f  jnz     loc_180015E03
0x180015f15  cmp     [rsp+2D0h+var_274], r14d
0x180015f1a  mov     ecx, r14d
0x180015f1d  setnz   cl
0x180015f20  mov     [rsi], ecx
0x180015f22  jmp     loc_180015E06
0x180015f27  xor     r9d, r9d; lpSecurityAttributes
0x180015f2a  mov     [rsp+2D0h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x180015f33  mov     dword ptr [rsp+2D0h+ResultLength], 2000080h; dwFlagsAndAttributes
0x180015f3b  lea     rcx, [rbp+1D0h+Buffer]; lpFileName
0x180015f3f  mov     [rsp+2D0h+Length], 3; dwCreationDisposition
0x180015f47  lea     edx, [r9+1]; dwDesiredAccess
0x180015f4b  mov     r8d, edx; dwShareMode
0x180015f4e  call    cs:__imp_CreateFileW
0x180015f55  nop     dword ptr [rax+rax+00h]
0x180015f5a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015f5e  jnz     short loc_180015F84
0x180015f60  mov     rcx, rax; hObject
0x180015f63  call    cs:__imp_CloseHandle
0x180015f6a  nop     dword ptr [rax+rax+00h]
0x180015f6f  jmp     loc_180015EBF
0x180015f74  cmp     eax, 0C0000034h
0x180015f79  mov     ebx, r14d
0x180015f7c  cmovnz  ebx, eax
0x180015f7f  jmp     loc_180015EBF
0x180015f84  mov     dword ptr [rsi], 1
0x180015f8a  jmp     short loc_180015F60
```
