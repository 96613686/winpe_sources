# Cortana::ConstraintIndex::Search::Configuration::DetectSku(void)

- ea: `0x18007a164`
- end: `0x18007a22f`
- name: `?DetectSku@Configuration@Search@ConstraintIndex@Cortana@@CAXXZ`
- size: `203`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c7e70`

## callees

- `0x1800049e0`
- `0x18007a164`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007a1ca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007a1ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007a1e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007a1ff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007a1e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007a1ff`

## string_xrefs

- `0x18007a19c`: `InstallationType`

## pseudocode

```c
void Cortana::ConstraintIndex::Search::Configuration::DetectSku(void)
{
  DWORD pcbData[4]; // [rsp+40h] [rbp-238h] BYREF
  _BYTE pvData[528]; // [rsp+50h] [rbp-228h] BYREF

  if ( !byte_18013E494 )
  {
    pcbData[0] = 520;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion",
            L"InstallationType",
            2u,
            0,
            pvData,
            pcbData) )
    {
      if ( (unsigned int)_o__wcsicmp(pvData, L"Client") )
      {
        if ( !(unsigned int)_o__wcsicmp(pvData, L"Server") )
          Cortana::ConstraintIndex::Search::Configuration::s_ServerSku = 1;
      }
      else
      {
        Cortana::ConstraintIndex::Search::Configuration::s_ClientSku = 1;
      }
      byte_18013E494 = 1;
    }
  }
}

```

## disassembly

```asm
0x18007a164  sub     rsp, 278h
0x18007a16b  mov     rax, cs:__security_cookie
0x18007a172  xor     rax, rsp
0x18007a175  mov     [rsp+278h+var_18], rax
0x18007a17d  cmp     cs:byte_18013E494, 0
0x18007a184  jnz     loc_18007A217
0x18007a18a  lea     rax, [rsp+278h+var_238]
0x18007a18f  mov     [rsp+278h+var_238], 208h
0x18007a197  mov     [rsp+278h+pcbData], rax; pcbData
0x18007a19c  lea     r8, Value; "InstallationType"
0x18007a1a3  lea     rax, [rsp+278h+var_228]
0x18007a1a8  mov     r9d, 2; dwFlags
0x18007a1ae  mov     [rsp+278h+pvData], rax; pvData
0x18007a1b3  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x18007a1ba  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18007a1c1  mov     [rsp+278h+pdwType], 0; pdwType
0x18007a1ca  call    cs:__imp_RegGetValueW
0x18007a1d0  test    eax, eax
0x18007a1d2  jnz     short loc_18007A217
0x18007a1d4  lea     rdx, aClient; "Client"
0x18007a1db  lea     rcx, [rsp+278h+var_228]
0x18007a1e0  call    cs:__imp__o__wcsicmp
0x18007a1e6  test    eax, eax
0x18007a1e8  jnz     short loc_18007A1F3
0x18007a1ea  mov     cs:?s_ClientSku@Configuration@Search@ConstraintIndex@Cortana@@0_NA, 1; bool Cortana::ConstraintIndex::Search::Configuration::s_ClientSku
0x18007a1f1  jmp     short loc_18007A210
0x18007a1f3  lea     rdx, aServer; "Server"
0x18007a1fa  lea     rcx, [rsp+278h+var_228]
0x18007a1ff  call    cs:__imp__o__wcsicmp
0x18007a205  test    eax, eax
0x18007a207  jnz     short loc_18007A210
0x18007a209  mov     cs:?s_ServerSku@Configuration@Search@ConstraintIndex@Cortana@@0_NA, 1; bool Cortana::ConstraintIndex::Search::Configuration::s_ServerSku
0x18007a210  mov     cs:byte_18013E494, 1
0x18007a217  mov     rcx, [rsp+278h+var_18]
0x18007a21f  xor     rcx, rsp; StackCookie
0x18007a222  call    __security_check_cookie
0x18007a227  add     rsp, 278h
0x18007a22e  retn
```
