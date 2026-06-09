# ZtRegWriteCertHashes

- ea: `0x1800091cc`
- end: `0x1800092c7`
- name: `ZtRegWriteCertHashes`
- size: `251`
- prototype: `__int64 __fastcall(HKEY hKey, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180009554`

## callees

- `0x1800091cc`
- `0x18000cee8`
- `0x1800125d4`
- `0x1800154c8`
- `0x180015864`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009278`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009278`

## pseudocode

```c
__int64 __fastcall ZtRegWriteCertHashes(HKEY hKey, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  LSTATUS v6; // eax
  int v8; // [rsp+40h] [rbp+8h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp+18h] BYREF

  lpData = 0;
  v8 = 0;
  if ( hKey && a2 )
  {
    v5 = *(unsigned int *)(a2 + 24);
    v4 = 0;
    if ( (_DWORD)v5 )
    {
      v4 = DnsZtCertHashListToString(*(_QWORD *)(a2 + 16), v5, &lpData, &v8);
      if ( !v4 )
      {
        if ( (xmmword_18001F260 & 4) != 0 )
          WPP_SF_S(1026, 0x17u, (ULONGLONG)WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, (const wchar_t *)lpData);
        v6 = RegSetValueExW(hKey, L"ClientCertHashes", 0, 1u, lpData, 2 * v8);
        v4 = v6;
        if ( v6 && (xmmword_18001F260 & 4) != 0 )
          WPP_SF_DS(1026, 0x18u, (ULONGLONG)WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, v6, L"ClientCertHashes");
      }
    }
  }
  else
  {
    v4 = 87;
  }
  Dns_Free(lpData);
  return v4;
}

```

## disassembly

```asm
0x1800091cc  mov     [rsp+arg_8], rbx
0x1800091d1  mov     [rsp+arg_18], rbp
0x1800091d6  push    rdi
0x1800091d7  sub     rsp, 30h
0x1800091db  mov     [rsp+38h+arg_10], 0
0x1800091e4  mov     rax, rdx
0x1800091e7  mov     [rsp+38h+arg_0], 0
0x1800091ef  mov     rdi, rcx
0x1800091f2  test    rcx, rcx
0x1800091f5  jnz     short loc_180009201
0x1800091f7  mov     ebx, 57h ; 'W'
0x1800091fc  jmp     loc_1800092AB
0x180009201  test    rax, rax
0x180009204  jz      short loc_1800091F7
0x180009206  mov     edx, [rdx+18h]
0x180009209  xor     ebx, ebx
0x18000920b  test    edx, edx
0x18000920d  jz      loc_1800092AB
0x180009213  mov     rcx, [rax+10h]
0x180009217  lea     r9, [rsp+38h+arg_0]
0x18000921c  lea     r8, [rsp+38h+arg_10]
0x180009221  call    DnsZtCertHashListToString
0x180009226  mov     ebx, eax
0x180009228  test    eax, eax
0x18000922a  jnz     short loc_1800092AB
0x18000922c  test    byte ptr cs:xmmword_18001F260, 4
0x180009233  jz      short loc_18000924E
0x180009235  mov     r9, [rsp+38h+arg_10]
0x18000923a  lea     edx, [rax+17h]
0x18000923d  mov     ecx, 402h
0x180009242  lea     r8, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids
0x180009249  call    WPP_SF_S
0x18000924e  mov     eax, [rsp+38h+arg_0]
0x180009252  lea     rbp, aClientcerthash; "ClientCertHashes"
0x180009259  add     eax, eax
0x18000925b  mov     r9d, 1; dwType
0x180009261  mov     [rsp+38h+cbData], eax; cbData
0x180009265  xor     r8d, r8d; Reserved
0x180009268  mov     rax, [rsp+38h+arg_10]
0x18000926d  mov     rdx, rbp; lpValueName
0x180009270  mov     rcx, rdi; hKey
0x180009273  mov     [rsp+38h+lpData], rax; lpData
0x180009278  call    cs:__imp_RegSetValueExW
0x18000927e  mov     ebx, eax
0x180009280  test    eax, eax
0x180009282  jz      short loc_1800092AB
0x180009284  test    byte ptr cs:xmmword_18001F260, 4
0x18000928b  jz      short loc_1800092AB
0x18000928d  mov     edx, 18h
0x180009292  mov     [rsp+38h+lpData], rbp
0x180009297  mov     ecx, 402h
0x18000929c  lea     r8, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids
0x1800092a3  mov     r9d, eax
0x1800092a6  call    WPP_SF_DS
0x1800092ab  mov     rcx, [rsp+38h+arg_10]; lpMem
0x1800092b0  call    Dns_Free
0x1800092b5  mov     rbp, [rsp+38h+arg_18]
0x1800092ba  mov     eax, ebx
0x1800092bc  mov     rbx, [rsp+38h+arg_8]
0x1800092c1  add     rsp, 30h
0x1800092c5  pop     rdi
0x1800092c6  retn
```
