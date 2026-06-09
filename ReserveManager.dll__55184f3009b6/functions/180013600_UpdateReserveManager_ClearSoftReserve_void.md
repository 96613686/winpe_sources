# UpdateReserveManager::ClearSoftReserve(void)

- ea: `0x180013600`
- end: `0x180013769`
- name: `?ClearSoftReserve@UpdateReserveManager@@UEAAJXZ`
- size: `361`
- prototype: `__int64 __fastcall(HKEY *this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800133f8`
- `0x180013600`
- `0x180015034`
- `0x180015ad0`
- `0x18001a8f0`
- `0x180027414`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001364a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013679`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800136c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013700`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013731`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001374f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001364a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013679`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800136c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013700`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013731`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001374f`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::ClearSoftReserve(HKEY *this, unsigned int a2)
{
  int v3; // eax
  unsigned int v4; // edi
  __int64 result; // rax
  int v6; // edi
  const char *v7; // r9
  int v8; // edi
  enum _STORAGE_RESERVE_ID v9; // r8d
  int fixed; // edi
  int v11; // ebx
  bool v12; // [rsp+20h] [rbp-38h] BYREF
  HANDLE *v13; // [rsp+28h] [rbp-30h] BYREF
  char v14; // [rsp+30h] [rbp-28h]
  __int64 v15; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v15 = -2;
  v13 = (HANDLE *)(this + 149);
  v14 = 0;
  v3 = AutoMutexLocker::Lock((AutoMutexLocker *)&v13, a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    try
    {
      v6 = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)this);
      if ( v6 >= 0 )
      {
        v12 = 0;
        v8 = DoesRegDwordExist(
               this[13],
               L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
               L"SoftParentingValidated",
               &v12);
        if ( v8 >= 0 )
        {
          if ( v12
            || (fixed = StorageReserveHelper::FixReserveAreaUntaggedParent(
                          (StorageReserveHelper *)(this + 82),
                          (const unsigned __int16 *)2,
                          v9),
                fixed >= 0) )
          {
            v11 = UpdateReserveManager::ClearReserve((UpdateReserveManager *)this, 2u);
            if ( v11 >= 0 )
            {
              if ( v14 && *v13 )
                ReleaseMutex(*v13);
              result = 0;
            }
            else
            {
              if ( v14 && *v13 )
                ReleaseMutex(*v13);
              result = (unsigned int)v11;
            }
          }
          else
          {
            if ( v14 && *v13 )
              ReleaseMutex(*v13);
            result = (unsigned int)fixed;
          }
        }
        else
        {
          if ( v14 && *v13 )
            ReleaseMutex(*v13);
          result = (unsigned int)v8;
        }
      }
      else
      {
        if ( v14 && *v13 )
          ReleaseMutex(*v13);
        result = (unsigned int)v6;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x483,
                             (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                             v7);
    }
  }
  else
  {
    if ( v14 )
    {
      if ( *v13 )
        ReleaseMutex(*v13);
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180013600  mov     r11, rsp
0x180013603  push    rdi
0x180013604  sub     rsp, 50h
0x180013608  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x180013610  mov     [r11+10h], rbx
0x180013614  mov     rbx, rcx
0x180013617  lea     rax, [rcx+4A8h]
0x18001361e  mov     [r11-30h], rax
0x180013622  mov     [rsp+58h+var_28], 0
0x180013627  lea     rcx, [r11-30h]; this
0x18001362b  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x180013630  mov     edi, eax
0x180013632  test    eax, eax
0x180013634  jns     short loc_180013657
0x180013636  cmp     [rsp+58h+var_28], 0
0x18001363b  jz      short loc_180013650
0x18001363d  mov     rcx, [rsp+58h+var_30]
0x180013642  mov     rcx, [rcx]; hMutex
0x180013645  test    rcx, rcx
0x180013648  jz      short loc_180013650
0x18001364a  call    cs:__imp_ReleaseMutex
0x180013650  mov     eax, edi
0x180013652  jmp     loc_18001375D
0x180013657  mov     rcx, rbx; this
0x18001365a  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001365f  mov     edi, eax
0x180013661  test    eax, eax
0x180013663  jns     short loc_180013686
0x180013665  cmp     [rsp+58h+var_28], 0
0x18001366a  jz      short loc_18001367F
0x18001366c  mov     rcx, [rsp+58h+var_30]
0x180013671  mov     rcx, [rcx]; hMutex
0x180013674  test    rcx, rcx
0x180013677  jz      short loc_18001367F
0x180013679  call    cs:__imp_ReleaseMutex
0x18001367f  mov     eax, edi
0x180013681  jmp     loc_18001375D
0x180013686  mov     [rsp+58h+var_38], 0
0x18001368b  lea     r9, [rsp+58h+var_38]; bool *
0x180013690  lea     r8, aSoftparentingv; "SoftParentingValidated"
0x180013697  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x18001369e  mov     rcx, [rbx+68h]; HKEY
0x1800136a2  call    ?DoesRegDwordExist@@YAJQEAUHKEY__@@QEB_W1PEA_N@Z; DoesRegDwordExist(HKEY__ * const,wchar_t const * const,wchar_t const * const,bool *)
0x1800136a7  mov     edi, eax
0x1800136a9  test    eax, eax
0x1800136ab  jns     short loc_1800136CE
0x1800136ad  cmp     [rsp+58h+var_28], 0
0x1800136b2  jz      short loc_1800136C7
0x1800136b4  mov     rcx, [rsp+58h+var_30]
0x1800136b9  mov     rcx, [rcx]; hMutex
0x1800136bc  test    rcx, rcx
0x1800136bf  jz      short loc_1800136C7
0x1800136c1  call    cs:__imp_ReleaseMutex
0x1800136c7  mov     eax, edi
0x1800136c9  jmp     loc_18001375D
0x1800136ce  cmp     [rsp+58h+var_38], 0
0x1800136d3  jnz     short loc_18001370A
0x1800136d5  lea     rcx, [rbx+290h]; this
0x1800136dc  mov     edx, 2; unsigned __int16 *
0x1800136e1  call    ?FixReserveAreaUntaggedParent@StorageReserveHelper@@YAJPEBGW4_STORAGE_RESERVE_ID@@@Z; StorageReserveHelper::FixReserveAreaUntaggedParent(ushort const *,_STORAGE_RESERVE_ID)
0x1800136e6  mov     edi, eax
0x1800136e8  test    eax, eax
0x1800136ea  jns     short loc_18001370A
0x1800136ec  cmp     [rsp+58h+var_28], 0
0x1800136f1  jz      short loc_180013706
0x1800136f3  mov     rcx, [rsp+58h+var_30]
0x1800136f8  mov     rcx, [rcx]; hMutex
0x1800136fb  test    rcx, rcx
0x1800136fe  jz      short loc_180013706
0x180013700  call    cs:__imp_ReleaseMutex
0x180013706  mov     eax, edi
0x180013708  jmp     short loc_18001375D
0x18001370a  mov     edx, 2; enum _STORAGE_RESERVE_ID
0x18001370f  mov     rcx, rbx; this
0x180013712  call    ?ClearReserve@UpdateReserveManager@@AEAAJW4_STORAGE_RESERVE_ID@@@Z; UpdateReserveManager::ClearReserve(_STORAGE_RESERVE_ID)
0x180013717  mov     ebx, eax
0x180013719  test    eax, eax
0x18001371b  jns     short loc_18001373B
0x18001371d  cmp     [rsp+58h+var_28], 0
0x180013722  jz      short loc_180013737
0x180013724  mov     rcx, [rsp+58h+var_30]
0x180013729  mov     rcx, [rcx]; hMutex
0x18001372c  test    rcx, rcx
0x18001372f  jz      short loc_180013737
0x180013731  call    cs:__imp_ReleaseMutex
0x180013737  mov     eax, ebx
0x180013739  jmp     short loc_18001375D
0x18001373b  cmp     [rsp+58h+var_28], 0
0x180013740  jz      short loc_180013755
0x180013742  mov     rax, [rsp+58h+var_30]
0x180013747  mov     rcx, [rax]; hMutex
0x18001374a  test    rcx, rcx
0x18001374d  jz      short loc_180013755
0x18001374f  call    cs:__imp_ReleaseMutex
0x180013755  xor     eax, eax
0x180013757  jmp     short loc_18001375D
0x180013759  mov     eax, [rsp+58h+var_20]
0x18001375d  mov     rbx, [rsp+58h+arg_8]
0x180013762  add     rsp, 50h
0x180013766  pop     rdi
0x180013767  retn
```
