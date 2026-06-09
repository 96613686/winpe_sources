# ZtRegWriteRules

- ea: `0x180008a60`
- end: `0x180008be6`
- name: `ZtRegWriteRules`
- size: `390`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, __int64, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180005134`

## callees

- `0x180008360`
- `0x180008a60`
- `0x18000cdd8`
- `0x180015008`
- `0x1800152b0`
- `0x1800154c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008bd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008bd1`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x180008b15`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x180008b15`

## pseudocode

```c
__int64 __fastcall ZtRegWriteRules(unsigned int a1, __int64 a2, __int64 a3, __int64 a4, HKEY a5)
{
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // rdi
  HKEY hKey; // [rsp+A0h] [rbp+18h] BYREF

  hKey = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_dq(1026, 0x2Au, (ULONGLONG)WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids, a1, a2);
  v8 = DnsRegDeleteTree(a5, L"ZtRules");
  if ( v8 || !a2 )
    goto LABEL_14;
  v9 = RegCreateKeyExInternalW(a5, L"ZtRules", 0, 0, 0, 196639, 0, &hKey, 0, a4);
  v8 = v9;
  if ( v9 )
  {
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_16;
    WPP_SF_d(1026, 0x2Bu, (ULONGLONG)WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids, v9);
    goto LABEL_14;
  }
  v10 = 0;
  if ( !a1 )
  {
LABEL_14:
    if ( (xmmword_18001F260 & 4) != 0 )
      WPP_SF_d(1026, 0x2Du, (ULONGLONG)WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids, v8);
    goto LABEL_16;
  }
  while ( 1 )
  {
    v8 = ZtRegWriteSingleRule(a2 + 48 * v10, hKey, a4);
    if ( v8 )
      break;
    v10 = (unsigned int)(v10 + 1);
    if ( (unsigned int)v10 >= a1 )
      goto LABEL_14;
  }
  if ( (xmmword_18001F260 & 4) != 0 )
  {
    WPP_SF_DS(
      1026,
      0x2Cu,
      (ULONGLONG)WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids,
      v8,
      *(const wchar_t **)(a2 + 48 * v10 + 16));
    goto LABEL_14;
  }
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x180008a60  mov     rax, rsp
0x180008a63  mov     [rax+18h], r8
0x180008a67  push    rbx
0x180008a68  push    rbp
0x180008a69  push    rsi
0x180008a6a  push    rdi
0x180008a6b  push    r14
0x180008a6d  push    r15
0x180008a6f  sub     rsp, 58h
0x180008a73  mov     r15, r9
0x180008a76  mov     qword ptr [rax+18h], 0
0x180008a7e  mov     rbp, rdx
0x180008a81  mov     esi, ecx
0x180008a83  test    byte ptr cs:xmmword_18001F260, 4
0x180008a8a  jz      short loc_180008AA9
0x180008a8c  mov     edx, 2Ah ; '*'
0x180008a91  mov     [rax-68h], rbp
0x180008a95  mov     ecx, 402h
0x180008a9a  lea     r8, WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids
0x180008aa1  mov     r9d, esi
0x180008aa4  call    WPP_SF_dq
0x180008aa9  mov     rcx, [rsp+88h+arg_20]; hKey
0x180008ab1  lea     rdx, aZtrules; "ZtRules"
0x180008ab8  call    DnsRegDeleteTree
0x180008abd  mov     ebx, eax
0x180008abf  test    eax, eax
0x180008ac1  jnz     loc_180008BA2
0x180008ac7  test    rbp, rbp
0x180008aca  jz      loc_180008BA2
0x180008ad0  mov     rcx, [rsp+88h+arg_20]
0x180008ad8  lea     rax, [rsp+88h+hKey]
0x180008ae0  mov     [rsp+88h+var_40], r15
0x180008ae5  lea     rdx, aZtrules; "ZtRules"
0x180008aec  mov     [rsp+88h+var_48], 0
0x180008af5  xor     r9d, r9d
0x180008af8  mov     [rsp+88h+var_50], rax
0x180008afd  xor     r8d, r8d
0x180008b00  mov     [rsp+88h+var_58], 0
0x180008b09  mov     [rsp+88h+var_60], 3001Fh
0x180008b11  mov     dword ptr [rsp+88h+var_68], ebx
0x180008b15  call    cs:__imp_RegCreateKeyExInternalW
0x180008b1b  mov     ebx, eax
0x180008b1d  test    eax, eax
0x180008b1f  jnz     short loc_180008B80
0x180008b21  xor     edi, edi
0x180008b23  test    esi, esi
0x180008b25  jz      short loc_180008BA2
0x180008b27  mov     rdx, [rsp+88h+hKey]
0x180008b2f  lea     r14, [rdi+rdi*2]
0x180008b33  shl     r14, 4
0x180008b37  mov     r8, r15
0x180008b3a  add     r14, rbp
0x180008b3d  mov     rcx, r14
0x180008b40  call    ZtRegWriteSingleRule
0x180008b45  mov     ebx, eax
0x180008b47  test    eax, eax
0x180008b49  jnz     short loc_180008B53
0x180008b4b  inc     edi
0x180008b4d  cmp     edi, esi
0x180008b4f  jb      short loc_180008B27
0x180008b51  jmp     short loc_180008BA2
0x180008b53  test    byte ptr cs:xmmword_18001F260, 4
0x180008b5a  jz      short loc_180008BC4
0x180008b5c  mov     rax, [r14+10h]
0x180008b60  lea     r8, WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids
0x180008b67  mov     edx, 2Ch ; ','
0x180008b6c  mov     [rsp+88h+var_68], rax
0x180008b71  mov     ecx, 402h
0x180008b76  mov     r9d, ebx
0x180008b79  call    WPP_SF_DS
0x180008b7e  jmp     short loc_180008BA2
0x180008b80  test    byte ptr cs:xmmword_18001F260, 4
0x180008b87  jz      short loc_180008BC4
0x180008b89  mov     edx, 2Bh ; '+'
0x180008b8e  lea     r8, WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids
0x180008b95  mov     ecx, 402h
0x180008b9a  mov     r9d, eax
0x180008b9d  call    WPP_SF_d
0x180008ba2  test    byte ptr cs:xmmword_18001F260, 4
0x180008ba9  jz      short loc_180008BC4
0x180008bab  mov     edx, 2Dh ; '-'
0x180008bb0  lea     r8, WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids
0x180008bb7  mov     ecx, 402h
0x180008bbc  mov     r9d, ebx
0x180008bbf  call    WPP_SF_d
0x180008bc4  mov     rcx, [rsp+88h+hKey]; hKey
0x180008bcc  test    rcx, rcx
0x180008bcf  jz      short loc_180008BD7
0x180008bd1  call    cs:__imp_RegCloseKey
0x180008bd7  mov     eax, ebx
0x180008bd9  add     rsp, 58h
0x180008bdd  pop     r15
0x180008bdf  pop     r14
0x180008be1  pop     rdi
0x180008be2  pop     rsi
0x180008be3  pop     rbp
0x180008be4  pop     rbx
0x180008be5  retn
```
