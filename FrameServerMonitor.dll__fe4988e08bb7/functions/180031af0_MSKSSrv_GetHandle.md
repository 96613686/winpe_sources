# MSKSSrv_GetHandle

- ea: `0x180031af0`
- end: `0x180031d4f`
- name: `MSKSSrv_GetHandle`
- size: `607`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180011730`

## callees

- `0x180001dc0`
- `0x18000265c`
- `0x180006a98`
- `0x180031af0`
- `0x180031d58`
- `0x18004bdac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031d0d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031ce5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031ce5`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180031b7b`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180031c0f`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180031b7b`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180031c0f`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x180031bf8`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x180031bf8`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x180031b6a`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x180031b6a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180031cbc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180031cbc`

## pseudocode

```c
__int64 __fastcall MSKSSrv_GetHandle(_QWORD *a1)
{
  signed int v2; // ebx
  __int64 v3; // rdx
  CONFIGRET Device_Interface_List_SizeW; // eax
  signed int v5; // eax
  WCHAR *v6; // rax
  WCHAR *v7; // rsi
  CONFIGRET Device_Interface_ListW; // eax
  signed int v9; // eax
  const struct std::nothrow_t *v10; // rdx
  __int64 v11; // rdx
  unsigned int v12; // ebp
  signed int LastError; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  HANDLE FileW; // rdi
  ULONG pulLen; // [rsp+70h] [rbp+8h] BYREF

  pulLen = 0;
  if ( a1 )
  {
    *a1 = -1;
    v2 = 0;
    Device_Interface_List_SizeW = CM_Get_Device_Interface_List_SizeW(
                                    &pulLen,
                                    &GUID_3c0d501a_140b_11d1_b40f_00a0c9223196,
                                    0,
                                    0);
    if ( Device_Interface_List_SizeW )
    {
      v5 = CM_MapCrToWin32Err(Device_Interface_List_SizeW, 0xDu);
      v2 = v5;
      if ( v5 > 0 )
        v2 = (unsigned __int16)v5 | 0x80070000;
      if ( v2 < 0 )
      {
        if ( !g_wppLevels )
          return (unsigned int)v2;
        v3 = 14;
        goto LABEL_4;
      }
    }
    v6 = (WCHAR *)operator new[](saturated_mul(pulLen, 2u));
    v7 = v6;
    if ( !v6 )
    {
      v2 = -2147024882;
      if ( !g_wppLevels )
        return (unsigned int)v2;
      v3 = 15;
      goto LABEL_4;
    }
    Device_Interface_ListW = CM_Get_Device_Interface_ListW(&GUID_3c0d501a_140b_11d1_b40f_00a0c9223196, 0, v6, pulLen, 0);
    if ( !Device_Interface_ListW && *v7 )
      goto LABEL_22;
    v9 = CM_MapCrToWin32Err(Device_Interface_ListW, 0xDu);
    v2 = v9;
    if ( v9 > 0 )
      v2 = (unsigned __int16)v9 | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_22:
      v12 = 0;
      while ( 1 )
      {
        FileW = CreateFileW(v7, 0xC0000000, 0, 0, 3u, 0x80u, 0);
        if ( FileW != (HANDLE)-1LL )
          goto LABEL_31;
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)(v2 + 2147024894) > 1 || v12 >= 5 )
          break;
        ++v12;
        if ( byte_18005E5A5 )
          WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 27), v14, v15, (unsigned int)v2, v12);
        Sleep(0x3E8u);
      }
      MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( v2 >= 0 )
      {
LABEL_31:
        *a1 = FileW;
        goto LABEL_32;
      }
      if ( !g_wppLevels )
        goto LABEL_32;
      v11 = 18;
    }
    else
    {
      if ( !g_wppLevels )
      {
LABEL_32:
        operator delete(v7, v10);
        return (unsigned int)v2;
      }
      v11 = 16;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids, 0, v2);
    goto LABEL_32;
  }
  v2 = -2147467261;
  if ( g_wppLevels )
  {
    v3 = 13;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, &WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids, 0, v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180031af0  mov     [rsp+arg_8], rbx
0x180031af5  mov     [rsp+arg_10], rbp
0x180031afa  push    rsi
0x180031afb  push    rdi
0x180031afc  push    r12
0x180031afe  push    r14
0x180031b00  push    r15
0x180031b02  sub     rsp, 40h
0x180031b06  xor     r15d, r15d
0x180031b09  mov     r14, rcx
0x180031b0c  mov     [rsp+68h+pulLen], r15d
0x180031b11  test    rcx, rcx
0x180031b14  jnz     short loc_180031B4E
0x180031b16  mov     ebx, 80004003h
0x180031b1b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031b22  jb      loc_180031D13
0x180031b28  lea     edx, [rcx+0Dh]
0x180031b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b32  lea     r8, WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids
0x180031b39  xor     r9d, r9d
0x180031b3c  mov     [rsp+68h+ulFlags], ebx
0x180031b40  mov     rcx, [rcx+10h]
0x180031b44  call    WPP_SF_qD
0x180031b49  jmp     loc_180031D13
0x180031b4e  or      r12, 0FFFFFFFFFFFFFFFFh
0x180031b52  lea     rdx, _GUID_3c0d501a_140b_11d1_b40f_00a0c9223196; InterfaceClassGuid
0x180031b59  mov     [rcx], r12
0x180031b5c  xor     r9d, r9d; ulFlags
0x180031b5f  lea     rcx, [rsp+68h+pulLen]; pulLen
0x180031b64  xor     r8d, r8d; pDeviceID
0x180031b67  mov     ebx, r15d
0x180031b6a  call    cs:__imp_CM_Get_Device_Interface_List_SizeW
0x180031b70  test    eax, eax
0x180031b72  jz      short loc_180031BA8
0x180031b74  lea     edx, [r12+0Eh]; DefaultErr
0x180031b79  mov     ecx, eax; CmReturnCode
0x180031b7b  call    cs:__imp_CM_MapCrToWin32Err
0x180031b81  mov     ebx, eax
0x180031b83  test    eax, eax
0x180031b85  jle     short loc_180031B90
0x180031b87  movzx   ebx, ax
0x180031b8a  or      ebx, 80070000h
0x180031b90  test    ebx, ebx
0x180031b92  jns     short loc_180031BA8
0x180031b94  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031b9b  jb      loc_180031D13
0x180031ba1  mov     edx, 0Eh
0x180031ba6  jmp     short loc_180031B2B
0x180031ba8  mov     ecx, [rsp+68h+pulLen]
0x180031bac  mov     eax, 2
0x180031bb1  mul     rcx
0x180031bb4  cmovb   rax, r12
0x180031bb8  mov     rcx, rax; unsigned __int64
0x180031bbb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180031bc0  mov     rsi, rax
0x180031bc3  test    rax, rax
0x180031bc6  jnz     short loc_180031BE2
0x180031bc8  mov     ebx, 8007000Eh
0x180031bcd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031bd4  jb      loc_180031D13
0x180031bda  lea     edx, [rax+0Fh]
0x180031bdd  jmp     loc_180031B2B
0x180031be2  mov     r9d, [rsp+68h+pulLen]; BufferLen
0x180031be7  lea     rcx, _GUID_3c0d501a_140b_11d1_b40f_00a0c9223196; InterfaceClassGuid
0x180031bee  mov     r8, rsi; Buffer
0x180031bf1  mov     [rsp+68h+ulFlags], r15d; ulFlags
0x180031bf6  xor     edx, edx; pDeviceID
0x180031bf8  call    cs:__imp_CM_Get_Device_Interface_ListW
0x180031bfe  test    eax, eax
0x180031c00  jnz     short loc_180031C08
0x180031c02  cmp     [rsi], r15w
0x180031c06  jnz     short loc_180031C60
0x180031c08  mov     edx, 0Dh; DefaultErr
0x180031c0d  mov     ecx, eax; CmReturnCode
0x180031c0f  call    cs:__imp_CM_MapCrToWin32Err
0x180031c15  mov     ebx, eax
0x180031c17  test    eax, eax
0x180031c19  jle     short loc_180031C24
0x180031c1b  movzx   ebx, ax
0x180031c1e  or      ebx, 80070000h
0x180031c24  test    ebx, ebx
0x180031c26  jns     short loc_180031C60
0x180031c28  mov     rdi, r12
0x180031c2b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031c32  jb      loc_180031CFD
0x180031c38  mov     edx, 10h
0x180031c3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c44  lea     r8, WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids
0x180031c4b  xor     r9d, r9d
0x180031c4e  mov     [rsp+68h+ulFlags], ebx
0x180031c52  mov     rcx, [rcx+10h]
0x180031c56  call    WPP_SF_qD
0x180031c5b  jmp     loc_180031CFD
0x180031c60  mov     ebp, r15d
0x180031c63  jmp     short loc_180031CC2
0x180031c65  call    cs:__imp_GetLastError
0x180031c6b  mov     ebx, eax
0x180031c6d  test    eax, eax
0x180031c6f  jle     short loc_180031C7A
0x180031c71  movzx   ebx, ax
0x180031c74  or      ebx, 80070000h
0x180031c7a  lea     eax, [rbx+7FF8FFFEh]
0x180031c80  cmp     eax, 1
0x180031c83  ja      loc_180031D2E
0x180031c89  cmp     ebp, 5
0x180031c8c  jnb     loc_180031D2E
0x180031c92  inc     ebp
0x180031c94  cmp     cs:byte_18005E5A5, 1
0x180031c9b  jb      short loc_180031CB7
0x180031c9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ca4  mov     r9d, ebx
0x180031ca7  mov     [rsp+68h+ulFlags], ebp
0x180031cab  mov     rcx, [rcx+0D8h]
0x180031cb2  call    WPP_SF_Ddd
0x180031cb7  mov     ecx, 3E8h; dwMilliseconds
0x180031cbc  call    cs:__imp_Sleep
0x180031cc2  mov     [rsp+68h+hTemplateFile], r15; hTemplateFile
0x180031cc7  xor     r9d, r9d; lpSecurityAttributes
0x180031cca  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180031cd2  xor     r8d, r8d; dwShareMode
0x180031cd5  mov     edx, 0C0000000h; dwDesiredAccess
0x180031cda  mov     [rsp+68h+ulFlags], 3; dwCreationDisposition
0x180031ce2  mov     rcx, rsi; lpFileName
0x180031ce5  call    cs:__imp_CreateFileW
0x180031ceb  mov     rdi, rax
0x180031cee  cmp     rax, r12
0x180031cf1  jz      loc_180031C65
0x180031cf7  mov     [r14], rdi
0x180031cfa  mov     rdi, r12
0x180031cfd  mov     rcx, rsi; void *
0x180031d00  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031d05  cmp     rdi, r12
0x180031d08  jz      short loc_180031D13
0x180031d0a  mov     rcx, rdi; hObject
0x180031d0d  call    cs:__imp_CloseHandle
0x180031d13  lea     r11, [rsp+68h+var_28]
0x180031d18  mov     eax, ebx
0x180031d1a  mov     rbx, [r11+38h]
0x180031d1e  mov     rbp, [r11+40h]
0x180031d22  mov     rsp, r11
0x180031d25  pop     r15
0x180031d27  pop     r14
0x180031d29  pop     r12
0x180031d2b  pop     rdi
0x180031d2c  pop     rsi
0x180031d2d  retn
0x180031d2e  cmp     rdi, r12
0x180031d31  jnz     short loc_180031D38
0x180031d33  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031d38  test    ebx, ebx
0x180031d3a  jns     short loc_180031CF7
0x180031d3c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031d43  jb      short loc_180031CFD
0x180031d45  mov     edx, 12h
0x180031d4a  jmp     loc_180031C3D
```
