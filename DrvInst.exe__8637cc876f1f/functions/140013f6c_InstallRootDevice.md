# InstallRootDevice

- ea: `0x140013f6c`
- end: `0x140014147`
- name: `InstallRootDevice`
- size: `475`
- prototype: `__int64 __fastcall(int, DEVINST dnParent)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140012c2c`

## callees

- `0x140012d44`
- `0x140013f6c`
- `0x140027124`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140014005`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140014040`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140014005`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140014040`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140013ff2`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140013ff2`
- `CFGMGR32!CM_Create_DevNodeW` at `0x140013fd7`
- `CFGMGR32!CM_Create_DevNodeW` at `0x140013fd7`
- `DEVRTL!DevRtlWriteTextLog` at `0x140013fc0`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001402a`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014062`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014090`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400140ea`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001410f`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001412c`
- `DEVRTL!DevRtlWriteTextLog` at `0x140013fc0`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001402a`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014062`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014090`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400140ea`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001410f`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001412c`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140013f99`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140013f99`

## string_xrefs

- `0x140013fad`: `{Install Root Device: %ws}`
- `0x14001404f`: `Install Device: Device created.`
- `0x14001407d`: `Device does not need installation.`
- `0x1400140d3`: `Unable to install device. Error = 0x%08X`
- `0x1400140fc`: `Device requires reboot to complete installation.`
- `0x140014115`: `{Install Root Device: exit(0x%08X)}`

## pseudocode

```c
__int64 __fastcall InstallRootDevice(WCHAR *a1, DEVINST dnParent)
{
  __int64 ThreadLogToken; // rdi
  CONFIGRET v5; // eax
  CONFIGRET v6; // ebp
  CONFIGRET v7; // eax
  DWORD v8; // eax
  const char *v9; // r9
  DWORD v10; // ebx
  DWORD v11; // eax
  int v13[10]; // [rsp+40h] [rbp-28h] BYREF
  DEVNODE pdnDevInst; // [rsp+80h] [rbp+18h] BYREF
  __int64 v15; // [rsp+88h] [rbp+20h] BYREF

  pdnDevInst = 0;
  v13[0] = 0;
  LODWORD(v15) = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  DevRtlWriteTextLog(ThreadLogToken, 1, 196612, "{Install Root Device: %ws}", a1);
  v5 = CM_Create_DevNodeW(&pdnDevInst, a1, dnParent, 0);
  v6 = v5;
  if ( v5 == 16 )
  {
    v7 = CM_Locate_DevNodeW(&pdnDevInst, a1, 0);
    v6 = v7;
    if ( v7 )
    {
      v8 = CM_MapCrToWin32Err(v7, 0x490u);
      v9 = "Failed to locate existing device '%ws'. Error = 0x%08X(0x%02X)";
LABEL_4:
      v10 = v8;
      DevRtlWriteTextLog(ThreadLogToken, 1, 1, v9, a1, v8, v6);
      goto LABEL_14;
    }
  }
  else
  {
    if ( v5 )
    {
      v8 = CM_MapCrToWin32Err(v5, 0x490u);
      v9 = "Failed to register device '%ws'. Error = 0x%08X(0x%02X)";
      goto LABEL_4;
    }
    DevRtlWriteTextLog(ThreadLogToken, 1, 65540, "Install Device: Device created.");
  }
  if ( (unsigned int)DevUtilsGetConfigFlags(pdnDevInst, v13) )
  {
    DevRtlWriteTextLog(ThreadLogToken, 1, 4, "Device does not need installation.");
    v10 = 0;
  }
  else
  {
    v11 = DispatchRootDeviceOperation(
            (int)a1,
            pdnDevInst,
            (int)&InstallRootDeviceWorker,
            0,
            0xEA60u,
            (__int64)&v15,
            ThreadLogToken);
    v10 = v11;
    if ( v11 )
    {
      DevRtlWriteTextLog(ThreadLogToken, 1, 2, "Unable to install device. Error = 0x%08X", v11);
    }
    else if ( (_DWORD)v15 )
    {
      DevRtlWriteTextLog(ThreadLogToken, 1, 2, "Device requires reboot to complete installation.");
    }
  }
LABEL_14:
  DevRtlWriteTextLog(ThreadLogToken, 1, 327684, "{Install Root Device: exit(0x%08X)}", v10);
  return v10;
}

```

## disassembly

