# FindApoRegistrationUnderDevice(ushort *,_GUID,bool &)

- ea: `0x1800345ec`
- end: `0x1800346f2`
- name: `?FindApoRegistrationUnderDevice@@YAJPEAGU_GUID@@AEA_N@Z`
- size: `262`
- prototype: `__int64 __fastcall(DEVINSTID_W pDeviceID, struct _GUID *__struct_ptr, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800343c4`

## callees

- `0x18001deb0`
- `0x180027858`
- `0x180033464`
- `0x1800345ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800346b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800346da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800346b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800346da`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180034684`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180034684`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180034617`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180034617`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180034626`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18003468e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180034626`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18003468e`

## pseudocode

```c
__int64 __fastcall FindApoRegistrationUnderDevice(DEVINSTID_W pDeviceID, struct _GUID *a2, bool *a3)
{
  CONFIGRET v5; // eax
  DWORD v6; // eax
  CONFIGRET v8; // eax
  signed int v9; // eax
  signed int v10; // ebx
  bool v11; // al
  HKEY v12; // rcx
  unsigned int phkDevice; // [rsp+20h] [rbp-28h]
  struct _GUID v14; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DEVINST dnDevNode; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  *a3 = 0;
  dnDevNode = 0;
  v5 = CM_Locate_DevNodeW(&dnDevNode, pDeviceID, 0);
  v6 = CM_MapCrToWin32Err(v5, 0x507u);
  if ( v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x127,
             (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
             (const char *)v6,
             phkDevice);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = CM_Open_DevNode_Key(dnDevNode, 0x20019u, 0, 1u, &hKey, 1u);
  v9 = CM_MapCrToWin32Err(v8, 0x507u);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 >= 0 )
  {
    v14 = *a2;
    v11 = IsAPOClsidRegistered(hKey, &v14);
    v12 = hKey;
    *a3 = v11;
    if ( v12 )
      RegCloseKey(v12);
    return 0;
  }
  else
  {
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x1800345ec  mov     rax, rsp
0x1800345ef  mov     [rax+8], rbx
0x1800345f3  mov     [rax+10h], rsi
0x1800345f7  push    rdi
0x1800345f8  sub     rsp, 40h
0x1800345fc  mov     rsi, rdx
0x1800345ff  mov     byte ptr [r8], 0
0x180034603  mov     rdx, rcx; pDeviceID
0x180034606  mov     dword ptr [rax+18h], 0
0x18003460d  mov     rdi, r8
0x180034610  lea     rcx, [rax+18h]; pdnDevInst
0x180034614  xor     r8d, r8d; ulFlags
0x180034617  call    cs:__imp_CM_Locate_DevNodeW
0x18003461d  mov     ebx, 507h
0x180034622  mov     ecx, eax; CmReturnCode
0x180034624  mov     edx, ebx; DefaultErr
0x180034626  call    cs:__imp_CM_MapCrToWin32Err
0x18003462c  test    eax, eax
0x18003462e  jz      short loc_18003464E
0x180034630  mov     rcx, [rsp+48h]; this
0x180034635  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\lib\\audioen"...
0x18003463c  mov     r9d, eax; char *
0x18003463f  mov     edx, 127h; void *
0x180034644  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180034649  jmp     loc_1800346E2
0x18003464e  xor     edx, edx
0x180034650  mov     [rsp+48h+hKey], 0
0x180034659  lea     rcx, [rsp+48h+hKey]
0x18003465e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180034663  mov     ecx, [rsp+48h+dnDevNode]; dnDevNode
0x180034667  lea     rax, [rsp+48h+hKey]
0x18003466c  mov     r9d, 1; Disposition
0x180034672  xor     r8d, r8d; ulHardwareProfile
0x180034675  mov     [rsp+48h+ulFlags], r9d; ulFlags
0x18003467a  mov     edx, 20019h; samDesired
0x18003467f  mov     [rsp+48h+phkDevice], rax; phkDevice
0x180034684  call    cs:__imp_CM_Open_DevNode_Key
0x18003468a  mov     ecx, eax; CmReturnCode
0x18003468c  mov     edx, ebx; DefaultErr
0x18003468e  call    cs:__imp_CM_MapCrToWin32Err
0x180034694  mov     ebx, eax
0x180034696  test    eax, eax
0x180034698  jle     short loc_1800346A3
0x18003469a  movzx   ebx, ax
0x18003469d  or      ebx, 80070000h
0x1800346a3  mov     rcx, [rsp+48h+hKey]; hKey
0x1800346a8  test    ebx, ebx
0x1800346aa  jns     short loc_1800346BB
0x1800346ac  test    rcx, rcx
0x1800346af  jz      short loc_1800346B7
0x1800346b1  call    cs:__imp_RegCloseKey
0x1800346b7  mov     eax, ebx
0x1800346b9  jmp     short loc_1800346E2
0x1800346bb  movaps  xmm0, xmmword ptr [rsi]
0x1800346be  lea     rdx, [rsp+48h+var_18]; struct _GUID
0x1800346c3  movdqa  xmmword ptr [rsp+48h+var_18.Data1], xmm0
0x1800346c9  call    ?IsAPOClsidRegistered@@YA_NPEAUHKEY__@@U_GUID@@@Z; IsAPOClsidRegistered(HKEY__ *,_GUID)
0x1800346ce  mov     rcx, [rsp+48h+hKey]; hKey
0x1800346d3  mov     [rdi], al
0x1800346d5  test    rcx, rcx
0x1800346d8  jz      short loc_1800346E0
0x1800346da  call    cs:__imp_RegCloseKey
0x1800346e0  xor     eax, eax
0x1800346e2  mov     rbx, [rsp+48h+arg_0]
0x1800346e7  mov     rsi, [rsp+48h+arg_8]
0x1800346ec  add     rsp, 40h
0x1800346f0  pop     rdi
0x1800346f1  retn
```
