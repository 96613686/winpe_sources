# PnpUtilsCreateSelectionDeviceDescriptor(HDRIVERSTORE__ *,ulong,_DRVUTILS_UPDATE_INFO *,_DRIVERSTORE_DEVICE_DESCRIPTORW *)

- ea: `0x1400298ec`
- end: `0x140029a36`
- name: `?PnpUtilsCreateSelectionDeviceDescriptor@@YAHPEAUHDRIVERSTORE__@@KPEAU_DRVUTILS_UPDATE_INFO@@PEAU_DRIVERSTORE_DEVICE_DESCRIPTORW@@@Z`
- size: `330`
- prototype: `_BOOL8 __fastcall(struct HDRIVERSTORE__ *, DEVINST, struct _DRVUTILS_UPDATE_INFO *, struct _DRIVERSTORE_DEVICE_DESCRIPTORW *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x14002c2bc`

## callees

- `0x14002405c`
- `0x1400240b8`
- `0x140026bec`
- `0x1400298ec`
- `0x14002b434`
- `0x14002b748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002995b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002995b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140029a1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140029a1c`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400299aa`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400299ef`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400299aa`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400299ef`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14002991d`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14002991d`

## string_xrefs

- `0x1400299d6`: `Unable to populate device descriptor with specified extension INFs. Error = 0x%08X`

## pseudocode

