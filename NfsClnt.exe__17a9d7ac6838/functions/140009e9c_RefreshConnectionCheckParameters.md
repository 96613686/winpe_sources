# RefreshConnectionCheckParameters

- ea: `0x140009e9c`
- end: `0x14000a0a7`
- name: `RefreshConnectionCheckParameters`
- size: `523`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007dd0`

## callees

- `0x140009e9c`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x140009f26`
- `ADVAPI32!RegGetValueW` at `0x140009f70`
- `ADVAPI32!RegGetValueW` at `0x140009fd1`
- `ADVAPI32!RegGetValueW` at `0x14000a036`
- `ADVAPI32!RegGetValueW` at `0x140009f26`
- `ADVAPI32!RegGetValueW` at `0x140009f70`
- `ADVAPI32!RegGetValueW` at `0x140009fd1`
- `ADVAPI32!RegGetValueW` at `0x14000a036`
- `KERNEL32!GetTickCount64` at `0x140009ec3`
- `KERNEL32!GetTickCount64` at `0x140009ec3`

## string_xrefs

- `0x140009f43`: `ConnectionCheckConfigurationRefresh`

## pseudocode

```c
__int64 RefreshConnectionCheckParameters()
{
  ULONGLONG TickCount64; // rdi
  int v1; // esi
  __int64 v2; // r14
  __int64 v3; // r12
  __int64 v4; // r15
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // ecx
  DWORD pcbData; // [rsp+70h] [rbp+30h] BYREF
  unsigned int pvData; // [rsp+78h] [rbp+38h] BYREF

  pvData = 0;
  pcbData = 0;
  TickCount64 = GetTickCount64();
  if ( qword_140021B88 + qword_140021B90 < TickCount64 )
  {
    v1 = 0;
    v2 = 60;
    v3 = 60;
    pcbData = 4;
    v4 = 10;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
            L"EnableUdpFailover",
            0x18u,
            0,
            &pvData,
            &pcbData) )
      LOBYTE(v1) = pvData != 0;
    pcbData = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
            L"ConnectionCheckConfigurationRefresh",
            0x18u,
            0,
            &pvData,
            &pcbData) )
    {
      if ( pvData <= 1 || (v5 = 600, pvData < 0x258) )
      {
        v5 = 1;
        if ( pvData > 1 )
          v5 = pvData;
      }
      v3 = v5;
    }
    pcbData = 4;
    v6 = 3600;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
            L"ConnectionCheckExpirationPresent",
            0x18u,
            0,
            &pvData,
            &pcbData) )
    {
      if ( pvData < 0xE10 )
      {
        v7 = 0;
        if ( pvData )
          v7 = pvData;
      }
      else
      {
        v7 = 3600;
      }
      v2 = v7;
    }
    pcbData = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
            L"ConnectionCheckExpirationAbsent",
            0x18u,
            0,
            &pvData,
            &pcbData) )
    {
      if ( pvData < 0xE10 )
      {
        v6 = 0;
        if ( pvData )
          v6 = pvData;
      }
      v4 = v6;
    }
    dword_140021B70 = v1;
    qword_140021B78 = 1000 * v2;
    qword_140021B90 = TickCount64;
    qword_140021B80 = 1000 * v4;
    qword_140021B88 = 1000 * v3;
  }
  return 0;
}

```

## disassembly

