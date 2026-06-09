# ZtRegWriteConfig

- ea: `0x180003f58`
- end: `0x180004153`
- name: `ZtRegWriteConfig`
- size: `507`
- prototype: `__int64 __fastcall(HKEY hKey, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180005134`

## callees

- `0x180003cb8`
- `0x180003f58`
- `0x18000ce60`
- `0x180015008`
- `0x180015398`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003fe7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800040aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800040e0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004116`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003fe7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800040aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800040e0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004116`

## string_xrefs

- `0x1800040f7`: `ZtdnsServiceNameRefreshTimeout`

## pseudocode

```c
__int64 __fastcall ZtRegWriteConfig(HKEY hKey, __int64 a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  const BYTE *lpData; // rsi
  LSTATUS v9; // eax

  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qq(1026, 0xEu, (ULONGLONG)WPP_3241f1bf244939c0c0359531c6639c66_Traceguids, hKey, a2);
  if ( hKey && a2 )
  {
    v4 = 0;
    if ( g_fVelocityZtdns )
    {
      v5 = (unsigned int)(*(_DWORD *)(a2 + 16) - 1) <= 1
         ? RegSetValueExW(hKey, L"EnableZtdns", 0, 4u, (const BYTE *)(a2 + 16), 4u)
         : DnsRegDeleteValue(hKey, L"EnableZtdns");
      v4 = v5;
      if ( !v5 )
      {
        v4 = ZtRegWriteBool(hKey, L"ZtdnsAuditMode", *(_DWORD *)(a2 + 20));
        if ( !v4 )
        {
          v4 = ZtRegWriteBool(hKey, L"ZtdnsBlockLocalIps", *(_DWORD *)(a2 + 24));
          if ( !v4 )
          {
            v4 = ZtRegWriteBool(hKey, L"ZtdnsAllowHostsFile", *(_DWORD *)(a2 + 28));
            if ( !v4 )
            {
              v4 = ZtRegWriteBool(hKey, L"ZtdnsAllowIcsDhcpServer", *(_DWORD *)(a2 + 32));
              if ( !v4 )
              {
                v4 = ZtRegWriteBool(hKey, L"ZtdnsEnableForwarder", *(_DWORD *)(a2 + 36));
                if ( !v4 )
                {
                  v6 = *(_DWORD *)(a2 + 40)
                     ? RegSetValueExW(hKey, L"ZtdnsUnicastLifetime", 0, 4u, (const BYTE *)(a2 + 40), 4u)
                     : DnsRegDeleteValue(hKey, L"ZtdnsUnicastLifetime");
                  v4 = v6;
                  if ( !v6 )
                  {
                    v7 = *(_DWORD *)(a2 + 44)
                       ? RegSetValueExW(hKey, L"ZtdnsMaxRecordAge", 0, 4u, (const BYTE *)(a2 + 44), 4u)
                       : DnsRegDeleteValue(hKey, L"ZtdnsMaxRecordAge");
                    v4 = v7;
                    if ( !v7 )
                    {
                      lpData = (const BYTE *)(a2 + 48);
                      if ( *(_DWORD *)lpData )
                        v9 = RegSetValueExW(hKey, L"ZtdnsServiceNameRefreshTimeout", 0, 4u, lpData, 4u);
                      else
                        v9 = DnsRegDeleteValue(hKey, L"ZtdnsServiceNameRefreshTimeout");
                      v4 = v9;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v4 = 87;
  }
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 0xFu, (ULONGLONG)WPP_3241f1bf244939c0c0359531c6639c66_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180003f58  push    rbx
0x180003f5a  push    rsi
0x180003f5b  push    rdi
0x180003f5c  push    r14
0x180003f5e  sub     rsp, 38h
0x180003f62  mov     rsi, rdx
0x180003f65  mov     rdi, rcx
0x180003f68  mov     r14d, 4
0x180003f6e  test    byte ptr cs:xmmword_18001F260, r14b
0x180003f75  jz      short loc_180003F94
0x180003f77  lea     edx, [r14+0Ah]
0x180003f7b  mov     [rsp+58h+lpData], rsi
0x180003f80  mov     ecx, 402h
0x180003f85  lea     r8, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x180003f8c  mov     r9, rdi
0x180003f8f  call    WPP_SF_qq
0x180003f94  test    rdi, rdi
0x180003f97  jnz     short loc_180003FA3
0x180003f99  mov     ebx, 57h ; 'W'
0x180003f9e  jmp     loc_180004125
0x180003fa3  test    rsi, rsi
0x180003fa6  jz      short loc_180003F99
0x180003fa8  xor     ebx, ebx
0x180003faa  cmp     cs:g_fVelocityZtdns, ebx
0x180003fb0  jz      loc_180004125
0x180003fb6  lea     rcx, [rsi+10h]
0x180003fba  mov     eax, [rcx]
0x180003fbc  lea     rdx, aEnableztdns; "EnableZtdns"
0x180003fc3  dec     eax
0x180003fc5  cmp     eax, 1
0x180003fc8  jbe     short loc_180003FD4
0x180003fca  mov     rcx, rdi; hKey
0x180003fcd  call    DnsRegDeleteValue
0x180003fd2  jmp     short loc_180003FED
0x180003fd4  mov     [rsp+58h+cbData], r14d; cbData
0x180003fd9  mov     r9d, r14d; dwType
0x180003fdc  mov     [rsp+58h+lpData], rcx; lpData
0x180003fe1  xor     r8d, r8d; Reserved
0x180003fe4  mov     rcx, rdi; hKey
0x180003fe7  call    cs:__imp_RegSetValueExW
0x180003fed  mov     ebx, eax
0x180003fef  test    eax, eax
0x180003ff1  jnz     loc_180004125
0x180003ff7  mov     r8d, [rsi+14h]
0x180003ffb  lea     rdx, aZtdnsauditmode; "ZtdnsAuditMode"
0x180004002  mov     rcx, rdi; hKey
0x180004005  call    ZtRegWriteBool
0x18000400a  mov     ebx, eax
0x18000400c  test    eax, eax
0x18000400e  jnz     loc_180004125
0x180004014  mov     r8d, [rsi+18h]
0x180004018  lea     rdx, aZtdnsblockloca; "ZtdnsBlockLocalIps"
0x18000401f  mov     rcx, rdi; hKey
0x180004022  call    ZtRegWriteBool
0x180004027  mov     ebx, eax
0x180004029  test    eax, eax
0x18000402b  jnz     loc_180004125
0x180004031  mov     r8d, [rsi+1Ch]
0x180004035  lea     rdx, aZtdnsallowhost; "ZtdnsAllowHostsFile"
0x18000403c  mov     rcx, rdi; hKey
0x18000403f  call    ZtRegWriteBool
0x180004044  mov     ebx, eax
0x180004046  test    eax, eax
0x180004048  jnz     loc_180004125
0x18000404e  mov     r8d, [rsi+20h]
0x180004052  lea     rdx, aZtdnsallowicsd; "ZtdnsAllowIcsDhcpServer"
0x180004059  mov     rcx, rdi; hKey
0x18000405c  call    ZtRegWriteBool
0x180004061  mov     ebx, eax
0x180004063  test    eax, eax
0x180004065  jnz     loc_180004125
0x18000406b  mov     r8d, [rsi+24h]
0x18000406f  lea     rdx, aZtdnsenablefor; "ZtdnsEnableForwarder"
0x180004076  mov     rcx, rdi; hKey
0x180004079  call    ZtRegWriteBool
0x18000407e  mov     ebx, eax
0x180004080  test    eax, eax
0x180004082  jnz     loc_180004125
0x180004088  lea     rax, [rsi+28h]
0x18000408c  mov     rcx, rdi; hKey
0x18000408f  lea     rdx, aZtdnsunicastli; "ZtdnsUnicastLifetime"
0x180004096  cmp     [rax], ebx
0x180004098  jz      short loc_1800040B2
0x18000409a  mov     [rsp+58h+cbData], r14d; cbData
0x18000409f  mov     r9d, r14d; dwType
0x1800040a2  xor     r8d, r8d; Reserved
0x1800040a5  mov     [rsp+58h+lpData], rax; lpData
0x1800040aa  call    cs:__imp_RegSetValueExW
0x1800040b0  jmp     short loc_1800040B7
0x1800040b2  call    DnsRegDeleteValue
0x1800040b7  mov     ebx, eax
0x1800040b9  test    eax, eax
0x1800040bb  jnz     short loc_180004125
0x1800040bd  lea     rax, [rsi+2Ch]
0x1800040c1  mov     rcx, rdi; hKey
0x1800040c4  cmp     dword ptr [rax], 0
0x1800040c7  lea     rdx, aZtdnsmaxrecord; "ZtdnsMaxRecordAge"
0x1800040ce  jz      short loc_1800040E8
0x1800040d0  mov     [rsp+58h+cbData], r14d; cbData
0x1800040d5  mov     r9d, r14d; dwType
0x1800040d8  xor     r8d, r8d; Reserved
0x1800040db  mov     [rsp+58h+lpData], rax; lpData
0x1800040e0  call    cs:__imp_RegSetValueExW
0x1800040e6  jmp     short loc_1800040ED
0x1800040e8  call    DnsRegDeleteValue
0x1800040ed  mov     ebx, eax
0x1800040ef  test    eax, eax
0x1800040f1  jnz     short loc_180004125
0x1800040f3  add     rsi, 30h ; '0'
0x1800040f7  lea     rdx, aZtdnsservicena; "ZtdnsServiceNameRefreshTimeout"
0x1800040fe  mov     rcx, rdi; hKey
0x180004101  cmp     dword ptr [rsi], 0
0x180004104  jz      short loc_18000411E
0x180004106  mov     [rsp+58h+cbData], r14d; cbData
0x18000410b  mov     r9d, r14d; dwType
0x18000410e  xor     r8d, r8d; Reserved
0x180004111  mov     [rsp+58h+lpData], rsi; lpData
0x180004116  call    cs:__imp_RegSetValueExW
0x18000411c  jmp     short loc_180004123
0x18000411e  call    DnsRegDeleteValue
0x180004123  mov     ebx, eax
0x180004125  test    byte ptr cs:xmmword_18001F260, r14b
0x18000412c  jz      short loc_180004147
0x18000412e  mov     edx, 0Fh
0x180004133  lea     r8, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x18000413a  mov     ecx, 402h
0x18000413f  mov     r9d, ebx
0x180004142  call    WPP_SF_d
0x180004147  mov     eax, ebx
0x180004149  add     rsp, 38h
0x18000414d  pop     r14
0x18000414f  pop     rdi
0x180004150  pop     rsi
0x180004151  pop     rbx
0x180004152  retn
```
