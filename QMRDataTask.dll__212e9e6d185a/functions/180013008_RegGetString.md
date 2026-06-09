# RegGetString

- ea: `0x180013008`
- end: `0x18001315f`
- name: `RegGetString`
- size: `343`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f418`

## callees

- `0x180013008`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001312e`
- `KERNEL32!GetLastError` at `0x18001312e`
- `KERNEL32!GetProcessHeap` at `0x1800130b8`
- `KERNEL32!GetProcessHeap` at `0x180013116`
- `KERNEL32!GetProcessHeap` at `0x1800130b8`
- `KERNEL32!GetProcessHeap` at `0x180013116`
- `KERNEL32!HeapAlloc` at `0x1800130c9`
- `KERNEL32!HeapAlloc` at `0x1800130c9`
- `KERNEL32!HeapFree` at `0x180013124`
- `KERNEL32!HeapFree` at `0x180013124`
- `KERNEL32!SetLastError` at `0x180013142`
- `KERNEL32!SetLastError` at `0x18001314c`
- `KERNEL32!SetLastError` at `0x180013142`
- `KERNEL32!SetLastError` at `0x18001314c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001313a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001313a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013093`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800130fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013093`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800130fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001305a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001305a`

## pseudocode

```c
BYTE *__fastcall RegGetString(HKEY a1, __int64 a2, __int64 a3)
{
  DWORD v3; // ecx
  LSTATUS v4; // eax
  BYTE *v5; // rbx
  DWORD LastError; // edi
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v9; // rax
  HANDLE v10; // rax
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF
  int v14; // [rsp+5Ch] [rbp+2Ch]
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  int v16; // [rsp+64h] [rbp+34h]

  v16 = HIDWORD(a3);
  v14 = HIDWORD(a2);
  hKey = 0;
  cbData = 0;
  Type = 0;
  if ( !a1 )
  {
    v3 = 87;
LABEL_16:
    SetLastError(v3);
    return 0;
  }
  v4 = RegOpenKeyExW(a1, L"Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, &hKey);
  if ( v4 || !hKey )
  {
    v3 = v4;
    goto LABEL_16;
  }
  v5 = 0;
  LastError = RegQueryValueExW(hKey, L"EditionID", 0, &Type, 0, &cbData);
  if ( !LastError )
  {
    if ( Type - 1 <= 1 )
    {
      v7 = cbData;
      ProcessHeap = GetProcessHeap();
      v9 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v7);
      v5 = v9;
      if ( !v9 )
      {
        LastError = GetLastError();
        goto LABEL_14;
      }
      *(_WORD *)v9 = 0;
      LastError = RegQueryValueExW(hKey, L"EditionID", 0, 0, v9, &cbData);
      if ( !LastError )
      {
        if ( Type - 1 <= 1 )
          goto LABEL_14;
        LastError = 13;
      }
      v10 = GetProcessHeap();
      HeapFree(v10, 0, v5);
      v5 = 0;
      goto LABEL_14;
    }
    LastError = 13;
  }
LABEL_14:
  RegCloseKey(hKey);
  SetLastError(LastError);
  return v5;
}

```

## disassembly

