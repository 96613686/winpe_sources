# RegGetStringEx

- ea: `0x18004a8d4`
- end: `0x18004aa3c`
- name: `RegGetStringEx`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180048a6c`

## callees

- `0x18004a8d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a997`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a9f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a997`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a9f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004aa03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004aa03`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a9a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a9a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a910`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aa26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a910`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aa26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004a972`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004a9da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004a972`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004a9da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a934`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a934`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004aa1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004aa1e`

## pseudocode

```c
BYTE *__fastcall RegGetStringEx(HKEY a1, const WCHAR *a2, __int64 a3)
{
  DWORD LastError; // ebx
  BYTE *v6; // rdi
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v9; // rax
  HANDLE v10; // rax
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+60h] [rbp+30h] BYREF
  int v13; // [rsp+64h] [rbp+34h]
  DWORD cbData; // [rsp+68h] [rbp+38h] BYREF

  v13 = HIDWORD(a3);
  hKey = 0;
  cbData = 0;
  Type = 0;
  if ( !a1 )
  {
    SetLastError(0x57u);
    return 0;
  }
  if ( !a2 )
  {
    hKey = a1;
    goto LABEL_8;
  }
  LastError = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  if ( !LastError )
  {
    a1 = hKey;
    if ( hKey )
    {
LABEL_8:
      v6 = 0;
      LastError = RegQueryValueExW(a1, L"ImageState", 0, &Type, 0, &cbData);
      if ( LastError )
        goto LABEL_17;
      if ( Type - 1 > 1 )
      {
        LastError = 13;
        goto LABEL_17;
      }
      v7 = cbData;
      ProcessHeap = GetProcessHeap();
      v9 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v7);
      v6 = v9;
      if ( v9 )
      {
        *(_WORD *)v9 = 0;
        LastError = RegQueryValueExW(hKey, L"ImageState", 0, 0, v9, &cbData);
        if ( !LastError )
        {
          if ( Type - 1 <= 1 )
            goto LABEL_17;
          LastError = 13;
        }
        v10 = GetProcessHeap();
        HeapFree(v10, 0, v6);
        v6 = 0;
      }
      else
      {
        LastError = GetLastError();
      }
LABEL_17:
      if ( a2 )
        RegCloseKey(hKey);
      goto LABEL_19;
    }
  }
  v6 = 0;
LABEL_19:
  SetLastError(LastError);
  return v6;
}

```

## disassembly

