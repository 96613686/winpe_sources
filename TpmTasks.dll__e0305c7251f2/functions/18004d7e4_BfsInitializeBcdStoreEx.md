# BfsInitializeBcdStoreEx

- ea: `0x18004d7e4`
- end: `0x18004dc08`
- name: `BfsInitializeBcdStoreEx`
- size: `1060`
- prototype: `__int64 __fastcall(void *Src, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180048c3c`

## callees

- `0x1800078b0`
- `0x180008724`
- `0x1800466ec`
- `0x18004ccf0`
- `0x18004cd48`
- `0x18004cdd4`
- `0x18004d7e4`
- `0x18004ddb4`
- `0x18004df58`
- `0x18004e30c`
- `0x18004f08c`
- `0x18004f620`
- `0x18004f970`
- `0x180050344`
- `0x180050410`
- `0x1800526c4`
- `0x1800528a8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18004d917`
- `ntdll!RtlInitUnicodeString` at `0x18004d917`
- `ntdll!RtlNtStatusToDosError` at `0x18004dbc7`
- `ntdll!RtlNtStatusToDosError` at `0x18004dbc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004dbcf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004dbcf`
- `bcd!BcdFlushStore` at `0x18004db37`
- `bcd!BcdFlushStore` at `0x18004db37`
- `bcd!BcdOpenStoreFromFile` at `0x18004d942`
- `bcd!BcdOpenStoreFromFile` at `0x18004d942`
- `bcd!BcdMarkAsSystemStore` at `0x18004da61`
- `bcd!BcdMarkAsSystemStore` at `0x18004da61`
- `bcd!BcdCloseStore` at `0x18004db57`
- `bcd!BcdCloseStore` at `0x18004db9c`
- `bcd!BcdCloseStore` at `0x18004dbac`
- `bcd!BcdCloseStore` at `0x18004db57`
- `bcd!BcdCloseStore` at `0x18004db9c`
- `bcd!BcdCloseStore` at `0x18004dbac`
- `bcd!BcdCreateStore` at `0x18004da3a`
- `bcd!BcdCreateStore` at `0x18004da3a`
- `bcd!BcdOpenStore` at `0x18004d956`
- `bcd!BcdOpenStore` at `0x18004d9ab`
- `bcd!BcdOpenStore` at `0x18004d956`
- `bcd!BcdOpenStore` at `0x18004d9ab`
- `bcd!BcdForciblyUnloadStore` at `0x18004d980`
- `bcd!BcdForciblyUnloadStore` at `0x18004db2f`
- `bcd!BcdForciblyUnloadStore` at `0x18004d980`
- `bcd!BcdForciblyUnloadStore` at `0x18004db2f`

## string_xrefs

