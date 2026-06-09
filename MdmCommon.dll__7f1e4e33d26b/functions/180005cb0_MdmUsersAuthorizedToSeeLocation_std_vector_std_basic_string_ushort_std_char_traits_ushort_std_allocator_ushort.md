# MdmUsersAuthorizedToSeeLocation(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *)

- ea: `0x180005cb0`
- end: `0x180005e3d`
- name: `?MdmUsersAuthorizedToSeeLocation@@YAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `397`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005e50`

## callees

- `0x180001520`
- `0x18000269c`
- `0x180002bb8`
- `0x180002e50`
- `0x180005cb0`
- `0x1800064f0`
- `0x180006548`
- `0x1800142c8`

## string_xrefs

- `0x180005d53`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`

## pseudocode

```c
__int64 __fastcall MdmUsersAuthorizedToSeeLocation(__int64 *a1, __int64 a2, __int64 a3)
{
  int v4; // edx
  __int64 v5; // rcx
  int v6; // esi
  __int64 v7; // r8
  __int64 i; // rdi
  __int64 v9; // r14
  __int64 v10; // rdx
  __int64 j; // rdi
  __int64 v12; // r14
  __int64 v13; // rdx
  int v15; // [rsp+30h] [rbp-19h] BYREF
  __int128 v16; // [rsp+38h] [rbp-11h] BYREF
  __int64 v17; // [rsp+48h] [rbp-1h]
  __int128 v18; // [rsp+50h] [rbp+7h] BYREF
  __int64 v19; // [rsp+60h] [rbp+17h]
  _BYTE v20[16]; // [rsp+68h] [rbp+1Fh] BYREF
  int *v21; // [rsp+78h] [rbp+2Fh]
  __int64 v22; // [rsp+80h] [rbp+37h]

  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_USERS_AUTHORIZED_TO_SEE_LOCATION, a3, 1, v20);
  v18 = 0;
  v19 = 0;
  v16 = 0;
  v17 = 0;
  v6 = MdmAccountHelper::EnumerateAllUsers((__int64 *)&v18, (__int64 *)&v16, 0);
  if ( v6 >= 0 )
  {
    v9 = *((_QWORD *)&v18 + 1);
    for ( i = v18; i != v9; i += 32 )
    {
      v10 = a1[1];
      if ( v10 == a1[2] )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, v10, i);
      }
      else
      {
        std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
          v5,
          v10,
          i);
        a1[1] += 32;
      }
    }
    v12 = *((_QWORD *)&v16 + 1);
    for ( j = v16; j != v12; j += 32 )
    {
      v13 = a1[1];
      if ( v13 == a1[2] )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, v13, j);
      }
      else
      {
        std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
          v5,
          v13,
          j);
        a1[1] += 32;
      }
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v5,
      v4,
      v6,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      48,
      "CHR(MdmAccountHelper::EnumerateAllUsers(&vAdmins, &vDeviceOwners, nullptr))");
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    v15 = v6;
    v21 = &v15;
    v22 = 4;
    McGenEventWrite_EventWriteTransfer(v5, MDMCOMMON_USERS_AUTHORIZED_TO_SEE_LOCATION_RESULT, v7, 2, v20);
  }
  std::vector<std::wstring>::~vector<std::wstring>((__int64)&v16);
  std::vector<std::wstring>::~vector<std::wstring>((__int64)&v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005cb0  mov     [rsp-8+arg_8], rbx
0x180005cb5  mov     [rsp-8+arg_10], rsi
0x180005cba  push    rbp
0x180005cbb  push    rdi
0x180005cbc  push    r14
0x180005cbe  lea     rbp, [rsp-47h]
0x180005cc3  sub     rsp, 90h
0x180005cca  mov     rax, cs:__security_cookie
0x180005cd1  xor     rax, rsp
0x180005cd4  mov     [rbp+57h+var_18], rax
0x180005cd8  mov     rbx, rcx
0x180005cdb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180005ce2  jz      short loc_180005CFF
0x180005ce4  lea     rax, [rbp+57h+var_38]
0x180005ce8  mov     [rsp+0A0h+var_80], rax
0x180005ced  mov     r9d, 1
0x180005cf3  lea     rdx, MDMCOMMON_USERS_AUTHORIZED_TO_SEE_LOCATION
0x180005cfa  call    McGenEventWrite_EventWriteTransfer
0x180005cff  xorps   xmm0, xmm0
0x180005d02  movdqu  [rbp+57h+var_50], xmm0
0x180005d07  mov     [rbp+57h+var_40], 0
0x180005d0f  movdqu  [rbp+57h+var_68], xmm0
0x180005d14  mov     [rbp+57h+var_58], 0
0x180005d1c  xor     r8d, r8d
0x180005d1f  lea     rdx, [rbp+57h+var_68]
0x180005d23  lea     rcx, [rbp+57h+var_50]
0x180005d27  call    ?EnumerateAllUsers@MdmAccountHelper@@SAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00@Z; MdmAccountHelper::EnumerateAllUsers(std::vector<std::wstring> *,std::vector<std::wstring> *,std::vector<std::wstring> *)
0x180005d2c  mov     esi, eax
0x180005d2e  test    eax, eax
0x180005d30  jns     short loc_180005D64
0x180005d32  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180005d39  jz      loc_180005DCC
0x180005d3f  lea     rax, aChrMdmaccounth_1; "CHR(MdmAccountHelper::EnumerateAllUsers"...
0x180005d46  mov     [rsp+0A0h+var_78], rax
0x180005d4b  mov     dword ptr [rsp+0A0h+var_80], 330h
0x180005d53  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180005d5a  mov     r8d, esi
0x180005d5d  call    McTemplateU0dsqs_EventWriteTransfer
0x180005d62  jmp     short loc_180005DCC
0x180005d64  mov     rdi, qword ptr [rbp+57h+var_50]
0x180005d68  mov     r14, qword ptr [rbp+57h+var_50+8]
0x180005d6c  jmp     short loc_180005D93
0x180005d6e  mov     rdx, [rbx+8]
0x180005d72  mov     r8, rdi
0x180005d75  cmp     rdx, [rbx+10h]
0x180005d79  jz      short loc_180005D87
0x180005d7b  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@SAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(std::allocator<std::wstring> &,std::wstring * const,std::wstring const &)
0x180005d80  add     qword ptr [rbx+8], 20h ; ' '
0x180005d85  jmp     short loc_180005D8F
0x180005d87  mov     rcx, rbx
0x180005d8a  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180005d8f  add     rdi, 20h ; ' '
0x180005d93  cmp     rdi, r14
0x180005d96  jnz     short loc_180005D6E
0x180005d98  mov     rdi, qword ptr [rbp+57h+var_68]
0x180005d9c  mov     r14, qword ptr [rbp+57h+var_68+8]
0x180005da0  jmp     short loc_180005DC7
0x180005da2  mov     rdx, [rbx+8]
0x180005da6  mov     r8, rdi
0x180005da9  cmp     rdx, [rbx+10h]
0x180005dad  jz      short loc_180005DBB
0x180005daf  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@SAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(std::allocator<std::wstring> &,std::wstring * const,std::wstring const &)
0x180005db4  add     qword ptr [rbx+8], 20h ; ' '
0x180005db9  jmp     short loc_180005DC3
0x180005dbb  mov     rcx, rbx
0x180005dbe  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180005dc3  add     rdi, 20h ; ' '
0x180005dc7  cmp     rdi, r14
0x180005dca  jnz     short loc_180005DA2
0x180005dcc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180005dd3  jz      short loc_180005E04
0x180005dd5  mov     [rbp+57h+var_70], esi
0x180005dd8  lea     rax, [rbp+57h+var_70]
0x180005ddc  mov     [rbp+57h+var_28], rax
0x180005de0  mov     [rbp+57h+var_20], 4
0x180005de8  lea     rax, [rbp+57h+var_38]
0x180005dec  mov     [rsp+0A0h+var_80], rax
0x180005df1  mov     r9d, 2
0x180005df7  lea     rdx, MDMCOMMON_USERS_AUTHORIZED_TO_SEE_LOCATION_RESULT
0x180005dfe  call    McGenEventWrite_EventWriteTransfer
0x180005e03  nop
0x180005e04  lea     rcx, [rbp+57h+var_68]
0x180005e08  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180005e0d  nop
0x180005e0e  lea     rcx, [rbp+57h+var_50]
0x180005e12  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180005e17  mov     eax, esi
0x180005e19  mov     rcx, [rbp+57h+var_18]
0x180005e1d  xor     rcx, rsp; StackCookie
0x180005e20  call    __security_check_cookie
0x180005e25  lea     r11, [rsp+0A0h+var_10]
0x180005e2d  mov     rbx, [r11+28h]
0x180005e31  mov     rsi, [r11+30h]
0x180005e35  mov     rsp, r11
0x180005e38  pop     r14
0x180005e3a  pop     rdi
0x180005e3b  pop     rbp
0x180005e3c  retn
```
