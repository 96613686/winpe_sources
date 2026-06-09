# UpdateReserveManager::PrepareForAuditMode(void)

- ea: `0x18001b3d0`
- end: `0x18001b55a`
- name: `?PrepareForAuditMode@UpdateReserveManager@@UEAAJXZ`
- size: `394`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000fafc`
- `0x18001328c`
- `0x180015ad0`
- `0x18001a8f0`
- `0x18001b3d0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b41a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b489`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b4bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b4f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b522`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b540`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b41a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b489`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b4bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b4f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b522`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b540`

## string_xrefs

- `0x18001b430`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001b43c`: `UpdateReserveManager::PrepareForAuditMode`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::PrepareForAuditMode(UpdateReserveManager *this)
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
        v11[1] = "UpdateReserveManager::PrepareForAuditMode";
        v11[2] = 1519;
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
          v7 = (*(__int64 (__fastcall **)(UpdateReserveManager *, __int64))(*(_QWORD *)this + 48LL))(this, 1);
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
                             (void *)0x5FA,
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
0x18001b3d0  mov     r11, rsp
0x18001b3d3  push    rdi
0x18001b3d4  sub     rsp, 60h
0x18001b3d8  mov     qword ptr [r11-10h], 0FFFFFFFFFFFFFFFEh
0x18001b3e0  mov     [r11+10h], rbx
0x18001b3e4  mov     rbx, rcx
0x18001b3e7  lea     rax, [rcx+4A8h]
0x18001b3ee  mov     [r11-48h], rax
0x18001b3f2  mov     [rsp+68h+var_40], 0
0x18001b3f7  lea     rcx, [r11-48h]; this
0x18001b3fb  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x18001b400  mov     edi, eax
0x18001b402  test    eax, eax
0x18001b404  jns     short loc_18001B427
0x18001b406  cmp     [rsp+68h+var_40], 0
0x18001b40b  jz      short loc_18001B420
0x18001b40d  mov     rcx, [rsp+68h+var_48]
0x18001b412  mov     rcx, [rcx]; hMutex
0x18001b415  test    rcx, rcx
0x18001b418  jz      short loc_18001B420
0x18001b41a  call    cs:__imp_ReleaseMutex
0x18001b420  mov     eax, edi
0x18001b422  jmp     loc_18001B54E
0x18001b427  cmp     byte ptr [rbx+498h], 0
0x18001b42e  jz      short loc_18001B499
0x18001b430  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001b437  mov     [rsp+68h+var_30], rax
0x18001b43c  lea     rax, aUpdatereservem_21; "UpdateReserveManager::PrepareForAuditMo"...
0x18001b443  mov     [rsp+68h+var_28], rax
0x18001b448  mov     [rsp+68h+var_20], 5EFh
0x18001b451  lea     rax, aStaticCastDwor; "static_cast<DWORD>(50L)"
0x18001b458  mov     [rsp+68h+var_18], rax
0x18001b45d  mov     r8d, 80070032h
0x18001b463  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001b46a  lea     rcx, [rsp+68h+var_30]
0x18001b46f  call    RtlReportErrorOrigination
0x18001b474  nop
0x18001b475  cmp     [rsp+68h+var_40], 0
0x18001b47a  jz      short loc_18001B48F
0x18001b47c  mov     rax, [rsp+68h+var_48]
0x18001b481  mov     rcx, [rax]; hMutex
0x18001b484  test    rcx, rcx
0x18001b487  jz      short loc_18001B48F
0x18001b489  call    cs:__imp_ReleaseMutex
0x18001b48f  mov     eax, 80070032h
0x18001b494  jmp     loc_18001B54E
0x18001b499  mov     rcx, rbx; this
0x18001b49c  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001b4a1  mov     edi, eax
0x18001b4a3  test    eax, eax
0x18001b4a5  jns     short loc_18001B4C8
0x18001b4a7  cmp     [rsp+68h+var_40], 0
0x18001b4ac  jz      short loc_18001B4C1
0x18001b4ae  mov     rcx, [rsp+68h+var_48]
0x18001b4b3  mov     rcx, [rcx]; hMutex
0x18001b4b6  test    rcx, rcx
0x18001b4b9  jz      short loc_18001B4C1
0x18001b4bb  call    cs:__imp_ReleaseMutex
0x18001b4c1  mov     eax, edi
0x18001b4c3  jmp     loc_18001B54E
0x18001b4c8  mov     rax, [rbx]
0x18001b4cb  mov     edx, 1
0x18001b4d0  mov     rcx, rbx
0x18001b4d3  mov     rax, [rax+30h]
0x18001b4d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4dc  mov     edi, eax
0x18001b4de  test    eax, eax
0x18001b4e0  jns     short loc_18001B500
0x18001b4e2  cmp     [rsp+68h+var_40], 0
0x18001b4e7  jz      short loc_18001B4FC
0x18001b4e9  mov     rcx, [rsp+68h+var_48]
0x18001b4ee  mov     rcx, [rcx]; hMutex
0x18001b4f1  test    rcx, rcx
0x18001b4f4  jz      short loc_18001B4FC
0x18001b4f6  call    cs:__imp_ReleaseMutex
0x18001b4fc  mov     eax, edi
0x18001b4fe  jmp     short loc_18001B54E
0x18001b500  mov     rcx, rbx; this
0x18001b503  call    ?CleanReserveManagerState@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::CleanReserveManagerState(void)
0x18001b508  mov     ebx, eax
0x18001b50a  test    eax, eax
0x18001b50c  jns     short loc_18001B52C
0x18001b50e  cmp     [rsp+68h+var_40], 0
0x18001b513  jz      short loc_18001B528
0x18001b515  mov     rcx, [rsp+68h+var_48]
0x18001b51a  mov     rcx, [rcx]; hMutex
0x18001b51d  test    rcx, rcx
0x18001b520  jz      short loc_18001B528
0x18001b522  call    cs:__imp_ReleaseMutex
0x18001b528  mov     eax, ebx
0x18001b52a  jmp     short loc_18001B54E
0x18001b52c  cmp     [rsp+68h+var_40], 0
0x18001b531  jz      short loc_18001B546
0x18001b533  mov     rax, [rsp+68h+var_48]
0x18001b538  mov     rcx, [rax]; hMutex
0x18001b53b  test    rcx, rcx
0x18001b53e  jz      short loc_18001B546
0x18001b540  call    cs:__imp_ReleaseMutex
0x18001b546  xor     eax, eax
0x18001b548  jmp     short loc_18001B54E
0x18001b54a  mov     eax, [rsp+68h+var_38]
0x18001b54e  mov     rbx, [rsp+68h+arg_8]
0x18001b553  add     rsp, 60h
0x18001b557  pop     rdi
0x18001b558  retn
```
