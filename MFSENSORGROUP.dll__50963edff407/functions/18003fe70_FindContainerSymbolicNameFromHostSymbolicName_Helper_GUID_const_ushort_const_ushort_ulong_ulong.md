# FindContainerSymbolicNameFromHostSymbolicName_Helper(_GUID const &,ushort const *,ushort *,ulong,ulong *)

- ea: `0x18003fe70`
- end: `0x1800401cd`
- name: `?FindContainerSymbolicNameFromHostSymbolicName_Helper@@YAJAEBU_GUID@@PEBGPEAGKPEAK@Z`
- size: `861`
- prototype: `__int64 __fastcall(const struct _GUID *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x18001a100`

## callees

- `0x180005b90`
- `0x180005fa0`
- `0x18000d1f0`
- `0x180015e80`
- `0x180016328`
- `0x18001635c`
- `0x180025d70`
- `0x18003ccec`
- `0x18003fe70`
- `0x180044b28`
- `0x180044f30`
- `0x180045900`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004009f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004009f`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18003ff28`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18003ff28`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x18003ff17`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x18003ff17`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x18003ff91`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x18003ff91`

## pseudocode

```c
__int64 __fastcall FindContainerSymbolicNameFromHostSymbolicName_Helper(
        const struct _GUID *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  GUID v3; // xmm0
  ULONG v4; // esi
  WCHAR *v7; // r14
  int v8; // eax
  signed int v9; // ebx
  __int64 v10; // rdx
  CONFIGRET Device_Interface_List_SizeW; // eax
  signed int v12; // eax
  void **unique; // rax
  void *v14; // rcx
  PZZWSTR v15; // rbx
  CONFIGRET Device_Interface_ListW; // edi
  __int64 v17; // rdx
  ULONG v18; // r15d
  const WCHAR *v19; // rdi
  unsigned __int64 v20; // r10
  ULONG pulLen; // [rsp+30h] [rbp-D0h] BYREF
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  PZZWSTR Buffer; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v25; // [rsp+48h] [rbp-B8h] BYREF
  GUID InterfaceClassGuid; // [rsp+50h] [rbp-B0h] BYREF
  DEVPROPKEY PropertyKey; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszDeviceInterface[264]; // [rsp+80h] [rbp-80h] BYREF
  BYTE PropertyBuffer[528]; // [rsp+290h] [rbp+190h] BYREF

  v3 = *a1;
  v4 = 0;
  v25 = 0;
  v7 = 0;
  InterfaceClassGuid = v3;
  if ( !a2 )
  {
    v8 = -2147024809;
    v9 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_49;
    v10 = 117;
    goto LABEL_4;
  }
  if ( a3 )
  {
    while ( 1 )
    {
      Buffer = 0;
      pulLen = 0;
      Device_Interface_List_SizeW = CM_Get_Device_Interface_List_SizeW(&pulLen, &InterfaceClassGuid, 0, 0);
      if ( Device_Interface_List_SizeW )
      {
        v12 = CM_MapCrToWin32Err(Device_Interface_List_SizeW, 0xDu);
        v9 = v12;
        if ( v12 > 0 )
          v9 = (unsigned __int16)v12 | 0x80070000;
        if ( v9 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_49;
          v17 = 119;
          goto LABEL_48;
        }
      }
      unique = (void **)wil::make_unique_nothrow<unsigned short [0]>(&Block, pulLen);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
        (void **)&Buffer,
        unique);
      v14 = Block;
      Block = 0;
      if ( v14 )
        operator delete(v14);
      v15 = Buffer;
      if ( !Buffer )
        break;
      Device_Interface_ListW = CM_Get_Device_Interface_ListW(&InterfaceClassGuid, 0, Buffer, pulLen, 0);
      if ( !Device_Interface_ListW )
      {
        wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::swap(&v25, &Buffer);
        v18 = pulLen;
        if ( Buffer )
          operator delete(Buffer);
        v7 = (WCHAR *)v25;
        if ( v18 > 1 )
        {
          PropertyKey.pid = 4;
          v19 = v25;
          PropertyKey.fmtid = (DEVPROPGUID)SensorGroupFMTGUID;
          while ( *v19 && v4 < v18 )
          {
            memset_0(pszDeviceInterface, 0, 0x208u);
            memset_0(PropertyBuffer, 0, 0x208u);
            v8 = FSGetUniqueSymbolicName(v19, pszDeviceInterface, 0x104u, 0);
            v9 = v8;
            if ( v8 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_49;
              v10 = 121;
              goto LABEL_4;
            }
            if ( (int)FSGetDeviceInterfaceProperty(pszDeviceInterface, &PropertyKey, PropertyBuffer, 0x208u, &pulLen) >= 0
              && !(unsigned int)_o__wcsicmp(a2, PropertyBuffer) )
            {
              Block = 0;
              v8 = StringCchLengthW(pszDeviceInterface, 0x104u, (unsigned __int64 *)&Block);
              v9 = v8;
              if ( v8 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_49;
                v10 = 122;
                goto LABEL_4;
              }
              if ( (unsigned __int64)Block + 1 > v20 )
              {
                v9 = -1072860816;
                if ( !g_wppLevels )
                  goto LABEL_49;
                v17 = 123;
                goto LABEL_48;
              }
              v8 = StringCchCopyW(a3, v20, pszDeviceInterface);
              v9 = v8;
              if ( v8 < 0 && g_wppLevels )
              {
                v10 = 124;
                goto LABEL_4;
              }
              goto LABEL_49;
            }
            if ( *v19 )
            {
              do
              {
                ++v19;
                ++v4;
              }
              while ( *v19 );
              if ( v4 >= v18 )
                continue;
            }
            ++v4;
            ++v19;
          }
        }
LABEL_19:
        v9 = -1072875819;
        goto LABEL_49;
      }
      if ( v15 )
        operator delete(v15);
      if ( Device_Interface_ListW != 26 )
        goto LABEL_19;
    }
    v9 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_49;
    v17 = 120;
LABEL_48:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v9);
  }
  else
  {
    v8 = -2147024809;
    v9 = -2147024809;
    if ( g_wppLevels )
    {
      v10 = 118;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v8);
    }
  }
