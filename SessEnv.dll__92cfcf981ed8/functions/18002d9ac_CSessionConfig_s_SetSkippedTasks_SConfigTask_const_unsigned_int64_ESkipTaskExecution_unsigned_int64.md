# CSessionConfig::s_SetSkippedTasks(SConfigTask const *,unsigned __int64,ESkipTaskExecution *,unsigned __int64 *)

- ea: `0x18002d9ac`
- end: `0x18002daef`
- name: `?s_SetSkippedTasks@CSessionConfig@@SAJPEBUSConfigTask@@_KPEAW4ESkipTaskExecution@@PEA_K@Z`
- size: `323`
- prototype: `__int64 __fastcall(const struct SConfigTask *, unsigned __int64, enum ESkipTaskExecution *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18002c890`
- `0x180030a10`

## callees

- `0x180003f30`
- `0x18002d9ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002da06`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002da06`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002da87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002da87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dada`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dada`

## string_xrefs

- `0x18002da30`: `RegOpenKeyEx REG_CONTROL_TSERVER failed failed: 0x%x in %s`
- `0x18002d9f2`: `System\CurrentControlSet\Control\Terminal Server\ConfigTasks\Skip`
- `0x18002da3a`: `CSessionConfig::s_SetSkippedTasks`

## pseudocode

```c
__int64 __fastcall CSessionConfig::s_SetSkippedTasks(
        LPCWSTR *a1,
        unsigned __int64 a2,
        enum ESkipTaskExecution *a3,
        unsigned __int64 *a4)
{
  LSTATUS v7; // eax
  signed int v8; // ebx
  unsigned __int64 i; // rdi
  LSTATUS v10; // eax
  int v11; // eax
  DWORD cbData; // [rsp+30h] [rbp-18h] BYREF
  DWORD Type; // [rsp+34h] [rbp-14h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  int Data; // [rsp+98h] [rbp+50h] BYREF
  int v17; // [rsp+9Ch] [rbp+54h]

  v17 = HIDWORD(a4);
  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 0;
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\ConfigTasks\\Skip",
         0,
         0x20019u,
         &hKey);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 != 2 )
    {
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      if ( v8 < 0 )
      {
        _DbgPrintMessage(
          8,
          "RegOpenKeyEx REG_CONTROL_TSERVER failed failed: 0x%x in %s",
          (unsigned int)v8,
          "CSessionConfig::s_SetSkippedTasks");
        goto LABEL_22;
      }
    }
  }
  else
  {
    for ( i = 0; i < a2; ++i )
    {
      cbData = 4;
      v10 = RegQueryValueExW(hKey, a1[4 * i + 1], 0, &Type, (LPBYTE)&Data, &cbData);
      if ( (v10 & 0xFFFFFFFD) != 0 )
      {
        v8 = v10 > 0 ? (unsigned __int16)v10 | 0x80070000 : v10;
        if ( v8 < 0 )
        {
          _DbgPrintMessage(
            8,
            "RegQueryValueEx failed failed: 0x%x in %s",
            (unsigned int)v8,
            "CSessionConfig::s_SetSkippedTasks");
          goto LABEL_22;
        }
      }
      if ( !Data || v10 )
      {
        v11 = 0;
      }
      else
      {
        Data = 0;
        v11 = 1;
      }
      *((_DWORD *)a3 + i) = v11;
    }
  }
  v8 = 0;
LABEL_22:
  RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002d9ac  mov     qword ptr [rsp-30h+Data], r9
