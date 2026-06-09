# Wallet::WalletLocationManager::GetIsLocationServicesEnabled(int *)

- ea: `0x1800159f0`
- end: `0x180015abf`
- name: `?GetIsLocationServicesEnabled@WalletLocationManager@Wallet@@UEAAJPEAH@Z`
- size: `207`
- prototype: `__int64 __fastcall(Wallet::WalletLocationManager *__hidden this, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180014230`
- `0x1800159f0`
- `0x180043090`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x180015a94`
- `ntdll!NtQueryWnfStateData` at `0x180015a94`

## string_xrefs

- `0x180015a3d`: `GetIsLocationServicesEnabled`

## pseudocode

```c
__int64 __fastcall Wallet::WalletLocationManager::GetIsLocationServicesEnabled(
        Wallet::WalletLocationManager *this,
        int *a2)
{
  __int64 result; // rax
  int v4; // [rsp+30h] [rbp-30h] BYREF
  int v5; // [rsp+34h] [rbp-2Ch] BYREF
  int v6; // [rsp+38h] [rbp-28h] BYREF
  int *v7; // [rsp+40h] [rbp-20h] BYREF
  __int64 v8; // [rsp+48h] [rbp-18h] BYREF
  __int64 v9; // [rsp+50h] [rbp-10h] BYREF

  if ( _InterlockedIncrement(&dword_18006BDC4) == 1 )
  {
    v8 = 0;
    v7 = &dword_18006BDC4;
    wil::details::ApiTelemetryLogger::InitApiData<unsigned short const (&)[22],unsigned short const (&)[29],std::nullptr_t,long volatile *>(
      this,
      L"GetIsLocationServicesEnabled",
      &v8,
      &v7);
  }
  v9 = WNF_LFS_MASTERSWITCH_STATE;
  v6 = 0;
  v4 = 0;
  v5 = 4;
  if ( !a2 )
    return 2147500035LL;
  result = (unsigned int)NtQueryWnfStateData(&v9, 0, 0, &v6, &v4, &v5) | 0x10000000;
  if ( (int)result >= 0 )
  {
    result = 0;
    *a2 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800159f0  mov     [rsp-8+arg_0], rbx
0x1800159f5  push    rbp
0x1800159f6  mov     rbp, rsp
0x1800159f9  sub     rsp, 60h
0x1800159fd  mov     rax, cs:__security_cookie
0x180015a04  xor     rax, rsp
0x180015a07  mov     [rbp+var_8], rax
0x180015a0b  mov     rbx, rdx
0x180015a0e  mov     eax, 1
0x180015a13  lock xadd cs:dword_18006BDC4, eax
0x180015a1b  inc     eax
0x180015a1d  cmp     eax, 1
0x180015a20  jnz     short loc_180015A49
0x180015a22  lea     rax, dword_18006BDC4
0x180015a29  mov     [rbp+var_18], 0
0x180015a31  lea     r9, [rbp+var_20]
0x180015a35  mov     [rbp+var_20], rax
0x180015a39  lea     r8, [rbp+var_18]
0x180015a3d  lea     rdx, aGetislocations; "GetIsLocationServicesEnabled"
0x180015a44  call    ??$InitApiData@AEAY0BG@$$CBGAEAY0BN@$$CBG$$TPECJ@ApiTelemetryLogger@details@wil@@SAXAEAY0BG@$$CBGAEAY0BN@$$CBG$$QEA$$T$$QEAPECJ@Z
0x180015a49  mov     rax, cs:WNF_LFS_MASTERSWITCH_STATE
0x180015a50  mov     [rbp+var_10], rax
0x180015a54  mov     [rbp+var_28], 0
0x180015a5b  mov     [rbp+var_30], 0
0x180015a62  mov     [rbp+var_2C], 4
0x180015a69  test    rbx, rbx
0x180015a6c  jnz     short loc_180015A75
0x180015a6e  mov     eax, 80004003h
0x180015a73  jmp     short loc_180015AA8
0x180015a75  lea     rax, [rbp+var_2C]
0x180015a79  xor     r8d, r8d
0x180015a7c  mov     [rsp+60h+var_38], rax
0x180015a81  lea     r9, [rbp+var_28]
0x180015a85  lea     rax, [rbp+var_30]
0x180015a89  xor     edx, edx
0x180015a8b  lea     rcx, [rbp+var_10]
0x180015a8f  mov     [rsp+60h+var_40], rax
0x180015a94  call    cs:__imp_NtQueryWnfStateData
0x180015a9a  or      eax, 10000000h
0x180015a9f  jl      short loc_180015AA8
0x180015aa1  mov     ecx, [rbp+var_30]
0x180015aa4  xor     eax, eax
0x180015aa6  mov     [rbx], ecx
0x180015aa8  mov     rcx, [rbp+var_8]
0x180015aac  xor     rcx, rsp; StackCookie
0x180015aaf  call    __security_check_cookie
0x180015ab4  mov     rbx, [rsp+60h+arg_0]
0x180015ab9  add     rsp, 60h
0x180015abd  pop     rbp
0x180015abe  retn
```
