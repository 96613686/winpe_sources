# GetHardwareLaunchATApp(int,ushort *,uint)

- ea: `0x140005f00`
- end: `0x140006122`
- name: `?GetHardwareLaunchATApp@@YA_NHPEAGI@Z`
- size: `546`
- prototype: `bool __fastcall(int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400048b8`

## callees

- `0x140005f00`
- `0x140007708`
- `0x140015b00`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140006010`
- `ADVAPI32!RegQueryValueExW` at `0x140006010`
- `ADVAPI32!RegOpenKeyExW` at `0x140005fc2`
- `ADVAPI32!RegOpenKeyExW` at `0x1400060d3`
- `ADVAPI32!RegOpenKeyExW` at `0x140005fc2`
- `ADVAPI32!RegOpenKeyExW` at `0x1400060d3`
- `ADVAPI32!RegCloseKey` at `0x140006078`
- `ADVAPI32!RegCloseKey` at `0x140006078`
- `KERNEL32!CloseHandle` at `0x140005f5d`
- `KERNEL32!CloseHandle` at `0x140005f5d`
- `KERNEL32!OpenMutexW` at `0x140005f4f`
- `KERNEL32!OpenMutexW` at `0x140005f4f`
- `msvcrt!wcscpy_s` at `0x140005f74`
- `msvcrt!wcscpy_s` at `0x140006068`
- `msvcrt!wcscpy_s` at `0x140006094`
- `msvcrt!wcscpy_s` at `0x140005f74`
- `msvcrt!wcscpy_s` at `0x140006068`
- `msvcrt!wcscpy_s` at `0x140006094`

## string_xrefs

- `0x140005fb4`: `Control Panel\Accessibility\SlateLaunch\`
- `0x1400060c5`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\SlateLaunch`

## pseudocode

```c
bool __fastcall GetHardwareLaunchATApp(int a1, unsigned __int16 *a2)
{
  bool v4; // di
  HANDLE v5; // rax
  HKEY v6; // r14
  HKEY v7; // rcx
  int v8; // ebx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v13[3]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Destination[256]; // [rsp+60h] [rbp-A0h] BYREF

  *a2 = 0;
  Destination[0] = 0;
  v4 = 1;
  v5 = OpenMutexW(0x100000u, 0, L"Global\\Windows.Machine.OOBE");
  if ( v5 )
  {
    CloseHandle(v5);
    wcscpy_s(Destination, 0x100u, L"Narrator");
LABEL_16:
    wcscpy_s(a2, 0x100u, Destination);
    return v4;
  }
  v6 = 0;
  Type = 256;
  v13[1] = 0;
  v13[2] = 0;
  hKey = 0;
  if ( a1 )
  {
    if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Accessibility\\SlateLaunch\\", 0, 0x20019u, &hKey) )
    {
      v6 = hKey;
      *(_DWORD *)Data = 0;
      Type = 0;
      v13[0] = hKey;
      v7 = hKey;
      LODWORD(hKey) = 4;
      if ( !RegQueryValueExW(v7, L"LaunchAT", 0, &Type, Data, (LPDWORD)&hKey) && Type == 4 )
      {
        if ( *(_DWORD *)Data )
        {
          Type = 256;
          v8 = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v13, L"ATapp", Destination, &Type);
          goto LABEL_11;
        }
        v4 = 0;
      }
      v8 = 0;
LABEL_11:
      if ( !v8 )
        goto LABEL_13;
    }
LABEL_12:
    wcscpy_s(Destination, 0x100u, L"Narrator");
    goto LABEL_13;
  }
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\SlateLaunch",
         0,
         0x20019u,
         &hKey) )
  {
    goto LABEL_12;
  }
  v6 = hKey;
  v13[0] = hKey;
  if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v13, L"ATapp", Destination, &Type) )
    goto LABEL_12;
  v4 = Type > 1;
LABEL_13:
  if ( v6 )
    RegCloseKey(v6);
  if ( v4 )
    goto LABEL_16;
  return v4;
}

```

## disassembly

