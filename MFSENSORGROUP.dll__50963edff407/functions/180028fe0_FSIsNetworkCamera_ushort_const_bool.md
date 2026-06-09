# FSIsNetworkCamera(ushort const *,bool *)

- ea: `0x180028fe0`
- end: `0x1800291eb`
- name: `?FSIsNetworkCamera@@YAJPEBGPEA_N@Z`
- size: `523`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, bool *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180057220`
- `0x180066ae0`

## callees

- `0x180005fa0`
- `0x180028fe0`
- `0x180044b28`
- `0x180045300`
- `0x180045900`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18002903b`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800290b7`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800290fc`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18002903b`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800290b7`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800290fc`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180029111`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180029177`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180029111`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180029177`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180029142`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180029142`

## pseudocode

```c
__int64 __fastcall FSIsNetworkCamera(LPCWSTR pszDeviceInterface, bool *a2)
{
  CONFIGRET Device_Interface_PropertyW; // eax
  __int64 v5; // r15
  void *v6; // rax
  void *v7; // rbx
  CONFIGRET v8; // eax
  signed int v9; // eax
  signed int v10; // edi
  signed int v12; // eax
  ULONG PropertyBufferSize; // [rsp+60h] [rbp+30h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+70h] [rbp+40h] BYREF

  if ( !pszDeviceInterface )
    return (unsigned int)-2147024809;
  if ( !a2 )
    return (unsigned int)-2147467261;
  *a2 = 0;
  PropertyType = 0;
  PropertyBufferSize = 0;
  Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                 pszDeviceInterface,
                                 &DEVPKEY_DeviceInterface_ReferenceString,
                                 &PropertyType,
                                 0,
                                 &PropertyBufferSize,
                                 0);
  v5 = PropertyBufferSize;
  if ( Device_Interface_PropertyW == 26 || !Device_Interface_PropertyW )
    goto LABEL_4;
  v12 = CM_MapCrToWin32Err(Device_Interface_PropertyW, 0xDu);
  v10 = v12;
  if ( v12 > 0 )
    v10 = (unsigned __int16)v12 | 0x80070000;
  if ( v10 >= 0 )
  {
LABEL_4:
    v6 = operator new[](v5 + 2, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    if ( !v6 )
    {
      v10 = -2147024882;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          100,
          &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids,
          0,
          -2147024882);
      return (unsigned int)v10;
    }
    memset_0(v6, 0, v5 + 2);
    memset_0(v7, 0, v5 + 2);
    PropertyType = 0;
    PropertyBufferSize = 0;
    v8 = CM_Get_Device_Interface_PropertyW(
           pszDeviceInterface,
           &DEVPKEY_DeviceInterface_ReferenceString,
           &PropertyType,
           0,
           &PropertyBufferSize,
           0);
    if ( v8 == 26 )
    {
      if ( (_DWORD)v5 == -2 )
        goto LABEL_22;
      if ( PropertyBufferSize > (int)v5 + 2 )
      {
        v10 = -1072860816;
LABEL_15:
        operator delete(v7);
        return (unsigned int)v10;
      }
      PropertyBufferSize = v5 + 2;
      v8 = CM_Get_Device_Interface_PropertyW(
             pszDeviceInterface,
             &DEVPKEY_DeviceInterface_ReferenceString,
             &PropertyType,
             (PBYTE)v7,
             &PropertyBufferSize,
             0);
    }
    if ( v8 )
    {
      v9 = CM_MapCrToWin32Err(v8, 0xDu);
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      if ( v10 < 0 )
        goto LABEL_15;
      goto LABEL_13;
    }
LABEL_22:
    v10 = 0;
LABEL_13:
    if ( CompareStringOrdinal(L"{F5E9E279-06E1-4094-96C4-B43B37852EB2}", -1, (LPCWCH)v7, -1, 1) == 2 )
      *a2 = 1;
    goto LABEL_15;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180028fe0  mov     [rsp-28h+arg_8], rbx
0x180028fe5  push    rbp
0x180028fe6  push    rsi
0x180028fe7  push    rdi
0x180028fe8  push    r14
0x180028fea  push    r15
0x180028fec  mov     rbp, rsp
0x180028fef  sub     rsp, 30h
0x180028ff3  mov     r14, rdx
0x180028ff6  mov     rsi, rcx
0x180028ff9  test    rcx, rcx
0x180028ffc  jz      loc_18002919A
0x180029002  test    rdx, rdx
0x180029005  jz      loc_1800291A8
0x18002900b  mov     byte ptr [rdx], 0
0x18002900e  lea     rax, [rbp+arg_0]
0x180029012  lea     rdx, DEVPKEY_DeviceInterface_ReferenceString; PropertyKey
0x180029019  mov     [rsp+30h+ulFlags], 0; ulFlags
0x180029021  xor     r9d, r9d; PropertyBuffer
0x180029024  mov     [rsp+30h+PropertyBufferSize], rax; PropertyBufferSize
0x180029029  lea     r8, [rbp+PropertyType]; PropertyType
0x18002902d  mov     [rbp+PropertyType], 0
0x180029034  mov     [rbp+arg_0], 0
0x18002903b  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x180029041  mov     r15d, [rbp+arg_0]
0x180029045  cmp     eax, 1Ah
0x180029048  jnz     loc_180029168
0x18002904e  lea     rdi, [r15+2]
0x180029052  mov     rcx, rdi; unsigned __int64
0x180029055  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002905c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180029061  mov     rbx, rax
0x180029064  test    rax, rax
0x180029067  jz      loc_1800291B5
0x18002906d  mov     r8, rdi; Size
0x180029070  xor     edx, edx; Val
0x180029072  mov     rcx, rax; void *
0x180029075  call    memset_0
0x18002907a  mov     r8, rdi; Size
0x18002907d  xor     edx, edx; Val
0x18002907f  mov     rcx, rbx; void *
0x180029082  call    memset_0
0x180029087  lea     rax, [rbp+arg_0]
0x18002908b  mov     [rsp+30h+ulFlags], 0; ulFlags
0x180029093  xor     r9d, r9d; PropertyBuffer
0x180029096  mov     [rsp+30h+PropertyBufferSize], rax; PropertyBufferSize
0x18002909b  lea     r8, [rbp+PropertyType]; PropertyType
0x18002909f  mov     [rbp+PropertyType], 0
0x1800290a6  lea     rdx, DEVPKEY_DeviceInterface_ReferenceString; PropertyKey
0x1800290ad  mov     [rbp+arg_0], 0
0x1800290b4  mov     rcx, rsi; pszDeviceInterface
0x1800290b7  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x1800290bd  cmp     eax, 1Ah
0x1800290c0  jnz     short loc_180029102
0x1800290c2  lea     eax, [r15+2]
0x1800290c6  test    eax, eax
0x1800290c8  jz      loc_180029196
0x1800290ce  cmp     [rbp+arg_0], eax
0x1800290d1  ja      loc_1800291A1
0x1800290d7  mov     [rbp+arg_0], eax
0x1800290da  lea     r8, [rbp+PropertyType]; PropertyType
0x1800290de  lea     rax, [rbp+arg_0]
0x1800290e2  mov     [rsp+30h+ulFlags], 0; ulFlags
0x1800290ea  mov     r9, rbx; PropertyBuffer
0x1800290ed  mov     [rsp+30h+PropertyBufferSize], rax; PropertyBufferSize
0x1800290f2  lea     rdx, DEVPKEY_DeviceInterface_ReferenceString; PropertyKey
0x1800290f9  mov     rcx, rsi; pszDeviceInterface
0x1800290fc  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x180029102  test    eax, eax
0x180029104  jz      loc_180029196
0x18002910a  mov     edx, 0Dh; DefaultErr
0x18002910f  mov     ecx, eax; CmReturnCode
0x180029111  call    cs:__imp_CM_MapCrToWin32Err
0x180029117  mov     edi, eax
0x180029119  test    eax, eax
0x18002911b  jle     short loc_180029126
0x18002911d  movzx   edi, ax
0x180029120  or      edi, 80070000h
0x180029126  test    edi, edi
0x180029128  js      short loc_18002914D
0x18002912a  or      edx, 0FFFFFFFFh; cchCount1
0x18002912d  mov     dword ptr [rsp+30h+PropertyBufferSize], 1; bIgnoreCase
0x180029135  mov     r9d, edx; cchCount2
0x180029138  lea     rcx, String1; "{F5E9E279-06E1-4094-96C4-B43B37852EB2}"
0x18002913f  mov     r8, rbx; lpString2
0x180029142  call    cs:__imp_CompareStringOrdinal
0x180029148  cmp     eax, 2
0x18002914b  jz      short loc_1800291AF
0x18002914d  mov     rcx, rbx; Block
0x180029150  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029155  mov     rbx, [rsp+30h+arg_8]
0x18002915a  mov     eax, edi
0x18002915c  add     rsp, 30h
0x180029160  pop     r15
0x180029162  pop     r14
0x180029164  pop     rdi
0x180029165  pop     rsi
0x180029166  pop     rbp
0x180029167  retn
0x180029168  test    eax, eax
0x18002916a  jz      loc_18002904E
0x180029170  mov     edx, 0Dh; DefaultErr
0x180029175  mov     ecx, eax; CmReturnCode
0x180029177  call    cs:__imp_CM_MapCrToWin32Err
0x18002917d  mov     edi, eax
0x18002917f  test    eax, eax
0x180029181  jle     short loc_18002918C
0x180029183  movzx   edi, ax
0x180029186  or      edi, 80070000h
0x18002918c  test    edi, edi
0x18002918e  jns     loc_18002904E
0x180029194  jmp     short loc_180029155
0x180029196  xor     edi, edi
0x180029198  jmp     short loc_18002912A
0x18002919a  mov     edi, 80070057h
0x18002919f  jmp     short loc_180029155
0x1800291a1  mov     edi, 0C00D7170h
0x1800291a6  jmp     short loc_18002914D
0x1800291a8  mov     edi, 80004003h
0x1800291ad  jmp     short loc_180029155
0x1800291af  mov     byte ptr [r14], 1
0x1800291b3  jmp     short loc_18002914D
0x1800291b5  mov     edi, 8007000Eh
0x1800291ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800291c1  jb      short loc_180029155
0x1800291c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800291ca  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x1800291d1  mov     edx, 64h ; 'd'
0x1800291d6  mov     dword ptr [rsp+30h+PropertyBufferSize], edi
0x1800291da  xor     r9d, r9d
0x1800291dd  mov     rcx, [rcx+10h]
0x1800291e1  call    WPP_SF_qD
0x1800291e6  jmp     loc_180029155
```
