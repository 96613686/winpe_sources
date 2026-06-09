# CRegistryChangeListener::_Initialize(HKEY__ *,ushort const *,REGISTRY_LISTENER_FLAGS,void (*)(void *),void *)

- ea: `0x180009468`
- end: `0x180009611`
- name: `?_Initialize@CRegistryChangeListener@@QEAAJPEAUHKEY__@@PEBGW4REGISTRY_LISTENER_FLAGS@@P6AXPEAX@Z3@Z`
- size: `425`
- prototype: `__int64 __fastcall(__int64, __int64, void *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009180`

## callees

- `0x1800034cc`
- `0x180009468`
- `0x180009618`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000955e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000955e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009518`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009518`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800094b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800094b9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009588`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009588`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800095c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800095c2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800095a4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800095a4`
- `SHLWAPI!SHStrDupW` at `0x1800094e1`
- `SHLWAPI!SHStrDupW` at `0x1800094e1`

## pseudocode

```c
__int64 __fastcall CRegistryChangeListener::_Initialize(
        __int64 a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  LSTATUS v7; // eax
  int Error; // ebx
  unsigned int *v9; // rsi
  HANDLE EventW; // rax
  PTP_WORK ThreadpoolWork; // rax
  PTP_WAIT ThreadpoolWait; // rax
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  ppv = a3;
  *(_DWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 56) = CUACSettingsPage::s_UACSettingChangeCB;
  *(_QWORD *)(a1 + 72) = a6;
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
         0,
         0x20019u,
         (PHKEY)(a1 + 32));
  Error = v7;
  if ( v7 > 0 )
    Error = (unsigned __int16)v7 | 0x80070000;
  if ( Error >= 0 )
  {
    Error = SHStrDupW(L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\System", (LPWSTR *)(a1 + 80));
    if ( Error >= 0 )
    {
      ppv = 0;
      Error = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
      if ( Error >= 0 )
      {
        v9 = (unsigned int *)(a1 + 48);
        Error = (*(__int64 (__fastcall **)(LPVOID, __int64, GUID *, __int64))(*(_QWORD *)ppv + 24LL))(
                  ppv,
                  a1,
                  &IID_IOleCommandTarget,
                  a1 + 48);
        if ( Error < 0 )
        {
LABEL_14:
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          return (unsigned int)Error;
        }
        EventW = CreateEventW(0, 0, 0, 0);
        *(_QWORD *)(a1 + 24) = EventW;
        if ( EventW )
        {
          Error = CRegistryChangeListener::_RestoreChangeCallback((CRegistryChangeListener *)a1);
          if ( Error < 0 )
            goto LABEL_13;
          ThreadpoolWork = CreateThreadpoolWork(CRegistryChangeListener::s_CleanupCB, (PVOID)a1, 0);
          *(_QWORD *)(a1 + 64) = ThreadpoolWork;
          if ( ThreadpoolWork )
          {
            ThreadpoolWait = CreateThreadpoolWait(CRegistryChangeListener::s_RegistryChangeCB, (PVOID)(int)*v9, 0);
            *(_QWORD *)(a1 + 40) = ThreadpoolWait;
            if ( ThreadpoolWait )
            {
              _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
              SetThreadpoolWait(*(PTP_WAIT *)(a1 + 40), *(HANDLE *)(a1 + 24), 0);
              goto LABEL_14;
            }
          }
        }
        Error = ResultFromKnownLastError();
        if ( Error >= 0 )
          goto LABEL_14;
LABEL_13:
        (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, *v9);
        *v9 = 0;
        goto LABEL_14;
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180009468  mov     r11, rsp
0x18000946b  mov     [r11+8], rbx
0x18000946f  mov     [r11+10h], rsi
0x180009473  mov     [r11+18h], r8
0x180009477  push    rdi
0x180009478  sub     rsp, 30h
0x18000947c  lea     rax, ?s_UACSettingChangeCB@CUACSettingsPage@@CAXPEAX@Z; CUACSettingsPage::s_UACSettingChangeCB(void *)
0x180009483  mov     dword ptr [rcx+58h], 0
0x18000948a  mov     [rcx+38h], rax
0x18000948e  lea     rdx, psz; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180009495  mov     rax, [rsp+38h+arg_28]
0x18000949a  mov     rdi, rcx
0x18000949d  mov     [rcx+48h], rax
0x1800094a1  mov     r9d, 20019h; samDesired
0x1800094a7  lea     rax, [rcx+20h]
0x1800094ab  xor     r8d, r8d; ulOptions
0x1800094ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800094b5  mov     [r11-18h], rax
0x1800094b9  call    cs:__imp_RegOpenKeyExW
0x1800094bf  mov     ebx, eax
0x1800094c1  test    eax, eax
0x1800094c3  jle     short loc_1800094CE
0x1800094c5  movzx   ebx, ax
0x1800094c8  or      ebx, 80070000h
0x1800094ce  test    ebx, ebx
0x1800094d0  js      loc_1800095FF
0x1800094d6  lea     rdx, [rdi+50h]; ppwsz
0x1800094da  lea     rcx, psz; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800094e1  call    cs:__imp_SHStrDupW
0x1800094e7  mov     ebx, eax
0x1800094e9  test    eax, eax
0x1800094eb  js      loc_1800095FF
0x1800094f1  xor     edx, edx; pUnkOuter
0x1800094f3  mov     [rsp+38h+arg_10], 0
0x1800094fc  lea     rax, [rsp+38h+arg_10]
0x180009501  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180009508  mov     [rsp+38h+ppv], rax; ppv
0x18000950d  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180009514  lea     r8d, [rdx+1]; dwClsContext
0x180009518  call    cs:__imp_CoCreateInstance
0x18000951e  mov     ebx, eax
0x180009520  test    eax, eax
0x180009522  js      loc_1800095FF
0x180009528  mov     rcx, [rsp+38h+arg_10]
0x18000952d  lea     rsi, [rdi+30h]
0x180009531  mov     r9, rsi
0x180009534  lea     r8, IID_IOleCommandTarget
0x18000953b  mov     rdx, rdi
0x18000953e  mov     rax, [rcx]
0x180009541  mov     rax, [rax+18h]
0x180009545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000954a  mov     ebx, eax
0x18000954c  test    eax, eax
0x18000954e  js      loc_1800095EE
0x180009554  xor     r9d, r9d; lpName
0x180009557  xor     r8d, r8d; bInitialState
0x18000955a  xor     edx, edx; bManualReset
0x18000955c  xor     ecx, ecx; lpEventAttributes
0x18000955e  call    cs:__imp_CreateEventW
0x180009564  mov     [rdi+18h], rax
0x180009568  test    rax, rax
0x18000956b  jz      short loc_1800095CA
0x18000956d  mov     rcx, rdi; this
0x180009570  call    ?_RestoreChangeCallback@CRegistryChangeListener@@AEAAJXZ; CRegistryChangeListener::_RestoreChangeCallback(void)
0x180009575  mov     ebx, eax
0x180009577  test    eax, eax
0x180009579  js      short loc_1800095D5
0x18000957b  xor     r8d, r8d; pcbe
0x18000957e  lea     rcx, ?s_CleanupCB@CRegistryChangeListener@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180009585  mov     rdx, rdi; pv
0x180009588  call    cs:__imp_CreateThreadpoolWork
0x18000958e  mov     [rdi+40h], rax
0x180009592  test    rax, rax
0x180009595  jz      short loc_1800095CA
0x180009597  movsxd  rdx, dword ptr [rsi]; pv
0x18000959a  lea     rcx, ?s_RegistryChangeCB@CRegistryChangeListener@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800095a1  xor     r8d, r8d; pcbe
0x1800095a4  call    cs:__imp_CreateThreadpoolWait
0x1800095aa  mov     [rdi+28h], rax
0x1800095ae  test    rax, rax
0x1800095b1  jz      short loc_1800095CA
0x1800095b3  lock inc dword ptr [rdi+10h]
0x1800095b7  mov     rdx, [rdi+18h]; h
0x1800095bb  xor     r8d, r8d; pftTimeout
0x1800095be  mov     rcx, [rdi+28h]; pwa
0x1800095c2  call    cs:__imp_SetThreadpoolWait
0x1800095c8  jmp     short loc_1800095EE
0x1800095ca  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800095cf  mov     ebx, eax
0x1800095d1  test    eax, eax
0x1800095d3  jns     short loc_1800095EE
0x1800095d5  mov     rcx, [rsp+38h+arg_10]
0x1800095da  mov     edx, [rsi]
0x1800095dc  mov     rax, [rcx]
0x1800095df  mov     rax, [rax+20h]
0x1800095e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095e8  mov     dword ptr [rsi], 0
0x1800095ee  mov     rcx, [rsp+38h+arg_10]
0x1800095f3  mov     rax, [rcx]
0x1800095f6  mov     rax, [rax+10h]
0x1800095fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095ff  mov     rsi, [rsp+38h+arg_8]
0x180009604  mov     eax, ebx
0x180009606  mov     rbx, [rsp+38h+arg_0]
0x18000960b  add     rsp, 30h
0x18000960f  pop     rdi
0x180009610  retn
```
