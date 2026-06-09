# ZtRegReadClientCerts

- ea: `0x180008e40`
- end: `0x1800090c9`
- name: `ZtRegReadClientCerts`
- size: `649`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180009420`

## callees

- `0x180008cd0`
- `0x180008e40`
- `0x1800096b8`
- `0x180009eac`
- `0x18000d308`
- `0x18000d5b4`
- `0x18000dbcc`
- `0x180012564`
- `0x1800125d4`
- `0x180015008`
- `0x180015478`

## import_xrefs

- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18000904d`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18000904d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800090b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800090b0`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x180008f35`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x180008f35`

## string_xrefs

- `0x180008f12`: `ZtClientCertConfig`

## pseudocode

```c
__int64 __fastcall ZtRegReadClientCerts(__int64 a1, __int64 a2, _QWORD *a3)
{
  void *v3; // rdi
  signed int v7; // ebx
  _DWORD *v8; // rax
  signed int v9; // eax
  int CertsHashOrEku; // eax
  int v11; // eax
  int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF

  v3 = 0;
  hKey[0] = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qqq(1026, 17, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, a1, a2, a3);
  if ( a3 )
    *a3 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        v8 = (_DWORD *)Dns_Allocate(48);
        v3 = v8;
        if ( v8 )
        {
          *v8 = 1;
          v7 = 0;
          v9 = RegOpenKeyExInternalW(a1, L"ZtClientCertConfig", 0, 131097, hKey, a2);
          if ( v9 == 2 )
            goto LABEL_27;
          v7 = v9 > 0 ? (unsigned __int16)v9 | 0x80070000 : v9;
          if ( v7 >= 0 )
          {
            CertsHashOrEku = ZtRegGetCertsHashOrEku(hKey[0], L"ClientCertHashes");
            v7 = CertsHashOrEku;
            if ( CertsHashOrEku > 0 )
              v7 = (unsigned __int16)CertsHashOrEku | 0x80070000;
            if ( v7 >= 0 )
            {
              v11 = ZtRegGetCertsHashOrEku(hKey[0], L"ClientCertEkus");
              v7 = v11;
              if ( v11 > 0 )
                v7 = (unsigned __int16)v11 | 0x80070000;
              if ( v7 >= 0 )
              {
                v12 = ZtValidateClientCertConfig(v3);
                v7 = v12;
                if ( v12 > 0 )
                  v7 = (unsigned __int16)v12 | 0x80070000;
                if ( v7 >= 0 )
                {
LABEL_27:
                  *a3 = v3;
                  v3 = 0;
                }
              }
            }
          }
        }
        else
        {
          v7 = -2147024882;
        }
      }
      else
      {
        v7 = -2147024809;
      }
    }
    else
    {
      v7 = -2147024809;
    }
  }
  else
  {
    v7 = -2147024809;
  }
  if ( g_fVelocityZtdnsApiRefactor )
    ZtFreeClientCertConfig(v3);
  else
    DnsFreeZtClientCertConfig(v3);
  Dns_Free(0);
  Dns_Free(0);
  if ( (xmmword_18001F260 & 4) != 0 )
  {
    v13 = WX_WIN32_FROM_HR((unsigned int)v7);
    WPP_SF_d(1026, 18, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, v13);
  }
  v14 = WX_WIN32_FROM_HR((unsigned int)v7);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v14;
}

