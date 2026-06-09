# EnableStats(ushort const *,int *)

- ea: `0x180018728`
- end: `0x180018853`
- name: `?EnableStats@@YAJPEBGPEAH@Z`
- size: `299`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800117f0`
- `0x180011810`

## callees

- `0x180018728`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180018832`
- `ADVAPI32!RegCloseKey` at `0x180018832`
- `ADVAPI32!RegCreateKeyExW` at `0x1800187a1`
- `ADVAPI32!RegCreateKeyExW` at `0x1800187a1`
- `ADVAPI32!RegSetValueExW` at `0x180018817`
- `ADVAPI32!RegSetValueExW` at `0x180018817`
- `ADVAPI32!RegQueryValueExW` at `0x1800187de`
- `ADVAPI32!RegQueryValueExW` at `0x1800187de`

## pseudocode

```c
__int64 __fastcall EnableStats(LPCWSTR lpSubKey, int *a2)
{
  LSTATUS v3; // ebx
  LSTATUS v4; // eax
  HKEY v5; // rcx
  DWORD Type; // [rsp+50h] [rbp-20h] BYREF
  BYTE v8[4]; // [rsp+54h] [rbp-1Ch] BYREF
  DWORD v9; // [rsp+58h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  int Data; // [rsp+90h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+28h] BYREF

  hKey = 0;
  v9 = 0;
  *(_DWORD *)v8 = 0;
  Data = 0;
  cbData = 0;
  Type = 0;
  v3 = RegCreateKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &v9);
  if ( !v3 )
  {
    cbData = 4;
    Type = 4;
    if ( RegQueryValueExW(hKey, L"Stats", 0, &Type, (LPBYTE)&Data, &cbData) )
      Data = 0;
    *(_DWORD *)v8 = *a2 != 0;
    v4 = RegSetValueExW(hKey, L"Stats", 0, 4u, v8, 4u);
    v5 = hKey;
    v3 = v4;
    *a2 = Data != 0;
    if ( v5 )
      RegCloseKey(v5);
  }
  return v3 != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180018728  mov     r11, rsp
0x18001872b  mov     [r11+8], rbx
0x18001872f  mov     [r11+10h], rdi
0x180018733  push    rbp
0x180018734  mov     rbp, rsp
0x180018737  sub     rsp, 70h
0x18001873b  lea     rax, [rbp+var_18]
0x18001873f  mov     [rbp+hKey], 0
0x180018747  mov     [r11-38h], rax
0x18001874b  mov     rdi, rdx
0x18001874e  lea     rax, [rbp+hKey]
0x180018752  mov     [rbp+var_18], 0
0x180018759  mov     [r11-40h], rax
0x18001875d  mov     rdx, rcx; lpSubKey
0x180018760  mov     qword ptr [r11-48h], 0
0x180018768  xor     r9d, r9d; lpClass
0x18001876b  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x180018773  xor     r8d, r8d; Reserved
0x180018776  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001877d  mov     [rsp+70h+dwOptions], 0; dwOptions
0x180018785  mov     dword ptr [rbp+var_1C], 0
0x18001878c  mov     [rbp+Data], 0
0x180018793  mov     [rbp+cbData], 0
0x18001879a  mov     [rbp+Type], 0
0x1800187a1  call    cs:__imp_RegCreateKeyExW
0x1800187a7  mov     ebx, eax
0x1800187a9  test    eax, eax
0x1800187ab  jnz     loc_180018838
0x1800187b1  mov     rcx, [rbp+hKey]; hKey
0x1800187b5  lea     ebx, [rax+4]
0x1800187b8  lea     rax, [rbp+cbData]
0x1800187bc  mov     [rbp+cbData], ebx
0x1800187bf  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x1800187c4  lea     r9, [rbp+Type]; lpType
0x1800187c8  lea     rax, [rbp+Data]
0x1800187cc  mov     [rbp+Type], ebx
0x1800187cf  xor     r8d, r8d; lpReserved
0x1800187d2  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x1800187d7  lea     rdx, aStats; "Stats"
0x1800187de  call    cs:__imp_RegQueryValueExW
0x1800187e4  test    eax, eax
0x1800187e6  jz      short loc_1800187EF
0x1800187e8  mov     [rbp+Data], 0
0x1800187ef  mov     rcx, [rbp+hKey]; hKey
0x1800187f3  lea     rdx, aStats; "Stats"
0x1800187fa  xor     eax, eax
0x1800187fc  mov     [rsp+70h+samDesired], ebx; cbData
0x180018800  cmp     [rdi], eax
0x180018802  mov     r9d, ebx; dwType
0x180018805  setnz   al
0x180018808  xor     r8d, r8d; Reserved
0x18001880b  mov     dword ptr [rbp+var_1C], eax
0x18001880e  lea     rax, [rbp+var_1C]
0x180018812  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x180018817  call    cs:__imp_RegSetValueExW
0x18001881d  mov     rcx, [rbp+hKey]; hKey
0x180018821  mov     ebx, eax
0x180018823  xor     eax, eax
0x180018825  cmp     [rbp+Data], eax
0x180018828  setnz   al
0x18001882b  mov     [rdi], eax
0x18001882d  test    rcx, rcx
0x180018830  jz      short loc_180018838
0x180018832  call    cs:__imp_RegCloseKey
0x180018838  neg     ebx
0x18001883a  lea     r11, [rsp+70h+var_s0]
0x18001883f  mov     rbx, [r11+10h]
0x180018843  mov     rdi, [r11+18h]
0x180018847  sbb     eax, eax
0x180018849  and     eax, 80004005h
0x18001884e  mov     rsp, r11
0x180018851  pop     rbp
0x180018852  retn
```
