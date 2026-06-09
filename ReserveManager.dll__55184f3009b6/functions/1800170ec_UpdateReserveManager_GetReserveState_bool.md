# UpdateReserveManager::GetReserveState(bool *)

- ea: `0x1800170ec`
- end: `0x18001729f`
- name: `?GetReserveState@UpdateReserveManager@@QEAAJPEA_N@Z`
- size: `435`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this, bool *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18000c820`
- `0x180014960`
- `0x180015240`

## callees

- `0x18000fafc`
- `0x180016cac`
- `0x1800170ec`
- `0x18001a8f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001713d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800171ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001721a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017256`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001727e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001713d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800171ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001721a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017256`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001727e`

## string_xrefs

- `0x180017153`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800171c1`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001715f`: `UpdateReserveManager::GetReserveState`
- `0x1800171cd`: `UpdateReserveManager::GetReserveState`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::GetReserveState(UpdateReserveManager *this, bool *a2)
{
  int v4; // eax
  unsigned int v5; // esi
  __int64 result; // rax
  const char *v7; // r9
  int PassedPolicyValue; // ebx
  unsigned int v9; // [rsp+20h] [rbp-48h] BYREF
  HANDLE *v10; // [rsp+28h] [rbp-40h] BYREF
  char v11; // [rsp+30h] [rbp-38h]
  const char *v12; // [rsp+38h] [rbp-30h] BYREF
  const char *v13; // [rsp+40h] [rbp-28h]
  __int64 v14; // [rsp+48h] [rbp-20h]
  const char *v15; // [rsp+50h] [rbp-18h]
  __int64 v16; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v16 = -2;
  v10 = (HANDLE *)((char *)this + 1192);
  v11 = 0;
  v4 = AutoMutexLocker::Lock((AutoMutexLocker *)&v10, (unsigned int)a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    try
    {
      if ( *((_BYTE *)this + 1176) )
      {
        v12 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v13 = "UpdateReserveManager::GetReserveState";
        v14 = 1676;
        v15 = "static_cast<DWORD>(50L)";
        RtlReportErrorOrigination(&v12, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942450LL);
        if ( v11 && *v10 )
          ReleaseMutex(*v10);
        result = 2147942450LL;
      }
      else if ( a2 )
      {
        v9 = 0;
        PassedPolicyValue = UpdateReserveManager::GetPassedPolicyValue(this, &v9);
        if ( PassedPolicyValue >= 0 )
        {
          *a2 = v9 != 0;
          if ( v11 && *v10 )
            ReleaseMutex(*v10);
          result = 0;
        }
        else
        {
          if ( v11 && *v10 )
            ReleaseMutex(*v10);
          result = (unsigned int)PassedPolicyValue;
        }
      }
      else
      {
        v12 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v13 = "UpdateReserveManager::GetReserveState";
        v14 = 1681;
        v15 = "((HRESULT)0x80070057L)";
        RtlReportErrorOrigination(&v12, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942487LL);
        if ( v11 && *v10 )
          ReleaseMutex(*v10);
        result = 2147942487LL;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x6A2,
                             (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                             v7);
    }
  }
  else
  {
    if ( v11 )
    {
      if ( *v10 )
        ReleaseMutex(*v10);
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800170ec  mov     r11, rsp
0x1800170ef  push    rdi
0x1800170f0  sub     rsp, 60h
0x1800170f4  mov     qword ptr [r11-10h], 0FFFFFFFFFFFFFFFEh
0x1800170fc  mov     [r11+18h], rbx
0x180017100  mov     [r11+20h], rsi
0x180017104  mov     rdi, rdx
0x180017107  mov     rbx, rcx
0x18001710a  lea     rax, [rcx+4A8h]
0x180017111  mov     [r11-40h], rax
0x180017115  mov     [rsp+68h+var_38], 0
0x18001711a  lea     rcx, [r11-40h]; this
0x18001711e  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x180017123  mov     esi, eax
0x180017125  test    eax, eax
0x180017127  jns     short loc_18001714A
0x180017129  cmp     [rsp+68h+var_38], 0
0x18001712e  jz      short loc_180017143
0x180017130  mov     rcx, [rsp+68h+var_40]
0x180017135  mov     rcx, [rcx]; hMutex
0x180017138  test    rcx, rcx
0x18001713b  jz      short loc_180017143
0x18001713d  call    cs:__imp_ReleaseMutex
0x180017143  mov     eax, esi
0x180017145  jmp     loc_18001728C
0x18001714a  cmp     byte ptr [rbx+498h], 0
0x180017151  jz      short loc_1800171BC
0x180017153  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001715a  mov     [rsp+68h+var_30], rax
0x18001715f  lea     rax, aUpdatereservem_2; "UpdateReserveManager::GetReserveState"
0x180017166  mov     [rsp+68h+var_28], rax
0x18001716b  mov     [rsp+68h+var_20], 68Ch
0x180017174  lea     rax, aStaticCastDwor; "static_cast<DWORD>(50L)"
0x18001717b  mov     [rsp+68h+var_18], rax
0x180017180  mov     r8d, 80070032h
0x180017186  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001718d  lea     rcx, [rsp+68h+var_30]
0x180017192  call    RtlReportErrorOrigination
0x180017197  nop
0x180017198  cmp     [rsp+68h+var_38], 0
0x18001719d  jz      short loc_1800171B2
0x18001719f  mov     rax, [rsp+68h+var_40]
0x1800171a4  mov     rcx, [rax]; hMutex
0x1800171a7  test    rcx, rcx
0x1800171aa  jz      short loc_1800171B2
0x1800171ac  call    cs:__imp_ReleaseMutex
0x1800171b2  mov     eax, 80070032h
0x1800171b7  jmp     loc_18001728C
0x1800171bc  test    rdi, rdi
0x1800171bf  jnz     short loc_180017227
0x1800171c1  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800171c8  mov     [rsp+68h+var_30], rax
0x1800171cd  lea     rax, aUpdatereservem_2; "UpdateReserveManager::GetReserveState"
0x1800171d4  mov     [rsp+68h+var_28], rax
0x1800171d9  mov     [rsp+68h+var_20], 691h
0x1800171e2  lea     rax, aHresult0x80070; "((HRESULT)0x80070057L)"
0x1800171e9  mov     [rsp+68h+var_18], rax
0x1800171ee  mov     r8d, 80070057h
0x1800171f4  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800171fb  lea     rcx, [rsp+68h+var_30]
0x180017200  call    RtlReportErrorOrigination
0x180017205  nop
0x180017206  cmp     [rsp+68h+var_38], dil
0x18001720b  jz      short loc_180017220
0x18001720d  mov     rax, [rsp+68h+var_40]
0x180017212  mov     rcx, [rax]; hMutex
0x180017215  test    rcx, rcx
0x180017218  jz      short loc_180017220
0x18001721a  call    cs:__imp_ReleaseMutex
0x180017220  mov     eax, 80070057h
0x180017225  jmp     short loc_18001728C
0x180017227  mov     [rsp+68h+var_48], 0
0x18001722f  lea     rdx, [rsp+68h+var_48]; unsigned int *
0x180017234  mov     rcx, rbx; this
0x180017237  call    ?GetPassedPolicyValue@UpdateReserveManager@@AEAAJPEAK@Z; UpdateReserveManager::GetPassedPolicyValue(ulong *)
0x18001723c  mov     ebx, eax
0x18001723e  test    eax, eax
0x180017240  jns     short loc_180017260
0x180017242  cmp     [rsp+68h+var_38], 0
0x180017247  jz      short loc_18001725C
0x180017249  mov     rcx, [rsp+68h+var_40]
0x18001724e  mov     rcx, [rcx]; hMutex
0x180017251  test    rcx, rcx
0x180017254  jz      short loc_18001725C
0x180017256  call    cs:__imp_ReleaseMutex
0x18001725c  mov     eax, ebx
0x18001725e  jmp     short loc_18001728C
0x180017260  cmp     [rsp+68h+var_48], 0
0x180017265  setnz   al
0x180017268  mov     [rdi], al
0x18001726a  cmp     [rsp+68h+var_38], 0
0x18001726f  jz      short loc_180017284
0x180017271  mov     rax, [rsp+68h+var_40]
0x180017276  mov     rcx, [rax]; hMutex
0x180017279  test    rcx, rcx
0x18001727c  jz      short loc_180017284
0x18001727e  call    cs:__imp_ReleaseMutex
0x180017284  xor     eax, eax
0x180017286  jmp     short loc_18001728C
0x180017288  mov     eax, [rsp+68h+var_48]
0x18001728c  lea     r11, [rsp+68h+var_8]
0x180017291  mov     rbx, [r11+20h]
0x180017295  mov     rsi, [r11+28h]
0x180017299  mov     rsp, r11
0x18001729c  pop     rdi
0x18001729d  retn
```
