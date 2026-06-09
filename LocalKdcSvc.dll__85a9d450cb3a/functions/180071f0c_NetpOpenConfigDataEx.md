# NetpOpenConfigDataEx

- ea: `0x180071f0c`
- end: `0x18007200c`
- name: `NetpOpenConfigDataEx`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180037bd0`

## callees

- `0x1800038cc`
- `0x1800038d8`
- `0x18006e434`
- `0x180071f0c`
- `0x180072180`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071fcb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071fcb`

## string_xrefs

- `0x180071f6a`: `System\CurrentControlSet\Services\`

## pseudocode

```c
__int64 __fastcall NetpOpenConfigDataEx(HKEY **a1, __int64 a2, HKEY a3)
{
  HKEY *v4; // rbx
  wchar_t *v6; // rax
  wchar_t *v7; // rdi
  unsigned int v8; // esi
  HKEY phkResult; // [rsp+70h] [rbp+18h] BYREF

  phkResult = a3;
  *a1 = 0;
  v4 = (HKEY *)NetpMemoryAllocate(16);
  if ( !v4 )
    return 8;
  phkResult = 0;
  v6 = (wchar_t *)NetpMemoryAllocate(108);
  v7 = v6;
  if ( !v6 )
  {
    NetpMemoryFree(v4);
    return 8;
  }
  wcscpy_s(v6, 0x36u, L"System\\CurrentControlSet\\Services\\");
  wcscat_s(v7, 0x36u, L"NETLOGON");
  wcscat_s(v7, 0x36u, L"\\");
  wcscat_s(v7, 0x36u, L"Parameters");
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, &phkResult);
  if ( v8 == 2 )
    v8 = 2146;
  NetpMemoryFree(v7);
  if ( v8 )
  {
    NetpMemoryFree(v4);
    v4 = 0;
  }
  else
  {
    *v4 = phkResult;
  }
  *a1 = v4;
  return v8;
}

```

## disassembly

```asm
0x180071f0c  mov     [rsp+arg_10], r8
0x180071f11  push    rbx
0x180071f12  push    rsi
0x180071f13  push    rdi
0x180071f14  push    r14
0x180071f16  sub     rsp, 38h
0x180071f1a  mov     r14, rcx
0x180071f1d  mov     qword ptr [rcx], 0
0x180071f24  mov     ecx, 10h
0x180071f29  call    NetpMemoryAllocate
0x180071f2e  mov     rbx, rax
0x180071f31  test    rax, rax
0x180071f34  jnz     short loc_180071F40
0x180071f36  mov     eax, 8
0x180071f3b  jmp     loc_180072002
0x180071f40  mov     ecx, 6Ch ; 'l'
0x180071f45  mov     [rsp+58h+arg_10], 0
0x180071f4e  call    NetpMemoryAllocate
0x180071f53  mov     rdi, rax
0x180071f56  test    rax, rax
0x180071f59  jnz     short loc_180071F65
0x180071f5b  mov     rcx, rbx
0x180071f5e  call    NetpMemoryFree
0x180071f63  jmp     short loc_180071F36
0x180071f65  mov     esi, 36h ; '6'
0x180071f6a  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\"
0x180071f71  mov     edx, esi; SizeInWords
0x180071f73  mov     rcx, rdi; Destination
0x180071f76  call    wcscpy_s
0x180071f7b  lea     r8, aNetlogon; "NETLOGON"
0x180071f82  mov     edx, esi; SizeInWords
0x180071f84  mov     rcx, rdi; Destination
0x180071f87  call    wcscat_s
0x180071f8c  lea     r8, asc_1800A1204; "\\"
0x180071f93  mov     edx, esi; SizeInWords
0x180071f95  mov     rcx, rdi; Destination
0x180071f98  call    wcscat_s
0x180071f9d  lea     r8, aParameters; "Parameters"
0x180071fa4  mov     edx, esi; SizeInWords
0x180071fa6  mov     rcx, rdi; Destination
0x180071fa9  call    wcscat_s
0x180071fae  lea     rax, [rsp+58h+arg_10]
0x180071fb3  mov     r9d, 20019h; samDesired
0x180071fb9  xor     r8d, r8d; ulOptions
0x180071fbc  mov     [rsp+58h+phkResult], rax; phkResult
0x180071fc1  mov     rdx, rdi; lpSubKey
0x180071fc4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180071fcb  call    cs:__imp_RegOpenKeyExW
0x180071fd1  mov     esi, eax
0x180071fd3  cmp     eax, 2
0x180071fd6  jnz     short loc_180071FDD
0x180071fd8  mov     esi, 862h
0x180071fdd  mov     rcx, rdi
0x180071fe0  call    NetpMemoryFree
0x180071fe5  test    esi, esi
0x180071fe7  jz      short loc_180071FF5
0x180071fe9  mov     rcx, rbx
0x180071fec  call    NetpMemoryFree
0x180071ff1  xor     ebx, ebx
0x180071ff3  jmp     short loc_180071FFD
0x180071ff5  mov     rcx, [rsp+58h+arg_10]
0x180071ffa  mov     [rbx], rcx
0x180071ffd  mov     [r14], rbx
0x180072000  mov     eax, esi
0x180072002  add     rsp, 38h
0x180072006  pop     r14
0x180072008  pop     rdi
0x180072009  pop     rsi
0x18007200a  pop     rbx
0x18007200b  retn
```
