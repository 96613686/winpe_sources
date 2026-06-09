# CDriveConfiguration::Thread_Initialize(void)

- ea: `0x180010800`
- end: `0x1800109a7`
- name: `?Thread_Initialize@CDriveConfiguration@@AEAAJXZ`
- size: `423`
- prototype: `__int64 __fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000fb00`

## callees

- `0x180002290`
- `0x180004170`
- `0x18000e300`
- `0x18000e840`
- `0x18000f430`
- `0x18000fb40`
- `0x180010800`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010858`
- `KERNEL32!GetLastError` at `0x180010858`
- `KERNEL32!GetSystemPowerStatus` at `0x18001084e`
- `KERNEL32!GetSystemPowerStatus` at `0x18001084e`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::Thread_Initialize(CDriveConfiguration *this)
{
  int v2; // esi
  signed int v3; // ebx
  signed int LastError; // eax
  int DeviceNameFromVolume; // ebx
  int v6; // eax
  struct IVdsVolume *v8; // [rsp+28h] [rbp-40h] BYREF
  signed int v9; // [rsp+30h] [rbp-38h]
  int v10; // [rsp+34h] [rbp-34h]
  CDriveConfiguration *v11; // [rsp+38h] [rbp-30h]
  struct _SYSTEM_POWER_STATUS v12; // [rsp+40h] [rbp-28h] BYREF

  v11 = this;
  v8 = 0;
  v2 = 0;
  v3 = 0;
  v9 = 0;
  *(_QWORD *)&v12.ACLineStatus = 0;
  v12.BatteryFullLifeTime = 0;
  if ( !GetSystemPowerStatus(&v12) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_4;
  }
  if ( v12.ACLineStatus == 1 || v12.BatteryFlag == 0x80 )
  {
    v2 = 0;
  }
  else
  {
    if ( v12.ACLineStatus == 0xFF && v12.BatteryFlag == 0xFF )
    {
      v3 = -2136997865;
LABEL_4:
      v9 = v3;
      goto LABEL_13;
    }
    v2 = 1;
  }
  v10 = v2;
LABEL_13:
  if ( v3 >= 0 )
  {
    if ( v2 )
    {
      DeviceNameFromVolume = -1063256040;
      goto LABEL_26;
    }
  }
  else
  {
    BdeCfgLogError(1, 1084227652);
  }
  DeviceNameFromVolume = BdeCfgCheckAndGetBootVolume(&v8);
  if ( DeviceNameFromVolume == -1063256060 )
    DeviceNameFromVolume = -1063256062;
  if ( DeviceNameFromVolume >= 0 )
  {
    v6 = *((_DWORD *)this + 295) == 1
       ? CDriveConfiguration::DetectTargetDrive(this, v8)
       : CDriveConfiguration::InitializeFromParams(this, v8);
    DeviceNameFromVolume = v6;
    if ( v6 >= 0 )
    {
      DeviceNameFromVolume = BdeCfgGetDeviceNameFromVolume(v8, 0x104u, (unsigned __int16 *)this + 34);
      if ( DeviceNameFromVolume >= 0 )
        BdeCfgLogTargetAction((char *)this + 64);
    }
  }
LABEL_26:
  if ( v8 )
    ((void (__fastcall *)(struct IVdsVolume *))v8->lpVtbl->Release)(v8);
  if ( DeviceNameFromVolume < 0 )
    BdeCfgLogError(1, (unsigned int)DeviceNameFromVolume);
  *((_DWORD *)this + 1) = DeviceNameFromVolume;
  *(_BYTE *)this = 1;
  (***((void (__fastcall ****)(_QWORD, _QWORD))this + 157))(*((_QWORD *)this + 157), (unsigned int)DeviceNameFromVolume);
  return (unsigned int)DeviceNameFromVolume;
}

```

## disassembly

