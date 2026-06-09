# MdmHttpWrapper::RegistrationTriggerToString(MdmRegistrationTrigger,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180011cf4`
- end: `0x180012031`
- name: `?RegistrationTriggerToString@MdmHttpWrapper@@CAJW4MdmRegistrationTrigger@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `829`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c38c`
- `0x18000e97c`

## callees

- `0x1800028e4`
- `0x180006548`
- `0x180011cf4`
- `0x18001d51c`

## string_xrefs

- `0x180011edd`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::RegistrationTriggerToString(int a1, __int64 a2)
{
  unsigned int v3; // edi
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  __int64 v7; // rax
  char *v8; // rbx
  const wchar_t *v9; // r9
  char *v10; // rbx
  unsigned __int64 v11; // rdx
  char *v12; // rbx
  char *v13; // rbx
  char *v14; // rbx
  int v15; // ecx
  char *v16; // rbx
  const wchar_t *v17; // rdx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  char *v21; // rbx
  char *v22; // rbx
  char *v23; // rbx
  char *v24; // rbx
  __int64 v26; // [rsp+0h] [rbp-38h] BYREF

  v3 = 0;
  if ( a1 > 5 )
  {
    v18 = a1 - 6;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( !v19 )
      {
        v11 = 18;
        if ( *(_QWORD *)(a2 + 24) >= 0x12u )
        {
          v24 = *(char **)a2;
          *(_QWORD *)(a2 + 16) = 18;
          memmove_0(v24, L"ConnectedToNetwork", 0x24u);
          *((_WORD *)v24 + 18) = 0;
          return v3;
        }
        v9 = L"ConnectedToNetwork";
        goto LABEL_58;
      }
      v20 = v19 - 1;
      if ( !v20 )
      {
        v11 = 11;
        if ( *(_QWORD *)(a2 + 24) >= 0xBu )
        {
          v23 = *(char **)a2;
          *(_QWORD *)(a2 + 16) = 11;
          memmove_0(v23, L"ScreenOnOff", 0x16u);
          *((_WORD *)v23 + 11) = 0;
          return v3;
        }
        v9 = L"ScreenOnOff";
        goto LABEL_58;
      }
      v6 = v20 - 1;
      if ( !v6 )
      {
        v11 = 10;
        if ( *(_QWORD *)(a2 + 24) >= 0xAu )
        {
          v22 = *(char **)a2;
          *(_QWORD *)(a2 + 16) = 10;
          memmove_0(v22, L"NewAccount", 0x14u);
          *((_WORD *)v22 + 10) = 0;
          return v3;
        }
        v9 = L"NewAccount";
        goto LABEL_58;
      }
      if ( v6 != 1 )
        goto LABEL_35;
      v7 = 22;
      if ( *(_QWORD *)(a2 + 24) >= 0x16u )
      {
        v21 = *(char **)a2;
        *(_QWORD *)(a2 + 16) = 22;
        memmove_0(v21, L"ProtectionStateChanged", 0x2Cu);
        *((_WORD *)v21 + 22) = 0;
        return v3;
      }
      v9 = L"ProtectionStateChanged";
LABEL_14:
      v11 = v7;
LABEL_58:
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          (char **)a2,
          v11,
          a2,
          v9);
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v15,
              (unsigned int)&v26,
              -2147024882,
              (const char *)(unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
              25,
              "CHR(((HRESULT)0x8007000EL))");
          v3 = -2147024882;
          __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180012020);
        }
      }
      return v3;
    }
    if ( *(_QWORD *)(a2 + 24) < 0xDu )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)a2,
        0xDu,
        a2,
        L"AccountChange");
      return v3;
    }
    v16 = *(char **)a2;
    *(_QWORD *)(a2 + 16) = 13;
    v17 = L"AccountChange";