- `0x18004d96c`: `Reopening system store.`
- `0x18004d927`: `Opening store from %ws`
- `0x18004da46`: `Failed to create a new system store. Status = [%x]`
- `0x18004dac5`: `Failed to create recovery store. Status = [%x]`
- `0x18004d9db`: `BcdOpenStore failed with unexpected error code, Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfsInitializeBcdStoreEx(void *Src, unsigned int a2)
{
  unsigned int v3; // r15d
  char v5; // r13
  NTSTATUS v6; // ebx
  const wchar_t *v7; // rax
  struct _UNICODE_STRING *p_DestinationString; // rdi
  NTSTATUS v9; // eax
  int v10; // eax
  const wchar_t *v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  int RecoveryStore; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  ULONG v21; // eax
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v26; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  v23 = 0;
  v24 = 0;
  v3 = ~BYTE2(a2) & 2;
  DestinationString = 0;
  v26 = 0;
  BfspLogInitialize((a2 & 8) == 0 ? 3 : 0);
  BfspLogMessage(
    2,
    L"BfsInitializeBcdStore flags(0x%08x) RetainElementData:%c DelExistinObject:%c",
    a2,
    (a2 & 0x40) != 0 ? 121 : 110,
    (a2 & 0x2000) != 0 ? 121 : 110);
  v5 = 0;
  v6 = BfspInitializeGlobalState(Src);
  if ( v6 >= 0 )
  {
    v5 = 1;
    v6 = BfspOpenTemplateStore(&v24);
    if ( v6 >= 0 )
    {
      if ( (a2 & 0x10) != 0 )
      {
        v7 = L"\\EFI\\Microsoft\\Boot\\BCD";
        if ( !byte_1800A4538 )
          v7 = L"\\boot\\BCD";
        swprintf_s(Buffer, 0x104u, L"%s%s", ::Src, v7);
        RtlInitUnicodeString(&DestinationString, Buffer);
        p_DestinationString = &DestinationString;
        BfspLogMessage(2, L"Opening store from %ws", Buffer);
        v9 = BcdOpenStoreFromFile(&DestinationString, &v23);
      }
      else
      {
        p_DestinationString = 0;
        v6 = BcdOpenStore(0, v3, &v23);
        if ( v6 < 0 )
          goto LABEL_13;
        if ( (a2 & 0x40000) != 0 )
          goto LABEL_29;
        BfspLogMessage(2, L"Reopening system store.");
        v10 = BcdForciblyUnloadStore(v23);
        if ( v10 < 0 )
          BfspLogMessage(3, L"Failed to forcibly unload the system store. Status = [%x]", (unsigned int)v10);
        v23 = 0;
        v9 = BcdOpenStore(0, v3, &v23);
      }
      v6 = v9;
LABEL_13:
      if ( v6 == -1073741275 || v6 == -1073741809 )
      {
        BfspLogMessage(2, L"System BCD store does not exist, creating.");
      }
      else
      {
        if ( v6 != -1073741476 && v6 != -1073741492 )
        {
          if ( v6 < 0 )
          {
            v11 = L"BcdOpenStore failed with unexpected error code, Status = [%x]";
LABEL_19:
            v12 = (unsigned int)v6;
            v13 = 4;
LABEL_48:
            BfspLogMessage(v13, v11, v12);
            goto LABEL_49;
          }
          goto LABEL_29;
        }
        BfspLogMessage(3, L"System BCD store is corrupt.");
        v14 = BfspBackupCorruptStore(p_DestinationString);
        if ( v14 < 0 )
          BfspLogMessage(3, L"Failed to backup corrupt BCD store. Status = [%x]", (unsigned int)v14);
      }
      v15 = BcdCreateStore(p_DestinationString, &v23);
      v6 = v15;
      if ( v15 < 0 )
      {
        v11 = L"Failed to create a new system store. Status = [%x]";
        goto LABEL_25;
      }
      if ( p_DestinationString )
      {
        v15 = BcdMarkAsSystemStore(v23);
        v6 = v15;
        if ( v15 < 0 )
        {
          v11 = L"Failed to mark store as system store. Status = [%x]";
          goto LABEL_25;
        }
      }
LABEL_29:
      v15 = BfspPopulateNewBcdStore(v24, v23, &v26);
      v6 = v15;
      if ( v15 >= 0 )
      {
        BfspCleanupDebuggerSettings(v23);
        BfspCleanupHypervisorSettings(v23);
        RecoveryStore = BfspCreateRecoveryStore(v24, a2);
        if ( RecoveryStore < 0 )
          BfspLogMessage(3, L"Failed to create recovery store. Status = [%x]", (unsigned int)RecoveryStore);
        if ( (a2 & 0x4000) != 0 )
        {
          v17 = BfspRestoreWinreObject(Src, &v26);
          if ( v17 < 0 )
            BfspLogMessage(3, L"Failed to add WinRE entry. Status = [%x]", (unsigned int)v17);
          v18 = BfspRestoreHyperVSetting(v23, Src, &v26, a2);
          if ( v18 < 0 )
            BfspLogMessage(3, L"Failed detect Hyper-V setting. Status = [%x]", (unsigned int)v18);
        }
        if ( (a2 & 0x10) != 0 )
        {
          v19 = BcdForciblyUnloadStore(v23);
        }
        else
        {
          v20 = BcdFlushStore(v23);
          if ( v20 < 0 )
            BfspLogMessage(3, L"Failed to flush BCD to disk. Status = [%x]", (unsigned int)v20);
          v19 = BcdCloseStore(v23);
        }
        v23 = 0;
        v6 = v19;
        if ( v19 < 0 )
        {
          v11 = L"Failed to close the system store. Status = [%x]";
          goto LABEL_19;
        }
        v15 = BfspFlushSystemPartition();
        if ( !v15 )
          goto LABEL_49;
        v11 = L"Failed to flush system partition. Error = [%x]";
        v13 = 3;
LABEL_47:
        v12 = (unsigned int)v15;
        goto LABEL_48;
      }
      v11 = L"Failed to populate BCD store. Status = [%x]";
LABEL_25:
      v13 = 4;
      goto LABEL_47;
    }
  }
LABEL_49:
  if ( v23 )
    BcdCloseStore(v23);
  if ( v24 )
    BcdCloseStore(v24);
  if ( v5 )
    BfspDestroyGlobalState();
  BfspLogDestroy();
  if ( v6 >= 0 )
    return 1;
  v21 = RtlNtStatusToDosError(v6);
  SetLastError(v21);
  return 0;
}

```

