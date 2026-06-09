# FSFindInterfacesWithMatchingInstanceId(ushort const *,_GUID const &,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)

- ea: `0x18002796c`
- end: `0x180027b09`
- name: `?FSFindInterfacesWithMatchingInstanceId@@YAJPEBGAEBU_GUID@@AEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z`
- size: `413`
- prototype: `__int64 __fastcall(LPCWCH lpString2)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002aa0c`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x180009608`
- `0x18000a270`
- `0x18001794c`
- `0x1800179ac`
- `0x180027708`
- `0x18002796c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180027a73`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180027a73`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180027a43`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180027a43`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180027a2e`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180027a2e`

## pseudocode

```c
__int64 __fastcall FSFindInterfacesWithMatchingInstanceId(LPCWCH lpString2, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  signed int v6; // edi
  _QWORD *i; // rbx
  const WCHAR *v8; // rcx
  CONFIGRET Device_Interface_PropertyW; // eax
  signed int v10; // eax
  __int64 v11; // rdx
  ULONG PropertyBufferSize; // [rsp+30h] [rbp-D0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD v15[3]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR PropertyBuffer[200]; // [rsp+50h] [rbp-B0h] BYREF

  utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(v15);
  if ( lpString2 )
  {
    v6 = FSEnumDeviceInterfaces(&GUID_e5323777_f976_4f5b_9b55_b94699c46e44, v5, v15);
    if ( v6 >= 0 )
    {
      for ( i = (_QWORD *)v15[0]; i != v15; i = (_QWORD *)*i )
      {
        memset_0(PropertyBuffer, 0, sizeof(PropertyBuffer));
        v8 = (const WCHAR *)i[2];
        PropertyType = 0;
        PropertyBufferSize = 400;
        Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                       v8,
                                       &DEVPKEY_Device_InstanceId,
                                       &PropertyType,
                                       (PBYTE)PropertyBuffer,
                                       &PropertyBufferSize,
                                       0);
        if ( Device_Interface_PropertyW )
        {
          v10 = CM_MapCrToWin32Err(Device_Interface_PropertyW, 0xDu);
          v6 = v10;
          if ( v10 > 0 )
            v6 = (unsigned __int16)v10 | 0x80070000;
          if ( v6 < 0 )
          {
            if ( !g_wppLevels )
              break;
            v11 = 49;
            goto LABEL_18;
          }
        }
        else
        {
          v6 = 0;
        }
        if ( CompareStringOrdinal(PropertyBuffer, -1, lpString2, -1, 1) == 2
          && !(unsigned __int8)utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::push_back(
                                 a3,
                                 i + 2) )
        {
          v6 = -2147024882;
          if ( !g_wppLevels )
            break;
          v11 = 50;
LABEL_18:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v6);
          break;
        }
      }
    }
  }
  else
  {
    v6 = -2147024809;
  }
  utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear(v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002796c  mov     [rsp-8+arg_8], rbx
0x180027971  push    rbp
0x180027972  push    rsi
0x180027973  push    rdi
0x180027974  push    r14
0x180027976  push    r15
0x180027978  lea     rbp, [rsp-0F0h]
0x180027980  sub     rsp, 1F0h
0x180027987  mov     rax, cs:__security_cookie
0x18002798e  xor     rax, rsp
0x180027991  mov     [rbp+110h+var_30], rax
0x180027998  mov     rsi, rcx
0x18002799b  mov     r15, r8
0x18002799e  lea     rcx, [rsp+210h+var_1D8]
0x1800279a3  call    ??0?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA@XZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>(void)
0x1800279a8  test    rsi, rsi
0x1800279ab  jnz     short loc_1800279B7
0x1800279ad  mov     edi, 80070057h
0x1800279b2  jmp     loc_180027AD7
0x1800279b7  lea     r8, [rsp+210h+var_1D8]
0x1800279bc  lea     rcx, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44
0x1800279c3  call    ?FSEnumDeviceInterfaces@@YAJAEBU_GUID@@_NAEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; FSEnumDeviceInterfaces(_GUID const &,bool,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x1800279c8  mov     edi, eax
0x1800279ca  test    eax, eax
0x1800279cc  js      loc_180027AD7
0x1800279d2  mov     rbx, [rsp+210h+var_1D8]
0x1800279d7  lea     rax, [rsp+210h+var_1D8]
0x1800279dc  cmp     rbx, rax
0x1800279df  jz      loc_180027AD7
0x1800279e5  xor     edx, edx; Val
0x1800279e7  lea     rcx, [rsp+210h+PropertyBuffer]; void *
0x1800279ec  mov     r8d, 190h; Size
0x1800279f2  call    memset_0
0x1800279f7  mov     rcx, [rbx+10h]; pszDeviceInterface
0x1800279fb  lea     rax, [rsp+210h+var_1E0]
0x180027a00  mov     [rsp+210h+ulFlags], 0; ulFlags
0x180027a08  lea     r9, [rsp+210h+PropertyBuffer]; PropertyBuffer
0x180027a0d  lea     r8, [rsp+210h+PropertyType]; PropertyType
0x180027a12  mov     [rsp+210h+PropertyBufferSize], rax; PropertyBufferSize
0x180027a17  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x180027a1e  mov     [rsp+210h+PropertyType], 0
0x180027a26  mov     [rsp+210h+var_1E0], 190h
0x180027a2e  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x180027a34  test    eax, eax
0x180027a36  jnz     short loc_180027A3C
0x180027a38  xor     edi, edi
0x180027a3a  jmp     short loc_180027A5C
0x180027a3c  mov     edx, 0Dh; DefaultErr
0x180027a41  mov     ecx, eax; CmReturnCode
0x180027a43  call    cs:__imp_CM_MapCrToWin32Err
0x180027a49  mov     edi, eax
0x180027a4b  test    eax, eax
0x180027a4d  jle     short loc_180027A58
0x180027a4f  movzx   edi, ax
0x180027a52  or      edi, 80070000h
0x180027a58  test    edi, edi
0x180027a5a  js      short loc_180027AAB
0x180027a5c  or      r9d, 0FFFFFFFFh; cchCount2
0x180027a60  mov     dword ptr [rsp+210h+PropertyBufferSize], 1; bIgnoreCase
0x180027a68  or      edx, r9d; cchCount1
0x180027a6b  lea     rcx, [rsp+210h+PropertyBuffer]; lpString1
0x180027a70  mov     r8, rsi; lpString2
0x180027a73  call    cs:__imp_CompareStringOrdinal
0x180027a79  cmp     eax, 2
0x180027a7c  jnz     short loc_180027A8E
0x180027a7e  lea     rdx, [rbx+10h]
0x180027a82  mov     rcx, r15
0x180027a85  call    ?push_back@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::push_back(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180027a8a  test    al, al
0x180027a8c  jz      short loc_180027A96
0x180027a8e  mov     rbx, [rbx]
0x180027a91  jmp     loc_1800279D7
0x180027a96  mov     edi, 8007000Eh
0x180027a9b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027aa2  jb      short loc_180027AD7
0x180027aa4  mov     edx, 32h ; '2'
0x180027aa9  jmp     short loc_180027AB9
0x180027aab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027ab2  jb      short loc_180027AD7
0x180027ab4  mov     edx, 31h ; '1'
0x180027ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ac0  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x180027ac7  xor     r9d, r9d
0x180027aca  mov     dword ptr [rsp+210h+PropertyBufferSize], edi
0x180027ace  mov     rcx, [rcx+10h]
0x180027ad2  call    WPP_SF_qD
0x180027ad7  lea     rcx, [rsp+210h+var_1D8]
0x180027adc  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::clear(void)
0x180027ae1  mov     eax, edi
0x180027ae3  mov     rcx, [rbp+110h+var_30]
0x180027aea  xor     rcx, rsp; StackCookie
0x180027aed  call    __security_check_cookie
0x180027af2  mov     rbx, [rsp+210h+arg_8]
0x180027afa  add     rsp, 1F0h
0x180027b01  pop     r15
0x180027b03  pop     r14
0x180027b05  pop     rdi
0x180027b06  pop     rsi
0x180027b07  pop     rbp
0x180027b08  retn
```
