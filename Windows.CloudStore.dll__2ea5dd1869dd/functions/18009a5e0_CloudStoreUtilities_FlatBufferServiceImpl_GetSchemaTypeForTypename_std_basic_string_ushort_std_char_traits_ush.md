# CloudStoreUtilities::FlatBufferServiceImpl::GetSchemaTypeForTypename(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18009a5e0`
- end: `0x18009a70f`
- name: `?GetSchemaTypeForTypename@FlatBufferServiceImpl@CloudStoreUtilities@@UEAA?AW4RegisteredSchemaTypes@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18009a5e0`
- `0x1801201a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a628`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a628`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009a6a7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009a6a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a63d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a6e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a63d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a6e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009a6cc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009a6cc`

## pseudocode

```c
__int64 __fastcall CloudStoreUtilities::FlatBufferServiceImpl::GetSchemaTypeForTypename(__int64 a1, const WCHAR *a2)
{
  LSTATUS v3; // eax
  LSTATUS ValueW; // eax
  bool v6; // zf
  HKEY hKey; // [rsp+40h] [rbp-238h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-230h] BYREF
  WCHAR String1[264]; // [rsp+50h] [rbp-228h] BYREF

  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudStore\\Schema\\",
         0,
         0x20019u,
         &hKey);
  if ( v3 == 2 || v3 == 3 )
    goto LABEL_2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  pcbData = 520;
  ValueW = RegGetValueW(hKey, a2, L"SchemaType", 2u, 0, String1, &pcbData);
  if ( ValueW )
  {
    String1[0] = 0;
    v6 = ValueW == 0;
    if ( ValueW > 0 )
      v6 = 0;
    if ( !v6 )
      goto LABEL_2;
  }
  if ( CompareStringOrdinal(String1, -1, L"FlatBuffers", -1, 1) != 2 )
  {
LABEL_2:
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 1;
  }
}

```

## disassembly

```asm
0x18009a5e0  push    rbx
0x18009a5e2  sub     rsp, 270h
0x18009a5e9  mov     rax, cs:__security_cookie
0x18009a5f0  xor     rax, rsp
0x18009a5f3  mov     [rsp+278h+var_18], rax
0x18009a5fb  mov     rbx, rdx
0x18009a5fe  mov     [rsp+278h+hKey], 0
0x18009a607  lea     rax, [rsp+278h+hKey]
0x18009a60c  mov     r9d, 20019h; samDesired
0x18009a612  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18009a619  mov     [rsp+278h+phkResult], rax; phkResult
0x18009a61e  xor     r8d, r8d; ulOptions
0x18009a621  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009a628  call    cs:__imp_RegOpenKeyExW
0x18009a62e  cmp     eax, 2
0x18009a631  jnz     short loc_18009A65E
0x18009a633  mov     rcx, [rsp+278h+hKey]; hKey
0x18009a638  test    rcx, rcx
0x18009a63b  jz      short loc_18009A643
0x18009a63d  call    cs:__imp_RegCloseKey
0x18009a643  xor     eax, eax
0x18009a645  mov     rcx, [rsp+278h+var_18]
0x18009a64d  xor     rcx, rsp; StackCookie
0x18009a650  call    __security_check_cookie
0x18009a655  add     rsp, 270h
0x18009a65c  pop     rbx
0x18009a65d  retn
0x18009a65e  cmp     eax, 3
0x18009a661  jz      short loc_18009A633
0x18009a663  cmp     qword ptr [rbx+18h], 7
0x18009a668  jbe     short loc_18009A66D
0x18009a66a  mov     rbx, [rbx]
0x18009a66d  mov     rcx, [rsp+278h+hKey]; hkey
0x18009a672  lea     rax, [rsp+278h+var_230]
0x18009a677  mov     [rsp+278h+pcbData], rax; pcbData
0x18009a67c  lea     r8, aSchematype; "SchemaType"
0x18009a683  lea     rax, [rsp+278h+String1]
0x18009a688  mov     [rsp+278h+var_230], 208h
0x18009a690  mov     [rsp+278h+pvData], rax; pvData
0x18009a695  mov     r9d, 2; dwFlags
0x18009a69b  mov     rdx, rbx; lpSubKey
0x18009a69e  mov     [rsp+278h+phkResult], 0; pdwType
0x18009a6a7  call    cs:__imp_RegGetValueW
0x18009a6ad  test    eax, eax
0x18009a6af  jnz     short loc_18009A6F2
0x18009a6b1  or      edx, 0FFFFFFFFh; cchCount1
0x18009a6b4  lea     r8, String2; "FlatBuffers"
0x18009a6bb  mov     ebx, 1
0x18009a6c0  lea     rcx, [rsp+278h+String1]; lpString1
0x18009a6c5  mov     r9d, edx; cchCount2
0x18009a6c8  mov     dword ptr [rsp+278h+phkResult], ebx; bIgnoreCase
0x18009a6cc  call    cs:__imp_CompareStringOrdinal
0x18009a6d2  cmp     eax, 2
0x18009a6d5  jnz     loc_18009A633
0x18009a6db  mov     rcx, [rsp+278h+hKey]; hKey
0x18009a6e0  test    rcx, rcx
0x18009a6e3  jz      short loc_18009A6EB
0x18009a6e5  call    cs:__imp_RegCloseKey
0x18009a6eb  mov     eax, ebx
0x18009a6ed  jmp     loc_18009A645
0x18009a6f2  xor     ecx, ecx
0x18009a6f4  mov     [rsp+278h+String1], cx
0x18009a6f9  test    eax, eax
0x18009a6fb  jle     short loc_18009A707
0x18009a6fd  movzx   eax, ax
0x18009a700  or      eax, 80070000h
0x18009a705  test    eax, eax
0x18009a707  jnz     loc_18009A633
0x18009a70d  jmp     short loc_18009A6B1
```
