# RelativePanelHelper::GetDeviceInstanceIdFromInterfacePath(ushort const *,HSTRING__ * *)

- ea: `0x1800626ac`
- end: `0x18006280b`
- name: `?GetDeviceInstanceIdFromInterfacePath@RelativePanelHelper@@SAJPEBGPEAPEAUHSTRING__@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, HSTRING *string)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180062814`
- `0x180062b6c`

## callees

- `0x180005fa0`
- `0x180044f30`
- `0x180045900`
- `0x1800626ac`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180062755`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180062755`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180062766`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180062766`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800627ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800627ac`

## pseudocode

```c
__int64 __fastcall RelativePanelHelper::GetDeviceInstanceIdFromInterfacePath(
        LPCWSTR pszDeviceInterface,
        HSTRING *string)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  CONFIGRET Device_Interface_PropertyW; // eax
  signed int v7; // eax
  __int64 v8; // rdx
  HRESULT v9; // eax
  ULONG PropertyBufferSize; // [rsp+30h] [rbp-1B8h] BYREF
  DEVPROPTYPE PropertyType[3]; // [rsp+34h] [rbp-1B4h] BYREF
  WCHAR PropertyBuffer[200]; // [rsp+40h] [rbp-1A8h] BYREF

  memset_0(PropertyBuffer, 0, sizeof(PropertyBuffer));
  PropertyBufferSize = 400;
  PropertyType[0] = 0;
  if ( pszDeviceInterface )
  {
    if ( !string )
    {
      v4 = -2147467261;
      if ( !g_wppLevels )
        return v4;
      v5 = 21;
      goto LABEL_4;
    }
    Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                   pszDeviceInterface,
                                   &DEVPKEY_Device_InstanceId,
                                   PropertyType,
                                   (PBYTE)PropertyBuffer,
                                   &PropertyBufferSize,
                                   0);
    if ( Device_Interface_PropertyW )
    {
      v7 = CM_MapCrToWin32Err(Device_Interface_PropertyW, 0xDu);
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      if ( (v4 & 0x80000000) != 0 )
      {
        if ( !g_wppLevels )
          return v4;
        v5 = 22;
        goto LABEL_4;
      }
    }
    v8 = -1;
    do
      ++v8;
    while ( PropertyBuffer[v8] );
    v9 = WindowsCreateString(PropertyBuffer, v8, string);
    v4 = v9;
    if ( v9 < 0 && g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_aee6aa9be8a63b0b8ddb6c6384966d29_Traceguids, 0, v9);
  }
  else
  {
    v4 = -2147024809;
    if ( g_wppLevels )
    {
      v5 = 20;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, WPP_aee6aa9be8a63b0b8ddb6c6384966d29_Traceguids, 0, v4);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800626ac  mov     [rsp+arg_10], rbx
0x1800626b1  mov     [rsp+arg_18], rsi
0x1800626b6  push    rdi
0x1800626b7  sub     rsp, 1E0h
0x1800626be  mov     rax, cs:__security_cookie
0x1800626c5  xor     rax, rsp
0x1800626c8  mov     [rsp+1E8h+var_18], rax
0x1800626d0  mov     rdi, rdx
0x1800626d3  mov     rbx, rcx
0x1800626d6  mov     esi, 190h
0x1800626db  lea     rcx, [rsp+1E8h+PropertyBuffer]; void *
0x1800626e0  mov     r8d, esi; Size
0x1800626e3  xor     edx, edx; Val
0x1800626e5  call    memset_0
0x1800626ea  mov     [rsp+1E8h+var_1B8], esi
0x1800626ee  xor     esi, esi
0x1800626f0  mov     [rsp+1E8h+PropertyType], esi
0x1800626f4  test    rbx, rbx
0x1800626f7  jnz     short loc_180062717
0x1800626f9  mov     ebx, 80070057h
0x1800626fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062705  jb      loc_1800627E4
0x18006270b  lea     edx, [rsi+14h]
0x18006270e  mov     dword ptr [rsp+1E8h+PropertyBufferSize], ebx
0x180062712  jmp     loc_1800627CA
0x180062717  test    rdi, rdi
0x18006271a  jnz     short loc_180062733
0x18006271c  mov     ebx, 80004003h
0x180062721  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062728  jb      loc_1800627E4
0x18006272e  lea     edx, [rdi+15h]
0x180062731  jmp     short loc_18006270E
0x180062733  lea     rax, [rsp+1E8h+var_1B8]
0x180062738  mov     [rsp+1E8h+ulFlags], esi; ulFlags
0x18006273c  lea     r9, [rsp+1E8h+PropertyBuffer]; PropertyBuffer
0x180062741  mov     [rsp+1E8h+PropertyBufferSize], rax; PropertyBufferSize
0x180062746  lea     r8, [rsp+1E8h+PropertyType]; PropertyType
0x18006274b  mov     rcx, rbx; pszDeviceInterface
0x18006274e  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x180062755  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x18006275b  test    eax, eax
0x18006275d  jz      short loc_180062792
0x18006275f  mov     edx, 0Dh; DefaultErr
0x180062764  mov     ecx, eax; CmReturnCode
0x180062766  call    cs:__imp_CM_MapCrToWin32Err
0x18006276c  mov     ebx, eax
0x18006276e  test    eax, eax
0x180062770  jle     short loc_18006277B
0x180062772  movzx   ebx, ax
0x180062775  or      ebx, 80070000h
0x18006277b  test    ebx, ebx
0x18006277d  jns     short loc_180062792
0x18006277f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062786  jb      short loc_1800627E4
0x180062788  mov     edx, 16h
0x18006278d  jmp     loc_18006270E
0x180062792  lea     rax, [rsp+1E8h+PropertyBuffer]
0x180062797  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18006279b  inc     rdx; length
0x18006279e  cmp     [rax+rdx*2], si
0x1800627a2  jnz     short loc_18006279B
0x1800627a4  mov     r8, rdi; string
0x1800627a7  lea     rcx, [rsp+1E8h+PropertyBuffer]; sourceString
0x1800627ac  call    cs:__imp_WindowsCreateString
0x1800627b2  mov     ebx, eax
0x1800627b4  test    eax, eax
0x1800627b6  jns     short loc_1800627E4
0x1800627b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800627bf  jb      short loc_1800627E4
0x1800627c1  mov     edx, 17h
0x1800627c6  mov     dword ptr [rsp+1E8h+PropertyBufferSize], eax
0x1800627ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800627d1  lea     r8, WPP_aee6aa9be8a63b0b8ddb6c6384966d29_Traceguids
0x1800627d8  xor     r9d, r9d
0x1800627db  mov     rcx, [rcx+10h]
0x1800627df  call    WPP_SF_qD
0x1800627e4  mov     eax, ebx
0x1800627e6  mov     rcx, [rsp+1E8h+var_18]
0x1800627ee  xor     rcx, rsp; StackCookie
0x1800627f1  call    __security_check_cookie
0x1800627f6  lea     r11, [rsp+1E8h+var_8]
0x1800627fe  mov     rbx, [r11+20h]
0x180062802  mov     rsi, [r11+28h]
0x180062806  mov     rsp, r11
0x180062809  pop     rdi
0x18006280a  retn
```