```asm
0x180013008  mov     qword ptr [rsp-18h+cbData], r8
0x18001300d  mov     qword ptr [rsp-18h+Type], rdx
0x180013012  push    rbp
0x180013013  push    rbx
0x180013014  push    rdi
0x180013015  mov     rbp, rsp
0x180013018  sub     rsp, 30h
0x18001301c  mov     [rbp+hKey], 0
0x180013024  mov     [rbp+cbData], 0
0x18001302b  mov     [rbp+Type], 0
0x180013032  test    rcx, rcx
0x180013035  jnz     short loc_180013041
0x180013037  mov     ecx, 57h ; 'W'; hKey
0x18001303c  jmp     loc_18001314C
0x180013041  lea     rax, [rbp+hKey]
0x180013045  mov     r9d, 20019h; samDesired
0x18001304b  xor     r8d, r8d; ulOptions
0x18001304e  mov     [rsp+30h+phkResult], rax; phkResult
0x180013053  lea     rdx, aMicrosoftWindo_0; "Microsoft\\Windows NT\\CurrentVersion"
0x18001305a  call    cs:__imp_RegOpenKeyExW
0x180013060  test    eax, eax
0x180013062  jnz     loc_18001314A
0x180013068  mov     rcx, [rbp+hKey]; hKey
0x18001306c  test    rcx, rcx
0x18001306f  jz      loc_18001314A
0x180013075  lea     rax, [rbp+cbData]
0x180013079  xor     ebx, ebx
0x18001307b  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180013080  lea     r9, [rbp+Type]; lpType
0x180013084  xor     r8d, r8d; lpReserved
0x180013087  mov     [rsp+30h+phkResult], rbx; lpData
0x18001308c  lea     rdx, aEditionid; "EditionID"
0x180013093  call    cs:__imp_RegQueryValueExW
0x180013099  mov     edi, eax
0x18001309b  test    eax, eax
0x18001309d  jnz     loc_180013136
0x1800130a3  mov     eax, [rbp+Type]
0x1800130a6  dec     eax
0x1800130a8  cmp     eax, 1
0x1800130ab  jbe     short loc_1800130B5
0x1800130ad  lea     edi, [rbx+0Dh]
0x1800130b0  jmp     loc_180013136
0x1800130b5  mov     ebx, [rbp+cbData]
0x1800130b8  call    cs:__imp_GetProcessHeap
0x1800130be  mov     r8d, ebx; dwBytes
0x1800130c1  mov     edx, 8; dwFlags
0x1800130c6  mov     rcx, rax; hHeap
0x1800130c9  call    cs:__imp_HeapAlloc
0x1800130cf  mov     rbx, rax
0x1800130d2  test    rax, rax
0x1800130d5  jz      short loc_18001312E
0x1800130d7  xor     eax, eax
0x1800130d9  lea     rdx, aEditionid; "EditionID"
0x1800130e0  mov     [rbx], ax
0x1800130e3  xor     r9d, r9d; lpType
0x1800130e6  mov     rcx, [rbp+hKey]; hKey
0x1800130ea  lea     rax, [rbp+cbData]
0x1800130ee  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800130f3  xor     r8d, r8d; lpReserved
0x1800130f6  mov     [rsp+30h+phkResult], rbx; lpData
0x1800130fb  call    cs:__imp_RegQueryValueExW
0x180013101  mov     edi, eax
0x180013103  test    eax, eax
0x180013105  jnz     short loc_180013116
0x180013107  mov     eax, [rbp+Type]
0x18001310a  dec     eax
0x18001310c  cmp     eax, 1
0x18001310f  jbe     short loc_180013136
0x180013111  mov     edi, 0Dh
0x180013116  call    cs:__imp_GetProcessHeap
0x18001311c  mov     r8, rbx; lpMem
0x18001311f  xor     edx, edx; dwFlags
0x180013121  mov     rcx, rax; hHeap
0x180013124  call    cs:__imp_HeapFree
0x18001312a  xor     ebx, ebx
0x18001312c  jmp     short loc_180013136
0x18001312e  call    cs:__imp_GetLastError
0x180013134  mov     edi, eax
0x180013136  mov     rcx, [rbp+hKey]; hKey
0x18001313a  call    cs:__imp_RegCloseKey
0x180013140  mov     ecx, edi; dwErrCode
0x180013142  call    cs:__imp_SetLastError
0x180013148  jmp     short loc_180013154
0x18001314a  mov     ecx, eax; dwErrCode
0x18001314c  call    cs:__imp_SetLastError
0x180013152  xor     ebx, ebx
0x180013154  mov     rax, rbx
0x180013157  add     rsp, 30h
0x18001315b  pop     rdi
0x18001315c  pop     rbx
0x18001315d  pop     rbp
0x18001315e  retn
```
