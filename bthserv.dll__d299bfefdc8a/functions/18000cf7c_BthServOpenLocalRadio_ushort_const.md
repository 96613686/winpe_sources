# BthServOpenLocalRadio(ushort const *)

- ea: `0x18000cf7c`
- end: `0x18000d3fb`
- name: `?BthServOpenLocalRadio@@YAHPEBG@Z`
- size: `1151`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18000c9d8`
- `0x18000cdfc`

## callees

- `0x18000ab58`
- `0x18000b10c`
- `0x18000c4cc`
- `0x18000cf7c`
- `0x18000deb0`
- `0x18000ed10`
- `0x18000f2e8`
- `0x180010e0c`
- `0x1800110fc`
- `0x180011194`
- `0x18001140c`
- `0x1800114c8`
- `0x180012f00`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d226`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d226`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d0ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d0ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d08c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d08c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d186`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d30d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d30d`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000d0fd`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000d0fd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d079`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d079`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall BthServOpenLocalRadio(LPCWSTR lpFileName)
{
  unsigned int v2; // ebp
  char v3; // di
  _BYTE *v4; // rcx
  bool v5; // dl
  _UNKNOWN **v6; // rax
  bool v7; // dl
  HANDLE FileW; // rbx
  __int64 v9; // r8
  void **v10; // r14
  bool v11; // bl
  bool v12; // si
  int v13; // r8d
  int v14; // edx
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rax
  unsigned __int64 i; // rax
  unsigned __int64 v18; // rcx
  bool v19; // bl
  bool v20; // si
  int v21; // r8d
  int v22; // edx
  _BYTE *v23; // rcx
  bool v24; // bl
  bool v25; // si
  int v26; // r8d
  int v27; // edx
  volatile signed __int32 *v28; // rbx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-68h]
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-60h]
  void **v32; // [rsp+50h] [rbp-38h] BYREF
  volatile signed __int32 *v33; // [rsp+58h] [rbp-30h]
  int v34; // [rsp+98h] [rbp+10h] BYREF
  RTL_SRWLOCK *v35; // [rsp+A0h] [rbp+18h]

  v34 = 0;
  v2 = 0;
  v3 = 1;
  v4 = WPP_GLOBAL_Control;
  v5 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v6 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v4 = WPP_GLOBAL_Control;
    v6 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  v7 = v4 != (_BYTE *)&WPP_GLOBAL_Control && v4[25] >= 5u;
  if ( v7 || v6 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sS(*((_QWORD *)v4 + 2), v7, v6 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v4 + 5));
  FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
  AcquireSRWLockExclusive(&stru_180044AC0);
  v35 = &stru_180044AC0;
  wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
    qword_180044AC8,
    FileW);
  ReleaseSRWLockExclusive(&stru_180044AC0);
  BthServGlobals::GetSafeRadioHandle(&Globals, &v32, v9);
  v10 = v32;
  if ( v32 && (char *)*v32 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( pv )
    {
      if ( !TrySubmitThreadpoolCallback(BthServUnregisterDeviceNotificationCallback, pv, 0) )
      {
        v11 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
        v12 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          GetLastError();
          LOBYTE(v13) = v12;
          LOBYTE(v14) = v11;
          WPP_RECORDER_AND_TRACE_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v14,
            v13,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            dwCreationDisposition,
            dwFlagsAndAttributes,
            86,
            (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
        }
      }
      pv = 0;
    }
    v34 = 1;
    if ( !WaitForSingleObject(hMutex, 0xFFFFFFFF) )
    {
      v15 = (unsigned __int64)qword_180044B38;
      if ( qword_180044B38 )
      {
        while ( 1 )
        {
LABEL_47:
          if ( (int)BthAuthClientWalkFxn(v15, &v34) < 0 )
            goto LABEL_48;
          v16 = *(_QWORD *)v15;
          if ( !*(_QWORD *)v15 )
          {
            v16 = *(_QWORD *)(v15 + 8);
            if ( !v16 )
              break;
          }
          if ( (qword_180044B40 & 1) != 0 )
            v15 ^= v16;
          else
            v15 = v16;
        }
        for ( i = v15; ; v15 = i )
        {
          i = *(_QWORD *)(i + 16) & 0xFFFFFFFFFFFFFFFCuLL;
          if ( (qword_180044B40 & 1) != 0 )
          {
            if ( !i )
              break;
            i ^= v15;
          }
          if ( !i )
            break;
          v18 = *(_QWORD *)(i + 8);
          if ( (qword_180044B40 & 1) != 0 )
          {
            if ( !v18 )
              continue;
            v18 ^= i;
          }
          if ( v18 && v18 != v15 )
          {
            v15 = v18;
            goto LABEL_47;
          }
        }
      }
LABEL_48:
      ReleaseMutex(hMutex);
    }
    pv = BthServRegisterHandleNotifications(*v10);
    if ( pv )
    {
      v2 = BthServListenForAsyncEvents(hObject == 0);
    }
    else
    {
      v19 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      v20 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        GetLastError();
        LOBYTE(v21) = v20;
        LOBYTE(v22) = v19;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v22,
          v21,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          dwCreationDisposition,
          dwFlagsAndAttributes,
          87,
          (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
      }
      BthServGlobals::CloseRadioHandle((BthServGlobals *)&Globals);
      wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
        &v32,
        -1);
    }
    BthServBluetoothControlPanelTasksSetState(1);
    BthServStartLEPrepairing();
    goto LABEL_67;
  }
  v23 = WPP_GLOBAL_Control;
  v24 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
  v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v24 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    GetLastError();
    LOBYTE(v26) = v25;
    LOBYTE(v27) = v24;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v27,
      v26,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      dwCreationDisposition,
      dwFlagsAndAttributes,
      88,
      (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
LABEL_67:
    v23 = WPP_GLOBAL_Control;
  }
  v28 = v33;
  if ( v33 )
  {
    if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
      if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
    }
    v23 = WPP_GLOBAL_Control;
  }
  if ( v23 == (_BYTE *)&WPP_GLOBAL_Control || v23[25] < 5u )
    v3 = 0;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)v23 + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v23 + 5));
  return v2;
}

