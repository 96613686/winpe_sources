# GetCurrentProcessWebPlatformVersionUncached

- ea: `0x18000a00c`
- end: `0x18000a0ea`
- name: `GetCurrentProcessWebPlatformVersionUncached`
- size: `222`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007660`

## callees

- `0x18000a00c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a06d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a06d`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x18000a09f`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x18000a09f`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackageOSMaxVersionTested` at `0x18000a0d2`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackageOSMaxVersionTested` at `0x18000a0d2`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetCurrentPackageContext` at `0x18000a0be`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetCurrentPackageContext` at `0x18000a0be`

## pseudocode

```c
__int64 GetCurrentProcessWebPlatformVersionUncached()
{
  LSTATUS ValueW; // ecx
  __int64 result; // rax
  DWORD v2; // [rsp+50h] [rbp+8h] BYREF
  __int64 v3; // [rsp+58h] [rbp+10h] BYREF
  __int64 v4; // [rsp+60h] [rbp+18h] BYREF

  v3 = 0;
  v4 = 0;
  if ( dword_180011958 )
  {
    ValueW = dword_180011938;
  }
  else
  {
    v2 = 8;
    dword_180011958 = 1;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\wwahost.exe",
               L"TestEffectiveWebPlatformVersion",
               0x40u,
               0,
               &qword_180011968,
               &v2);
    dword_180011938 = ValueW;
  }
  if ( ValueW )
  {
    if ( (unsigned int)QuirkIsEnabled(983052) )
    {
      if ( (unsigned int)GetCurrentPackageContext(0, 0, &v4) || (unsigned int)GetPackageOSMaxVersionTested(v4, &v3) )
        return 0;
      else
        return v3;
    }
    else
    {
      return 0x6000400000000LL;
    }
  }
  else
  {
    result = qword_180011968;
    v3 = qword_180011968;
  }
  return result;
}

```

## disassembly

```asm
0x18000a00c  mov     r11, rsp
0x18000a00f  sub     rsp, 48h
0x18000a013  xor     eax, eax
0x18000a015  cmp     cs:dword_180011958, eax
0x18000a01b  mov     [r11+10h], rax
0x18000a01f  mov     [r11+18h], rax
0x18000a023  jnz     short loc_18000A082
0x18000a025  lea     rax, [r11+8]
0x18000a029  mov     [rsp+48h+arg_0], 8
0x18000a031  mov     [r11-18h], rax
0x18000a035  lea     r8, aTesteffectivew; "TestEffectiveWebPlatformVersion"
0x18000a03c  lea     rax, qword_180011968
0x18000a043  mov     cs:dword_180011958, 1
0x18000a04d  mov     [r11-20h], rax
0x18000a051  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000a058  mov     r9d, 40h ; '@'; dwFlags
0x18000a05e  mov     qword ptr [r11-28h], 0
0x18000a066  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000a06d  call    cs:__imp_RegGetValueW
0x18000a073  mov     ecx, eax
0x18000a075  mov     cs:dword_180011938, eax
0x18000a07b  mov     rax, [rsp+48h+arg_8]
0x18000a080  jmp     short loc_18000A088
0x18000a082  mov     ecx, cs:dword_180011938
0x18000a088  test    ecx, ecx
0x18000a08a  jnz     short loc_18000A09A
0x18000a08c  mov     rax, cs:qword_180011968
0x18000a093  mov     [rsp+48h+arg_8], rax
0x18000a098  jmp     short loc_18000A0E5
0x18000a09a  mov     ecx, 0F000Ch
0x18000a09f  call    cs:__imp_QuirkIsEnabled
0x18000a0a5  test    eax, eax
0x18000a0a7  jnz     short loc_18000A0B5
0x18000a0a9  mov     rax, 6000400000000h
0x18000a0b3  jmp     short loc_18000A0E5
0x18000a0b5  lea     r8, [rsp+48h+arg_10]
0x18000a0ba  xor     edx, edx
0x18000a0bc  xor     ecx, ecx
0x18000a0be  call    cs:__imp_GetCurrentPackageContext
0x18000a0c4  test    eax, eax
0x18000a0c6  jnz     short loc_18000A0E3
0x18000a0c8  mov     rcx, [rsp+48h+arg_10]
0x18000a0cd  lea     rdx, [rsp+48h+arg_8]
0x18000a0d2  call    cs:__imp_GetPackageOSMaxVersionTested
0x18000a0d8  test    eax, eax
0x18000a0da  jnz     short loc_18000A0E3
0x18000a0dc  mov     rax, [rsp+48h+arg_8]
0x18000a0e1  jmp     short loc_18000A0E5
0x18000a0e3  xor     eax, eax
0x18000a0e5  add     rsp, 48h
0x18000a0e9  retn
```
