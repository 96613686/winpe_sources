# pHandleDriverInstall

- ea: `0x1400161bc`
- end: `0x1400165a4`
- name: `pHandleDriverInstall`
- size: `1000`
- prototype: `__int64 __fastcall(int, void *, __int64, __int64, __int64, unsigned __int16, __int64, __int64, int, unsigned int, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x140009820`

## callees

- `0x140012ce8`
- `0x140013758`
- `0x140013e14`
- `0x140014860`
- `0x1400161bc`
- `0x140020f3c`
- `0x140022bc8`
- `0x14002bff4`
- `0x140045f30`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x14001630f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140016326`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14001630f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140016326`
- `ntdll!DbgPrintEx` at `0x140016277`
- `ntdll!DbgPrintEx` at `0x140016277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400162a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400162f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400163d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400162a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400162f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400163d6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14001634e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14001634e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016579`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400162d2`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400163a6`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400164d8`
- `DEVRTL!DevRtlWriteTextLog` at `0x140016562`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400162d2`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400163a6`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400164d8`
- `DEVRTL!DevRtlWriteTextLog` at `0x140016562`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14001627e`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x14001622d`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x14001622d`
- `drvstore!DriverStoreSetLogContext` at `0x140016285`
- `drvstore!DriverStoreSetLogContext` at `0x140016285`
- `drvstore!pServerImportDriverPackage` at `0x1400164b7`
- `drvstore!pServerImportDriverPackage` at `0x1400164b7`
- `drvstore!pServerDeleteDriverPackage` at `0x14001645e`
- `drvstore!pServerDeleteDriverPackage` at `0x14001645e`
- `drvstore!DriverStoreOpenW` at `0x1400162e7`
- `drvstore!DriverStoreOpenW` at `0x1400162e7`
- `drvstore!DriverStoreClose` at `0x14001656b`
- `drvstore!DriverStoreClose` at `0x14001656b`
- `drvstore!DriverStoreSelectNodeW` at `0x1400163cc`
- `drvstore!DriverStoreSelectNodeW` at `0x1400163cc`
- `drvstore!DriverStoreMountNodeW` at `0x14001637e`
- `drvstore!DriverStoreMountNodeW` at `0x14001637e`

## string_xrefs

- `0x140016254`: `delete`
- `0x14001625b`: `install`
- `0x140016301`: `Failed to open the driver store. Error = 0x%08X`
- `0x14001654b`: `Failed to create driver store node path. Error = 0x%08X`
- `0x140016393`: `Reboot required after mounting new driver store node.`
- `0x1400163b0`: `Failed to mount writeable driver store node. Error = 0x%08X`
- `0x1400163e0`: `Failed to selected writeable driver store node. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall pHandleDriverInstall(
        int a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned __int16 a6,
        __int64 a7,
        __int64 a8,
        int a9,
        unsigned int a10,
        int *a11)
{
  void *v13; // rbx
  const wchar_t *v14; // r9
  DWORD LastError; // ebx
  const char *v16; // r9
  __int64 v17; // r14
  void *v18; // rdi
  int v19; // r13d
  char IsStateSeparationEnabled; // al
  const WCHAR *v21; // rcx
  const char *v22; // r9
  __int64 DriverStoreNotifyContext; // rax
  int v24; // esi
  int v25; // esi
  int v26; // esi
  DWORD v27; // eax
  DWORD v29; // [rsp+20h] [rbp-2B8h]
  int v30; // [rsp+50h] [rbp-288h] BYREF
  void *v31; // [rsp+58h] [rbp-280h]
  __int64 v32; // [rsp+60h] [rbp-278h]
  __int64 v33; // [rsp+68h] [rbp-270h]
  __int64 v34; // [rsp+70h] [rbp-268h]
  int *v35; // [rsp+78h] [rbp-260h]
  WCHAR Dst[264]; // [rsp+80h] [rbp-258h] BYREF

  v34 = a5;
  v13 = a2;
  v33 = a8;
  v35 = a11;
  v32 = a3;
  v31 = a2;
  v30 = 0;
  DevRtlSetThreadLogToken(a7);
  if ( (unsigned int)DoDebugBreak(L"DebugDriver") )
  {
    if ( a1 == 4 )
    {
      v14 = L"add";
    }
    else
    {
      v14 = L"delete";
      if ( a1 != 5 )
        v14 = L"install";
    }
    DbgPrintEx(
      0x23u,
      0,
      "\nDRVINST.EXE: Entering debugger while %ws driver package to Driver Store.\nINF = \"%ls\" ...\n\n",
      v14,
      a4);
    __debugbreak();
  }
  DriverStoreSetLogContext(DevRtlGetThreadLogToken);
  if ( !(unsigned int)PnpPolIsDriverImportAllowed(v13) )
  {
    LastError = GetLastError();
    v16 = "Driver package import is blocked by policy. Error = 0x%08X";
    if ( LastError != 5 )
      v16 = "Failed to determine driver store import policy. Error = 0x%08X";
    goto LABEL_10;
  }
  v17 = DriverStoreOpenW(0, 0, 0, 0);
  if ( !v17 )
  {
    LastError = GetLastError();
    v16 = "Failed to open the driver store. Error = 0x%08X";
LABEL_10:
    DevRtlWriteTextLog(a7, 0x4000000, 1, v16);
    return LastError;
  }
  v18 = 0;
  v19 = 0;
  if ( !(unsigned __int8)RtlIsStateSeparationEnabled()
    && !(unsigned int)Feature_Writeable_DriverStore__private_IsEnabledDeviceUsageNoInline() )
  {
    goto LABEL_24;
  }
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v21 = L"%OsDataDrive%\\OEMDRIVERS";
  if ( !IsStateSeparationEnabled )
    v21 = L"%SystemRoot%\\OEMDRIVERS";
  if ( ExpandEnvironmentStringsW(v21, Dst, 0x104u) - 1 > 0x103 )
  {
    LastError = 87;
    v22 = "Failed to create driver store node path. Error = 0x%08X";
    goto LABEL_40;
  }
  LastError = DriverStoreMountNodeW(v17, L"OEMDRIVERS", Dst, 0, 5);
  if ( LastError == 183
    || (v19 = 1,
        DevRtlWriteTextLog(a7, 0x4000000, 2, "Reboot required after mounting new driver store node."),
        !LastError) )
  {
    if ( !(unsigned int)DriverStoreSelectNodeW(v17, L"OEMDRIVERS", 0) )
    {
      v29 = GetLastError();
      v22 = "Failed to selected writeable driver store node. Error = 0x%08X";
      LastError = v29;
      goto LABEL_40;
    }
    v13 = v31;
LABEL_24:
    if ( a1 != 8 )
    {
      if ( a1 == 9 )
      {
LABEL_34:
        v27 = UninstallDriver(v17, a4, a10, &v30);
        goto LABEL_36;
      }
      DriverStoreNotifyContext = CreateDriverStoreNotifyContext(v17, v13, v32);
      v18 = (void *)DriverStoreNotifyContext;
      v24 = a1 - 4;
      if ( !v24 )
      {
        LastError = pServerImportDriverPackage(
                      v17,
                      a4,
                      v34,
                      a6,
                      0,
                      a10,
                      v33,
                      a9,
                      &DriverStoreNotifyCallback,
                      DriverStoreNotifyContext);
        if ( LastError )
          goto LABEL_41;
        DevRtlWriteTextLog(a7, 1, 5, "Doing device matching lookup");
        PnpUtilsGetMatchingDevices(v17, v33, MarkDeviceForReinstallCallback, 0, a7);
        goto LABEL_37;
      }
      v25 = v24 - 1;
      if ( !v25 )
      {
        v27 = pServerDeleteDriverPackage(v17, a4, a10, &DriverStoreNotifyCallback, DriverStoreNotifyContext);
        goto LABEL_36;
      }
      v26 = v25 - 3;
      if ( v26 )
      {
        if ( v26 != 1 )
        {
          LastError = 87;
          goto LABEL_41;
        }
        goto LABEL_34;
      }
    }
    v27 = InstallDriver(v17, a4, a10, &v30);
LABEL_36:
    LastError = v27;
    if ( v27 )
      goto LABEL_41;
LABEL_37:
    if ( v35 )
      *v35 = v30 | v19;
    goto LABEL_41;
  }
  v22 = "Failed to mount writeable driver store node. Error = 0x%08X";
LABEL_40:
  DevRtlWriteTextLog(a7, 0x4000000, 1, v22);
LABEL_41:
  DriverStoreClose(v17);
  if ( v18 )
    LocalFree(v18);
  return LastError;
}

