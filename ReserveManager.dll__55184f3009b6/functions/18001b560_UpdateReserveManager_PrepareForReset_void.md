# UpdateReserveManager::PrepareForReset(void)

- ea: `0x18001b560`
- end: `0x18001b74e`
- name: `?PrepareForReset@UpdateReserveManager@@UEAAJXZ`
- size: `494`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x18000fafc`
- `0x1800133c4`
- `0x180015ad0`
- `0x18001a8f0`
- `0x18001b560`
- `0x18001fa18`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b5aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b619`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b64b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b67a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b6b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b6e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b716`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b734`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b5aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b619`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b64b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b67a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b6b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b6e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b716`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b734`

## string_xrefs

- `0x18001b5c0`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001b5cc`: `UpdateReserveManager::PrepareForReset`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::PrepareForReset(UpdateReserveManager *this)
{
  signed int v2; // eax
  unsigned int v3; // edi
  __int64 result; // rax
  const char *v5; // r9
  int v6; // edi
  int v7; // edi
  int v8; // edi
  int active; // edi
  int v10; // ebx
  HANDLE *v11; // [rsp+20h] [rbp-48h] BYREF
  char v12; // [rsp+28h] [rbp-40h]
  _QWORD v13[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v13[4] = -2;
  v11 = (HANDLE *)((char *)this + 1192);
  v12 = 0;
  v2 = AutoMutexLocker::Lock(&v11);
  v3 = v2;
  if ( v2 >= 0 )
  {
    try
    {
      if ( *((_BYTE *)this + 1176) )
      {
        v6 = UpdateReserveManager::EnsureNotInSafeMode(this);
        if ( v6 >= 0 )
        {
          v7 = UpdateReserveManager::ClearHardReserve(this);
          if ( v7 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(UpdateReserveManager *))(*(_QWORD *)this + 40LL))(this);
            if ( v8 >= 0 )
            {
              active = UpdateReserveManager::SetActiveScenario(this, 0);
              if ( active >= 0 )
              {
                v10 = (*(__int64 (__fastcall **)(UpdateReserveManager *, _QWORD))(*(_QWORD *)this + 48LL))(this, 0);
                if ( v10 >= 0 )
                {
                  if ( v12 && *v11 )
                    ReleaseMutex(*v11);
                  result = 0;
                }
                else
                {
                  if ( v12 && *v11 )
                    ReleaseMutex(*v11);
                  result = (unsigned int)v10;
                }
              }
              else
              {
                if ( v12 && *v11 )
                  ReleaseMutex(*v11);
                result = (unsigned int)active;
              }
            }
            else
            {
              if ( v12 && *v11 )
                ReleaseMutex(*v11);
              result = (unsigned int)v8;
            }
          }
          else
          {
            if ( v12 && *v11 )
              ReleaseMutex(*v11);
            result = (unsigned int)v7;
          }
        }
        else
        {
          if ( v12 && *v11 )
            ReleaseMutex(*v11);
          result = (unsigned int)v6;
        }
      }
      else
      {
        v13[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v13[1] = "UpdateReserveManager::PrepareForReset";
        v13[2] = 1228;
        v13[3] = "static_cast<DWORD>(50L)";
        RtlReportErrorOrigination(v13, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942450LL);
        if ( v12 && *v11 )
          ReleaseMutex(*v11);
        result = 2147942450LL;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x4DC,
                             (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                             v5);
    }
  }
  else
  {
    if ( v12 )
    {
      if ( *v11 )
        ReleaseMutex(*v11);
    }
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18001b560  mov     r11, rsp
0x18001b563  push    rdi
0x18001b564  sub     rsp, 60h
0x18001b568  mov     qword ptr [r11-10h], 0FFFFFFFFFFFFFFFEh
0x18001b570  mov     [r11+10h], rbx
0x18001b574  mov     rbx, rcx
0x18001b577  lea     rax, [rcx+4A8h]
0x18001b57e  mov     [r11-48h], rax
0x18001b582  mov     [rsp+68h+var_40], 0
0x18001b587  lea     rcx, [r11-48h]; this
0x18001b58b  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x18001b590  mov     edi, eax
0x18001b592  test    eax, eax
0x18001b594  jns     short loc_18001B5B7
0x18001b596  cmp     [rsp+68h+var_40], 0
0x18001b59b  jz      short loc_18001B5B0
0x18001b59d  mov     rcx, [rsp+68h+var_48]
0x18001b5a2  mov     rcx, [rcx]; hMutex
0x18001b5a5  test    rcx, rcx
0x18001b5a8  jz      short loc_18001B5B0
0x18001b5aa  call    cs:__imp_ReleaseMutex
0x18001b5b0  mov     eax, edi
0x18001b5b2  jmp     loc_18001B742
0x18001b5b7  cmp     byte ptr [rbx+498h], 0
0x18001b5be  jnz     short loc_18001B629
0x18001b5c0  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001b5c7  mov     [rsp+68h+var_30], rax
0x18001b5cc  lea     rax, aUpdatereservem_16; "UpdateReserveManager::PrepareForReset"
0x18001b5d3  mov     [rsp+68h+var_28], rax
0x18001b5d8  mov     [rsp+68h+var_20], 4CCh
0x18001b5e1  lea     rax, aStaticCastDwor; "static_cast<DWORD>(50L)"
0x18001b5e8  mov     [rsp+68h+var_18], rax
0x18001b5ed  mov     r8d, 80070032h
0x18001b5f3  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001b5fa  lea     rcx, [rsp+68h+var_30]
0x18001b5ff  call    RtlReportErrorOrigination
0x18001b604  nop
0x18001b605  cmp     [rsp+68h+var_40], 0
0x18001b60a  jz      short loc_18001B61F
0x18001b60c  mov     rax, [rsp+68h+var_48]
0x18001b611  mov     rcx, [rax]; hMutex
0x18001b614  test    rcx, rcx
0x18001b617  jz      short loc_18001B61F
0x18001b619  call    cs:__imp_ReleaseMutex
0x18001b61f  mov     eax, 80070032h
0x18001b624  jmp     loc_18001B742
0x18001b629  mov     rcx, rbx; this
0x18001b62c  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001b631  mov     edi, eax
0x18001b633  test    eax, eax
0x18001b635  jns     short loc_18001B658
0x18001b637  cmp     [rsp+68h+var_40], 0
0x18001b63c  jz      short loc_18001B651
0x18001b63e  mov     rcx, [rsp+68h+var_48]
0x18001b643  mov     rcx, [rcx]; hMutex
0x18001b646  test    rcx, rcx
0x18001b649  jz      short loc_18001B651
0x18001b64b  call    cs:__imp_ReleaseMutex
0x18001b651  mov     eax, edi
0x18001b653  jmp     loc_18001B742
0x18001b658  mov     rcx, rbx; this
0x18001b65b  call    ?ClearHardReserve@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::ClearHardReserve(void)
0x18001b660  mov     edi, eax
0x18001b662  test    eax, eax
0x18001b664  jns     short loc_18001B687
0x18001b666  cmp     [rsp+68h+var_40], 0
0x18001b66b  jz      short loc_18001B680
0x18001b66d  mov     rcx, [rsp+68h+var_48]
0x18001b672  mov     rcx, [rcx]; hMutex
0x18001b675  test    rcx, rcx
0x18001b678  jz      short loc_18001B680
0x18001b67a  call    cs:__imp_ReleaseMutex
0x18001b680  mov     eax, edi
0x18001b682  jmp     loc_18001B742
0x18001b687  mov     rax, [rbx]
0x18001b68a  mov     rcx, rbx
0x18001b68d  mov     rax, [rax+28h]
0x18001b691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b696  mov     edi, eax
0x18001b698  test    eax, eax
0x18001b69a  jns     short loc_18001B6BD
0x18001b69c  cmp     [rsp+68h+var_40], 0
0x18001b6a1  jz      short loc_18001B6B6
0x18001b6a3  mov     rcx, [rsp+68h+var_48]
0x18001b6a8  mov     rcx, [rcx]; hMutex
0x18001b6ab  test    rcx, rcx
0x18001b6ae  jz      short loc_18001B6B6
0x18001b6b0  call    cs:__imp_ReleaseMutex
0x18001b6b6  mov     eax, edi
0x18001b6b8  jmp     loc_18001B742
0x18001b6bd  xor     edx, edx
0x18001b6bf  mov     rcx, rbx
0x18001b6c2  call    ?SetActiveScenario@UpdateReserveManager@@AEAAJW4ScenarioId@IUpdateReserveManager@@@Z; UpdateReserveManager::SetActiveScenario(IUpdateReserveManager::ScenarioId)
0x18001b6c7  mov     edi, eax
0x18001b6c9  test    eax, eax
0x18001b6cb  jns     short loc_18001B6EB
0x18001b6cd  cmp     [rsp+68h+var_40], 0
0x18001b6d2  jz      short loc_18001B6E7
0x18001b6d4  mov     rcx, [rsp+68h+var_48]
0x18001b6d9  mov     rcx, [rcx]; hMutex
0x18001b6dc  test    rcx, rcx
0x18001b6df  jz      short loc_18001B6E7
0x18001b6e1  call    cs:__imp_ReleaseMutex
0x18001b6e7  mov     eax, edi
0x18001b6e9  jmp     short loc_18001B742
0x18001b6eb  mov     rax, [rbx]
0x18001b6ee  xor     edx, edx
0x18001b6f0  mov     rcx, rbx
0x18001b6f3  mov     rax, [rax+30h]
0x18001b6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6fc  mov     ebx, eax
0x18001b6fe  test    eax, eax
0x18001b700  jns     short loc_18001B720
0x18001b702  cmp     [rsp+68h+var_40], 0
0x18001b707  jz      short loc_18001B71C
0x18001b709  mov     rcx, [rsp+68h+var_48]
0x18001b70e  mov     rcx, [rcx]; hMutex
0x18001b711  test    rcx, rcx
0x18001b714  jz      short loc_18001B71C
0x18001b716  call    cs:__imp_ReleaseMutex
0x18001b71c  mov     eax, ebx
0x18001b71e  jmp     short loc_18001B742
0x18001b720  cmp     [rsp+68h+var_40], 0
0x18001b725  jz      short loc_18001B73A
0x18001b727  mov     rax, [rsp+68h+var_48]
0x18001b72c  mov     rcx, [rax]; hMutex
0x18001b72f  test    rcx, rcx
0x18001b732  jz      short loc_18001B73A
0x18001b734  call    cs:__imp_ReleaseMutex
0x18001b73a  xor     eax, eax
0x18001b73c  jmp     short loc_18001B742
0x18001b73e  mov     eax, [rsp+68h+var_38]
0x18001b742  mov     rbx, [rsp+68h+arg_8]
0x18001b747  add     rsp, 60h
0x18001b74b  pop     rdi
0x18001b74c  retn
```
