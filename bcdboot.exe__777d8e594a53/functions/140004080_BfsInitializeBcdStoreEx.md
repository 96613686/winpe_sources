# BfsInitializeBcdStoreEx

- ea: `0x140004080`
- end: `0x1400045bf`
- name: `BfsInitializeBcdStoreEx`
- size: `1343`
- prototype: `__int64 __fastcall(void *Src, unsigned int, __int64, __int128 *, __int64)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140001bc8`
- `0x140009658`

## callees

- `0x140002ba8`
- `0x140004080`
- `0x1400045c8`
- `0x140004a60`
- `0x140004e20`
- `0x140005e18`
- `0x14000636c`
- `0x140006cd8`
- `0x140007c10`
- `0x140007cdc`
- `0x14000e578`
- `0x14000e5c8`
- `0x14000e628`
- `0x14000efc8`
- `0x14001a8c4`
- `0x14001a964`
- `0x14001ac80`
- `0x14001acec`
- `0x14001adb8`
- `0x14001bb00`
- `0x140026650`
- `0x140027010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1400041fc`
- `msvcrt!swprintf_s` at `0x140004221`
- `msvcrt!swprintf_s` at `0x1400041fc`
- `msvcrt!swprintf_s` at `0x140004221`
- `KERNEL32!SetLastError` at `0x14000458d`
- `KERNEL32!SetLastError` at `0x14000458d`
- `KERNEL32!GetLastError` at `0x140004441`
- `KERNEL32!GetLastError` at `0x140004488`
- `KERNEL32!GetLastError` at `0x140004441`
- `KERNEL32!GetLastError` at `0x140004488`
- `KERNEL32!GetProcAddress` at `0x14000445a`
- `KERNEL32!GetProcAddress` at `0x14000445a`
- `KERNEL32!FreeLibrary` at `0x140004493`
- `KERNEL32!FreeLibrary` at `0x140004493`
- `KERNEL32!LoadLibraryExW` at `0x140004433`
- `KERNEL32!LoadLibraryExW` at `0x140004433`
- `SHLWAPI!PathRemoveBackslashW` at `0x1400040f5`
- `SHLWAPI!PathRemoveBackslashW` at `0x140004104`
- `SHLWAPI!PathRemoveBackslashW` at `0x1400040f5`
- `SHLWAPI!PathRemoveBackslashW` at `0x140004104`
- `ntdll!RtlNtStatusToDosError` at `0x140004585`
- `ntdll!RtlNtStatusToDosError` at `0x140004585`
- `ntdll!RtlInitUnicodeString` at `0x140004231`
- `ntdll!RtlInitUnicodeString` at `0x140004231`

## string_xrefs

- `0x140004241`: `Opening store from %ws`
- `0x140004289`: `Reopening system store.`
- `0x140004362`: `Failed to create a new system store. Status = [%x]`
- `0x140004300`: `BcdOpenStore failed with unexpected error code, Status = [%x]`
- `0x14000440c`: `Failed to create recovery store. Status = [%x]`
- `0x14000442a`: `REAGENT.DLL`
- `0x140004450`: `WinRePostBCDRepair`

## pseudocode

