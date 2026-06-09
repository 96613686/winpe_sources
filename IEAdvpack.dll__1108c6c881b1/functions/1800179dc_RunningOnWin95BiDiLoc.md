# RunningOnWin95BiDiLoc

- ea: `0x1800179dc`
- end: `0x180017b96`
- name: `RunningOnWin95BiDiLoc`
- size: `442`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008a6c`

## callees

- `0x1800179dc`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `USER32!CharNextA` at `0x180017b42`
- `USER32!CharNextA` at `0x180017b42`
- `USER32!GetSystemMetrics` at `0x180017a88`
- `USER32!GetSystemMetrics` at `0x180017a88`
- `KERNEL32!GetVersionExW` at `0x180017a52`
- `KERNEL32!GetVersionExW` at `0x180017a52`
- `ADVAPI32!RegCloseKey` at `0x180017af9`
- `ADVAPI32!RegCloseKey` at `0x180017af9`
- `ADVAPI32!RegQueryValueExA` at `0x180017aec`
- `ADVAPI32!RegQueryValueExA` at `0x180017aec`
- `ADVAPI32!RegOpenKeyExA` at `0x180017ab7`
- `ADVAPI32!RegOpenKeyExA` at `0x180017ab7`

## pseudocode

```c
__int64 RunningOnWin95BiDiLoc()
{
  unsigned int v0; // edi
  LSTATUS v1; // ebx
  const CHAR *i; // rcx
  CHAR v3; // dl
  int v4; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[16]; // [rsp+160h] [rbp+60h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  v0 = dword_1800251B8;
  hKey = 0;
  Type = 0;
  cbData = 12;
  if ( dword_1800251B8 == -2 )
  {
    dword_1800251B8 = 0;
    VersionInformation.dwOSVersionInfoSize = 276;
    if ( !GetVersionExW(&VersionInformation) )
      return (unsigned int)dword_1800251B8;
    v0 = 1;
    if ( VersionInformation.dwPlatformId != 1 )
      return (unsigned int)dword_1800251B8;
    if ( VersionInformation.dwMajorVersion != 4 )
      return (unsigned int)dword_1800251B8;
    if ( VersionInformation.dwMinorVersion >= 0xA )
      return (unsigned int)dword_1800251B8;
    if ( !GetSystemMetrics(74) )
      return (unsigned int)dword_1800251B8;
    if ( RegOpenKeyExA(HKEY_CURRENT_USER, "Control Panel\\Desktop\\ResourceLocale", 0, 0x20019u, &hKey) )
      return (unsigned int)dword_1800251B8;
    v1 = RegQueryValueExA(hKey, byte_180020E95, 0, &Type, Data, &cbData);
    RegCloseKey(hKey);
    if ( v1 )
      return (unsigned int)dword_1800251B8;
    for ( i = (const CHAR *)Data; ; i = CharNextA(i) )
    {
      if ( (unsigned __int8)(*i - 48) > 9u )
      {
        v3 = *i - 32;
        if ( *i < 97 )
          v3 = *i;
        if ( (unsigned int)(v3 - 65) > 5 )
        {
          if ( i != (const CHAR *)Data )
          {
            v4 = v1 & 0x3FF;
            if ( v4 == 1 || v4 == 13 )
            {
              dword_1800251B8 = 1;
              return v0;
            }
          }
          return (unsigned int)dword_1800251B8;
        }
        v1 = v3 + 16 * v1 - 55;
      }
      else
      {
        v1 = *i + 16 * (v1 - 3);
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800179dc  mov     [rsp-8+arg_0], rbx
0x1800179e1  mov     [rsp-8+arg_8], rdi
0x1800179e6  push    rbp
0x1800179e7  lea     rbp, [rsp-80h]
0x1800179ec  sub     rsp, 180h
0x1800179f3  mov     rax, cs:__security_cookie
0x1800179fa  xor     rax, rsp
0x1800179fd  mov     [rbp+80h+var_10], rax
0x180017a01  xor     edx, edx; Val
0x180017a03  lea     rcx, [rsp+180h+VersionInformation.dwMajorVersion]; void *
0x180017a08  mov     r8d, 110h; Size
0x180017a0e  call    memset_0
0x180017a13  mov     edi, cs:dword_1800251B8
0x180017a19  mov     [rsp+180h+hKey], 0
0x180017a22  mov     [rsp+180h+Type], 0
0x180017a2a  mov     [rsp+180h+cbData], 0Ch
0x180017a32  cmp     edi, 0FFFFFFFEh
0x180017a35  jnz     loc_180017B73
0x180017a3b  lea     rcx, [rsp+180h+VersionInformation]; lpVersionInformation
0x180017a40  mov     cs:dword_1800251B8, 0
0x180017a4a  mov     [rsp+180h+VersionInformation.dwOSVersionInfoSize], 114h
0x180017a52  call    cs:__imp_GetVersionExW
0x180017a58  test    eax, eax
0x180017a5a  jz      loc_180017B6D
0x180017a60  mov     edi, 1
0x180017a65  cmp     [rsp+180h+VersionInformation.dwPlatformId], edi
0x180017a69  jnz     loc_180017B6D
0x180017a6f  cmp     [rsp+180h+VersionInformation.dwMajorVersion], 4
0x180017a74  jnz     loc_180017B6D
0x180017a7a  cmp     [rsp+180h+VersionInformation.dwMinorVersion], 0Ah
0x180017a7f  jnb     loc_180017B6D
0x180017a85  lea     ecx, [rdi+49h]; nIndex
0x180017a88  call    cs:__imp_GetSystemMetrics
0x180017a8e  test    eax, eax
0x180017a90  jz      loc_180017B6D
0x180017a96  lea     rax, [rsp+180h+hKey]
0x180017a9b  mov     r9d, 20019h; samDesired
0x180017aa1  xor     r8d, r8d; ulOptions
0x180017aa4  mov     [rsp+180h+phkResult], rax; phkResult
0x180017aa9  lea     rdx, aControlPanelDe; "Control Panel\\Desktop\\ResourceLocale"
0x180017ab0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180017ab7  call    cs:__imp_RegOpenKeyExA
0x180017abd  test    eax, eax
0x180017abf  jnz     loc_180017B6D
0x180017ac5  mov     rcx, [rsp+180h+hKey]; hKey
0x180017aca  lea     rax, [rsp+180h+cbData]
0x180017acf  mov     [rsp+180h+lpcbData], rax; lpcbData
0x180017ad4  lea     r9, [rsp+180h+Type]; lpType
0x180017ad9  lea     rax, [rbp+80h+Data]
0x180017add  xor     r8d, r8d; lpReserved
0x180017ae0  lea     rdx, byte_180020E95; lpValueName
0x180017ae7  mov     [rsp+180h+phkResult], rax; lpData
0x180017aec  call    cs:__imp_RegQueryValueExA
0x180017af2  mov     rcx, [rsp+180h+hKey]; hKey
0x180017af7  mov     ebx, eax
0x180017af9  call    cs:__imp_RegCloseKey
0x180017aff  test    ebx, ebx
0x180017b01  jnz     short loc_180017B6D
0x180017b03  lea     rcx, [rbp+80h+Data]; lpsz
0x180017b07  mov     al, [rcx]
0x180017b09  sub     al, 30h ; '0'
0x180017b0b  cmp     al, 9
0x180017b0d  ja      short loc_180017B1C
0x180017b0f  movsx   eax, byte ptr [rcx]
0x180017b12  add     ebx, 0FFFFFFFDh
0x180017b15  shl     ebx, 4
0x180017b18  add     ebx, eax
0x180017b1a  jmp     short loc_180017B42
0x180017b1c  mov     al, [rcx]
0x180017b1e  sub     al, 20h ; ' '
0x180017b20  cmp     byte ptr [rcx], 61h ; 'a'
0x180017b23  movzx   edx, al
0x180017b26  movzx   eax, byte ptr [rcx]
0x180017b29  cmovl   edx, eax
0x180017b2c  movsx   r8d, dl
0x180017b30  lea     eax, [r8-41h]
0x180017b34  cmp     eax, 5
0x180017b37  ja      short loc_180017B4D
0x180017b39  shl     ebx, 4
0x180017b3c  add     ebx, 0FFFFFFC9h
0x180017b3f  add     ebx, r8d
0x180017b42  call    cs:__imp_CharNextA
0x180017b48  mov     rcx, rax
0x180017b4b  jmp     short loc_180017B07
0x180017b4d  lea     rax, [rbp+80h+Data]
0x180017b51  cmp     rcx, rax
0x180017b54  jz      short loc_180017B6D
0x180017b56  and     ebx, 3FFh
0x180017b5c  cmp     ebx, edi
0x180017b5e  jz      short loc_180017B65
0x180017b60  cmp     ebx, 0Dh
0x180017b63  jnz     short loc_180017B6D
0x180017b65  mov     cs:dword_1800251B8, edi
0x180017b6b  jmp     short loc_180017B73
0x180017b6d  mov     edi, cs:dword_1800251B8
0x180017b73  mov     eax, edi
0x180017b75  mov     rcx, [rbp+80h+var_10]
0x180017b79  xor     rcx, rsp; StackCookie
0x180017b7c  call    __security_check_cookie
0x180017b81  lea     r11, [rsp+180h+var_s0]
0x180017b89  mov     rbx, [r11+10h]
0x180017b8d  mov     rdi, [r11+18h]
0x180017b91  mov     rsp, r11
0x180017b94  pop     rbp
0x180017b95  retn
```
