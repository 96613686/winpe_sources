# SetPortugueseReform(Speller::CSpellerDataStorage *,int)

- ea: `0x180096864`
- end: `0x180096945`
- name: `?SetPortugueseReform@@YAXPEAVCSpellerDataStorage@Speller@@H@Z`
- size: `225`
- prototype: `void __fastcall(struct Speller::CSpellerDataStorage *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180097560`

## callees

- `0x180096864`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009692c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009692c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800968b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800968b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800968e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800968e8`

## pseudocode

```c
void __fastcall SetPortugueseReform(struct Speller::CSpellerDataStorage *a1, unsigned int a2)
{
  int v4; // ebx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 4;
  v4 = 1;
  if ( RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Shared Tools\\Proofing Tools\\1.0\\Office",
         0,
         0x11u,
         &hKey)
    || RegQueryValueExW(hKey, L"PortugalModes", 0, &Type, (LPBYTE)&Data, &cbData)
    || Type != 4
    || Data > 3 )
  {
    goto LABEL_9;
  }
  if ( Data == 3 )
  {
    v4 = 0;
    goto LABEL_12;
  }
  if ( Data != 1 )
  {
    if ( Data == 2 )
    {
LABEL_11:
      v4 = 2;
      goto LABEL_12;
    }
LABEL_9:
    if ( (a2 & 0x10000000) != 0 )
    {
      v4 = ((a2 >> 29) & 1) == 0;
      goto LABEL_12;
    }
    goto LABEL_11;
  }
LABEL_12:
  if ( hKey )
    RegCloseKey(hKey);
  *((_DWORD *)a1 + 140) = v4;
}

```

## disassembly

```asm
0x180096864  mov     [rsp-18h+arg_8], rbx
0x180096869  push    rbp
0x18009686a  push    rsi
0x18009686b  push    rdi
0x18009686c  mov     rbp, rsp
0x18009686f  sub     rsp, 40h
0x180096873  mov     edi, edx
0x180096875  mov     [rbp+hKey], 0
0x18009687d  mov     rsi, rcx
0x180096880  mov     [rbp+Type], 0
0x180096887  lea     rax, [rbp+hKey]
0x18009688b  mov     [rbp+Data], 0
0x180096892  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Shared Tools\\Proo"...
0x180096899  mov     [rsp+40h+phkResult], rax; phkResult
0x18009689e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800968a5  mov     [rbp+cbData], 4
0x1800968ac  mov     r9d, 11h; samDesired
0x1800968b2  xor     r8d, r8d; ulOptions
0x1800968b5  call    cs:__imp_RegOpenKeyExW
0x1800968bb  mov     ebx, 1
0x1800968c0  test    eax, eax
0x1800968c2  jnz     short loc_18009690F
0x1800968c4  mov     rcx, [rbp+hKey]; hKey
0x1800968c8  lea     rax, [rbp+cbData]
0x1800968cc  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800968d1  lea     r9, [rbp+Type]; lpType
0x1800968d5  lea     rax, [rbp+Data]
0x1800968d9  xor     r8d, r8d; lpReserved
0x1800968dc  lea     rdx, ValueName; "PortugalModes"
0x1800968e3  mov     [rsp+40h+phkResult], rax; lpData
0x1800968e8  call    cs:__imp_RegQueryValueExW
0x1800968ee  test    eax, eax
0x1800968f0  jnz     short loc_18009690F
0x1800968f2  cmp     [rbp+Type], 4
0x1800968f6  jnz     short loc_18009690F
0x1800968f8  mov     eax, [rbp+Data]
0x1800968fb  cmp     eax, 3
0x1800968fe  ja      short loc_18009690F
0x180096900  jnz     short loc_180096906
0x180096902  xor     ebx, ebx
0x180096904  jmp     short loc_180096923
0x180096906  cmp     eax, ebx
0x180096908  jz      short loc_180096923
0x18009690a  cmp     eax, 2
0x18009690d  jz      short loc_18009691E
0x18009690f  bt      edi, 1Ch
0x180096913  jnb     short loc_18009691E
0x180096915  shr     edi, 1Dh
0x180096918  not     edi
0x18009691a  and     ebx, edi
0x18009691c  jmp     short loc_180096923
0x18009691e  mov     ebx, 2
0x180096923  mov     rcx, [rbp+hKey]; hKey
0x180096927  test    rcx, rcx
0x18009692a  jz      short loc_180096932
0x18009692c  call    cs:__imp_RegCloseKey
0x180096932  mov     [rsi+230h], ebx
0x180096938  mov     rbx, [rsp+40h+arg_8]
0x18009693d  add     rsp, 40h
0x180096941  pop     rdi
0x180096942  pop     rsi
0x180096943  pop     rbp
0x180096944  retn
```
