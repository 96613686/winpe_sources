# UpdateDevicesUsingInf(ushort const *,_ASD_INF_DATA *)

- ea: `0x180039e40`
- end: `0x18003a236`
- name: `?UpdateDevicesUsingInf@@YAHPEBGPEAU_ASD_INF_DATA@@@Z`
- size: `1014`
- prototype: `__int64 __fastcall(wchar_t *Str, struct _ASD_INF_DATA *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180039760`

## callees

- `0x180001008`
- `0x18000119c`
- `0x180001cf0`
- `0x180039c78`
- `0x180039d88`
- `0x180039e40`
- `0x1800543c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180039f87`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003a062`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003a0ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180039f87`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003a062`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003a0ca`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180039ed6`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180039ed6`
- `KERNEL32!GetLastError` at `0x180039eb9`
- `KERNEL32!GetLastError` at `0x180039eb9`
- `KERNEL32!SetLastError` at `0x18003a205`
- `KERNEL32!SetLastError` at `0x18003a205`
- `ADVAPI32!EventUnregister` at `0x18003a1fd`
- `ADVAPI32!EventUnregister` at `0x18003a1fd`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x180039fb7`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x180039fb7`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180039f5c`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18003a043`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18003a0ab`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180039f5c`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18003a043`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18003a0ab`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180039ea7`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180039ea7`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180039f14`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18003a0e4`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180039f14`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18003a0e4`

## string_xrefs

- `0x180039fce`: `Reinstalling device %ws`
- `0x180039fda`: `UpdateDevicesUsingInf`

## pseudocode

