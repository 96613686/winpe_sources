# CIdentityPolicy::IsPku2uDisabled(void)

- ea: `0x180006fa0`
- end: `0x180007151`
- name: `?IsPku2uDisabled@CIdentityPolicy@@QEAAHXZ`
- size: `433`
- prototype: `_BOOL8 __fastcall(CIdentityPolicy *this)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800066f0`
- `0x18000d51c`
- `0x180014c2c`
- `0x180015c94`

## callees

- `0x180006fa0`
- `0x18001a342`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800070b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800070b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007146`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007146`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000703c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000703c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800070f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800070f6`

## pseudocode

```c
_BOOL8 __fastcall CIdentityPolicy::IsPku2uDisabled(CIdentityPolicy *this)
{
  BOOL v2; // edi
  int v3; // esi
  bool v5; // zf
  BOOL v6; // eax
  DWORD pdwType; // [rsp+40h] [rbp-158h] BYREF
  int pvData; // [rsp+44h] [rbp-154h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-150h] BYREF
  DWORD pcbData[4]; // [rsp+50h] [rbp-148h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+60h] [rbp-138h] BYREF
  char v12; // [rsp+17Ah] [rbp-1Eh]

  pcbData[0] = 4;
  pdwType = 0;
  v2 = 1;
  pvData = 0;
  if ( !*((_DWORD *)this + 6) )
  {
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( GetVersionExW(&VersionInformation) )
    {
      v5 = v12 == 1;
      *((_DWORD *)this + 6) = 1;
      v6 = !v5;
      v5 = v12 == 2;
      *((_DWORD *)this + 4) = v6;
      *((_DWORD *)this + 5) = v5;
    }
  }
  phkResult = 0;
  if ( !*((_DWORD *)this + 5) )
  {
    v3 = *((_DWORD *)this + 4);
    if ( !*((_QWORD *)this + 1) )
    {
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa", 0, 0x20019u, &phkResult) )
      {
LABEL_6:
        if ( phkResult )
          RegCloseKey(phkResult);
        return v2;
      }
      if ( !_InterlockedCompareExchange64((volatile signed __int64 *)this + 1, (signed __int64)phkResult, 0) )
        phkResult = 0;
    }
    if ( RegGetValueW(*((HKEY *)this + 1), L"Pku2u", L"AllowOnlineID", 0x10u, &pdwType, &pvData, pcbData)
      || pdwType != 4 )
    {
      v2 = v3 != 0;
    }
    else
    {
      v2 = pvData == 0;
    }
    goto LABEL_6;
  }
  return v2;
}

```

## disassembly

```asm
0x180006fa0  mov     [rsp+arg_10], rbx
0x180006fa5  mov     [rsp+arg_18], rbp
0x180006faa  push    rdi
0x180006fab  sub     rsp, 190h
0x180006fb2  mov     rax, cs:__security_cookie
0x180006fb9  xor     rax, rsp
0x180006fbc  mov     [rsp+198h+var_18], rax
0x180006fc4  xor     ebp, ebp
0x180006fc6  mov     [rsp+198h+var_148], 4
0x180006fce  mov     rbx, rcx
0x180006fd1  mov     [rsp+198h+var_158], ebp
0x180006fd5  mov     edi, 1
0x180006fda  mov     [rsp+198h+var_154], ebp
0x180006fde  cmp     [rcx+18h], ebp
0x180006fe1  jz      loc_1800070D7
0x180006fe7  mov     [rsp+198h+phkResult], rbp
0x180006fec  cmp     [rbx+14h], ebp
0x180006fef  jnz     short loc_180007068
0x180006ff1  mov     [rsp+198h+arg_8], rsi
0x180006ff9  mov     esi, [rbx+10h]
0x180006ffc  cmp     [rbx+8], rbp
0x180007000  jz      loc_18000708F
0x180007006  mov     rcx, [rbx+8]; hkey
0x18000700a  lea     rax, [rsp+198h+var_148]
0x18000700f  mov     [rsp+198h+pcbData], rax; pcbData
0x180007014  lea     r8, Value; "AllowOnlineID"
0x18000701b  lea     rax, [rsp+198h+var_154]
0x180007020  mov     r9d, 10h; dwFlags
0x180007026  mov     [rsp+198h+pvData], rax; pvData
0x18000702b  lea     rdx, aPku2u; "Pku2u"
0x180007032  lea     rax, [rsp+198h+var_158]
0x180007037  mov     [rsp+198h+pdwType], rax; pdwType
0x18000703c  call    cs:__imp_RegGetValueW
0x180007042  test    eax, eax
0x180007044  jz      loc_18000712C
0x18000704a  test    esi, esi
0x18000704c  mov     edi, ebp
0x18000704e  setnz   dil
0x180007052  mov     rcx, [rsp+198h+phkResult]; hKey
0x180007057  mov     rsi, [rsp+198h+arg_8]
0x18000705f  test    rcx, rcx
0x180007062  jnz     loc_180007146
0x180007068  mov     eax, edi
0x18000706a  mov     rcx, [rsp+198h+var_18]
0x180007072  xor     rcx, rsp; StackCookie
0x180007075  call    __security_check_cookie
0x18000707a  lea     r11, [rsp+198h+var_8]
0x180007082  mov     rbx, [r11+20h]
0x180007086  mov     rbp, [r11+28h]
0x18000708a  mov     rsp, r11
0x18000708d  pop     rdi
0x18000708e  retn
0x18000708f  lea     rax, [rsp+198h+phkResult]
0x180007094  mov     r9d, 20019h; samDesired
0x18000709a  xor     r8d, r8d; ulOptions
0x18000709d  mov     [rsp+198h+pdwType], rax; phkResult
0x1800070a2  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Lsa"
0x1800070a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800070b0  call    cs:__imp_RegOpenKeyExW
0x1800070b6  test    eax, eax
0x1800070b8  jnz     short loc_180007052
0x1800070ba  mov     rcx, [rsp+198h+phkResult]
0x1800070bf  xor     eax, eax
0x1800070c1  lock cmpxchg [rbx+8], rcx
0x1800070c7  jnz     loc_180007006
0x1800070cd  mov     [rsp+198h+phkResult], rbp
0x1800070d2  jmp     loc_180007006
0x1800070d7  xor     edx, edx; Val
0x1800070d9  lea     rcx, [rsp+198h+VersionInformation.dwMajorVersion]; void *
0x1800070de  mov     r8d, 118h; Size
0x1800070e4  call    memset_0
0x1800070e9  lea     rcx, [rsp+198h+VersionInformation]; lpVersionInformation
0x1800070ee  mov     [rsp+198h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800070f6  call    cs:__imp_GetVersionExW
0x1800070fc  test    eax, eax
0x1800070fe  jz      loc_180006FE7
0x180007104  cmp     [rsp+198h+var_1E], dil
0x18000710c  mov     eax, ebp
0x18000710e  mov     [rbx+18h], edi
0x180007111  setnz   al
0x180007114  cmp     [rsp+198h+var_1E], 2
0x18000711c  mov     [rbx+10h], eax
0x18000711f  mov     eax, ebp
0x180007121  setz    al
0x180007124  mov     [rbx+14h], eax
0x180007127  jmp     loc_180006FE7
0x18000712c  cmp     [rsp+198h+var_158], 4
0x180007131  jnz     loc_18000704A
0x180007137  cmp     [rsp+198h+var_154], ebp
0x18000713b  mov     edi, ebp
0x18000713d  setz    dil
0x180007141  jmp     loc_180007052
0x180007146  call    cs:__imp_RegCloseKey
0x18000714c  jmp     loc_180007068
```