```

## disassembly

```asm
0x1400161bc  push    rbx
0x1400161be  push    rsi
0x1400161bf  push    rdi
0x1400161c0  push    r12
0x1400161c2  push    r13
0x1400161c4  push    r14
0x1400161c6  push    r15
0x1400161c8  sub     rsp, 2A0h
0x1400161cf  mov     rax, cs:__security_cookie
0x1400161d6  xor     rax, rsp
0x1400161d9  mov     [rsp+2D8h+var_48], rax
0x1400161e1  mov     rax, [rsp+2D8h+arg_20]
0x1400161e9  mov     esi, ecx
0x1400161eb  mov     r15, [rsp+2D8h+arg_30]
0x1400161f3  mov     r12, r9
0x1400161f6  mov     [rsp+2D8h+var_268], rax
0x1400161fb  mov     rcx, r15
0x1400161fe  mov     rax, [rsp+2D8h+arg_38]
0x140016206  mov     rbx, rdx
0x140016209  mov     [rsp+2D8h+var_270], rax
0x14001620e  mov     rax, [rsp+2D8h+arg_50]
0x140016216  mov     [rsp+2D8h+var_260], rax
0x14001621b  mov     [rsp+2D8h+var_278], r8
0x140016220  mov     [rsp+2D8h+var_280], rdx
0x140016225  mov     [rsp+2D8h+var_288], 0
0x14001622d  call    cs:__imp_DevRtlSetThreadLogToken
0x140016233  lea     rcx, aDebugdriver; "DebugDriver"
0x14001623a  call    DoDebugBreak
0x14001623f  test    eax, eax
0x140016241  jz      short loc_14001627E
0x140016243  cmp     esi, 4
0x140016246  jnz     short loc_140016251
0x140016248  lea     r9, aAdd; "add"
0x14001624f  jmp     short loc_140016266
0x140016251  cmp     esi, 5
0x140016254  lea     r9, aDelete; "delete"
0x14001625b  lea     rax, aInstall; "install"
0x140016262  cmovnz  r9, rax
0x140016266  xor     edx, edx; Level
0x140016268  mov     [rsp+2D8h+var_2B8], r12
0x14001626d  lea     r8, aDrvinstExeEnte; "\nDRVINST.EXE: Entering debugger while "...
0x140016274  lea     ecx, [rdx+23h]; ComponentId
0x140016277  call    cs:__imp_DbgPrintEx
0x14001627d  int     3; Trap to Debugger
0x14001627e  mov     rcx, cs:__imp_DevRtlGetThreadLogToken
0x140016285  call    cs:__imp_DriverStoreSetLogContext
0x14001628b  movzx   r8d, [rsp+2D8h+arg_28]
0x140016294  mov     rdx, r12
0x140016297  mov     rcx, rbx; TokenHandle
0x14001629a  call    PnpPolIsDriverImportAllowed
0x14001629f  test    eax, eax
0x1400162a1  jnz     short loc_1400162DD
0x1400162a3  call    cs:__imp_GetLastError
0x1400162a9  mov     ebx, eax
0x1400162ab  lea     r9, aDriverPackageI_7; "Driver package import is blocked by pol"...
0x1400162b2  cmp     ebx, 5
0x1400162b5  mov     dword ptr [rsp+2D8h+var_2B8], ebx
0x1400162b9  lea     rax, aFailedToDeterm_1; "Failed to determine driver store import"...
0x1400162c0  cmovnz  r9, rax
0x1400162c4  mov     edx, 4000000h
0x1400162c9  mov     r8d, 1
0x1400162cf  mov     rcx, r15
0x1400162d2  call    cs:__imp_DevRtlWriteTextLog
0x1400162d8  jmp     loc_14001657F
0x1400162dd  xor     r9d, r9d
0x1400162e0  xor     r8d, r8d
0x1400162e3  xor     edx, edx
0x1400162e5  xor     ecx, ecx
0x1400162e7  call    cs:__imp_DriverStoreOpenW
0x1400162ed  mov     r14, rax
0x1400162f0  test    rax, rax
0x1400162f3  jnz     short loc_14001630A
0x1400162f5  call    cs:__imp_GetLastError
0x1400162fb  mov     ebx, eax
0x1400162fd  mov     dword ptr [rsp+2D8h+var_2B8], eax
0x140016301  lea     r9, aFailedToOpenTh; "Failed to open the driver store. Error "...
0x140016308  jmp     short loc_1400162C4
0x14001630a  xor     edi, edi
0x14001630c  xor     r13d, r13d
0x14001630f  call    cs:__imp_RtlIsStateSeparationEnabled
0x140016315  test    al, al
0x140016317  jnz     short loc_140016326
0x140016319  call    Feature_Writeable_DriverStore__private_IsEnabledDeviceUsageNoInline
0x14001631e  test    eax, eax
0x140016320  jz      loc_1400163F9
0x140016326  call    cs:__imp_RtlIsStateSeparationEnabled
0x14001632c  lea     rdx, Src; "%SystemRoot%\\OEMDRIVERS"
0x140016333  mov     r8d, 104h; nSize
0x140016339  test    al, al
0x14001633b  lea     rcx, aOsdatadriveOem; "%OsDataDrive%\\OEMDRIVERS"
0x140016342  cmovz   rcx, rdx; lpSrc
0x140016346  lea     rdx, [rsp+2D8h+Dst]; lpDst
0x14001634e  call    cs:__imp_ExpandEnvironmentStringsW
0x140016354  dec     eax
0x140016356  cmp     eax, 103h
0x14001635b  ja      loc_140016546
0x140016361  xor     r9d, r9d
0x140016364  mov     dword ptr [rsp+2D8h+var_2B8], 5
0x14001636c  lea     r8, [rsp+2D8h+Dst]
0x140016374  mov     rcx, r14
0x140016377  lea     rdx, aOemdrivers; "OEMDRIVERS"
0x14001637e  call    cs:__imp_DriverStoreMountNodeW
0x140016384  mov     ebx, eax
0x140016386  cmp     eax, 0B7h
0x14001638b  jz      short loc_1400163BF
0x14001638d  mov     r13d, 1
0x140016393  lea     r9, aRebootRequired_0; "Reboot required after mounting new driv"...
0x14001639a  mov     edx, 4000000h
0x14001639f  mov     rcx, r15
0x1400163a2  lea     r8d, [r13+1]
0x1400163a6  call    cs:__imp_DevRtlWriteTextLog
0x1400163ac  test    ebx, ebx
0x1400163ae  jz      short loc_1400163BF
0x1400163b0  lea     r9, aFailedToMountW; "Failed to mount writeable driver store "...
0x1400163b7  mov     r8d, r13d
0x1400163ba  jmp     loc_140016556
0x1400163bf  xor     r8d, r8d
0x1400163c2  lea     rdx, aOemdrivers; "OEMDRIVERS"
0x1400163c9  mov     rcx, r14
0x1400163cc  call    cs:__imp_DriverStoreSelectNodeW
0x1400163d2  test    eax, eax
0x1400163d4  jnz     short loc_1400163F4
0x1400163d6  call    cs:__imp_GetLastError
0x1400163dc  mov     dword ptr [rsp+2D8h+var_2B8], eax
0x1400163e0  lea     r9, aFailedToSelect_0; "Failed to selected writeable driver sto"...
0x1400163e7  mov     ebx, eax
0x1400163e9  mov     r8d, 1
0x1400163ef  jmp     loc_14001655A
0x1400163f4  mov     rbx, [rsp+2D8h+var_280]
0x1400163f9  cmp     esi, 8
0x1400163fc  jz      loc_140016514
0x140016402  cmp     esi, 9
0x140016405  jz      loc_1400164FA
0x14001640b  mov     r8, [rsp+2D8h+var_278]
0x140016410  mov     rdx, rbx
0x140016413  mov     rcx, r14
0x140016416  call    CreateDriverStoreNotifyContext
0x14001641b  mov     rdi, rax
0x14001641e  sub     esi, 4
0x140016421  jz      short loc_140016469
0x140016423  sub     esi, 1
0x140016426  jz      short loc_140016444
0x140016428  sub     esi, 3
0x14001642b  jz      loc_140016514
0x140016431  cmp     esi, 1
0x140016434  jz      loc_1400164FA
0x14001643a  mov     ebx, 57h ; 'W'
0x14001643f  jmp     loc_140016568
0x140016444  mov     r8d, [rsp+2D8h+arg_48]
0x14001644c  lea     r9, DriverStoreNotifyCallback
0x140016453  mov     rdx, r12
0x140016456  mov     [rsp+2D8h+var_2B8], rax
0x14001645b  mov     rcx, r14
0x14001645e  call    cs:__imp_pServerDeleteDriverPackage
0x140016464  jmp     loc_14001652C
0x140016469  mov     rsi, [rsp+2D8h+var_270]
0x14001646e  mov     rdx, r12
0x140016471  movzx   r9d, [rsp+2D8h+arg_28]
0x14001647a  mov     rcx, r14
0x14001647d  mov     r8, [rsp+2D8h+var_268]
0x140016482  mov     [rsp+2D8h+var_290], rax
0x140016487  lea     rax, DriverStoreNotifyCallback
0x14001648e  mov     [rsp+2D8h+var_298], rax
0x140016493  mov     eax, [rsp+2D8h+arg_40]
0x14001649a  mov     [rsp+2D8h+var_2A0], eax
0x14001649e  mov     eax, [rsp+2D8h+arg_48]
0x1400164a5  mov     [rsp+2D8h+var_2A8], rsi
0x1400164aa  mov     [rsp+2D8h+var_2B0], eax
0x1400164ae  mov     [rsp+2D8h+var_2B8], 0
0x1400164b7  call    cs:__imp_pServerImportDriverPackage
0x1400164bd  mov     ebx, eax
0x1400164bf  test    eax, eax
0x1400164c1  jnz     loc_140016568
0x1400164c7  lea     r9, aDoingDeviceMat; "Doing device matching lookup"
0x1400164ce  mov     rcx, r15
0x1400164d1  lea     edx, [rax+1]
0x1400164d4  lea     r8d, [rax+5]
0x1400164d8  call    cs:__imp_DevRtlWriteTextLog
0x1400164de  xor     r9d, r9d
0x1400164e1  mov     [rsp+2D8h+var_2B8], r15
0x1400164e6  lea     r8, MarkDeviceForReinstallCallback
0x1400164ed  mov     rdx, rsi
0x1400164f0  mov     rcx, r14
0x1400164f3  call    PnpUtilsGetMatchingDevices
0x1400164f8  jmp     short loc_140016532
0x1400164fa  mov     r8d, [rsp+2D8h+arg_48]
0x140016502  lea     r9, [rsp+2D8h+var_288]
0x140016507  mov     rdx, r12
0x14001650a  mov     rcx, r14
0x14001650d  call    UninstallDriver
0x140016512  jmp     short loc_14001652C
0x140016514  mov     r8d, [rsp+2D8h+arg_48]
0x14001651c  lea     r9, [rsp+2D8h+var_288]
0x140016521  mov     rdx, r12
0x140016524  mov     rcx, r14
0x140016527  call    InstallDriver
0x14001652c  mov     ebx, eax
0x14001652e  test    eax, eax
0x140016530  jnz     short loc_140016568
0x140016532  mov     rax, [rsp+2D8h+var_260]
0x140016537  test    rax, rax
0x14001653a  jz      short loc_140016568
0x14001653c  or      r13d, [rsp+2D8h+var_288]
0x140016541  mov     [rax], r13d
0x140016544  jmp     short loc_140016568
0x140016546  mov     ebx, 57h ; 'W'
0x14001654b  lea     r9, aFailedToCreate_2; "Failed to create driver store node path"...
0x140016552  lea     r8d, [rbx-56h]
0x140016556  mov     dword ptr [rsp+2D8h+var_2B8], ebx
0x14001655a  mov     edx, 4000000h
0x14001655f  mov     rcx, r15
0x140016562  call    cs:__imp_DevRtlWriteTextLog
0x140016568  mov     rcx, r14
0x14001656b  call    cs:__imp_DriverStoreClose
0x140016571  test    rdi, rdi
0x140016574  jz      short loc_14001657F
0x140016576  mov     rcx, rdi; hMem
0x140016579  call    cs:__imp_LocalFree
0x14001657f  mov     eax, ebx
0x140016581  mov     rcx, [rsp+2D8h+var_48]
0x140016589  xor     rcx, rsp; StackCookie
0x14001658c  call    __security_check_cookie
0x140016591  add     rsp, 2A0h
0x140016598  pop     r15
0x14001659a  pop     r14
0x14001659c  pop     r13
0x14001659e  pop     r12
0x1400165a0  pop     rdi
0x1400165a1  pop     rsi
0x1400165a2  pop     rbx
0x1400165a3  retn
```
