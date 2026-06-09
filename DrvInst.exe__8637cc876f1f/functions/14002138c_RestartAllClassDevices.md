# RestartAllClassDevices

- ea: `0x14002138c`
- end: `0x140021445`
- name: `RestartAllClassDevices`
- size: `185`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140013e14`
- `0x140014860`

## callees

- `0x140020ea8`
- `0x14002138c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400213c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400213f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400213c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400213f7`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1400213b3`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1400213b3`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400213ed`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400213ed`
- `DEVOBJ!DevObjRestartDevices` at `0x14002140c`
- `DEVOBJ!DevObjRestartDevices` at `0x14002140c`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14002142d`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14002142d`

## pseudocode

```c
__int64 __fastcall RestartAllClassDevices(__int64 a1, int a2)
{
  __int64 DeviceInfoList; // rax
  __int64 v5; // rdi
  DWORD LastError; // ebx

  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v5 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    return GetLastError();
  }
  else
  {
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, a1, 0, 2, 0, 0)
      && (unsigned int)DevObjRestartDevices(v5, 0, a2 | 1u) )
    {
      LastError = 0;
      if ( (unsigned int)DevicesNeedReboot(v5) )
        LastError = 3010;
    }
    else
    {
      LastError = GetLastError();
    }
    DevObjDestroyDeviceInfoList(v5);
  }
  return LastError;
}

```

## disassembly

```asm
0x14002138c  mov     [rsp+arg_0], rbx
0x140021391  mov     [rsp+arg_8], rsi
0x140021396  push    rdi
0x140021397  sub     rsp, 30h
0x14002139b  mov     ebx, edx
0x14002139d  mov     [rsp+38h+var_18], 0
0x1400213a6  mov     rsi, rcx
0x1400213a9  xor     edx, edx
0x1400213ab  xor     ecx, ecx
0x1400213ad  xor     r9d, r9d
0x1400213b0  xor     r8d, r8d
0x1400213b3  call    cs:__imp_DevObjCreateDeviceInfoList
0x1400213b9  mov     rdi, rax
0x1400213bc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400213c0  jnz     short loc_1400213CC
0x1400213c2  call    cs:__imp_GetLastError
0x1400213c8  mov     ebx, eax
0x1400213ca  jmp     short loc_140021433
0x1400213cc  mov     [rsp+38h+var_10], 0
0x1400213d5  mov     r9d, 2
0x1400213db  xor     r8d, r8d
0x1400213de  mov     [rsp+38h+var_18], 0
0x1400213e7  mov     rdx, rsi
0x1400213ea  mov     rcx, rdi
0x1400213ed  call    cs:__imp_DevObjGetClassDevs
0x1400213f3  test    eax, eax
0x1400213f5  jnz     short loc_140021401
0x1400213f7  call    cs:__imp_GetLastError
0x1400213fd  mov     ebx, eax
0x1400213ff  jmp     short loc_14002142A
0x140021401  or      ebx, 1
0x140021404  xor     edx, edx
0x140021406  mov     r8d, ebx
0x140021409  mov     rcx, rdi
0x14002140c  call    cs:__imp_DevObjRestartDevices
0x140021412  test    eax, eax
0x140021414  jz      short loc_1400213F7
0x140021416  mov     rcx, rdi
0x140021419  xor     ebx, ebx
0x14002141b  call    DevicesNeedReboot
0x140021420  test    eax, eax
0x140021422  mov     ecx, 0BC2h
0x140021427  cmovnz  ebx, ecx
0x14002142a  mov     rcx, rdi
0x14002142d  call    cs:__imp_DevObjDestroyDeviceInfoList
0x140021433  mov     rsi, [rsp+38h+arg_8]
0x140021438  mov     eax, ebx
0x14002143a  mov     rbx, [rsp+38h+arg_0]
0x14002143f  add     rsp, 30h
0x140021443  pop     rdi
0x140021444  retn
```
