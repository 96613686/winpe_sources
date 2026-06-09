# CCbsWorker::InitializeUpdateReserves(void)

- ea: `0x14000b2f8`
- end: `0x14000b498`
- name: `?InitializeUpdateReserves@CCbsWorker@@UEAAJXZ`
- size: `416`
- prototype: `__int64 __fastcall(CCbsWorker *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140009710`

## callees

- `0x1400064bc`
- `0x14000af9c`
- `0x14000b2f8`
- `0x14000e328`
- `0x140011a30`
- `0x140025030`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x14000b38c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x14000b38c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b397`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14000b41c`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14000b41c`

## string_xrefs

- `0x14000b467`: `Error: Not reversed from impersonation on func: %s`
- `0x14000b31e`: `InitializeUpdateReserves called`
- `0x14000b372`: `Failed to get handle to reserve manager dll`
- `0x14000b385`: `InitializeReservesAndUpdatePolicy`
- `0x14000b3ae`: `Failed to get proc address for InitializeReservesAndUpdatePolicy`
- `0x14000b3d9`: `Failed to initialize update reserves`
- `0x14000b3e2`: `TiAttemptedInitialization`
- `0x14000b402`: `Failed to set TiAttemptedInitialization to 1`
- `0x14000b40e`: `Software\Microsoft\Windows\CurrentVersion\Component Based Servicing\ReservesRebootPending`
- `0x14000b43e`: `Failed to delete KeepTiAutoStart.`
- `0x14000b45d`: `CCbsWorker::InitializeUpdateReserves`

## pseudocode

```c
__int64 __fastcall CCbsWorker::InitializeUpdateReserves(CCbsWorker *this)
{
  __int64 v1; // rcx
  int IsAuditBoot; // eax
  __int64 v3; // rcx
  signed int v4; // ebx
  int ReserveManagerDllHandle; // eax
  const char *v6; // r9
  int v7; // edx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  HKEY v10; // rcx
  LSTATUS v11; // eax
  HINSTANCE v12; // rdx
  int v14; // [rsp+30h] [rbp-18h] BYREF
  HMODULE hModule[2]; // [rsp+38h] [rbp-10h] BYREF

  v14 = 0;
  hModule[0] = 0;
  CBSWdsLog(0x4000000u, 0, 0, "InitializeUpdateReserves called");
  IsAuditBoot = OrchestrateIsAuditBootEx(v1, &v14);
  v4 = IsAuditBoot;
  if ( IsAuditBoot < 0 )
    CBSWdsLog(0x4000000u, IsAuditBoot, (size_t *)1, "Failed to get if the current boot is audit boot");
  if ( !v14 )
  {
    ReserveManagerDllHandle = CCbsWorker::GetReserveManagerDllHandle(v3, hModule);
    v4 = ReserveManagerDllHandle;
    if ( ReserveManagerDllHandle < 0 )
    {
      v6 = "Failed to get handle to reserve manager dll";
LABEL_6:
      v7 = ReserveManagerDllHandle;
LABEL_24:
      CBSWdsLog(0x4000000u, v7, (size_t *)1, v6);
      goto LABEL_25;
    }
    ProcAddress = GetProcAddress(hModule[0], "InitializeReservesAndUpdatePolicy");
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v6 = "Failed to get proc address for InitializeReservesAndUpdatePolicy";
      if ( v4 >= 0 )
        v4 = -2147467259;
      goto LABEL_23;
    }
    ReserveManagerDllHandle = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, _QWORD))ProcAddress)(0, L"TiWorker", 0);
    v4 = ReserveManagerDllHandle;
    if ( ReserveManagerDllHandle < 0 )
    {
      v6 = "Failed to initialize update reserves";
      goto LABEL_6;
    }
    ReserveManagerDllHandle = CbsRegSetDWORDValue(
                                v10,
                                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                                0,
                                (wchar_t *)L"TiAttemptedInitialization",
                                1u);
    v4 = ReserveManagerDllHandle;
    if ( ReserveManagerDllHandle < 0 )
    {
      v6 = "Failed to set TiAttemptedInitialization to 1";
      goto LABEL_6;
    }
  }
  v11 = RegDeleteKeyW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\ReservesRebootPending");
  if ( (v11 & 0xFFFFFFFC) != 0 || v11 == 1 )
  {
    if ( v11 > 0 )
      v4 = (unsigned __int16)v11 | 0x80070000;
    else
      v4 = v11;
    v6 = "Failed to delete KeepTiAutoStart.";
LABEL_23:
    v7 = v4;
    goto LABEL_24;
  }
LABEL_25:
  if ( NtCurrentTeb()->IsImpersonating )
    CBSWdsLog(
      0x4000000u,
      0,
      0,
      "Error: Not reversed from impersonation on func: %s",
      "CCbsWorker::InitializeUpdateReserves");
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(
    (Windows::Detail **)hModule,
    v12);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000b2f8  mov     rax, rsp
