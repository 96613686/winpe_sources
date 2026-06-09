# UpdateReserveManager::GetReserveIdForScenario(IUpdateReserveManager::ScenarioId,_STORAGE_RESERVE_ID *)

- ea: `0x180016fb8`
- end: `0x1800170e3`
- name: `?GetReserveIdForScenario@UpdateReserveManager@@AEAAJW4ScenarioId@IUpdateReserveManager@@PEAW4_STORAGE_RESERVE_ID@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(UpdateReserveManager *, int, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001ac20`
- `0x18001c9e0`

## callees

- `0x18000fafc`
- `0x180015ad0`
- `0x180015e20`
- `0x180016fb8`

## string_xrefs

- `0x18001702a`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180017070`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180017044`: `UpdateReserveManager::GetReserveIdForScenario`
- `0x18001708a`: `UpdateReserveManager::GetReserveIdForScenario`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::GetReserveIdForScenario(UpdateReserveManager *a1, int a2, _DWORD *a3)
{
  __int64 result; // rax
  int v7; // [rsp+20h] [rbp-30h] BYREF
  const char *v8; // [rsp+28h] [rbp-28h] BYREF
  const char *v9; // [rsp+30h] [rbp-20h]
  __int64 v10; // [rsp+38h] [rbp-18h]
  const char *v11; // [rsp+40h] [rbp-10h]

  result = UpdateReserveManager::EnsureNotInSafeMode(a1);
  if ( (int)result >= 0 )
  {
    switch ( a2 )
    {
      case 0:
        *a3 = 0;
        return 0;
      case 1:
        goto LABEL_13;
      case 2:
        *a3 = 2;
        break;
      case 6:
        *a3 = 3;
        break;
      case 7:
        v10 = 3464;
        v8 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v9 = "UpdateReserveManager::GetReserveIdForScenario";
        v11 = "((SCODE) (((unsigned long)(1)<<31) | ((unsigned long)(15)<<16) | ((unsigned long)(0x973))) )";
        RtlReportErrorOrigination(&v8, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2148469107LL);
        return 2148469107LL;
      default:
        v7 = 0;
        result = UpdateReserveManager::GetActiveScenario((HKEY *)a1, (enum IUpdateReserveManager::ScenarioId *)&v7);
        if ( (int)result < 0 )
          return result;
        if ( v7 != a2 )
        {
          v10 = 3473;
          v8 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v9 = "UpdateReserveManager::GetReserveIdForScenario";
          v11 = "((SCODE) (((unsigned long)(1)<<31) | ((unsigned long)(15)<<16) | ((unsigned long)(0x971))) )";
          RtlReportErrorOrigination(&v8, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2148469105LL);
          return 2148469105LL;
        }
LABEL_13:
        *a3 = 1;
        return 0;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180016fb8  mov     [rsp-18h+arg_8], rbx
0x180016fbd  push    rbp
0x180016fbe  push    rsi
0x180016fbf  push    rdi
0x180016fc0  mov     rbp, rsp
0x180016fc3  sub     rsp, 50h
0x180016fc7  mov     rbx, r8
0x180016fca  mov     edi, edx
0x180016fcc  mov     rsi, rcx
0x180016fcf  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x180016fd4  test    eax, eax
0x180016fd6  js      loc_1800170D6
0x180016fdc  mov     eax, edi
0x180016fde  test    edi, edi
0x180016fe0  jz      loc_1800170CE
0x180016fe6  sub     eax, 1
0x180016fe9  jz      loc_1800170C6
0x180016fef  sub     eax, 1
0x180016ff2  jz      loc_1800170BE
0x180016ff8  sub     eax, 4
0x180016ffb  jz      loc_1800170B6
0x180017001  cmp     eax, 1
0x180017004  jz      short loc_180017070
0x180017006  lea     rdx, [rbp+var_30]; enum IUpdateReserveManager::ScenarioId *
0x18001700a  mov     [rbp+var_30], 0
0x180017011  mov     rcx, rsi; this
0x180017014  call    ?GetActiveScenario@UpdateReserveManager@@AEAAJPEAW4ScenarioId@IUpdateReserveManager@@@Z; UpdateReserveManager::GetActiveScenario(IUpdateReserveManager::ScenarioId *)
0x180017019  test    eax, eax
0x18001701b  js      loc_1800170D6
0x180017021  cmp     [rbp+var_30], edi
0x180017024  jz      loc_1800170C6
0x18001702a  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180017031  mov     [rbp+var_18], 0D91h
0x180017039  mov     [rbp+var_28], rax
0x18001703d  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180017044  lea     rax, aUpdatereservem_10; "UpdateReserveManager::GetReserveIdForSc"...
0x18001704b  mov     r8d, 800F0971h
0x180017051  mov     [rbp+var_20], rax
0x180017055  lea     rcx, [rbp+var_28]
0x180017059  lea     rax, aScodeUnsignedL_4; "((SCODE) (((unsigned long)(1)<<31) | (("...
0x180017060  mov     [rbp+var_10], rax
0x180017064  call    RtlReportErrorOrigination
0x180017069  mov     eax, 800F0971h
0x18001706e  jmp     short loc_1800170D6
0x180017070  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180017077  mov     [rbp+var_18], 0D88h
0x18001707f  mov     [rbp+var_28], rax
0x180017083  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001708a  lea     rax, aUpdatereservem_10; "UpdateReserveManager::GetReserveIdForSc"...
0x180017091  mov     r8d, 800F0973h
0x180017097  mov     [rbp+var_20], rax
0x18001709b  lea     rcx, [rbp+var_28]
0x18001709f  lea     rax, aScodeUnsignedL_3; "((SCODE) (((unsigned long)(1)<<31) | (("...
0x1800170a6  mov     [rbp+var_10], rax
0x1800170aa  call    RtlReportErrorOrigination
0x1800170af  mov     eax, 800F0973h
0x1800170b4  jmp     short loc_1800170D6
0x1800170b6  mov     dword ptr [rbx], 3
0x1800170bc  jmp     short loc_1800170D4
0x1800170be  mov     dword ptr [rbx], 2
0x1800170c4  jmp     short loc_1800170D4
0x1800170c6  mov     dword ptr [rbx], 1
0x1800170cc  jmp     short loc_1800170D4
0x1800170ce  mov     dword ptr [rbx], 0
0x1800170d4  xor     eax, eax
0x1800170d6  mov     rbx, [rsp+50h+arg_8]
0x1800170db  add     rsp, 50h
0x1800170df  pop     rdi
0x1800170e0  pop     rsi
0x1800170e1  pop     rbp
0x1800170e2  retn
```