```asm
0x140005f00  mov     [rsp-8+arg_0], rbx
0x140005f05  mov     [rsp-8+arg_10], rdi
0x140005f0a  push    rbp
0x140005f0b  push    r14
0x140005f0d  push    r15
0x140005f0f  lea     rbp, [rsp-170h]
0x140005f17  sub     rsp, 270h
0x140005f1e  mov     rax, cs:__security_cookie
0x140005f25  xor     rax, rsp
0x140005f28  mov     [rbp+180h+var_20], rax
0x140005f2f  xor     eax, eax
0x140005f31  lea     r8, Name; "Global\\Windows.Machine.OOBE"
0x140005f38  mov     r15, rdx
0x140005f3b  mov     [rdx], ax
0x140005f3e  mov     ebx, ecx
0x140005f40  mov     [rsp+280h+Destination], ax
0x140005f45  xor     edx, edx; bInheritHandle
0x140005f47  mov     ecx, 100000h; dwDesiredAccess
0x140005f4c  lea     edi, [rax+1]
0x140005f4f  call    cs:__imp_OpenMutexW
0x140005f55  test    rax, rax
0x140005f58  jz      short loc_140005F7F
0x140005f5a  mov     rcx, rax; hObject
0x140005f5d  call    cs:__imp_CloseHandle
0x140005f63  lea     r8, aNarrator_0; "Narrator"
0x140005f6a  mov     edx, 100h; SizeInWords
0x140005f6f  lea     rcx, [rsp+280h+Destination]; Destination
0x140005f74  call    cs:__imp_wcscpy_s
0x140005f7a  jmp     loc_140006087
0x140005f7f  xor     r14d, r14d
0x140005f82  mov     [rsp+280h+Type], 100h
0x140005f8a  xor     r8d, r8d; ulOptions
0x140005f8d  mov     [rsp+280h+var_230], r14
0x140005f92  mov     [rsp+280h+var_228], r14
0x140005f97  lea     rax, [rsp+280h+hKey]
0x140005f9c  mov     [rsp+280h+hKey], r14
0x140005fa1  mov     r9d, 20019h; samDesired
0x140005fa7  mov     [rsp+280h+phkResult], rax; phkResult
0x140005fac  test    ebx, ebx
0x140005fae  jz      loc_1400060C5
0x140005fb4  lea     rdx, SubKey; "Control Panel\\Accessibility\\SlateLaun"...
0x140005fbb  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140005fc2  call    cs:__imp_RegOpenKeyExW
0x140005fc8  test    eax, eax
0x140005fca  jnz     loc_140006057
0x140005fd0  mov     r14, [rsp+280h+hKey]
0x140005fd5  lea     r9, [rsp+280h+Type]; lpType
0x140005fda  mov     dword ptr [rsp+280h+Data], eax
0x140005fde  lea     rdx, ValueName; "LaunchAT"
0x140005fe5  mov     [rsp+280h+Type], eax
0x140005fe9  xor     r8d, r8d; lpReserved
0x140005fec  lea     rax, [rsp+280h+hKey]
0x140005ff1  mov     [rsp+280h+var_238], r14
0x140005ff6  mov     [rsp+280h+lpcbData], rax; lpcbData
0x140005ffb  mov     rcx, r14; hKey
0x140005ffe  lea     rax, [rsp+280h+Data]
0x140006003  mov     dword ptr [rsp+280h+hKey], 4
0x14000600b  mov     [rsp+280h+phkResult], rax; lpData
0x140006010  call    cs:__imp_RegQueryValueExW
0x140006016  test    eax, eax
0x140006018  jnz     short loc_140006051
0x14000601a  cmp     [rsp+280h+Type], 4
0x14000601f  jnz     short loc_140006051
0x140006021  cmp     dword ptr [rsp+280h+Data], eax
0x140006025  jz      short loc_14000604E
0x140006027  lea     r9, [rsp+280h+Type]; unsigned int *
0x14000602c  mov     [rsp+280h+Type], 100h
0x140006034  lea     r8, [rsp+280h+Destination]; unsigned __int16 *
0x140006039  lea     rdx, aAtapp; "ATapp"
0x140006040  lea     rcx, [rsp+280h+var_238]; this
0x140006045  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14000604a  mov     ebx, eax
0x14000604c  jmp     short loc_140006053
0x14000604e  xor     dil, dil
0x140006051  xor     ebx, ebx
0x140006053  test    ebx, ebx
0x140006055  jz      short loc_140006070
0x140006057  lea     r8, aNarrator_0; "Narrator"
0x14000605e  mov     edx, 100h; SizeInWords
0x140006063  lea     rcx, [rsp+280h+Destination]; Destination
0x140006068  call    cs:__imp_wcscpy_s
0x14000606e  xor     ebx, ebx
0x140006070  test    r14, r14
0x140006073  jz      short loc_14000607E
0x140006075  mov     rcx, r14; hKey
0x140006078  call    cs:__imp_RegCloseKey
0x14000607e  test    ebx, ebx
0x140006080  jnz     short loc_14000609A
0x140006082  test    dil, dil
0x140006085  jz      short loc_14000609A
0x140006087  lea     r8, [rsp+280h+Destination]; Source
0x14000608c  mov     edx, 100h; SizeInWords
0x140006091  mov     rcx, r15; Destination
0x140006094  call    cs:__imp_wcscpy_s
0x14000609a  mov     al, dil
0x14000609d  mov     rcx, [rbp+180h+var_20]
0x1400060a4  xor     rcx, rsp; StackCookie
0x1400060a7  call    __security_check_cookie
0x1400060ac  lea     r11, [rsp+280h+var_10]
0x1400060b4  mov     rbx, [r11+20h]
0x1400060b8  mov     rdi, [r11+30h]
0x1400060bc  mov     rsp, r11
0x1400060bf  pop     r15
0x1400060c1  pop     r14
0x1400060c3  pop     rbp
0x1400060c4  retn
0x1400060c5  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400060cc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400060d3  call    cs:__imp_RegOpenKeyExW
0x1400060d9  test    eax, eax
0x1400060db  jnz     loc_140006057
0x1400060e1  mov     r14, [rsp+280h+hKey]
0x1400060e6  lea     r9, [rsp+280h+Type]; unsigned int *
0x1400060eb  lea     r8, [rsp+280h+Destination]; unsigned __int16 *
0x1400060f0  mov     [rsp+280h+var_238], r14
0x1400060f5  lea     rdx, aAtapp; "ATapp"
0x1400060fc  lea     rcx, [rsp+280h+var_238]; this
0x140006101  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x140006106  mov     ebx, eax
0x140006108  test    eax, eax
0x14000610a  jnz     loc_140006057
0x140006110  cmp     [rsp+280h+Type], edi
0x140006114  ja      loc_140006070
0x14000611a  xor     dil, dil
0x14000611d  jmp     loc_140006070
```
