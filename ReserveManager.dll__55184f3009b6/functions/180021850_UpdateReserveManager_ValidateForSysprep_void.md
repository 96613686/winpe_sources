# UpdateReserveManager::ValidateForSysprep(void)

- ea: `0x180021850`
- end: `0x180021a1f`
- name: `?ValidateForSysprep@UpdateReserveManager@@UEAAJXZ`
- size: `463`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x18000fafc`
- `0x180015ad0`
- `0x180015e20`
- `0x18001a8f0`
- `0x180021850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002189a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021911`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021943`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021977`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800219e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021a05`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002189a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021911`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021943`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021977`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800219e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021a05`

## string_xrefs

- `0x1800218b8`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18002198b`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800218c4`: `UpdateReserveManager::ValidateForSysprep`
- `0x180021997`: `UpdateReserveManager::ValidateForSysprep`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::ValidateForSysprep(UpdateReserveManager *this)
{
  signed int v2; // eax
  unsigned int v3; // edi
  __int64 result; // rax
  const char *v5; // r9
  int v6; // edi
  int ActiveScenario; // ebx
  int v8; // [rsp+20h] [rbp-48h] BYREF
  HANDLE *v9; // [rsp+28h] [rbp-40h] BYREF
  char v10; // [rsp+30h] [rbp-38h]
  const char *v11; // [rsp+38h] [rbp-30h] BYREF
  const char *v12; // [rsp+40h] [rbp-28h]
  __int64 v13; // [rsp+48h] [rbp-20h]
  const char *v14; // [rsp+50h] [rbp-18h]
  __int64 v15; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v15 = -2;
  v9 = (HANDLE *)((char *)this + 1192);
  v10 = 0;
  v2 = AutoMutexLocker::Lock(&v9);
  v3 = v2;
  if ( v2 >= 0 )
  {
    try
    {
      v8 = 0;
      if ( *((_BYTE *)this + 1176) )
      {
        v11 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v12 = "UpdateReserveManager::ValidateForSysprep";
        v13 = 1493;
        v14 = "static_cast<DWORD>(50L)";
        RtlReportErrorOrigination(&v11, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942450LL);
        if ( v10 && *v9 )
          ReleaseMutex(*v9);
        result = 2147942450LL;
      }
      else
      {
        v6 = UpdateReserveManager::EnsureNotInSafeMode(this);
        if ( v6 >= 0 )
        {
          ActiveScenario = UpdateReserveManager::GetActiveScenario(
                             (HKEY *)this,
                             (enum IUpdateReserveManager::ScenarioId *)&v8);
          if ( ActiveScenario >= 0 )
          {
            if ( v8 )
            {
              v11 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
              v12 = "UpdateReserveManager::ValidateForSysprep";
              v13 = 1502;
              v14 = "((SCODE) (((unsigned long)(1)<<31) | ((unsigned long)(15)<<16) | ((unsigned long)(0x975))) )";
              RtlReportErrorOrigination(&v11, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2148469109LL);
              if ( v10 && *v9 )
                ReleaseMutex(*v9);
              result = 2148469109LL;
            }
            else
            {
              if ( v10 && *v9 )
                ReleaseMutex(*v9);
              result = 0;
            }
          }
          else
          {
            if ( v10 && *v9 )
              ReleaseMutex(*v9);
            result = (unsigned int)ActiveScenario;
          }
        }
        else
        {
          if ( v10 && *v9 )
            ReleaseMutex(*v9);
          result = (unsigned int)v6;
        }
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x5E3,
                             (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                             v5);
    }
  }
  else
  {
    if ( v10 )
    {
      if ( *v9 )
        ReleaseMutex(*v9);
    }
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180021850  mov     r11, rsp
0x180021853  push    rdi
0x180021854  sub     rsp, 60h
0x180021858  mov     qword ptr [r11-10h], 0FFFFFFFFFFFFFFFEh
0x180021860  mov     [r11+10h], rbx
0x180021864  mov     rbx, rcx
0x180021867  lea     rax, [rcx+4A8h]
0x18002186e  mov     [r11-40h], rax
0x180021872  mov     [rsp+68h+var_38], 0
0x180021877  lea     rcx, [r11-40h]; this
0x18002187b  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x180021880  mov     edi, eax
0x180021882  test    eax, eax
0x180021884  jns     short loc_1800218A7
0x180021886  cmp     [rsp+68h+var_38], 0
0x18002188b  jz      short loc_1800218A0
0x18002188d  mov     rcx, [rsp+68h+var_40]
0x180021892  mov     rcx, [rcx]; hMutex
0x180021895  test    rcx, rcx
0x180021898  jz      short loc_1800218A0
0x18002189a  call    cs:__imp_ReleaseMutex
0x1800218a0  mov     eax, edi
0x1800218a2  jmp     loc_180021A13
0x1800218a7  mov     [rsp+68h+var_48], 0
0x1800218af  cmp     byte ptr [rbx+498h], 0
0x1800218b6  jz      short loc_180021921
0x1800218b8  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800218bf  mov     [rsp+68h+var_30], rax
0x1800218c4  lea     rax, aUpdatereservem; "UpdateReserveManager::ValidateForSyspre"...
0x1800218cb  mov     [rsp+68h+var_28], rax
0x1800218d0  mov     [rsp+68h+var_20], 5D5h
0x1800218d9  lea     rax, aStaticCastDwor; "static_cast<DWORD>(50L)"
0x1800218e0  mov     [rsp+68h+var_18], rax
0x1800218e5  mov     r8d, 80070032h
0x1800218eb  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800218f2  lea     rcx, [rsp+68h+var_30]
0x1800218f7  call    RtlReportErrorOrigination
0x1800218fc  nop
0x1800218fd  cmp     [rsp+68h+var_38], 0
0x180021902  jz      short loc_180021917
0x180021904  mov     rax, [rsp+68h+var_40]
0x180021909  mov     rcx, [rax]; hMutex
0x18002190c  test    rcx, rcx
0x18002190f  jz      short loc_180021917
0x180021911  call    cs:__imp_ReleaseMutex
0x180021917  mov     eax, 80070032h
0x18002191c  jmp     loc_180021A13
0x180021921  mov     rcx, rbx; this
0x180021924  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x180021929  mov     edi, eax
0x18002192b  test    eax, eax
0x18002192d  jns     short loc_180021950
0x18002192f  cmp     [rsp+68h+var_38], 0
0x180021934  jz      short loc_180021949
0x180021936  mov     rcx, [rsp+68h+var_40]
0x18002193b  mov     rcx, [rcx]; hMutex
0x18002193e  test    rcx, rcx
0x180021941  jz      short loc_180021949
0x180021943  call    cs:__imp_ReleaseMutex
0x180021949  mov     eax, edi
0x18002194b  jmp     loc_180021A13
0x180021950  lea     rdx, [rsp+68h+var_48]; enum IUpdateReserveManager::ScenarioId *
0x180021955  mov     rcx, rbx; this
0x180021958  call    ?GetActiveScenario@UpdateReserveManager@@AEAAJPEAW4ScenarioId@IUpdateReserveManager@@@Z; UpdateReserveManager::GetActiveScenario(IUpdateReserveManager::ScenarioId *)
0x18002195d  mov     ebx, eax
0x18002195f  test    eax, eax
0x180021961  jns     short loc_180021984
0x180021963  cmp     [rsp+68h+var_38], 0
0x180021968  jz      short loc_18002197D
0x18002196a  mov     rcx, [rsp+68h+var_40]
0x18002196f  mov     rcx, [rcx]; hMutex
0x180021972  test    rcx, rcx
0x180021975  jz      short loc_18002197D
0x180021977  call    cs:__imp_ReleaseMutex
0x18002197d  mov     eax, ebx
0x18002197f  jmp     loc_180021A13
0x180021984  cmp     [rsp+68h+var_48], 0
0x180021989  jz      short loc_1800219F1
0x18002198b  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180021992  mov     [rsp+68h+var_30], rax
0x180021997  lea     rax, aUpdatereservem; "UpdateReserveManager::ValidateForSyspre"...
0x18002199e  mov     [rsp+68h+var_28], rax
0x1800219a3  mov     [rsp+68h+var_20], 5DEh
0x1800219ac  lea     rax, aScodeUnsignedL_5; "((SCODE) (((unsigned long)(1)<<31) | (("...
0x1800219b3  mov     [rsp+68h+var_18], rax
0x1800219b8  mov     r8d, 800F0975h
0x1800219be  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800219c5  lea     rcx, [rsp+68h+var_30]
0x1800219ca  call    RtlReportErrorOrigination
0x1800219cf  nop
0x1800219d0  cmp     [rsp+68h+var_38], 0
0x1800219d5  jz      short loc_1800219EA
0x1800219d7  mov     rax, [rsp+68h+var_40]
0x1800219dc  mov     rcx, [rax]; hMutex
0x1800219df  test    rcx, rcx
0x1800219e2  jz      short loc_1800219EA
0x1800219e4  call    cs:__imp_ReleaseMutex
0x1800219ea  mov     eax, 800F0975h
0x1800219ef  jmp     short loc_180021A13
0x1800219f1  cmp     [rsp+68h+var_38], 0
0x1800219f6  jz      short loc_180021A0B
0x1800219f8  mov     rax, [rsp+68h+var_40]
0x1800219fd  mov     rcx, [rax]; hMutex
0x180021a00  test    rcx, rcx
0x180021a03  jz      short loc_180021A0B
0x180021a05  call    cs:__imp_ReleaseMutex
0x180021a0b  xor     eax, eax
0x180021a0d  jmp     short loc_180021A13
0x180021a0f  mov     eax, [rsp+68h+var_48]
0x180021a13  mov     rbx, [rsp+68h+arg_8]
0x180021a18  add     rsp, 60h
0x180021a1c  pop     rdi
0x180021a1d  retn
```