```c
_BOOL8 __fastcall PnpUtilsCreateSelectionDeviceDescriptor(
        struct HDRIVERSTORE__ *a1,
        DEVINST a2,
        struct _DRVUTILS_UPDATE_INFO *a3,
        struct _DRIVERSTORE_DEVICE_DESCRIPTORW *a4)
{
  __int64 ThreadLogToken; // r14
  int v7; // edi
  DWORD LastError; // ebx
  __int64 v9; // rdx
  DWORD v10; // eax
  struct HDRIVERSTORE__ *v12; // [rsp+30h] [rbp-38h] BYREF
  DEVINST v13; // [rsp+38h] [rbp-30h]
  _DWORD v14[7]; // [rsp+3Ch] [rbp-2Ch] BYREF
  __int64 v15; // [rsp+58h] [rbp-10h]
  int v16; // [rsp+A8h] [rbp+40h] BYREF

  v16 = 0;
  v12 = a1;
  v13 = a2;
  memset(v14, 0, sizeof(v14));
  ThreadLogToken = DevRtlGetThreadLogToken();
  v15 = ThreadLogToken;
  if ( !(unsigned int)PnpUtilsCreateDeviceDescriptor(v13) )
  {
    v7 = 0;
LABEL_3:
    LastError = GetLastError();
    goto LABEL_11;
  }
  v7 = 1;
  if ( !(unsigned int)DrvUtilsUpdateInfoEnumDriverInfs(a3, 3, &PnpUtilsSelectionInfCallback, &v12) )
    goto LABEL_3;
  v9 = v14[5];
  if ( *(_QWORD *)&v14[1] || v14[5] )
  {
    LastError = 0;
    *((_QWORD *)a4 + 4) = *(_QWORD *)&v14[1];
    if ( !(_DWORD)v9 )
      goto LABEL_17;
    v10 = pSetupStringArrayToMultiSz(*(_QWORD *)&v14[3], v9, (char *)a4 + 40, &v16);
    LastError = v10;
    if ( v10 )
      DevRtlWriteTextLog(
        ThreadLogToken,
        512,
        2,
        "Unable to populate device descriptor with specified extension INFs. Error = 0x%08X",
        v10);
  }
  else
  {
    DevRtlWriteTextLog(ThreadLogToken, 512, 2, "Specified drivers do not contain a match for this device");
    LastError = 13;
  }
LABEL_11:
  if ( v14[5] )
    pSetupFreeStringArray(*(_QWORD *)&v14[3]);
  if ( v7 && LastError && a4 )
    PnpUtilsDestroyDeviceDescriptor(a4);
LABEL_17:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x1400298ec  push    rbp
0x1400298ee  push    rbx
0x1400298ef  push    rsi
0x1400298f0  push    rdi
0x1400298f1  push    r14
0x1400298f3  push    r15
0x1400298f5  mov     rbp, rsp
0x1400298f8  sub     rsp, 68h
0x1400298fc  xorps   xmm0, xmm0
0x1400298ff  mov     [rbp+arg_8], 0
0x140029906  movups  [rbp+var_38], xmm0
0x14002990a  mov     rsi, r9
0x14002990d  mov     r15, r8
0x140029910  movups  [rbp+var_28], xmm0
0x140029914  mov     edi, edx
0x140029916  mov     rbx, rcx
0x140029919  movups  xmmword ptr [rbp+var_18], xmm0
0x14002991d  call    cs:__imp_DevRtlGetThreadLogToken
0x140029923  xorps   xmm0, xmm0
0x140029926  mov     qword ptr [rbp+var_28+0Ch], 0
0x14002992e  xor     r8d, r8d
0x140029931  mov     dword ptr [rbp+var_18+4], 0
0x140029938  mov     rdx, rsi
0x14002993b  mov     qword ptr [rbp+var_38], rbx
0x14002993f  mov     ecx, edi; dnDevInst
0x140029941  mov     dword ptr [rbp+var_38+8], edi
0x140029944  movdqu  [rbp+var_38+0Ch], xmm0
0x140029949  mov     r14, rax
0x14002994c  mov     [rbp+var_18+8], rax
0x140029950  call    PnpUtilsCreateDeviceDescriptor
0x140029955  test    eax, eax
0x140029957  jnz     short loc_140029968
0x140029959  xor     edi, edi
0x14002995b  call    cs:__imp_GetLastError
0x140029961  mov     ebx, eax
0x140029963  jmp     loc_1400299F5
0x140029968  mov     edi, 1
0x14002996d  lea     r9, [rbp+var_38]
0x140029971  lea     r8, ?PnpUtilsSelectionInfCallback@@YAHPEAU_DRVUTILS_UPDATE_INFO@@PEBGW4_DRVUTILS_UPDATE_INFO_DRIVER_FLAG@@W4_DRVUTILS_DRIVER_TYPE_FLAG@@_J@Z; PnpUtilsSelectionInfCallback(_DRVUTILS_UPDATE_INFO *,ushort const *,_DRVUTILS_UPDATE_INFO_DRIVER_FLAG,_DRVUTILS_DRIVER_TYPE_FLAG,__int64)
0x140029978  mov     rcx, r15
0x14002997b  lea     edx, [rdi+2]
0x14002997e  call    DrvUtilsUpdateInfoEnumDriverInfs
0x140029983  test    eax, eax
0x140029985  jz      short loc_14002995B
0x140029987  mov     rax, qword ptr [rbp+var_28]
0x14002998b  mov     edx, dword ptr [rbp+var_18]
0x14002998e  test    rax, rax
0x140029991  jnz     short loc_1400299B5
0x140029993  test    edx, edx
0x140029995  jnz     short loc_1400299B5
0x140029997  lea     r9, aSpecifiedDrive; "Specified drivers do not contain a matc"...
0x14002999e  mov     edx, 200h
0x1400299a3  lea     r8d, [rdi+1]
0x1400299a7  mov     rcx, r14
0x1400299aa  call    cs:__imp_DevRtlWriteTextLog
0x1400299b0  lea     ebx, [rdi+0Ch]
0x1400299b3  jmp     short loc_1400299F5
0x1400299b5  xor     ebx, ebx
0x1400299b7  mov     [rsi+20h], rax
0x1400299bb  test    edx, edx
0x1400299bd  jz      short loc_140029A1A
0x1400299bf  mov     rcx, qword ptr [rbp+var_28+8]
0x1400299c3  lea     r8, [rsi+28h]
0x1400299c7  lea     r9, [rbp+arg_8]
0x1400299cb  call    pSetupStringArrayToMultiSz
0x1400299d0  mov     ebx, eax
0x1400299d2  test    eax, eax
0x1400299d4  jz      short loc_1400299F5
0x1400299d6  lea     r9, aUnableToPopula; "Unable to populate device descriptor wi"...
0x1400299dd  mov     [rsp+68h+var_48], eax
0x1400299e1  mov     edx, 200h
0x1400299e6  mov     r8d, 2
0x1400299ec  mov     rcx, r14
0x1400299ef  call    cs:__imp_DevRtlWriteTextLog
0x1400299f5  mov     edx, dword ptr [rbp+var_18]
0x1400299f8  test    edx, edx
0x1400299fa  jz      short loc_140029A05
0x1400299fc  mov     rcx, qword ptr [rbp+var_28+8]
0x140029a00  call    pSetupFreeStringArray
0x140029a05  test    edi, edi
0x140029a07  jz      short loc_140029A1A
0x140029a09  test    ebx, ebx
0x140029a0b  jz      short loc_140029A1A
0x140029a0d  test    rsi, rsi
0x140029a10  jz      short loc_140029A1A
0x140029a12  mov     rcx, rsi
0x140029a15  call    PnpUtilsDestroyDeviceDescriptor
0x140029a1a  mov     ecx, ebx; dwErrCode
0x140029a1c  call    cs:__imp_SetLastError
0x140029a22  xor     eax, eax
0x140029a24  test    ebx, ebx
0x140029a26  setz    al
0x140029a29  add     rsp, 68h
0x140029a2d  pop     r15
0x140029a2f  pop     r14
0x140029a31  pop     rdi
0x140029a32  pop     rsi
0x140029a33  pop     rbx
0x140029a34  pop     rbp
0x140029a35  retn
```
