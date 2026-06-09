# MSKSSrv_GetHandle

- ea: `0x18006133c`
- end: `0x18006159b`
- name: `MSKSSrv_GetHandle`
- size: `607`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001aadc`
- `0x18001fdd0`
- `0x18006bf9c`
- `0x180090b60`

## callees

- `0x1800041f0`
- `0x180004f20`
- `0x180009608`
- `0x18006133c`
- `0x180061acc`
- `0x1800e37a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800614b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800614b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061559`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061559`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180061508`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180061508`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800613c7`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006145b`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800613c7`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006145b`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x1800613b6`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x1800613b6`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x180061444`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x180061444`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061531`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061531`

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
        if ( byte_18010EC4D )
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
0x18006133c  mov     [rsp+arg_8], rbx
0x180061341  mov     [rsp+arg_10], rbp
0x180061346  push    rsi
0x180061347  push    rdi
0x180061348  push    r12
0x18006134a  push    r14
0x18006134c  push    r15
0x18006134e  sub     rsp, 40h
0x180061352  xor     r15d, r15d
0x180061355  mov     r14, rcx
0x180061358  mov     [rsp+68h+pulLen], r15d
0x18006135d  test    rcx, rcx
0x180061360  jnz     short loc_18006139A
0x180061362  mov     ebx, 80004003h
0x180061367  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006136e  jb      loc_18006155F
0x180061374  lea     edx, [rcx+0Dh]
0x180061377  mov     rcx, cs:WPP_GLOBAL_Control
0x18006137e  lea     r8, WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids
0x180061385  xor     r9d, r9d
0x180061388  mov     [rsp+68h+ulFlags], ebx
0x18006138c  mov     rcx, [rcx+10h]
0x180061390  call    WPP_SF_qD
0x180061395  jmp     loc_18006155F
0x18006139a  or      r12, 0FFFFFFFFFFFFFFFFh
0x18006139e  lea     rdx, _GUID_3c0d501a_140b_11d1_b40f_00a0c9223196; InterfaceClassGuid
0x1800613a5  mov     [rcx], r12
0x1800613a8  xor     r9d, r9d; ulFlags
0x1800613ab  lea     rcx, [rsp+68h+pulLen]; pulLen
0x1800613b0  xor     r8d, r8d; pDeviceID
0x1800613b3  mov     ebx, r15d
0x1800613b6  call    cs:__imp_CM_Get_Device_Interface_List_SizeW
0x1800613bc  test    eax, eax
0x1800613be  jz      short loc_1800613F4
0x1800613c0  lea     edx, [r12+0Eh]; DefaultErr
0x1800613c5  mov     ecx, eax; CmReturnCode
0x1800613c7  call    cs:__imp_CM_MapCrToWin32Err
0x1800613cd  mov     ebx, eax
0x1800613cf  test    eax, eax
0x1800613d1  jle     short loc_1800613DC
0x1800613d3  movzx   ebx, ax
0x1800613d6  or      ebx, 80070000h
0x1800613dc  test    ebx, ebx
0x1800613de  jns     short loc_1800613F4
0x1800613e0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800613e7  jb      loc_18006155F
0x1800613ed  mov     edx, 0Eh
0x1800613f2  jmp     short loc_180061377
0x1800613f4  mov     ecx, [rsp+68h+pulLen]
0x1800613f8  mov     eax, 2
0x1800613fd  mul     rcx
0x180061400  cmovb   rax, r12
0x180061404  mov     rcx, rax; unsigned __int64
0x180061407  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006140c  mov     rsi, rax
0x18006140f  test    rax, rax
0x180061412  jnz     short loc_18006142E
0x180061414  mov     ebx, 8007000Eh
0x180061419  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061420  jb      loc_18006155F
0x180061426  lea     edx, [rax+0Fh]
0x180061429  jmp     loc_180061377
0x18006142e  mov     r9d, [rsp+68h+pulLen]; BufferLen
0x180061433  lea     rcx, _GUID_3c0d501a_140b_11d1_b40f_00a0c9223196; InterfaceClassGuid
0x18006143a  mov     r8, rsi; Buffer
0x18006143d  mov     [rsp+68h+ulFlags], r15d; ulFlags
0x180061442  xor     edx, edx; pDeviceID
0x180061444  call    cs:__imp_CM_Get_Device_Interface_ListW
0x18006144a  test    eax, eax
0x18006144c  jnz     short loc_180061454
0x18006144e  cmp     [rsi], r15w
0x180061452  jnz     short loc_1800614AC
0x180061454  mov     edx, 0Dh; DefaultErr
0x180061459  mov     ecx, eax; CmReturnCode
0x18006145b  call    cs:__imp_CM_MapCrToWin32Err
0x180061461  mov     ebx, eax
0x180061463  test    eax, eax
0x180061465  jle     short loc_180061470
0x180061467  movzx   ebx, ax
0x18006146a  or      ebx, 80070000h
0x180061470  test    ebx, ebx
0x180061472  jns     short loc_1800614AC
0x180061474  mov     rdi, r12
0x180061477  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006147e  jb      loc_180061549
0x180061484  mov     edx, 10h
0x180061489  mov     rcx, cs:WPP_GLOBAL_Control
0x180061490  lea     r8, WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids
0x180061497  xor     r9d, r9d
0x18006149a  mov     [rsp+68h+ulFlags], ebx
0x18006149e  mov     rcx, [rcx+10h]
0x1800614a2  call    WPP_SF_qD
0x1800614a7  jmp     loc_180061549
0x1800614ac  mov     ebp, r15d
0x1800614af  jmp     short loc_18006150E
0x1800614b1  call    cs:__imp_GetLastError
0x1800614b7  mov     ebx, eax
0x1800614b9  test    eax, eax
0x1800614bb  jle     short loc_1800614C6
0x1800614bd  movzx   ebx, ax
0x1800614c0  or      ebx, 80070000h
0x1800614c6  lea     eax, [rbx+7FF8FFFEh]
0x1800614cc  cmp     eax, 1
0x1800614cf  ja      loc_18006157A
0x1800614d5  cmp     ebp, 5
0x1800614d8  jnb     loc_18006157A
0x1800614de  inc     ebp
0x1800614e0  cmp     cs:byte_18010EC4D, 1
0x1800614e7  jb      short loc_180061503
0x1800614e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800614f0  mov     r9d, ebx
0x1800614f3  mov     [rsp+68h+ulFlags], ebp
0x1800614f7  mov     rcx, [rcx+0D8h]
0x1800614fe  call    WPP_SF_Ddd
0x180061503  mov     ecx, 3E8h; dwMilliseconds
0x180061508  call    cs:__imp_Sleep
0x18006150e  mov     [rsp+68h+hTemplateFile], r15; hTemplateFile
0x180061513  xor     r9d, r9d; lpSecurityAttributes
0x180061516  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006151e  xor     r8d, r8d; dwShareMode
0x180061521  mov     edx, 0C0000000h; dwDesiredAccess
0x180061526  mov     [rsp+68h+ulFlags], 3; dwCreationDisposition
0x18006152e  mov     rcx, rsi; lpFileName
0x180061531  call    cs:__imp_CreateFileW
0x180061537  mov     rdi, rax
0x18006153a  cmp     rax, r12
0x18006153d  jz      loc_1800614B1
0x180061543  mov     [r14], rdi
0x180061546  mov     rdi, r12
0x180061549  mov     rcx, rsi; void *
0x18006154c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180061551  cmp     rdi, r12
0x180061554  jz      short loc_18006155F
0x180061556  mov     rcx, rdi; hObject
0x180061559  call    cs:__imp_CloseHandle
0x18006155f  lea     r11, [rsp+68h+var_28]
0x180061564  mov     eax, ebx
0x180061566  mov     rbx, [r11+38h]
0x18006156a  mov     rbp, [r11+40h]
0x18006156e  mov     rsp, r11
0x180061571  pop     r15
0x180061573  pop     r14
0x180061575  pop     r12
0x180061577  pop     rdi
0x180061578  pop     rsi
0x180061579  retn
0x18006157a  cmp     rdi, r12
0x18006157d  jnz     short loc_180061584
0x18006157f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "h != INVALID_HANDLE_VALUE")
0x180061584  test    ebx, ebx
0x180061586  jns     short loc_180061543
0x180061588  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006158f  jb      short loc_180061549
0x180061591  mov     edx, 12h
0x180061596  jmp     loc_180061489
```
