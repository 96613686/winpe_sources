# DriverStoreNotifyCallback

- ea: `0x140013220`
- end: `0x140013750`
- name: `DriverStoreNotifyCallback`
- size: `1328`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140001fc0`
- `0x14000bcbc`
- `0x140012c2c`
- `0x140013140`
- `0x140013220`
- `0x1400138b0`
- `0x140013ccc`
- `0x1400143b8`
- `0x1400146e0`
- `0x1400147d4`
- `0x140014d40`
- `0x140014e08`
- `0x1400210c0`
- `0x140022e1c`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400135f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400135f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400134d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001352b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400134d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001352b`
- `DEVRTL!DevRtlWriteTextLog` at `0x140013350`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001338b`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400134b5`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400134f8`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001354d`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001356d`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400135d5`
- `DEVRTL!DevRtlWriteTextLog` at `0x140013646`
- `DEVRTL!DevRtlWriteTextLog` at `0x140013680`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001370f`
- `DEVRTL!DevRtlWriteTextLog` at `0x140013350`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001338b`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400134b5`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400134f8`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001354d`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001356d`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400135d5`
- `DEVRTL!DevRtlWriteTextLog` at `0x140013646`
- `DEVRTL!DevRtlWriteTextLog` at `0x140013680`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001370f`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14001325e`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14001325e`
- `ext-ms-win-drvinst-desktop-l1-1-0!SetDriverPackageRestorePoint` at `0x1400135a9`
- `ext-ms-win-drvinst-desktop-l1-1-0!SetDriverPackageRestorePoint` at `0x140013664`
- `ext-ms-win-drvinst-desktop-l1-1-0!SetDriverPackageRestorePoint` at `0x1400135a9`
- `ext-ms-win-drvinst-desktop-l1-1-0!SetDriverPackageRestorePoint` at `0x140013664`
- `drvstore!DriverPackageClose` at `0x1400133b7`
- `drvstore!DriverPackageClose` at `0x140013576`
- `drvstore!DriverPackageClose` at `0x1400133b7`
- `drvstore!DriverPackageClose` at `0x140013576`
- `drvstore!DriverPackageOpenW` at `0x140013322`
- `drvstore!DriverPackageOpenW` at `0x140013487`
- `drvstore!DriverPackageOpenW` at `0x140013322`
- `drvstore!DriverPackageOpenW` at `0x140013487`

## string_xrefs

