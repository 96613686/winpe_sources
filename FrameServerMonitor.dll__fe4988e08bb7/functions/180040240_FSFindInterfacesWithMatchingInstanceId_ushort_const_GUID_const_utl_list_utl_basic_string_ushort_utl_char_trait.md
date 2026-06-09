# FSFindInterfacesWithMatchingInstanceId(ushort const *,_GUID const &,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)

- ea: `0x180040240`
- end: `0x1800403dd`
- name: `?FSFindInterfacesWithMatchingInstanceId@@YAJPEBGAEBU_GUID@@AEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z`
- size: `413`
- prototype: `__int64 __fastcall(LPCWCH lpString2, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042a74`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x1800060f8`
- `0x180006a98`
- `0x180006d38`
- `0x18000d154`
- `0x180017b70`
- `0x180040004`
- `0x180040240`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040347`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040347`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180040317`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180040317`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180040302`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180040302`

## pseudocode

```c
__int64 __fastcall FSFindInterfacesWithMatchingInstanceId(LPCWCH lpString2, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  signed int v6; // edi
  void **i; // rbx
  const WCHAR *v8; // rcx
  CONFIGRET Device_Interface_PropertyW; // eax
  signed int v10; // eax
  __int64 v11; // rdx
  ULONG PropertyBufferSize; // [rsp+30h] [rbp-D0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+34h] [rbp-CCh] BYREF
  void **v15[3]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR PropertyBuffer[200]; // [rsp+50h] [rbp-B0h] BYREF

  utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(v15);
  if ( lpString2 )
  {
    v6 = FSEnumDeviceInterfaces(&GUID_e5323777_f976_4f5b_9b55_b94699c46e44, v5, v15);
    if ( v6 >= 0 )
    {
      for ( i = v15[0]; i != (void **)v15; i = (void **)*i )
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
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
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
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
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
0x180040240  mov     [rsp-8+arg_8], rbx
0x180040245  push    rbp
0x180040246  push    rsi
0x180040247  push    rdi
0x180040248  push    r14
0x18004024a  push    r15
0x18004024c  lea     rbp, [rsp-0F0h]
0x180040254  sub     rsp, 1F0h
0x18004025b  mov     rax, cs:__security_cookie
0x180040262  xor     rax, rsp
0x180040265  mov     [rbp+110h+var_30], rax
0x18004026c  mov     rsi, rcx
0x18004026f  mov     r15, r8
0x180040272  lea     rcx, [rsp+210h+var_1D8]
0x180040277  call    ??0?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA@XZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>(void)
0x18004027c  test    rsi, rsi
0x18004027f  jnz     short loc_18004028B
0x180040281  mov     edi, 80070057h
0x180040286  jmp     loc_1800403AB
0x18004028b  lea     r8, [rsp+210h+var_1D8]
0x180040290  lea     rcx, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44
0x180040297  call    ?FSEnumDeviceInterfaces@@YAJAEBU_GUID@@_NAEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; FSEnumDeviceInterfaces(_GUID const &,bool,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x18004029c  mov     edi, eax
0x18004029e  test    eax, eax
0x1800402a0  js      loc_1800403AB
0x1800402a6  mov     rbx, [rsp+210h+var_1D8]
0x1800402ab  lea     rax, [rsp+210h+var_1D8]
0x1800402b0  cmp     rbx, rax
0x1800402b3  jz      loc_1800403AB
0x1800402b9  xor     edx, edx; Val
0x1800402bb  lea     rcx, [rsp+210h+PropertyBuffer]; void *
0x1800402c0  mov     r8d, 190h; Size
0x1800402c6  call    memset_0
0x1800402cb  mov     rcx, [rbx+10h]; pszDeviceInterface
0x1800402cf  lea     rax, [rsp+210h+var_1E0]
0x1800402d4  mov     [rsp+210h+ulFlags], 0; ulFlags
0x1800402dc  lea     r9, [rsp+210h+PropertyBuffer]; PropertyBuffer
0x1800402e1  lea     r8, [rsp+210h+PropertyType]; PropertyType
0x1800402e6  mov     [rsp+210h+PropertyBufferSize], rax; PropertyBufferSize
0x1800402eb  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x1800402f2  mov     [rsp+210h+PropertyType], 0
0x1800402fa  mov     [rsp+210h+var_1E0], 190h
0x180040302  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x180040308  test    eax, eax
0x18004030a  jnz     short loc_180040310
0x18004030c  xor     edi, edi
0x18004030e  jmp     short loc_180040330
0x180040310  mov     edx, 0Dh; DefaultErr
0x180040315  mov     ecx, eax; CmReturnCode
0x180040317  call    cs:__imp_CM_MapCrToWin32Err
0x18004031d  mov     edi, eax
0x18004031f  test    eax, eax
0x180040321  jle     short loc_18004032C
0x180040323  movzx   edi, ax
0x180040326  or      edi, 80070000h
0x18004032c  test    edi, edi
0x18004032e  js      short loc_18004037F
0x180040330  or      r9d, 0FFFFFFFFh; cchCount2
0x180040334  mov     dword ptr [rsp+210h+PropertyBufferSize], 1; bIgnoreCase
0x18004033c  or      edx, r9d; cchCount1
0x18004033f  lea     rcx, [rsp+210h+PropertyBuffer]; lpString1
0x180040344  mov     r8, rsi; lpString2
0x180040347  call    cs:__imp_CompareStringOrdinal
0x18004034d  cmp     eax, 2
0x180040350  jnz     short loc_180040362
0x180040352  lea     rdx, [rbx+10h]
0x180040356  mov     rcx, r15
0x180040359  call    ?push_back@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::push_back(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18004035e  test    al, al
0x180040360  jz      short loc_18004036A
0x180040362  mov     rbx, [rbx]
0x180040365  jmp     loc_1800402AB
0x18004036a  mov     edi, 8007000Eh
0x18004036f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180040374  cmp     al, 1
0x180040376  jb      short loc_1800403AB
0x180040378  mov     edx, 32h ; '2'
0x18004037d  jmp     short loc_18004038D
0x18004037f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180040384  cmp     al, 1
0x180040386  jb      short loc_1800403AB
0x180040388  mov     edx, 31h ; '1'
0x18004038d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040394  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18004039b  xor     r9d, r9d
0x18004039e  mov     dword ptr [rsp+210h+PropertyBufferSize], edi
0x1800403a2  mov     rcx, [rcx+10h]
0x1800403a6  call    WPP_SF_qD
0x1800403ab  lea     rcx, [rsp+210h+var_1D8]
0x1800403b0  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::clear(void)
0x1800403b5  mov     eax, edi
0x1800403b7  mov     rcx, [rbp+110h+var_30]
0x1800403be  xor     rcx, rsp; StackCookie
0x1800403c1  call    __security_check_cookie
0x1800403c6  mov     rbx, [rsp+210h+arg_8]
0x1800403ce  add     rsp, 1F0h
0x1800403d5  pop     r15
0x1800403d7  pop     r14
0x1800403d9  pop     rdi
0x1800403da  pop     rsi
0x1800403db  pop     rbp
0x1800403dc  retn
```
