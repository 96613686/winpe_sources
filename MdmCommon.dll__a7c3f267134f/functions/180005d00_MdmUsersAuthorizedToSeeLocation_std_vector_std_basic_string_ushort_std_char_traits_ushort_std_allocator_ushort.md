# MdmUsersAuthorizedToSeeLocation(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *)

- ea: `0x180005d00`
- end: `0x180005e8e`
- name: `?MdmUsersAuthorizedToSeeLocation@@YAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005ea0`

## callees

- `0x180001520`
- `0x18000269c`
- `0x180002bb8`
- `0x180002e54`
- `0x180005d00`
- `0x180006560`
- `0x1800065c0`
- `0x1800146d4`

## string_xrefs

- `0x180005da3`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MdmUsersAuthorizedToSeeLocation(__int64 a1, __int64 a2, __int64 a3)
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
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+68h] [rbp+1Fh] BYREF
  int *v21; // [rsp+78h] [rbp+2Fh]
  __int64 v22; // [rsp+80h] [rbp+37h]

  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      a1,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_USERS_AUTHORIZED_TO_SEE_LOCATION,
      a3,
      1u,
      &v20);
  v18 = 0;
  v19 = 0;
  v16 = 0;
  v17 = 0;
  v6 = MdmAccountHelper::EnumerateAllUsers((__int64)&v18, (__int64)&v16, 0);
  if ( v6 >= 0 )
  {
    v9 = *((_QWORD *)&v18 + 1);
    for ( i = v18; i != v9; i += 32 )
    {
      v10 = *(_QWORD *)(a1 + 8);
      if ( v10 == *(_QWORD *)(a1 + 16) )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, v10, i);
      }
      else
      {
        std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
          v5,
          v10,
          i);
        *(_QWORD *)(a1 + 8) += 32LL;
      }
    }
    v12 = *((_QWORD *)&v16 + 1);
    for ( j = v16; j != v12; j += 32 )
    {
      v13 = *(_QWORD *)(a1 + 8);
      if ( v13 == *(_QWORD *)(a1 + 16) )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, v13, j);
      }
      else
      {
        std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
          v5,
          v13,
          j);
        *(_QWORD *)(a1 + 8) += 32LL;
      }
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v5,
      v4,
      v6,
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      48,
      "CHR(MdmAccountHelper::EnumerateAllUsers(&vAdmins, &vDeviceOwners, nullptr))");
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    v15 = v6;
    v21 = &v15;
    v22 = 4;
    McGenEventWrite_EventWriteTransfer(
      v5,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_USERS_AUTHORIZED_TO_SEE_LOCATION_RESULT,
      v7,
      2u,
      &v20);
  }
  std::vector<std::wstring>::~vector<std::wstring>(&v16);
  std::vector<std::wstring>::~vector<std::wstring>(&v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005d00  mov     [rsp-8+arg_8], rbx
0x180005d05  mov     [rsp-8+arg_10], rsi
0x180005d0a  push    rbp
0x180005d0b  push    rdi
0x180005d0c  push    r14
0x180005d0e  lea     rbp, [rsp-47h]
0x180005d13  sub     rsp, 90h
0x180005d1a  mov     rax, cs:__security_cookie
0x180005d21  xor     rax, rsp
0x180005d24  mov     [rbp+57h+var_18], rax
0x180005d28  mov     rbx, rcx
0x180005d2b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180005d32  jz      short loc_180005D4F
0x180005d34  lea     rax, [rbp+57h+var_38]
0x180005d38  mov     [rsp+0A0h+var_80], rax
0x180005d3d  mov     r9d, 1
0x180005d43  lea     rdx, MDMCOMMON_USERS_AUTHORIZED_TO_SEE_LOCATION
0x180005d4a  call    McGenEventWrite_EventWriteTransfer
0x180005d4f  xorps   xmm0, xmm0
0x180005d52  movdqu  [rbp+57h+var_50], xmm0
0x180005d57  mov     [rbp+57h+var_40], 0
0x180005d5f  movdqu  [rbp+57h+var_68], xmm0
0x180005d64  mov     [rbp+57h+var_58], 0
0x180005d6c  xor     r8d, r8d
0x180005d6f  lea     rdx, [rbp+57h+var_68]
0x180005d73  lea     rcx, [rbp+57h+var_50]
0x180005d77  call    ?EnumerateAllUsers@MdmAccountHelper@@SAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00@Z; MdmAccountHelper::EnumerateAllUsers(std::vector<std::wstring> *,std::vector<std::wstring> *,std::vector<std::wstring> *)
0x180005d7c  mov     esi, eax
0x180005d7e  test    eax, eax
0x180005d80  jns     short loc_180005DB4
0x180005d82  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180005d89  jz      loc_180005E1C
0x180005d8f  lea     rax, aChrMdmaccounth_1; "CHR(MdmAccountHelper::EnumerateAllUsers"...
0x180005d96  mov     [rsp+0A0h+var_78], rax
0x180005d9b  mov     dword ptr [rsp+0A0h+var_80], 330h
0x180005da3  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180005daa  mov     r8d, esi
0x180005dad  call    McTemplateU0dsqs_EventWriteTransfer
0x180005db2  jmp     short loc_180005E1C
0x180005db4  mov     rdi, qword ptr [rbp+57h+var_50]
0x180005db8  mov     r14, qword ptr [rbp+57h+var_50+8]
0x180005dbc  jmp     short loc_180005DE3
0x180005dbe  mov     rdx, [rbx+8]
0x180005dc2  mov     r8, rdi
0x180005dc5  cmp     rdx, [rbx+10h]
0x180005dc9  jz      short loc_180005DD7
0x180005dcb  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@SAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(std::allocator<std::wstring> &,std::wstring * const,std::wstring const &)
0x180005dd0  add     qword ptr [rbx+8], 20h ; ' '
0x180005dd5  jmp     short loc_180005DDF
0x180005dd7  mov     rcx, rbx
0x180005dda  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180005ddf  add     rdi, 20h ; ' '
0x180005de3  cmp     rdi, r14
0x180005de6  jnz     short loc_180005DBE
0x180005de8  mov     rdi, qword ptr [rbp+57h+var_68]
0x180005dec  mov     r14, qword ptr [rbp+57h+var_68+8]
0x180005df0  jmp     short loc_180005E17
0x180005df2  mov     rdx, [rbx+8]
0x180005df6  mov     r8, rdi
0x180005df9  cmp     rdx, [rbx+10h]
0x180005dfd  jz      short loc_180005E0B
0x180005dff  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@SAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(std::allocator<std::wstring> &,std::wstring * const,std::wstring const &)
0x180005e04  add     qword ptr [rbx+8], 20h ; ' '
0x180005e09  jmp     short loc_180005E13
0x180005e0b  mov     rcx, rbx
0x180005e0e  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180005e13  add     rdi, 20h ; ' '
0x180005e17  cmp     rdi, r14
0x180005e1a  jnz     short loc_180005DF2
0x180005e1c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180005e23  jz      short loc_180005E54
0x180005e25  mov     [rbp+57h+var_70], esi
0x180005e28  lea     rax, [rbp+57h+var_70]
0x180005e2c  mov     [rbp+57h+var_28], rax
0x180005e30  mov     [rbp+57h+var_20], 4
0x180005e38  lea     rax, [rbp+57h+var_38]
0x180005e3c  mov     [rsp+0A0h+var_80], rax
0x180005e41  mov     r9d, 2
0x180005e47  lea     rdx, MDMCOMMON_USERS_AUTHORIZED_TO_SEE_LOCATION_RESULT
0x180005e4e  call    McGenEventWrite_EventWriteTransfer
0x180005e53  nop
0x180005e54  lea     rcx, [rbp+57h+var_68]
0x180005e58  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180005e5d  nop
0x180005e5e  lea     rcx, [rbp+57h+var_50]
0x180005e62  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180005e67  mov     eax, esi
0x180005e69  mov     rcx, [rbp+57h+var_18]
0x180005e6d  xor     rcx, rsp; StackCookie
0x180005e70  call    __security_check_cookie
0x180005e75  lea     r11, [rsp+0A0h+var_10]
0x180005e7d  mov     rbx, [r11+28h]
0x180005e81  mov     rsi, [r11+30h]
0x180005e85  mov     rsp, r11
0x180005e88  pop     r14
0x180005e8a  pop     rdi
0x180005e8b  pop     rbp
0x180005e8c  retn
```