- `0x14001349f`: `Unable to open driver package '%ws' for import completion. Error = 0x%08X`
- `0x1400135b1`: `System restore point was set earlier, but implementation cannot be found to commit.`
- `0x14001333a`: `Unable to open driver package '%ws' for deletion. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall DriverStoreNotifyCallback(int a1, __int64 a2, __int64 a3)
{
  void *v4; // rbp
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 ThreadLogToken; // r14
  int v12; // edi
  int v13; // edi
  int v14; // edi
  int v15; // edi
  const wchar_t *FileTitle; // rax
  _QWORD *v17; // rsi
  __int64 v18; // rax
  __int64 v19; // rdi
  const wchar_t *v20; // rax
  unsigned int v21; // edi
  __int64 v22; // rax
  __int64 v23; // rdi
  int DriverPackageRootDevices; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  int v29; // eax
  __int64 v31; // [rsp+28h] [rbp-280h]
  DWORD v32; // [rsp+28h] [rbp-280h]
  DWORD LastError; // [rsp+28h] [rbp-280h]
  DWORD v34; // [rsp+28h] [rbp-280h]
  DWORD v35; // [rsp+28h] [rbp-280h]
  _QWORD v36[2]; // [rsp+50h] [rbp-258h] BYREF
  _WORD v37[264]; // [rsp+60h] [rbp-248h] BYREF

  v4 = 0;
  v36[0] = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  if ( !a2 || !a3 )
    return 87;
  v12 = a1 - 1;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( !v15 )
        {
          v18 = DriverPackageOpenW(a2, *(unsigned __int16 *)(a2 + 520), 0, 1, 0);
          v19 = v18;
          if ( v18 )
          {
            if ( (unsigned int)GetDriverPackageRootDevices(v18, v36) )
            {
              v4 = (void *)v36[0];
              if ( v36[0] )
              {
                UnconfigureRootDevices(a2, v36[0]);
                *(_QWORD *)(a3 + 40) = v4;
                v4 = 0;
              }
            }
            else
            {
              LastError = GetLastError();
              DevRtlWriteTextLog(
                ThreadLogToken,
                1,
                2,
                "Unable to get root devices from driver package '%ws'. Error = 0x%08X",
                a2,
                LastError);
              v4 = (void *)v36[0];
            }
            DriverPackageClose(v19);
          }
          else
          {
            v32 = GetLastError();
            DevRtlWriteTextLog(
              ThreadLogToken,
              1,
              2,
              "Unable to open driver package '%ws' for deletion. Error = 0x%08X",
              a2,
              v32);
          }
          if ( !(unsigned int)GetDriverPackageSystemPath(*(_QWORD *)(a3 + 32), a2, a3 + 48) )
            *(_WORD *)(a3 + 48) = 0;
          goto LABEL_48;
        }
        if ( v15 == 1 )
        {
          if ( *(_DWORD *)(a2 + 1580) )
          {
            v17 = (_QWORD *)(a3 + 40);
            if ( *v17 )
              ConfigureRootDevices(a2, *v17);
          }
          else
          {
            if ( *(_WORD *)(a2 + 1056) )
            {
              FileTitle = (const wchar_t *)pSetupGetFileTitle(a2 + 1056);
              UnpublishDriverPackageCatalog(FileTitle);
            }
            v17 = (_QWORD *)(a3 + 40);
          }
          if ( *v17 )
          {
            v4 = (void *)*v17;
            *v17 = 0;
          }
          goto LABEL_48;
        }
        return 87;
      }
      if ( *(_DWORD *)(a2 + 1580) )
      {
LABEL_42:
        if ( (*(_BYTE *)(a2 + 524) & 4) != 0 || !*(_QWORD *)(a3 + 24) )
        {
          DevRtlWriteTextLog(ThreadLogToken, 128, 5, "No system restore point was set earlier.");
        }
        else if ( (unsigned __int8)IsSetDriverPackageRestorePointPresent(v8, v7, v9, v10) )
        {
          SetDriverPackageRestorePoint(a2, a3 + 24, *(_DWORD *)(a2 + 1580) == 0);
        }
        else
        {
          DevRtlWriteTextLog(
            ThreadLogToken,
            128,
            2,
            "System restore point was set earlier, but implementation cannot be found to commit.");
        }
LABEL_48:
        v21 = 0;
        if ( v4 )
          HeapFree(hHeap, 0, v4);
        return v21;
      }
      FlushDriverPackageFiles((LPCWSTR)a2, (LPCWSTR)(a2 + 1056), (LPCWSTR)(a2 + 528), *(LPCWSTR *)(a2 + 1048));
      if ( !*(_WORD *)(a2 + 1056) || !*(_WORD *)(a2 + 528) )
        goto LABEL_31;
      if ( !(unsigned int)GetDriverPackageSystemPath(*(_QWORD *)(a3 + 32), a2, v37) )
        v37[0] = 0;
      v20 = (const wchar_t *)pSetupGetFileTitle(a2 + 1056);
      v21 = PublishDriverPackageCatalog(v20);
      if ( !v21 )
      {
LABEL_31:
        v22 = DriverPackageOpenW(a2, *(unsigned __int16 *)(a2 + 520), 0, 1, 0);
        v23 = v22;
        if ( v22 )
        {
          DriverPackageRootDevices = GetDriverPackageRootDevices(v22, v36);
          v4 = (void *)v36[0];
          if ( DriverPackageRootDevices )
          {
            if ( v36[0] )
              ConfigureRootDevices(a2, v36[0]);
          }
          else
          {
            v35 = GetLastError();
            DevRtlWriteTextLog(
              ThreadLogToken,
              1,
              2,
              "Unable to get root devices from driver package '%ws'. Error = 0x%08X",
              a2,
              v35);
          }
          if ( !(unsigned int)DriverPackageSupportsNativeArchitecture(v23, ThreadLogToken) )
          {
            if ( (unsigned int)SendNativeArchitectureUnsupportedEvent((unsigned __int16 *)a2) )
            {
              DevRtlWriteTextLog(
                ThreadLogToken,
                1,
                5,
                "Sent native architecture unsupported event for driver package '%ws'.",
                a2);
            }
            else
            {
              LODWORD(v31) = GetLastError();
              DevRtlWriteTextLog(
                ThreadLogToken,
                1,
                2,
                "Unable to send native architecture unsupported event for driver package '%ws'. Error = 0x%08X",
                a2,
                v31);
            }
          }
          DriverPackageClose(v23);
        }
        else
        {
          v34 = GetLastError();
          DevRtlWriteTextLog(
            ThreadLogToken,
            1,
            2,
            "Unable to open driver package '%ws' for import completion. Error = 0x%08X",
            a2,
            v34);
        }
        goto LABEL_42;
      }
    }
    else
    {
      if ( (*(_BYTE *)(a2 + 524) & 4) != 0 )
      {
        DevRtlWriteTextLog(ThreadLogToken, 128, 5, "System restore point not required.");
      }
      else if ( (*(_DWORD *)(a3 + 16) & 0xF0000000) != 0 )
      {
        if ( (unsigned int)PnpPolIsSystemRestoreDisabled() )
        {
          DevRtlWriteTextLog(ThreadLogToken, 128, 5, "System restore disabled by policy. Error = 0x%08X", 1260);
        }
        else if ( (unsigned __int8)IsSetDriverPackageRestorePointPresent(v26, v25, v27, v28) )
        {
          *(_QWORD *)(a3 + 24) = 0;
          SetDriverPackageRestorePoint(a2, a3 + 24, 0);
        }
        else
        {
          DevRtlWriteTextLog(ThreadLogToken, 128, 5, "System restore implementation not present.");
        }
      }
      else
      {
        DevRtlWriteTextLog(ThreadLogToken, 128, 5, "System restore not required for signed driver package.");
      }
      return 0;
    }
  }
  else
  {
    v29 = ValidateDriverPackage(
            (unsigned __int16 *)a2,
            *(_WORD *)(a2 + 520),
            (WCHAR *)(a2 + 528),
            *(const WCHAR **)(a2 + 1048),
            *(_QWORD *)a3,
            *(_QWORD *)(a3 + 8),
            (*(_DWORD *)(a2 + 524) >> 3) & 1,
            *(_DWORD *)(a2 + 1576),
            (unsigned __int16 *)(a2 + 1584),
            (_DWORD *)(a2 + 2104));
    v21 = v29;
    if ( v29 )
      DevRtlWriteTextLog(ThreadLogToken, 32, 1, "Driver package failed signature validation. Error = 0x%08X", v29);
    *(_DWORD *)(a3 + 16) = *(_DWORD *)(a2 + 2104);
  }
  return v21;
}

```

