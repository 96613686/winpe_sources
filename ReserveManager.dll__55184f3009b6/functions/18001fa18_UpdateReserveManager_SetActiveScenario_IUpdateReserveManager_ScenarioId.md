# UpdateReserveManager::SetActiveScenario(IUpdateReserveManager::ScenarioId)

- ea: `0x18001fa18`
- end: `0x18001fae9`
- name: `?SetActiveScenario@UpdateReserveManager@@AEAAJW4ScenarioId@IUpdateReserveManager@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(UpdateReserveManager *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012340`
- `0x1800155e0`
- `0x18001b560`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x180015ad0`
- `0x18001fa18`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x18001fa6e`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x18001fa6e`

## string_xrefs

- `0x18001fa83`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001fa8f`: `UpdateReserveManager::SetActiveScenario`
- `0x18001fa9b`: `::RegSetKeyValueW(m_SoftwareKey, L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"ActiveScenario", ( 4ul ), &Value, sizeof(Value))`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::SetActiveScenario(UpdateReserveManager *a1, int a2)
{
  __int64 result; // rax
  HKEY v5; // rcx
  int v6; // ebx
  _QWORD v7[4]; // [rsp+30h] [rbp-38h] BYREF
  int Data; // [rsp+50h] [rbp-18h] BYREF

  result = UpdateReserveManager::EnsureNotInSafeMode(a1);
  if ( (int)result >= 0 )
  {
    v5 = (HKEY)*((_QWORD *)a1 + 13);
    Data = a2;
    v6 = RegSetKeyValueW(v5, L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"ActiveScenario", 4u, &Data, 4u);
    if ( v6 )
    {
      v7[2] = 3531;
      v7[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v7[1] = "UpdateReserveManager::SetActiveScenario";
      v7[3] = "::RegSetKeyValueW(m_SoftwareKey, L\"Microsoft\\\\Windows\\\\CurrentVersion\\\\ReserveManager\", L\"ActiveS"
              "cenario\", ( 4ul ), &Value, sizeof(Value))";
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      RtlReportErrorOrigination(v7, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v6);
      return (unsigned int)v6;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001fa18  mov     [rsp+arg_10], rbx
0x18001fa1d  push    rdi
0x18001fa1e  sub     rsp, 60h
0x18001fa22  mov     rax, cs:__security_cookie
0x18001fa29  xor     rax, rsp
0x18001fa2c  mov     [rsp+68h+var_10], rax
0x18001fa31  mov     edi, edx
0x18001fa33  mov     rbx, rcx
0x18001fa36  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001fa3b  test    eax, eax
0x18001fa3d  js      loc_18001FACE
0x18001fa43  mov     rcx, [rbx+68h]; hKey
0x18001fa47  lea     rax, [rsp+68h+Data]
0x18001fa4c  mov     r9d, 4; dwType
0x18001fa52  mov     [rsp+68h+Data], edi
0x18001fa56  mov     [rsp+68h+cbData], r9d; cbData
0x18001fa5b  lea     r8, aActivescenario; "ActiveScenario"
0x18001fa62  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x18001fa69  mov     [rsp+68h+lpData], rax; lpData
0x18001fa6e  call    cs:__imp_RegSetKeyValueW
0x18001fa74  mov     ebx, eax
0x18001fa76  test    eax, eax
0x18001fa78  jz      short loc_18001FACC
0x18001fa7a  mov     [rsp+68h+var_28], 0DCBh
0x18001fa83  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001fa8a  mov     [rsp+68h+var_38], rax
0x18001fa8f  lea     rax, aUpdatereservem_17; "UpdateReserveManager::SetActiveScenario"
0x18001fa96  mov     [rsp+68h+var_30], rax
0x18001fa9b  lea     rax, aRegsetkeyvalue_3; "::RegSetKeyValueW(m_SoftwareKey, L\"Mic"...
0x18001faa2  mov     [rsp+68h+var_20], rax
0x18001faa7  test    ebx, ebx
0x18001faa9  jle     short loc_18001FAB4
0x18001faab  movzx   ebx, bx
0x18001faae  or      ebx, 80070000h
0x18001fab4  mov     r8d, ebx
0x18001fab7  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001fabe  lea     rcx, [rsp+68h+var_38]
0x18001fac3  call    RtlReportErrorOrigination
0x18001fac8  mov     eax, ebx
0x18001faca  jmp     short loc_18001FACE
0x18001facc  xor     eax, eax
0x18001face  mov     rcx, [rsp+68h+var_10]
0x18001fad3  xor     rcx, rsp; StackCookie
0x18001fad6  call    __security_check_cookie
0x18001fadb  mov     rbx, [rsp+68h+arg_10]
0x18001fae3  add     rsp, 60h
0x18001fae7  pop     rdi
0x18001fae8  retn
```
