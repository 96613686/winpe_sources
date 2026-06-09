# MdmHttpWrapper::RegistrationTriggerToString(MdmRegistrationTrigger,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800120d0`
- end: `0x18001240e`
- name: `?RegistrationTriggerToString@MdmHttpWrapper@@CAJW4MdmRegistrationTrigger@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `830`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c6e8`
- `0x18000edc0`

## callees

- `0x1800028e4`
- `0x1800065c0`
- `0x1800120d0`
- `0x18001dbfc`

## string_xrefs

- `0x1800122b9`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::RegistrationTriggerToString(int a1, __int64 a2)
{
  unsigned int v3; // edi
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  __int64 v7; // rax
  _WORD *v8; // rbx
  const wchar_t *v9; // r9
  _WORD *v10; // rbx
  __int64 v11; // rdx
  _WORD *v12; // rbx
  _WORD *v13; // rbx
  _WORD *v14; // rbx
  int v15; // ecx
  _WORD *v16; // rbx
  const wchar_t *v17; // rdx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  _WORD *v21; // rbx
  _WORD *v22; // rbx
  _WORD *v23; // rbx
  _WORD *v24; // rbx
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
          v24 = *(_WORD **)a2;
          *(_QWORD *)(a2 + 16) = 18;
          memmove_0(v24, L"ConnectedToNetwork", 0x24u);
          v24[18] = 0;
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
          v23 = *(_WORD **)a2;
          *(_QWORD *)(a2 + 16) = 11;
          memmove_0(v23, L"ScreenOnOff", 0x16u);
          v23[11] = 0;
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
          v22 = *(_WORD **)a2;
          *(_QWORD *)(a2 + 16) = 10;
          memmove_0(v22, L"NewAccount", 0x14u);
          v22[10] = 0;
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
        v21 = *(_WORD **)a2;
        *(_QWORD *)(a2 + 16) = 22;
        memmove_0(v21, L"ProtectionStateChanged", 0x2Cu);
        v21[22] = 0;
        return v3;
      }
      v9 = L"ProtectionStateChanged";
LABEL_14:
      v11 = v7;
LABEL_58:
      try
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a2, v11, a2, v9);
      }
      catch ( std::bad_alloc )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v15,
            (unsigned int)&v26,
            -2147024882,
            "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
            25,
            "CHR(((HRESULT)0x8007000EL))");
        return (unsigned int)-2147024882;
      }
      return v3;
    }
    if ( *(_QWORD *)(a2 + 24) < 0xDu )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        a2,
        13,
        a2,
        L"AccountChange");
      return v3;
    }
    v16 = *(_WORD **)a2;
    *(_QWORD *)(a2 + 16) = 13;
    v17 = L"AccountChange";
LABEL_52:
    memmove_0(v16, v17, 0x1Au);
    v16[13] = 0;
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
    v16 = *(_WORD **)a2;
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
        v14 = (_WORD *)a2;
      else
        v14 = *(_WORD **)a2;
      *(_QWORD *)(a2 + 16) = 7;
      memmove_0(v14, L"Unknown", 0xEu);
      v14[7] = 0;
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
      v13 = *(_WORD **)a2;
      *(_QWORD *)(a2 + 16) = 15;
      memmove_0(v13, L"FirstTimeSignIn", 0x1Eu);
      v13[15] = 0;
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
      v12 = *(_WORD **)a2;
      *(_QWORD *)(a2 + 16) = 8;
      memmove_0(v12, L"Periodic", 0x10u);
      v12[8] = 0;
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
      v10 = *(_WORD **)a2;
      *(_QWORD *)(a2 + 16) = 14;
      memmove_0(v10, L"SimCardChanged", 0x1Cu);
      v10[14] = 0;
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
      v8 = *(_WORD **)a2;
      *(_QWORD *)(a2 + 16) = 20;
      memmove_0(v8, L"OSUpgradeToThreshold", 0x28u);
      v8[20] = 0;
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
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      20,
      "CHR(((HRESULT)0x80070057L))");
  return v3;
}

