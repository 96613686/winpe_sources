# RegistryAllocAndGetString

- ea: `0x18001a35c`
- end: `0x18001a442`
- name: `RegistryAllocAndGetString`
- size: `230`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001a7a0`

## callees

- `0x18001a35c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a3dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a3dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a3c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a3c6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a3a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a419`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a3a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a419`

## pseudocode

```c
LSTATUS __fastcall RegistryAllocAndGetString(HKEY hKey, __int64 a2, BYTE **a3)
{
  LSTATUS result; // eax
  bool v6; // cc
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *lpData; // rax
  DWORD dwBytes; // [rsp+48h] [rbp+10h] BYREF
  int dwBytes_4; // [rsp+4Ch] [rbp+14h]
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF

  dwBytes_4 = HIDWORD(a2);
  Type = 0;
  dwBytes = 0;
  result = RegQueryValueExW(hKey, L"LastSoapErrorTraceId", 0, &Type, 0, &dwBytes);
  v6 = result <= 0;
  if ( !result )
  {
    if ( Type != 1 )
      return -2147024809;
    v7 = dwBytes;
    ProcessHeap = GetProcessHeap();
    lpData = (BYTE *)HeapAlloc(ProcessHeap, 8u, v7);
    *a3 = lpData;
    if ( !lpData )
      return -2147024882;
    result = RegQueryValueExW(hKey, L"LastSoapErrorTraceId", 0, &Type, lpData, &dwBytes);
    v6 = result <= 0;
  }
  if ( !v6 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001a35c  mov     r11, rsp
0x18001a35f  mov     [r11+8], rbx
0x18001a363  mov     [r11+18h], rsi
0x18001a367  mov     [r11+10h], rdx
0x18001a36b  push    rdi
0x18001a36c  sub     rsp, 30h
0x18001a370  lea     rax, [r11+10h]
0x18001a374  mov     [rsp+38h+Type], 0
0x18001a37c  mov     rsi, r8
0x18001a37f  mov     [r11-10h], rax
0x18001a383  lea     r9, [r11+20h]; lpType
0x18001a387  mov     qword ptr [r11-18h], 0
0x18001a38f  xor     r8d, r8d; lpReserved
0x18001a392  mov     dword ptr [rsp+38h+dwBytes], 0
0x18001a39a  lea     rdx, aLastsoaperrort; "LastSoapErrorTraceId"
0x18001a3a1  mov     rdi, rcx
0x18001a3a4  call    cs:__imp_RegQueryValueExW
0x18001a3ab  nop     dword ptr [rax+rax+00h]
0x18001a3b0  test    eax, eax
0x18001a3b2  jnz     short loc_18001A427
0x18001a3b4  cmp     [rsp+38h+Type], 1
0x18001a3b9  jz      short loc_18001A3C2
0x18001a3bb  mov     eax, 80070057h
0x18001a3c0  jmp     short loc_18001A431
0x18001a3c2  mov     ebx, dword ptr [rsp+38h+dwBytes]
0x18001a3c6  call    cs:__imp_GetProcessHeap
0x18001a3cd  nop     dword ptr [rax+rax+00h]
0x18001a3d2  mov     r8d, ebx; dwBytes
0x18001a3d5  mov     edx, 8; dwFlags
0x18001a3da  mov     rcx, rax; hHeap
0x18001a3dd  call    cs:__imp_HeapAlloc
0x18001a3e4  nop     dword ptr [rax+rax+00h]
0x18001a3e9  mov     [rsi], rax
0x18001a3ec  test    rax, rax
0x18001a3ef  jnz     short loc_18001A3F8
0x18001a3f1  mov     eax, 8007000Eh
0x18001a3f6  jmp     short loc_18001A431
0x18001a3f8  lea     rcx, [rsp+38h+dwBytes]
0x18001a3fd  xor     r8d, r8d; lpReserved
0x18001a400  mov     [rsp+38h+lpcbData], rcx; lpcbData
0x18001a405  lea     r9, [rsp+38h+Type]; lpType
0x18001a40a  mov     rcx, rdi; hKey
0x18001a40d  mov     [rsp+38h+lpData], rax; lpData
0x18001a412  lea     rdx, aLastsoaperrort; "LastSoapErrorTraceId"
0x18001a419  call    cs:__imp_RegQueryValueExW
0x18001a420  nop     dword ptr [rax+rax+00h]
0x18001a425  test    eax, eax
0x18001a427  jle     short loc_18001A431
0x18001a429  movzx   eax, ax
0x18001a42c  or      eax, 80070000h
0x18001a431  mov     rbx, [rsp+38h+arg_0]
0x18001a436  mov     rsi, [rsp+38h+arg_10]
0x18001a43b  add     rsp, 30h
0x18001a43f  pop     rdi
0x18001a440  retn
```
