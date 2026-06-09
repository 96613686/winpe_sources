# ZtRegWriteClientCerts

- ea: `0x180009554`
- end: `0x1800096b2`
- name: `ZtRegWriteClientCerts`
- size: `350`
- prototype: `__int64 __fastcall(__int64, __int64, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180005134`

## callees

- `0x1800090d0`
- `0x1800091cc`
- `0x180009554`
- `0x18000cdd8`
- `0x180015008`
- `0x180015094`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800096a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800096a1`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x18000960a`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x18000960a`

## string_xrefs

- `0x18000959f`: `ZtClientCertConfig`
- `0x1800095dc`: `ZtClientCertConfig`

## pseudocode

```c
__int64 __fastcall ZtRegWriteClientCerts(__int64 a1, __int64 a2, HKEY a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // eax
  __int64 v8; // rdx
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  hKey = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_q(1026, 27, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, a1);
  if ( !a1 )
  {
    v6 = 87;
    goto LABEL_16;
  }
  v7 = DnsRegDeleteTree(a3, L"ZtClientCertConfig");
  v6 = v7;
  if ( v7 )
  {
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_18;
    v8 = 28;
LABEL_15:
    WPP_SF_d(1026, v8, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, v7);
    goto LABEL_16;
  }
  if ( *(_DWORD *)(a1 + 24) || *(_DWORD *)(a1 + 40) )
  {
    v7 = RegCreateKeyExInternalW(a3, L"ZtClientCertConfig", 0, 0, 0, 196639, 0, &hKey, 0, a2);
    v6 = v7;
    if ( !v7 )
    {
      v6 = ZtRegWriteCertHashes(hKey);
      if ( !v6 )
        v6 = ZtRegWriteCertEkus(hKey);
      goto LABEL_16;
    }
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_18;
    v8 = 29;
    goto LABEL_15;
  }
LABEL_16:
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 30, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, v6);
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180009554  mov     rax, rsp
0x180009557  push    rbx
0x180009558  push    rbp
0x180009559  push    rsi
0x18000955a  push    rdi
0x18000955b  sub     rsp, 58h
0x18000955f  mov     rsi, r8
0x180009562  mov     qword ptr [rax+8], 0
0x18000956a  mov     rbp, rdx
0x18000956d  mov     rdi, rcx
0x180009570  test    byte ptr cs:xmmword_18001F260, 4
0x180009577  jz      short loc_180009592
0x180009579  mov     edx, 1Bh
0x18000957e  lea     r8, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids
0x180009585  mov     ecx, 402h
0x18000958a  mov     r9, rdi
0x18000958d  call    WPP_SF_q
0x180009592  test    rdi, rdi
0x180009595  jnz     short loc_18000959F
0x180009597  lea     ebx, [rdi+57h]
0x18000959a  jmp     loc_180009672
0x18000959f  lea     rdx, aZtclientcertco; "ZtClientCertConfig"
0x1800095a6  mov     rcx, rsi; hKey
0x1800095a9  call    DnsRegDeleteTree
0x1800095ae  mov     ebx, eax
0x1800095b0  test    eax, eax
0x1800095b2  jnz     loc_180009650
0x1800095b8  cmp     [rdi+18h], eax
0x1800095bb  jnz     short loc_1800095C6
0x1800095bd  cmp     [rdi+28h], eax
0x1800095c0  jz      loc_180009672
0x1800095c6  mov     [rsp+78h+var_30], rbp
0x1800095cb  lea     rax, [rsp+78h+hKey]
0x1800095d3  mov     [rsp+78h+var_38], 0
0x1800095dc  lea     rdx, aZtclientcertco; "ZtClientCertConfig"
0x1800095e3  mov     [rsp+78h+var_40], rax
0x1800095e8  xor     r9d, r9d
0x1800095eb  mov     [rsp+78h+var_48], 0
0x1800095f4  xor     r8d, r8d
0x1800095f7  mov     [rsp+78h+var_50], 3001Fh
0x1800095ff  mov     rcx, rsi
0x180009602  mov     [rsp+78h+var_58], 0
0x18000960a  call    cs:__imp_RegCreateKeyExInternalW
0x180009610  mov     ebx, eax
0x180009612  test    eax, eax
0x180009614  jnz     short loc_180009640
0x180009616  mov     rcx, [rsp+78h+hKey]; hKey
0x18000961e  mov     rdx, rdi
0x180009621  call    ZtRegWriteCertHashes
0x180009626  mov     ebx, eax
0x180009628  test    eax, eax
0x18000962a  jnz     short loc_180009672
0x18000962c  mov     rcx, [rsp+78h+hKey]; hKey
0x180009634  mov     rdx, rdi
0x180009637  call    ZtRegWriteCertEkus
0x18000963c  mov     ebx, eax
0x18000963e  jmp     short loc_180009672
0x180009640  test    byte ptr cs:xmmword_18001F260, 4
0x180009647  jz      short loc_180009694
0x180009649  mov     edx, 1Dh
0x18000964e  jmp     short loc_18000965E
0x180009650  test    byte ptr cs:xmmword_18001F260, 4
0x180009657  jz      short loc_180009694
0x180009659  mov     edx, 1Ch
0x18000965e  mov     r9d, eax
0x180009661  lea     r8, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids
0x180009668  mov     ecx, 402h
0x18000966d  call    WPP_SF_d
0x180009672  test    byte ptr cs:xmmword_18001F260, 4
0x180009679  jz      short loc_180009694
0x18000967b  mov     edx, 1Eh
0x180009680  lea     r8, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids
0x180009687  mov     ecx, 402h
0x18000968c  mov     r9d, ebx
0x18000968f  call    WPP_SF_d
0x180009694  mov     rcx, [rsp+78h+hKey]; hKey
0x18000969c  test    rcx, rcx
0x18000969f  jz      short loc_1800096A7
0x1800096a1  call    cs:__imp_RegCloseKey
0x1800096a7  mov     eax, ebx
0x1800096a9  add     rsp, 58h
0x1800096ad  pop     rdi
0x1800096ae  pop     rsi
0x1800096af  pop     rbp
0x1800096b0  pop     rbx
0x1800096b1  retn
```