0x14000b2fb  mov     [rax+8], rbx
0x14000b2ff  mov     [rax+10h], rbp
0x14000b303  push    rsi
0x14000b304  sub     rsp, 40h
0x14000b308  mov     ebp, 4000000h
0x14000b30d  mov     dword ptr [rax-18h], 0
0x14000b314  mov     ecx, ebp
0x14000b316  mov     qword ptr [rax-10h], 0
0x14000b31e  lea     r9, aInitializeupda; "InitializeUpdateReserves called"
0x14000b325  xor     r8d, r8d
0x14000b328  xor     edx, edx
0x14000b32a  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000b32f  lea     rdx, [rsp+48h+var_18]
0x14000b334  call    OrchestrateIsAuditBootEx
0x14000b339  mov     ebx, eax
0x14000b33b  mov     esi, 1
0x14000b340  test    eax, eax
0x14000b342  jns     short loc_14000B357
0x14000b344  lea     r9, aFailedToGetIfT; "Failed to get if the current boot is au"...
0x14000b34b  mov     r8d, esi
0x14000b34e  mov     edx, eax
0x14000b350  mov     ecx, ebp
0x14000b352  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000b357  cmp     [rsp+48h+var_18], 0
0x14000b35c  jnz     loc_14000B40E
0x14000b362  lea     rdx, [rsp+48h+hModule]
0x14000b367  call    ?GetReserveManagerDllHandle@CCbsWorker@@AEAAJPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Z; CCbsWorker::GetReserveManagerDllHandle(Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *)
0x14000b36c  mov     ebx, eax
0x14000b36e  test    eax, eax
0x14000b370  jns     short loc_14000B380
0x14000b372  lea     r9, aFailedToGetHan; "Failed to get handle to reserve manager"...
0x14000b379  mov     edx, eax
0x14000b37b  jmp     loc_14000B447
0x14000b380  mov     rcx, [rsp+48h+hModule]; hModule
0x14000b385  lea     rdx, aInitializerese; "InitializeReservesAndUpdatePolicy"
0x14000b38c  call    cs:__imp_GetProcAddress
0x14000b392  test    rax, rax
0x14000b395  jnz     short loc_14000B3C2
0x14000b397  call    cs:__imp_GetLastError
0x14000b39d  mov     ebx, eax
0x14000b39f  test    eax, eax
0x14000b3a1  jle     short loc_14000B3AC
0x14000b3a3  movzx   ebx, ax
0x14000b3a6  or      ebx, 80070000h
0x14000b3ac  test    ebx, ebx
0x14000b3ae  lea     r9, aFailedToGetPro_1; "Failed to get proc address for Initiali"...
0x14000b3b5  mov     eax, 80004005h
0x14000b3ba  cmovns  ebx, eax
0x14000b3bd  jmp     loc_14000B445
0x14000b3c2  xor     r8d, r8d
0x14000b3c5  lea     rdx, aTiworker; "TiWorker"
0x14000b3cc  xor     ecx, ecx
0x14000b3ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b3d3  mov     ebx, eax
0x14000b3d5  test    eax, eax
0x14000b3d7  jns     short loc_14000B3E2
0x14000b3d9  lea     r9, aFailedToInitia_7; "Failed to initialize update reserves"
0x14000b3e0  jmp     short loc_14000B379
0x14000b3e2  lea     r9, aTiattemptedini; "TiAttemptedInitialization"
0x14000b3e9  mov     [rsp+48h+var_28], esi; unsigned int
0x14000b3ed  xor     r8d, r8d; unsigned int
0x14000b3f0  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14000b3f7  call    ?CbsRegSetDWORDValue@@YAJPEAUHKEY__@@PEB_WK1K@Z; CbsRegSetDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong)
0x14000b3fc  mov     ebx, eax
0x14000b3fe  test    eax, eax
0x14000b400  jns     short loc_14000B40E
0x14000b402  lea     r9, aFailedToSetTia; "Failed to set TiAttemptedInitialization"...
0x14000b409  jmp     loc_14000B379
0x14000b40e  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000b415  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000b41c  call    cs:__imp_RegDeleteKeyW
0x14000b422  test    eax, 0FFFFFFFCh
0x14000b427  jnz     short loc_14000B42D
0x14000b429  cmp     eax, esi
0x14000b42b  jnz     short loc_14000B451
0x14000b42d  test    eax, eax
0x14000b42f  jg      short loc_14000B435
0x14000b431  mov     ebx, eax
0x14000b433  jmp     short loc_14000B43E
0x14000b435  movzx   ebx, ax
0x14000b438  or      ebx, 80070000h
0x14000b43e  lea     r9, aFailedToDelete_3; "Failed to delete KeepTiAutoStart."
0x14000b445  mov     edx, ebx
0x14000b447  mov     r8d, esi
0x14000b44a  mov     ecx, ebp
0x14000b44c  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000b451  mov     eax, gs:179Ch
0x14000b459  test    eax, eax
0x14000b45b  jz      short loc_14000B47C
0x14000b45d  lea     rax, aCcbsworkerInit_0; "CCbsWorker::InitializeUpdateReserves"
0x14000b464  xor     r8d, r8d
0x14000b467  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x14000b46e  mov     qword ptr [rsp+48h+var_28], rax
0x14000b473  xor     edx, edx
0x14000b475  mov     ecx, ebp
0x14000b477  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000b47c  lea     rcx, [rsp+48h+hModule]
0x14000b481  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x14000b486  mov     rbp, [rsp+48h+arg_8]
0x14000b48b  mov     eax, ebx
0x14000b48d  mov     rbx, [rsp+48h+arg_0]
0x14000b492  add     rsp, 40h
0x14000b496  pop     rsi
0x14000b497  retn
```