```

## disassembly

```asm
0x180008e40  mov     [rsp-28h+arg_8], rbx
0x180008e45  push    rbp
0x180008e46  push    rsi
0x180008e47  push    rdi
0x180008e48  push    r14
0x180008e4a  push    r15
0x180008e4c  mov     rbp, rsp
0x180008e4f  sub     rsp, 40h
0x180008e53  xor     edi, edi
0x180008e55  mov     [rbp+arg_4], 0
0x180008e5c  mov     [rbp+lpMem], rdi
0x180008e60  mov     r15, r8
0x180008e63  mov     [rbp+Src], rdi
0x180008e67  mov     rsi, rdx
0x180008e6a  mov     r14, rcx
0x180008e6d  mov     [rbp+hKey], 0
0x180008e75  test    byte ptr cs:xmmword_18001F260, 4
0x180008e7c  jz      short loc_180008E9F
0x180008e7e  mov     [rsp+40h+var_18], r8
0x180008e83  lea     edx, [rdi+11h]
0x180008e86  lea     r8, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids
0x180008e8d  mov     [rsp+40h+var_20], rsi
0x180008e92  mov     ecx, 402h
0x180008e97  mov     r9, r14
0x180008e9a  call    WPP_SF_qqq
0x180008e9f  test    r15, r15
0x180008ea2  jz      short loc_180008EA7
0x180008ea4  mov     [r15], rdi
0x180008ea7  test    r14, r14
0x180008eaa  jnz     short loc_180008EBD
0x180008eac  mov     ebx, 80070057h
0x180008eb1  mov     [rbp+arg_4], 8Fh
0x180008eb8  jmp     loc_18000903A
0x180008ebd  test    rsi, rsi
0x180008ec0  jnz     short loc_180008ED3
0x180008ec2  mov     ebx, 80070057h
0x180008ec7  mov     [rbp+arg_4], 90h
0x180008ece  jmp     loc_18000903A
0x180008ed3  test    r15, r15
0x180008ed6  jnz     short loc_180008EE9
0x180008ed8  mov     ebx, 80070057h
0x180008edd  mov     [rbp+arg_4], 91h
0x180008ee4  jmp     loc_18000903A
0x180008ee9  mov     ecx, 30h ; '0'
0x180008eee  call    Dns_Allocate
0x180008ef3  mov     rdi, rax
0x180008ef6  test    rax, rax
0x180008ef9  jnz     short loc_180008F0C
0x180008efb  mov     ebx, 8007000Eh
0x180008f00  mov     [rbp+arg_4], 94h
0x180008f07  jmp     loc_18000903A
0x180008f0c  mov     dword ptr [rax], 1
0x180008f12  lea     rdx, aZtclientcertco; "ZtClientCertConfig"
0x180008f19  lea     rax, [rbp+hKey]
0x180008f1d  mov     [rsp+40h+var_18], rsi
0x180008f22  mov     r9d, 20019h
0x180008f28  mov     [rsp+40h+var_20], rax
0x180008f2d  xor     r8d, r8d
0x180008f30  mov     rcx, r14
0x180008f33  xor     ebx, ebx
0x180008f35  call    cs:__imp_RegOpenKeyExInternalW
0x180008f3b  cmp     eax, 2
0x180008f3e  jz      loc_180009035
0x180008f44  mov     esi, 80070000h
0x180008f49  test    eax, eax
0x180008f4b  jg      short loc_180008F51
0x180008f4d  mov     ebx, eax
0x180008f4f  jmp     short loc_180008F56
0x180008f51  movzx   ebx, ax
0x180008f54  or      ebx, esi
0x180008f56  test    ebx, ebx
0x180008f58  jns     short loc_180008F66
0x180008f5a  mov     [rbp+arg_4], 0A3h
0x180008f61  jmp     loc_18000903A
0x180008f66  mov     rcx, [rbp+hKey]; hKey
0x180008f6a  lea     r8, [rbp+lpMem]
0x180008f6e  lea     rdx, aClientcerthash; "ClientCertHashes"
0x180008f75  call    ZtRegGetCertsHashOrEku
0x180008f7a  mov     ebx, eax
0x180008f7c  test    eax, eax
0x180008f7e  jle     short loc_180008F85
0x180008f80  movzx   ebx, ax
0x180008f83  or      ebx, esi
0x180008f85  test    ebx, ebx
0x180008f87  jns     short loc_180008F95
0x180008f89  mov     [rbp+arg_4], 0A7h
0x180008f90  jmp     loc_18000903A
0x180008f95  mov     rcx, [rbp+lpMem]
0x180008f99  test    rcx, rcx
0x180008f9c  jz      short loc_180008FC0
0x180008f9e  mov     r8, rdi
0x180008fa1  xor     edx, edx
0x180008fa3  call    DnsZtParseCertHashList
0x180008fa8  mov     ebx, eax
0x180008faa  test    eax, eax
0x180008fac  jle     short loc_180008FB3
0x180008fae  movzx   ebx, ax
0x180008fb1  or      ebx, esi
0x180008fb3  test    ebx, ebx
0x180008fb5  jns     short loc_180008FC0
0x180008fb7  mov     [rbp+arg_4], 0ABh
0x180008fbe  jmp     short loc_18000903A
0x180008fc0  mov     rcx, [rbp+hKey]; hKey
0x180008fc4  lea     r8, [rbp+Src]
0x180008fc8  lea     rdx, aClientcertekus; "ClientCertEkus"
0x180008fcf  call    ZtRegGetCertsHashOrEku
0x180008fd4  mov     ebx, eax
0x180008fd6  test    eax, eax
0x180008fd8  jle     short loc_180008FDF
0x180008fda  movzx   ebx, ax
0x180008fdd  or      ebx, esi
0x180008fdf  test    ebx, ebx
0x180008fe1  jns     short loc_180008FEC
0x180008fe3  mov     [rbp+arg_4], 0B0h
0x180008fea  jmp     short loc_18000903A
0x180008fec  mov     rcx, [rbp+Src]; Src
0x180008ff0  test    rcx, rcx
0x180008ff3  jz      short loc_180009015
0x180008ff5  mov     rdx, rdi
0x180008ff8  call    DnsZtParseCertEkuList
0x180008ffd  mov     ebx, eax
0x180008fff  test    eax, eax
0x180009001  jle     short loc_180009008
0x180009003  movzx   ebx, ax
0x180009006  or      ebx, esi
0x180009008  test    ebx, ebx
0x18000900a  jns     short loc_180009015
0x18000900c  mov     [rbp+arg_4], 0B4h
0x180009013  jmp     short loc_18000903A
0x180009015  mov     rcx, rdi
0x180009018  call    ZtValidateClientCertConfig
0x18000901d  mov     ebx, eax
0x18000901f  test    eax, eax
0x180009021  jle     short loc_180009028
0x180009023  movzx   ebx, ax
0x180009026  or      ebx, esi
0x180009028  test    ebx, ebx
0x18000902a  jns     short loc_180009035
0x18000902c  mov     [rbp+arg_4], 0B7h
0x180009033  jmp     short loc_18000903A
0x180009035  mov     [r15], rdi
0x180009038  xor     edi, edi
0x18000903a  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x180009041  mov     rcx, rdi; lpMem
0x180009044  jz      short loc_18000904D
0x180009046  call    ZtFreeClientCertConfig
0x18000904b  jmp     short loc_180009053
0x18000904d  call    cs:__imp_DnsFreeZtClientCertConfig
0x180009053  mov     rcx, [rbp+lpMem]; lpMem
0x180009057  call    Dns_Free
0x18000905c  mov     rcx, [rbp+Src]; lpMem
0x180009060  mov     [rbp+lpMem], 0
0x180009068  call    Dns_Free
0x18000906d  mov     [rbp+Src], 0
0x180009075  test    byte ptr cs:xmmword_18001F260, 4
0x18000907c  jz      short loc_18000909E
0x18000907e  mov     ecx, ebx
0x180009080  call    WX_WIN32_FROM_HR
0x180009085  mov     r9d, eax
0x180009088  lea     r8, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids
0x18000908f  mov     edx, 12h
0x180009094  mov     ecx, 402h
0x180009099  call    WPP_SF_d
0x18000909e  mov     ecx, ebx
0x1800090a0  call    WX_WIN32_FROM_HR
0x1800090a5  mov     rcx, [rbp+hKey]; hKey
0x1800090a9  mov     ebx, eax
0x1800090ab  test    rcx, rcx
0x1800090ae  jz      short loc_1800090B6
0x1800090b0  call    cs:__imp_RegCloseKey
0x1800090b6  mov     eax, ebx
0x1800090b8  mov     rbx, [rsp+40h+arg_8]
0x1800090bd  add     rsp, 40h
0x1800090c1  pop     r15
0x1800090c3  pop     r14
0x1800090c5  pop     rdi
0x1800090c6  pop     rsi
0x1800090c7  pop     rbp
0x1800090c8  retn
```
