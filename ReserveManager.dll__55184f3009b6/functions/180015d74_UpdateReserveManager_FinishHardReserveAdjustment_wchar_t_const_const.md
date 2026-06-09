# UpdateReserveManager::FinishHardReserveAdjustment(wchar_t const * const)

- ea: `0x180015d74`
- end: `0x180015e18`
- name: `?FinishHardReserveAdjustment@UpdateReserveManager@@AEAAJQEB_W@Z`
- size: `164`
- prototype: `__int64 __fastcall(HKEY *this, const WCHAR *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180013850`
- `0x18001d140`

## callees

- `0x18000fafc`
- `0x180015d74`
- `0x180019634`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180015d8e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180015d8e`

## string_xrefs

- `0x180015da3`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180015db8`: `UpdateReserveManager::FinishHardReserveAdjustment`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::FinishHardReserveAdjustment(HKEY *this, const WCHAR *a2)
{
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  __int64 result; // rax
  _QWORD v6[5]; // [rsp+20h] [rbp-28h] BYREF

  v3 = RegDeleteKeyExW(this[13], a2, 0x100u, 0);
  v4 = v3;
  if ( v3 == 2 || !v3 )
  {
    if ( *((_BYTE *)this + 1178) )
      return 0;
    result = UpdateReserveManager::InitializeReservesInternal(this, 2);
    if ( (int)result >= 0 )
      return 0;
  }
  else
  {
    v6[2] = 3813;
    v6[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v6[1] = "UpdateReserveManager::FinishHardReserveAdjustment";
    v6[3] = "RetValue";
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    RtlReportErrorOrigination(v6, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v4);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180015d74  mov     [rsp+arg_10], rbx
0x180015d79  push    rdi
0x180015d7a  sub     rsp, 40h
0x180015d7e  mov     rdi, rcx
0x180015d81  xor     r9d, r9d; Reserved
0x180015d84  mov     rcx, [rcx+68h]; hKey
0x180015d88  mov     r8d, 100h; samDesired
0x180015d8e  call    cs:__imp_RegDeleteKeyExW
0x180015d94  mov     edx, 2
0x180015d99  mov     ebx, eax
0x180015d9b  cmp     eax, edx
0x180015d9d  jz      short loc_180015DF3
0x180015d9f  test    eax, eax
0x180015da1  jz      short loc_180015DF3
0x180015da3  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180015daa  mov     [rsp+48h+var_18], 0EE5h
0x180015db3  mov     [rsp+48h+var_28], rax
0x180015db8  lea     rax, aUpdatereservem_15; "UpdateReserveManager::FinishHardReserve"...
0x180015dbf  mov     [rsp+48h+var_20], rax
0x180015dc4  lea     rax, aRetvalue; "RetValue"
0x180015dcb  mov     [rsp+48h+var_10], rax
0x180015dd0  jle     short loc_180015DDB
0x180015dd2  movzx   ebx, bx
0x180015dd5  or      ebx, 80070000h
0x180015ddb  mov     r8d, ebx
0x180015dde  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180015de5  lea     rcx, [rsp+48h+var_28]
0x180015dea  call    RtlReportErrorOrigination
0x180015def  mov     eax, ebx
0x180015df1  jmp     short loc_180015E0D
0x180015df3  cmp     byte ptr [rdi+49Ah], 0
0x180015dfa  jnz     short loc_180015E0B
0x180015dfc  xor     r8d, r8d
0x180015dff  mov     rcx, rdi
0x180015e02  call    ?InitializeReservesInternal@UpdateReserveManager@@AEAAJW4InitializeReservesFlags@IUpdateReserveManager@@PEA_N@Z; UpdateReserveManager::InitializeReservesInternal(IUpdateReserveManager::InitializeReservesFlags,bool *)
0x180015e07  test    eax, eax
0x180015e09  js      short loc_180015E0D
0x180015e0b  xor     eax, eax
0x180015e0d  mov     rbx, [rsp+48h+arg_10]
0x180015e12  add     rsp, 40h
0x180015e16  pop     rdi
0x180015e17  retn
```
