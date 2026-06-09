# ZtRegReadTrustedCa

- ea: `0x180009808`
- end: `0x1800099a2`
- name: `ZtRegReadTrustedCa`
- size: `410`
- prototype: `__int64 __fastcall(__int64, __int64, LPVOID **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800099a8`

## callees

- `0x180009808`
- `0x18000d5b4`
- `0x18000dc74`
- `0x18000f9c8`
- `0x180012564`
- `0x1800125d4`
- `0x180015008`
- `0x180015478`

## import_xrefs

- `DNSAPI!DnsFreeZtTrustedCa` at `0x180009951`
- `DNSAPI!DnsFreeZtTrustedCa` at `0x180009951`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000998d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000998d`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x1800098bb`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x1800098bb`

## pseudocode

```c
__int64 __fastcall ZtRegReadTrustedCa(__int64 a1, __int64 a2, LPVOID **a3)
{
  LPVOID *v3; // rdi
  unsigned int StringValueW; // ebx
  _DWORD *v8; // rax
  unsigned int v9; // eax
  __int64 v10; // r8
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  hKey = 0;
  lpMem = 0;
  LODWORD(v12) = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qqq(1026, 0x15u, (ULONGLONG)WPP_2074faa7941838f94d01dce17c4721b7_Traceguids, a1, a2, a3);
  if ( a3 )
    *a3 = 0;
  if ( !a1 || !a2 || !a3 )
  {
    StringValueW = 87;
    goto LABEL_20;
  }
  v8 = Dns_Allocate(0x20u);
  v3 = (LPVOID *)v8;
  if ( !v8 )
  {
    StringValueW = 14;
    goto LABEL_20;
  }
  *v8 = 1;
  v9 = RegOpenKeyExInternalW(a1, L"ZtTrustedCa", 0, 131097, &hKey, a2);
  StringValueW = v9;
  if ( v9 == 2 )
  {
    StringValueW = 0;
LABEL_17:
    *a3 = v3;
    v3 = 0;
    goto LABEL_20;
  }
  if ( v9 )
    goto LABEL_20;
  StringValueW = privateRegReadStringValueW(hKey, L"CertHashes", v10, (BYTE **)&lpMem, (DWORD *)&v12);
  if ( StringValueW )
    goto LABEL_20;
  if ( (_DWORD)v12 )
  {
    StringValueW = DnsZtParseCertHashList(lpMem, v3, 0);
    if ( StringValueW )
      goto LABEL_20;
    goto LABEL_17;
  }
  StringValueW = 13;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 0x16u, (ULONGLONG)WPP_2074faa7941838f94d01dce17c4721b7_Traceguids, 13);
LABEL_20:
  if ( g_fVelocityZtdnsApiRefactor )
    ZtFreeTrustedCa(v3);
  else
    DnsFreeZtTrustedCa(v3);
  Dns_Free(lpMem);
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 0x17u, (ULONGLONG)WPP_2074faa7941838f94d01dce17c4721b7_Traceguids, StringValueW);
  if ( hKey )
    RegCloseKey(hKey);
  return StringValueW;
}

