# CoreDeviceInstallWorker

- ea: `0x14001e944`
- end: `0x14001edcd`
- name: `CoreDeviceInstallWorker`
- size: `1161`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14001dc80`

## callees

- `0x140010918`
- `0x140018dc0`
- `0x14001c718`
- `0x14001e944`
- `0x14001ee30`
- `0x14001f0cc`
- `0x14001fa98`
- `0x14001fc78`
- `0x140020418`
- `0x140027670`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001eb01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001eb01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001eb90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ebde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ed3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001eb90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ebde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ed3d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x14001ea50`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x14001ea50`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x14001ec4c`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x14001ec4c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001ec91`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001ecd7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001ec91`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001ecd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ec5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ec5d`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ea7f`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ebb0`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ec03`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ed5d`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ea7f`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ebb0`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ec03`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001ed5d`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14001e9dd`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14001e9dd`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x14001ed33`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x14001ed33`

## string_xrefs

- `0x14001ea69`: `Marking non-present device %ws for reinstall.`
- `0x14001eb9a`: `Failed to select extension INFs for device. Error = 0x%08X`
- `0x14001ed47`: `Unable to track installed device %ws. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall CoreDeviceInstallWorker(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        wchar_t *a4,
        wchar_t *a5,
        unsigned int a6,
        __int64 a7,
        __int64 a8)
{
  void *v11; // rsi
  unsigned __int64 ThreadLogToken; // r13
  __int64 v13; // rdi
  unsigned int LastError; // ebx
  __int64 v15; // r12
  int v16; // ecx
  int v18; // ebx
  int v19; // ecx
  PHKEY phkDevice; // [rsp+20h] [rbp-E0h]
  ULONG ulFlags[2]; // [rsp+28h] [rbp-D8h]
  ULONG ulFlagsa[2]; // [rsp+28h] [rbp-D8h]
  unsigned int v23; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v24; // [rsp+44h] [rbp-BCh]
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  int v26[2]; // [rsp+50h] [rbp-B0h]
  ULONG pulProblemNumber; // [rsp+58h] [rbp-A8h] BYREF
  ULONG pulStatus; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *Str; // [rsp+68h] [rbp-98h]
  int v31[2]; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+78h] [rbp-88h]
  unsigned int v33[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v34; // [rsp+88h] [rbp-78h]
  wchar_t *v35; // [rsp+90h] [rbp-70h]
  wchar_t *v36; // [rsp+98h] [rbp-68h]
  __int128 v37; // [rsp+A0h] [rbp-60h]
  HKEY hKey; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-48h]
  __int64 v40; // [rsp+C0h] [rbp-40h]
  __int128 v41; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v42; // [rsp+D8h] [rbp-28h]
  __int128 v43; // [rsp+E8h] [rbp-18h]

  v39 = a7;
  *(_QWORD *)v31 = a8;
  v24 = a2;
  *(_QWORD *)v26 = a1;
  v11 = 0;
  Str = a5;
  v29 = 0;
  v25 = 0;
  pulStatus = 0;
  pulProblemNumber = 0;
  v23 = 0;
  hKey = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v33[1] = 0;
  v37 = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  DrvInstActionCallback(0, 0);
  v33[0] = a2;
  v34 = a3;
  v35 = a4;
  v36 = a5;
  DrvInstActionCallback(7, v33);
  v13 = *((_QWORD *)&v37 + 1);
  if ( *((_QWORD *)&v37 + 1) )
    *(_DWORD *)(*((_QWORD *)&v37 + 1) + 2968LL) = 1;
  *(_QWORD *)&v37 = v13;
  DrvInstActionCallback(8, v33);
  v40 = *((_QWORD *)&v37 + 1);
  if ( CM_Get_DevNode_Status(&pulStatus, &pulProblemNumber, a2, 0) )
  {
    LastError = 0;
    if ( a4 )
    {
      DevRtlWriteTextLog(ThreadLogToken, 1, 4, "Marking non-present device %ws for reinstall.", a3);
      DevUtilsMarkDeviceForReinstall(v24, ThreadLogToken);
    }
    goto LABEL_6;
  }
  DrvInstActionCallback(3, v33);
  if ( DWORD2(v37) )
  {
    LastError = 1115;
LABEL_6:
    v15 = v25;
    goto LABEL_7;
  }
  v11 = Str;
  if ( a4 && (unsigned int)ExtensionsRequireSelection(Str) )
  {
    if ( !(unsigned int)SelectExtensionDrivers(v26[0], a2, a3, a4, (__int64)&v29, ThreadLogToken) )
    {
      LastError = GetLastError();
      DevRtlWriteTextLog(ThreadLogToken, 1, 1, "Failed to select extension INFs for device. Error = 0x%08X", LastError);
      v11 = (void *)v29;
      goto LABEL_6;
    }
    v11 = (void *)v29;
  }
  if ( !(unsigned int)BuildDriverNodeInfo(*(_QWORD *)v26, a4, v11, &v25) )
  {
    ulFlags[0] = GetLastError();
    LastError = ulFlags[0];
    DevRtlWriteTextLog(
      ThreadLogToken,
      1,
      1,
      "Failed to resolve selected driver node '%ws'. Error = 0x%08X",
      v11,
      *(_QWORD *)ulFlags);
    goto LABEL_6;
  }
  v15 = v25;
  v24 = 0;
  LogDeviceInstallStart(*(_QWORD *)v26, a2, a3, v25);
  if ( CM_Open_DevNode_Key(a2, 0x20019u, 0, 1u, &hKey, 1u) )
  {
    v18 = v24;
  }
  else
  {
    v18 = 1;
    RegCloseKey(hKey);
  }
  if ( v13 )
  {
    *(_DWORD *)(v13 + 2936) = a6;
    *(_DWORD *)(v13 + 2932) = v18;
    *(_DWORD *)(v13 + 2940) = (a6 >> 18) & 1;
    GetSystemTimeAsFileTime((LPFILETIME)(v13 + 2944));
  }
  LastError = ConfigureDevice(v26[0], a3, v15, a6, (int)DrvInstActionCallback, 0, &v23);
  if ( v13 )
  {
    GetSystemTimeAsFileTime((LPFILETIME)(v13 + 2956));
    *(_DWORD *)(v13 + 2964) = LastError;
    *(_DWORD *)(v13 + 2952) = (v23 >> 30) & 1;
  }
  if ( LastError || !v39 )
    goto LABEL_7;
  v41 = 0;
  LODWORD(v41) = 48;
  v42 = 0;
  v43 = 0;
  if ( !(unsigned int)DevObjOpenDeviceInfo(v39, a3, 0, 0, &v41) )
  {
    ulFlagsa[0] = GetLastError();
    DevRtlWriteTextLog(
      ThreadLogToken,
      1,
      2,
      "Unable to track installed device %ws. Error = 0x%08X",
      a3,
      *(_QWORD *)ulFlagsa);
LABEL_7:
    if ( v13 )
    {
      if ( !LastError || (v16 = 11, (a6 & 0x10000) == 0) )
        v16 = 10;
      DrvInstActionCallback(v16, v33);
      *(_QWORD *)&v37 = v13;
      DrvInstActionCallback(9, v33);
    }
    goto LABEL_12;
  }
  v19 = v31[0];
  if ( !*(_QWORD *)v31 )
    goto LABEL_7;
  v31[1] = 0;
  v31[0] = v23 & 0x40000005;
  if ( (a6 & 0x1000) != 0 )
    v31[0] = v23 & 0x40000005 | 0x80000000;
  if ( (a6 & 0x40000000) == 0 )
    goto LABEL_7;
  v32 = v13;
  LODWORD(phkDevice) = 16;
  if ( (unsigned int)pSetupStringTableAddStringEx(v19, (size_t)phkDevice) == -1 )
    goto LABEL_7;
