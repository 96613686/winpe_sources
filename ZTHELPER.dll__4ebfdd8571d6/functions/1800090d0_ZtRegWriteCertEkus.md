# ZtRegWriteCertEkus

- ea: `0x1800090d0`
- end: `0x1800091c4`
- name: `ZtRegWriteCertEkus`
- size: `244`
- prototype: `__int64 __fastcall(HKEY hKey, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180009554`

## callees

- `0x1800090d0`
- `0x18000d0a0`
- `0x1800125d4`
- `0x1800154c8`
- `0x180015864`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009172`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009172`

## pseudocode

```c
__int64 __fastcall ZtRegWriteCertEkus(HKEY hKey, __int64 a2)
{
  BYTE *lpData; // rdi
  unsigned int v5; // ebx
  __int64 v6; // rdx
  LSTATUS v7; // eax
  int v9; // [rsp+50h] [rbp+8h] BYREF
  BYTE *v10; // [rsp+60h] [rbp+18h] BYREF

  lpData = 0;
  v10 = 0;
  v9 = 0;
  if ( hKey && a2 )
  {
    v6 = *(unsigned int *)(a2 + 40);
    v5 = 0;
    if ( (_DWORD)v6 )
    {
      v5 = DnsZtEkusToString(*(_QWORD *)(a2 + 32), v6, &v10, &v9);
      if ( v5 )
      {
        lpData = v10;
      }
      else
      {
        lpData = v10;
        if ( (xmmword_18001F260 & 4) != 0 )
          WPP_SF_S(1026, 0x19u, (ULONGLONG)WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, (const wchar_t *)v10);
        v7 = RegSetValueExW(hKey, L"ClientCertEkus", 0, 1u, lpData, 2 * v9);
        v5 = v7;
        if ( v7 && (xmmword_18001F260 & 4) != 0 )
          WPP_SF_DS(1026, 0x1Au, (ULONGLONG)WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, v7, L"ClientCertEkus");
      }
    }
  }
  else
  {
    v5 = 87;
  }
  Dns_Free(lpData);
  return v5;
}

```

## disassembly

```asm
0x1800090d0  mov     [rsp+arg_8], rbx
0x1800090d5  push    rsi
0x1800090d6  push    rdi
0x1800090d7  push    r14
0x1800090d9  sub     rsp, 30h
0x1800090dd  xor     edi, edi
0x1800090df  mov     rax, rdx
0x1800090e2  mov     [rsp+48h+arg_10], rdi
0x1800090e7  mov     rsi, rcx
0x1800090ea  mov     [rsp+48h+arg_0], edi
0x1800090ee  test    rcx, rcx
0x1800090f1  jnz     short loc_1800090FD
0x1800090f3  mov     ebx, 57h ; 'W'
0x1800090f8  jmp     loc_1800091AC
0x1800090fd  test    rax, rax
0x180009100  jz      short loc_1800090F3
0x180009102  mov     edx, [rdx+28h]
0x180009105  xor     ebx, ebx
0x180009107  test    edx, edx
0x180009109  jz      loc_1800091AC
0x18000910f  mov     rcx, [rax+20h]
0x180009113  lea     r9, [rsp+48h+arg_0]
0x180009118  lea     r8, [rsp+48h+arg_10]
0x18000911d  call    DnsZtEkusToString
0x180009122  mov     ebx, eax
0x180009124  test    eax, eax
0x180009126  jnz     short loc_1800091A7
0x180009128  test    byte ptr cs:xmmword_18001F260, 4
0x18000912f  mov     rdi, [rsp+48h+arg_10]
0x180009134  jz      short loc_18000914D
0x180009136  lea     edx, [rax+19h]
0x180009139  mov     ecx, 402h
0x18000913e  mov     r9, rdi
0x180009141  lea     r8, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids
0x180009148  call    WPP_SF_S
0x18000914d  mov     eax, [rsp+48h+arg_0]
0x180009151  lea     r14, aClientcertekus; "ClientCertEkus"
0x180009158  add     eax, eax
0x18000915a  mov     r9d, 1; dwType
0x180009160  mov     [rsp+48h+cbData], eax; cbData
0x180009164  xor     r8d, r8d; Reserved
0x180009167  mov     rdx, r14; lpValueName
0x18000916a  mov     [rsp+48h+lpData], rdi; lpData
0x18000916f  mov     rcx, rsi; hKey
0x180009172  call    cs:__imp_RegSetValueExW
0x180009178  mov     ebx, eax
0x18000917a  test    eax, eax
0x18000917c  jz      short loc_1800091AC
0x18000917e  test    byte ptr cs:xmmword_18001F260, 4
0x180009185  jz      short loc_1800091AC
0x180009187  mov     edx, 1Ah
0x18000918c  mov     [rsp+48h+lpData], r14
0x180009191  mov     ecx, 402h
0x180009196  lea     r8, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids
0x18000919d  mov     r9d, eax
0x1800091a0  call    WPP_SF_DS
0x1800091a5  jmp     short loc_1800091AC
0x1800091a7  mov     rdi, [rsp+48h+arg_10]
0x1800091ac  mov     rcx, rdi; lpMem
0x1800091af  call    Dns_Free
0x1800091b4  mov     eax, ebx
0x1800091b6  mov     rbx, [rsp+48h+arg_8]
0x1800091bb  add     rsp, 30h
0x1800091bf  pop     r14
0x1800091c1  pop     rdi
0x1800091c2  pop     rsi
0x1800091c3  retn
```
