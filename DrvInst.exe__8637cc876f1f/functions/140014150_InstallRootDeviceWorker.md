# InstallRootDeviceWorker

- ea: `0x140014150`
- end: `0x140014231`
- name: `InstallRootDeviceWorker`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140014150`
- `0x140018dc0`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Setup_DevNode` at `0x1400141b1`
- `api-ms-win-devices-config-l1-1-1!CM_Setup_DevNode` at `0x1400141b1`
- `CFGMGR32!CM_MapCrToSpErr` at `0x1400141f8`
- `CFGMGR32!CM_MapCrToSpErr` at `0x1400141f8`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001418a`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400141e2`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001421e`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001418a`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400141e2`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001421e`

## string_xrefs

- `0x14001416c`: `Install Device: Setting up device.`
- `0x1400141d2`: `Install Device: Setting up device completed.`
- `0x140014206`: `Install Device: Setting up device failed. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall InstallRootDeviceWorker(__int64 a1, DEVINST a2, __int64 a3, _DWORD *a4, __int64 a5)
{
  CONFIGRET v7; // ebx
  unsigned int v9[8]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v10; // [rsp+50h] [rbp-18h]

  memset(v9, 0, sizeof(v9));
  v10 = 0;
  DevRtlWriteTextLog(a5, 1, 65540, "Install Device: Setting up device.");
  *(_QWORD *)&v10 = L"RootDevice_Setup";
  DrvInstActionCallback(17, v9);
  v7 = CM_Setup_DevNode(a2, 0);
  DrvInstActionCallback(18, 0);
  if ( v7 )
  {
    v7 = CM_MapCrToSpErr(v7, 13);
    DevRtlWriteTextLog(a5, 1, 65538, "Install Device: Setting up device failed. Error = 0x%08X", v7);
  }
  else
  {
    DevRtlWriteTextLog(a5, 1, 65540, "Install Device: Setting up device completed.");
    if ( a4 )
      *a4 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x140014150  mov     rax, rsp
0x140014153  mov     [rax+8], rbx
0x140014157  push    rdi
0x140014158  sub     rsp, 60h
0x14001415c  mov     rcx, [rsp+68h+arg_20]
0x140014164  xorps   xmm0, xmm0
0x140014167  mov     rdi, r9
0x14001416a  mov     ebx, edx
0x14001416c  lea     r9, aInstallDeviceS_0; "Install Device: Setting up device."
0x140014173  mov     edx, 1
0x140014178  mov     r8d, 10004h
0x14001417e  movups  xmmword ptr [rax-38h], xmm0
0x140014182  movups  xmmword ptr [rax-28h], xmm0
0x140014186  movups  xmmword ptr [rax-18h], xmm0
0x14001418a  call    cs:__imp_DevRtlWriteTextLog
0x140014190  xor     r8d, r8d
0x140014193  lea     rax, aRootdeviceSetu; "RootDevice_Setup"
0x14001419a  lea     rdx, [rsp+68h+var_38]
0x14001419f  mov     qword ptr [rsp+68h+var_18], rax
0x1400141a4  lea     ecx, [r8+11h]
0x1400141a8  call    DrvInstActionCallback
0x1400141ad  xor     edx, edx; ulFlags
0x1400141af  mov     ecx, ebx; dnDevInst
0x1400141b1  call    cs:__imp_CM_Setup_DevNode
0x1400141b7  xor     edx, edx
0x1400141b9  xor     r8d, r8d
0x1400141bc  mov     ebx, eax
0x1400141be  lea     ecx, [rdx+12h]
0x1400141c1  call    DrvInstActionCallback
0x1400141c6  test    ebx, ebx
0x1400141c8  jnz     short loc_1400141F1
0x1400141ca  mov     rcx, [rsp+68h+arg_20]
0x1400141d2  lea     r9, aInstallDeviceS_1; "Install Device: Setting up device compl"...
0x1400141d9  lea     edx, [rbx+1]
0x1400141dc  mov     r8d, 10004h
0x1400141e2  call    cs:__imp_DevRtlWriteTextLog
0x1400141e8  test    rdi, rdi
0x1400141eb  jz      short loc_140014224
0x1400141ed  mov     [rdi], ebx
0x1400141ef  jmp     short loc_140014224
0x1400141f1  mov     edx, 0Dh
0x1400141f6  mov     ecx, ebx
0x1400141f8  call    cs:__imp_CM_MapCrToSpErr
0x1400141fe  mov     rcx, [rsp+68h+arg_20]
0x140014206  lea     r9, aInstallDeviceS; "Install Device: Setting up device faile"...
0x14001420d  mov     edx, 1
0x140014212  mov     [rsp+68h+var_48], eax
0x140014216  mov     r8d, 10002h
0x14001421c  mov     ebx, eax
0x14001421e  call    cs:__imp_DevRtlWriteTextLog
0x140014224  mov     eax, ebx
0x140014226  mov     rbx, [rsp+68h+arg_0]
0x14001422b  add     rsp, 60h
0x14001422f  pop     rdi
0x140014230  retn
```