LABEL_12:
  *(_QWORD *)&v37 = v40;
  DrvInstActionCallback(8, v33);
  if ( v11 && !Str )
    HeapFree(hHeap, 0, v11);
  if ( v15 )
    FreeDriverNodeInfo(v15);
  return LastError;
}

```

## disassembly

```asm
0x14001e944  push    rbp
0x14001e946  push    rbx
0x14001e947  push    rsi
0x14001e948  push    rdi
0x14001e949  push    r12
0x14001e94b  push    r13
0x14001e94d  push    r14
0x14001e94f  push    r15
0x14001e951  lea     rbp, [rsp-8]
0x14001e956  sub     rsp, 108h
0x14001e95d  mov     rax, cs:__security_cookie
0x14001e964  xor     rax, rsp
0x14001e967  mov     [rbp+40h+var_48], rax
0x14001e96b  mov     rax, [rbp+40h+arg_30]
0x14001e972  xor     r14d, r14d
0x14001e975  mov     rdi, [rbp+40h+arg_20]
0x14001e979  xorps   xmm0, xmm0
0x14001e97c  xorps   xmm1, xmm1
0x14001e97f  mov     [rbp+40h+var_88], rax
0x14001e983  mov     rax, [rbp+40h+arg_38]
0x14001e98a  mov     r12, r9
0x14001e98d  mov     qword ptr [rsp+140h+var_D0], rax
0x14001e992  mov     r15, r8
0x14001e995  mov     ebx, edx
0x14001e997  mov     [rsp+140h+var_FC], edx
0x14001e99b  mov     qword ptr [rsp+140h+var_F0], rcx
0x14001e9a0  mov     esi, r14d
0x14001e9a3  mov     [rsp+140h+Str], rdi
0x14001e9a8  mov     [rsp+140h+var_E0], r14
0x14001e9ad  mov     [rsp+140h+var_F8], r14
0x14001e9b2  mov     [rsp+140h+pulStatus], r14d
0x14001e9b7  mov     [rsp+140h+pulProblemNumber], r14d
0x14001e9bc  mov     [rsp+140h+var_100], r14d
0x14001e9c1  mov     [rbp+40h+hKey], r14
0x14001e9c5  movups  [rbp+40h+var_78], xmm0
0x14001e9c9  movups  [rbp+40h+var_68], xmm0
0x14001e9cd  movups  [rbp+40h+var_58], xmm0
0x14001e9d1  movups  [rbp+40h+var_C0], xmm1
0x14001e9d5  movups  [rbp+40h+var_B0], xmm1
0x14001e9d9  movups  [rbp+40h+var_A0], xmm1
0x14001e9dd  call    cs:__imp_DevRtlGetThreadLogToken
0x14001e9e3  xor     r8d, r8d
0x14001e9e6  xor     edx, edx
0x14001e9e8  xor     ecx, ecx
0x14001e9ea  mov     r13, rax
0x14001e9ed  call    DrvInstActionCallback
0x14001e9f2  xor     r8d, r8d
0x14001e9f5  mov     dword ptr [rbp+40h+var_C0], ebx
0x14001e9f8  lea     rdx, [rbp+40h+var_C0]
0x14001e9fc  mov     qword ptr [rbp+40h+var_C0+8], r15
0x14001ea00  lea     ecx, [r14+7]
0x14001ea04  mov     qword ptr [rbp+40h+var_B0], r12
0x14001ea08  mov     qword ptr [rbp+40h+var_B0+8], rdi
0x14001ea0c  call    DrvInstActionCallback
0x14001ea11  mov     rdi, qword ptr [rbp+40h+var_A0+8]
0x14001ea15  test    rdi, rdi
0x14001ea18  jz      short loc_14001EA24
0x14001ea1a  mov     dword ptr [rdi+0B98h], 1
0x14001ea24  xor     r8d, r8d
0x14001ea27  mov     qword ptr [rbp+40h+var_A0], rdi
0x14001ea2b  lea     rdx, [rbp+40h+var_C0]
0x14001ea2f  lea     ecx, [r8+8]
0x14001ea33  call    DrvInstActionCallback
0x14001ea38  mov     rax, qword ptr [rbp+40h+var_A0+8]
0x14001ea3c  lea     rdx, [rsp+140h+pulProblemNumber]; pulProblemNumber
0x14001ea41  xor     r9d, r9d; ulFlags
0x14001ea44  mov     [rbp+40h+var_80], rax
0x14001ea48  mov     r8d, ebx; dnDevInst
0x14001ea4b  lea     rcx, [rsp+140h+pulStatus]; pulStatus
0x14001ea50  call    cs:__imp_CM_Get_DevNode_Status
0x14001ea56  mov     r14d, [rbp+40h+arg_28]
0x14001ea5a  test    eax, eax
0x14001ea5c  jz      loc_14001EB36
0x14001ea62  xor     ebx, ebx
0x14001ea64  test    r12, r12
0x14001ea67  jz      short loc_14001EA91
0x14001ea69  lea     r9, aMarkingNonPres; "Marking non-present device %ws for rein"...
0x14001ea70  mov     [rsp+140h+phkDevice], r15
0x14001ea75  lea     edx, [rbx+1]
0x14001ea78  mov     rcx, r13
0x14001ea7b  lea     r8d, [rbx+4]
0x14001ea7f  call    cs:__imp_DevRtlWriteTextLog
0x14001ea85  mov     ecx, [rsp+140h+var_FC]
0x14001ea89  mov     rdx, r13
0x14001ea8c  call    DevUtilsMarkDeviceForReinstall
0x14001ea91  mov     r12, [rsp+140h+var_F8]
0x14001ea96  test    rdi, rdi
0x14001ea99  jz      short loc_14001EAD0
0x14001ea9b  test    ebx, ebx
0x14001ea9d  jz      short loc_14001EAAB
0x14001ea9f  mov     ecx, 0Bh
0x14001eaa4  bt      r14d, 10h
0x14001eaa9  jb      short loc_14001EAB0
0x14001eaab  mov     ecx, 0Ah
0x14001eab0  xor     r8d, r8d
0x14001eab3  lea     rdx, [rbp+40h+var_C0]
0x14001eab7  call    DrvInstActionCallback
0x14001eabc  xor     r8d, r8d
0x14001eabf  mov     qword ptr [rbp+40h+var_A0], rdi
0x14001eac3  lea     rdx, [rbp+40h+var_C0]
0x14001eac7  lea     ecx, [r8+9]
0x14001eacb  call    DrvInstActionCallback
0x14001ead0  mov     rax, [rbp+40h+var_80]
0x14001ead4  lea     rdx, [rbp+40h+var_C0]
0x14001ead8  xor     r8d, r8d
0x14001eadb  mov     qword ptr [rbp+40h+var_A0], rax
0x14001eadf  lea     ecx, [r8+8]
0x14001eae3  call    DrvInstActionCallback
0x14001eae8  test    rsi, rsi
0x14001eaeb  jz      short loc_14001EB07
0x14001eaed  cmp     [rsp+140h+Str], 0
0x14001eaf3  jnz     short loc_14001EB07
0x14001eaf5  mov     rcx, cs:hHeap; hHeap
0x14001eafc  mov     r8, rsi; lpMem
0x14001eaff  xor     edx, edx; dwFlags
0x14001eb01  call    cs:__imp_HeapFree
0x14001eb07  test    r12, r12
0x14001eb0a  jz      short loc_14001EB14
0x14001eb0c  mov     rcx, r12
0x14001eb0f  call    FreeDriverNodeInfo
0x14001eb14  mov     eax, ebx
0x14001eb16  mov     rcx, [rbp+40h+var_48]
0x14001eb1a  xor     rcx, rsp; StackCookie
0x14001eb1d  call    __security_check_cookie
0x14001eb22  add     rsp, 108h
0x14001eb29  pop     r15
0x14001eb2b  pop     r14
0x14001eb2d  pop     r13
0x14001eb2f  pop     r12
0x14001eb31  pop     rdi
0x14001eb32  pop     rsi
0x14001eb33  pop     rbx
0x14001eb34  pop     rbp
0x14001eb35  retn
0x14001eb36  xor     r8d, r8d
0x14001eb39  lea     rdx, [rbp+40h+var_C0]
0x14001eb3d  lea     ecx, [r8+3]
0x14001eb41  call    DrvInstActionCallback
0x14001eb46  cmp     dword ptr [rbp+40h+var_A0+8], esi
0x14001eb49  jz      short loc_14001EB55
0x14001eb4b  mov     ebx, 45Bh
0x14001eb50  jmp     loc_14001EA91
0x14001eb55  mov     rsi, [rsp+140h+Str]
0x14001eb5a  test    r12, r12
0x14001eb5d  jz      short loc_14001EBC5
0x14001eb5f  mov     rcx, rsi; Str
0x14001eb62  call    ExtensionsRequireSelection
0x14001eb67  test    eax, eax
0x14001eb69  jz      short loc_14001EBC5
0x14001eb6b  mov     rcx, qword ptr [rsp+140h+var_F0]; int
0x14001eb70  lea     rax, [rsp+140h+var_E0]
0x14001eb75  mov     qword ptr [rsp+140h+ulFlags], r13; unsigned __int64
0x14001eb7a  mov     r9, r12; String1
0x14001eb7d  mov     r8, r15; int
0x14001eb80  mov     [rsp+140h+phkDevice], rax; __int64
0x14001eb85  mov     edx, ebx; int
0x14001eb87  call    SelectExtensionDrivers
0x14001eb8c  test    eax, eax
0x14001eb8e  jnz     short loc_14001EBC0
0x14001eb90  call    cs:__imp_GetLastError
0x14001eb96  mov     dword ptr [rsp+140h+phkDevice], eax
0x14001eb9a  lea     r9, aFailedToSelect; "Failed to select extension INFs for dev"...
0x14001eba1  mov     ebx, eax
0x14001eba3  mov     rcx, r13
0x14001eba6  mov     eax, 1
0x14001ebab  mov     r8d, eax
0x14001ebae  mov     edx, eax
0x14001ebb0  call    cs:__imp_DevRtlWriteTextLog
0x14001ebb6  mov     rsi, [rsp+140h+var_E0]
0x14001ebbb  jmp     loc_14001EA91
0x14001ebc0  mov     rsi, [rsp+140h+var_E0]
0x14001ebc5  mov     rcx, qword ptr [rsp+140h+var_F0]
0x14001ebca  lea     r9, [rsp+140h+var_F8]
0x14001ebcf  mov     r8, rsi
0x14001ebd2  mov     rdx, r12
0x14001ebd5  call    BuildDriverNodeInfo
0x14001ebda  test    eax, eax
0x14001ebdc  jnz     short loc_14001EC0E
0x14001ebde  call    cs:__imp_GetLastError
0x14001ebe4  mov     [rsp+140h+ulFlags], eax
0x14001ebe8  lea     r9, aFailedToResolv_0; "Failed to resolve selected driver node "...
0x14001ebef  mov     rcx, r13
0x14001ebf2  mov     [rsp+140h+phkDevice], rsi
0x14001ebf7  mov     ebx, eax
0x14001ebf9  mov     eax, 1
0x14001ebfe  mov     r8d, eax
0x14001ec01  mov     edx, eax
0x14001ec03  call    cs:__imp_DevRtlWriteTextLog
0x14001ec09  jmp     loc_14001EA91
0x14001ec0e  mov     r12, [rsp+140h+var_F8]
0x14001ec13  mov     r8, r15
0x14001ec16  mov     rcx, qword ptr [rsp+140h+var_F0]
0x14001ec1b  mov     r9, r12
0x14001ec1e  mov     edx, ebx
0x14001ec20  mov     [rsp+140h+var_FC], 0
0x14001ec28  call    LogDeviceInstallStart
0x14001ec2d  mov     ecx, 1
0x14001ec32  lea     rax, [rbp+40h+hKey]
0x14001ec36  mov     [rsp+140h+ulFlags], ecx; ulFlags
0x14001ec3a  mov     r9d, ecx; Disposition
0x14001ec3d  mov     ecx, ebx; dnDevNode
0x14001ec3f  mov     [rsp+140h+phkDevice], rax; phkDevice
0x14001ec44  xor     r8d, r8d; ulHardwareProfile
0x14001ec47  mov     edx, 20019h; samDesired
0x14001ec4c  call    cs:__imp_CM_Open_DevNode_Key
0x14001ec52  test    eax, eax
0x14001ec54  jnz     short loc_14001EC65
0x14001ec56  mov     rcx, [rbp+40h+hKey]; hKey
0x14001ec5a  lea     ebx, [rax+1]
0x14001ec5d  call    cs:__imp_RegCloseKey
0x14001ec63  jmp     short loc_14001EC69
0x14001ec65  mov     ebx, [rsp+140h+var_FC]
0x14001ec69  test    rdi, rdi
0x14001ec6c  jz      short loc_14001EC97
0x14001ec6e  mov     eax, r14d
0x14001ec71  mov     [rdi+0B78h], r14d
0x14001ec78  shr     eax, 12h
0x14001ec7b  lea     rcx, [rdi+0B80h]; lpSystemTimeAsFileTime
0x14001ec82  and     eax, 1
0x14001ec85  mov     [rdi+0B74h], ebx
0x14001ec8b  mov     [rdi+0B7Ch], eax
0x14001ec91  call    cs:__imp_GetSystemTimeAsFileTime
0x14001ec97  mov     rcx, qword ptr [rsp+140h+var_F0]
0x14001ec9c  lea     rax, [rsp+140h+var_100]
0x14001eca1  mov     [rsp+140h+var_110], rax
0x14001eca6  mov     r9d, r14d
0x14001eca9  lea     rax, DrvInstActionCallback
0x14001ecb0  mov     qword ptr [rsp+140h+ulFlags], 0
0x14001ecb9  mov     r8, r12
0x14001ecbc  mov     [rsp+140h+phkDevice], rax
0x14001ecc1  mov     rdx, r15
0x14001ecc4  call    ConfigureDevice
0x14001ecc9  mov     ebx, eax
0x14001eccb  test    rdi, rdi
0x14001ecce  jz      short loc_14001ECF3
0x14001ecd0  lea     rcx, [rdi+0B8Ch]; lpSystemTimeAsFileTime
0x14001ecd7  call    cs:__imp_GetSystemTimeAsFileTime
0x14001ecdd  mov     [rdi+0B94h], ebx
0x14001ece3  mov     eax, [rsp+140h+var_100]
0x14001ece7  shr     eax, 1Eh
0x14001ecea  and     eax, 1
0x14001eced  mov     [rdi+0B88h], eax
0x14001ecf3  test    ebx, ebx
0x14001ecf5  jnz     loc_14001EA96
0x14001ecfb  mov     rax, [rbp+40h+var_88]
0x14001ecff  test    rax, rax
0x14001ed02  jz      loc_14001EA96
0x14001ed08  xorps   xmm0, xmm0
0x14001ed0b  lea     rcx, [rbp+40h+var_78]
0x14001ed0f  mov     [rsp+140h+phkDevice], rcx
0x14001ed14  xor     r9d, r9d
0x14001ed17  movups  [rbp+40h+var_78], xmm0
0x14001ed1b  mov     rcx, rax
0x14001ed1e  mov     dword ptr [rbp+40h+var_78], 30h ; '0'
0x14001ed25  xor     r8d, r8d
0x14001ed28  mov     rdx, r15
0x14001ed2b  movups  [rbp+40h+var_68], xmm0
0x14001ed2f  movups  [rbp+40h+var_58], xmm0
0x14001ed33  call    cs:__imp_DevObjOpenDeviceInfo
0x14001ed39  test    eax, eax
0x14001ed3b  jnz     short loc_14001ED68
0x14001ed3d  call    cs:__imp_GetLastError
0x14001ed43  mov     [rsp+140h+ulFlags], eax
0x14001ed47  lea     r9, aUnableToTrackI; "Unable to track installed device %ws. E"...
0x14001ed4e  mov     rcx, r13
0x14001ed51  mov     [rsp+140h+phkDevice], r15
0x14001ed56  lea     edx, [rbx+1]
0x14001ed59  lea     r8d, [rbx+2]
0x14001ed5d  call    cs:__imp_DevRtlWriteTextLog
0x14001ed63  jmp     loc_14001EA96
0x14001ed68  mov     rcx, qword ptr [rsp+140h+var_D0]; int
0x14001ed6d  test    rcx, rcx
0x14001ed70  jz      loc_14001EA96
0x14001ed76  mov     eax, [rsp+140h+var_100]
0x14001ed7a  and     eax, 40000005h
0x14001ed7f  mov     [rsp+140h+var_D0+4], 0
0x14001ed87  mov     [rsp+140h+var_D0], eax
0x14001ed8b  bt      r14d, 0Ch
0x14001ed90  jnb     short loc_14001ED9A
0x14001ed92  bts     eax, 1Fh
0x14001ed96  mov     [rsp+140h+var_D0], eax
0x14001ed9a  bt      r14d, 1Eh
0x14001ed9f  jnb     loc_14001EA96
0x14001eda5  lea     r9, [rsp+140h+var_D0]
0x14001edaa  mov     [rsp+140h+var_C8], rdi
0x14001edaf  mov     rdx, r15
0x14001edb2  mov     dword ptr [rsp+140h+phkDevice], 10h; size_t
0x14001edba  call    pSetupStringTableAddStringEx
0x14001edbf  cmp     eax, 0FFFFFFFFh
0x14001edc2  jnz     loc_14001EAD0
0x14001edc8  jmp     loc_14001EA96
```