```asm
0x140009e9c  mov     [rsp-28h+arg_10], rbx
0x140009ea1  mov     [rsp-28h+arg_18], rsi
0x140009ea6  push    rbp
0x140009ea7  push    rdi
0x140009ea8  push    r12
0x140009eaa  push    r14
0x140009eac  push    r15
0x140009eae  mov     rbp, rsp
0x140009eb1  sub     rsp, 40h
0x140009eb5  mov     [rbp+arg_8], 0
0x140009ebc  mov     [rbp+arg_0], 0
0x140009ec3  call    cs:__imp_GetTickCount64
0x140009ec9  mov     rdx, cs:qword_140021B90
0x140009ed0  mov     rdi, rax
0x140009ed3  add     rdx, cs:qword_140021B88
0x140009eda  cmp     rdx, rax
0x140009edd  jnb     loc_14000A08C
0x140009ee3  xor     esi, esi
0x140009ee5  lea     rax, [rbp+arg_0]
0x140009ee9  mov     [rsp+40h+pcbData], rax; pcbData
0x140009eee  lea     r8, Value; "EnableUdpFailover"
0x140009ef5  lea     rax, [rbp+arg_8]
0x140009ef9  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140009f00  mov     [rsp+40h+pvData], rax; pvData
0x140009f05  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x140009f0c  lea     r14d, [rsi+3Ch]
0x140009f10  mov     [rsp+40h+pdwType], rsi; pdwType
0x140009f15  lea     ebx, [rsi+4]
0x140009f18  mov     r12d, r14d
0x140009f1b  lea     r9d, [rsi+18h]; dwFlags
0x140009f1f  mov     [rbp+arg_0], ebx
0x140009f22  lea     r15d, [rsi+0Ah]
0x140009f26  call    cs:__imp_RegGetValueW
0x140009f2c  test    eax, eax
0x140009f2e  jnz     short loc_140009F37
0x140009f30  cmp     [rbp+arg_8], esi
0x140009f33  setnz   sil
0x140009f37  lea     rax, [rbp+arg_0]
0x140009f3b  mov     [rbp+arg_0], ebx
0x140009f3e  mov     [rsp+40h+pcbData], rax; pcbData
0x140009f43  lea     r8, aConnectionchec; "ConnectionCheckConfigurationRefresh"
0x140009f4a  lea     rax, [rbp+arg_8]
0x140009f4e  mov     r9d, 18h; dwFlags
0x140009f54  mov     [rsp+40h+pvData], rax; pvData
0x140009f59  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x140009f60  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140009f67  mov     [rsp+40h+pdwType], 0; pdwType
0x140009f70  call    cs:__imp_RegGetValueW
0x140009f76  test    eax, eax
0x140009f78  jnz     short loc_140009F98
0x140009f7a  mov     ecx, [rbp+arg_8]
0x140009f7d  cmp     ecx, 1
0x140009f80  jbe     short loc_140009F8B
0x140009f82  mov     eax, 258h
0x140009f87  cmp     ecx, eax
0x140009f89  jnb     short loc_140009F95
0x140009f8b  mov     eax, 1
0x140009f90  cmp     ecx, eax
0x140009f92  cmova   eax, ecx
0x140009f95  mov     r12d, eax
0x140009f98  lea     rax, [rbp+arg_0]
0x140009f9c  mov     [rbp+arg_0], ebx
0x140009f9f  mov     [rsp+40h+pcbData], rax; pcbData
0x140009fa4  lea     r8, aConnectionchec_1; "ConnectionCheckExpirationPresent"
0x140009fab  lea     rax, [rbp+arg_8]
0x140009faf  mov     r9d, 18h; dwFlags
0x140009fb5  mov     [rsp+40h+pvData], rax; pvData
0x140009fba  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x140009fc1  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140009fc8  mov     [rsp+40h+pdwType], 0; pdwType
0x140009fd1  call    cs:__imp_RegGetValueW
0x140009fd7  mov     ebx, 0E10h
0x140009fdc  test    eax, eax
0x140009fde  jnz     short loc_140009FF9
0x140009fe0  mov     eax, [rbp+arg_8]
0x140009fe3  test    eax, eax
0x140009fe5  jz      short loc_140009FEF
0x140009fe7  cmp     eax, ebx
0x140009fe9  jb      short loc_140009FEF
0x140009feb  mov     ecx, ebx
0x140009fed  jmp     short loc_140009FF6
0x140009fef  xor     ecx, ecx
0x140009ff1  test    eax, eax
0x140009ff3  cmovnz  ecx, eax
0x140009ff6  mov     r14d, ecx
0x140009ff9  lea     rax, [rbp+arg_0]
0x140009ffd  mov     [rbp+arg_0], 4
0x14000a004  mov     [rsp+40h+pcbData], rax; pcbData
0x14000a009  lea     r8, aConnectionchec_0; "ConnectionCheckExpirationAbsent"
0x14000a010  lea     rax, [rbp+arg_8]
0x14000a014  mov     r9d, 18h; dwFlags
0x14000a01a  mov     [rsp+40h+pvData], rax; pvData
0x14000a01f  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x14000a026  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14000a02d  mov     [rsp+40h+pdwType], 0; pdwType
0x14000a036  call    cs:__imp_RegGetValueW
0x14000a03c  test    eax, eax
0x14000a03e  jnz     short loc_14000A055
0x14000a040  mov     eax, [rbp+arg_8]
0x14000a043  test    eax, eax
0x14000a045  jz      short loc_14000A04B
0x14000a047  cmp     eax, ebx
0x14000a049  jnb     short loc_14000A052
0x14000a04b  xor     ebx, ebx
0x14000a04d  test    eax, eax
0x14000a04f  cmovnz  ebx, eax
0x14000a052  mov     r15d, ebx
0x14000a055  imul    rax, r14, 3E8h
0x14000a05c  mov     cs:dword_140021B70, esi
0x14000a062  mov     cs:qword_140021B78, rax
0x14000a069  imul    rax, r15, 3E8h
0x14000a070  mov     cs:qword_140021B90, rdi
0x14000a077  mov     cs:qword_140021B80, rax
0x14000a07e  imul    rax, r12, 3E8h
0x14000a085  mov     cs:qword_140021B88, rax
0x14000a08c  lea     r11, [rsp+40h+var_s0]
0x14000a091  xor     eax, eax
0x14000a093  mov     rbx, [r11+40h]
0x14000a097  mov     rsi, [r11+48h]
0x14000a09b  mov     rsp, r11
0x14000a09e  pop     r15
0x14000a0a0  pop     r14
0x14000a0a2  pop     r12
0x14000a0a4  pop     rdi
0x14000a0a5  pop     rbp
0x14000a0a6  retn
```