## disassembly

```asm
0x18004d7e4  mov     [rsp-8+arg_10], rbx
0x18004d7e9  push    rbp
0x18004d7ea  push    rsi
0x18004d7eb  push    rdi
0x18004d7ec  push    r12
0x18004d7ee  push    r13
0x18004d7f0  push    r14
0x18004d7f2  push    r15
0x18004d7f4  lea     rbp, [rsp-180h]
0x18004d7fc  sub     rsp, 280h
0x18004d803  mov     rax, cs:__security_cookie
0x18004d80a  xor     rax, rsp
0x18004d80d  mov     [rbp+1B0h+var_40], rax
0x18004d814  mov     r12, rcx
0x18004d817  mov     [rsp+2B0h+var_280], 0
0x18004d820  mov     r15d, edx
0x18004d823  mov     [rsp+2B0h+var_278], 0
0x18004d82c  shr     r15d, 10h
0x18004d830  mov     eax, edx
0x18004d832  and     al, 8
0x18004d834  xorps   xmm0, xmm0
0x18004d837  xorps   xmm1, xmm1
0x18004d83a  not     r15d
0x18004d83d  and     r15d, 2
0x18004d841  mov     esi, edx
0x18004d843  neg     al
0x18004d845  movups  xmmword ptr [rsp+2B0h+DestinationString.Length], xmm0
0x18004d84a  sbb     ecx, ecx
0x18004d84c  not     ecx
0x18004d84e  and     ecx, 3
0x18004d851  movups  [rsp+2B0h+var_260], xmm1
0x18004d856  call    BfspLogInitialize
0x18004d85b  mov     eax, esi
0x18004d85d  lea     rdx, aBfsinitializeb; "BfsInitializeBcdStore flags(0x%08x) Ret"...
0x18004d864  and     eax, 2000h
0x18004d869  mov     r8d, esi
0x18004d86c  neg     eax
0x18004d86e  mov     eax, esi
0x18004d870  sbb     ecx, ecx
0x18004d872  and     al, 40h
0x18004d874  and     ecx, 0Bh
0x18004d877  add     ecx, 6Eh ; 'n'
0x18004d87a  neg     al
0x18004d87c  mov     dword ptr [rsp+2B0h+var_290], ecx
0x18004d880  mov     ecx, 2
0x18004d885  sbb     r9d, r9d
0x18004d888  and     r9d, 0Bh
0x18004d88c  add     r9d, 6Eh ; 'n'
0x18004d890  call    BfspLogMessage
0x18004d895  xor     r9d, r9d
0x18004d898  xor     r8d, r8d
0x18004d89b  mov     edx, esi
0x18004d89d  mov     rcx, r12; Src
0x18004d8a0  xor     r13b, r13b
0x18004d8a3  call    BfspInitializeGlobalState
0x18004d8a8  mov     ebx, eax
0x18004d8aa  test    eax, eax
0x18004d8ac  js      loc_18004DB92
0x18004d8b2  lea     rcx, [rsp+2B0h+var_278]
0x18004d8b7  mov     r13b, 1
0x18004d8ba  call    BfspOpenTemplateStore
0x18004d8bf  mov     ebx, eax
0x18004d8c1  test    eax, eax
0x18004d8c3  js      loc_18004DB92
0x18004d8c9  mov     r14d, esi
0x18004d8cc  and     r14d, 10h
0x18004d8d0  jz      short loc_18004D94A
0x18004d8d2  cmp     cs:byte_1800A4538, 0
0x18004d8d9  lea     rcx, aBootBcd; "\\boot\\BCD"
0x18004d8e0  mov     r9, cs:Src
0x18004d8e7  lea     rax, aEfiMicrosoftBo_2; "\\EFI\\Microsoft\\Boot\\BCD"
0x18004d8ee  cmovz   rax, rcx
0x18004d8f2  lea     r8, aSS_0; "%s%s"
0x18004d8f9  lea     rcx, [rsp+2B0h+Buffer]; Buffer
0x18004d8fe  mov     [rsp+2B0h+var_290], rax
0x18004d903  mov     edx, 104h; BufferCount
0x18004d908  call    swprintf_s
0x18004d90d  lea     rdx, [rsp+2B0h+Buffer]; SourceString
0x18004d912  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x18004d917  call    cs:__imp_RtlInitUnicodeString
0x18004d91d  lea     r8, [rsp+2B0h+Buffer]
0x18004d922  mov     ecx, 2
0x18004d927  lea     rdx, aOpeningStoreFr; "Opening store from %ws"
0x18004d92e  lea     rdi, [rsp+2B0h+DestinationString]
0x18004d933  call    BfspLogMessage
0x18004d938  lea     rdx, [rsp+2B0h+var_280]
0x18004d93d  lea     rcx, [rsp+2B0h+DestinationString]
0x18004d942  call    cs:__imp_BcdOpenStoreFromFile
0x18004d948  jmp     short loc_18004D9B1
0x18004d94a  lea     r8, [rsp+2B0h+var_280]
0x18004d94f  mov     edx, r15d
0x18004d952  xor     ecx, ecx
0x18004d954  xor     edi, edi
0x18004d956  call    cs:__imp_BcdOpenStore
0x18004d95c  mov     ebx, eax
0x18004d95e  test    eax, eax
0x18004d960  js      short loc_18004D9B3
0x18004d962  bt      esi, 12h
0x18004d966  jb      loc_18004DA76
0x18004d96c  lea     rdx, aReopeningSyste; "Reopening system store."
0x18004d973  lea     ecx, [rdi+2]
0x18004d976  call    BfspLogMessage
0x18004d97b  mov     rcx, [rsp+2B0h+var_280]
0x18004d980  call    cs:__imp_BcdForciblyUnloadStore
0x18004d986  test    eax, eax
0x18004d988  jns     short loc_18004D99C
0x18004d98a  mov     r8d, eax
0x18004d98d  lea     rdx, aFailedToForcib; "Failed to forcibly unload the system st"...
0x18004d994  lea     ecx, [rdi+3]
0x18004d997  call    BfspLogMessage
0x18004d99c  lea     r8, [rsp+2B0h+var_280]
0x18004d9a1  mov     [rsp+2B0h+var_280], rdi
0x18004d9a6  mov     edx, r15d
0x18004d9a9  xor     ecx, ecx
0x18004d9ab  call    cs:__imp_BcdOpenStore
0x18004d9b1  mov     ebx, eax
0x18004d9b3  cmp     ebx, 0C0000225h
0x18004d9b9  jz      short loc_18004DA21
0x18004d9bb  cmp     ebx, 0C000000Fh
0x18004d9c1  jz      short loc_18004DA21
0x18004d9c3  cmp     ebx, 0C000015Ch
0x18004d9c9  jz      short loc_18004D9EF
0x18004d9cb  cmp     ebx, 0C000014Ch
0x18004d9d1  jz      short loc_18004D9EF
0x18004d9d3  test    ebx, ebx
0x18004d9d5  jns     loc_18004DA76
0x18004d9db  lea     rdx, aBcdopenstoreFa; "BcdOpenStore failed with unexpected err"...
0x18004d9e2  mov     r8d, ebx
0x18004d9e5  mov     ecx, 4
0x18004d9ea  jmp     loc_18004DB8D
0x18004d9ef  mov     ebx, 3
0x18004d9f4  lea     rdx, aSystemBcdStore; "System BCD store is corrupt."
0x18004d9fb  mov     ecx, ebx
0x18004d9fd  call    BfspLogMessage
0x18004da02  mov     rcx, rdi
0x18004da05  call    BfspBackupCorruptStore
0x18004da0a  test    eax, eax
0x18004da0c  jns     short loc_18004DA32
0x18004da0e  mov     r8d, eax
0x18004da11  lea     rdx, aFailedToBackup; "Failed to backup corrupt BCD store. Sta"...
0x18004da18  mov     ecx, ebx
0x18004da1a  call    BfspLogMessage
0x18004da1f  jmp     short loc_18004DA32
0x18004da21  lea     rdx, aSystemBcdStore_0; "System BCD store does not exist, creati"...
0x18004da28  mov     ecx, 2
0x18004da2d  call    BfspLogMessage
0x18004da32  lea     rdx, [rsp+2B0h+var_280]
0x18004da37  mov     rcx, rdi
0x18004da3a  call    cs:__imp_BcdCreateStore
0x18004da40  mov     ebx, eax
0x18004da42  test    eax, eax
0x18004da44  jns     short loc_18004DA57
0x18004da46  lea     rdx, aFailedToCreate_6; "Failed to create a new system store. St"...
0x18004da4d  mov     ecx, 4
0x18004da52  jmp     loc_18004DB8A
0x18004da57  test    rdi, rdi
0x18004da5a  jz      short loc_18004DA76
0x18004da5c  mov     rcx, [rsp+2B0h+var_280]
0x18004da61  call    cs:__imp_BcdMarkAsSystemStore
0x18004da67  mov     ebx, eax
0x18004da69  test    eax, eax
0x18004da6b  jns     short loc_18004DA76
0x18004da6d  lea     rdx, aFailedToMarkSt; "Failed to mark store as system store. S"...
0x18004da74  jmp     short loc_18004DA4D
0x18004da76  mov     rdx, [rsp+2B0h+var_280]
0x18004da7b  lea     r8, [rsp+2B0h+var_260]
0x18004da80  mov     rcx, [rsp+2B0h+var_278]
0x18004da85  call    BfspPopulateNewBcdStore
0x18004da8a  mov     ebx, eax
0x18004da8c  test    eax, eax
0x18004da8e  jns     short loc_18004DA99
0x18004da90  lea     rdx, aFailedToPopula; "Failed to populate BCD store. Status = "...
0x18004da97  jmp     short loc_18004DA4D
0x18004da99  mov     rcx, [rsp+2B0h+var_280]
0x18004da9e  call    BfspCleanupDebuggerSettings
0x18004daa3  mov     rcx, [rsp+2B0h+var_280]
0x18004daa8  call    BfspCleanupHypervisorSettings
0x18004daad  mov     rcx, [rsp+2B0h+var_278]
0x18004dab2  mov     edx, esi
0x18004dab4  call    BfspCreateRecoveryStore
0x18004dab9  mov     edi, 3
0x18004dabe  test    eax, eax
0x18004dac0  jns     short loc_18004DAD3
0x18004dac2  mov     r8d, eax
0x18004dac5  lea     rdx, aFailedToCreate_4; "Failed to create recovery store. Status"...
0x18004dacc  mov     ecx, edi
0x18004dace  call    BfspLogMessage
0x18004dad3  bt      esi, 0Eh
0x18004dad7  jnb     short loc_18004DB25
0x18004dad9  lea     rdx, [rsp+2B0h+var_260]
0x18004dade  mov     rcx, r12
0x18004dae1  call    BfspRestoreWinreObject
0x18004dae6  test    eax, eax
0x18004dae8  jns     short loc_18004DAFB
0x18004daea  mov     r8d, eax
0x18004daed  lea     rdx, aFailedToAddWin; "Failed to add WinRE entry. Status = [%x"...
0x18004daf4  mov     ecx, edi
0x18004daf6  call    BfspLogMessage
0x18004dafb  mov     rcx, [rsp+2B0h+var_280]
0x18004db00  lea     r8, [rsp+2B0h+var_260]
0x18004db05  mov     r9d, esi
0x18004db08  mov     rdx, r12
0x18004db0b  call    BfspRestoreHyperVSetting
0x18004db10  test    eax, eax
0x18004db12  jns     short loc_18004DB25
0x18004db14  mov     r8d, eax
0x18004db17  lea     rdx, aFailedDetectHy; "Failed detect Hyper-V setting. Status ="...
0x18004db1e  mov     ecx, edi
0x18004db20  call    BfspLogMessage
0x18004db25  mov     rcx, [rsp+2B0h+var_280]
0x18004db2a  test    r14d, r14d
0x18004db2d  jz      short loc_18004DB37
0x18004db2f  call    cs:__imp_BcdForciblyUnloadStore
0x18004db35  jmp     short loc_18004DB5D
0x18004db37  call    cs:__imp_BcdFlushStore
0x18004db3d  test    eax, eax
0x18004db3f  jns     short loc_18004DB52
0x18004db41  mov     r8d, eax
0x18004db44  lea     rdx, aFailedToFlushB; "Failed to flush BCD to disk. Status = ["...
0x18004db4b  mov     ecx, edi
0x18004db4d  call    BfspLogMessage
0x18004db52  mov     rcx, [rsp+2B0h+var_280]
0x18004db57  call    cs:__imp_BcdCloseStore
0x18004db5d  mov     [rsp+2B0h+var_280], 0
0x18004db66  mov     ebx, eax
0x18004db68  test    eax, eax
0x18004db6a  jns     short loc_18004DB78
0x18004db6c  lea     rdx, aFailedToCloseT; "Failed to close the system store. Statu"...
0x18004db73  jmp     loc_18004D9E2
0x18004db78  call    BfspFlushSystemPartition
0x18004db7d  test    eax, eax
0x18004db7f  jz      short loc_18004DB92
0x18004db81  lea     rdx, aFailedToFlushS; "Failed to flush system partition. Error"...
0x18004db88  mov     ecx, edi
0x18004db8a  mov     r8d, eax
0x18004db8d  call    BfspLogMessage
0x18004db92  mov     rcx, [rsp+2B0h+var_280]
0x18004db97  test    rcx, rcx
0x18004db9a  jz      short loc_18004DBA2
0x18004db9c  call    cs:__imp_BcdCloseStore
0x18004dba2  mov     rcx, [rsp+2B0h+var_278]
0x18004dba7  test    rcx, rcx
0x18004dbaa  jz      short loc_18004DBB2
0x18004dbac  call    cs:__imp_BcdCloseStore
0x18004dbb2  test    r13b, r13b
0x18004dbb5  jz      short loc_18004DBBC
0x18004dbb7  call    BfspDestroyGlobalState
0x18004dbbc  call    BfspLogDestroy
0x18004dbc1  test    ebx, ebx
0x18004dbc3  jns     short loc_18004DBD9
0x18004dbc5  mov     ecx, ebx; Status
0x18004dbc7  call    cs:__imp_RtlNtStatusToDosError
0x18004dbcd  mov     ecx, eax; dwErrCode
0x18004dbcf  call    cs:__imp_SetLastError
0x18004dbd5  xor     eax, eax
0x18004dbd7  jmp     short loc_18004DBDE
0x18004dbd9  mov     eax, 1
0x18004dbde  mov     rcx, [rbp+1B0h+var_40]
0x18004dbe5  xor     rcx, rsp; StackCookie
0x18004dbe8  call    __security_check_cookie
0x18004dbed  mov     rbx, [rsp+2B0h+arg_10]
0x18004dbf5  add     rsp, 280h
0x18004dbfc  pop     r15
0x18004dbfe  pop     r14
0x18004dc00  pop     r13
0x18004dc02  pop     r12
0x18004dc04  pop     rdi
0x18004dc05  pop     rsi
0x18004dc06  pop     rbp
0x18004dc07  retn
```
