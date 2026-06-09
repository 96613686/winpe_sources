# ProfileIsActive

- ea: `0x180065d48`
- end: `0x180065f09`
- name: `ProfileIsActive`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18006a370`

## callees

- `0x180065d48`
- `0x180066490`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065e30`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065e83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065e30`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065e83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065df2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065df2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065ee4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065ee4`

## string_xrefs

- `0x180065dc6`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x180065dd8`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x180065e7c`: `AutoTriggerProfilePhonebookPath`

## pseudocode

```c
__int64 __fastcall ProfileIsActive(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  const WCHAR *v6; // rdx
  BYTE *v7; // rax
  __int64 v8; // rsi
  int v9; // edx
  int v10; // ecx
  BYTE *v11; // rax
  __int64 v12; // rdi
  int v13; // ecx
  int v14; // edx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[528]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v20[528]; // [rsp+250h] [rbp+150h] BYREF

  cbData = 0;
  Type = 0;
  hKey = 0;
  v4 = 0;
  memset_0(Data, 0, 0x105u);
  memset_0(v20, 0, 0x105u);
  if ( a2 )
  {
    v5 = StateSepEnabled();
    v6 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    if ( !v5 )
      v6 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey) )
    {
      cbData = 520;
      if ( !RegQueryValueExW(hKey, L"AutoTriggerProfileEntryName", 0, &Type, Data, &cbData) && Type - 1 <= 1 )
      {
        cbData = 520;
        if ( !RegQueryValueExW(hKey, L"AutoTriggerProfilePhonebookPath", 0, &Type, v20, &cbData) && Type - 1 <= 1 )
        {
          v7 = Data;
          v8 = a1 - (_QWORD)Data;
          do
          {
            v9 = *(unsigned __int16 *)&v7[v8];
            v10 = *(unsigned __int16 *)v7 - v9;
            if ( v10 )
              break;
            v7 += 2;
          }
          while ( v9 );
          if ( !v10 )
          {
            v11 = v20;
            v12 = a2 - (_QWORD)v20;
            do
            {
              v13 = *(unsigned __int16 *)&v11[v12];
              v14 = *(unsigned __int16 *)v11 - v13;
              if ( v14 )
                break;
              v11 += 2;
            }
            while ( v13 );
            if ( !v14 )
              v4 = 1;
          }
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x180065d48  push    rbp
0x180065d4a  push    rbx
0x180065d4b  push    rsi
0x180065d4c  push    rdi
0x180065d4d  push    r14
0x180065d4f  lea     rbp, [rsp-370h]
0x180065d57  sub     rsp, 470h
0x180065d5e  mov     rax, cs:__security_cookie
0x180065d65  xor     rax, rsp
0x180065d68  mov     [rbp+390h+var_30], rax
0x180065d6f  mov     rdi, rdx
0x180065d72  mov     [rsp+490h+cbData], 0
0x180065d7a  mov     rsi, rcx
0x180065d7d  mov     [rsp+490h+Type], 0
0x180065d85  mov     r14d, 105h
0x180065d8b  mov     [rsp+490h+hKey], 0
0x180065d94  mov     r8d, r14d; Size
0x180065d97  lea     rcx, [rsp+490h+Data]; void *
0x180065d9c  xor     edx, edx; Val
0x180065d9e  xor     ebx, ebx
0x180065da0  call    memset_0
0x180065da5  mov     r8d, r14d; Size
0x180065da8  lea     rcx, [rbp+390h+var_240]; void *
0x180065daf  xor     edx, edx; Val
0x180065db1  call    memset_0
0x180065db6  test    rdi, rdi
0x180065db9  jz      loc_180065EEA
0x180065dbf  call    StateSepEnabled
0x180065dc4  test    eax, eax
0x180065dc6  lea     rcx, aSystemCurrentc_21; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180065dcd  lea     rax, [rsp+490h+hKey]
0x180065dd2  mov     r9d, 20019h; samDesired
0x180065dd8  lea     rdx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x180065ddf  mov     [rsp+490h+phkResult], rax; phkResult
0x180065de4  cmovz   rdx, rcx; lpSubKey
0x180065de8  xor     r8d, r8d; ulOptions
0x180065deb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180065df2  call    cs:__imp_RegOpenKeyExW
0x180065df8  test    eax, eax
0x180065dfa  jnz     loc_180065EDA
0x180065e00  mov     rcx, [rsp+490h+hKey]; hKey
0x180065e05  lea     rax, [rsp+490h+cbData]
0x180065e0a  mov     [rsp+490h+lpcbData], rax; lpcbData
0x180065e0f  lea     r9, [rsp+490h+Type]; lpType
0x180065e14  lea     rax, [rsp+490h+Data]
0x180065e19  mov     [rsp+490h+cbData], 208h
0x180065e21  xor     r8d, r8d; lpReserved
0x180065e24  mov     [rsp+490h+phkResult], rax; lpData
0x180065e29  lea     rdx, aAutotriggerpro; "AutoTriggerProfileEntryName"
0x180065e30  call    cs:__imp_RegQueryValueExW
0x180065e36  test    eax, eax
0x180065e38  jnz     loc_180065EDA
0x180065e3e  mov     eax, [rsp+490h+Type]
0x180065e42  lea     r14d, [rbx+1]
0x180065e46  dec     eax
0x180065e48  cmp     eax, r14d
0x180065e4b  ja      loc_180065EDA
0x180065e51  mov     rcx, [rsp+490h+hKey]; hKey
0x180065e56  lea     rax, [rsp+490h+cbData]
0x180065e5b  mov     [rsp+490h+lpcbData], rax; lpcbData
0x180065e60  lea     r9, [rsp+490h+Type]; lpType
0x180065e65  lea     rax, [rbp+390h+var_240]
0x180065e6c  mov     [rsp+490h+cbData], 208h
0x180065e74  xor     r8d, r8d; lpReserved
0x180065e77  mov     [rsp+490h+phkResult], rax; lpData
0x180065e7c  lea     rdx, aAutotriggerpro_1; "AutoTriggerProfilePhonebookPath"
0x180065e83  call    cs:__imp_RegQueryValueExW
0x180065e89  test    eax, eax
0x180065e8b  jnz     short loc_180065EDA
0x180065e8d  mov     eax, [rsp+490h+Type]
0x180065e91  dec     eax
0x180065e93  cmp     eax, r14d
0x180065e96  ja      short loc_180065EDA
0x180065e98  lea     rax, [rsp+490h+Data]
0x180065e9d  sub     rsi, rax
0x180065ea0  movzx   ecx, word ptr [rax]
0x180065ea3  movzx   edx, word ptr [rax+rsi]
0x180065ea7  sub     ecx, edx
0x180065ea9  jnz     short loc_180065EB3
0x180065eab  add     rax, 2
0x180065eaf  test    edx, edx
0x180065eb1  jnz     short loc_180065EA0
0x180065eb3  test    ecx, ecx
0x180065eb5  jnz     short loc_180065EDA
0x180065eb7  lea     rax, [rbp+390h+var_240]
0x180065ebe  sub     rdi, rax
0x180065ec1  movzx   edx, word ptr [rax]
0x180065ec4  movzx   ecx, word ptr [rax+rdi]
0x180065ec8  sub     edx, ecx
0x180065eca  jnz     short loc_180065ED4
0x180065ecc  add     rax, 2
0x180065ed0  test    ecx, ecx
0x180065ed2  jnz     short loc_180065EC1
0x180065ed4  test    edx, edx
0x180065ed6  cmovz   ebx, r14d
0x180065eda  mov     rcx, [rsp+490h+hKey]; hKey
0x180065edf  test    rcx, rcx
0x180065ee2  jz      short loc_180065EEA
0x180065ee4  call    cs:__imp_RegCloseKey
0x180065eea  mov     eax, ebx
0x180065eec  mov     rcx, [rbp+390h+var_30]
0x180065ef3  xor     rcx, rsp; StackCookie
0x180065ef6  call    __security_check_cookie
0x180065efb  add     rsp, 470h
0x180065f02  pop     r14
0x180065f04  pop     rdi
0x180065f05  pop     rsi
0x180065f06  pop     rbx
0x180065f07  pop     rbp
0x180065f08  retn
```
