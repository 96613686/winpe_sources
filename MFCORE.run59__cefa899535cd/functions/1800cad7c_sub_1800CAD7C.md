# sub_1800CAD7C

- ea: `0x1800cad7c`
- end: `0x1800cb16a`
- name: `sub_1800CAD7C`
- size: `1006`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18017b2c8`

## callees

- `0x180050d6c`
- `0x18009efc4`
- `0x1800caaac`
- `0x1800cac5c`
- `0x1800cad7c`
- `0x1800cc484`
- `0x180164580`
- `0x18017c198`
- `0x180258480`
- `0x1802592a0`
- `0x1802d0d0c`
- `0x180344d40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800caf1e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800caf1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800cadf4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800cadf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800caf83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800caf83`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800caf4b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800caf4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800caf38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800caf38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cafd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cafd9`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800caee2`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800caee2`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800caeb6`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800cb0e5`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800caeb6`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800cb0e5`

## pseudocode

```c
void __fastcall sub_1800CAD7C(__int64 *a1, _DWORD *a2, _DWORD *a3)
{
  __int64 v6; // rax
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  int v10; // r14d
  const char *v11; // rsi
  const WCHAR *v12; // rbx
  CONFIGRET Device_Interface_PropertyW; // eax
  signed int v14; // eax
  bool v15; // sf
  DWORD CurrentProcessId; // eax
  __int64 v17; // r9
  __int64 v18; // rdx
  signed int LastError; // eax
  const char *v20; // r9
  _BYTE v21[4]; // [rsp+30h] [rbp-D0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+34h] [rbp-CCh] BYREF
  ULONG PropertyBufferSize; // [rsp+38h] [rbp-C8h] BYREF
  ULONG v24; // [rsp+3Ch] [rbp-C4h] BYREF
  LPCWSTR pszDeviceInterface; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR *p_pszDeviceInterface; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  char v28; // [rsp+58h] [rbp-A8h]
  BYTE PropertyBuffer[16]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF

  memset(Filename, 0, 0x208u);
  *a2 = 0;
  v24 = 0;
  *(GUID *)PropertyBuffer = guidExtendedType;
  pszDeviceInterface = 0;
  v21[0] = 0;
  *a3 = 0;
  GetModuleFileNameW(0, Filename, 0x104u);
  if ( (unsigned __int8)byte_1803CECED >= 8u )
    sub_180164580(
      *((_QWORD *)RequestContext + 27),
      106,
      (unsigned int)&stru_180365F00,
      (unsigned int)Filename,
      (char)a1);
  v27 = 0;
  p_pszDeviceInterface = &pszDeviceInterface;
  v6 = *a1;
  v28 = 1;
  v10 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64 *, ULONG *))(v6 + 104))(
          a1,
          &xmmword_180365EE0,
          &v27,
          &v24);
  if ( v28 )
    sub_1800CC484(p_pszDeviceInterface, v27);
  v11 = "true";
  if ( v10 < 0 )
  {
    if ( byte_1803CECE8 )
      sub_180050D6C(*((_QWORD *)RequestContext + 2), 107, &stru_180365F00, 0, v10);
    goto LABEL_23;
  }
  v12 = pszDeviceInterface;
  v24 = 0;
  PropertyType = 0;
  PropertyBufferSize = 0;
  if ( pszDeviceInterface )
  {
    Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                   pszDeviceInterface,
                                   &stru_180364D50,
                                   &PropertyType,
                                   0,
                                   &PropertyBufferSize,
                                   0);
    v24 = PropertyBufferSize;
    if ( Device_Interface_PropertyW == 26 )
    {
      if ( PropertyBufferSize > 0x10 )
        goto LABEL_12;
      PropertyBufferSize = 16;
      Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                     v12,
                                     &stru_180364D50,
                                     &PropertyType,
                                     PropertyBuffer,
                                     &PropertyBufferSize,
                                     0);
    }
    if ( !Device_Interface_PropertyW )
      goto LABEL_35;
    v14 = CM_MapCrToWin32Err(Device_Interface_PropertyW, 0xDu);
    v15 = v14 < 0;
    if ( v14 > 0 )
      v15 = 1;
    if ( !v15 )
    {
LABEL_35:
      *a2 = 2;
      if ( (unsigned __int8)byte_1803CECED < 8u )
        goto LABEL_24;
      sub_18009EFC4(*((_QWORD *)RequestContext + 27), 108, &stru_180365F00);
      goto LABEL_23;
    }
  }
LABEL_12:
  if ( sub_18017C198(v21) )
  {
    *a2 = 1;
    if ( (unsigned __int8)byte_1803CECED < 8u )
      goto LABEL_24;
    v20 = "true";
    if ( !v21[0] )
      v20 = "false";
    sub_1800CAC5C(*((_QWORD *)RequestContext + 27), 111, &stru_180365F00, v20);
    goto LABEL_23;
  }
  if ( !wcsstr(Filename, L"RealSenseDCM") )
  {
LABEL_23:
    if ( (unsigned __int8)byte_1803CECED >= 8u )
    {
      if ( *a3 != 1 )
        v11 = "false";
      sub_1802D0D0C(*((_QWORD *)RequestContext + 27), v7, v8, v9, *a2, (__int64)v11);
    }
    goto LABEL_24;
  }
  PropertyType = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &PropertyType) )
  {
    if ( (unsigned __int8)byte_1803CECED < 8u )
      goto LABEL_24;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v18 = 113;
    v17 = (unsigned int)LastError;
    goto LABEL_22;
  }
  v17 = PropertyType;
  if ( !PropertyType )
  {
    *a3 = 1;
    *a2 = 2;
  }
  if ( (unsigned __int8)byte_1803CECED >= 8u )
  {
    v18 = 112;
LABEL_22:
    sub_1800CAAAC(*((_QWORD *)RequestContext + 27), v18, &stru_180365F00, v17);
    goto LABEL_23;
  }
LABEL_24:
  if ( pszDeviceInterface )
    CoTaskMemFree((LPVOID)pszDeviceInterface);
}

```