```asm
0x140013f6c  mov     rax, rsp
0x140013f6f  mov     [rax+8], rbx
0x140013f73  mov     [rax+10h], rbp
0x140013f77  push    rsi
0x140013f78  push    rdi
0x140013f79  push    r14
0x140013f7b  sub     rsp, 50h
0x140013f7f  mov     ebx, edx
0x140013f81  mov     dword ptr [rax+18h], 0
0x140013f88  mov     rsi, rcx
0x140013f8b  mov     dword ptr [rax-28h], 0
0x140013f92  mov     dword ptr [rax+20h], 0
0x140013f99  call    cs:__imp_DevRtlGetThreadLogToken
0x140013f9f  mov     r14d, 1
0x140013fa5  mov     qword ptr [rsp+68h+dwMilliseconds], rsi
0x140013faa  mov     edx, r14d
0x140013fad  lea     r9, aInstallRootDev_0; "{Install Root Device: %ws}"
0x140013fb4  mov     rcx, rax
0x140013fb7  mov     r8d, 30004h
0x140013fbd  mov     rdi, rax
0x140013fc0  call    cs:__imp_DevRtlWriteTextLog
0x140013fc6  xor     r9d, r9d; ulFlags
0x140013fc9  lea     rcx, [rsp+68h+pdnDevInst]; pdnDevInst
0x140013fd1  mov     r8d, ebx; dnParent
0x140013fd4  mov     rdx, rsi; pDeviceID
0x140013fd7  call    cs:__imp_CM_Create_DevNodeW
0x140013fdd  mov     ebp, eax
0x140013fdf  cmp     eax, 10h
0x140013fe2  jnz     short loc_140014035
0x140013fe4  xor     r8d, r8d; ulFlags
0x140013fe7  lea     rcx, [rsp+68h+pdnDevInst]; pdnDevInst
0x140013fef  mov     rdx, rsi; pDeviceID
0x140013ff2  call    cs:__imp_CM_Locate_DevNodeW
0x140013ff8  mov     ebp, eax
0x140013ffa  test    eax, eax
0x140013ffc  jz      short loc_140014068
0x140013ffe  mov     edx, 490h; DefaultErr
0x140014003  mov     ecx, eax; CmReturnCode
0x140014005  call    cs:__imp_CM_MapCrToWin32Err
0x14001400b  lea     r9, aFailedToLocate_1; "Failed to locate existing device '%ws'."...
0x140014012  mov     dword ptr [rsp+68h+var_38], ebp
0x140014016  mov     r8d, r14d
0x140014019  mov     dword ptr [rsp+68h+var_40], eax
0x14001401d  mov     edx, r14d
0x140014020  mov     rcx, rdi
0x140014023  mov     qword ptr [rsp+68h+dwMilliseconds], rsi
0x140014028  mov     ebx, eax
0x14001402a  call    cs:__imp_DevRtlWriteTextLog
0x140014030  jmp     loc_140014115
0x140014035  test    ebp, ebp
0x140014037  jz      short loc_14001404F
0x140014039  mov     edx, 490h; DefaultErr
0x14001403e  mov     ecx, ebp; CmReturnCode
0x140014040  call    cs:__imp_CM_MapCrToWin32Err
0x140014046  lea     r9, aFailedToRegist; "Failed to register device '%ws'. Error "...
0x14001404d  jmp     short loc_140014012
0x14001404f  lea     r9, aInstallDeviceD; "Install Device: Device created."
0x140014056  mov     r8d, 10004h
0x14001405c  mov     edx, r14d
0x14001405f  mov     rcx, rdi
0x140014062  call    cs:__imp_DevRtlWriteTextLog
0x140014068  mov     ecx, [rsp+68h+pdnDevInst]
0x14001406f  lea     rdx, [rsp+68h+var_28]
0x140014074  call    DevUtilsGetConfigFlags
0x140014079  test    eax, eax
0x14001407b  jz      short loc_14001409A
0x14001407d  lea     r9, aDeviceDoesNotN; "Device does not need installation."
0x140014084  mov     r8d, 4
0x14001408a  mov     edx, r14d
0x14001408d  mov     rcx, rdi
0x140014090  call    cs:__imp_DevRtlWriteTextLog
0x140014096  xor     ebx, ebx
0x140014098  jmp     short loc_140014115
0x14001409a  mov     edx, [rsp+68h+pdnDevInst]; int
0x1400140a1  lea     rax, [rsp+68h+arg_18]
0x1400140a9  mov     [rsp+68h+var_38], rdi; __int64
0x1400140ae  lea     r8, InstallRootDeviceWorker; int
0x1400140b5  mov     [rsp+68h+var_40], rax; __int64
0x1400140ba  xor     r9d, r9d; int
0x1400140bd  mov     rcx, rsi; int
0x1400140c0  mov     [rsp+68h+dwMilliseconds], 0EA60h; dwMilliseconds
0x1400140c8  call    DispatchRootDeviceOperation
0x1400140cd  mov     ebx, eax
0x1400140cf  test    eax, eax
0x1400140d1  jz      short loc_1400140F2
0x1400140d3  lea     r9, aUnableToInstal; "Unable to install device. Error = 0x%08"...
0x1400140da  mov     [rsp+68h+dwMilliseconds], eax
0x1400140de  mov     r8d, 2
0x1400140e4  mov     edx, r14d
0x1400140e7  mov     rcx, rdi
0x1400140ea  call    cs:__imp_DevRtlWriteTextLog
0x1400140f0  jmp     short loc_140014115
0x1400140f2  cmp     dword ptr [rsp+68h+arg_18], 0
0x1400140fa  jz      short loc_140014115
0x1400140fc  lea     r9, aDeviceRequires_1; "Device requires reboot to complete inst"...
0x140014103  mov     r8d, 2
0x140014109  mov     edx, r14d
0x14001410c  mov     rcx, rdi
0x14001410f  call    cs:__imp_DevRtlWriteTextLog
0x140014115  lea     r9, aInstallRootDev; "{Install Root Device: exit(0x%08X)}"
0x14001411c  mov     [rsp+68h+dwMilliseconds], ebx
0x140014120  mov     r8d, 50004h
0x140014126  mov     edx, r14d
0x140014129  mov     rcx, rdi
0x14001412c  call    cs:__imp_DevRtlWriteTextLog
0x140014132  mov     rbp, [rsp+68h+arg_8]
0x140014137  mov     eax, ebx
0x140014139  mov     rbx, [rsp+68h+arg_0]
0x14001413e  add     rsp, 50h
0x140014142  pop     r14
0x140014144  pop     rdi
0x140014145  pop     rsi
0x140014146  retn
```
