# UpdateReserveManager::GetScenarioIdForReserve(_STORAGE_RESERVE_ID,IUpdateReserveManager::ScenarioId *)

- ea: `0x1800172a8`
- end: `0x18001736c`
- name: `?GetScenarioIdForReserve@UpdateReserveManager@@AEAAJW4_STORAGE_RESERVE_ID@@PEAW4ScenarioId@IUpdateReserveManager@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this, enum _STORAGE_RESERVE_ID, enum IUpdateReserveManager::ScenarioId *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180017380`

## callees

- `0x18000fafc`
- `0x180015ad0`
- `0x180015e20`
- `0x1800172a8`

## string_xrefs

- `0x1800172e3`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800172ff`: `UpdateReserveManager::GetScenarioIdForReserve`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::GetScenarioIdForReserve(
        UpdateReserveManager *this,
        enum _STORAGE_RESERVE_ID a2,
        enum IUpdateReserveManager::ScenarioId *a3)
{
  __int64 result; // rax
  int v7; // ebx
  int v8; // ebx
  int ActiveScenario; // eax
  unsigned int v10; // ecx
  _QWORD v11[5]; // [rsp+20h] [rbp-28h] BYREF

  result = UpdateReserveManager::EnsureNotInSafeMode(this);
  if ( (int)result >= 0 )
  {
    if ( a2 == StorageReserveIdNone )
    {
      *(_DWORD *)a3 = 0;
      return 0;
    }
    v7 = a2 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        if ( v8 != 1 )
        {
          v11[2] = 3510;
          v11[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v11[1] = "UpdateReserveManager::GetScenarioIdForReserve";
          v11[3] = "((SCODE) (((unsigned long)(1)<<31) | ((unsigned long)(15)<<16) | ((unsigned long)(0x972))) )";
          RtlReportErrorOrigination(v11, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2148469106LL);
          return 2148469106LL;
        }
        *(_DWORD *)a3 = 6;
      }
      else
      {
        *(_DWORD *)a3 = 2;
      }
      return 0;
    }
    ActiveScenario = UpdateReserveManager::GetActiveScenario((HKEY *)this, a3);
    v10 = 0;
    if ( ActiveScenario < 0 )
      return (unsigned int)ActiveScenario;
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x1800172a8  mov     [rsp+arg_8], rbx
0x1800172ad  mov     [rsp+arg_18], rsi
0x1800172b2  push    rdi
0x1800172b3  sub     rsp, 40h
0x1800172b7  mov     rdi, r8
0x1800172ba  mov     ebx, edx
0x1800172bc  mov     rsi, rcx
0x1800172bf  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x1800172c4  test    eax, eax
0x1800172c6  js      loc_18001735C
0x1800172cc  test    ebx, ebx
0x1800172ce  jz      loc_180017354
0x1800172d4  sub     ebx, 1
0x1800172d7  jz      short loc_18001733E
0x1800172d9  sub     ebx, 1
0x1800172dc  jz      short loc_180017336
0x1800172de  cmp     ebx, 1
0x1800172e1  jz      short loc_18001732E
0x1800172e3  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800172ea  mov     [rsp+48h+var_18], 0DB6h
0x1800172f3  mov     [rsp+48h+var_28], rax
0x1800172f8  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800172ff  lea     rax, aUpdatereservem_28; "UpdateReserveManager::GetScenarioIdForR"...
0x180017306  mov     r8d, 800F0972h
0x18001730c  mov     [rsp+48h+var_20], rax
0x180017311  lea     rcx, [rsp+48h+var_28]
0x180017316  lea     rax, aScodeUnsignedL_0; "((SCODE) (((unsigned long)(1)<<31) | (("...
0x18001731d  mov     [rsp+48h+var_10], rax
0x180017322  call    RtlReportErrorOrigination
0x180017327  mov     eax, 800F0972h
0x18001732c  jmp     short loc_18001735C
0x18001732e  mov     dword ptr [rdi], 6
0x180017334  jmp     short loc_18001735A
0x180017336  mov     dword ptr [rdi], 2
0x18001733c  jmp     short loc_18001735A
0x18001733e  mov     rdx, rdi; enum IUpdateReserveManager::ScenarioId *
0x180017341  mov     rcx, rsi; this
0x180017344  call    ?GetActiveScenario@UpdateReserveManager@@AEAAJPEAW4ScenarioId@IUpdateReserveManager@@@Z; UpdateReserveManager::GetActiveScenario(IUpdateReserveManager::ScenarioId *)
0x180017349  xor     ecx, ecx
0x18001734b  test    eax, eax
0x18001734d  cmovs   ecx, eax
0x180017350  mov     eax, ecx
0x180017352  jmp     short loc_18001735C
0x180017354  mov     dword ptr [rdi], 0
0x18001735a  xor     eax, eax
0x18001735c  mov     rbx, [rsp+48h+arg_8]
0x180017361  mov     rsi, [rsp+48h+arg_18]
0x180017366  add     rsp, 40h
0x18001736a  pop     rdi
0x18001736b  retn
```