## disassembly

```asm
0x1800cad7c  push    rbp
0x1800cad7e  push    rbx
0x1800cad7f  push    rsi
0x1800cad80  push    rdi
0x1800cad81  push    r12
0x1800cad83  push    r14
0x1800cad85  push    r15
0x1800cad87  lea     rbp, [rsp-190h]
0x1800cad8f  sub     rsp, 290h
0x1800cad96  mov     rax, cs:__security_cookie
0x1800cad9d  xor     rax, rsp
0x1800cada0  mov     [rbp+1C0h+var_40], rax
0x1800cada7  mov     r15, r8
0x1800cadaa  mov     rdi, rdx
0x1800cadad  mov     rbx, rcx
0x1800cadb0  xor     edx, edx; Val
0x1800cadb2  mov     r8d, 208h; Size
0x1800cadb8  lea     rcx, [rsp+2C0h+Filename]; void *
0x1800cadbd  call    memset
0x1800cadc2  movups  xmm0, xmmword ptr cs:guidExtendedType.Data1
0x1800cadc9  xor     r12d, r12d
0x1800cadcc  lea     rdx, [rsp+2C0h+Filename]; lpFilename
0x1800cadd1  mov     [rdi], r12d
0x1800cadd4  mov     r8d, 104h; nSize
0x1800cadda  xor     ecx, ecx; hModule
0x1800caddc  mov     [rsp+2C0h+var_284], r12d
0x1800cade1  movdqu  xmmword ptr [rsp+2C0h+PropertyBuffer], xmm0
0x1800cade7  mov     [rsp+2C0h+pszDeviceInterface], r12
0x1800cadec  mov     [rsp+2C0h+var_290], r12b
0x1800cadf1  mov     [r15], r12d
0x1800cadf4  call    cs:GetModuleFileNameW
0x1800cadfb  nop     dword ptr [rax+rax+00h]
0x1800cae00  cmp     cs:byte_1803CECED, 8
0x1800cae07  jnb     loc_1800CB04D
0x1800cae0d  lea     rax, [rsp+2C0h+pszDeviceInterface]
0x1800cae12  mov     [rsp+2C0h+var_270], r12
0x1800cae17  mov     [rsp+2C0h+var_278], rax
0x1800cae1c  lea     r9, [rsp+2C0h+var_284]
0x1800cae21  mov     rax, [rbx]
0x1800cae24  lea     r8, [rsp+2C0h+var_270]
0x1800cae29  lea     rdx, xmmword_180365EE0
0x1800cae30  mov     [rsp+2C0h+var_268], 1
0x1800cae35  mov     rcx, rbx
0x1800cae38  mov     rax, [rax+68h]
0x1800cae3c  call    cs:__guard_dispatch_icall_fptr
0x1800cae42  mov     ebx, eax
0x1800cae44  mov     r14d, eax
0x1800cae47  shr     ebx, 1Fh
0x1800cae4a  cmp     [rsp+2C0h+var_268], r12b
0x1800cae4f  jz      short loc_1800CAE60
0x1800cae51  mov     rdx, [rsp+2C0h+var_270]
0x1800cae56  mov     rcx, [rsp+2C0h+var_278]
0x1800cae5b  call    sub_1800CC484
0x1800cae60  lea     rsi, aTrue_0; "true"
0x1800cae67  lea     rax, aFalse_0; "false"
0x1800cae6e  test    bl, bl
0x1800cae70  jnz     loc_1800CB07B
0x1800cae76  mov     rbx, [rsp+2C0h+pszDeviceInterface]
0x1800cae7b  mov     r14d, 80070000h
0x1800cae81  mov     [rsp+2C0h+var_284], r12d
0x1800cae86  mov     [rsp+2C0h+PropertyType], r12d
0x1800cae8b  mov     [rsp+2C0h+var_288], r12d
0x1800cae90  test    rbx, rbx
0x1800cae93  jz      short loc_1800CAF00
0x1800cae95  lea     rax, [rsp+2C0h+var_288]
0x1800cae9a  mov     [rsp+2C0h+ulFlags], r12d; ulFlags
0x1800cae9f  xor     r9d, r9d; PropertyBuffer
0x1800caea2  mov     [rsp+2C0h+PropertyBufferSize], rax; PropertyBufferSize
0x1800caea7  lea     r8, [rsp+2C0h+PropertyType]; PropertyType
0x1800caeac  mov     rcx, rbx; pszDeviceInterface
0x1800caeaf  lea     rdx, stru_180364D50; PropertyKey
0x1800caeb6  call    cs:CM_Get_Device_Interface_PropertyW
0x1800caebd  nop     dword ptr [rax+rax+00h]
0x1800caec2  mov     ecx, [rsp+2C0h+var_288]
0x1800caec6  mov     [rsp+2C0h+var_284], ecx
0x1800caeca  cmp     eax, 1Ah
0x1800caecd  jz      loc_1800CB0B1
0x1800caed3  test    eax, eax
0x1800caed5  jz      loc_1800CB0F6
0x1800caedb  mov     edx, 0Dh; DefaultErr
0x1800caee0  mov     ecx, eax; CmReturnCode
0x1800caee2  call    cs:CM_MapCrToWin32Err
0x1800caee9  nop     dword ptr [rax+rax+00h]
0x1800caeee  test    eax, eax
0x1800caef0  jle     short loc_1800CAEFA
0x1800caef2  movzx   eax, ax
0x1800caef5  or      eax, r14d
0x1800caef8  test    eax, eax
0x1800caefa  jns     loc_1800CB0F6
0x1800caf00  lea     rcx, [rsp+2C0h+var_290]
0x1800caf05  call    sub_18017C198
0x1800caf0a  test    al, al
0x1800caf0c  jnz     loc_1800CB007
0x1800caf12  lea     rdx, aRealsensedcm; "RealSenseDCM"
0x1800caf19  lea     rcx, [rsp+2C0h+Filename]; Str
0x1800caf1e  call    cs:wcsstr
0x1800caf25  nop     dword ptr [rax+rax+00h]
0x1800caf2a  test    rax, rax
0x1800caf2d  jz      loc_1800CAFBB
0x1800caf33  mov     [rsp+2C0h+PropertyType], r12d
0x1800caf38  call    cs:GetCurrentProcessId
0x1800caf3f  nop     dword ptr [rax+rax+00h]
0x1800caf44  mov     ecx, eax; dwProcessId
0x1800caf46  lea     rdx, [rsp+2C0h+PropertyType]; pSessionId
0x1800caf4b  call    cs:ProcessIdToSessionId
0x1800caf52  nop     dword ptr [rax+rax+00h]
0x1800caf57  cmp     eax, 1
0x1800caf5a  jnz     loc_1800CB12D
0x1800caf60  mov     r9d, [rsp+2C0h+PropertyType]
0x1800caf65  test    r9d, r9d
0x1800caf68  jnz     short loc_1800CAF73
0x1800caf6a  mov     [r15], eax
0x1800caf6d  mov     dword ptr [rdi], 2
0x1800caf73  cmp     cs:byte_1803CECED, 8
0x1800caf7a  jb      short loc_1800CAFCF
0x1800caf7c  mov     edx, 70h ; 'p'
0x1800caf81  jmp     short loc_1800CAFA1
0x1800caf83  call    cs:GetLastError
0x1800caf8a  nop     dword ptr [rax+rax+00h]
0x1800caf8f  test    eax, eax
0x1800caf91  jle     short loc_1800CAF99
0x1800caf93  movzx   eax, ax
0x1800caf96  or      eax, r14d
0x1800caf99  mov     edx, 71h ; 'q'
0x1800caf9e  mov     r9d, eax
0x1800cafa1  mov     rcx, cs:RequestContext
0x1800cafa8  lea     r8, stru_180365F00
0x1800cafaf  mov     rcx, [rcx+0D8h]
0x1800cafb6  call    sub_1800CAAAC
0x1800cafbb  lea     rax, aFalse_0; "false"
0x1800cafc2  cmp     cs:byte_1803CECED, 8
0x1800cafc9  jnb     loc_1800CB13F
0x1800cafcf  mov     rcx, [rsp+2C0h+pszDeviceInterface]; pv
0x1800cafd4  test    rcx, rcx
0x1800cafd7  jz      short loc_1800CAFE5
0x1800cafd9  call    cs:CoTaskMemFree
0x1800cafe0  nop     dword ptr [rax+rax+00h]
0x1800cafe5  mov     rcx, [rbp+1C0h+var_40]
0x1800cafec  xor     rcx, rsp; StackCookie
0x1800cafef  call    __security_check_cookie
0x1800caff4  add     rsp, 290h
0x1800caffb  pop     r15
0x1800caffd  pop     r14
0x1800cafff  pop     r12
0x1800cb001  pop     rdi
0x1800cb002  pop     rsi
0x1800cb003  pop     rbx
0x1800cb004  pop     rbp
0x1800cb005  retn
0x1800cb007  mov     dword ptr [rdi], 1
0x1800cb00d  cmp     cs:byte_1803CECED, 8
0x1800cb014  jb      short loc_1800CAFCF
0x1800cb016  mov     rcx, cs:RequestContext
0x1800cb01d  lea     rax, aFalse_0; "false"
0x1800cb024  cmp     [rsp+2C0h+var_290], r12b
0x1800cb029  lea     r8, stru_180365F00
0x1800cb030  mov     r9, rsi
0x1800cb033  mov     edx, 6Fh ; 'o'
0x1800cb038  cmovz   r9, rax
0x1800cb03c  mov     rcx, [rcx+0D8h]
0x1800cb043  call    sub_1800CAC5C
0x1800cb048  jmp     loc_1800CAFBB
0x1800cb04d  mov     rcx, cs:RequestContext
0x1800cb054  lea     r9, [rsp+2C0h+Filename]
0x1800cb059  mov     edx, 6Ah ; 'j'
0x1800cb05e  mov     [rsp+2C0h+PropertyBufferSize], rbx
0x1800cb063  lea     r8, stru_180365F00
0x1800cb06a  mov     rcx, [rcx+0D8h]
0x1800cb071  call    sub_180164580
0x1800cb076  jmp     loc_1800CAE0D
0x1800cb07b  cmp     cs:byte_1803CECE8, 1
0x1800cb082  jb      loc_1800CAFC2
0x1800cb088  mov     rcx, cs:RequestContext
0x1800cb08f  lea     r8, stru_180365F00
0x1800cb096  mov     edx, 6Bh ; 'k'
0x1800cb09b  mov     dword ptr [rsp+2C0h+PropertyBufferSize], r14d
0x1800cb0a0  xor     r9d, r9d
0x1800cb0a3  mov     rcx, [rcx+10h]
0x1800cb0a7  call    sub_180050D6C
0x1800cb0ac  jmp     loc_1800CAFBB
0x1800cb0b1  cmp     ecx, 10h
0x1800cb0b4  ja      loc_1800CAF00
0x1800cb0ba  lea     rax, [rsp+2C0h+var_288]
0x1800cb0bf  mov     [rsp+2C0h+ulFlags], r12d; ulFlags
0x1800cb0c4  lea     r9, [rsp+2C0h+PropertyBuffer]; PropertyBuffer
0x1800cb0c9  mov     [rsp+2C0h+PropertyBufferSize], rax; PropertyBufferSize
0x1800cb0ce  lea     r8, [rsp+2C0h+PropertyType]; PropertyType
0x1800cb0d3  mov     [rsp+2C0h+var_288], 10h
0x1800cb0db  lea     rdx, stru_180364D50; PropertyKey
0x1800cb0e2  mov     rcx, rbx; pszDeviceInterface
0x1800cb0e5  call    cs:CM_Get_Device_Interface_PropertyW
0x1800cb0ec  nop     dword ptr [rax+rax+00h]
0x1800cb0f1  jmp     loc_1800CAED3
0x1800cb0f6  mov     dword ptr [rdi], 2
0x1800cb0fc  cmp     cs:byte_1803CECED, 8
0x1800cb103  jb      loc_1800CAFCF
0x1800cb109  mov     rcx, cs:RequestContext
0x1800cb110  lea     r8, stru_180365F00
0x1800cb117  mov     edx, 6Ch ; 'l'
0x1800cb11c  mov     rcx, [rcx+0D8h]
0x1800cb123  call    sub_18009EFC4
0x1800cb128  jmp     loc_1800CAFBB
0x1800cb12d  cmp     cs:byte_1803CECED, 8
0x1800cb134  jb      loc_1800CAFCF
0x1800cb13a  jmp     loc_1800CAF83
0x1800cb13f  cmp     dword ptr [r15], 1
0x1800cb143  mov     rcx, cs:RequestContext
0x1800cb14a  cmovnz  rsi, rax
0x1800cb14e  mov     eax, [rdi]
0x1800cb150  mov     qword ptr [rsp+2C0h+ulFlags], rsi
0x1800cb155  mov     dword ptr [rsp+2C0h+PropertyBufferSize], eax
0x1800cb159  mov     rcx, [rcx+0D8h]
0x1800cb160  call    sub_1802D0D0C
0x1800cb165  jmp     loc_1800CAFCF
```
