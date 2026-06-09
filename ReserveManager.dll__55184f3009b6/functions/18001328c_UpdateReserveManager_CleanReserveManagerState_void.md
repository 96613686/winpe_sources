# UpdateReserveManager::CleanReserveManagerState(void)

- ea: `0x18001328c`
- end: `0x1800133be`
- name: `?CleanReserveManagerState@UpdateReserveManager@@AEAAJXZ`
- size: `306`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b3d0`
- `0x18001b760`

## callees

- `0x18000fafc`
- `0x18001328c`
- `0x180015ad0`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x1800132c0`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x180013331`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x18001335e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x18001338e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x1800132c0`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x180013331`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x18001335e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x18001338e`

## string_xrefs

- `0x1800132d9`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180013380`: `TiAttemptedInitialization`
- `0x1800132e4`: `UpdateReserveManager::CleanReserveManagerState`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::CleanReserveManagerState(HKEY *this)
{
  __int64 result; // rax
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  bool v5; // zf
  bool v6; // sf
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  _QWORD v10[2]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v11; // [rsp+30h] [rbp-10h]
  const char *v12; // [rsp+38h] [rbp-8h]

  result = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)this);
  if ( (int)result >= 0 )
  {
    v3 = RegDeleteKeyValueW(this[13], L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"ShippedWithReserves");
    v4 = v3;
    if ( v3 == 2 || (v5 = v3 == 0, v6 = v3 < 0, !v3) )
    {
      v7 = RegDeleteKeyValueW(this[13], L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"PassedPolicy");
      v4 = v7;
      if ( v7 == 2 || (v5 = v7 == 0, v6 = v7 < 0, !v7) )
      {
        v8 = RegDeleteKeyValueW(this[13], L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"UserFreeSpaceMarker");
        v4 = v8;
        if ( v8 == 2 || (v5 = v8 == 0, v6 = v8 < 0, !v8) )
        {
          v9 = RegDeleteKeyValueW(
                 this[13],
                 L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                 L"TiAttemptedInitialization");
          v4 = v9;
          if ( v9 == 2 )
            return 0;
          v5 = v9 == 0;
          v6 = v9 < 0;
          if ( !v9 )
            return 0;
          v11 = 4300;
        }
        else
        {
          v11 = 4290;
        }
      }
      else
      {
        v11 = 4281;
      }
    }
    else
    {
      v11 = 4271;
    }
    v10[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v10[1] = "UpdateReserveManager::CleanReserveManagerState";
    v12 = "RetValue";
    if ( !v6 && !v5 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    RtlReportErrorOrigination(v10, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v4);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18001328c  mov     [rsp-8+arg_8], rbx
0x180013291  mov     [rsp-8+arg_10], rdi
0x180013296  push    rbp
0x180013297  mov     rbp, rsp
0x18001329a  sub     rsp, 40h
0x18001329e  mov     rdi, rcx
0x1800132a1  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x1800132a6  test    eax, eax
0x1800132a8  js      loc_1800133AE
0x1800132ae  mov     rcx, [rdi+68h]; hKey
0x1800132b2  lea     r8, ValueName; "ShippedWithReserves"
0x1800132b9  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x1800132c0  call    cs:__imp_RegDeleteKeyValueW
0x1800132c6  mov     ebx, eax
0x1800132c8  cmp     eax, 2
0x1800132cb  jz      short loc_18001331F
0x1800132cd  test    eax, eax
0x1800132cf  jz      short loc_18001331F
0x1800132d1  mov     [rbp+var_10], 10AFh
0x1800132d9  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800132e0  mov     [rbp+var_20], rax
0x1800132e4  lea     rax, aUpdatereservem_18; "UpdateReserveManager::CleanReserveManag"...
0x1800132eb  mov     [rbp+var_18], rax
0x1800132ef  lea     rax, aRetvalue; "RetValue"
0x1800132f6  mov     [rbp+var_8], rax
0x1800132fa  jle     short loc_180013305
0x1800132fc  movzx   ebx, bx
0x1800132ff  or      ebx, 80070000h
0x180013305  mov     r8d, ebx
0x180013308  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001330f  lea     rcx, [rbp+var_20]
0x180013313  call    RtlReportErrorOrigination
0x180013318  mov     eax, ebx
0x18001331a  jmp     loc_1800133AE
0x18001331f  mov     rcx, [rdi+68h]; hKey
0x180013323  lea     r8, aPassedpolicy; "PassedPolicy"
0x18001332a  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180013331  call    cs:__imp_RegDeleteKeyValueW
0x180013337  mov     ebx, eax
0x180013339  cmp     eax, 2
0x18001333c  jz      short loc_18001334C
0x18001333e  test    eax, eax
0x180013340  jz      short loc_18001334C
0x180013342  mov     [rbp+var_10], 10B9h
0x18001334a  jmp     short loc_1800132D9
0x18001334c  mov     rcx, [rdi+68h]; hKey
0x180013350  lea     r8, aUserfreespacem; "UserFreeSpaceMarker"
0x180013357  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x18001335e  call    cs:__imp_RegDeleteKeyValueW
0x180013364  mov     ebx, eax
0x180013366  cmp     eax, 2
0x180013369  jz      short loc_18001337C
0x18001336b  test    eax, eax
0x18001336d  jz      short loc_18001337C
0x18001336f  mov     [rbp+var_10], 10C2h
0x180013377  jmp     loc_1800132D9
0x18001337c  mov     rcx, [rdi+68h]; hKey
0x180013380  lea     r8, aTiattemptedini; "TiAttemptedInitialization"
0x180013387  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x18001338e  call    cs:__imp_RegDeleteKeyValueW
0x180013394  mov     ebx, eax
0x180013396  cmp     eax, 2
0x180013399  jz      short loc_1800133AC
0x18001339b  test    eax, eax
0x18001339d  jz      short loc_1800133AC
0x18001339f  mov     [rbp+var_10], 10CCh
0x1800133a7  jmp     loc_1800132D9
0x1800133ac  xor     eax, eax
0x1800133ae  mov     rbx, [rsp+40h+arg_8]
0x1800133b3  mov     rdi, [rsp+40h+arg_10]
0x1800133b8  add     rsp, 40h
0x1800133bc  pop     rbp
0x1800133bd  retn
```