```asm
0x18004a8d4  mov     [rsp-18h+arg_8], rbx
0x18004a8d9  mov     [rsp-18h+cbData], r9d
0x18004a8de  mov     qword ptr [rsp-18h+Type], r8
0x18004a8e3  push    rbp
0x18004a8e4  push    rsi
0x18004a8e5  push    rdi
0x18004a8e6  mov     rbp, rsp
0x18004a8e9  sub     rsp, 30h
0x18004a8ed  mov     [rbp+hKey], 0
0x18004a8f5  mov     rsi, rdx
0x18004a8f8  mov     [rbp+cbData], 0
0x18004a8ff  mov     [rbp+Type], 0
0x18004a906  test    rcx, rcx
0x18004a909  jnz     short loc_18004A91D
0x18004a90b  mov     ecx, 57h ; 'W'; dwErrCode
0x18004a910  call    cs:__imp_SetLastError
0x18004a916  xor     eax, eax
0x18004a918  jmp     loc_18004AA2F
0x18004a91d  test    rsi, rsi
0x18004a920  jz      short loc_18004A950
0x18004a922  lea     rax, [rbp+hKey]
0x18004a926  mov     r9d, 20019h; samDesired
0x18004a92c  xor     r8d, r8d; ulOptions
0x18004a92f  mov     [rsp+30h+phkResult], rax; phkResult
0x18004a934  call    cs:__imp_RegOpenKeyExW
0x18004a93a  mov     ebx, eax
0x18004a93c  test    eax, eax
0x18004a93e  jnz     short loc_18004A949
0x18004a940  mov     rcx, [rbp+hKey]; hKey
0x18004a944  test    rcx, rcx
0x18004a947  jnz     short loc_18004A954
0x18004a949  xor     edi, edi
0x18004a94b  jmp     loc_18004AA24
0x18004a950  mov     [rbp+hKey], rcx
0x18004a954  lea     rax, [rbp+cbData]
0x18004a958  xor     edi, edi
0x18004a95a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18004a95f  lea     r9, [rbp+Type]; lpType
0x18004a963  xor     r8d, r8d; lpReserved
0x18004a966  mov     [rsp+30h+phkResult], rdi; lpData
0x18004a96b  lea     rdx, KeyName; "ImageState"
0x18004a972  call    cs:__imp_RegQueryValueExW
0x18004a978  mov     ebx, eax
0x18004a97a  test    eax, eax
0x18004a97c  jnz     loc_18004AA15
0x18004a982  mov     eax, [rbp+Type]
0x18004a985  dec     eax
0x18004a987  cmp     eax, 1
0x18004a98a  jbe     short loc_18004A994
0x18004a98c  lea     ebx, [rdi+0Dh]
0x18004a98f  jmp     loc_18004AA15
0x18004a994  mov     ebx, [rbp+cbData]
0x18004a997  call    cs:__imp_GetProcessHeap
0x18004a99d  mov     r8d, ebx; dwBytes
0x18004a9a0  mov     edx, 8; dwFlags
0x18004a9a5  mov     rcx, rax; hHeap
0x18004a9a8  call    cs:__imp_HeapAlloc
0x18004a9ae  mov     rdi, rax
0x18004a9b1  test    rax, rax
0x18004a9b4  jz      short loc_18004AA0D
0x18004a9b6  xor     ecx, ecx
0x18004a9b8  lea     rdx, KeyName; "ImageState"
0x18004a9bf  mov     [rax], cx
0x18004a9c2  xor     r9d, r9d; lpType
0x18004a9c5  mov     rcx, [rbp+hKey]; hKey
0x18004a9c9  lea     rax, [rbp+cbData]
0x18004a9cd  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18004a9d2  xor     r8d, r8d; lpReserved
0x18004a9d5  mov     [rsp+30h+phkResult], rdi; lpData
0x18004a9da  call    cs:__imp_RegQueryValueExW
0x18004a9e0  mov     ebx, eax
0x18004a9e2  test    eax, eax
0x18004a9e4  jnz     short loc_18004A9F5
0x18004a9e6  mov     eax, [rbp+Type]
0x18004a9e9  dec     eax
0x18004a9eb  cmp     eax, 1
0x18004a9ee  jbe     short loc_18004AA15
0x18004a9f0  mov     ebx, 0Dh
0x18004a9f5  call    cs:__imp_GetProcessHeap
0x18004a9fb  mov     r8, rdi; lpMem
0x18004a9fe  xor     edx, edx; dwFlags
0x18004aa00  mov     rcx, rax; hHeap
0x18004aa03  call    cs:__imp_HeapFree
0x18004aa09  xor     edi, edi
0x18004aa0b  jmp     short loc_18004AA15
0x18004aa0d  call    cs:__imp_GetLastError
0x18004aa13  mov     ebx, eax
0x18004aa15  test    rsi, rsi
0x18004aa18  jz      short loc_18004AA24
0x18004aa1a  mov     rcx, [rbp+hKey]; hKey
0x18004aa1e  call    cs:__imp_RegCloseKey
0x18004aa24  mov     ecx, ebx; dwErrCode
0x18004aa26  call    cs:__imp_SetLastError
0x18004aa2c  mov     rax, rdi
0x18004aa2f  mov     rbx, [rsp+30h+arg_8]
0x18004aa34  add     rsp, 30h
0x18004aa38  pop     rdi
0x18004aa39  pop     rsi
0x18004aa3a  pop     rbp
0x18004aa3b  retn
```
