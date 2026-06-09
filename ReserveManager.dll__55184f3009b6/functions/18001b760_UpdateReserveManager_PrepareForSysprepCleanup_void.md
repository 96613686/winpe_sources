# UpdateReserveManager::PrepareForSysprepCleanup(void)

- ea: `0x18001b760`
- end: `0x18001b8e7`
- name: `?PrepareForSysprepCleanup@UpdateReserveManager@@UEAAJXZ`
- size: `391`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000fafc`
- `0x18001328c`
- `0x180015ad0`
- `0x18001a8f0`
- `0x18001b760`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b7aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b819`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b84b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b883`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b8af`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b8cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b7aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b819`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b84b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b883`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b8af`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b8cd`

## string_xrefs

- `0x18001b7c0`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001b7cc`: `UpdateReserveManager::PrepareForSysprepCleanup`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::PrepareForSysprepCleanup(UpdateReserveManager *this)
{
  signed int v2; // eax
  unsigned int v3; // edi
  __int64 result; // rax
  const char *v5; // r9
  int v6; // edi
  int v7; // edi
  int v8; // ebx
  HANDLE *v9; // [rsp+20h] [rbp-48h] BYREF
  char v10; // [rsp+28h] [rbp-40h]
  _QWORD v11[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v11[4] = -2;
  v9 = (HANDLE *)((char *)this + 1192);
  v10 = 0;
  v2 = AutoMutexLocker::Lock(&v9);
  v3 = v2;
  if ( v2 >= 0 )
  {
    try
    {
      if ( *((_BYTE *)this + 1176) )
      {
        v11[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v11[1] = "UpdateReserveManager::PrepareForSysprepCleanup";
        v11[2] = 1468;
        v11[3] = "static_cast<DWORD>(50L)";
        RtlReportErrorOrigination(v11, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942450LL);
        if ( v10 && *v9 )
          ReleaseMutex(*v9);
        result = 2147942450LL;
      }
      else
      {
        v6 = UpdateReserveManager::EnsureNotInSafeMode(this);
        if ( v6 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(UpdateReserveManager *, _QWORD))(*(_QWORD *)this + 112LL))(this, 0);
          if ( v7 >= 0 )
          {
            v8 = UpdateReserveManager::CleanReserveManagerState((HKEY *)this);
            if ( v8 >= 0 )
            {
              if ( v10 && *v9 )
                ReleaseMutex(*v9);
              result = 0;
            }
            else
            {
              if ( v10 && *v9 )
                ReleaseMutex(*v9);
              result = (unsigned int)v8;
            }
          }
          else
          {
            if ( v10 && *v9 )
              ReleaseMutex(*v9);
            result = (unsigned int)v7;
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
                             (void *)0x5C7,
                             (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
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
0x18001b760  mov     r11, rsp
0x18001b763  push    rdi
0x18001b764  sub     rsp, 60h
0x18001b768  mov     qword ptr [r11-10h], 0FFFFFFFFFFFFFFFEh
0x18001b770  mov     [r11+10h], rbx
0x18001b774  mov     rbx, rcx
0x18001b777  lea     rax, [rcx+4A8h]
0x18001b77e  mov     [r11-48h], rax
0x18001b782  mov     [rsp+68h+var_40], 0
0x18001b787  lea     rcx, [r11-48h]; this
0x18001b78b  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x18001b790  mov     edi, eax
0x18001b792  test    eax, eax
0x18001b794  jns     short loc_18001B7B7
0x18001b796  cmp     [rsp+68h+var_40], 0
0x18001b79b  jz      short loc_18001B7B0
0x18001b79d  mov     rcx, [rsp+68h+var_48]
0x18001b7a2  mov     rcx, [rcx]; hMutex
0x18001b7a5  test    rcx, rcx
0x18001b7a8  jz      short loc_18001B7B0
0x18001b7aa  call    cs:__imp_ReleaseMutex
0x18001b7b0  mov     eax, edi
0x18001b7b2  jmp     loc_18001B8DB
0x18001b7b7  cmp     byte ptr [rbx+498h], 0
0x18001b7be  jz      short loc_18001B829
0x18001b7c0  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001b7c7  mov     [rsp+68h+var_30], rax
0x18001b7cc  lea     rax, aUpdatereservem_42; "UpdateReserveManager::PrepareForSysprep"...
0x18001b7d3  mov     [rsp+68h+var_28], rax
0x18001b7d8  mov     [rsp+68h+var_20], 5BCh
0x18001b7e1  lea     rax, aStaticCastDwor; "static_cast<DWORD>(50L)"
0x18001b7e8  mov     [rsp+68h+var_18], rax
0x18001b7ed  mov     r8d, 80070032h
0x18001b7f3  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001b7fa  lea     rcx, [rsp+68h+var_30]
0x18001b7ff  call    RtlReportErrorOrigination
0x18001b804  nop
0x18001b805  cmp     [rsp+68h+var_40], 0
0x18001b80a  jz      short loc_18001B81F
0x18001b80c  mov     rax, [rsp+68h+var_48]
0x18001b811  mov     rcx, [rax]; hMutex
0x18001b814  test    rcx, rcx
0x18001b817  jz      short loc_18001B81F
0x18001b819  call    cs:__imp_ReleaseMutex
0x18001b81f  mov     eax, 80070032h
0x18001b824  jmp     loc_18001B8DB
0x18001b829  mov     rcx, rbx; this
0x18001b82c  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001b831  mov     edi, eax
0x18001b833  test    eax, eax
0x18001b835  jns     short loc_18001B858
0x18001b837  cmp     [rsp+68h+var_40], 0
0x18001b83c  jz      short loc_18001B851
0x18001b83e  mov     rcx, [rsp+68h+var_48]
0x18001b843  mov     rcx, [rcx]; hMutex
0x18001b846  test    rcx, rcx
0x18001b849  jz      short loc_18001B851
0x18001b84b  call    cs:__imp_ReleaseMutex
0x18001b851  mov     eax, edi
0x18001b853  jmp     loc_18001B8DB
0x18001b858  mov     rax, [rbx]
0x18001b85b  xor     edx, edx
0x18001b85d  mov     rcx, rbx
0x18001b860  mov     rax, [rax+70h]
0x18001b864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b869  mov     edi, eax
0x18001b86b  test    eax, eax
0x18001b86d  jns     short loc_18001B88D
0x18001b86f  cmp     [rsp+68h+var_40], 0
0x18001b874  jz      short loc_18001B889
0x18001b876  mov     rcx, [rsp+68h+var_48]
0x18001b87b  mov     rcx, [rcx]; hMutex
0x18001b87e  test    rcx, rcx
0x18001b881  jz      short loc_18001B889
0x18001b883  call    cs:__imp_ReleaseMutex
0x18001b889  mov     eax, edi
0x18001b88b  jmp     short loc_18001B8DB
0x18001b88d  mov     rcx, rbx; this
0x18001b890  call    ?CleanReserveManagerState@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::CleanReserveManagerState(void)
0x18001b895  mov     ebx, eax
0x18001b897  test    eax, eax
0x18001b899  jns     short loc_18001B8B9
0x18001b89b  cmp     [rsp+68h+var_40], 0
0x18001b8a0  jz      short loc_18001B8B5
0x18001b8a2  mov     rcx, [rsp+68h+var_48]
0x18001b8a7  mov     rcx, [rcx]; hMutex
0x18001b8aa  test    rcx, rcx
0x18001b8ad  jz      short loc_18001B8B5
0x18001b8af  call    cs:__imp_ReleaseMutex
0x18001b8b5  mov     eax, ebx
0x18001b8b7  jmp     short loc_18001B8DB
0x18001b8b9  cmp     [rsp+68h+var_40], 0
0x18001b8be  jz      short loc_18001B8D3
0x18001b8c0  mov     rax, [rsp+68h+var_48]
0x18001b8c5  mov     rcx, [rax]; hMutex
0x18001b8c8  test    rcx, rcx
0x18001b8cb  jz      short loc_18001B8D3
0x18001b8cd  call    cs:__imp_ReleaseMutex
0x18001b8d3  xor     eax, eax
0x18001b8d5  jmp     short loc_18001B8DB
0x18001b8d7  mov     eax, [rsp+68h+var_38]
0x18001b8db  mov     rbx, [rsp+68h+arg_8]
0x18001b8e0  add     rsp, 60h
0x18001b8e4  pop     rdi
0x18001b8e5  retn
```