```

## disassembly

```asm
0x1800120d0  mov     [rsp+arg_8], rbx
0x1800120d5  push    rdi
0x1800120d6  sub     rsp, 30h
0x1800120da  mov     r8, rdx
0x1800120dd  xor     edi, edi
0x1800120df  cmp     ecx, 5
0x1800120e2  jg      loc_180012272
0x1800120e8  jz      loc_18001224B
0x1800120ee  test    ecx, ecx
0x1800120f0  jz      loc_1800121FE
0x1800120f6  sub     ecx, 1
0x1800120f9  jz      loc_1800121C5
0x1800120ff  sub     ecx, 1
0x180012102  jz      loc_18001218C
0x180012108  sub     ecx, 1
0x18001210b  jz      short loc_18001214D
0x18001210d  cmp     ecx, 1
0x180012110  jnz     loc_180012297
0x180012116  lea     eax, [rdi+14h]
0x180012119  cmp     [rdx+18h], rax
0x18001211d  jb      short loc_180012144
0x18001211f  mov     rbx, [rdx]
0x180012122  mov     [rdx+10h], rax
0x180012126  lea     r8d, [rdi+28h]; Size
0x18001212a  lea     rdx, aOsupgradetothr; "OSUpgradeToThreshold"
0x180012131  mov     rcx, rbx; void *
0x180012134  call    memmove_0
0x180012139  xor     eax, eax
0x18001213b  mov     [rbx+28h], ax
0x18001213f  jmp     loc_1800123FA
0x180012144  lea     r9, aOsupgradetothr; "OSUpgradeToThreshold"
0x18001214b  jmp     short loc_180012184
0x18001214d  mov     eax, 0Eh
0x180012152  cmp     [rdx+18h], rax
0x180012156  jb      short loc_18001217D
0x180012158  mov     rbx, [rdx]
0x18001215b  mov     [rdx+10h], rax
0x18001215f  lea     r8d, [rax+0Eh]; Size
0x180012163  lea     rdx, aSimcardchanged; "SimCardChanged"
0x18001216a  mov     rcx, rbx; void *
0x18001216d  call    memmove_0
0x180012172  xor     eax, eax
0x180012174  mov     [rbx+1Ch], ax
0x180012178  jmp     loc_1800123FA
0x18001217d  lea     r9, aSimcardchanged; "SimCardChanged"
0x180012184  mov     rdx, rax
0x180012187  jmp     loc_18001223E
0x18001218c  mov     edx, 8
0x180012191  cmp     [r8+18h], rdx
0x180012195  jb      short loc_1800121BC
0x180012197  mov     rbx, [r8]
0x18001219a  mov     [r8+10h], rdx
0x18001219e  lea     r8d, [rdx+8]; Size
0x1800121a2  lea     rdx, aPeriodic; "Periodic"
0x1800121a9  mov     rcx, rbx; void *
0x1800121ac  call    memmove_0
0x1800121b1  xor     eax, eax
0x1800121b3  mov     [rbx+10h], ax
0x1800121b7  jmp     loc_1800123FA
0x1800121bc  lea     r9, aPeriodic; "Periodic"
0x1800121c3  jmp     short loc_18001223E
0x1800121c5  mov     edx, 0Fh
0x1800121ca  cmp     [r8+18h], rdx
0x1800121ce  jb      short loc_1800121F5
0x1800121d0  mov     rbx, [r8]
0x1800121d3  mov     [r8+10h], rdx
0x1800121d7  lea     r8d, [rdx+0Fh]; Size
0x1800121db  lea     rdx, aFirsttimesigni; "FirstTimeSignIn"
0x1800121e2  mov     rcx, rbx; void *
0x1800121e5  call    memmove_0
0x1800121ea  xor     eax, eax
0x1800121ec  mov     [rbx+1Eh], ax
0x1800121f0  jmp     loc_1800123FA
0x1800121f5  lea     r9, aFirsttimesigni; "FirstTimeSignIn"
0x1800121fc  jmp     short loc_18001223E
0x1800121fe  mov     edx, 7
0x180012203  cmp     [r8+18h], rdx
0x180012207  jb      short loc_180012237
0x180012209  jbe     short loc_180012210
0x18001220b  mov     rbx, [r8]
0x18001220e  jmp     short loc_180012213
0x180012210  mov     rbx, r8
0x180012213  mov     [r8+10h], rdx
0x180012217  mov     r8d, 0Eh; Size
0x18001221d  lea     rdx, aUnknown; "Unknown"
0x180012224  mov     rcx, rbx; void *
0x180012227  call    memmove_0
0x18001222c  xor     eax, eax
0x18001222e  mov     [rbx+0Eh], ax
0x180012232  jmp     loc_1800123FA
0x180012237  lea     r9, aUnknown; "Unknown"
0x18001223e  mov     rcx, r8
0x180012241  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180012246  jmp     loc_1800123FA
0x18001224b  mov     edx, 0Dh
0x180012250  cmp     [r8+18h], rdx
0x180012254  jb      short loc_180012269
0x180012256  mov     rbx, [r8]
0x180012259  mov     [r8+10h], rdx
0x18001225d  lea     rdx, aSettingchange; "SettingChange"
0x180012264  jmp     loc_1800123D4
0x180012269  lea     r9, aSettingchange; "SettingChange"
0x180012270  jmp     short loc_18001223E
0x180012272  sub     ecx, 6
0x180012275  jz      loc_1800123BB
0x18001227b  sub     ecx, 1
0x18001227e  jz      loc_180012382
0x180012284  sub     ecx, 1
0x180012287  jz      loc_180012346
0x18001228d  sub     ecx, 1
0x180012290  jz      short loc_18001230A
0x180012292  cmp     ecx, 1
0x180012295  jz      short loc_1800122CE
0x180012297  mov     edi, 80070057h
0x18001229c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800122a3  jz      short loc_1800122C9
0x1800122a5  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x80070057L))"
0x1800122ac  mov     [rsp+38h+var_10], rax
0x1800122b1  mov     [rsp+38h+var_18], 514h
0x1800122b9  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800122c0  mov     r8d, edi
0x1800122c3  call    McTemplateU0dsqs_EventWriteTransfer
0x1800122c8  nop
0x1800122c9  jmp     loc_180012400
0x1800122ce  mov     eax, 16h
0x1800122d3  cmp     [rdx+18h], rax
0x1800122d7  jb      short loc_1800122FE
0x1800122d9  mov     rbx, [rdx]
0x1800122dc  mov     [rdx+10h], rax
0x1800122e0  lea     r8d, [rax+16h]; Size
0x1800122e4  lea     rdx, aProtectionstat_1; "ProtectionStateChanged"
0x1800122eb  mov     rcx, rbx; void *
0x1800122ee  call    memmove_0
0x1800122f3  xor     eax, eax
0x1800122f5  mov     [rbx+2Ch], ax
0x1800122f9  jmp     loc_1800123FA
0x1800122fe  lea     r9, aProtectionstat_1; "ProtectionStateChanged"
0x180012305  jmp     loc_180012184
0x18001230a  mov     edx, 0Ah
0x18001230f  cmp     [r8+18h], rdx
0x180012313  jb      short loc_18001233A
0x180012315  mov     rbx, [r8]
0x180012318  mov     [r8+10h], rdx
0x18001231c  lea     r8d, [rdx+0Ah]; Size
0x180012320  lea     rdx, aNewaccount; "NewAccount"
0x180012327  mov     rcx, rbx; void *
0x18001232a  call    memmove_0
0x18001232f  xor     eax, eax
0x180012331  mov     [rbx+14h], ax
0x180012335  jmp     loc_1800123FA
0x18001233a  lea     r9, aNewaccount; "NewAccount"
0x180012341  jmp     loc_18001223E
0x180012346  mov     edx, 0Bh
0x18001234b  cmp     [r8+18h], rdx
0x18001234f  jb      short loc_180012376
0x180012351  mov     rbx, [r8]
0x180012354  mov     [r8+10h], rdx
0x180012358  lea     r8d, [rdx+0Bh]; Size
0x18001235c  lea     rdx, aScreenonoff; "ScreenOnOff"
0x180012363  mov     rcx, rbx; void *
0x180012366  call    memmove_0
0x18001236b  xor     eax, eax
0x18001236d  mov     [rbx+16h], ax
0x180012371  jmp     loc_1800123FA
0x180012376  lea     r9, aScreenonoff; "ScreenOnOff"
0x18001237d  jmp     loc_18001223E
0x180012382  mov     edx, 12h
0x180012387  cmp     [r8+18h], rdx
0x18001238b  jb      short loc_1800123AF
0x18001238d  mov     rbx, [r8]
0x180012390  mov     [r8+10h], rdx
0x180012394  lea     r8d, [rdx+12h]; Size
0x180012398  lea     rdx, aConnectedtonet; "ConnectedToNetwork"
0x18001239f  mov     rcx, rbx; void *
0x1800123a2  call    memmove_0
0x1800123a7  xor     eax, eax
0x1800123a9  mov     [rbx+24h], ax
0x1800123ad  jmp     short loc_1800123FA
0x1800123af  lea     r9, aConnectedtonet; "ConnectedToNetwork"
0x1800123b6  jmp     loc_18001223E
0x1800123bb  mov     edx, 0Dh
0x1800123c0  cmp     [r8+18h], rdx
0x1800123c4  jb      short loc_1800123EA
0x1800123c6  mov     rbx, [r8]
0x1800123c9  mov     [r8+10h], rdx
0x1800123cd  lea     rdx, aAccountchange; "AccountChange"
0x1800123d4  mov     r8d, 1Ah; Size
0x1800123da  mov     rcx, rbx; void *
0x1800123dd  call    memmove_0
0x1800123e2  xor     eax, eax
0x1800123e4  mov     [rbx+1Ah], ax
0x1800123e8  jmp     short loc_1800123FA
0x1800123ea  lea     r9, aAccountchange; "AccountChange"
0x1800123f1  mov     rcx, r8
0x1800123f4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800123f9  nop
0x1800123fa  jmp     short loc_180012400
0x1800123fc  mov     edi, [rsp+38h+arg_0]
0x180012400  mov     eax, edi
0x180012402  mov     rbx, [rsp+38h+arg_8]
0x180012407  add     rsp, 30h
0x18001240b  pop     rdi
0x18001240c  retn
```
