# PnpUtilsCreateExclusionDeviceDescriptor(ulong,_DRVUTILS_UPDATE_INFO *,_DRIVERSTORE_DEVICE_DESCRIPTORW *)

- ea: `0x140029764`
- end: `0x1400298e3`
- name: `?PnpUtilsCreateExclusionDeviceDescriptor@@YAHKPEAU_DRVUTILS_UPDATE_INFO@@PEAU_DRIVERSTORE_DEVICE_DESCRIPTORW@@@Z`
- size: `383`
- prototype: `_BOOL8 __fastcall(DEVINST dnDevInst, struct _DRVUTILS_UPDATE_INFO *, struct _DRIVERSTORE_DEVICE_DESCRIPTORW *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x14002c2bc`

## callees

- `0x14002405c`
- `0x1400240b8`
- `0x140026b08`
- `0x140026bec`
- `0x140029764`
- `0x14002b434`
- `0x14002b748`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140029808`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140029850`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140029808`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140029850`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400297c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400297c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029833`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400298bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400298bd`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002988f`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002988f`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140029797`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140029797`

## string_xrefs

- `0x140029876`: `Unable to populate installed extension drivers. Error = 0x%08X`
- `0x14002983b`: `Unable to determine the driver INFs installed on the device. Error = 0x%08X`

## pseudocode