LABEL_49:
  if ( v7 )
    operator delete(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003fe70  mov     [rsp-8+arg_18], rbx
0x18003fe75  push    rbp
0x18003fe76  push    rsi
0x18003fe77  push    rdi
0x18003fe78  push    r12
0x18003fe7a  push    r13
0x18003fe7c  push    r14
0x18003fe7e  push    r15
0x18003fe80  lea     rbp, [rsp-3B0h]
0x18003fe88  sub     rsp, 4B0h
0x18003fe8f  mov     rax, cs:__security_cookie
0x18003fe96  xor     rax, rsp
0x18003fe99  mov     [rbp+3E0h+var_40], rax
0x18003fea0  movups  xmm0, xmmword ptr [rcx]
0x18003fea3  xor     esi, esi
0x18003fea5  mov     r12, r8
0x18003fea8  mov     [rsp+4E0h+var_498], rsi
0x18003fead  mov     r13, rdx
0x18003feb0  mov     r14d, esi
0x18003feb3  movdqu  xmmword ptr [rsp+4E0h+InterfaceClassGuid.Data1], xmm0
0x18003feb9  test    rdx, rdx
0x18003febc  jnz     short loc_18003FEDE
0x18003febe  mov     eax, 80070057h
0x18003fec3  mov     ebx, eax
0x18003fec5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003fecc  jb      loc_180040194
0x18003fed2  lea     edx, [rsi+75h]
0x18003fed5  mov     [rsp+4E0h+ulFlags], eax
0x18003fed9  jmp     loc_18004017A
0x18003fede  test    r12, r12
0x18003fee1  jnz     short loc_18003FEFE
0x18003fee3  mov     eax, 80070057h
0x18003fee8  mov     ebx, eax
0x18003feea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003fef1  jb      loc_180040194
0x18003fef7  lea     edx, [r12+76h]
0x18003fefc  jmp     short loc_18003FED5
0x18003fefe  xor     r9d, r9d; ulFlags
0x18003ff01  mov     [rsp+4E0h+Buffer], rsi
0x18003ff06  xor     r8d, r8d; pDeviceID
0x18003ff09  mov     [rsp+4E0h+pulLen], esi
0x18003ff0d  lea     rdx, [rsp+4E0h+InterfaceClassGuid]; InterfaceClassGuid
0x18003ff12  lea     rcx, [rsp+4E0h+pulLen]; pulLen
0x18003ff17  call    cs:__imp_CM_Get_Device_Interface_List_SizeW
0x18003ff1d  test    eax, eax
0x18003ff1f  jz      short loc_18003FF41
0x18003ff21  mov     edx, 0Dh; DefaultErr
0x18003ff26  mov     ecx, eax; CmReturnCode
0x18003ff28  call    cs:__imp_CM_MapCrToWin32Err
0x18003ff2e  mov     ebx, eax
0x18003ff30  test    eax, eax
0x18003ff32  jle     short loc_18003FF3D
0x18003ff34  movzx   ebx, ax
0x18003ff37  or      ebx, 80070000h
0x18003ff3d  test    ebx, ebx
0x18003ff3f  js      short loc_18003FFBD
0x18003ff41  mov     edx, [rsp+4E0h+pulLen]
0x18003ff45  lea     rcx, [rsp+4E0h+Block]
0x18003ff4a  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18003ff4f  mov     rdx, rax
0x18003ff52  lea     rcx, [rsp+4E0h+Buffer]
0x18003ff57  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003ff5c  mov     rcx, [rsp+4E0h+Block]; Block
0x18003ff61  mov     [rsp+4E0h+Block], rsi
0x18003ff66  test    rcx, rcx
0x18003ff69  jz      short loc_18003FF70
0x18003ff6b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ff70  mov     rbx, [rsp+4E0h+Buffer]
0x18003ff75  test    rbx, rbx
0x18003ff78  jz      loc_180040163
0x18003ff7e  mov     r9d, [rsp+4E0h+pulLen]; BufferLen
0x18003ff83  lea     rcx, [rsp+4E0h+InterfaceClassGuid]; InterfaceClassGuid
0x18003ff88  mov     r8, rbx; Buffer
0x18003ff8b  mov     [rsp+4E0h+ulFlags], esi; ulFlags
0x18003ff8f  xor     edx, edx; pDeviceID
0x18003ff91  call    cs:__imp_CM_Get_Device_Interface_ListW
0x18003ff97  mov     edi, eax
0x18003ff99  test    eax, eax
0x18003ff9b  jz      short loc_18003FFD4
0x18003ff9d  test    rbx, rbx
0x18003ffa0  jz      short loc_18003FFAA
0x18003ffa2  mov     rcx, rbx; Block
0x18003ffa5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ffaa  cmp     edi, 1Ah
0x18003ffad  jz      loc_18003FEFE
0x18003ffb3  mov     ebx, 0C00D36D5h
0x18003ffb8  jmp     loc_180040194
0x18003ffbd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ffc4  jb      loc_180040194
0x18003ffca  mov     edx, 77h ; 'w'
0x18003ffcf  jmp     loc_180040176
0x18003ffd4  lea     rdx, [rsp+4E0h+Buffer]
0x18003ffd9  lea     rcx, [rsp+4E0h+var_498]
0x18003ffde  call    ?swap@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAXAEAV12@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::swap(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &)
0x18003ffe3  mov     rcx, [rsp+4E0h+Buffer]; Block
0x18003ffe8  mov     r15d, [rsp+4E0h+pulLen]
0x18003ffed  test    rcx, rcx
0x18003fff0  jz      short loc_18003FFF7
0x18003fff2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003fff7  mov     r14, [rsp+4E0h+var_498]
0x18003fffc  cmp     r15d, 1
0x180040000  jbe     short loc_18003FFB3
0x180040002  movups  xmm0, cs:SensorGroupFMTGUID
0x180040009  mov     [rsp+4E0h+PropertyKey.pid], 4
0x180040011  mov     rdi, r14
0x180040014  xor     ebx, ebx
0x180040016  movdqu  xmmword ptr [rsp+4E0h+PropertyKey.fmtid.Data1], xmm0
0x18004001c  cmp     [rdi], bx
0x18004001f  jz      short loc_18003FFB3
0x180040021  cmp     esi, r15d
0x180040024  jnb     short loc_18003FFB3
0x180040026  xor     edx, edx; Val
0x180040028  lea     rcx, [rbp+3E0h+pszDeviceInterface]; void *
0x18004002c  mov     r8d, 208h; Size
0x180040032  call    memset_0
0x180040037  xor     edx, edx; Val
0x180040039  lea     rcx, [rbp+3E0h+PropertyBuffer]; void *
0x180040040  mov     r8d, 208h; Size
0x180040046  call    memset_0
0x18004004b  xor     r9d, r9d; unsigned int *
0x18004004e  lea     rdx, [rbp+3E0h+pszDeviceInterface]; unsigned __int16 *
0x180040052  mov     r8d, 104h; unsigned int
0x180040058  mov     rcx, rdi; pszDeviceInterface
0x18004005b  call    ?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z; FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)
0x180040060  mov     ebx, eax
0x180040062  test    eax, eax
0x180040064  js      loc_180040150
0x18004006a  lea     rax, [rsp+4E0h+pulLen]
0x18004006f  mov     r9d, 208h; unsigned int
0x180040075  lea     r8, [rbp+3E0h+PropertyBuffer]; PropertyBuffer
0x18004007c  mov     qword ptr [rsp+4E0h+ulFlags], rax; unsigned int *
0x180040081  lea     rdx, [rsp+4E0h+PropertyKey]; PropertyKey
0x180040086  lea     rcx, [rbp+3E0h+pszDeviceInterface]; pszDeviceInterface
0x18004008a  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x18004008f  xor     ebx, ebx
0x180040091  test    eax, eax
0x180040093  js      short loc_1800400A9
0x180040095  lea     rdx, [rbp+3E0h+PropertyBuffer]
0x18004009c  mov     rcx, r13
0x18004009f  call    cs:__imp__o__wcsicmp
0x1800400a5  test    eax, eax
0x1800400a7  jz      short loc_1800400CD
0x1800400a9  cmp     [rdi], bx
0x1800400ac  jz      short loc_1800400C2
0x1800400ae  add     rdi, 2
0x1800400b2  inc     esi
0x1800400b4  cmp     [rdi], bx
0x1800400b7  jnz     short loc_1800400AE
0x1800400b9  cmp     esi, r15d
0x1800400bc  jnb     loc_18004001C
0x1800400c2  inc     esi
0x1800400c4  add     rdi, 2
0x1800400c8  jmp     loc_18004001C
0x1800400cd  mov     r10d, 104h
0x1800400d3  mov     [rsp+4E0h+Block], rbx
0x1800400d8  mov     edx, r10d; unsigned __int64
0x1800400db  lea     r8, [rsp+4E0h+Block]; unsigned __int64 *
0x1800400e0  lea     rcx, [rbp+3E0h+pszDeviceInterface]; unsigned __int16 *
0x1800400e4  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800400e9  mov     ebx, eax
0x1800400eb  test    eax, eax
0x1800400ed  jns     short loc_180040106
0x1800400ef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800400f6  jb      loc_180040194
0x1800400fc  mov     edx, 7Ah ; 'z'
0x180040101  jmp     loc_18003FED5
0x180040106  mov     rax, [rsp+4E0h+Block]
0x18004010b  inc     rax
0x18004010e  cmp     rax, r10
0x180040111  jbe     short loc_180040128
0x180040113  mov     ebx, 0C00D7170h
0x180040118  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004011f  jb      short loc_180040194
0x180040121  mov     edx, 7Bh ; '{'
0x180040126  jmp     short loc_180040176
0x180040128  lea     r8, [rbp+3E0h+pszDeviceInterface]; unsigned __int16 *
0x18004012c  mov     rdx, r10; unsigned __int64
0x18004012f  mov     rcx, r12; unsigned __int16 *
0x180040132  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180040137  mov     ebx, eax
0x180040139  test    eax, eax
0x18004013b  jns     short loc_180040194
0x18004013d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180040144  jb      short loc_180040194
0x180040146  mov     edx, 7Ch ; '|'
0x18004014b  jmp     loc_18003FED5
0x180040150  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180040157  jb      short loc_180040194
0x180040159  mov     edx, 79h ; 'y'
0x18004015e  jmp     loc_18003FED5
0x180040163  mov     ebx, 8007000Eh
0x180040168  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004016f  jb      short loc_180040194
0x180040171  mov     edx, 78h ; 'x'
0x180040176  mov     [rsp+4E0h+ulFlags], ebx
0x18004017a  mov     rcx, cs:WPP_GLOBAL_Control
0x180040181  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x180040188  xor     r9d, r9d
0x18004018b  mov     rcx, [rcx+10h]
0x18004018f  call    WPP_SF_qD
0x180040194  test    r14, r14
0x180040197  jz      short loc_1800401A1
0x180040199  mov     rcx, r14; Block
0x18004019c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800401a1  mov     eax, ebx
0x1800401a3  mov     rcx, [rbp+3E0h+var_40]
0x1800401aa  xor     rcx, rsp; StackCookie
0x1800401ad  call    __security_check_cookie
0x1800401b2  mov     rbx, [rsp+4E0h+arg_18]
0x1800401ba  add     rsp, 4B0h
0x1800401c1  pop     r15
0x1800401c3  pop     r14
0x1800401c5  pop     r13
0x1800401c7  pop     r12
0x1800401c9  pop     rdi
0x1800401ca  pop     rsi
0x1800401cb  pop     rbp
0x1800401cc  retn
```