```asm
0x180010800  mov     r11, rsp
0x180010803  mov     [r11+10h], rbx
0x180010807  mov     [r11+18h], rsi
0x18001080b  push    r14
0x18001080d  sub     rsp, 60h
0x180010811  mov     rax, cs:__security_cookie
0x180010818  xor     rax, rsp
0x18001081b  mov     [rsp+68h+var_18], rax
0x180010820  mov     r14, rcx
0x180010823  mov     [rsp+68h+var_30], rcx
0x180010828  mov     qword ptr [r11-40h], 0
0x180010830  mov     [rsp+68h+var_48], 0
0x180010838  xor     esi, esi
0x18001083a  xor     ebx, ebx
0x18001083c  mov     [rsp+68h+var_38], ebx
0x180010840  xor     eax, eax
0x180010842  mov     [r11-28h], rax
0x180010846  mov     [rsp+68h+var_20], eax
0x18001084a  lea     rcx, [r11-28h]; lpSystemPowerStatus
0x18001084e  call    cs:__imp_GetSystemPowerStatus
0x180010854  test    eax, eax
0x180010856  jnz     short loc_180010873
0x180010858  call    cs:__imp_GetLastError
0x18001085e  mov     ebx, eax
0x180010860  test    eax, eax
0x180010862  jle     short loc_18001086D
0x180010864  movzx   ebx, ax
0x180010867  or      ebx, 80070000h
0x18001086d  mov     [rsp+68h+var_38], ebx
0x180010871  jmp     short loc_1800108A0
0x180010873  mov     al, [rsp+68h+var_28]
0x180010877  cmp     al, 1
0x180010879  jz      short loc_18001089A
0x18001087b  cmp     [rsp+68h+var_27], 80h
0x180010880  jz      short loc_18001089A
0x180010882  cmp     al, 0FFh
0x180010884  jnz     short loc_180010893
0x180010886  cmp     [rsp+68h+var_27], al
0x18001088a  jnz     short loc_180010893
0x18001088c  mov     ebx, 80A00017h
0x180010891  jmp     short loc_18001086D
0x180010893  mov     esi, 1
0x180010898  jmp     short loc_18001089C
0x18001089a  xor     esi, esi
0x18001089c  mov     [rsp+68h+var_34], esi
0x1800108a0  mov     [rsp+68h+var_48], ebx
0x1800108a4  test    ebx, ebx
0x1800108a6  jns     short loc_1800108FE
0x1800108a8  mov     edx, 40A00044h
0x1800108ad  mov     ecx, 1
0x1800108b2  call    BdeCfgLogError
0x1800108b7  mov     [rsp+68h+var_48], 0
0x1800108bf  lea     rcx, [rsp+68h+var_40]; struct IVdsVolume **
0x1800108c4  call    ?BdeCfgCheckAndGetBootVolume@@YAJPEAPEAUIVdsVolume@@@Z; BdeCfgCheckAndGetBootVolume(IVdsVolume * *)
0x1800108c9  mov     ebx, eax
0x1800108cb  mov     [rsp+68h+var_48], eax
0x1800108cf  mov     eax, 0C0A00002h
0x1800108d4  cmp     ebx, 0C0A00004h
0x1800108da  cmovz   ebx, eax
0x1800108dd  mov     [rsp+68h+var_48], ebx
0x1800108e1  test    ebx, ebx
0x1800108e3  js      short loc_180010943
0x1800108e5  mov     rdx, [rsp+68h+var_40]; struct IVdsVolume *
0x1800108ea  mov     rcx, r14; this
0x1800108ed  cmp     dword ptr [r14+49Ch], 1
0x1800108f5  jnz     short loc_18001090D
0x1800108f7  call    ?DetectTargetDrive@CDriveConfiguration@@AEAAJPEAUIVdsVolume@@@Z; CDriveConfiguration::DetectTargetDrive(IVdsVolume *)
0x1800108fc  jmp     short loc_180010912
0x1800108fe  test    esi, esi
0x180010900  jz      short loc_1800108BF
0x180010902  mov     ebx, 0C0A00018h
0x180010907  mov     [rsp+68h+var_48], ebx
0x18001090b  jmp     short loc_180010943
0x18001090d  call    ?InitializeFromParams@CDriveConfiguration@@AEAAJPEAUIVdsVolume@@@Z; CDriveConfiguration::InitializeFromParams(IVdsVolume *)
0x180010912  mov     [rsp+68h+var_48], eax
0x180010916  mov     ebx, eax
0x180010918  test    eax, eax
0x18001091a  js      short loc_180010943
0x18001091c  lea     r8, [r14+44h]; unsigned __int16 *
0x180010920  mov     edx, 104h; unsigned __int64
0x180010925  mov     rcx, [rsp+68h+var_40]; struct IVdsVolume *
0x18001092a  call    ?BdeCfgGetDeviceNameFromVolume@@YAJPEAUIVdsVolume@@_KPEAG@Z; BdeCfgGetDeviceNameFromVolume(IVdsVolume *,unsigned __int64,ushort *)
0x18001092f  mov     ebx, eax
0x180010931  mov     [rsp+68h+var_48], eax
0x180010935  test    eax, eax
0x180010937  js      short loc_180010943
0x180010939  lea     rcx, [r14+40h]
0x18001093d  call    BdeCfgLogTargetAction
0x180010942  nop
0x180010943  mov     rcx, [rsp+68h+var_40]
0x180010948  test    rcx, rcx
0x18001094b  jz      short loc_180010959
0x18001094d  mov     rax, [rcx]
0x180010950  mov     rax, [rax+10h]
0x180010954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010959  test    ebx, ebx
0x18001095b  jns     short loc_180010969
0x18001095d  mov     edx, ebx
0x18001095f  mov     ecx, 1
0x180010964  call    BdeCfgLogError
0x180010969  mov     [r14+4], ebx
0x18001096d  mov     byte ptr [r14], 1
0x180010971  mov     rcx, [r14+4E8h]
0x180010978  mov     rax, [rcx]
0x18001097b  mov     edx, ebx
0x18001097d  mov     rax, [rax]
0x180010980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010985  mov     eax, ebx
0x180010987  mov     rcx, [rsp+68h+var_18]
0x18001098c  xor     rcx, rsp; StackCookie
0x18001098f  call    __security_check_cookie
0x180010994  lea     r11, [rsp+68h+var_8]
0x180010999  mov     rbx, [r11+18h]
0x18001099d  mov     rsi, [r11+20h]
0x1800109a1  mov     rsp, r11
0x1800109a4  pop     r14
0x1800109a6  retn
0x18001458d  push    rbx
0x18001458f  push    rbp
0x180014590  sub     rsp, 28h
0x180014594  mov     rbp, rdx
0x180014597  mov     rcx, [rbp+28h]
0x18001459b  test    rcx, rcx
0x18001459e  jz      short loc_1800145AD
0x1800145a0  mov     rax, [rcx]
0x1800145a3  mov     rax, [rax+10h]
0x1800145a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145ac  nop
0x1800145ad  mov     ebx, [rbp+20h]
0x1800145b0  test    ebx, ebx
0x1800145b2  jns     short loc_1800145C1
0x1800145b4  mov     edx, ebx
0x1800145b6  mov     ecx, 1
0x1800145bb  call    BdeCfgLogError
0x1800145c0  nop
0x1800145c1  mov     rax, [rbp+38h]
0x1800145c5  mov     [rax+4], ebx
0x1800145c8  mov     byte ptr [rax], 1
0x1800145cb  mov     rcx, [rax+4E8h]
0x1800145d2  mov     r8, [rcx]
0x1800145d5  mov     edx, ebx
0x1800145d7  mov     rax, [r8]
0x1800145da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145df  nop
0x1800145e0  add     rsp, 28h
0x1800145e4  pop     rbp
0x1800145e5  pop     rbx
0x1800145e6  retn
```