LABEL_52:
    memmove_0(v16, v17, 0x1Au);
    *((_WORD *)v16 + 13) = 0;
    return v3;
  }
  if ( a1 == 5 )
  {
    v11 = 13;
    if ( *(_QWORD *)(a2 + 24) < 0xDu )
    {
      v9 = L"SettingChange";
      goto LABEL_58;
    }
    v16 = *(char **)a2;
    *(_QWORD *)(a2 + 16) = 13;
    v17 = L"SettingChange";
    goto LABEL_52;
  }
  if ( !a1 )
  {
    v11 = 7;
    if ( *(_QWORD *)(a2 + 24) >= 7u )
    {
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v14 = (char *)a2;
      else
        v14 = *(char **)a2;
      *(_QWORD *)(a2 + 16) = 7;
      memmove_0(v14, L"Unknown", 0xEu);
      *((_WORD *)v14 + 7) = 0;
      return v3;
    }
    v9 = L"Unknown";
    goto LABEL_58;
  }
  v4 = a1 - 1;
  if ( !v4 )
  {
    v11 = 15;
    if ( *(_QWORD *)(a2 + 24) >= 0xFu )
    {
      v13 = *(char **)a2;
      *(_QWORD *)(a2 + 16) = 15;
      memmove_0(v13, L"FirstTimeSignIn", 0x1Eu);
      *((_WORD *)v13 + 15) = 0;
      return v3;
    }
    v9 = L"FirstTimeSignIn";
    goto LABEL_58;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v11 = 8;
    if ( *(_QWORD *)(a2 + 24) >= 8u )
    {
      v12 = *(char **)a2;
      *(_QWORD *)(a2 + 16) = 8;
      memmove_0(v12, L"Periodic", 0x10u);
      *((_WORD *)v12 + 8) = 0;
      return v3;
    }
    v9 = L"Periodic";
    goto LABEL_58;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v7 = 14;
    if ( *(_QWORD *)(a2 + 24) >= 0xEu )
    {
      v10 = *(char **)a2;
      *(_QWORD *)(a2 + 16) = 14;
      memmove_0(v10, L"SimCardChanged", 0x1Cu);
      *((_WORD *)v10 + 14) = 0;
      return v3;
    }
    v9 = L"SimCardChanged";
    goto LABEL_14;
  }
  if ( v6 == 1 )
  {
    v7 = 20;
    if ( *(_QWORD *)(a2 + 24) >= 0x14u )
    {
      v8 = *(char **)a2;
      *(_QWORD *)(a2 + 16) = 20;
      memmove_0(v8, L"OSUpgradeToThreshold", 0x28u);
      *((_WORD *)v8 + 20) = 0;
      return v3;
    }
    v9 = L"OSUpgradeToThreshold";
    goto LABEL_14;
  }
LABEL_35:
  v3 = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v6,
      a2,
      -2147024809,
      (const char *)(unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      20,
      "CHR(((HRESULT)0x80070057L))");
  return v3;
}

