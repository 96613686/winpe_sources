# RegGetString

- ea: `0x18003019c`
- end: `0x1800302f8`
- name: `RegGetString`
- size: `348`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001cc9c`

## callees

- `0x18003019c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800301ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800301ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800302d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800302d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003022f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030290`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003022f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030290`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030204`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800302dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030204`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800302dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800302c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800302c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030262`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030262`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030251`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800302ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030251`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800302ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800302b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800302b9`

## pseudocode

```c
BYTE *__fastcall RegGetString(__int64 a1, const WCHAR *a2, const WCHAR *a3)
{
  HKEY v5; // rcx
  LSTATUS v6; // eax
  BYTE *v7; // rbx
  DWORD LastError; // edi
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *lpData; // rax
  HANDLE v12; // rax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  int v16; // [rsp+64h] [rbp+24h]
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  v16 = HIDWORD(a1);
  hKey = 0;
  cbData = 0;
  Type = 0;
  v5 = HKEY_LOCAL_MACHINE;
  if ( a2 )
  {
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey);
    if ( v6 || (v5 = hKey) == 0 )
    {
      SetLastError(v6);
      return 0;
    }
  }
  else
  {
    hKey = HKEY_LOCAL_MACHINE;
  }
  v7 = 0;
  LastError = RegQueryValueExW(v5, a3, 0, &Type, 0, &cbData);
  if ( !LastError )
  {
    if ( Type - 1 <= 1 )
    {
      v9 = cbData;
      ProcessHeap = GetProcessHeap();
      lpData = (BYTE *)HeapAlloc(ProcessHeap, 8u, v9);
      v7 = lpData;
      if ( !lpData )
      {
        LastError = GetLastError();
        goto LABEL_15;
      }
      *(_WORD *)lpData = 0;
      LastError = RegQueryValueExW(hKey, a3, 0, 0, lpData, &cbData);
      if ( !LastError )
      {
        if ( Type - 1 <= 1 )
          goto LABEL_15;
        LastError = 13;
      }
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v7);
      v7 = 0;
      goto LABEL_15;
    }
    LastError = 13;
  }
LABEL_15:
  if ( a2 )
    RegCloseKey(hKey);
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x18003019c  mov     r11, rsp
0x18003019f  mov     [r11+10h], rbx
0x1800301a3  mov     [r11+18h], rsi
0x1800301a7  mov     [r11+8], rcx
0x1800301ab  push    rbp
0x1800301ac  push    rdi
0x1800301ad  push    r14
0x1800301af  mov     rbp, rsp
0x1800301b2  sub     rsp, 40h
0x1800301b6  mov     [rbp+hKey], 0
0x1800301be  mov     r14, r8
0x1800301c1  mov     [rbp+cbData], 0
0x1800301c8  mov     rsi, rdx
0x1800301cb  mov     [rbp+Type], 0
0x1800301d2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800301d9  test    rdx, rdx
0x1800301dc  jz      short loc_180030211
0x1800301de  lea     rax, [rbp+hKey]
0x1800301e2  mov     r9d, 20019h; samDesired
0x1800301e8  xor     r8d, r8d; ulOptions
0x1800301eb  mov     [r11-38h], rax
0x1800301ef  call    cs:__imp_RegOpenKeyExW
0x1800301f5  test    eax, eax
0x1800301f7  jnz     short loc_180030202
0x1800301f9  mov     rcx, [rbp+hKey]
0x1800301fd  test    rcx, rcx
0x180030200  jnz     short loc_180030215
0x180030202  mov     ecx, eax; dwErrCode
0x180030204  call    cs:__imp_SetLastError
0x18003020a  xor     ebx, ebx
0x18003020c  jmp     loc_1800302E2
0x180030211  mov     [rbp+hKey], rcx
0x180030215  lea     rax, [rbp+cbData]
0x180030219  xor     ebx, ebx
0x18003021b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180030220  lea     r9, [rbp+Type]; lpType
0x180030224  xor     r8d, r8d; lpReserved
0x180030227  mov     [rsp+40h+lpData], rbx; lpData
0x18003022c  mov     rdx, r14; lpValueName
0x18003022f  call    cs:__imp_RegQueryValueExW
0x180030235  mov     edi, eax
0x180030237  test    eax, eax
0x180030239  jnz     loc_1800302CB
0x18003023f  mov     eax, [rbp+Type]
0x180030242  dec     eax
0x180030244  cmp     eax, 1
0x180030247  jbe     short loc_18003024E
0x180030249  lea     edi, [rbx+0Dh]
0x18003024c  jmp     short loc_1800302CB
0x18003024e  mov     ebx, [rbp+cbData]
0x180030251  call    cs:__imp_GetProcessHeap
0x180030257  mov     r8d, ebx; dwBytes
0x18003025a  mov     edx, 8; dwFlags
0x18003025f  mov     rcx, rax; hHeap
0x180030262  call    cs:__imp_HeapAlloc
0x180030268  mov     rbx, rax
0x18003026b  test    rax, rax
0x18003026e  jz      short loc_1800302C3
0x180030270  xor     eax, eax
0x180030272  xor     r9d, r9d; lpType
0x180030275  mov     [rbx], ax
0x180030278  xor     r8d, r8d; lpReserved
0x18003027b  mov     rcx, [rbp+hKey]; hKey
0x18003027f  lea     rax, [rbp+cbData]
0x180030283  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180030288  mov     rdx, r14; lpValueName
0x18003028b  mov     [rsp+40h+lpData], rbx; lpData
0x180030290  call    cs:__imp_RegQueryValueExW
0x180030296  mov     edi, eax
0x180030298  test    eax, eax
0x18003029a  jnz     short loc_1800302AB
0x18003029c  mov     eax, [rbp+Type]
0x18003029f  dec     eax
0x1800302a1  cmp     eax, 1
0x1800302a4  jbe     short loc_1800302CB
0x1800302a6  mov     edi, 0Dh
0x1800302ab  call    cs:__imp_GetProcessHeap
0x1800302b1  mov     r8, rbx; lpMem
0x1800302b4  xor     edx, edx; dwFlags
0x1800302b6  mov     rcx, rax; hHeap
0x1800302b9  call    cs:__imp_HeapFree
0x1800302bf  xor     ebx, ebx
0x1800302c1  jmp     short loc_1800302CB
0x1800302c3  call    cs:__imp_GetLastError
0x1800302c9  mov     edi, eax
0x1800302cb  test    rsi, rsi
0x1800302ce  jz      short loc_1800302DA
0x1800302d0  mov     rcx, [rbp+hKey]; hKey
0x1800302d4  call    cs:__imp_RegCloseKey
0x1800302da  mov     ecx, edi; dwErrCode
0x1800302dc  call    cs:__imp_SetLastError
0x1800302e2  mov     rsi, [rsp+40h+arg_10]
0x1800302e7  mov     rax, rbx
0x1800302ea  mov     rbx, [rsp+40h+arg_8]
0x1800302ef  add     rsp, 40h
0x1800302f3  pop     r14
0x1800302f5  pop     rdi
0x1800302f6  pop     rbp
0x1800302f7  retn
```
