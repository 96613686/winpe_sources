# CVideoObjectDecoder::InitPostProcessingModeFromRegistry(void)

- ea: `0x1800193c8`
- end: `0x180019534`
- name: `?InitPostProcessingModeFromRegistry@CVideoObjectDecoder@@QEAAXXZ`
- size: `364`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001863c`

## callees

- `0x1800193c8`
- `0x18002aac0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019495`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019495`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800194c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800194d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800194e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800194c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800194d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800194e6`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18001942a`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180019447`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180019460`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18001942a`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180019447`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180019460`

## pseudocode

```c
void __fastcall CVideoObjectDecoder::InitPostProcessingModeFromRegistry(CVideoObjectDecoder *this)
{
  int v2; // ebx
  LSTATUS v3; // eax
  unsigned int v4; // ecx
  BOOL v5; // eax
  DWORD Type; // [rsp+30h] [rbp-29h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-25h] BYREF
  HKEY v8; // [rsp+38h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-19h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-11h] BYREF
  BYTE Data[80]; // [rsp+50h] [rbp-9h] BYREF

  Type = 0;
  cbData = 80;
  v8 = 0;
  hKey = 0;
  phkResult = 0;
  v2 = 0;
  if ( !RegOpenKeyW(HKEY_CURRENT_USER, L"SOFTWARE", &phkResult) )
  {
    v3 = RegOpenKeyW(phkResult, L"Microsoft", &hKey);
    if ( v3 )
    {
      if ( v3 == 2 )
        goto LABEL_12;
    }
    else
    {
      v3 = RegOpenKeyW(hKey, L"Scrunch", &v8);
    }
    if ( !v3 && !RegQueryValueExW(v8, L"MPEG4Pt2 Force Post Process Mode", 0, &Type, Data, &cbData) && Type == 4 )
    {
      LOBYTE(v2) = *(_DWORD *)Data >= 4u;
      v4 = *(_DWORD *)Data - 4;
      if ( *(_DWORD *)Data < 4u )
        v4 = *(_DWORD *)Data;
      if ( v4 < 4 )
        *((_DWORD *)this + 1637) = v4;
    }
  }
LABEL_12:
  if ( v8 )
    RegCloseKey(v8);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  v5 = v2 || *((_DWORD *)this + 314) * *((_DWORD *)this + 315) <= 414720;
  *((_DWORD *)this + 1639) = v5;
}

```

## disassembly

```asm
0x1800193c8  mov     [rsp-8+arg_8], rbx
0x1800193cd  mov     [rsp-8+arg_10], rdi
0x1800193d2  push    rbp
0x1800193d3  lea     rbp, [rsp-57h]
0x1800193d8  sub     rsp, 0B0h
0x1800193df  mov     rax, cs:__security_cookie
0x1800193e6  xor     rax, rsp
0x1800193e9  mov     [rbp+57h+var_10], rax
0x1800193ed  mov     rdi, rcx
0x1800193f0  mov     [rbp+57h+Type], 0
0x1800193f7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800193fe  mov     [rbp+57h+cbData], 50h ; 'P'
0x180019405  lea     r8, [rbp+57h+phkResult]; phkResult
0x180019409  mov     [rbp+57h+var_78], 0
0x180019411  lea     rdx, SubKey; "SOFTWARE"
0x180019418  mov     [rbp+57h+hKey], 0
0x180019420  mov     [rbp+57h+phkResult], 0
0x180019428  xor     ebx, ebx
0x18001942a  call    cs:__imp_RegOpenKeyW
0x180019430  test    eax, eax
0x180019432  jnz     loc_1800194BF
0x180019438  mov     rcx, [rbp+57h+phkResult]; hKey
0x18001943c  lea     r8, [rbp+57h+hKey]; phkResult
0x180019440  lea     rdx, aMicrosoft; "Microsoft"
0x180019447  call    cs:__imp_RegOpenKeyW
0x18001944d  test    eax, eax
0x18001944f  jnz     short loc_180019468
0x180019451  mov     rcx, [rbp+57h+hKey]; hKey
0x180019455  lea     r8, [rbp+57h+var_78]; phkResult
0x180019459  lea     rdx, aScrunch; "Scrunch"
0x180019460  call    cs:__imp_RegOpenKeyW
0x180019466  jmp     short loc_18001946D
0x180019468  cmp     eax, 2
0x18001946b  jz      short loc_1800194BF
0x18001946d  test    eax, eax
0x18001946f  jnz     short loc_1800194BF
0x180019471  mov     rcx, [rbp+57h+var_78]; hKey
0x180019475  lea     rax, [rbp+57h+cbData]
0x180019479  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x18001947e  lea     r9, [rbp+57h+Type]; lpType
0x180019482  lea     rax, [rbp+57h+Data]
0x180019486  xor     r8d, r8d; lpReserved
0x180019489  lea     rdx, ValueName; "MPEG4Pt2 Force Post Process Mode"
0x180019490  mov     [rsp+0B0h+lpData], rax; lpData
0x180019495  call    cs:__imp_RegQueryValueExW
0x18001949b  test    eax, eax
0x18001949d  jnz     short loc_1800194BF
0x18001949f  cmp     [rbp+57h+Type], 4
0x1800194a3  jnz     short loc_1800194BF
0x1800194a5  mov     eax, dword ptr [rbp+57h+Data]
0x1800194a8  cmp     eax, 4
0x1800194ab  setnb   bl
0x1800194ae  lea     ecx, [rax-4]
0x1800194b1  cmovb   ecx, eax
0x1800194b4  cmp     ecx, 4
0x1800194b7  jnb     short loc_1800194BF
0x1800194b9  mov     [rdi+1994h], ecx
0x1800194bf  mov     rcx, [rbp+57h+var_78]; hKey
0x1800194c3  test    rcx, rcx
0x1800194c6  jz      short loc_1800194CE
0x1800194c8  call    cs:__imp_RegCloseKey
0x1800194ce  mov     rcx, [rbp+57h+hKey]; hKey
0x1800194d2  test    rcx, rcx
0x1800194d5  jz      short loc_1800194DD
0x1800194d7  call    cs:__imp_RegCloseKey
0x1800194dd  mov     rcx, [rbp+57h+phkResult]; hKey
0x1800194e1  test    rcx, rcx
0x1800194e4  jz      short loc_1800194EC
0x1800194e6  call    cs:__imp_RegCloseKey
0x1800194ec  test    ebx, ebx
0x1800194ee  jnz     short loc_180019508
0x1800194f0  mov     eax, [rdi+4ECh]
0x1800194f6  imul    eax, [rdi+4E8h]
0x1800194fd  cmp     eax, 65400h
0x180019502  jle     short loc_180019508
0x180019504  xor     eax, eax
0x180019506  jmp     short loc_18001950D
0x180019508  mov     eax, 1
0x18001950d  mov     [rdi+199Ch], eax
0x180019513  mov     rcx, [rbp+57h+var_10]
0x180019517  xor     rcx, rsp; StackCookie
0x18001951a  call    __security_check_cookie
0x18001951f  lea     r11, [rsp+0B0h+var_s0]
0x180019527  mov     rbx, [r11+18h]
0x18001952b  mov     rdi, [r11+20h]
0x18001952f  mov     rsp, r11
0x180019532  pop     rbp
0x180019533  retn
```
