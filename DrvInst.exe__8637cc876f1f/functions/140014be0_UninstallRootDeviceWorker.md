# UninstallRootDeviceWorker

- ea: `0x140014be0`
- end: `0x140014d38`
- name: `UninstallRootDeviceWorker`
- size: `344`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callees

- `0x140014be0`
- `0x140018dc0`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014c4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014c81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014c4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014c81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014cdb`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014ca0`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014cff`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014ca0`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014cff`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x140014c77`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x140014c77`
- `DEVOBJ!DevObjDeleteDevice` at `0x140014cd1`
- `DEVOBJ!DevObjDeleteDevice` at `0x140014cd1`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140014c3f`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140014c3f`

## string_xrefs

- `0x140014c8b`: `Failed to open device. Error = 0x%08X`
- `0x140014ca8`: `RootDevice_Delete`
- `0x140014ce5`: `Failed to remove device '%ws'. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall UninstallRootDeviceWorker(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 DeviceInfoList; // rsi
  DWORD LastError; // ebx
  _OWORD v10[2]; // [rsp+30h] [rbp-31h] BYREF
  __int128 v11; // [rsp+50h] [rbp-11h]
  _OWORD v12[3]; // [rsp+60h] [rbp-1h] BYREF

  memset(v12, 0, sizeof(v12));
  memset(v10, 0, sizeof(v10));
  v11 = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList == -1 )
  {
    return GetLastError();
  }
  else
  {
    LODWORD(v12[0]) = 48;
    if ( (unsigned int)DevObjOpenDeviceInfo(DeviceInfoList, a1, 0, 0, v12) )
    {
      LastError = 0;
      *(_QWORD *)&v11 = L"RootDevice_Delete";
      DrvInstActionCallback(17, (unsigned int *)v10);
      if ( !(unsigned int)DevObjDeleteDevice(DeviceInfoList, v12, 0, a4) )
      {
        LastError = GetLastError();
        DevRtlWriteTextLog(a5, 1, 1, "Failed to remove device '%ws'. Error = 0x%08X", a1, LastError);
      }
      DrvInstActionCallback(18, 0);
    }
    else
    {
      LastError = GetLastError();
      DevRtlWriteTextLog(a5, 1, 1, "Failed to open device. Error = 0x%08X", LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x140014be0  mov     [rsp-8+arg_8], rbx
0x140014be5  mov     [rsp-8+arg_10], rsi
0x140014bea  push    rbp
0x140014beb  push    rdi
0x140014bec  push    r14
0x140014bee  lea     rbp, [rsp-3Fh]
0x140014bf3  sub     rsp, 0A0h
0x140014bfa  mov     rax, cs:__security_cookie
0x140014c01  xor     rax, rsp
0x140014c04  mov     [rbp+4Fh+var_20], rax
0x140014c08  xorps   xmm0, xmm0
0x140014c0b  mov     [rsp+0B0h+var_90], 0
0x140014c14  xorps   xmm1, xmm1
0x140014c17  mov     r14, r9
0x140014c1a  mov     rdi, rcx
0x140014c1d  xor     r9d, r9d
0x140014c20  xor     ecx, ecx
0x140014c22  xor     r8d, r8d
0x140014c25  xor     edx, edx
0x140014c27  movups  [rbp+4Fh+var_50], xmm0
0x140014c2b  movups  [rbp+4Fh+var_40], xmm0
0x140014c2f  movups  [rbp+4Fh+var_30], xmm0
0x140014c33  movups  [rbp+4Fh+var_80], xmm1
0x140014c37  movups  [rbp+4Fh+var_70], xmm1
0x140014c3b  movups  [rbp+4Fh+var_60], xmm1
0x140014c3f  call    cs:__imp_DevObjCreateDeviceInfoList
0x140014c45  mov     rsi, rax
0x140014c48  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140014c4c  jnz     short loc_140014C5B
0x140014c4e  call    cs:__imp_GetLastError
0x140014c54  mov     ebx, eax
0x140014c56  jmp     loc_140014D12
0x140014c5b  lea     rax, [rbp+4Fh+var_50]
0x140014c5f  mov     dword ptr [rbp+4Fh+var_50], 30h ; '0'
0x140014c66  xor     r9d, r9d
0x140014c69  mov     [rsp+0B0h+var_90], rax
0x140014c6e  xor     r8d, r8d
0x140014c71  mov     rdx, rdi
0x140014c74  mov     rcx, rsi
0x140014c77  call    cs:__imp_DevObjOpenDeviceInfo
0x140014c7d  test    eax, eax
0x140014c7f  jnz     short loc_140014CA8
0x140014c81  call    cs:__imp_GetLastError
0x140014c87  mov     rcx, [rbp+4Fh+arg_20]
0x140014c8b  lea     r9, aFailedToOpenDe_0; "Failed to open device. Error = 0x%08X"
0x140014c92  mov     edx, 1
0x140014c97  mov     dword ptr [rsp+0B0h+var_90], eax
0x140014c9b  mov     r8d, edx
0x140014c9e  mov     ebx, eax
0x140014ca0  call    cs:__imp_DevRtlWriteTextLog
0x140014ca6  jmp     short loc_140014D12
0x140014ca8  lea     rax, aRootdeviceDele; "RootDevice_Delete"
0x140014caf  xor     ebx, ebx
0x140014cb1  xor     r8d, r8d
0x140014cb4  mov     qword ptr [rbp+4Fh+var_60], rax
0x140014cb8  lea     rdx, [rbp+4Fh+var_80]
0x140014cbc  lea     ecx, [rbx+11h]
0x140014cbf  call    DrvInstActionCallback
0x140014cc4  mov     r9, r14
0x140014cc7  lea     rdx, [rbp+4Fh+var_50]
0x140014ccb  xor     r8d, r8d
0x140014cce  mov     rcx, rsi
0x140014cd1  call    cs:__imp_DevObjDeleteDevice
0x140014cd7  test    eax, eax
0x140014cd9  jnz     short loc_140014D05
0x140014cdb  call    cs:__imp_GetLastError
0x140014ce1  mov     rcx, [rbp+4Fh+arg_20]
0x140014ce5  lea     r9, aFailedToRemove; "Failed to remove device '%ws'. Error = "...
0x140014cec  mov     edx, 1
0x140014cf1  mov     [rsp+0B0h+var_88], eax
0x140014cf5  mov     r8d, edx
0x140014cf8  mov     [rsp+0B0h+var_90], rdi
0x140014cfd  mov     ebx, eax
0x140014cff  call    cs:__imp_DevRtlWriteTextLog
0x140014d05  xor     edx, edx
0x140014d07  xor     r8d, r8d
0x140014d0a  lea     ecx, [rdx+12h]
0x140014d0d  call    DrvInstActionCallback
0x140014d12  mov     eax, ebx
0x140014d14  mov     rcx, [rbp+4Fh+var_20]
0x140014d18  xor     rcx, rsp; StackCookie
0x140014d1b  call    __security_check_cookie
0x140014d20  lea     r11, [rsp+0B0h+var_10]
0x140014d28  mov     rbx, [r11+28h]
0x140014d2c  mov     rsi, [r11+30h]
0x140014d30  mov     rsp, r11
0x140014d33  pop     r14
0x140014d35  pop     rdi
0x140014d36  pop     rbp
0x140014d37  retn
```
