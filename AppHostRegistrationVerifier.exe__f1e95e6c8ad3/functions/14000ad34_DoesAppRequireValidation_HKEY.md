# DoesAppRequireValidation(HKEY__ *)

- ea: `0x14000ad34`
- end: `0x14000ae4e`
- name: `?DoesAppRequireValidation@@YA_NPEAUHKEY__@@@Z`
- size: `282`
- prototype: `bool __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000ed9c`

## callees

- `0x14000ad34`
- `0x14000c2c0`
- `0x14000fbb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000ad6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000add8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000ad6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000add8`

## string_xrefs

- `0x14000ad4c`: `LastValidationAttemptTime`

## pseudocode

```c
bool __fastcall DoesAppRequireValidation(HKEY hKey)
{
  int v2; // eax
  bool v3; // cl
  int v4; // eax
  bool v5; // cl
  unsigned __int64 v6; // rax
  int lpData; // [rsp+20h] [rbp-18h]
  int lpDataa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  __int64 v13; // [rsp+58h] [rbp+20h] BYREF

  v13 = 0;
  cbData = 8;
  v2 = RegQueryValueExW(hKey, L"LastValidationAttemptTime", 0, 0, (LPBYTE)&v13, &cbData);
  v3 = (v2 & 0xFFFFFFFD) == 0;
  if ( v2 > 0 )
    v2 = (unsigned __int16)v2 | 0x80070000;
  if ( !v3 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2C6,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v2,
      lpData);
  Data = 0;
  cbData = 4;
  v4 = RegQueryValueExW(hKey, L"FailedValiationCount", 0, 0, (LPBYTE)&Data, &cbData);
  v5 = (v4 & 0xFFFFFFFD) == 0;
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  if ( !v5 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2CC,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v4,
      lpDataa);
  v6 = (GetCurrentSystemTime() - v13) / 0xC92A69C000LL;
  if ( !Data )
    return (int)v6 > 4;
  return (int)v6 > 7 || (unsigned int)v6 > Data;
}

```

## disassembly

```asm
0x14000ad34  mov     r11, rsp
0x14000ad37  push    rbx
0x14000ad38  sub     rsp, 30h
0x14000ad3c  lea     rax, [r11+10h]
0x14000ad40  mov     qword ptr [r11+20h], 0
0x14000ad48  mov     [r11-10h], rax
0x14000ad4c  lea     rdx, ValueName; "LastValidationAttemptTime"
0x14000ad53  lea     rax, [r11+20h]
0x14000ad57  mov     [rsp+38h+cbData], 8
0x14000ad5f  xor     r9d, r9d; lpType
0x14000ad62  mov     [r11-18h], rax
0x14000ad66  xor     r8d, r8d; lpReserved
0x14000ad69  mov     rbx, rcx
0x14000ad6c  call    cs:__imp_RegQueryValueExW
0x14000ad72  test    eax, 0FFFFFFFDh
0x14000ad77  setz    cl
0x14000ad7a  test    eax, eax
0x14000ad7c  jle     short loc_14000AD86
0x14000ad7e  movzx   eax, ax
0x14000ad81  or      eax, 80070000h
0x14000ad86  test    cl, cl
0x14000ad88  jnz     short loc_14000ADA4
0x14000ad8a  mov     rcx, [rsp+38h]; this
0x14000ad8f  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000ad96  mov     r9d, eax; char *
0x14000ad99  mov     edx, 2C6h; void *
0x14000ad9e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000ada4  lea     rax, [rsp+38h+cbData]
0x14000ada9  mov     [rsp+38h+Data], 0
0x14000adb1  mov     [rsp+38h+lpcbData], rax; lpcbData
0x14000adb6  lea     rdx, aFailedvaliatio; "FailedValiationCount"
0x14000adbd  lea     rax, [rsp+38h+Data]
0x14000adc2  mov     [rsp+38h+cbData], 4
0x14000adca  xor     r9d, r9d; lpType
0x14000adcd  mov     [rsp+38h+lpData], rax; int
0x14000add2  xor     r8d, r8d; lpReserved
0x14000add5  mov     rcx, rbx; hKey
0x14000add8  call    cs:__imp_RegQueryValueExW
0x14000adde  test    eax, 0FFFFFFFDh
0x14000ade3  setz    cl
0x14000ade6  test    eax, eax
0x14000ade8  jle     short loc_14000ADF2
0x14000adea  movzx   eax, ax
0x14000aded  or      eax, 80070000h
0x14000adf2  test    cl, cl
0x14000adf4  jnz     short loc_14000AE10
0x14000adf6  mov     rcx, [rsp+38h]; this
0x14000adfb  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000ae02  mov     r9d, eax; char *
0x14000ae05  mov     edx, 2CCh; void *
0x14000ae0a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000ae10  call    ?GetCurrentSystemTime@@YA_KXZ; GetCurrentSystemTime(void)
0x14000ae15  sub     rax, [rsp+38h+arg_18]
0x14000ae1a  xor     edx, edx
0x14000ae1c  mov     rcx, 0C92A69C000h
0x14000ae26  div     rcx
0x14000ae29  mov     ecx, [rsp+38h+Data]
0x14000ae2d  test    ecx, ecx
0x14000ae2f  jz      short loc_14000AE42
0x14000ae31  cmp     eax, 7
0x14000ae34  jg      short loc_14000AE3E
0x14000ae36  cmp     eax, ecx
0x14000ae38  ja      short loc_14000AE3E
0x14000ae3a  xor     al, al
0x14000ae3c  jmp     short loc_14000AE48
0x14000ae3e  mov     al, 1
0x14000ae40  jmp     short loc_14000AE48
0x14000ae42  cmp     eax, 4
0x14000ae45  setnle  al
0x14000ae48  add     rsp, 30h
0x14000ae4c  pop     rbx
0x14000ae4d  retn
```
