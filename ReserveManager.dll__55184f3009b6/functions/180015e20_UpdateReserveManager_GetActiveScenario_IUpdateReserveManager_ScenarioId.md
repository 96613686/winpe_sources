# UpdateReserveManager::GetActiveScenario(IUpdateReserveManager::ScenarioId *)

- ea: `0x180015e20`
- end: `0x180015f1e`
- name: `?GetActiveScenario@UpdateReserveManager@@AEAAJPEAW4ScenarioId@IUpdateReserveManager@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(HKEY *this, enum IUpdateReserveManager::ScenarioId *)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012340`
- `0x180014960`
- `0x1800155e0`
- `0x180016fb8`
- `0x1800172a8`
- `0x1800192e0`
- `0x180019634`
- `0x180021850`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x180015ad0`
- `0x180015e20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015e91`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015e91`

## string_xrefs

- `0x180015ea2`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180015eb7`: `UpdateReserveManager::GetActiveScenario`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::GetActiveScenario(HKEY *this, enum IUpdateReserveManager::ScenarioId *a2)
{
  __int64 result; // rax
  HKEY v5; // rcx
  LSTATUS ValueW; // eax
  unsigned int v7; // ebx
  int v8; // edx
  _QWORD v9[4]; // [rsp+40h] [rbp-38h] BYREF
  int pvData; // [rsp+60h] [rbp-18h] BYREF
  DWORD pcbData; // [rsp+64h] [rbp-14h] BYREF

  result = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)this);
  if ( (int)result >= 0 )
  {
    v5 = this[13];
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(
               v5,
               L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
               L"ActiveScenario",
               0x10u,
               0,
               &pvData,
               &pcbData);
    v7 = ValueW;
    if ( ValueW == 2 || !ValueW )
    {
      v8 = pvData;
      result = 0;
      if ( (unsigned int)(pvData - 3) > 1 )
        v8 = 0;
      *(_DWORD *)a2 = v8;
    }
    else
    {
      v9[2] = 3557;
      v9[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v9[1] = "UpdateReserveManager::GetActiveScenario";
      v9[3] = "RetValue";
      if ( ValueW > 0 )
        v7 = (unsigned __int16)ValueW | 0x80070000;
      RtlReportErrorOrigination(v9, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v7);
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015e20  mov     [rsp+arg_10], rbx
0x180015e25  push    rdi
0x180015e26  sub     rsp, 70h
0x180015e2a  mov     rax, cs:__security_cookie
0x180015e31  xor     rax, rsp
0x180015e34  mov     [rsp+78h+var_10], rax
0x180015e39  mov     rdi, rdx
0x180015e3c  mov     rbx, rcx
0x180015e3f  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x180015e44  test    eax, eax
0x180015e46  js      loc_180015F03
0x180015e4c  mov     rcx, [rbx+68h]; hkey
0x180015e50  lea     rax, [rsp+78h+var_14]
0x180015e55  mov     [rsp+78h+pcbData], rax; pcbData
0x180015e5a  lea     r8, aActivescenario; "ActiveScenario"
0x180015e61  lea     rax, [rsp+78h+var_18]
0x180015e66  mov     [rsp+78h+var_18], 0
0x180015e6e  mov     [rsp+78h+pvData], rax; pvData
0x180015e73  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180015e7a  mov     r9d, 10h; dwFlags
0x180015e80  mov     [rsp+78h+pdwType], 0; pdwType
0x180015e89  mov     [rsp+78h+var_14], 4
0x180015e91  call    cs:__imp_RegGetValueW
0x180015e97  mov     ebx, eax
0x180015e99  cmp     eax, 2
0x180015e9c  jz      short loc_180015EF2
0x180015e9e  test    eax, eax
0x180015ea0  jz      short loc_180015EF2
0x180015ea2  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180015ea9  mov     [rsp+78h+var_28], 0DE5h
0x180015eb2  mov     [rsp+78h+var_38], rax
0x180015eb7  lea     rax, aUpdatereservem_0; "UpdateReserveManager::GetActiveScenario"
0x180015ebe  mov     [rsp+78h+var_30], rax
0x180015ec3  lea     rax, aRetvalue; "RetValue"
0x180015eca  mov     [rsp+78h+var_20], rax
0x180015ecf  jle     short loc_180015EDA
0x180015ed1  movzx   ebx, bx
0x180015ed4  or      ebx, 80070000h
0x180015eda  mov     r8d, ebx
0x180015edd  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180015ee4  lea     rcx, [rsp+78h+var_38]
0x180015ee9  call    RtlReportErrorOrigination
0x180015eee  mov     eax, ebx
0x180015ef0  jmp     short loc_180015F03
0x180015ef2  mov     edx, [rsp+78h+var_18]
0x180015ef6  xor     eax, eax
0x180015ef8  lea     ecx, [rdx-3]
0x180015efb  cmp     ecx, 1
0x180015efe  cmova   edx, eax
0x180015f01  mov     [rdi], edx
0x180015f03  mov     rcx, [rsp+78h+var_10]
0x180015f08  xor     rcx, rsp; StackCookie
0x180015f0b  call    __security_check_cookie
0x180015f10  mov     rbx, [rsp+78h+arg_10]
0x180015f18  add     rsp, 70h
0x180015f1c  pop     rdi
0x180015f1d  retn
```
