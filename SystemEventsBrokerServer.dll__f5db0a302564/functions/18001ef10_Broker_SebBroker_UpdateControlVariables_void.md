# Broker::SebBroker::UpdateControlVariables(void)

- ea: `0x18001ef10`
- end: `0x18001f055`
- name: `?UpdateControlVariables@SebBroker@Broker@@AEAAXXZ`
- size: `325`
- prototype: `void __fastcall(Broker::SebBroker *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c228`

## callees

- `0x180005a50`
- `0x18001ef10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001efbd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001effd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001efbd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001effd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ef85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ef85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f01c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f01c`

## string_xrefs

- `0x18001ef77`: `SYSTEM\CurrentControlSet\Services\SystemEventsBroker\Parameters`

## pseudocode

```c
void __fastcall Broker::SebBroker::UpdateControlVariables(Broker::SebBroker *this)
{
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+18h] BYREF
  int Data; // [rsp+60h] [rbp+20h] BYREF
  int v5; // [rsp+68h] [rbp+28h] BYREF

  Data = 0;
  v5 = 0;
  cbData = 0;
  hKey = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\SystemEventsBroker\\Parameters",
          0,
          1u,
          &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"NoParamValidation", 0, 0, (LPBYTE)&Data, &cbData) && Data )
      *((_DWORD *)this + 30) = 1;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"RegisterPrivateEnabled", 0, 0, (LPBYTE)&v5, &cbData) && v5 )
      *((_DWORD *)this + 31) = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
}

```

## disassembly

```asm
0x18001ef10  mov     [rsp-8+arg_0], rbx
0x18001ef15  push    rbp
0x18001ef16  mov     rbp, rsp
0x18001ef19  sub     rsp, 40h
0x18001ef1d  mov     rbx, rcx
0x18001ef20  mov     [rbp+Data], 0
0x18001ef27  mov     [rbp+arg_18], 0
0x18001ef2e  mov     [rbp+cbData], 0
0x18001ef35  mov     [rbp+hKey], 0
0x18001ef3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef44  test    byte ptr [rcx+1Ch], 1
0x18001ef48  jz      short loc_18001EF65
0x18001ef4a  cmp     byte ptr [rcx+19h], 4
0x18001ef4e  jb      short loc_18001EF65
0x18001ef50  mov     rcx, [rcx+10h]
0x18001ef54  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001ef5b  mov     edx, 0Ch
0x18001ef60  call    WPP_SF_
0x18001ef65  lea     rax, [rbp+hKey]
0x18001ef69  mov     r9d, 1; samDesired
0x18001ef6f  xor     r8d, r8d; ulOptions
0x18001ef72  mov     [rsp+40h+phkResult], rax; phkResult
0x18001ef77  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Sy"...
0x18001ef7e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ef85  call    cs:__imp_RegOpenKeyExW
0x18001ef8b  test    eax, eax
0x18001ef8d  jnz     loc_18001F013
0x18001ef93  mov     rcx, [rbp+hKey]; hKey
0x18001ef97  lea     rax, [rbp+cbData]
0x18001ef9b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001efa0  lea     rdx, ValueName; "NoParamValidation"
0x18001efa7  lea     rax, [rbp+Data]
0x18001efab  mov     [rbp+cbData], 4
0x18001efb2  xor     r9d, r9d; lpType
0x18001efb5  mov     [rsp+40h+phkResult], rax; lpData
0x18001efba  xor     r8d, r8d; lpReserved
0x18001efbd  call    cs:__imp_RegQueryValueExW
0x18001efc3  test    eax, eax
0x18001efc5  jnz     short loc_18001EFD3
0x18001efc7  cmp     [rbp+Data], eax
0x18001efca  jz      short loc_18001EFD3
0x18001efcc  mov     dword ptr [rbx+78h], 1
0x18001efd3  mov     rcx, [rbp+hKey]; hKey
0x18001efd7  lea     rax, [rbp+cbData]
0x18001efdb  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001efe0  lea     rdx, aRegisterprivat; "RegisterPrivateEnabled"
0x18001efe7  lea     rax, [rbp+arg_18]
0x18001efeb  mov     [rbp+cbData], 4
0x18001eff2  xor     r9d, r9d; lpType
0x18001eff5  mov     [rsp+40h+phkResult], rax; lpData
0x18001effa  xor     r8d, r8d; lpReserved
0x18001effd  call    cs:__imp_RegQueryValueExW
0x18001f003  test    eax, eax
0x18001f005  jnz     short loc_18001F013
0x18001f007  cmp     [rbp+arg_18], eax
0x18001f00a  jz      short loc_18001F013
0x18001f00c  mov     dword ptr [rbx+7Ch], 1
0x18001f013  mov     rcx, [rbp+hKey]; hKey
0x18001f017  test    rcx, rcx
0x18001f01a  jz      short loc_18001F022
0x18001f01c  call    cs:__imp_RegCloseKey
0x18001f022  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f029  test    byte ptr [rcx+1Ch], 1
0x18001f02d  jz      short loc_18001F04A
0x18001f02f  cmp     byte ptr [rcx+19h], 4
0x18001f033  jb      short loc_18001F04A
0x18001f035  mov     rcx, [rcx+10h]
0x18001f039  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001f040  mov     edx, 0Dh
0x18001f045  call    WPP_SF_
0x18001f04a  mov     rbx, [rsp+40h+arg_0]
0x18001f04f  add     rsp, 40h
0x18001f053  pop     rbp
0x18001f054  retn
```