```c
__int64 __fastcall BfsInitializeBcdStoreEx(void *Src, unsigned int a2, __int64 a3, __int128 *a4, __int64 a5)
{
  __int64 v8; // rdi
  WCHAR *v9; // rcx
  NTSTATUS v10; // ebx
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // r12
  const wchar_t *v14; // rcx
  __int64 v15; // rax
  struct _UNICODE_STRING *p_DestinationString; // rdi
  __int64 v17; // r8
  int v18; // eax
  __int64 v19; // r8
  int v20; // eax
  __int64 v21; // rdx
  int v22; // eax
  HANDLE v23; // rdi
  int v24; // eax
  const wchar_t *v25; // rdx
  __int64 v26; // rcx
  int RecoveryStore; // eax
  HMODULE Library; // rax
  HMODULE v29; // r14
  DWORD v30; // eax
  void *v31; // r15
  signed int LastError; // ebx
  FARPROC ProcAddress; // rax
  bool v34; // sf
  int v35; // eax
  int v36; // eax
  int v37; // eax
  ULONG v38; // eax
  HANDLE Handle; // [rsp+30h] [rbp-D0h] BYREF
  void *v41; // [rsp+38h] [rbp-C8h]
  __int64 v42; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v44; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  v41 = Src;
  Handle = 0;
  v42 = 0;
  v8 = 0;
  DestinationString = 0;
  v44 = 0;
  if ( a5 )
  {
    v8 = *(_QWORD *)(a5 + 16);
    if ( v8 )
      PathRemoveBackslashW(*(LPWSTR *)(a5 + 16));
    v9 = *(WCHAR **)(a5 + 8);
    if ( v9 )
      PathRemoveBackslashW(v9);
  }
  BfspLogInitialize((a2 & 8) == 0 ? 3 : 0);
  BfspLogMessage(
    2,
    L"BfsInitializeBcdStore flags(0x%08x) RetainElementData:%c DelExistinObject:%c",
    a2,
    (a2 & 0x40) != 0 ? 121 : 110,
    (a2 & 0x2000) != 0 ? 121 : 110);
  v10 = BfspInitializeGlobalState(Src);
  if ( v10 >= 0 )
  {
    v11 = BfspOpenTemplateStore(&v42);
    v13 = v42;
    v10 = v11;
    if ( v11 < 0 )
      goto LABEL_74;
    if ( (a2 & 0x10) != 0 )
    {
      v14 = L"\\EFI\\Microsoft\\Boot\\BCD";
      if ( !byte_14003F8F8 )
        v14 = L"\\boot\\BCD";
      if ( !v8 )
        goto LABEL_16;
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v8 + 2 * v15) );
      if ( v15 )
        swprintf_s(Buffer, 0x104u, L"%s\\%s%s", ::Src, v8, v14);
      else
LABEL_16:
        swprintf_s(Buffer, 0x104u, L"%s%s", ::Src, v14);
      RtlInitUnicodeString(&DestinationString, Buffer);
      p_DestinationString = &DestinationString;
      BfspLogMessage(2, L"Opening store from %ws", Buffer);
      v10 = BiOpenStoreWithHash(&DestinationString, 0, v17, &Handle);
    }
    else
    {
      p_DestinationString = 0;
      v10 = BiOpenStoreWithHash(0, ~BYTE2(a2) & 2, v12, &Handle);
      if ( v10 >= 0 )
      {
        if ( (a2 & 0x40000) != 0 )
          goto LABEL_39;
        BfspLogMessage(2, L"Reopening system store.");
        v18 = BcdForciblyUnloadStore(Handle);
        if ( v18 < 0 )
          BfspLogMessage(3, L"Failed to forcibly unload the system store. Status = [%x]", (unsigned int)v18);
        Handle = 0;
        v10 = BiOpenStoreWithHash(0, ~BYTE2(a2) & 2, v19, &Handle);
      }
    }
    if ( v10 == -1073741275 || v10 == -1073741809 )
    {
      BfspLogMessage(2, L"System BCD store does not exist, creating.");
    }
    else
    {
      if ( v10 != -1073741476 && v10 != -1073741492 )
      {
        if ( v10 < 0 )
        {
          BfspLogMessage(4, L"BcdOpenStore failed with unexpected error code, Status = [%x]", (unsigned int)v10);
LABEL_34:
          v23 = Handle;
          goto LABEL_72;
        }
        goto LABEL_39;
      }
      BfspLogMessage(3, L"System BCD store is corrupt.");
      v20 = BfspBackupCorruptStore(p_DestinationString);
      if ( v20 < 0 )
        BfspLogMessage(3, L"Failed to backup corrupt BCD store. Status = [%x]", (unsigned int)v20);
    }
    v22 = BcdCreateStoreEx(p_DestinationString, v21, &Handle);
    v10 = v22;
    if ( v22 < 0 )
    {
      BfspLogMessage(4, L"Failed to create a new system store. Status = [%x]", (unsigned int)v22);
      goto LABEL_34;
    }
    if ( p_DestinationString )
    {
      v23 = Handle;
      v24 = BcdMarkAsSystemStore(Handle);
      v10 = v24;
      if ( v24 < 0 )
      {
        v25 = L"Failed to mark store as system store. Status = [%x]";
LABEL_38:
        v26 = 4;
LABEL_71:
        BfspLogMessage(v26, v25, (unsigned int)v24);
LABEL_72:
        if ( v23 )
          BcdCloseStore((__int64)v23);
        goto LABEL_74;
      }
      goto LABEL_40;
    }
LABEL_39:
    v23 = Handle;
LABEL_40:
    if ( a4 )
      v44 = *a4;
    v24 = BfspPopulateNewBcdStore(v13, v23, &v44);
    v10 = v24;
    if ( v24 < 0 )
    {
      v25 = L"Failed to populate BCD store. Status = [%x]";
      goto LABEL_38;
    }
    if ( a4 )
      *a4 = v44;
    BfspCleanupDebuggerSettings(v23);
    BfspCleanupHypervisorSettings(v23);
    RecoveryStore = BfspCreateRecoveryStore(v13, a2);
    if ( RecoveryStore < 0 )
      BfspLogMessage(3, L"Failed to create recovery store. Status = [%x]", (unsigned int)RecoveryStore);
    if ( (a2 & 0x4000) != 0 )
    {
      Library = LoadLibraryExW(L"REAGENT.DLL", 0, 0);
      v29 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "WinRePostBCDRepair");
        if ( ProcAddress )
        {
          LastError = 0;
          v31 = v41;
          if ( !((unsigned int (__fastcall *)(void *, __int128 *))ProcAddress)(v41, &v44) )
            LastError = GetLastError();
        }
        else
        {
          v31 = v41;
          LastError = 127;
        }
        FreeLibrary(v29);
      }
      else
      {
        v30 = GetLastError();
        v31 = v41;
        LastError = v30;
      }
      v34 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0xC0070000;
        v34 = LastError < 0;
      }
      if ( v34 )
        BfspLogMessage(3, L"Failed to add WinRE entry. Status = [%x]", (unsigned int)LastError);
      v35 = BfspRestoreHyperVSetting(v23, v31, &v44, a2);
      if ( v35 < 0 )
        BfspLogMessage(3, L"Failed detect Hyper-V setting. Status = [%x]", (unsigned int)v35);
    }
    if ( (a2 & 0x10) != 0 )
    {
      v36 = BcdForciblyUnloadStore(v23);
    }
    else
    {
      v37 = BcdFlushStore(v23);
      if ( v37 < 0 )
        BfspLogMessage(3, L"Failed to flush BCD to disk. Status = [%x]", (unsigned int)v37);
      v36 = BcdCloseStore((__int64)v23);
    }
    v10 = v36;
    v23 = 0;
    if ( v36 >= 0 )
    {
      v24 = BfspFlushSystemPartition();
      if ( v24 )
      {
        v25 = L"Failed to flush system partition. Error = [%x]";
        v26 = 3;
        goto LABEL_71;
      }
    }
    else
    {
      BfspLogMessage(4, L"Failed to close the system store. Status = [%x]", (unsigned int)v36);
    }
LABEL_74:
    if ( v13 )
      BcdCloseStore(v13);
    BfspDestroyGlobalState();
  }
  BfspLogDestroy();
  if ( v10 >= 0 )
    return 1;
  v38 = RtlNtStatusToDosError(v10);
  SetLastError(v38);
  return 0;
}

```

