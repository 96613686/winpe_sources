# CBroker::SebBroker::UpdateControlVariables(void)

- ea: `0x1800207b8`
- end: `0x1800208b3`
- name: `?UpdateControlVariables@SebBroker@CBroker@@AEAAXXZ`
- size: `251`
- prototype: `void __fastcall(CBroker::SebBroker *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c57c`

## callees

- `0x180005a50`
- `0x1800207b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002085b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002085b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020823`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020823`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002087f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002087f`

## string_xrefs

- `0x180020815`: `SYSTEM\CurrentControlSet\Services\SystemEventsBroker\Parameters`

## pseudocode

```c
void __fastcall CBroker::SebBroker::UpdateControlVariables(CBroker::SebBroker *this)
{
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  int Data; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  Data = 0;
  cbData = 0;
  hKey = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\SystemEventsBroker\\Parameters",
          0,
          1u,
          &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"NoParamValidation", 0, 0, (LPBYTE)&Data, &cbData) )
    {
      if ( Data )
        *((_DWORD *)this + 86) = 1;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
}

```

## disassembly

```asm
0x1800207b8  push    rbx
0x1800207ba  sub     rsp, 30h
0x1800207be  mov     rbx, rcx
0x1800207c1  mov     [rsp+38h+Data], 0
0x1800207c9  mov     [rsp+38h+cbData], 0
0x1800207d1  mov     [rsp+38h+hKey], 0
0x1800207da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207e1  test    byte ptr [rcx+1Ch], 1
0x1800207e5  jz      short loc_180020802
0x1800207e7  cmp     byte ptr [rcx+19h], 4
0x1800207eb  jb      short loc_180020802
0x1800207ed  mov     rcx, [rcx+10h]
0x1800207f1  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x1800207f8  mov     edx, 0Eh
0x1800207fd  call    WPP_SF_
0x180020802  lea     rax, [rsp+38h+hKey]
0x180020807  mov     r9d, 1; samDesired
0x18002080d  xor     r8d, r8d; ulOptions
0x180020810  mov     [rsp+38h+phkResult], rax; phkResult
0x180020815  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Sy"...
0x18002081c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020823  call    cs:__imp_RegOpenKeyExW
0x180020829  test    eax, eax
0x18002082b  jnz     short loc_180020875
0x18002082d  mov     rcx, [rsp+38h+hKey]; hKey
0x180020832  lea     rax, [rsp+38h+cbData]
0x180020837  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002083c  lea     rdx, ValueName; "NoParamValidation"
0x180020843  lea     rax, [rsp+38h+Data]
0x180020848  mov     [rsp+38h+cbData], 4
0x180020850  xor     r9d, r9d; lpType
0x180020853  mov     [rsp+38h+phkResult], rax; lpData
0x180020858  xor     r8d, r8d; lpReserved
0x18002085b  call    cs:__imp_RegQueryValueExW
0x180020861  test    eax, eax
0x180020863  jnz     short loc_180020875
0x180020865  cmp     [rsp+38h+Data], eax
0x180020869  jz      short loc_180020875
0x18002086b  mov     dword ptr [rbx+158h], 1
0x180020875  mov     rcx, [rsp+38h+hKey]; hKey
0x18002087a  test    rcx, rcx
0x18002087d  jz      short loc_180020885
0x18002087f  call    cs:__imp_RegCloseKey
0x180020885  mov     rcx, cs:WPP_GLOBAL_Control
0x18002088c  test    byte ptr [rcx+1Ch], 1
0x180020890  jz      short loc_1800208AD
0x180020892  cmp     byte ptr [rcx+19h], 4
0x180020896  jb      short loc_1800208AD
0x180020898  mov     rcx, [rcx+10h]
0x18002089c  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x1800208a3  mov     edx, 0Fh
0x1800208a8  call    WPP_SF_
0x1800208ad  add     rsp, 30h
0x1800208b1  pop     rbx
0x1800208b2  retn
```