```c
_BOOL8 __fastcall PnpUtilsCreateExclusionDeviceDescriptor(
        DEVINST dnDevInst,
        struct _DRVUTILS_UPDATE_INFO *a2,
        struct _DRIVERSTORE_DEVICE_DESCRIPTORW *a3)
{
  int v6; // r14d
  __int64 ThreadLogToken; // r15
  DWORD LastError; // ebx
  __int64 v9; // r8
  LPVOID *v10; // rsi
  DWORD v11; // eax
  const char *v12; // r9
  __int64 v13; // rdx
  DWORD v15; // [rsp+20h] [rbp-30h]
  __int128 v16; // [rsp+30h] [rbp-20h] BYREF
  __int128 v17; // [rsp+40h] [rbp-10h]
  int v18; // [rsp+98h] [rbp+48h] BYREF

  v18 = 0;
  v6 = 1;
  ThreadLogToken = DevRtlGetThreadLogToken();
  v16 = 0;
  v17 = 0;
  if ( !(unsigned int)PnpUtilsCreateDeviceDescriptor(dnDevInst) )
  {
    v6 = 0;
    LastError = GetLastError();
    goto LABEL_13;
  }
  v9 = *((_QWORD *)a3 + 4);
  v10 = (LPVOID *)((char *)a3 + 40);
  LastError = 0;
  *(_QWORD *)&v17 = *((_QWORD *)a3 + 5);
  *((_QWORD *)&v17 + 1) = ThreadLogToken;
  if ( v9 && !(unsigned int)DrvUtilsUpdateInfoContainsDriverInf(a2, 1, v9) )
  {
    HeapFree(hHeap, 0, *((LPVOID *)a3 + 4));
    *((_QWORD *)a3 + 4) = 0;
  }
  if ( *v10 )
  {
    if ( !(unsigned int)DrvUtilsUpdateInfoEnumDriverInfs(a2, 2, ExcludedExtensionInfCallback, &v16) )
    {
      v11 = GetLastError();
      LastError = v11;
      v12 = "Unable to determine the driver INFs installed on the device. Error = 0x%08X";
LABEL_12:
      v15 = v11;
      DevRtlWriteTextLog(ThreadLogToken, 512, 2, v12, v15);
      goto LABEL_13;
    }
    HeapFree(hHeap, 0, *v10);
    v13 = DWORD2(v16);
    *v10 = 0;
    if ( (_DWORD)v13 )
    {
      v11 = pSetupStringArrayToMultiSz(v16, v13, (char *)a3 + 40, &v18);
      LastError = v11;
      if ( v11 )
      {
        v12 = "Unable to populate installed extension drivers. Error = 0x%08X";
        goto LABEL_12;
      }
    }
  }
LABEL_13:
  if ( DWORD2(v16) )
    pSetupFreeStringArray(v16);
  if ( v6 && LastError && a3 )
    PnpUtilsDestroyDeviceDescriptor(a3);
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x140029764  mov     [rsp-28h+arg_0], rbx
0x140029769  mov     [rsp-28h+arg_8], rsi
0x14002976e  push    rbp
0x14002976f  push    rdi
0x140029770  push    r12
0x140029772  push    r14
0x140029774  push    r15
0x140029776  mov     rbp, rsp
0x140029779  sub     rsp, 50h
0x14002977d  xorps   xmm0, xmm0
0x140029780  mov     [rbp+arg_18], 0
0x140029787  movups  [rbp+var_20], xmm0
0x14002978b  mov     rdi, r8
0x14002978e  mov     r12, rdx
0x140029791  movups  [rbp+var_10], xmm0
0x140029795  mov     ebx, ecx
0x140029797  call    cs:__imp_DevRtlGetThreadLogToken
0x14002979d  xorps   xmm0, xmm0
0x1400297a0  mov     r14d, 1
0x1400297a6  mov     r8d, r14d
0x1400297a9  mov     rdx, rdi
0x1400297ac  mov     ecx, ebx; dnDevInst
0x1400297ae  mov     r15, rax
0x1400297b1  movups  [rbp+var_20], xmm0
0x1400297b5  movups  [rbp+var_10], xmm0
0x1400297b9  call    PnpUtilsCreateDeviceDescriptor
0x1400297be  test    eax, eax
0x1400297c0  jnz     short loc_1400297D2
0x1400297c2  xor     r14d, r14d
0x1400297c5  call    cs:__imp_GetLastError
0x1400297cb  mov     ebx, eax
0x1400297cd  jmp     loc_140029895
0x1400297d2  mov     r8, [rdi+20h]
0x1400297d6  lea     rsi, [rdi+28h]
0x1400297da  mov     rax, [rsi]
0x1400297dd  xor     ebx, ebx
0x1400297df  mov     qword ptr [rbp+var_10], rax
0x1400297e3  mov     qword ptr [rbp+var_10+8], r15
0x1400297e7  test    r8, r8
0x1400297ea  jz      short loc_140029812
0x1400297ec  mov     edx, r14d
0x1400297ef  mov     rcx, r12
0x1400297f2  call    DrvUtilsUpdateInfoContainsDriverInf
0x1400297f7  test    eax, eax
0x1400297f9  jnz     short loc_140029812
0x1400297fb  mov     r8, [rdi+20h]; lpMem
0x1400297ff  xor     edx, edx; dwFlags
0x140029801  mov     rcx, cs:hHeap; hHeap
0x140029808  call    cs:__imp_HeapFree
0x14002980e  mov     [rdi+20h], rbx
0x140029812  cmp     [rsi], rbx
0x140029815  jz      short loc_140029895
0x140029817  lea     r9, [rbp+var_20]
0x14002981b  mov     edx, 2
0x140029820  lea     r8, ?ExcludedExtensionInfCallback@@YAHPEAU_DRVUTILS_UPDATE_INFO@@PEBGW4_DRVUTILS_UPDATE_INFO_DRIVER_FLAG@@W4_DRVUTILS_DRIVER_TYPE_FLAG@@_J@Z; ExcludedExtensionInfCallback(_DRVUTILS_UPDATE_INFO *,ushort const *,_DRVUTILS_UPDATE_INFO_DRIVER_FLAG,_DRVUTILS_DRIVER_TYPE_FLAG,__int64)
0x140029827  mov     rcx, r12
0x14002982a  call    DrvUtilsUpdateInfoEnumDriverInfs
0x14002982f  test    eax, eax
0x140029831  jnz     short loc_140029844
0x140029833  call    cs:__imp_GetLastError
0x140029839  mov     ebx, eax
0x14002983b  lea     r9, aUnableToDeterm_10; "Unable to determine the driver INFs ins"...
0x140029842  jmp     short loc_14002987D
0x140029844  mov     r8, [rsi]; lpMem
0x140029847  xor     edx, edx; dwFlags
0x140029849  mov     rcx, cs:hHeap; hHeap
0x140029850  call    cs:__imp_HeapFree
0x140029856  mov     edx, dword ptr [rbp+var_20+8]
0x140029859  mov     [rsi], rbx
0x14002985c  test    edx, edx
0x14002985e  jz      short loc_140029895
0x140029860  mov     rcx, qword ptr [rbp+var_20]
0x140029864  lea     r9, [rbp+arg_18]
0x140029868  mov     r8, rsi
0x14002986b  call    pSetupStringArrayToMultiSz
0x140029870  mov     ebx, eax
0x140029872  test    eax, eax
0x140029874  jz      short loc_140029895
0x140029876  lea     r9, aUnableToPopula_0; "Unable to populate installed extension "...
0x14002987d  mov     r8d, 2
0x140029883  mov     [rsp+50h+var_30], eax
0x140029887  mov     edx, 200h
0x14002988c  mov     rcx, r15
0x14002988f  call    cs:__imp_DevRtlWriteTextLog
0x140029895  mov     edx, dword ptr [rbp+var_20+8]
0x140029898  test    edx, edx
0x14002989a  jz      short loc_1400298A5
0x14002989c  mov     rcx, qword ptr [rbp+var_20]
0x1400298a0  call    pSetupFreeStringArray
0x1400298a5  test    r14d, r14d
0x1400298a8  jz      short loc_1400298BB
0x1400298aa  test    ebx, ebx
0x1400298ac  jz      short loc_1400298BB
0x1400298ae  test    rdi, rdi
0x1400298b1  jz      short loc_1400298BB
0x1400298b3  mov     rcx, rdi
0x1400298b6  call    PnpUtilsDestroyDeviceDescriptor
0x1400298bb  mov     ecx, ebx; dwErrCode
0x1400298bd  call    cs:__imp_SetLastError
0x1400298c3  xor     eax, eax
0x1400298c5  lea     r11, [rsp+50h+var_s0]
0x1400298ca  mov     rsi, [r11+38h]
0x1400298ce  test    ebx, ebx
0x1400298d0  mov     rbx, [r11+30h]
0x1400298d4  setz    al
0x1400298d7  mov     rsp, r11
0x1400298da  pop     r15
0x1400298dc  pop     r14
0x1400298de  pop     r12
0x1400298e0  pop     rdi
0x1400298e1  pop     rbp
0x1400298e2  retn
```