## disassembly

```asm
0x140013220  mov     [rsp+arg_0], rbx
0x140013225  mov     [rsp+arg_18], rbp
0x14001322a  push    rsi
0x14001322b  push    rdi
0x14001322c  push    r13
0x14001322e  push    r14
0x140013230  push    r15
0x140013232  sub     rsp, 280h
0x140013239  mov     rax, cs:__security_cookie
0x140013240  xor     rax, rsp
0x140013243  mov     [rsp+2A8h+var_38], rax
0x14001324b  xor     r13d, r13d
0x14001324e  mov     rsi, r8
0x140013251  mov     ebp, r13d
0x140013254  mov     [rsp+2A8h+var_258], r13
0x140013259  mov     rbx, rdx
0x14001325c  mov     edi, ecx
0x14001325e  call    cs:__imp_DevRtlGetThreadLogToken
0x140013264  mov     r14, rax
0x140013267  test    rbx, rbx
0x14001326a  jz      loc_14001371D
0x140013270  test    rsi, rsi
0x140013273  jz      loc_14001371D
0x140013279  sub     edi, 1
0x14001327c  jz      loc_14001368E
0x140013282  sub     edi, 1
0x140013285  jz      loc_1400135FE
0x14001328b  sub     edi, 1
0x14001328e  jz      loc_1400133DF
0x140013294  sub     edi, 1
0x140013297  jz      short loc_140013307
0x140013299  cmp     edi, 1
0x14001329c  jnz     loc_14001371D
0x1400132a2  cmp     [rbx+62Ch], r13d
0x1400132a9  jnz     short loc_1400132DF
0x1400132ab  lea     rcx, [rbx+420h]
0x1400132b2  cmp     [rcx], r13w
0x1400132b6  jz      short loc_1400132D9
0x1400132b8  lea     r8, [rsi+30h]
0x1400132bc  movzx   eax, word ptr [r8]
0x1400132c0  neg     ax
0x1400132c3  sbb     r9, r9
0x1400132c6  and     r9, r8
0x1400132c9  call    pSetupGetFileTitle
0x1400132ce  mov     rcx, rax; pszSrc
0x1400132d1  mov     rdx, r9
0x1400132d4  call    UnpublishDriverPackageCatalog
0x1400132d9  add     rsi, 28h ; '('
0x1400132dd  jmp     short loc_1400132F3
0x1400132df  add     rsi, 28h ; '('
0x1400132e3  mov     rdx, [rsi]
0x1400132e6  test    rdx, rdx
0x1400132e9  jz      short loc_1400132F3
0x1400132eb  mov     rcx, rbx
0x1400132ee  call    ConfigureRootDevices
0x1400132f3  cmp     [rsi], r13
0x1400132f6  jz      loc_1400135DB
0x1400132fc  mov     rbp, [rsi]
0x1400132ff  mov     [rsi], r13
0x140013302  jmp     loc_1400135DB
0x140013307  movzx   edx, word ptr [rbx+208h]
0x14001330e  mov     r15d, 1
0x140013314  mov     r9d, r15d
0x140013317  mov     [rsp+2A8h+var_288], r13
0x14001331c  xor     r8d, r8d
0x14001331f  mov     rcx, rbx
0x140013322  call    cs:__imp_DriverPackageOpenW
0x140013328  mov     rdi, rax
0x14001332b  test    rax, rax
0x14001332e  jnz     short loc_140013358
0x140013330  call    cs:__imp_GetLastError
0x140013336  mov     dword ptr [rsp+2A8h+var_280], eax
0x14001333a  lea     r9, aUnableToOpenDr_1; "Unable to open driver package '%ws' for"...
0x140013341  mov     edx, r15d
0x140013344  mov     [rsp+2A8h+var_288], rbx
0x140013349  lea     r8d, [r15+1]
0x14001334d  mov     rcx, r14
0x140013350  call    cs:__imp_DevRtlWriteTextLog
0x140013356  jmp     short loc_1400133BD
0x140013358  lea     rdx, [rsp+2A8h+var_258]
0x14001335d  mov     rcx, rdi
0x140013360  call    GetDriverPackageRootDevices
0x140013365  test    eax, eax
0x140013367  jnz     short loc_140013398
0x140013369  call    cs:__imp_GetLastError
0x14001336f  mov     dword ptr [rsp+2A8h+var_280], eax
0x140013373  lea     r9, aUnableToGetRoo; "Unable to get root devices from driver "...
0x14001337a  mov     r8d, 2
0x140013380  mov     [rsp+2A8h+var_288], rbx
0x140013385  mov     edx, r15d
0x140013388  mov     rcx, r14
0x14001338b  call    cs:__imp_DevRtlWriteTextLog
0x140013391  mov     rbp, [rsp+2A8h+var_258]
0x140013396  jmp     short loc_1400133B4
0x140013398  mov     rbp, [rsp+2A8h+var_258]
0x14001339d  test    rbp, rbp
0x1400133a0  jz      short loc_1400133B4
0x1400133a2  mov     rdx, rbp
0x1400133a5  mov     rcx, rbx
0x1400133a8  call    UnconfigureRootDevices
0x1400133ad  mov     [rsi+28h], rbp
0x1400133b1  mov     rbp, r13
0x1400133b4  mov     rcx, rdi
0x1400133b7  call    cs:__imp_DriverPackageClose
0x1400133bd  mov     rcx, [rsi+20h]
0x1400133c1  lea     r8, [rsi+30h]
0x1400133c5  mov     rdx, rbx
0x1400133c8  call    GetDriverPackageSystemPath
0x1400133cd  test    eax, eax
0x1400133cf  jnz     loc_1400135DB
0x1400133d5  mov     [rsi+30h], r13w
0x1400133da  jmp     loc_1400135DB
0x1400133df  cmp     [rbx+62Ch], r13d
0x1400133e6  jnz     loc_14001357C
0x1400133ec  mov     r9, [rbx+418h]; LPCWSTR
0x1400133f3  lea     rdi, [rbx+210h]
0x1400133fa  lea     r15, [rbx+420h]
0x140013401  mov     r8, rdi; LPCWSTR
0x140013404  mov     rdx, r15; LPCWSTR
0x140013407  mov     rcx, rbx; lpFileName
0x14001340a  call    FlushDriverPackageFiles
0x14001340f  cmp     [r15], r13w
0x140013413  jz      short loc_14001346C
0x140013415  cmp     [rdi], r13w
0x140013419  jz      short loc_14001346C
0x14001341b  mov     rcx, [rsi+20h]
0x14001341f  lea     r8, [rsp+2A8h+var_248]
0x140013424  mov     rdx, rbx
0x140013427  call    GetDriverPackageSystemPath
0x14001342c  test    eax, eax
0x14001342e  jnz     short loc_140013438
0x140013430  mov     [rsp+2A8h+var_248], r13w
0x140013436  jmp     short loc_140013445
0x140013438  lea     r10, [rsp+2A8h+var_248]
0x14001343d  cmp     [rsp+2A8h+var_248], r13w
0x140013443  jnz     short loc_140013448
0x140013445  mov     r10, r13
0x140013448  mov     rcx, r15
0x14001344b  call    pSetupGetFileTitle
0x140013450  mov     r9d, [rsi+10h]
0x140013454  mov     rcx, rax; pszSrc
0x140013457  mov     rdx, r10
0x14001345a  mov     r8, rdi
0x14001345d  call    PublishDriverPackageCatalog
0x140013462  mov     edi, eax
0x140013464  test    eax, eax
0x140013466  jnz     loc_140013722
0x14001346c  movzx   edx, word ptr [rbx+208h]
0x140013473  mov     r15d, 1
0x140013479  mov     r9d, r15d
0x14001347c  mov     [rsp+2A8h+var_288], r13
0x140013481  xor     r8d, r8d
0x140013484  mov     rcx, rbx
0x140013487  call    cs:__imp_DriverPackageOpenW
0x14001348d  mov     rdi, rax
0x140013490  test    rax, rax
0x140013493  jnz     short loc_1400134C0
0x140013495  call    cs:__imp_GetLastError
0x14001349b  mov     dword ptr [rsp+2A8h+var_280], eax
0x14001349f  lea     r9, aUnableToOpenDr; "Unable to open driver package '%ws' for"...
0x1400134a6  mov     edx, r15d
0x1400134a9  mov     [rsp+2A8h+var_288], rbx
0x1400134ae  lea     r8d, [r15+1]
0x1400134b2  mov     rcx, r14
0x1400134b5  call    cs:__imp_DevRtlWriteTextLog
0x1400134bb  jmp     loc_14001357C
0x1400134c0  lea     rdx, [rsp+2A8h+var_258]
0x1400134c5  mov     rcx, rdi
0x1400134c8  call    GetDriverPackageRootDevices
0x1400134cd  mov     rbp, [rsp+2A8h+var_258]
0x1400134d2  test    eax, eax
0x1400134d4  jnz     short loc_140013500
0x1400134d6  call    cs:__imp_GetLastError
0x1400134dc  mov     dword ptr [rsp+2A8h+var_280], eax
0x1400134e0  lea     r9, aUnableToGetRoo; "Unable to get root devices from driver "...
0x1400134e7  mov     r8d, 2
0x1400134ed  mov     [rsp+2A8h+var_288], rbx
0x1400134f2  mov     edx, r15d
0x1400134f5  mov     rcx, r14
0x1400134f8  call    cs:__imp_DevRtlWriteTextLog
0x1400134fe  jmp     short loc_140013510
0x140013500  test    rbp, rbp
0x140013503  jz      short loc_140013510
0x140013505  mov     rdx, rbp
0x140013508  mov     rcx, rbx
0x14001350b  call    ConfigureRootDevices
0x140013510  mov     rdx, r14
0x140013513  mov     rcx, rdi
0x140013516  call    DriverPackageSupportsNativeArchitecture
0x14001351b  test    eax, eax
0x14001351d  jnz     short loc_140013573
0x14001351f  mov     rcx, rbx; unsigned __int16 *
0x140013522  call    SendNativeArchitectureUnsupportedEvent
0x140013527  test    eax, eax
0x140013529  jnz     short loc_140013555
0x14001352b  call    cs:__imp_GetLastError
0x140013531  mov     dword ptr [rsp+2A8h+var_280], eax
0x140013535  lea     r9, aUnableToSendNa; "Unable to send native architecture unsu"...
0x14001353c  mov     r8d, 2
0x140013542  mov     [rsp+2A8h+var_288], rbx
0x140013547  mov     edx, r15d
0x14001354a  mov     rcx, r14
0x14001354d  call    cs:__imp_DevRtlWriteTextLog
0x140013553  jmp     short loc_140013573
0x140013555  lea     r9, aSentNativeArch; "Sent native architecture unsupported ev"...
0x14001355c  mov     [rsp+2A8h+var_288], rbx
0x140013561  mov     r8d, 5
0x140013567  mov     edx, r15d
0x14001356a  mov     rcx, r14
0x14001356d  call    cs:__imp_DevRtlWriteTextLog
0x140013573  mov     rcx, rdi
0x140013576  call    cs:__imp_DriverPackageClose
0x14001357c  test    byte ptr [rbx+20Ch], 4
0x140013583  jnz     short loc_1400135C0
0x140013585  cmp     [rsi+18h], r13
0x140013589  jz      short loc_1400135C0
0x14001358b  call    IsSetDriverPackageRestorePointPresent
0x140013590  test    al, al
0x140013592  jz      short loc_1400135B1
0x140013594  cmp     [rbx+62Ch], r13d
0x14001359b  lea     rdx, [rsi+18h]
0x14001359f  mov     r8d, r13d
0x1400135a2  mov     rcx, rbx
0x1400135a5  setz    r8b
0x1400135a9  call    cs:__imp_SetDriverPackageRestorePoint
0x1400135af  jmp     short loc_1400135DB
0x1400135b1  lea     r9, aSystemRestoreP_0; "System restore point was set earlier, b"...
0x1400135b8  mov     r8d, 2
0x1400135be  jmp     short loc_1400135CD
0x1400135c0  lea     r9, aNoSystemRestor; "No system restore point was set earlier"...
0x1400135c7  mov     r8d, 5
0x1400135cd  mov     edx, 80h
0x1400135d2  mov     rcx, r14
0x1400135d5  call    cs:__imp_DevRtlWriteTextLog
0x1400135db  mov     edi, r13d
0x1400135de  test    rbp, rbp
0x1400135e1  jz      loc_140013722
0x1400135e7  mov     rcx, cs:hHeap; hHeap
0x1400135ee  mov     r8, rbp; lpMem
0x1400135f1  xor     edx, edx; dwFlags
0x1400135f3  call    cs:__imp_HeapFree
0x1400135f9  jmp     loc_140013722
0x1400135fe  test    byte ptr [rbx+20Ch], 4
0x140013605  jz      short loc_140013610
0x140013607  lea     r9, aSystemRestoreP; "System restore point not required."
0x14001360e  jmp     short loc_140013673
0x140013610  test    dword ptr [rsi+10h], 0F0000000h
0x140013617  jnz     short loc_140013622
0x140013619  lea     r9, aSystemRestoreN; "System restore not required for signed "...
0x140013620  jmp     short loc_140013673
0x140013622  call    PnpPolIsSystemRestoreDisabled
0x140013627  test    eax, eax
0x140013629  jz      short loc_14001364E
0x14001362b  mov     edx, 80h
0x140013630  mov     dword ptr [rsp+2A8h+var_288], 4ECh
0x140013638  lea     r9, aSystemRestoreD; "System restore disabled by policy. Erro"...
0x14001363f  mov     rcx, r14
0x140013642  lea     r8d, [rdx-7Bh]
0x140013646  call    cs:__imp_DevRtlWriteTextLog
0x14001364c  jmp     short loc_140013686
0x14001364e  call    IsSetDriverPackageRestorePointPresent
0x140013653  test    al, al
0x140013655  jz      short loc_14001366C
0x140013657  lea     rdx, [rsi+18h]
0x14001365b  xor     r8d, r8d
0x14001365e  mov     rcx, rbx
0x140013661  mov     [rdx], r13
0x140013664  call    cs:__imp_SetDriverPackageRestorePoint
0x14001366a  jmp     short loc_140013686
0x14001366c  lea     r9, aSystemRestoreI; "System restore implementation not prese"...
0x140013673  mov     r8d, 5
0x140013679  mov     rcx, r14
0x14001367c  lea     edx, [r8+7Bh]
0x140013680  call    cs:__imp_DevRtlWriteTextLog
0x140013686  mov     edi, r13d
0x140013689  jmp     loc_140013722
0x14001368e  mov     ecx, [rbx+20Ch]
0x140013694  lea     rax, [rbx+630h]
0x14001369b  mov     r9, [rbx+418h]
0x1400136a2  lea     rbp, [rbx+838h]
0x1400136a9  movzx   edx, word ptr [rbx+208h]
0x1400136b0  lea     r8, [rbx+210h]
0x1400136b7  mov     [rsp+2A8h+var_260], rbp
0x1400136bc  mov     r15d, 1
0x1400136c2  mov     [rsp+2A8h+var_268], rax
0x1400136c7  mov     eax, [rbx+628h]
0x1400136cd  mov     [rsp+2A8h+var_270], eax
0x1400136d1  mov     rax, [rsi+8]
0x1400136d5  shr     ecx, 3
0x1400136d8  and     ecx, r15d
0x1400136db  mov     [rsp+2A8h+var_278], ecx
0x1400136df  mov     rcx, rbx
0x1400136e2  mov     [rsp+2A8h+var_280], rax
0x1400136e7  mov     rax, [rsi]
0x1400136ea  mov     [rsp+2A8h+var_288], rax
0x1400136ef  call    ValidateDriverPackage
0x1400136f4  mov     edi, eax
0x1400136f6  test    eax, eax
0x1400136f8  jz      short loc_140013715
0x1400136fa  lea     r9, aDriverPackageF; "Driver package failed signature validat"...
  ... truncated ...
```