```

## disassembly

```asm
0x180011cf4  mov     [rsp+arg_8], rbx
0x180011cf9  push    rdi
0x180011cfa  sub     rsp, 30h
0x180011cfe  mov     r8, rdx
0x180011d01  xor     edi, edi
0x180011d03  cmp     ecx, 5
0x180011d06  jg      loc_180011E96
0x180011d0c  jz      loc_180011E6F
0x180011d12  test    ecx, ecx
0x180011d14  jz      loc_180011E22
0x180011d1a  sub     ecx, 1
0x180011d1d  jz      loc_180011DE9
0x180011d23  sub     ecx, 1
0x180011d26  jz      loc_180011DB0
0x180011d2c  sub     ecx, 1
0x180011d2f  jz      short loc_180011D71
0x180011d31  cmp     ecx, 1
0x180011d34  jnz     loc_180011EBB
0x180011d3a  lea     eax, [rdi+14h]
0x180011d3d  cmp     [rdx+18h], rax
0x180011d41  jb      short loc_180011D68
0x180011d43  mov     rbx, [rdx]
0x180011d46  mov     [rdx+10h], rax
0x180011d4a  lea     r8d, [rdi+28h]; Size
0x180011d4e  lea     rdx, aOsupgradetothr; "OSUpgradeToThreshold"
0x180011d55  mov     rcx, rbx; void *
0x180011d58  call    memmove_0
0x180011d5d  xor     eax, eax
0x180011d5f  mov     [rbx+28h], ax
0x180011d63  jmp     loc_18001201E
0x180011d68  lea     r9, aOsupgradetothr; "OSUpgradeToThreshold"
0x180011d6f  jmp     short loc_180011DA8
0x180011d71  mov     eax, 0Eh
0x180011d76  cmp     [rdx+18h], rax
0x180011d7a  jb      short loc_180011DA1
0x180011d7c  mov     rbx, [rdx]
0x180011d7f  mov     [rdx+10h], rax
0x180011d83  lea     r8d, [rax+0Eh]; Size
0x180011d87  lea     rdx, aSimcardchanged; "SimCardChanged"
0x180011d8e  mov     rcx, rbx; void *
0x180011d91  call    memmove_0
0x180011d96  xor     eax, eax
0x180011d98  mov     [rbx+1Ch], ax
0x180011d9c  jmp     loc_18001201E
0x180011da1  lea     r9, aSimcardchanged; "SimCardChanged"
0x180011da8  mov     rdx, rax
0x180011dab  jmp     loc_180011E62
0x180011db0  mov     edx, 8
0x180011db5  cmp     [r8+18h], rdx
0x180011db9  jb      short loc_180011DE0
0x180011dbb  mov     rbx, [r8]
0x180011dbe  mov     [r8+10h], rdx
0x180011dc2  lea     r8d, [rdx+8]; Size
0x180011dc6  lea     rdx, aPeriodic; "Periodic"
0x180011dcd  mov     rcx, rbx; void *
0x180011dd0  call    memmove_0
0x180011dd5  xor     eax, eax
0x180011dd7  mov     [rbx+10h], ax
0x180011ddb  jmp     loc_18001201E
0x180011de0  lea     r9, aPeriodic; "Periodic"
0x180011de7  jmp     short loc_180011E62
0x180011de9  mov     edx, 0Fh
0x180011dee  cmp     [r8+18h], rdx
0x180011df2  jb      short loc_180011E19
0x180011df4  mov     rbx, [r8]
0x180011df7  mov     [r8+10h], rdx
0x180011dfb  lea     r8d, [rdx+0Fh]; Size
0x180011dff  lea     rdx, aFirsttimesigni; "FirstTimeSignIn"
0x180011e06  mov     rcx, rbx; void *
0x180011e09  call    memmove_0
0x180011e0e  xor     eax, eax
0x180011e10  mov     [rbx+1Eh], ax
0x180011e14  jmp     loc_18001201E
0x180011e19  lea     r9, aFirsttimesigni; "FirstTimeSignIn"
0x180011e20  jmp     short loc_180011E62
0x180011e22  mov     edx, 7
0x180011e27  cmp     [r8+18h], rdx
0x180011e2b  jb      short loc_180011E5B
0x180011e2d  jbe     short loc_180011E34
0x180011e2f  mov     rbx, [r8]
0x180011e32  jmp     short loc_180011E37
0x180011e34  mov     rbx, r8
0x180011e37  mov     [r8+10h], rdx
0x180011e3b  mov     r8d, 0Eh; Size
0x180011e41  lea     rdx, aUnknown; "Unknown"
0x180011e48  mov     rcx, rbx; void *
0x180011e4b  call    memmove_0
0x180011e50  xor     eax, eax
0x180011e52  mov     [rbx+0Eh], ax
0x180011e56  jmp     loc_18001201E
0x180011e5b  lea     r9, aUnknown; "Unknown"
0x180011e62  mov     rcx, r8
0x180011e65  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180011e6a  jmp     loc_18001201E
0x180011e6f  mov     edx, 0Dh
0x180011e74  cmp     [r8+18h], rdx
0x180011e78  jb      short loc_180011E8D
0x180011e7a  mov     rbx, [r8]
0x180011e7d  mov     [r8+10h], rdx
0x180011e81  lea     rdx, aSettingchange; "SettingChange"
0x180011e88  jmp     loc_180011FF8
0x180011e8d  lea     r9, aSettingchange; "SettingChange"
0x180011e94  jmp     short loc_180011E62
0x180011e96  sub     ecx, 6
0x180011e99  jz      loc_180011FDF
0x180011e9f  sub     ecx, 1
0x180011ea2  jz      loc_180011FA6
0x180011ea8  sub     ecx, 1
0x180011eab  jz      loc_180011F6A
0x180011eb1  sub     ecx, 1
0x180011eb4  jz      short loc_180011F2E
0x180011eb6  cmp     ecx, 1
0x180011eb9  jz      short loc_180011EF2
0x180011ebb  mov     edi, 80070057h
0x180011ec0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011ec7  jz      short loc_180011EED
0x180011ec9  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x80070057L))"
0x180011ed0  mov     [rsp+38h+var_10], rax
0x180011ed5  mov     [rsp+38h+var_18], 514h
0x180011edd  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180011ee4  mov     r8d, edi
0x180011ee7  call    McTemplateU0dsqs_EventWriteTransfer
0x180011eec  nop
0x180011eed  jmp     loc_180012024
0x180011ef2  mov     eax, 16h
0x180011ef7  cmp     [rdx+18h], rax
0x180011efb  jb      short loc_180011F22
0x180011efd  mov     rbx, [rdx]
0x180011f00  mov     [rdx+10h], rax
0x180011f04  lea     r8d, [rax+16h]; Size
0x180011f08  lea     rdx, aProtectionstat_1; "ProtectionStateChanged"
0x180011f0f  mov     rcx, rbx; void *
0x180011f12  call    memmove_0
0x180011f17  xor     eax, eax
0x180011f19  mov     [rbx+2Ch], ax
0x180011f1d  jmp     loc_18001201E
0x180011f22  lea     r9, aProtectionstat_1; "ProtectionStateChanged"
0x180011f29  jmp     loc_180011DA8
0x180011f2e  mov     edx, 0Ah
0x180011f33  cmp     [r8+18h], rdx
0x180011f37  jb      short loc_180011F5E
0x180011f39  mov     rbx, [r8]
0x180011f3c  mov     [r8+10h], rdx
0x180011f40  lea     r8d, [rdx+0Ah]; Size
0x180011f44  lea     rdx, aNewaccount; "NewAccount"
0x180011f4b  mov     rcx, rbx; void *
0x180011f4e  call    memmove_0
0x180011f53  xor     eax, eax
0x180011f55  mov     [rbx+14h], ax
0x180011f59  jmp     loc_18001201E
0x180011f5e  lea     r9, aNewaccount; "NewAccount"
0x180011f65  jmp     loc_180011E62
0x180011f6a  mov     edx, 0Bh
0x180011f6f  cmp     [r8+18h], rdx
0x180011f73  jb      short loc_180011F9A
0x180011f75  mov     rbx, [r8]
0x180011f78  mov     [r8+10h], rdx
0x180011f7c  lea     r8d, [rdx+0Bh]; Size
0x180011f80  lea     rdx, aScreenonoff; "ScreenOnOff"
0x180011f87  mov     rcx, rbx; void *
0x180011f8a  call    memmove_0
0x180011f8f  xor     eax, eax
0x180011f91  mov     [rbx+16h], ax
0x180011f95  jmp     loc_18001201E
0x180011f9a  lea     r9, aScreenonoff; "ScreenOnOff"
0x180011fa1  jmp     loc_180011E62
0x180011fa6  mov     edx, 12h
0x180011fab  cmp     [r8+18h], rdx
0x180011faf  jb      short loc_180011FD3
0x180011fb1  mov     rbx, [r8]
0x180011fb4  mov     [r8+10h], rdx
0x180011fb8  lea     r8d, [rdx+12h]; Size
0x180011fbc  lea     rdx, aConnectedtonet; "ConnectedToNetwork"
0x180011fc3  mov     rcx, rbx; void *
0x180011fc6  call    memmove_0
0x180011fcb  xor     eax, eax
0x180011fcd  mov     [rbx+24h], ax
0x180011fd1  jmp     short loc_18001201E
0x180011fd3  lea     r9, aConnectedtonet; "ConnectedToNetwork"
0x180011fda  jmp     loc_180011E62
0x180011fdf  mov     edx, 0Dh
0x180011fe4  cmp     [r8+18h], rdx
0x180011fe8  jb      short loc_18001200E
0x180011fea  mov     rbx, [r8]
0x180011fed  mov     [r8+10h], rdx
0x180011ff1  lea     rdx, aAccountchange; "AccountChange"
0x180011ff8  mov     r8d, 1Ah; Size
0x180011ffe  mov     rcx, rbx; void *
0x180012001  call    memmove_0
0x180012006  xor     eax, eax
0x180012008  mov     [rbx+1Ah], ax
0x18001200c  jmp     short loc_18001201E
0x18001200e  lea     r9, aAccountchange; "AccountChange"
0x180012015  mov     rcx, r8
0x180012018  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001201d  nop
0x18001201e  jmp     short loc_180012024
0x180012020  mov     edi, [rsp+38h+arg_0]
0x180012024  mov     eax, edi
0x180012026  mov     rbx, [rsp+38h+arg_8]
0x18001202b  add     rsp, 30h
0x18001202f  pop     rdi
0x180012030  retn
```