## disassembly

```asm
0x140004080  push    rbp
0x140004082  push    rbx
0x140004083  push    rsi
0x140004084  push    rdi
0x140004085  push    r12
0x140004087  push    r13
0x140004089  push    r14
0x14000408b  push    r15
0x14000408d  lea     rbp, [rsp-198h]
0x140004095  sub     rsp, 298h
0x14000409c  mov     rax, cs:__security_cookie
0x1400040a3  xor     rax, rsp
0x1400040a6  mov     [rbp+1D0h+var_50], rax
0x1400040ad  mov     rbx, [rbp+1D0h+arg_20]
0x1400040b4  xor     r15d, r15d
0x1400040b7  mov     [rsp+2D0h+var_298], rcx
0x1400040bc  xorps   xmm0, xmm0
0x1400040bf  mov     [rsp+2D0h+Handle], r15
0x1400040c4  xorps   xmm1, xmm1
0x1400040c7  mov     [rsp+2D0h+var_290], r15
0x1400040cc  mov     r14, r9
0x1400040cf  mov     r12, r8
0x1400040d2  mov     esi, edx
0x1400040d4  mov     r13, rcx
0x1400040d7  mov     edi, r15d
0x1400040da  movups  xmmword ptr [rsp+2D0h+DestinationString.Length], xmm0
0x1400040df  movups  [rsp+2D0h+var_278], xmm1
0x1400040e4  test    rbx, rbx
0x1400040e7  jz      short loc_14000410A
0x1400040e9  mov     rdi, [rbx+10h]
0x1400040ed  test    rdi, rdi
0x1400040f0  jz      short loc_1400040FB
0x1400040f2  mov     rcx, rdi; pszPath
0x1400040f5  call    cs:__imp_PathRemoveBackslashW
0x1400040fb  mov     rcx, [rbx+8]; pszPath
0x1400040ff  test    rcx, rcx
0x140004102  jz      short loc_14000410A
0x140004104  call    cs:__imp_PathRemoveBackslashW
0x14000410a  mov     eax, esi
0x14000410c  mov     r15d, esi
0x14000410f  shr     r15d, 10h
0x140004113  and     al, 8
0x140004115  not     r15d
0x140004118  and     r15d, 2
0x14000411c  neg     al
0x14000411e  sbb     ecx, ecx
0x140004120  not     ecx
0x140004122  and     ecx, 3
0x140004125  call    BfspLogInitialize
0x14000412a  mov     eax, esi
0x14000412c  lea     rdx, aBfsinitializeb; "BfsInitializeBcdStore flags(0x%08x) Ret"...
0x140004133  and     eax, 2000h
0x140004138  mov     r8d, esi
0x14000413b  neg     eax
0x14000413d  mov     eax, esi
0x14000413f  sbb     ecx, ecx
0x140004141  and     al, 40h
0x140004143  and     ecx, 0Bh
0x140004146  add     ecx, 6Eh ; 'n'
0x140004149  neg     al
0x14000414b  mov     dword ptr [rsp+2D0h+var_2B0], ecx
0x14000414f  mov     ecx, 2
0x140004154  sbb     r9d, r9d
0x140004157  and     r9d, 0Bh
0x14000415b  add     r9d, 6Eh ; 'n'
0x14000415f  call    BfspLogMessage
0x140004164  mov     r9, rbx
0x140004167  mov     r8, r12
0x14000416a  mov     edx, esi
0x14000416c  mov     rcx, r13; Src
0x14000416f  call    BfspInitializeGlobalState
0x140004174  mov     ebx, eax
0x140004176  test    eax, eax
0x140004178  js      loc_14000457A
0x14000417e  lea     rcx, [rsp+2D0h+var_290]
0x140004183  call    BfspOpenTemplateStore
0x140004188  mov     r12, [rsp+2D0h+var_290]
0x14000418d  mov     ebx, eax
0x14000418f  xor     eax, eax
0x140004191  test    ebx, ebx
0x140004193  js      loc_140004568
0x140004199  mov     r13d, esi
0x14000419c  and     r13d, 10h
0x1400041a0  jz      loc_140004267
0x1400041a6  xor     r15d, r15d
0x1400041a9  lea     rcx, aEfiMicrosoftBo_2; "\\EFI\\Microsoft\\Boot\\BCD"
0x1400041b0  cmp     cs:byte_14003F8F8, r15b
0x1400041b7  lea     rax, aBootBcd; "\\boot\\BCD"
0x1400041be  cmovz   rcx, rax
0x1400041c2  test    rdi, rdi
0x1400041c5  jz      short loc_140004204
0x1400041c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400041cb  inc     rax
0x1400041ce  cmp     [rdi+rax*2], r15w
0x1400041d3  jnz     short loc_1400041CB
0x1400041d5  test    rax, rax
0x1400041d8  jz      short loc_140004204
0x1400041da  mov     r9, cs:Src
0x1400041e1  lea     r8, aSSS_0; "%s\\%s%s"
0x1400041e8  mov     [rsp+2D0h+var_2A8], rcx
0x1400041ed  mov     edx, 104h; BufferCount
0x1400041f2  lea     rcx, [rsp+2D0h+Buffer]; Buffer
0x1400041f7  mov     [rsp+2D0h+var_2B0], rdi
0x1400041fc  call    cs:__imp_swprintf_s
0x140004202  jmp     short loc_140004227
0x140004204  mov     r9, cs:Src
0x14000420b  lea     r8, aSS_0; "%s%s"
0x140004212  mov     [rsp+2D0h+var_2B0], rcx
0x140004217  mov     edx, 104h; BufferCount
0x14000421c  lea     rcx, [rsp+2D0h+Buffer]; Buffer
0x140004221  call    cs:__imp_swprintf_s
0x140004227  lea     rdx, [rsp+2D0h+Buffer]; SourceString
0x14000422c  lea     rcx, [rsp+2D0h+DestinationString]; DestinationString
0x140004231  call    cs:__imp_RtlInitUnicodeString
0x140004237  lea     r8, [rsp+2D0h+Buffer]
0x14000423c  mov     ecx, 2
0x140004241  lea     rdx, aOpeningStoreFr; "Opening store from %ws"
0x140004248  lea     rdi, [rsp+2D0h+DestinationString]
0x14000424d  call    BfspLogMessage
0x140004252  lea     r9, [rsp+2D0h+Handle]
0x140004257  xor     edx, edx
0x140004259  lea     rcx, [rsp+2D0h+DestinationString]
0x14000425e  call    BiOpenStoreWithHash
0x140004263  mov     ebx, eax
0x140004265  jmp     short loc_1400042D5
0x140004267  lea     r9, [rsp+2D0h+Handle]
0x14000426c  mov     edx, r15d
0x14000426f  xor     ecx, ecx
0x140004271  mov     rdi, rax
0x140004274  call    BiOpenStoreWithHash
0x140004279  mov     ebx, eax
0x14000427b  test    eax, eax
0x14000427d  js      short loc_1400042D2
0x14000427f  bt      esi, 12h
0x140004283  jb      loc_1400043A6
0x140004289  lea     rdx, aReopeningSyste; "Reopening system store."
0x140004290  mov     ecx, 2
0x140004295  call    BfspLogMessage
0x14000429a  mov     rcx, [rsp+2D0h+Handle]; Handle
0x14000429f  call    BcdForciblyUnloadStore
0x1400042a4  xor     ebx, ebx
0x1400042a6  test    eax, eax
0x1400042a8  jns     short loc_1400042BC
0x1400042aa  mov     r8d, eax
0x1400042ad  lea     rdx, aFailedToForcib; "Failed to forcibly unload the system st"...
0x1400042b4  lea     ecx, [rbx+3]
0x1400042b7  call    BfspLogMessage
0x1400042bc  lea     r9, [rsp+2D0h+Handle]
0x1400042c1  mov     [rsp+2D0h+Handle], rbx
0x1400042c6  mov     edx, r15d
0x1400042c9  xor     ecx, ecx
0x1400042cb  call    BiOpenStoreWithHash
0x1400042d0  mov     ebx, eax
0x1400042d2  xor     r15d, r15d
0x1400042d5  cmp     ebx, 0C0000225h
0x1400042db  jz      short loc_14000433B
0x1400042dd  cmp     ebx, 0C000000Fh
0x1400042e3  jz      short loc_14000433B
0x1400042e5  cmp     ebx, 0C000015Ch
0x1400042eb  jz      short loc_140004309
0x1400042ed  cmp     ebx, 0C000014Ch
0x1400042f3  jz      short loc_140004309
0x1400042f5  test    ebx, ebx
0x1400042f7  jns     loc_1400043A9
0x1400042fd  mov     r8d, ebx
0x140004300  lea     rdx, aBcdopenstoreFa_0; "BcdOpenStore failed with unexpected err"...
0x140004307  jmp     short loc_140004369
0x140004309  mov     ebx, 3
0x14000430e  lea     rdx, aSystemBcdStore; "System BCD store is corrupt."
0x140004315  mov     ecx, ebx
0x140004317  call    BfspLogMessage
0x14000431c  mov     rcx, rdi
0x14000431f  call    BfspBackupCorruptStore
0x140004324  test    eax, eax
0x140004326  jns     short loc_14000434C
0x140004328  mov     r8d, eax
0x14000432b  lea     rdx, aFailedToBackup; "Failed to backup corrupt BCD store. Sta"...
0x140004332  mov     ecx, ebx
0x140004334  call    BfspLogMessage
0x140004339  jmp     short loc_14000434C
0x14000433b  lea     rdx, aSystemBcdStore_0; "System BCD store does not exist, creati"...
0x140004342  mov     ecx, 2
0x140004347  call    BfspLogMessage
0x14000434c  lea     r8, [rsp+2D0h+Handle]
0x140004351  mov     rcx, rdi
0x140004354  call    BcdCreateStoreEx
0x140004359  mov     ebx, eax
0x14000435b  test    eax, eax
0x14000435d  jns     short loc_14000437D
0x14000435f  mov     r8d, eax
0x140004362  lea     rdx, aFailedToCreate_9; "Failed to create a new system store. St"...
0x140004369  mov     ecx, 4
0x14000436e  call    BfspLogMessage
0x140004373  mov     rdi, [rsp+2D0h+Handle]
0x140004378  jmp     loc_14000455B
0x14000437d  test    rdi, rdi
0x140004380  jz      short loc_1400043A9
0x140004382  mov     rdi, [rsp+2D0h+Handle]
0x140004387  mov     rcx, rdi
0x14000438a  call    BcdMarkAsSystemStore
0x14000438f  mov     ebx, eax
0x140004391  test    eax, eax
0x140004393  jns     short loc_1400043AE
0x140004395  lea     rdx, aFailedToMarkSt; "Failed to mark store as system store. S"...
0x14000439c  mov     ecx, 4
0x1400043a1  jmp     loc_140004553
0x1400043a6  xor     r15d, r15d
0x1400043a9  mov     rdi, [rsp+2D0h+Handle]
0x1400043ae  test    r14, r14
0x1400043b1  jz      short loc_1400043BD
0x1400043b3  movups  xmm0, xmmword ptr [r14]
0x1400043b7  movdqu  [rsp+2D0h+var_278], xmm0
0x1400043bd  lea     r8, [rsp+2D0h+var_278]
0x1400043c2  mov     rdx, rdi
0x1400043c5  mov     rcx, r12
0x1400043c8  call    BfspPopulateNewBcdStore
0x1400043cd  mov     ebx, eax
0x1400043cf  test    eax, eax
0x1400043d1  jns     short loc_1400043DC
0x1400043d3  lea     rdx, aFailedToPopula; "Failed to populate BCD store. Status = "...
0x1400043da  jmp     short loc_14000439C
0x1400043dc  test    r14, r14
0x1400043df  jz      short loc_1400043EB
0x1400043e1  movups  xmm0, [rsp+2D0h+var_278]
0x1400043e6  movdqu  xmmword ptr [r14], xmm0
0x1400043eb  mov     rcx, rdi
0x1400043ee  call    BfspCleanupDebuggerSettings
0x1400043f3  mov     rcx, rdi
0x1400043f6  call    BfspCleanupHypervisorSettings
0x1400043fb  mov     edx, esi
0x1400043fd  mov     rcx, r12
0x140004400  call    BfspCreateRecoveryStore
0x140004405  test    eax, eax
0x140004407  jns     short loc_14000441D
0x140004409  mov     r8d, eax
0x14000440c  lea     rdx, aFailedToCreate_6; "Failed to create recovery store. Status"...
0x140004413  mov     ecx, 3
0x140004418  call    BfspLogMessage
0x14000441d  bt      esi, 0Eh
0x140004421  jnb     loc_1400044EB
0x140004427  xor     r8d, r8d; dwFlags
0x14000442a  lea     rcx, aReagentDll; "REAGENT.DLL"
0x140004431  xor     edx, edx; hFile
0x140004433  call    cs:__imp_LoadLibraryExW
0x140004439  mov     r14, rax
0x14000443c  test    rax, rax
0x14000443f  jnz     short loc_140004450
0x140004441  call    cs:__imp_GetLastError
0x140004447  mov     r15, [rsp+2D0h+var_298]
0x14000444c  mov     ebx, eax
0x14000444e  jmp     short loc_140004499
0x140004450  lea     rdx, aWinrepostbcdre; "WinRePostBCDRepair"
0x140004457  mov     rcx, r14; hModule
0x14000445a  call    cs:__imp_GetProcAddress
0x140004460  test    rax, rax
0x140004463  jnz     short loc_14000446F
0x140004465  mov     r15, [rsp+2D0h+var_298]
0x14000446a  lea     ebx, [rax+7Fh]
0x14000446d  jmp     short loc_140004490
0x14000446f  mov     ebx, r15d
0x140004472  lea     rdx, [rsp+2D0h+var_278]
0x140004477  mov     r15, [rsp+2D0h+var_298]
0x14000447c  mov     rcx, r15
0x14000447f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004484  test    eax, eax
0x140004486  jnz     short loc_140004490
0x140004488  call    cs:__imp_GetLastError
0x14000448e  mov     ebx, eax
0x140004490  mov     rcx, r14; hLibModule
0x140004493  call    cs:__imp_FreeLibrary
0x140004499  test    ebx, ebx
0x14000449b  jle     short loc_1400044A8
0x14000449d  movzx   ebx, bx
0x1400044a0  or      ebx, 0C0070000h
0x1400044a6  test    ebx, ebx
0x1400044a8  jns     short loc_1400044BE
0x1400044aa  mov     r8d, ebx
0x1400044ad  lea     rdx, aFailedToAddWin; "Failed to add WinRE entry. Status = [%x"...
0x1400044b4  mov     ecx, 3
0x1400044b9  call    BfspLogMessage
0x1400044be  mov     r9d, esi
0x1400044c1  lea     r8, [rsp+2D0h+var_278]
0x1400044c6  mov     rdx, r15
0x1400044c9  mov     rcx, rdi
0x1400044cc  call    BfspRestoreHyperVSetting
0x1400044d1  xor     r15d, r15d
0x1400044d4  test    eax, eax
0x1400044d6  jns     short loc_1400044EB
0x1400044d8  mov     r8d, eax
0x1400044db  lea     rdx, aFailedDetectHy; "Failed detect Hyper-V setting. Status ="...
0x1400044e2  lea     ecx, [r15+3]
0x1400044e6  call    BfspLogMessage
0x1400044eb  mov     rcx, rdi; Handle
0x1400044ee  test    r13d, r13d
0x1400044f1  jz      short loc_1400044FA
0x1400044f3  call    BcdForciblyUnloadStore
0x1400044f8  jmp     short loc_14000451F
0x1400044fa  call    BcdFlushStore
0x1400044ff  test    eax, eax
0x140004501  jns     short loc_140004517
  ... truncated ...
```