```

## disassembly

```asm
0x18000cf7c  mov     rax, rsp
0x18000cf7f  mov     [rax+8], rbx
0x18000cf83  mov     [rax+20h], rbp
0x18000cf87  push    rsi
0x18000cf88  push    rdi
0x18000cf89  push    r12
0x18000cf8b  push    r13
0x18000cf8d  push    r14
0x18000cf8f  sub     rsp, 60h
0x18000cf93  mov     rbx, rcx
0x18000cf96  mov     dword ptr [rax+10h], 0
0x18000cf9d  xor     ebp, ebp
0x18000cf9f  lea     r12, WPP_GLOBAL_Control
0x18000cfa6  lea     edi, [rbp+1]
0x18000cfa9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfb0  cmp     rcx, r12
0x18000cfb3  jz      short loc_18000CFC0
0x18000cfb5  cmp     byte ptr [rcx+19h], 5
0x18000cfb9  jb      short loc_18000CFC0
0x18000cfbb  mov     dl, dil
0x18000cfbe  jmp     short loc_18000CFC2
0x18000cfc0  xor     dl, dl
0x18000cfc2  lea     r13, WPP_RECORDER_INITIALIZED
0x18000cfc9  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18000cfd0  cmp     rax, r13
0x18000cfd3  setnz   r8b
0x18000cfd7  lea     r9, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000cfde  test    dl, dl
0x18000cfe0  jnz     short loc_18000CFE7
0x18000cfe2  test    r8b, r8b
0x18000cfe5  jz      short loc_18000D015
0x18000cfe7  mov     [rsp+88h+var_50], r9
0x18000cfec  mov     word ptr [rsp+88h+hTemplateFile], 54h ; 'T'
0x18000cff3  mov     r9, [rcx+28h]
0x18000cff7  mov     rcx, [rcx+10h]
0x18000cffb  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000d000  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d007  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18000d00e  lea     r9, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000d015  cmp     rcx, r12
0x18000d018  jz      short loc_18000D025
0x18000d01a  cmp     byte ptr [rcx+19h], 5
0x18000d01e  jb      short loc_18000D025
0x18000d020  mov     dl, dil
0x18000d023  jmp     short loc_18000D027
0x18000d025  xor     dl, dl
0x18000d027  cmp     rax, r13
0x18000d02a  setnz   r8b
0x18000d02e  test    dl, dl
0x18000d030  jnz     short loc_18000D037
0x18000d032  test    r8b, r8b
0x18000d035  jz      short loc_18000D055
0x18000d037  mov     [rsp+88h+var_40], rbx
0x18000d03c  mov     [rsp+88h+var_50], r9
0x18000d041  mov     word ptr [rsp+88h+hTemplateFile], 55h ; 'U'
0x18000d048  mov     r9, [rcx+28h]
0x18000d04c  mov     rcx, [rcx+10h]
0x18000d050  call    WPP_RECORDER_AND_TRACE_SF_sS
0x18000d055  mov     [rsp+88h+hTemplateFile], rbp; hTemplateFile
0x18000d05a  mov     [rsp+88h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18000d062  mov     eax, 3
0x18000d067  mov     [rsp+88h+dwCreationDisposition], eax; dwCreationDisposition
0x18000d06b  xor     r9d, r9d; lpSecurityAttributes
0x18000d06e  mov     r8d, eax; dwShareMode
0x18000d071  mov     edx, 0C0000000h; dwDesiredAccess
0x18000d076  mov     rcx, rbx; lpFileName
0x18000d079  call    cs:__imp_CreateFileW
0x18000d07f  mov     rbx, rax
0x18000d082  lea     rsi, stru_180044AC0
0x18000d089  mov     rcx, rsi; SRWLock
0x18000d08c  call    cs:__imp_AcquireSRWLockExclusive
0x18000d092  mov     [rsp+88h+arg_10], rsi
0x18000d09a  mov     rdx, rbx
0x18000d09d  lea     rcx, qword_180044AC8
0x18000d0a4  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x18000d0a9  nop
0x18000d0aa  mov     rcx, rsi; SRWLock
0x18000d0ad  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d0b3  lea     rdx, [rsp+88h+var_38]
0x18000d0b8  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x18000d0bf  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x18000d0c4  nop
0x18000d0c5  mov     r14, [rsp+88h+var_38]
0x18000d0ca  test    r14, r14
0x18000d0cd  jz      loc_18000D2E0
0x18000d0d3  mov     rax, [r14]
0x18000d0d6  sub     rax, rdi
0x18000d0d9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d0dd  ja      loc_18000D2E0
0x18000d0e3  mov     rdx, qword ptr cs:pv; pv
0x18000d0ea  test    rdx, rdx
0x18000d0ed  jz      loc_18000D175
0x18000d0f3  xor     r8d, r8d; pcbe
0x18000d0f6  lea     rcx, ?BthServUnregisterDeviceNotificationCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18000d0fd  call    cs:__imp_TrySubmitThreadpoolCallback
0x18000d103  test    eax, eax
0x18000d105  jnz     short loc_18000D16A
0x18000d107  mov     rax, cs:WPP_GLOBAL_Control
0x18000d10e  cmp     rax, r12
0x18000d111  jz      short loc_18000D11E
0x18000d113  cmp     byte ptr [rax+19h], 3
0x18000d117  jb      short loc_18000D11E
0x18000d119  mov     bl, dil
0x18000d11c  jmp     short loc_18000D120
0x18000d11e  xor     bl, bl
0x18000d120  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000d127  setnz   sil
0x18000d12b  test    bl, bl
0x18000d12d  jnz     short loc_18000D134
0x18000d12f  test    sil, sil
0x18000d132  jz      short loc_18000D16A
0x18000d134  call    cs:__imp_GetLastError
0x18000d13a  mov     dword ptr [rsp+88h+var_40], eax
0x18000d13e  lea     rax, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000d145  mov     [rsp+88h+var_50], rax
0x18000d14a  mov     word ptr [rsp+88h+hTemplateFile], 56h ; 'V'
0x18000d151  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d158  mov     r9, [rcx+28h]
0x18000d15c  mov     r8b, sil
0x18000d15f  mov     dl, bl
0x18000d161  mov     rcx, [rcx+10h]
0x18000d165  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18000d16a  mov     qword ptr cs:pv, 0
0x18000d175  mov     [rsp+88h+arg_8], edi
0x18000d17c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d17f  mov     rcx, cs:hMutex; hHandle
0x18000d186  call    cs:__imp_WaitForSingleObject
0x18000d18c  test    eax, eax
0x18000d18e  jnz     loc_18000D22C
0x18000d194  mov     rbx, cs:qword_180044B38
0x18000d19b  test    rbx, rbx
0x18000d19e  jz      short loc_18000D21F
0x18000d1a0  jmp     short loc_18000D20B
0x18000d1a2  mov     rax, [rbx]
0x18000d1a5  test    rax, rax
0x18000d1a8  jz      short loc_18000D1B8
0x18000d1aa  test    byte ptr cs:qword_180044B40, dil
0x18000d1b1  jz      short loc_18000D203
0x18000d1b3  xor     rbx, rax
0x18000d1b6  jmp     short loc_18000D20B
0x18000d1b8  mov     rax, [rbx+8]
0x18000d1bc  test    rax, rax
0x18000d1bf  jnz     short loc_18000D1AA
0x18000d1c1  mov     rax, rbx
0x18000d1c4  mov     rax, [rax+10h]
0x18000d1c8  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000d1cc  mov     dl, byte ptr cs:qword_180044B40
0x18000d1d2  and     dl, dil
0x18000d1d5  jz      short loc_18000D1DF
0x18000d1d7  test    rax, rax
0x18000d1da  jz      short loc_18000D21F
0x18000d1dc  xor     rax, rbx
0x18000d1df  test    rax, rax
0x18000d1e2  jz      short loc_18000D21F
0x18000d1e4  mov     rcx, [rax+8]
0x18000d1e8  test    dl, dl
0x18000d1ea  jz      short loc_18000D1F4
0x18000d1ec  test    rcx, rcx
0x18000d1ef  jz      short loc_18000D1FE
0x18000d1f1  xor     rcx, rax
0x18000d1f4  test    rcx, rcx
0x18000d1f7  jz      short loc_18000D1FE
0x18000d1f9  cmp     rcx, rbx
0x18000d1fc  jnz     short loc_18000D208
0x18000d1fe  mov     rbx, rax
0x18000d201  jmp     short loc_18000D1C4
0x18000d203  mov     rbx, rax
0x18000d206  jmp     short loc_18000D20B
0x18000d208  mov     rbx, rcx
0x18000d20b  lea     rdx, [rsp+88h+arg_8]
0x18000d213  mov     rcx, rbx
0x18000d216  call    BthAuthClientWalkFxn
0x18000d21b  test    eax, eax
0x18000d21d  jns     short loc_18000D1A2
0x18000d21f  mov     rcx, cs:hMutex; hMutex
0x18000d226  call    cs:__imp_ReleaseMutex
0x18000d22c  mov     rcx, [r14]; void *
0x18000d22f  call    ?BthServRegisterHandleNotifications@@YAPEAUHCMNOTIFICATION__@@PEAX@Z; BthServRegisterHandleNotifications(void *)
0x18000d234  mov     qword ptr cs:pv, rax
0x18000d23b  test    rax, rax
0x18000d23e  jz      short loc_18000D255
0x18000d240  xor     ecx, ecx
0x18000d242  cmp     qword ptr cs:hObject, rcx
0x18000d249  setz    cl; int
0x18000d24c  call    ?BthServListenForAsyncEvents@@YAHH@Z; BthServListenForAsyncEvents(int)
0x18000d251  mov     ebp, eax
0x18000d253  jmp     short loc_18000D2D2
0x18000d255  mov     rax, cs:WPP_GLOBAL_Control
0x18000d25c  cmp     rax, r12
0x18000d25f  jz      short loc_18000D26C
0x18000d261  cmp     byte ptr [rax+19h], 3
0x18000d265  jb      short loc_18000D26C
0x18000d267  mov     bl, dil
0x18000d26a  jmp     short loc_18000D26E
0x18000d26c  xor     bl, bl
0x18000d26e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000d275  setnz   sil
0x18000d279  test    bl, bl
0x18000d27b  jnz     short loc_18000D282
0x18000d27d  test    sil, sil
0x18000d280  jz      short loc_18000D2B8
0x18000d282  call    cs:__imp_GetLastError
0x18000d288  mov     dword ptr [rsp+88h+var_40], eax
0x18000d28c  lea     rax, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000d293  mov     [rsp+88h+var_50], rax
0x18000d298  mov     word ptr [rsp+88h+hTemplateFile], 57h ; 'W'
0x18000d29f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2a6  mov     r9, [rcx+28h]
0x18000d2aa  mov     r8b, sil
0x18000d2ad  mov     dl, bl
0x18000d2af  mov     rcx, [rcx+10h]
0x18000d2b3  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18000d2b8  lea     rcx, ?Globals@@3VBthServGlobals@@A; this
0x18000d2bf  call    ?CloseRadioHandle@BthServGlobals@@QEAAXXZ; BthServGlobals::CloseRadioHandle(void)
0x18000d2c4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000d2c8  lea     rcx, [rsp+88h+var_38]
0x18000d2cd  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x18000d2d2  mov     ecx, edi; int
0x18000d2d4  call    ?BthServBluetoothControlPanelTasksSetState@@YAXH@Z; BthServBluetoothControlPanelTasksSetState(int)
0x18000d2d9  call    ?BthServStartLEPrepairing@@YAXXZ; BthServStartLEPrepairing(void)
0x18000d2de  jmp     short loc_18000D343
0x18000d2e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2e7  cmp     rcx, r12
0x18000d2ea  jz      short loc_18000D2F7
0x18000d2ec  cmp     byte ptr [rcx+19h], 3
0x18000d2f0  jb      short loc_18000D2F7
0x18000d2f2  mov     bl, dil
0x18000d2f5  jmp     short loc_18000D2F9
0x18000d2f7  xor     bl, bl
0x18000d2f9  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000d300  setnz   sil
0x18000d304  test    bl, bl
0x18000d306  jnz     short loc_18000D30D
0x18000d308  test    sil, sil
0x18000d30b  jz      short loc_18000D34A
0x18000d30d  call    cs:__imp_GetLastError
0x18000d313  mov     dword ptr [rsp+88h+var_40], eax
0x18000d317  lea     rax, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000d31e  mov     [rsp+88h+var_50], rax
0x18000d323  mov     word ptr [rsp+88h+hTemplateFile], 58h ; 'X'
0x18000d32a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d331  mov     r9, [rcx+28h]
0x18000d335  mov     r8b, sil
0x18000d338  mov     dl, bl
0x18000d33a  mov     rcx, [rcx+10h]
0x18000d33e  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18000d343  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d34a  mov     rbx, [rsp+88h+var_30]
0x18000d34f  test    rbx, rbx
0x18000d352  jz      short loc_18000D392
0x18000d354  or      eax, 0FFFFFFFFh
0x18000d357  lock xadd [rbx+8], eax
0x18000d35c  cmp     eax, 1
0x18000d35f  jnz     short loc_18000D38B
0x18000d361  mov     rax, [rbx]
0x18000d364  mov     rcx, rbx
0x18000d367  mov     rax, [rax]
0x18000d36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d36f  or      eax, 0FFFFFFFFh
0x18000d372  lock xadd [rbx+0Ch], eax
0x18000d377  cmp     eax, 1
0x18000d37a  jnz     short loc_18000D38B
0x18000d37c  mov     rax, [rbx]
0x18000d37f  mov     rcx, rbx
0x18000d382  mov     rax, [rax+8]
0x18000d386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d38b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d392  cmp     rcx, r12
0x18000d395  jz      short loc_18000D39D
0x18000d397  cmp     byte ptr [rcx+19h], 5
0x18000d39b  jnb     short loc_18000D3A0
0x18000d39d  xor     dil, dil
0x18000d3a0  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000d3a7  setnz   r8b
0x18000d3ab  test    dil, dil
0x18000d3ae  jnz     short loc_18000D3B5
0x18000d3b0  test    r8b, r8b
0x18000d3b3  jz      short loc_18000D3E0
0x18000d3b5  movsxd  rax, ebp
0x18000d3b8  mov     [rsp+88h+var_40], rax
0x18000d3bd  lea     rax, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000d3c4  mov     [rsp+88h+var_50], rax
0x18000d3c9  mov     word ptr [rsp+88h+hTemplateFile], 59h ; 'Y'
0x18000d3d0  mov     r9, [rcx+28h]
0x18000d3d4  mov     dl, dil
0x18000d3d7  mov     rcx, [rcx+10h]
0x18000d3db  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000d3e0  mov     eax, ebp
0x18000d3e2  lea     r11, [rsp+88h+var_28]
0x18000d3e7  mov     rbx, [r11+30h]
0x18000d3eb  mov     rbp, [r11+48h]
0x18000d3ef  mov     rsp, r11
0x18000d3f2  pop     r14
0x18000d3f4  pop     r13
0x18000d3f6  pop     r12
0x18000d3f8  pop     rdi
0x18000d3f9  pop     rsi
0x18000d3fa  retn
```