```c
_BOOL8 __fastcall UpdateDevicesUsingInf(wchar_t *Str, struct _ASD_INF_DATA *a2)
{
  int v3; // r12d
  __int64 v4; // rsi
  HDEVINFO ClassDevsW; // rdi
  DWORD LastError; // ebx
  wchar_t *v7; // rax
  int v8; // r14d
  int v9; // r13d
  wchar_t *v10; // r15
  BOOL v11; // eax
  int v12; // ecx
  DWORD v13; // edx
  const OLECHAR *v14; // rax
  REGHANDLE v15; // rcx
  DWORD RequiredSize; // [rsp+40h] [rbp-C0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+44h] [rbp-BCh] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD v21; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+54h] [rbp-ACh]
  struct _ASD_INF_DATA *v23; // [rsp+58h] [rbp-A8h]
  _SP_DEVINFO_DATA DeviceInfoData; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+80h] [rbp-80h] BYREF
  int *v26; // [rsp+A0h] [rbp-60h]
  __int64 v27; // [rsp+A8h] [rbp-58h]
  const OLECHAR *v28; // [rsp+B0h] [rbp-50h]
  int v29; // [rsp+B8h] [rbp-48h]
  int v30; // [rsp+BCh] [rbp-44h]
  int *v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+C8h] [rbp-38h]
  DWORD *v33; // [rsp+D0h] [rbp-30h]
  __int64 v34; // [rsp+D8h] [rbp-28h]
  BYTE PropertyBuffer[528]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR DeviceInstanceId[200]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v23 = a2;
  v3 = 0;
  PropertyType = 0;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  RequiredSize = 0;
  TraceLoggingRegister_EventRegister_2U(&dword_180096900);
  v4 = -1;
  ClassDevsW = SetupDiGetClassDevsW(0, 0, 0, 4u);
  if ( ClassDevsW == (HDEVINFO)-1LL )
  {
    LastError = GetLastError();
  }
  else
  {
    DeviceInfoData.cbSize = 32;
    v7 = wcsrchr(Str, 0x5Cu);
    if ( v7 )
    {
      v8 = 2;
      v19 = 0;
      LastError = 0;
      v22 = 0;
      v21 = 0;
      v9 = 1;
      v10 = v7 + 1;
      if ( SetupDiEnumDeviceInfo(ClassDevsW, 0, &DeviceInfoData) )
      {
        do
        {
          if ( SetupDiGetDevicePropertyW(
                 ClassDevsW,
                 &DeviceInfoData,
                 &DEVPKEY_Device_DriverInfPath,
                 &PropertyType,
                 PropertyBuffer,
                 0x104u,
                 &RequiredSize,
                 0)
            && RequiredSize > 2
            && PropertyType == 18
            && !(unsigned int)_o__wcsicmp(PropertyBuffer, v10) )
          {
            v19 = 1;
            if ( SetupDiGetDeviceInstanceIdW(ClassDevsW, &DeviceInfoData, DeviceInstanceId, 0xC8u, 0) )
              AslLogCallPrintf(0, "UpdateDevicesUsingInf", 590, "Reinstalling device %ws", DeviceInstanceId);
            if ( ReinstallDevice(ClassDevsW, &DeviceInfoData, 0) )
              ReinstallDevice(ClassDevsW, &DeviceInfoData, 1);
            if ( LastError )
            {
              LastError = 0;
              if ( SetupDiGetDevicePropertyW(
                     ClassDevsW,
                     &DeviceInfoData,
                     &DEVPKEY_Device_DriverInfPath,
                     &PropertyType,
                     PropertyBuffer,
                     0x104u,
                     &RequiredSize,
                     0)
                && RequiredSize > 2
                && PropertyType == 18
                && (unsigned int)_o__wcsicmp(PropertyBuffer, v10) )
              {
                v3 = 1;
              }
            }
            else if ( SetupDiGetDevicePropertyW(
                        ClassDevsW,
                        &DeviceInfoData,
                        &DEVPKEY_Device_DriverInfPath,
                        &PropertyType,
                        PropertyBuffer,
                        0x104u,
                        &RequiredSize,
                        0)
                   && RequiredSize > 2
                   && PropertyType == 18
                   && !(unsigned int)_o__wcsicmp(PropertyBuffer, v10) )
            {
              v11 = RemoveMSIRegistration();
              if ( v11 )
              {
                LastError = 1;
                v22 = 1;
              }
              v12 = v9 - 1;
              if ( !v11 )
                v12 = v9;
              v9 = v12;
            }
            else
            {
              v3 = 1;
            }
          }
          v13 = v9++;
        }
        while ( SetupDiEnumDeviceInfo(ClassDevsW, v13, &DeviceInfoData) );
        LastError = v21;
        v4 = -1;
      }
      if ( (unsigned int)dword_180096900 > 5
        && (qword_180096910 & 0x200000000000LL) != 0
        && (qword_180096918 & 0x200000000000LL) == qword_180096918 )
      {
        v20 = v22;
        v21 = v3;
        v33 = &v21;
        v14 = (const OLECHAR *)*((_QWORD *)v23 + 2);
        v34 = 4;
        v31 = &v20;
        v32 = 4;
        if ( v14 )
        {
          do
            ++v4;
          while ( v14[v4] );
          v8 = 2 * v4 + 2;
        }
        else
        {
          v14 = &psz;
        }
        v28 = v14;
        v29 = v8;
        v26 = &v19;
        v30 = 0;
        v27 = 4;
        tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180096900, byte_180089329, 0, 0, 6u, &v25);
      }
    }
    else
    {
      LastError = 87;
    }
  }
  v15 = RegHandle;
  dword_180096900 = 0;
  RegHandle = 0;
  EventUnregister(v15);
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180039e40  push    rbp
0x180039e42  push    rbx
0x180039e43  push    rsi
0x180039e44  push    rdi
0x180039e45  push    r12
0x180039e47  push    r13
0x180039e49  push    r14
0x180039e4b  push    r15
0x180039e4d  lea     rbp, [rsp-398h]
0x180039e55  sub     rsp, 498h
0x180039e5c  mov     rax, cs:__security_cookie
0x180039e63  xor     rax, rsp
0x180039e66  mov     [rbp+3D0h+var_50], rax
0x180039e6d  xorps   xmm0, xmm0
0x180039e70  mov     [rsp+4D0h+var_478], rdx
0x180039e75  mov     rbx, rcx
0x180039e78  xor     r12d, r12d
0x180039e7b  lea     rcx, dword_180096900; CallbackContext
0x180039e82  mov     [rsp+4D0h+PropertyType], r12d
0x180039e87  movups  xmmword ptr [rsp+4D0h+DeviceInfoData.cbSize], xmm0
0x180039e8c  mov     [rsp+4D0h+var_490], r12d
0x180039e91  movups  xmmword ptr [rsp+4D0h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x180039e96  call    TraceLoggingRegister_EventRegister_2U
0x180039e9b  lea     r9d, [r12+4]; Flags
0x180039ea0  xor     r8d, r8d; hwndParent
0x180039ea3  xor     edx, edx; Enumerator
0x180039ea5  xor     ecx, ecx; ClassGuid
0x180039ea7  call    cs:__imp_SetupDiGetClassDevsW
0x180039ead  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180039eb1  mov     rdi, rax
0x180039eb4  cmp     rax, rsi
0x180039eb7  jnz     short loc_180039EC6
0x180039eb9  call    cs:__imp_GetLastError
0x180039ebf  mov     ebx, eax
0x180039ec1  jmp     loc_18003A1E8
0x180039ec6  mov     edx, 5Ch ; '\'; Ch
0x180039ecb  mov     [rsp+4D0h+DeviceInfoData.cbSize], 20h ; ' '
0x180039ed3  mov     rcx, rbx; Str
0x180039ed6  call    cs:__imp_wcsrchr
0x180039edc  mov     r15, rax
0x180039edf  test    rax, rax
0x180039ee2  jnz     short loc_180039EEC
0x180039ee4  lea     ebx, [rax+57h]
0x180039ee7  jmp     loc_18003A1E8
0x180039eec  mov     r14d, 2
0x180039ef2  mov     [rsp+4D0h+var_488], r12d
0x180039ef7  mov     ebx, r12d
0x180039efa  mov     [rsp+4D0h+var_47C], r12d
0x180039eff  lea     r8, [rsp+4D0h+DeviceInfoData]; DeviceInfoData
0x180039f04  mov     [rsp+4D0h+var_480], ebx
0x180039f08  xor     edx, edx; MemberIndex
0x180039f0a  mov     rcx, rdi; DeviceInfoSet
0x180039f0d  lea     r13d, [r14-1]
0x180039f11  add     r15, r14
0x180039f14  call    cs:__imp_SetupDiEnumDeviceInfo
0x180039f1a  test    eax, eax
0x180039f1c  jz      loc_18003A0FA
0x180039f22  mov     esi, r13d
0x180039f25  mov     [rsp+4D0h+Flags], 0; Flags
0x180039f2d  lea     rax, [rsp+4D0h+var_490]
0x180039f32  mov     [rsp+4D0h+RequiredSize], rax; RequiredSize
0x180039f37  lea     r9, [rsp+4D0h+PropertyType]; PropertyType
0x180039f3c  lea     rax, [rbp+3D0h+var_3F0]
0x180039f40  mov     [rsp+4D0h+PropertyBufferSize], 104h; PropertyBufferSize
0x180039f48  lea     r8, DEVPKEY_Device_DriverInfPath; PropertyKey
0x180039f4f  mov     [rsp+4D0h+PropertyBuffer], rax; PropertyBuffer
0x180039f54  lea     rdx, [rsp+4D0h+DeviceInfoData]; DeviceInfoData
0x180039f59  mov     rcx, rdi; DeviceInfoSet
0x180039f5c  call    cs:__imp_SetupDiGetDevicePropertyW
0x180039f62  test    eax, eax
0x180039f64  jz      loc_18003A0D6
0x180039f6a  cmp     [rsp+4D0h+var_490], r14d
0x180039f6f  jbe     loc_18003A0D6
0x180039f75  cmp     [rsp+4D0h+PropertyType], 12h
0x180039f7a  jnz     loc_18003A0D6
0x180039f80  mov     rdx, r15
0x180039f83  lea     rcx, [rbp+3D0h+var_3F0]
0x180039f87  call    cs:__imp__o__wcsicmp
0x180039f8d  test    eax, eax
0x180039f8f  jnz     loc_18003A0D6
0x180039f95  mov     r9d, 0C8h; DeviceInstanceIdSize
0x180039f9b  mov     [rsp+4D0h+var_488], esi
0x180039f9f  lea     r8, [rbp+3D0h+DeviceInstanceId]; DeviceInstanceId
0x180039fa6  mov     [rsp+4D0h+PropertyBuffer], 0; RequiredSize
0x180039faf  lea     rdx, [rsp+4D0h+DeviceInfoData]; DeviceInfoData
0x180039fb4  mov     rcx, rdi; DeviceInfoSet
0x180039fb7  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x180039fbd  test    eax, eax
0x180039fbf  jz      short loc_180039FE8
0x180039fc1  lea     rax, [rbp+3D0h+DeviceInstanceId]
0x180039fc8  mov     r8d, 24Eh
0x180039fce  lea     r9, aReinstallingDe; "Reinstalling device %ws"
0x180039fd5  mov     [rsp+4D0h+PropertyBuffer], rax
0x180039fda  lea     rdx, aUpdatedevicesu; "UpdateDevicesUsingInf"
0x180039fe1  xor     ecx, ecx
0x180039fe3  call    AslLogCallPrintf
0x180039fe8  xor     r8d, r8d; int
0x180039feb  lea     rdx, [rsp+4D0h+DeviceInfoData]; DeviceInfoData
0x180039ff0  mov     rcx, rdi; DeviceInfoSet
0x180039ff3  call    ?ReinstallDevice@@YAHPEAXPEAU_SP_DEVINFO_DATA@@H@Z; ReinstallDevice(void *,_SP_DEVINFO_DATA *,int)
0x180039ff8  test    eax, eax
0x180039ffa  jz      short loc_18003A00C
0x180039ffc  mov     r8d, esi; int
0x180039fff  lea     rdx, [rsp+4D0h+DeviceInfoData]; DeviceInfoData
0x18003a004  mov     rcx, rdi; DeviceInfoSet
0x18003a007  call    ?ReinstallDevice@@YAHPEAXPEAU_SP_DEVINFO_DATA@@H@Z; ReinstallDevice(void *,_SP_DEVINFO_DATA *,int)
0x18003a00c  lea     rax, [rsp+4D0h+var_490]
0x18003a011  mov     rcx, rdi; DeviceInfoSet
0x18003a014  lea     r9, [rsp+4D0h+PropertyType]; PropertyType
0x18003a019  lea     r8, DEVPKEY_Device_DriverInfPath; PropertyKey
0x18003a020  lea     rdx, [rsp+4D0h+DeviceInfoData]; DeviceInfoData
0x18003a025  test    ebx, ebx
0x18003a027  jnz     short loc_18003A08F
0x18003a029  mov     [rsp+4D0h+Flags], ebx; Flags
0x18003a02d  mov     [rsp+4D0h+RequiredSize], rax; RequiredSize
0x18003a032  lea     rax, [rbp+3D0h+var_3F0]
0x18003a036  mov     [rsp+4D0h+PropertyBufferSize], 104h; PropertyBufferSize
0x18003a03e  mov     [rsp+4D0h+PropertyBuffer], rax; PropertyBuffer
0x18003a043  call    cs:__imp_SetupDiGetDevicePropertyW
0x18003a049  test    eax, eax
0x18003a04b  jz      short loc_18003A08A
0x18003a04d  cmp     [rsp+4D0h+var_490], r14d
0x18003a052  jbe     short loc_18003A08A
0x18003a054  cmp     [rsp+4D0h+PropertyType], 12h
0x18003a059  jnz     short loc_18003A08A
0x18003a05b  mov     rdx, r15
0x18003a05e  lea     rcx, [rbp+3D0h+var_3F0]
0x18003a062  call    cs:__imp__o__wcsicmp
0x18003a068  test    eax, eax
0x18003a06a  jnz     short loc_18003A08A
0x18003a06c  call    ?RemoveMSIRegistration@@YAHXZ; RemoveMSIRegistration(void)
0x18003a071  test    eax, eax
0x18003a073  jz      short loc_18003A07B
0x18003a075  mov     ebx, esi
0x18003a077  mov     [rsp+4D0h+var_47C], esi
0x18003a07b  lea     ecx, [r13-1]
0x18003a07f  test    eax, eax
0x18003a081  cmovz   ecx, r13d
0x18003a085  mov     r13d, ecx
0x18003a088  jmp     short loc_18003A0D6
0x18003a08a  mov     r12d, esi
0x18003a08d  jmp     short loc_18003A0D6
0x18003a08f  xor     ebx, ebx
0x18003a091  mov     [rsp+4D0h+Flags], ebx; Flags
0x18003a095  mov     [rsp+4D0h+RequiredSize], rax; RequiredSize
0x18003a09a  lea     rax, [rbp+3D0h+var_3F0]
0x18003a09e  mov     [rsp+4D0h+PropertyBufferSize], 104h; PropertyBufferSize
0x18003a0a6  mov     [rsp+4D0h+PropertyBuffer], rax; PropertyBuffer
0x18003a0ab  call    cs:__imp_SetupDiGetDevicePropertyW
0x18003a0b1  test    eax, eax
0x18003a0b3  jz      short loc_18003A0D6
0x18003a0b5  cmp     [rsp+4D0h+var_490], r14d
0x18003a0ba  jbe     short loc_18003A0D6
0x18003a0bc  cmp     [rsp+4D0h+PropertyType], 12h
0x18003a0c1  jnz     short loc_18003A0D6
0x18003a0c3  mov     rdx, r15
0x18003a0c6  lea     rcx, [rbp+3D0h+var_3F0]
0x18003a0ca  call    cs:__imp__o__wcsicmp
0x18003a0d0  test    eax, eax
0x18003a0d2  cmovnz  r12d, esi
0x18003a0d6  mov     edx, r13d; MemberIndex
0x18003a0d9  lea     r8, [rsp+4D0h+DeviceInfoData]; DeviceInfoData
0x18003a0de  mov     rcx, rdi; DeviceInfoSet
0x18003a0e1  add     r13d, esi
0x18003a0e4  call    cs:__imp_SetupDiEnumDeviceInfo
0x18003a0ea  test    eax, eax
0x18003a0ec  jnz     loc_180039F25
0x18003a0f2  mov     ebx, [rsp+4D0h+var_480]
0x18003a0f6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003a0fa  mov     eax, cs:dword_180096900
0x18003a100  cmp     eax, 5
0x18003a103  jbe     loc_18003A1E5
0x18003a109  mov     rcx, cs:qword_180096918
0x18003a110  mov     rdx, 200000000000h
0x18003a11a  mov     rax, cs:qword_180096910
0x18003a121  test    rdx, rax
0x18003a124  jz      loc_18003A1E5
0x18003a12a  mov     rax, rcx
0x18003a12d  and     rax, rdx
0x18003a130  cmp     rax, rcx
0x18003a133  jnz     loc_18003A1E5
0x18003a139  mov     eax, [rsp+4D0h+var_47C]
0x18003a13d  mov     ecx, [rsp+4D0h+var_488]
0x18003a141  mov     [rsp+4D0h+var_484], eax
0x18003a145  mov     rax, [rsp+4D0h+var_478]
0x18003a14a  mov     [rsp+4D0h+var_488], ecx
0x18003a14e  lea     rcx, [rsp+4D0h+var_480]
0x18003a153  mov     [rsp+4D0h+var_480], r12d
0x18003a158  xor     r12d, r12d
0x18003a15b  mov     [rbp+3D0h+var_400], rcx
0x18003a15f  lea     rcx, [rsp+4D0h+var_484]
0x18003a164  mov     rax, [rax+10h]
0x18003a168  mov     [rbp+3D0h+var_3F8], 4
0x18003a170  mov     [rbp+3D0h+var_410], rcx
0x18003a174  mov     [rbp+3D0h+var_408], 4
0x18003a17c  test    rax, rax
0x18003a17f  jz      short loc_18003A195
0x18003a181  inc     rsi
0x18003a184  cmp     [rax+rsi*2], r12w
0x18003a189  jnz     short loc_18003A181
0x18003a18b  lea     r14d, ds:2[rsi*2]
0x18003a193  jmp     short loc_18003A19C
0x18003a195  lea     rax, psz
0x18003a19c  mov     [rbp+3D0h+var_420], rax
0x18003a1a0  lea     rdx, byte_180089329
0x18003a1a7  lea     rax, [rsp+4D0h+var_488]
0x18003a1ac  mov     [rbp+3D0h+var_418], r14d
0x18003a1b0  mov     [rbp+3D0h+var_430], rax
0x18003a1b4  lea     rcx, dword_180096900
0x18003a1bb  lea     rax, [rbp+3D0h+var_450]
0x18003a1bf  mov     [rbp+3D0h+var_414], r12d
0x18003a1c3  mov     qword ptr [rsp+4D0h+PropertyBufferSize], rax
0x18003a1c8  xor     r9d, r9d
0x18003a1cb  xor     r8d, r8d
0x18003a1ce  mov     dword ptr [rsp+4D0h+PropertyBuffer], 6
0x18003a1d6  mov     [rbp+3D0h+var_428], 4
0x18003a1de  call    _tlgWriteTransfer_EventWriteTransfer
0x18003a1e3  jmp     short loc_18003A1E8
0x18003a1e5  xor     r12d, r12d
0x18003a1e8  mov     rcx, cs:RegHandle; RegHandle
0x18003a1ef  mov     cs:dword_180096900, r12d
0x18003a1f6  mov     cs:RegHandle, r12
0x18003a1fd  call    cs:__imp_EventUnregister
0x18003a203  mov     ecx, ebx; dwErrCode
0x18003a205  call    cs:__imp_SetLastError
0x18003a20b  test    ebx, ebx
0x18003a20d  mov     eax, r12d
0x18003a210  setz    al
0x18003a213  mov     rcx, [rbp+3D0h+var_50]
0x18003a21a  xor     rcx, rsp; StackCookie
0x18003a21d  call    __security_check_cookie
0x18003a222  add     rsp, 498h
0x18003a229  pop     r15
0x18003a22b  pop     r14
0x18003a22d  pop     r13
0x18003a22f  pop     r12
0x18003a231  pop     rdi
0x18003a232  pop     rsi
0x18003a233  pop     rbx
0x18003a234  pop     rbp
0x18003a235  retn
```