```

## disassembly

```asm
0x180009808  mov     rax, rsp
0x18000980b  mov     [rax+10h], rbx
0x18000980f  push    rbp
0x180009810  push    rsi
0x180009811  push    rdi
0x180009812  sub     rsp, 30h
0x180009816  xor     edi, edi
0x180009818  mov     qword ptr [rax+20h], 0
0x180009820  mov     [rax+18h], rdi
0x180009824  mov     rsi, r8
0x180009827  mov     [rax+8], edi
0x18000982a  mov     rbx, rdx
0x18000982d  mov     rbp, rcx
0x180009830  test    byte ptr cs:xmmword_18001F260, 4
0x180009837  jz      short loc_180009858
0x180009839  mov     [rax-20h], r8
0x18000983d  lea     edx, [rdi+15h]
0x180009840  lea     r8, WPP_2074faa7941838f94d01dce17c4721b7_Traceguids
0x180009847  mov     [rax-28h], rbx
0x18000984b  mov     ecx, 402h
0x180009850  mov     r9, rbp
0x180009853  call    WPP_SF_qqq
0x180009858  test    rsi, rsi
0x18000985b  jz      short loc_180009860
0x18000985d  mov     [rsi], rdi
0x180009860  test    rbp, rbp
0x180009863  jnz     short loc_18000986F
0x180009865  mov     ebx, 57h ; 'W'
0x18000986a  jmp     loc_18000993E
0x18000986f  test    rbx, rbx
0x180009872  jz      short loc_180009865
0x180009874  test    rsi, rsi
0x180009877  jz      short loc_180009865
0x180009879  mov     ecx, 20h ; ' '
0x18000987e  call    Dns_Allocate
0x180009883  mov     rdi, rax
0x180009886  test    rax, rax
0x180009889  jnz     short loc_180009893
0x18000988b  lea     ebx, [rax+0Eh]
0x18000988e  jmp     loc_18000993E
0x180009893  mov     dword ptr [rax], 1
0x180009899  lea     rdx, aZttrustedca; "ZtTrustedCa"
0x1800098a0  lea     rax, [rsp+48h+hKey]
0x1800098a5  mov     [rsp+48h+var_20], rbx
0x1800098aa  mov     r9d, 20019h
0x1800098b0  mov     [rsp+48h+var_28], rax
0x1800098b5  xor     r8d, r8d
0x1800098b8  mov     rcx, rbp
0x1800098bb  call    cs:__imp_RegOpenKeyExInternalW
0x1800098c1  mov     ebx, eax
0x1800098c3  cmp     eax, 2
0x1800098c6  jnz     short loc_1800098CC
0x1800098c8  xor     ebx, ebx
0x1800098ca  jmp     short loc_180009912
0x1800098cc  test    eax, eax
0x1800098ce  jnz     short loc_18000993E
0x1800098d0  mov     rcx, [rsp+48h+hKey]; hKey
0x1800098d5  lea     rax, [rsp+48h+arg_0]
0x1800098da  lea     r9, [rsp+48h+lpMem]
0x1800098df  mov     [rsp+48h+var_28], rax; __int64
0x1800098e4  lea     rdx, aCerthashes; "CertHashes"
0x1800098eb  call    privateRegReadStringValueW
0x1800098f0  mov     ebx, eax
0x1800098f2  test    eax, eax
0x1800098f4  jnz     short loc_18000993E
0x1800098f6  cmp     dword ptr [rsp+48h+arg_0], eax
0x1800098fa  jbe     short loc_180009919
0x1800098fc  mov     rcx, [rsp+48h+lpMem]
0x180009901  xor     r8d, r8d
0x180009904  mov     rdx, rdi
0x180009907  call    DnsZtParseCertHashList
0x18000990c  mov     ebx, eax
0x18000990e  test    eax, eax
0x180009910  jnz     short loc_18000993E
0x180009912  mov     [rsi], rdi
0x180009915  xor     edi, edi
0x180009917  jmp     short loc_18000993E
0x180009919  mov     ebx, 0Dh
0x18000991e  test    byte ptr cs:xmmword_18001F260, 4
0x180009925  jz      short loc_18000993E
0x180009927  lea     edx, [rbx+9]
0x18000992a  mov     ecx, 402h
0x18000992f  mov     r9d, ebx
0x180009932  lea     r8, WPP_2074faa7941838f94d01dce17c4721b7_Traceguids
0x180009939  call    WPP_SF_d
0x18000993e  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x180009945  mov     rcx, rdi; lpMem
0x180009948  jz      short loc_180009951
0x18000994a  call    ZtFreeTrustedCa
0x18000994f  jmp     short loc_180009957
0x180009951  call    cs:__imp_DnsFreeZtTrustedCa
0x180009957  mov     rcx, [rsp+48h+lpMem]; lpMem
0x18000995c  call    Dns_Free
0x180009961  test    byte ptr cs:xmmword_18001F260, 4
0x180009968  jz      short loc_180009983
0x18000996a  mov     edx, 17h
0x18000996f  lea     r8, WPP_2074faa7941838f94d01dce17c4721b7_Traceguids
0x180009976  mov     ecx, 402h
0x18000997b  mov     r9d, ebx
0x18000997e  call    WPP_SF_d
0x180009983  mov     rcx, [rsp+48h+hKey]; hKey
0x180009988  test    rcx, rcx
0x18000998b  jz      short loc_180009993
0x18000998d  call    cs:__imp_RegCloseKey
0x180009993  mov     eax, ebx
0x180009995  mov     rbx, [rsp+48h+arg_8]
0x18000999a  add     rsp, 30h
0x18000999e  pop     rdi
0x18000999f  pop     rsi
0x1800099a0  pop     rbp
0x1800099a1  retn
```
