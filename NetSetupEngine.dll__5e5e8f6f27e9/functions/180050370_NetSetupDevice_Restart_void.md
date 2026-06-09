# NetSetupDevice::Restart(void)

- ea: `0x180050370`
- end: `0x180050551`
- name: `?Restart@NetSetupDevice@@QEAAXXZ`
- size: `481`
- prototype: `void __fastcall(NetSetupDevice *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x18004fff0`

## callees

- `0x180017814`
- `0x18001dee8`
- `0x180050204`
- `0x180050370`
- `0x1800505ec`
- `0x18005097c`
- `0x18005b034`
- `0x180065035`
- `0x18007fee8`
- `0x1800800bc`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-devices-config-l1-1-0!CM_Setup_DevNode` at `0x18005044d`
- `api-ms-win-devices-config-l1-1-0!CM_Setup_DevNode` at `0x18005044d`
- `api-ms-win-devices-config-l1-1-0!CM_Query_And_Remove_SubTreeW` at `0x1800503d1`
- `api-ms-win-devices-config-l1-1-0!CM_Query_And_Remove_SubTreeW` at `0x1800503d1`

## pseudocode

```c
void __fastcall NetSetupDevice::Restart(NetSetupDevice *this)
{
  DEVINST v2; // ecx
  CONFIGRET v3; // eax
  int v4; // edx
  int v5; // r8d
  unsigned int v6; // esi
  int v7; // eax
  CONFIGRET v8; // eax
  unsigned int v9; // esi
  int v10; // eax
  int ProblemCode; // eax
  _BYTE pExceptionObject[208]; // [rsp+30h] [rbp-308h] BYREF
  _PNP_VETO_TYPE pVetoType[4]; // [rsp+100h] [rbp-238h] BYREF
  WCHAR pszVetoName[264]; // [rsp+110h] [rbp-228h] BYREF

  NetSetupDevice::EnsureDeviceInstance(this);
  v2 = *(_DWORD *)this;
  pVetoType[0] = PNP_VetoTypeUnknown;
  pszVetoName[0] = 0;
  v3 = CM_Query_And_Remove_SubTreeW(v2, pVetoType, pszVetoName, 0x104u, 2u);
  v6 = v3;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_DSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v5, pVetoType[0], (__int64)pszVetoName, v3);
    v7 = My_CM_MapCrToWin32Err(v6);
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, v7);
    throw (HResultException *)pExceptionObject;
  }
  v8 = CM_Setup_DevNode(*(_DWORD *)this, 0);
  v9 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids, v8);
    v10 = My_CM_MapCrToWin32Err(v9);
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, v10);
    throw (HResultException *)pExceptionObject;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids,
      *((_QWORD *)this + 1));
  ProblemCode = NetSetupDevice::GetProblemCode(this);
  if ( ProblemCode && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids,
      ProblemCode,
      *((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x180050370  mov     [rsp+arg_8], rbx
0x180050375  mov     [rsp+arg_10], rsi
0x18005037a  push    rdi
0x18005037b  sub     rsp, 330h
0x180050382  mov     rax, cs:__security_cookie
0x180050389  xor     rax, rsp
0x18005038c  mov     [rsp+338h+var_18], rax
0x180050394  mov     rdi, rcx
0x180050397  call    ?EnsureDeviceInstance@NetSetupDevice@@AEAAXXZ; NetSetupDevice::EnsureDeviceInstance(void)
0x18005039c  mov     ecx, [rdi]; dnAncestor
0x18005039e  lea     r8, [rsp+338h+pszVetoName]; pszVetoName
0x1800503a6  xor     eax, eax
0x1800503a8  mov     [rsp+338h+pVetoType], 0
0x1800503b3  mov     r9d, 104h; ulNameLength
0x1800503b9  mov     [rsp+338h+pszVetoName], ax
0x1800503c1  lea     rdx, [rsp+338h+pVetoType]; pVetoType
0x1800503c9  mov     [rsp+338h+ulFlags], 2; ulFlags
0x1800503d1  call    cs:__imp_CM_Query_And_Remove_SubTreeW
0x1800503d7  mov     esi, eax
0x1800503d9  test    eax, eax
0x1800503db  jz      short loc_180050449
0x1800503dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800503e4  lea     rbx, WPP_GLOBAL_Control
0x1800503eb  cmp     rcx, rbx
0x1800503ee  jz      short loc_180050418
0x1800503f0  cmp     byte ptr [rcx+19h], 2
0x1800503f4  jb      short loc_180050418
0x1800503f6  mov     r9d, [rsp+338h+pVetoType]
0x1800503fe  mov     rcx, [rcx+10h]
0x180050402  mov     [rsp+338h+var_310], eax
0x180050406  lea     rax, [rsp+338h+pszVetoName]
0x18005040e  mov     qword ptr [rsp+338h+ulFlags], rax
0x180050413  call    WPP_SF_DSD
0x180050418  mov     ecx, esi; unsigned int
0x18005041a  call    ?My_CM_MapCrToWin32Err@@YAKKK@Z; My_CM_MapCrToWin32Err(ulong,ulong)
0x18005041f  test    eax, eax
0x180050421  jle     short loc_18005042B
0x180050423  movzx   eax, ax
0x180050426  or      eax, 80070000h
0x18005042b  mov     edx, eax; int
0x18005042d  lea     rcx, [rsp+338h+pExceptionObject]; this
0x180050432  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180050437  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18005043e  lea     rcx, [rsp+338h+pExceptionObject]; pExceptionObject
0x180050443  call    _CxxThrowException_0
0x180050449  mov     ecx, [rdi]; dnDevInst
0x18005044b  xor     edx, edx; ulFlags
0x18005044d  call    cs:__imp_CM_Setup_DevNode
0x180050453  mov     esi, eax
0x180050455  test    eax, eax
0x180050457  jz      short loc_1800504BB
0x180050459  mov     rcx, cs:WPP_GLOBAL_Control
0x180050460  lea     rbx, WPP_GLOBAL_Control
0x180050467  cmp     rcx, rbx
0x18005046a  jz      short loc_18005048A
0x18005046c  cmp     byte ptr [rcx+19h], 2
0x180050470  jb      short loc_18005048A
0x180050472  mov     rcx, [rcx+10h]
0x180050476  lea     r8, WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids
0x18005047d  mov     edx, 25h ; '%'
0x180050482  mov     r9d, eax
0x180050485  call    WPP_SF_d
0x18005048a  mov     ecx, esi; unsigned int
0x18005048c  call    ?My_CM_MapCrToWin32Err@@YAKKK@Z; My_CM_MapCrToWin32Err(ulong,ulong)
0x180050491  test    eax, eax
0x180050493  jle     short loc_18005049D
0x180050495  movzx   eax, ax
0x180050498  or      eax, 80070000h
0x18005049d  mov     edx, eax; int
0x18005049f  lea     rcx, [rsp+338h+pExceptionObject]; this
0x1800504a4  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800504a9  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800504b0  lea     rcx, [rsp+338h+pExceptionObject]; pExceptionObject
0x1800504b5  call    _CxxThrowException_0
0x1800504bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800504c2  lea     rbx, WPP_GLOBAL_Control
0x1800504c9  cmp     rcx, rbx
0x1800504cc  jz      short loc_1800504ED
0x1800504ce  cmp     byte ptr [rcx+19h], 4
0x1800504d2  jb      short loc_1800504ED
0x1800504d4  mov     r9, [rdi+8]
0x1800504d8  lea     r8, WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids
0x1800504df  mov     rcx, [rcx+10h]
0x1800504e3  mov     edx, 26h ; '&'
0x1800504e8  call    WPP_SF_S
0x1800504ed  mov     rcx, rdi
0x1800504f0  call    ?GetProblemCode@NetSetupDevice@@QEAAKW4ProblemCodeFailPolicy@1@@Z; NetSetupDevice::GetProblemCode(NetSetupDevice::ProblemCodeFailPolicy)
0x1800504f5  test    eax, eax
0x1800504f7  jz      short loc_18005052C
0x1800504f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180050500  cmp     rcx, rbx
0x180050503  jz      short loc_18005052C
0x180050505  cmp     byte ptr [rcx+19h], 3
0x180050509  jb      short loc_18005052C
0x18005050b  mov     r8, [rdi+8]
0x18005050f  mov     edx, 27h ; '''
0x180050514  mov     rcx, [rcx+10h]
0x180050518  mov     r9d, eax
0x18005051b  mov     qword ptr [rsp+338h+ulFlags], r8
0x180050520  lea     r8, WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids
0x180050527  call    WPP_SF_DS
0x18005052c  mov     rcx, [rsp+338h+var_18]
0x180050534  xor     rcx, rsp; StackCookie
0x180050537  call    __security_check_cookie
0x18005053c  lea     r11, [rsp+338h+var_8]
0x180050544  mov     rbx, [r11+18h]
0x180050548  mov     rsi, [r11+20h]
0x18005054c  mov     rsp, r11
0x18005054f  pop     rdi
0x180050550  retn
```