0x18002d9b1  push    rbp
0x18002d9b2  push    rbx
0x18002d9b3  push    rsi
0x18002d9b4  push    rdi
0x18002d9b5  push    r14
0x18002d9b7  push    r15
0x18002d9b9  mov     rbp, rsp
0x18002d9bc  sub     rsp, 48h
0x18002d9c0  mov     r14, r8
0x18002d9c3  mov     [rbp+hKey], 0
0x18002d9cb  mov     rsi, rdx
0x18002d9ce  mov     [rbp+Data], 0
0x18002d9d5  mov     r15, rcx
0x18002d9d8  mov     [rbp+Type], 0
0x18002d9df  lea     rax, [rbp+hKey]
0x18002d9e3  mov     [rbp+cbData], 0
0x18002d9ea  xor     r8d, r8d; ulOptions
0x18002d9ed  mov     [rsp+48h+phkResult], rax; phkResult
0x18002d9f2  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Ter"...
0x18002d9f9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002da00  mov     r9d, 20019h; samDesired
0x18002da06  call    cs:__imp_RegOpenKeyExW
0x18002da0c  mov     ebx, eax
0x18002da0e  test    eax, eax
0x18002da10  jz      short loc_18002DA50
0x18002da12  cmp     eax, 2
0x18002da15  jz      loc_18002DAD4
0x18002da1b  test    eax, eax
0x18002da1d  jle     short loc_18002DA28
0x18002da1f  movzx   ebx, ax
0x18002da22  or      ebx, 80070000h
0x18002da28  test    ebx, ebx
0x18002da2a  jns     loc_18002DAD4
0x18002da30  lea     rdx, aRegopenkeyexRe_0; "RegOpenKeyEx REG_CONTROL_TSERVER failed"...
0x18002da37  mov     r8d, ebx
0x18002da3a  lea     r9, aCsessionconfig_8; "CSessionConfig::s_SetSkippedTasks"
0x18002da41  mov     ecx, 8; int
0x18002da46  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002da4b  jmp     loc_18002DAD6
0x18002da50  xor     edi, edi
0x18002da52  cmp     rdi, rsi
0x18002da55  jnb     short loc_18002DAD4
0x18002da57  mov     rcx, [rbp+hKey]; hKey
0x18002da5b  lea     rax, [rbp+cbData]
0x18002da5f  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002da64  lea     r9, [rbp+Type]; lpType
0x18002da68  lea     rax, [rbp+Data]
0x18002da6c  mov     [rbp+cbData], 4
0x18002da73  mov     rdx, rdi
0x18002da76  mov     [rsp+48h+phkResult], rax; lpData
0x18002da7b  shl     rdx, 5
0x18002da7f  xor     r8d, r8d; lpReserved
0x18002da82  mov     rdx, [rdx+r15+8]; lpValueName
0x18002da87  call    cs:__imp_RegQueryValueExW
0x18002da8d  test    eax, 0FFFFFFFDh
0x18002da92  jz      short loc_18002DAA9
0x18002da94  test    eax, eax
0x18002da96  jg      short loc_18002DA9C
0x18002da98  mov     ebx, eax
0x18002da9a  jmp     short loc_18002DAA5
0x18002da9c  movzx   ebx, ax
0x18002da9f  or      ebx, 80070000h
0x18002daa5  test    ebx, ebx
0x18002daa7  js      short loc_18002DAC8
0x18002daa9  cmp     [rbp+Data], 0
0x18002daad  jz      short loc_18002DABD
0x18002daaf  test    eax, eax
0x18002dab1  jnz     short loc_18002DABD
0x18002dab3  mov     [rbp+Data], eax
0x18002dab6  mov     eax, 1
0x18002dabb  jmp     short loc_18002DABF
0x18002dabd  xor     eax, eax
0x18002dabf  mov     [r14+rdi*4], eax
0x18002dac3  inc     rdi
0x18002dac6  jmp     short loc_18002DA52
0x18002dac8  lea     rdx, aRegqueryvaluee_8; "RegQueryValueEx failed failed: 0x%x in "...
0x18002dacf  jmp     loc_18002DA37
0x18002dad4  xor     ebx, ebx
0x18002dad6  mov     rcx, [rbp+hKey]; hKey
0x18002dada  call    cs:__imp_RegCloseKey
0x18002dae0  mov     eax, ebx
0x18002dae2  add     rsp, 48h
0x18002dae6  pop     r15
0x18002dae8  pop     r14
0x18002daea  pop     rdi
0x18002daeb  pop     rsi
0x18002daec  pop     rbx
0x18002daed  pop     rbp
0x18002daee  retn
```
